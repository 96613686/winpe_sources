# CAVLNode::remove_node(CAVLNode *)

- ea: `0x140021798`
- end: `0x14002182c`
- name: `?remove_node@CAVLNode@@QEAAPEAV1@PEAV1@@Z`
- size: `148`
- prototype: `struct CAVLNode *__fastcall(CAVLNode *__hidden this, struct CAVLNode *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14001ed8c`
- `0x140021798`

## callees

- `0x14002155c`
- `0x14002159c`
- `0x140021760`
- `0x140021798`
- `0x140021834`

## pseudocode

```c
struct CAVLNode *__fastcall CAVLNode::remove_node(struct CAVLNode **this, struct CAVLNode *a2)
{
  __int64 v2; // r8
  struct CAVLNode **v3; // rbx
  CAVLNode *v4; // rdi
  struct CAVLNode *v6; // rdx
  struct CAVLNode *v7; // rax
  CAVLNode *v8; // r8
  CAVLNode *v9; // rsi
  struct CAVLNode *v10; // rax
  CAVLNode *v11; // r8
  CAVLNode *v12; // rcx

  v2 = *((_QWORD *)a2 + 1);
  v3 = (struct CAVLNode **)a2;
  v4 = *(CAVLNode **)a2;
  if ( v2 )
  {
    v7 = CAVLNode::Lmost(*(struct CAVLNode **)(v2 + 16));
    v9 = v7;
    if ( v7 )
    {
      v10 = CAVLNode::remove_node(v8, v7);
      CAVLNode::right(v9, v10);
      v8 = v9;
    }
    CAVLNode::left(v8, v3[2]);
    v12 = v11;
    goto LABEL_10;
  }
  v6 = (struct CAVLNode *)*((_QWORD *)a2 + 2);
  while ( v3 != this )
  {
    if ( v3 == *((struct CAVLNode ***)v4 + 1) )
      CAVLNode::right(v4, v6);
    else
      CAVLNode::left(v4, v6);
    v3 = (struct CAVLNode **)v4;
    v4 = *(CAVLNode **)v4;
    v12 = (CAVLNode *)v3;
LABEL_10:
    v6 = CAVLNode::balance(v12);
  }
  return v6;
}

```

## disassembly

```asm
0x140021798  push    rbx
0x14002179a  push    rbp
0x14002179b  push    rsi
0x14002179c  push    rdi
0x14002179d  sub     rsp, 28h
0x1400217a1  mov     r8, [rdx+8]
0x1400217a5  mov     rbx, rdx
0x1400217a8  mov     rdi, [rdx]
0x1400217ab  mov     rbp, rcx
0x1400217ae  test    r8, r8
0x1400217b1  jnz     short loc_1400217B9
0x1400217b3  mov     rdx, [rdx+10h]
0x1400217b7  jmp     short loc_14002181A
0x1400217b9  mov     rcx, [r8+10h]; struct CAVLNode *
0x1400217bd  call    ?Lmost@CAVLNode@@SAPEAV1@PEAV1@@Z; CAVLNode::Lmost(CAVLNode *)
0x1400217c2  mov     rsi, rax
0x1400217c5  test    rax, rax
0x1400217c8  jz      short loc_1400217E3
0x1400217ca  mov     rdx, rax; struct CAVLNode *
0x1400217cd  mov     rcx, r8; this
0x1400217d0  call    ?remove_node@CAVLNode@@QEAAPEAV1@PEAV1@@Z; CAVLNode::remove_node(CAVLNode *)
0x1400217d5  mov     rdx, rax; struct CAVLNode *
0x1400217d8  mov     rcx, rsi; this
0x1400217db  call    ?right@CAVLNode@@AEAAXPEAV1@@Z; CAVLNode::right(CAVLNode *)
0x1400217e0  mov     r8, rsi
0x1400217e3  mov     rdx, [rbx+10h]; struct CAVLNode *
0x1400217e7  mov     rcx, r8; this
0x1400217ea  call    ?left@CAVLNode@@AEAAXPEAV1@@Z; CAVLNode::left(CAVLNode *)
0x1400217ef  mov     rcx, r8
0x1400217f2  jmp     short loc_140021812
0x1400217f4  mov     rcx, rdi; this
0x1400217f7  cmp     rbx, [rdi+8]
0x1400217fb  jnz     short loc_140021804
0x1400217fd  call    ?right@CAVLNode@@AEAAXPEAV1@@Z; CAVLNode::right(CAVLNode *)
0x140021802  jmp     short loc_140021809
0x140021804  call    ?left@CAVLNode@@AEAAXPEAV1@@Z; CAVLNode::left(CAVLNode *)
0x140021809  mov     rbx, rdi
0x14002180c  mov     rdi, [rdi]
0x14002180f  mov     rcx, rbx; this
0x140021812  call    ?balance@CAVLNode@@AEAAPEAV1@XZ; CAVLNode::balance(void)
0x140021817  mov     rdx, rax; struct CAVLNode *
0x14002181a  cmp     rbx, rbp
0x14002181d  jnz     short loc_1400217F4
0x14002181f  mov     rax, rdx
0x140021822  add     rsp, 28h
0x140021826  pop     rdi
0x140021827  pop     rsi
0x140021828  pop     rbp
0x140021829  pop     rbx
0x14002182a  retn
```
