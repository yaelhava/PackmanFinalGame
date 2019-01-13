# PackmanFinalGame
ReadMe - Pacman final game
מגישות: יעל חווה 315745828 ונעמה הרטוב 315745828
מטרת המשחק: אכילת כל הפירות שבלוח, תוך כדי צבירת ניקוד מקסימלי.
אופן המשחק: אתחול המשחק הוא ע"י העלאת קובץ של נתוני הלוח. המשתמש יוכל לבחור איזה מבין המשחקים הוא רוצה לשחק ולפי זה לוח המשחק יתעדכן.
לדוגמה העלאת הקובץ:

במשחק ישנם פירות אשר מטרת השחקן היא לאכול אותם. במהלך המשחק השחקן יוכל להיפגש בכמה סוגי שחקנים אחרים: (אותם אובייקטים לא בכל משחק נמצאים, תלוי בקובץ הלוח).
רוחות- רוחות אשר השחקן לא ירצה להיפגש איתן, הרוחות מורידות לשחקן ניקוד ברגע שמגיעות אליו.
קירות- הקירות קבועים, אין באפשרות השחקן לעבור דרכם.
פאקמנים אחרים- ישנם עוד פאקמנים במשחק אשר גם יכולים לאכול פירות וככה לגרום לשחקן הראשי לצבור פחות נקודות. בנוסף השחקן הראשי יוכל לאכול את אותם פאקמנים ולקבל גם עליהם ניקוד.
איך לשחק: למשתמש יש 2 אפשרויות למשחק:
1.	משחק אנושי- המשתמש בוחר משחק שבו רוצה לשחק ובנוסף בוחר את המיקום ההתחלתי של השחקן שלו. לאחר מכן הוא מתחיל את המשחק ע"י לחיצה על הכפתור "RUN" . ברגע שהשחקן התחיל את המשחק הוא שולט לאן איזה כיוון השחקן שלו ירוץ במהלך המשחק, שליטה זו נעשית ע"י לחיצת עכבר על המסך, לאחר הלחיצה השחקן ישנה את כיוון התזוזה שלו לפי הכיוון של איפה שהמשתמש לחץ על המסך. ככה המשתמש יוכל לשחק בעצמו ולהחליט כיצד השחקן שלו יזוז על המסך ואיזה פירות יאכל ואיך יתחמק מרוחות אם ירצה.
2.	משחק ע"י מערכת אוטומטית- המשתמש בוחר משחק שבו ירצה לשחק ובוחר את המיקום ההתחלתי של השחקן שלו. כעת תפקיד המשתמש הסתיים ולאחר לחיצה על הכפתור 
"Run Algo" המערכת תחשב לבד איך הכי כדאי לה לאכול את הפירות ותזיז את השחקן לפי המסלול אותו חישבה. 

בסוף המשחק השחקן יוכל לראות את התוצאה שלו לפי המשתמש שלו. בנוסף יוכל לראות את התוצאות שלו ביחס לתוצאות אחרות ואת הממוצע של כולם. כל זה נמצא בתוך הכפתור MYSQL ושם תיפתח טבלה שבה מפורט כל החישובים.


מבנה הפרויקט
 המשחק מחולק למחלקות וחבילות, כך שכל אחד אחראי על תפקידו וביחד נוצר המשחק עצמו. 
TheGame Packet
חבילה זו אחראית על כל האובייקטים הנמצאים במשחק. להלן המחלקות אשר ממשות חבילה זו:
Block: מחלקה המייצגת את הקירות שבמשחק.
Fruit: מחלקה המייצגת את הפירות שבמשחק
FruitMetaData: מחלקה המחזיקה חלק מן המידע על הפירות.
Game: מחלקה המחזיקה את כל האלמנטים של המשחק.
Ghost: מחלקה המייצגת את הרוחות שבמשחק.
Packman: מחלקה המייצגת את הפאקמנים שבמשחק.
PackmanMetaData: מחלקה המחזיקה חלק מן המידע על הפאקמנים.
Player: מחלקה המייצגת את השחקן של המשתמש.
GUI Packet
בחבילה זו נהפוך את המשחק למוחשי , נוכל להפעיל דרכו את כל האלמנטים של המשחק ולראות אותו מתפקד.
החבילה מיוצגת ע"י מחלקה הנקראת MyFrame אשר בה נעשים כל החישובים וההמרות הנצרכים כדי לגרום למשחק להפוך למוחשי ולפעול. 
Geom Packet
במחלקה זו ייוצגו כל המבנים הגיאומטריים שבמשחק.
Line: ייצוג קו, דרך בין 2 נקודות במשחק.
Point3D: הגדרת נקודה על המשחק וחישובה.
Coords Packet
בחבילה זו יתבצעו כל החישובים על הנקודות והמרתם למפה. 
Mycoords: חישוב הנקודות.
Map: המרה של הנקודות לפי המפה מפיקסל לנקודת GPS וכן ההפך. בנוסף חישוב מרחק בין 2 נקודות והזווית ביניהם.



Algorithm Packet
חבילה זו מחשבת את האלגוריתם עצמו. 
DistanceComperator: השוואה בין גודל המרחקים.
Edge: בדיקת דרך בין 2 נקודות, האם הדרך עוברת דרך קירות או לא. אם כן המסלול לא יכנס לחישוב האלגוריתם. 
FastestRoad: מחלקה המחזיקה את המסלול המהיר ביותר מבין הדרכים בין השחקן לפירות. במחלקה זו יוחזק המסלול, הפרי והמרחק.
GraphBlock: חישוב המסלולים בין הקירות.
PointNode: מחלקה המחזיקה את הנקודה ואת הID של נקודה מסוימת בגרף.
RunAlgo: מחלקה זו מחשבת את המסלול המהיר ביותר בין פרי לשחקן. לאחר החישוב היא תקח את המסלול הכי מהיר ותזיז את הפאקמן אל המיקום של הפרי, האלגוריתם ימשיך לעבוד עד שכל הפירות יאכלו או שזמן המשחק ייגמר.
Threads Packet
בחבילה זו יופעל הthread על חישוב האלגוריתם כדי להפעיל את ריצת השחקן על מסלול אכילת הפירות.
RoadThread: מחלקה המבצעת את פעולת הthread על מסלול אכילת הפירות.

משחק מהנה!
😊