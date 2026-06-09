# CPopupWindow::CalculateRect(tagPOINT)

- ea: `0x180047db8`
- end: `0x180047f4d`
- name: `?CalculateRect@CPopupWindow@@IEAAXUtagPOINT@@@Z`
- size: `405`
- prototype: `void __fastcall(CPopupWindow *__hidden this, struct tagPOINT)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180047ffc`

## callees

- `0x180047db8`
- `0x180075c90`

## import_xrefs

- `USER32!OffsetRect` at `0x180047f0c`
- `USER32!OffsetRect` at `0x180047f22`
- `USER32!OffsetRect` at `0x180047f0c`
- `USER32!OffsetRect` at `0x180047f22`
- `USER32!DrawTextA` at `0x180047e65`
- `USER32!DrawTextA` at `0x180047ea5`
- `USER32!DrawTextA` at `0x180047e65`
- `USER32!DrawTextA` at `0x180047ea5`
- `USER32!GetDesktopWindow` at `0x180047df3`
- `USER32!GetDesktopWindow` at `0x180047df3`
- `USER32!GetClientRect` at `0x180047e00`
- `USER32!GetClientRect` at `0x180047e00`
- `GDI32!SelectObject` at `0x180047e33`
- `GDI32!SelectObject` at `0x180047eb8`
- `GDI32!SelectObject` at `0x180047e33`
- `GDI32!SelectObject` at `0x180047eb8`
- `GDI32!CreateDCA` at `0x180047e1b`
- `GDI32!CreateDCA` at `0x180047e1b`

## pseudocode

```c
void __fastcall CPopupWindow::CalculateRect(CPopupWindow *this, struct tagPOINT a2)
{
  LONG y; // r12d
  LONG x; // ebx
  HWND DesktopWindow; // rax
  int v6; // esi
  HDC DCA; // rax
  void *v8; // rdx
  HGDIOBJ v9; // r15
  HDC v10; // r14
  const CHAR *v11; // rdx
  int v12; // ebx
  int v13; // edx
  int v14; // eax
  struct tagRECT Rect; // [rsp+30h] [rbp-20h] BYREF

  y = a2.y;
  x = a2.x;
  Rect = 0;
  DesktopWindow = GetDesktopWindow();
  GetClientRect(DesktopWindow, &Rect);
  v6 = Rect.bottom - Rect.top;
  DCA = CreateDCA("DISPLAY", 0, 0, 0);
  v8 = (void *)*((_QWORD *)this + 8);
  v9 = 0;
  v10 = DCA;
  if ( v8 )
    v9 = SelectObject(DCA, v8);
  DrawTextA(v10, *((LPCSTR *)this + 7), -1, &Rect, g_fBiDi != 0 ? 134480 : 3408);
  if ( 12 * Rect.bottom < Rect.right )
  {
    v11 = (const CHAR *)*((_QWORD *)this + 7);
    Rect.right = 12 * Rect.bottom;
    DrawTextA(v10, v11, -1, &Rect, g_fBiDi != 0 ? 134480 : 3408);
  }
  if ( *((_QWORD *)this + 8) )
    SelectObject(v10, v9);
  v12 = x - (Rect.right - Rect.left) / 2;
  v13 = v12 - *((_DWORD *)this + 18);
  *((_DWORD *)this + 5) = y - *((_DWORD *)this + 19);
  v14 = v12 + *((_DWORD *)this + 20) - Rect.left;
  *((_DWORD *)this + 4) = v13;
  *((_DWORD *)this + 6) = Rect.right + v14;
  *((_DWORD *)this + 7) = y + Rect.bottom + *((_DWORD *)this + 21) - Rect.top;
  if ( v13 < 0 )
    OffsetRect((LPRECT)this + 1, -v13, 0);
  if ( *((_DWORD *)this + 7) > v6 )
    OffsetRect((LPRECT)this + 1, 0, v6 - *((_DWORD *)this + 7));
}

```

## disassembly

```asm
0x180047db8  mov     [rsp-28h+arg_10], rbx
0x180047dbd  mov     [rsp-28h+arg_18], rsi
0x180047dc2  push    rbp
0x180047dc3  push    rdi
0x180047dc4  push    r12
0x180047dc6  push    r14
0x180047dc8  push    r15
0x180047dca  mov     rbp, rsp
0x180047dcd  sub     rsp, 50h
0x180047dd1  mov     rax, cs:__security_cookie
0x180047dd8  xor     rax, rsp
0x180047ddb  mov     [rbp+var_10], rax
0x180047ddf  mov     r12, rdx
0x180047de2  xorps   xmm0, xmm0
0x180047de5  shr     r12, 20h
0x180047de9  mov     rbx, rdx
0x180047dec  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180047df0  mov     rdi, rcx
0x180047df3  call    cs:__imp_GetDesktopWindow
0x180047df9  mov     rcx, rax; hWnd
0x180047dfc  lea     rdx, [rbp+Rect]; lpRect
0x180047e00  call    cs:__imp_GetClientRect
0x180047e06  mov     esi, [rbp+Rect.bottom]
0x180047e09  lea     rcx, pszDriver; "DISPLAY"
0x180047e10  sub     esi, [rbp+Rect.top]
0x180047e13  xor     r9d, r9d; pdm
0x180047e16  xor     r8d, r8d; pszPort
0x180047e19  xor     edx, edx; pwszDevice
0x180047e1b  call    cs:__imp_CreateDCA
0x180047e21  mov     rdx, [rdi+40h]; h
0x180047e25  xor     r15d, r15d
0x180047e28  mov     r14, rax
0x180047e2b  test    rdx, rdx
0x180047e2e  jz      short loc_180047E3C
0x180047e30  mov     rcx, rax; hdc
0x180047e33  call    cs:__imp_SelectObject
0x180047e39  mov     r15, rax
0x180047e3c  mov     ecx, cs:?g_fBiDi@@3HA; int g_fBiDi
0x180047e42  lea     r9, [rbp+Rect]; lprc
0x180047e46  neg     ecx
0x180047e48  mov     rcx, r14; hdc
0x180047e4b  sbb     edx, edx
0x180047e4d  or      r8d, 0FFFFFFFFh; cchText
0x180047e51  and     edx, 20000h
0x180047e57  add     edx, 0D50h
0x180047e5d  mov     [rsp+50h+format], edx; format
0x180047e61  mov     rdx, [rdi+38h]; lpchText
0x180047e65  call    cs:__imp_DrawTextA
0x180047e6b  mov     eax, [rbp+Rect.bottom]
0x180047e6e  lea     ecx, [rax+rax*2]
0x180047e71  shl     ecx, 2
0x180047e74  cmp     ecx, [rbp+Rect.right]
0x180047e77  jge     short loc_180047EAB
0x180047e79  mov     eax, cs:?g_fBiDi@@3HA; int g_fBiDi
0x180047e7f  lea     r9, [rbp+Rect]; lprc
0x180047e83  mov     rdx, [rdi+38h]; lpchText
0x180047e87  neg     eax
0x180047e89  mov     [rbp+Rect.right], ecx
0x180047e8c  sbb     ecx, ecx
0x180047e8e  or      r8d, 0FFFFFFFFh; cchText
0x180047e92  and     ecx, 20000h
0x180047e98  add     ecx, 0D50h
0x180047e9e  mov     [rsp+50h+format], ecx; format
0x180047ea2  mov     rcx, r14; hdc
0x180047ea5  call    cs:__imp_DrawTextA
0x180047eab  cmp     qword ptr [rdi+40h], 0
0x180047eb0  jz      short loc_180047EBE
0x180047eb2  mov     rdx, r15; h
0x180047eb5  mov     rcx, r14; hdc
0x180047eb8  call    cs:__imp_SelectObject
0x180047ebe  mov     eax, [rbp+Rect.right]
0x180047ec1  lea     r14, [rdi+10h]
0x180047ec5  sub     eax, [rbp+Rect.left]
0x180047ec8  mov     ecx, 2
0x180047ecd  cdq
0x180047ece  idiv    ecx
0x180047ed0  sub     ebx, eax
0x180047ed2  mov     eax, r12d
0x180047ed5  sub     eax, [rdi+4Ch]
0x180047ed8  mov     edx, ebx
0x180047eda  sub     edx, [rdi+48h]
0x180047edd  mov     [rdi+14h], eax
0x180047ee0  mov     eax, [rdi+50h]
0x180047ee3  sub     eax, [rbp+Rect.left]
0x180047ee6  add     eax, ebx
0x180047ee8  mov     [r14], edx
0x180047eeb  add     eax, [rbp+Rect.right]
0x180047eee  mov     [rdi+18h], eax
0x180047ef1  mov     eax, [rdi+54h]
0x180047ef4  sub     eax, [rbp+Rect.top]
0x180047ef7  add     eax, [rbp+Rect.bottom]
0x180047efa  add     eax, r12d
0x180047efd  mov     [rdi+1Ch], eax
0x180047f00  test    edx, edx
0x180047f02  jns     short loc_180047F12
0x180047f04  neg     edx; dx
0x180047f06  xor     r8d, r8d; dy
0x180047f09  mov     rcx, r14; lprc
0x180047f0c  call    cs:__imp_OffsetRect
0x180047f12  cmp     [rdi+1Ch], esi
0x180047f15  jle     short loc_180047F28
0x180047f17  sub     esi, [rdi+1Ch]
0x180047f1a  xor     edx, edx; dx
0x180047f1c  mov     r8d, esi; dy
0x180047f1f  mov     rcx, r14; lprc
0x180047f22  call    cs:__imp_OffsetRect
0x180047f28  mov     rcx, [rbp+var_10]
0x180047f2c  xor     rcx, rsp; StackCookie
0x180047f2f  call    __security_check_cookie
0x180047f34  lea     r11, [rsp+50h+var_s0]
0x180047f39  mov     rbx, [r11+40h]
0x180047f3d  mov     rsi, [r11+48h]
0x180047f41  mov     rsp, r11
0x180047f44  pop     r15
0x180047f46  pop     r14
0x180047f48  pop     r12
0x180047f4a  pop     rdi
0x180047f4b  pop     rbp
0x180047f4c  retn
```
