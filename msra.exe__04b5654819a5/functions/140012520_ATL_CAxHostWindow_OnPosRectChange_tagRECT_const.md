# ATL::CAxHostWindow::OnPosRectChange(tagRECT const *)

- ea: `0x140012520`
- end: `0x140012615`
- name: `?OnPosRectChange@CAxHostWindow@ATL@@UEAAJPEBUtagRECT@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140012520`
- `0x14004ad80`

## import_xrefs

- `USER32!ClientToScreen` at `0x14001255d`
- `USER32!ClientToScreen` at `0x140012576`
- `USER32!ClientToScreen` at `0x14001255d`
- `USER32!ClientToScreen` at `0x140012576`
- `USER32!GetParent` at `0x140012586`
- `USER32!GetParent` at `0x140012586`
- `USER32!ScreenToClient` at `0x1400125a2`
- `USER32!ScreenToClient` at `0x1400125ba`
- `USER32!ScreenToClient` at `0x1400125a2`
- `USER32!ScreenToClient` at `0x1400125ba`
- `USER32!MoveWindow` at `0x1400125ee`
- `USER32!MoveWindow` at `0x1400125ee`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPosRectChange(ATL::CAxHostWindow *this, const struct tagRECT *a2)
{
  HWND v4; // rcx
  HWND Parent; // rax
  HWND v6; // rbx
  tagPOINT Point[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = (HWND)*((_QWORD *)this - 10);
  *(struct tagRECT *)&Point[0].x = *a2;
  if ( ClientToScreen(v4, Point) )
    ClientToScreen(*((HWND *)this - 10), &Point[1]);
  Parent = GetParent(*((HWND *)this - 10));
  v6 = Parent;
  if ( Parent )
  {
    if ( ScreenToClient(Parent, Point) )
      ScreenToClient(v6, &Point[1]);
  }
  MoveWindow(*((HWND *)this - 10), Point[0].x, Point[0].y, Point[1].x - Point[0].x, Point[1].y - Point[0].y, 1);
  return 0;
}

```

## disassembly

```asm
0x140012520  mov     [rsp+arg_10], rbx
0x140012525  push    rdi
0x140012526  sub     rsp, 50h
0x14001252a  mov     rax, cs:__security_cookie
0x140012531  xor     rax, rsp
0x140012534  mov     [rsp+58h+var_18], rax
0x140012539  mov     rdi, rcx
0x14001253c  test    rdx, rdx
0x14001253f  jnz     short loc_14001254B
0x140012541  mov     eax, 80004003h
0x140012546  jmp     loc_1400125FC
0x14001254b  movups  xmm0, xmmword ptr [rdx]
0x14001254e  mov     rcx, [rcx-50h]; hWnd
0x140012552  lea     rdx, [rsp+58h+Point]; lpPoint
0x140012557  movdqu  xmmword ptr [rsp+58h+Point.x], xmm0
0x14001255d  call    cs:__imp_ClientToScreen
0x140012564  nop     dword ptr [rax+rax+00h]
0x140012569  test    eax, eax
0x14001256b  jz      short loc_140012582
0x14001256d  mov     rcx, [rdi-50h]; hWnd
0x140012571  lea     rdx, [rsp+58h+Point.x+8]; lpPoint
0x140012576  call    cs:__imp_ClientToScreen
0x14001257d  nop     dword ptr [rax+rax+00h]
0x140012582  mov     rcx, [rdi-50h]; hWnd
0x140012586  call    cs:__imp_GetParent
0x14001258d  nop     dword ptr [rax+rax+00h]
0x140012592  mov     rbx, rax
0x140012595  test    rax, rax
0x140012598  jz      short loc_1400125C6
0x14001259a  lea     rdx, [rsp+58h+Point]; lpPoint
0x14001259f  mov     rcx, rax; hWnd
0x1400125a2  call    cs:__imp_ScreenToClient
0x1400125a9  nop     dword ptr [rax+rax+00h]
0x1400125ae  test    eax, eax
0x1400125b0  jz      short loc_1400125C6
0x1400125b2  lea     rdx, [rsp+58h+Point.x+8]; lpPoint
0x1400125b7  mov     rcx, rbx; hWnd
0x1400125ba  call    cs:__imp_ScreenToClient
0x1400125c1  nop     dword ptr [rax+rax+00h]
0x1400125c6  mov     eax, [rsp+58h+Point.y+8]
0x1400125ca  mov     r8d, [rsp+58h+Point.y]; Y
0x1400125cf  sub     eax, r8d
0x1400125d2  mov     r9d, [rsp+58h+Point.x+8]
0x1400125d7  mov     edx, [rsp+58h+Point.x]; X
0x1400125db  sub     r9d, edx; nWidth
0x1400125de  mov     rcx, [rdi-50h]; hWnd
0x1400125e2  mov     [rsp+58h+bRepaint], 1; bRepaint
0x1400125ea  mov     [rsp+58h+nHeight], eax; nHeight
0x1400125ee  call    cs:__imp_MoveWindow
0x1400125f5  nop     dword ptr [rax+rax+00h]
0x1400125fa  xor     eax, eax
0x1400125fc  mov     rcx, [rsp+58h+var_18]
0x140012601  xor     rcx, rsp; StackCookie
0x140012604  call    __security_check_cookie
0x140012609  mov     rbx, [rsp+58h+arg_10]
0x14001260e  add     rsp, 50h
0x140012612  pop     rdi
0x140012613  retn
```
