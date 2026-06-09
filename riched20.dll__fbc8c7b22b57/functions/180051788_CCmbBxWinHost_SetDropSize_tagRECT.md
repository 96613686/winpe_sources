# CCmbBxWinHost::SetDropSize(tagRECT *)

- ea: `0x180051788`
- end: `0x18005182a`
- name: `?SetDropSize@CCmbBxWinHost@@IEAAXPEAUtagRECT@@@Z`
- size: `162`
- prototype: `void __fastcall(CCmbBxWinHost *__hidden this, struct tagRECT *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004f8e0`
- `0x180050874`

## callees

- `0x18004f05c`

## import_xrefs

- `USER32!MoveWindow` at `0x180051812`
- `USER32!MoveWindow` at `0x180051812`
- `USER32!ClientToScreen` at `0x1800517c5`
- `USER32!ClientToScreen` at `0x1800517da`
- `USER32!ClientToScreen` at `0x1800517c5`
- `USER32!ClientToScreen` at `0x1800517da`

## pseudocode

```c
void __fastcall CCmbBxWinHost::SetDropSize(CCmbBxWinHost *this, struct tagRECT *a2)
{
  HWND v4; // rcx
  struct tagPOINT v5; // [rsp+40h] [rbp+8h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp+10h] BYREF

  *((_DWORD *)this + 30) |= 2u;
  CCmbBxWinHost::HideListBox(this, 0, 0);
  v4 = (HWND)*((_QWORD *)this + 2);
  Point = *(struct tagPOINT *)&a2->left;
  v5 = *(struct tagPOINT *)&a2->right;
  ClientToScreen(v4, &Point);
  ClientToScreen(*((HWND *)this + 2), &v5);
  MoveWindow(*((HWND *)this + 16), Point.x, Point.y, v5.x - Point.x, v5.y - Point.y, 0);
}

```

## disassembly

```asm
0x180051788  mov     [rsp+arg_10], rbx
0x18005178d  push    rdi
0x18005178e  sub     rsp, 30h
0x180051792  or      dword ptr [rcx+78h], 2
0x180051796  mov     rbx, rdx
0x180051799  xor     edx, edx; int
0x18005179b  xor     r8d, r8d; int
0x18005179e  mov     rdi, rcx
0x1800517a1  call    ?HideListBox@CCmbBxWinHost@@QEAAHHH@Z; CCmbBxWinHost::HideListBox(int,int)
0x1800517a6  mov     rax, [rbx]
0x1800517a9  lea     rdx, [rsp+38h+Point]; lpPoint
0x1800517ae  mov     rcx, [rdi+10h]; hWnd
0x1800517b2  mov     qword ptr [rsp+38h+Point.x], rax
0x1800517b7  mov     eax, [rbx+8]
0x1800517ba  mov     [rsp+38h+arg_0.x], eax
0x1800517be  mov     eax, [rbx+0Ch]
0x1800517c1  mov     [rsp+38h+arg_0.y], eax
0x1800517c5  call    cs:__imp_ClientToScreen
0x1800517cc  nop     dword ptr [rax+rax+00h]
0x1800517d1  mov     rcx, [rdi+10h]; hWnd
0x1800517d5  lea     rdx, [rsp+38h+arg_0]; lpPoint
0x1800517da  call    cs:__imp_ClientToScreen
0x1800517e1  nop     dword ptr [rax+rax+00h]
0x1800517e6  mov     eax, [rsp+38h+arg_0.y]
0x1800517ea  mov     r8d, [rsp+38h+Point.y]; Y
0x1800517ef  sub     eax, r8d
0x1800517f2  mov     r9d, [rsp+38h+arg_0.x]
0x1800517f7  mov     rdx, qword ptr [rsp+38h+Point.x]; X
0x1800517fc  mov     rcx, [rdi+80h]; hWnd
0x180051803  sub     r9d, edx; nWidth
0x180051806  mov     [rsp+38h+bRepaint], 0; bRepaint
0x18005180e  mov     [rsp+38h+nHeight], eax; nHeight
0x180051812  call    cs:__imp_MoveWindow
0x180051819  nop     dword ptr [rax+rax+00h]
0x18005181e  mov     rbx, [rsp+38h+arg_10]
0x180051823  add     rsp, 30h
0x180051827  pop     rdi
0x180051828  retn
```
