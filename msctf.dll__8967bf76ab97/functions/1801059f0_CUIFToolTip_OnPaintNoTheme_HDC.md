# CUIFToolTip::OnPaintNoTheme(HDC__ *)

- ea: `0x1801059f0`
- end: `0x180105b94`
- name: `?OnPaintNoTheme@CUIFToolTip@@UEAAXPEAUHDC__@@@Z`
- size: `420`
- prototype: `void(CUIFToolTip *__hidden this, HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1801059f0`
- `0x180106a60`

## import_xrefs

- `USER32!DrawTextExW` at `0x180105b46`
- `USER32!DrawTextExW` at `0x180105b46`
- `USER32!FillRect` at `0x180105ac9`
- `USER32!FillRect` at `0x180105ac9`
- `USER32!GetSysColor` at `0x180105a7f`
- `USER32!GetSysColor` at `0x180105aa9`
- `USER32!GetSysColor` at `0x180105a7f`
- `USER32!GetSysColor` at `0x180105aa9`
- `GDI32!DeleteObject` at `0x180105ad2`
- `GDI32!DeleteObject` at `0x180105ad2`
- `GDI32!SelectObject` at `0x180105a22`
- `GDI32!SelectObject` at `0x180105b6a`
- `GDI32!SelectObject` at `0x180105a22`
- `GDI32!SelectObject` at `0x180105b6a`
- `GDI32!CreateSolidBrush` at `0x180105ab1`
- `GDI32!CreateSolidBrush` at `0x180105ab1`
- `GDI32!SetBkMode` at `0x180105a33`
- `GDI32!SetBkMode` at `0x180105b5e`
- `GDI32!SetBkMode` at `0x180105a33`
- `GDI32!SetBkMode` at `0x180105b5e`
- `GDI32!SetTextColor` at `0x180105a8a`
- `GDI32!SetTextColor` at `0x180105b52`
- `GDI32!SetTextColor` at `0x180105a8a`
- `GDI32!SetTextColor` at `0x180105b52`

## pseudocode

```c
void __fastcall CUIFToolTip::OnPaintNoTheme(CUIFToolTip *this, HDC a2)
{
  HGDIOBJ v4; // r15
  int v5; // eax
  _WORD *v6; // rcx
  int v7; // r12d
  COLORREF SysColor; // eax
  COLORREF v9; // r14d
  COLORREF v10; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v12; // rsi
  LONG v13; // ecx
  WCHAR *v14; // rdx
  LONG v15; // eax
  LONG v16; // ecx
  struct tagRECT v17; // [rsp+30h] [rbp-40h] BYREF
  RECT rc; // [rsp+40h] [rbp-30h] BYREF
  __int128 v19; // [rsp+50h] [rbp-20h]
  int v20; // [rsp+60h] [rbp-10h]

  v4 = SelectObject(a2, *((HGDIOBJ *)this + 14));
  v5 = SetBkMode(a2, 1);
  v6 = (_WORD *)*((_QWORD *)this + 32);
  v7 = v5;
  rc = *(RECT *)((char *)this + 88);
  v17 = 0;
  if ( v6 && *v6 )
  {
    if ( *((_DWORD *)this + 77) )
      SysColor = *((_DWORD *)this + 79);
    else
      SysColor = GetSysColor(23);
    v9 = SetTextColor(a2, SysColor);
    if ( *((_DWORD *)this + 76) )
      v10 = *((_DWORD *)this + 78);
    else
      v10 = GetSysColor(24);
    SolidBrush = CreateSolidBrush(v10);
    v12 = SolidBrush;
    if ( SolidBrush )
    {
      FillRect(a2, &rc, SolidBrush);
      DeleteObject(v12);
    }
    v13 = rc.left + *((_DWORD *)this + 71);
    v14 = (WCHAR *)*((_QWORD *)this + 32);
    v17.right = rc.right - *((_DWORD *)this + 73);
    v15 = rc.bottom - *((_DWORD *)this + 74);
    v17.left = v13;
    v16 = rc.top + *((_DWORD *)this + 72);
    v17.bottom = v15;
    v17.top = v16;
    v19 = 0;
    v20 = 0;
    if ( *((int *)this + 75) <= 0 )
      DrawTextExW(a2, v14, -1, &v17, 0x20u, 0);
    else
      DrawTextExW(a2, v14, -1, &v17, 0x10u, 0);
    SetTextColor(a2, v9);
    SetBkMode(a2, v7);
    SelectObject(a2, v4);
  }
}

```

## disassembly

```asm
0x1801059f0  mov     [rsp-38h+arg_10], rbx
0x1801059f5  push    rbp
0x1801059f6  push    rsi
0x1801059f7  push    rdi
0x1801059f8  push    r12
0x1801059fa  push    r13
0x1801059fc  push    r14
0x1801059fe  push    r15
0x180105a00  mov     rbp, rsp
0x180105a03  sub     rsp, 70h
0x180105a07  mov     rax, cs:__security_cookie
0x180105a0e  xor     rax, rsp
0x180105a11  mov     [rbp+var_8], rax
0x180105a15  mov     rdi, rdx
0x180105a18  mov     rbx, rcx
0x180105a1b  mov     rdx, [rcx+70h]; h
0x180105a1f  mov     rcx, rdi; hdc
0x180105a22  call    cs:__imp_SelectObject
0x180105a28  mov     edx, 1; mode
0x180105a2d  mov     rcx, rdi; hdc
0x180105a30  mov     r15, rax
0x180105a33  call    cs:__imp_SetBkMode
0x180105a39  movups  xmm0, xmmword ptr [rbx+58h]
0x180105a3d  mov     rcx, [rbx+100h]
0x180105a44  xor     r13d, r13d
0x180105a47  xorps   xmm1, xmm1
0x180105a4a  mov     r12d, eax
0x180105a4d  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x180105a52  movups  xmmword ptr [rbp+var_40.left], xmm1
0x180105a56  test    rcx, rcx
0x180105a59  jz      loc_180105B70
0x180105a5f  cmp     [rcx], r13w
0x180105a63  jz      loc_180105B70
0x180105a69  cmp     [rbx+134h], r13d
0x180105a70  jz      short loc_180105A7A
0x180105a72  mov     eax, [rbx+13Ch]
0x180105a78  jmp     short loc_180105A85
0x180105a7a  mov     ecx, 17h; nIndex
0x180105a7f  call    cs:__imp_GetSysColor
0x180105a85  mov     edx, eax; color
0x180105a87  mov     rcx, rdi; hdc
0x180105a8a  call    cs:__imp_SetTextColor
0x180105a90  mov     r14d, eax
0x180105a93  cmp     [rbx+130h], r13d
0x180105a9a  jz      short loc_180105AA4
0x180105a9c  mov     eax, [rbx+138h]
0x180105aa2  jmp     short loc_180105AAF
0x180105aa4  mov     ecx, 18h; nIndex
0x180105aa9  call    cs:__imp_GetSysColor
0x180105aaf  mov     ecx, eax; color
0x180105ab1  call    cs:__imp_CreateSolidBrush
0x180105ab7  mov     rsi, rax
0x180105aba  test    rax, rax
0x180105abd  jz      short loc_180105AD8
0x180105abf  mov     r8, rax; hbr
0x180105ac2  lea     rdx, [rbp+rc]; lprc
0x180105ac6  mov     rcx, rdi; hDC
0x180105ac9  call    cs:__imp_FillRect
0x180105acf  mov     rcx, rsi; ho
0x180105ad2  call    cs:__imp_DeleteObject
0x180105ad8  mov     eax, [rbp+rc.right]
0x180105adb  lea     r9, [rbp+var_40]; lprc
0x180105adf  sub     eax, [rbx+124h]
0x180105ae5  or      r8d, 0FFFFFFFFh; cchText
0x180105ae9  mov     ecx, [rbx+11Ch]
0x180105aef  xorps   xmm0, xmm0
0x180105af2  add     ecx, [rbp+rc.left]
0x180105af5  mov     rdx, [rbx+100h]; lpchText
0x180105afc  mov     [rbp+var_40.right], eax
0x180105aff  mov     eax, [rbp+rc.bottom]
0x180105b02  sub     eax, [rbx+128h]
0x180105b08  mov     [rbp+var_40.left], ecx
0x180105b0b  mov     ecx, [rbx+120h]
0x180105b11  add     ecx, [rbp+rc.top]
0x180105b14  mov     [rbp+var_40.bottom], eax
0x180105b17  xor     eax, eax
0x180105b19  mov     [rbp+var_40.top], ecx
0x180105b1c  mov     rcx, rdi; hdc
0x180105b1f  mov     [rsp+70h+lpdtp], r13; lpdtp
0x180105b24  movups  [rbp+var_20], xmm0
0x180105b28  mov     [rbp+var_10], eax
0x180105b2b  cmp     [rbx+12Ch], r13d
0x180105b32  jle     short loc_180105B3E
0x180105b34  mov     [rsp+70h+format], 10h
0x180105b3c  jmp     short loc_180105B46
0x180105b3e  mov     [rsp+70h+format], 20h ; ' '; format
0x180105b46  call    cs:__imp_DrawTextExW
0x180105b4c  mov     edx, r14d; color
0x180105b4f  mov     rcx, rdi; hdc
0x180105b52  call    cs:__imp_SetTextColor
0x180105b58  mov     edx, r12d; mode
0x180105b5b  mov     rcx, rdi; hdc
0x180105b5e  call    cs:__imp_SetBkMode
0x180105b64  mov     rdx, r15; h
0x180105b67  mov     rcx, rdi; hdc
0x180105b6a  call    cs:__imp_SelectObject
0x180105b70  mov     rcx, [rbp+var_8]
0x180105b74  xor     rcx, rsp; StackCookie
0x180105b77  call    __security_check_cookie
0x180105b7c  mov     rbx, [rsp+70h+arg_10]
0x180105b84  add     rsp, 70h
0x180105b88  pop     r15
0x180105b8a  pop     r14
0x180105b8c  pop     r13
0x180105b8e  pop     r12
0x180105b90  pop     rdi
0x180105b91  pop     rsi
0x180105b92  pop     rbp
0x180105b93  retn
```
