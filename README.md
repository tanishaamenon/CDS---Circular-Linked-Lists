# Doubly Linked List

**Aim:** <br>
To study and implement Circular Linked List. <br>
<br>
**Theory:** <br>
A circular linked list is a modified form of a simple linked list in which instead of the terminating structure at the end of the list, the very first node is pointed to from the last node thereby forming a circular structure. This is true for both singly linked lists and doubly linked lists. In a circular singly linked list, every node in this case has a single pointer which points to another node termed the next node and the next node sometime called the last node in the structure completed in one circular direction points to the first structure in this case. In the case of circular doubly linked list, there exist two pointers in each node, one pointing to the next node and the other on the previous node, where the last node is connected to the first node and the first node is directed towards the last node.<br>

Advantages of Doubly Linked Lists: <br>
&#8594; No Null Termination <br>
&#8594; Efficient Cycling <br>
&#8594; Can Traverse from Any Node <br>
<br>

Disadvantages of Doubly Linked Lists: <br>
&#8594; Infinite Loop Risk <br>
&#8594; Complex Insertions and Deletions <br>
<br>

**Code:** <br>
<br>

```
#include <iostream>
using namespace std;

struct node 
{
    int data;     
    node* next;  
};

node* createnode(int value) 
{
    node* newnode = new node(); 
    newnode->data = value;      
    newnode->next = nullptr;    
    return newnode;
}

void insertdata(node*& head, int value) 
{
    node* newnode = createnode(value);

    if (head == nullptr) 
    {
        head = newnode;
        newnode->next = head; 
    } 
    
    else 
    {
        
        node* temp = head;
        while (temp->next != head) 
        {
            temp = temp->next;
        }
        temp->next = newnode;
        newnode->next = head;
    }
}

void display(node* head) 
{
    if (head == nullptr) 
    {
        cout << "List is empty!" << endl;
        return;
    }

    node* temp = head;

    do 
    {
        cout << temp->data << " -> ";
        temp = temp->next;
    } 
    while (temp != head);

    cout << "(back to head)" << endl;
}

int main() 
{
    node* head = nullptr;

    insertdata(head, 10);
    insertdata(head, 20);
    insertdata(head, 30);
    insertdata(head, 40);

    
    cout << "Circular Linked List: ";
    display(head);

    return 0;
}

```
<br>


**Outputs:**  <br>
<br>
![expcll output](https://github.com/tanishaamenon/CDS---Circular-Linked-Lists/blob/main/exp17cll.JPG) <br>
<br>

**Conclusion:** <br>
&#8594; We learnt about circular linked list in C++. <br>
&#8594; We learnt the use case of circular linked list in C++. <br>
*******
<br>
