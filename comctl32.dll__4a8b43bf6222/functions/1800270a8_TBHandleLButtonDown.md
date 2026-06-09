# TBHandleLButtonDown

- ea: `0x1800270a8`
- end: `0x18002721a`
- name: `TBHandleLButtonDown`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180027f8c`
- `0x18002aab0`

## callees

- `0x1800115f0`
- `0x180018e04`
- `0x1800197bc`
- `0x1800260b8`
- `0x1800270a8`
- `0x180029290`
- `0x180029ac4`
- `0x18004c388`

## import_xrefs

- `USER32!SetCapture` at `0x180027172`
- `USER32!SetCapture` at `0x18002718d`
- `USER32!SetCapture` at `0x180027172`
- `USER32!SetCapture` at `0x18002718d`
- `USER32!PtInRect` at `0x180027149`
- `USER32!PtInRect` at `0x180027149`
- `USER32!UpdateWindow` at `0x1800271b3`
- `USER32!UpdateWindow` at `0x1800271b3`

## pseudocode

```c
void __fastcall TBHandleLButtonDown(__int64 a1, int a2, int a3)
{
  HWND v5; // rbp
  __int64 v6; // rax
  __int64 v7; // rsi
  char v8; // al
  __int64 v9; // rdx
  char v10; // al
  POINT pt; // [rsp+20h] [rbp-38h]
  RECT rc; // [rsp+28h] [rbp-30h] BYREF

  if ( a3 >= 0 && a3 < *(_DWORD *)(a1 + 200) )
  {
    v5 = *(HWND *)a1;
    pt.x = (unsigned __int16)a2;
    pt.y = HIWORD(a2);
    v6 = *(_QWORD *)(a1 + 80);
    rc = 0;
    v7 = v6 + 40LL * a3;
    if ( (*(_BYTE *)(v7 + 9) & 0x88) != 0 )
    {
      TB_GetItemRect(a1, (unsigned int)a3, &rc);
      rc.left = rc.right - *(_DWORD *)(a1 + 208);
    }
    v8 = *(_BYTE *)(v7 + 9);
    if ( (v8 & 0x88) == 0 || (*(_BYTE *)(a1 + 56) & 1) != 0 && (v8 & 8) != 0 && v8 >= 0 && !PtInRect(&rc, pt) )
    {
      *(_QWORD *)(a1 + 88) = v7;
      SetCapture(v5);
      v10 = *(_BYTE *)(v7 + 8);
      if ( (v10 & 4) != 0 )
      {
        *(_BYTE *)(v7 + 8) = v10 | 2;
        InvalidateButton(a1, v7, 1);
        UpdateWindow(v5);
        MyNotifyWinEvent(32778, v5, 4294967292LL);
      }
      *(_DWORD *)(a1 + 316) &= ~0x200u;
      v9 = *(_QWORD *)(a1 + 88);
      if ( !v9 )
        goto LABEL_16;
    }
    else
    {
      if ( (unsigned int)TBToggleDropDown((_QWORD *)a1, a3, 1) )
        return;
      *(_QWORD *)(a1 + 88) = v7;
      SetCapture(v5);
      *(_DWORD *)(a1 + 316) &= ~0x200u;
      v9 = *(_QWORD *)(a1 + 88);
    }
    SendItemNotify(a1, *(unsigned int *)(v9 + 4), 4294966595LL);
LABEL_16:
    GetMessagePosClient(*(HWND *)a1, (LPPOINT)(a1 + 96));
  }
}

```

## disassembly

```asm
0x1800270a8  test    r8d, r8d
0x1800270ab  js      locret_180027219
0x1800270b1  mov     [rsp+arg_18], rbx
0x1800270b6  push    rbp
0x1800270b7  push    rsi
0x1800270b8  push    rdi
0x1800270b9  sub     rsp, 40h
0x1800270bd  mov     rax, cs:__security_cookie
0x1800270c4  xor     rax, rsp
0x1800270c7  mov     [rsp+58h+var_20], rax
0x1800270cc  movsxd  rdi, r8d
0x1800270cf  mov     rbx, rcx
0x1800270d2  cmp     edi, [rcx+0C8h]
0x1800270d8  jge     loc_180027200
0x1800270de  mov     rbp, [rcx]
0x1800270e1  xorps   xmm0, xmm0
0x1800270e4  movzx   eax, dx
0x1800270e7  lea     rcx, [rdi+rdi*4]
0x1800270eb  shr     rdx, 10h
0x1800270ef  mov     [rsp+58h+pt.x], eax
0x1800270f3  movzx   eax, dx
0x1800270f6  mov     [rsp+58h+pt.y], eax
0x1800270fa  mov     rax, [rbx+50h]
0x1800270fe  movups  xmmword ptr [rsp+58h+rc.left], xmm0
0x180027103  lea     rsi, [rax+rcx*8]
0x180027107  test    byte ptr [rsi+9], 88h
0x18002710b  jz      short loc_18002712A
0x18002710d  lea     r8, [rsp+58h+rc]
0x180027112  mov     edx, edi
0x180027114  mov     rcx, rbx
0x180027117  call    TB_GetItemRect
0x18002711c  mov     eax, [rsp+58h+rc.right]
0x180027120  sub     eax, [rbx+0D0h]
0x180027126  mov     [rsp+58h+rc.left], eax
0x18002712a  mov     al, [rsi+9]
0x18002712d  test    al, 88h
0x18002712f  jz      short loc_180027186
0x180027131  test    byte ptr [rbx+38h], 1
0x180027135  jz      short loc_180027153
0x180027137  test    al, 8
0x180027139  jz      short loc_180027153
0x18002713b  test    al, al
0x18002713d  js      short loc_180027153
0x18002713f  mov     rdx, qword ptr [rsp+58h+pt.x]; pt
0x180027144  lea     rcx, [rsp+58h+rc]; lprc
0x180027149  call    cs:__imp_PtInRect
0x18002714f  test    eax, eax
0x180027151  jz      short loc_180027186
0x180027153  mov     r8d, 1
0x180027159  mov     edx, edi
0x18002715b  mov     rcx, rbx
0x18002715e  call    TBToggleDropDown
0x180027163  test    eax, eax
0x180027165  jnz     loc_180027200
0x18002716b  mov     rcx, rbp; hWnd
0x18002716e  mov     [rbx+58h], rsi
0x180027172  call    cs:__imp_SetCapture
0x180027178  btr     dword ptr [rbx+13Ch], 9
0x180027180  mov     rdx, [rbx+58h]
0x180027184  jmp     short loc_1800271E3
0x180027186  mov     rcx, rbp; hWnd
0x180027189  mov     [rbx+58h], rsi
0x18002718d  call    cs:__imp_SetCapture
0x180027193  mov     al, [rsi+8]
0x180027196  test    al, 4
0x180027198  jz      short loc_1800271D2
0x18002719a  or      al, 2
0x18002719c  mov     r8d, 1
0x1800271a2  mov     rdx, rsi
0x1800271a5  mov     [rsi+8], al
0x1800271a8  mov     rcx, rbx
0x1800271ab  call    InvalidateButton
0x1800271b0  mov     rcx, rbp; hWnd
0x1800271b3  call    cs:__imp_UpdateWindow
0x1800271b9  lea     eax, [rdi+1]
0x1800271bc  mov     r8d, 0FFFFFFFCh
0x1800271c2  movsxd  r9, eax
0x1800271c5  mov     rdx, rbp
0x1800271c8  mov     ecx, 800Ah
0x1800271cd  call    MyNotifyWinEvent
0x1800271d2  btr     dword ptr [rbx+13Ch], 9
0x1800271da  mov     rdx, [rbx+58h]
0x1800271de  test    rdx, rdx
0x1800271e1  jz      short loc_1800271F4
0x1800271e3  mov     edx, [rdx+4]
0x1800271e6  mov     r8d, 0FFFFFD43h
0x1800271ec  mov     rcx, rbx
0x1800271ef  call    SendItemNotify
0x1800271f4  mov     rcx, [rbx]; hWnd
0x1800271f7  lea     rdx, [rbx+60h]; lpPoint
0x1800271fb  call    GetMessagePosClient
0x180027200  mov     rcx, [rsp+58h+var_20]
0x180027205  xor     rcx, rsp; StackCookie
0x180027208  call    __security_check_cookie
0x18002720d  mov     rbx, [rsp+58h+arg_18]
0x180027212  add     rsp, 40h
0x180027216  pop     rdi
0x180027217  pop     rsi
0x180027218  pop     rbp
0x180027219  retn
```
