# CReBar::_EraseBkgnd(HDC__ *,int)

- ea: `0x1800518dc`
- end: `0x180051df4`
- name: `?_EraseBkgnd@CReBar@@AEAAHPEAUHDC__@@H@Z`
- size: `1304`
- prototype: `__int64 __fastcall(CReBar *__hidden this, HDC hdc, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004f5f0`
- `0x180050f38`

## callees

- `0x180007fc4`
- `0x180034a84`
- `0x180036850`
- `0x1800518dc`
- `0x180052740`
- `0x1800527ac`
- `0x180102814`
- `0x18010380c`
- `0x180114520`
- `0x180114ebc`
- `0x1801315c0`

## import_xrefs

- `GDI32!SelectObject` at `0x180051d34`
- `GDI32!SelectObject` at `0x180051d34`
- `GDI32!DeleteDC` at `0x180051dbc`
- `GDI32!DeleteDC` at `0x180051dbc`
- `GDI32!CreateCompatibleDC` at `0x180051d09`
- `GDI32!CreateCompatibleDC` at `0x180051d09`
- `GDI32!GetClipBox` at `0x1800519c1`
- `GDI32!GetClipBox` at `0x1800519c1`
- `USER32!GetSystemMetrics` at `0x180051bbf`
- `USER32!GetSystemMetrics` at `0x180051c02`
- `USER32!GetSystemMetrics` at `0x180051c2c`
- `USER32!GetSystemMetrics` at `0x180051c42`
- `USER32!GetSystemMetrics` at `0x180051c70`
- `USER32!GetSystemMetrics` at `0x180051c86`
- `USER32!GetSystemMetrics` at `0x180051c99`
- `USER32!GetSystemMetrics` at `0x180051caf`
- `USER32!GetSystemMetrics` at `0x180051cdd`
- `USER32!GetSystemMetrics` at `0x180051cf3`
- `USER32!GetSystemMetrics` at `0x180051bbf`
- `USER32!GetSystemMetrics` at `0x180051c02`
- `USER32!GetSystemMetrics` at `0x180051c2c`
- `USER32!GetSystemMetrics` at `0x180051c42`
- `USER32!GetSystemMetrics` at `0x180051c70`
- `USER32!GetSystemMetrics` at `0x180051c86`
- `USER32!GetSystemMetrics` at `0x180051c99`
- `USER32!GetSystemMetrics` at `0x180051caf`
- `USER32!GetSystemMetrics` at `0x180051cdd`
- `USER32!GetSystemMetrics` at `0x180051cf3`
- `USER32!GetClientRect` at `0x1800519a0`
- `USER32!GetClientRect` at `0x1800519a0`
- `USER32!SetRect` at `0x180051a5f`
- `USER32!SetRect` at `0x180051a5f`
- `UxTheme!DrawThemeBackground` at `0x180051a1a`
- `UxTheme!DrawThemeBackground` at `0x180051ae5`
- `UxTheme!DrawThemeBackground` at `0x180051a1a`
- `UxTheme!DrawThemeBackground` at `0x180051ae5`
- `UxTheme!IsThemeBackgroundPartiallyTransparent` at `0x1800519e9`
- `UxTheme!IsThemeBackgroundPartiallyTransparent` at `0x1800519e9`
- `UxTheme!DrawThemeParentBackground` at `0x180051b5c`
- `UxTheme!DrawThemeParentBackground` at `0x180051b5c`

## pseudocode

```c
__int64 __fastcall CReBar::_EraseBkgnd(CReBar *this, HDC hdc)
{
  HWND *v2; // r15
  int v3; // r14d
  __int64 v6; // rdi
  int v7; // eax
  int v8; // ecx
  HDC CompatibleDC; // r12
  int v10; // r13d
  int v11; // r14d
  unsigned int v12; // eax
  int v13; // r8d
  int v14; // edx
  int v15; // ecx
  int v16; // r9d
  bool v17; // zf
  char v18; // r14
  __int16 v19; // ax
  void *v20; // rcx
  COLORREF BkColor; // eax
  int v23; // eax
  int SystemMetrics; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  COLORREF v28; // r13d
  unsigned int v29; // [rsp+50h] [rbp-69h]
  int v30; // [rsp+54h] [rbp-65h]
  int v31; // [rsp+58h] [rbp-61h]
  __int64 v32; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v33[16]; // [rsp+68h] [rbp-51h] BYREF
  int v34; // [rsp+78h] [rbp-41h]
  HDC v35; // [rsp+80h] [rbp-39h]
  struct tagRECT rc; // [rsp+88h] [rbp-31h] BYREF
  __int64 v37; // [rsp+98h] [rbp-21h]
  int v38; // [rsp+A0h] [rbp-19h]
  __int64 v39; // [rsp+A8h] [rbp-11h]
  struct tagRECT Rect; // [rsp+B0h] [rbp-9h] BYREF
  struct tagRECT rect; // [rsp+C0h] [rbp+7h] BYREF

  v2 = (HWND *)((char *)this + 56);
  v32 = 0;
  v3 = *((_DWORD *)this + 18);
  memset_0(v33, 0, 0x48u);
  v6 = *((_QWORD *)this + 36);
  v35 = hdc;
  v38 = 0;
  v39 = 0;
  Rect = 0;
  v34 = 3;
  v7 = CCSendNotify((__int64)v2, -12, (LPARAM)&v32);
  v8 = 0;
  if ( (v7 & 0xFE01) == 0 )
    v8 = v7;
  *((_DWORD *)this + 19) = v8;
  if ( (v8 & 4) == 0 )
  {
    CompatibleDC = 0;
    v10 = v3 & 0x80;
    v11 = v3 & 0x400;
    v31 = v10;
    v30 = v11;
    GetClientRect(*v2, &Rect);
    if ( *((_QWORD *)this + 42) )
    {
      rect = 0;
      if ( GetClipBox(hdc, &rect) == 1 )
        rect = Rect;
      if ( (*((_BYTE *)this + 88) & 0x20) == 0 && IsThemeBackgroundPartiallyTransparent(*((HTHEME *)this + 42), 6, 0) )
        DrawThemeParentBackground(*v2, hdc, 0);
      DrawThemeBackground(*((HTHEME *)this + 42), hdc, 6, 0, &Rect, &rect);
    }
    else
    {
      BkColor = CReBar::_GetBkColor(this);
      if ( BkColor != -1 )
        FillRectClr(hdc, &Rect, BkColor);
    }
    v12 = 0;
    v29 = 0;
    if ( *((_DWORD *)this + 66) )
    {
      while ( (*(_BYTE *)v6 & 8) != 0 )
      {
LABEL_26:
        ++v12;
        v6 += 144;
        v29 = v12;
        if ( v12 >= *((_DWORD *)this + 66) )
        {
          if ( CompatibleDC )
            DeleteDC(CompatibleDC);
          goto LABEL_29;
        }
      }
      if ( v10 )
      {
        v13 = *(_DWORD *)(v6 + 48);
        v14 = *(_DWORD *)(v6 + 52);
        v15 = *(_DWORD *)(v6 + 56);
        v16 = *(_DWORD *)(v6 + 60);
      }
      else
      {
        v13 = *(_DWORD *)(v6 + 52);
        v14 = *(_DWORD *)(v6 + 48);
        v15 = *(_DWORD *)(v6 + 60);
        v16 = *(_DWORD *)(v6 + 56);
      }
      SetRect(&rc, v14, v13, v14 + v16, v13 + v15);
      if ( v11 )
      {
        if ( (*(_DWORD *)v6 & 0x20000000) != 0 )
          v23 = 0;
        else
          v23 = *((_DWORD *)this + 57);
        if ( *(_DWORD *)(v6 + 48) == v23 )
        {
          if ( v10 )
            Rect.right = GetSystemMetrics(45) + *(_DWORD *)(v6 + 52) + *(_DWORD *)(v6 + 60);
          else
            Rect.bottom = GetSystemMetrics(46) + *(_DWORD *)(v6 + 52) + *(_DWORD *)(v6 + 60);
          CCThemeDrawEdge(*((_QWORD *)this + 42), hdc, &Rect);
        }
        else if ( v10 )
        {
          rc.right += GetSystemMetrics(45) / 2;
          SystemMetrics = GetSystemMetrics(46);
          v25 = *((_QWORD *)this + 42);
          rc.top -= SystemMetrics;
          CCThemeDrawEdge(v25, hdc, &rc);
          rc.right += GetSystemMetrics(45) / -2;
          rc.top += GetSystemMetrics(46);
        }
        else
        {
          rc.bottom += GetSystemMetrics(46) / 2;
          v26 = GetSystemMetrics(45);
          v27 = *((_QWORD *)this + 42);
          rc.left -= v26;
          CCThemeDrawEdge(v27, hdc, &rc);
          rc.bottom += GetSystemMetrics(46) / -2;
          rc.left += GetSystemMetrics(45);
        }
      }
      v17 = (*((_BYTE *)v2 + 20) & 0x20) == 0;
      v37 = *(unsigned int *)(v6 + 104);
      v38 = 0;
      if ( v17 || (v34 = 65539, v19 = CCSendNotify((__int64)v2, -12, (LPARAM)&v32), v18 = v19, (v19 & 0xFE01) != 0) )
      {
        v18 = 0;
      }
      else if ( (v19 & 4) != 0 )
      {
        goto LABEL_23;
      }
      if ( *(_QWORD *)(v6 + 96) )
      {
        if ( !CompatibleDC )
        {
          CompatibleDC = CreateCompatibleDC(hdc);
          if ( !CompatibleDC )
          {
LABEL_25:
            v12 = v29;
            v11 = v30;
            goto LABEL_26;
          }
          CReBar::_Realize(this, hdc, 1, 0);
        }
        SelectObject(CompatibleDC, *(HGDIOBJ *)(v6 + 96));
        CReBar::_BandTileBlt(
          this,
          (struct tagREBARBAND *)v6,
          rc.left,
          rc.top,
          rc.right - rc.left,
          rc.bottom - rc.top,
          hdc,
          CompatibleDC);
      }
      else
      {
        v20 = (void *)*((_QWORD *)this + 42);
        if ( v20 )
        {
          DrawThemeBackground(v20, hdc, 3, 0, &rc, 0);
        }
        else
        {
          v28 = CReBar::_BandGetBkColor(this, (const struct tagREBARBAND *)v6);
          if ( v28 != CReBar::_GetBkColor(this) )
            FillRectClr(hdc, &rc, v28);
          v10 = v31;
        }
      }
LABEL_23:
      if ( (v18 & 0x40) != 0 )
        CICustomDrawNotify(v2, 65540, &v32);
      goto LABEL_25;
    }
  }
LABEL_29:
  if ( (*((_BYTE *)this + 76) & 0x40) != 0 )
  {
    v38 = 0;
    v37 = 0;
    v39 = 0;
    CICustomDrawNotify(v2, 4, &v32);
  }
  return 1;
}

```

## disassembly

```asm
0x1800518dc  mov     [rsp-8+arg_10], rbx
0x1800518e1  push    rbp
0x1800518e2  push    rsi
0x1800518e3  push    rdi
0x1800518e4  push    r12
0x1800518e6  push    r13
0x1800518e8  push    r14
0x1800518ea  push    r15
0x1800518ec  lea     rbp, [rsp-27h]
0x1800518f1  sub     rsp, 0E0h
0x1800518f8  mov     rax, cs:__security_cookie
0x1800518ff  xor     rax, rsp
0x180051902  mov     [rbp+57h+var_40], rax
0x180051906  lea     r15, [rcx+38h]
0x18005190a  mov     [rbp+57h+var_B0], 0
0x180051912  mov     r14d, [r15+10h]
0x180051916  mov     rsi, rdx
0x180051919  xor     edx, edx; Val
0x18005191b  mov     rbx, rcx
0x18005191e  lea     rcx, [rbp+57h+var_A8]; void *
0x180051922  lea     r8d, [rdx+48h]; Size
0x180051926  call    memset_0
0x18005192b  mov     rdi, [rbx+120h]
0x180051932  lea     r8, [rbp+57h+var_B0]
0x180051936  xorps   xmm0, xmm0
0x180051939  mov     [rbp+57h+var_90], rsi
0x18005193d  mov     edx, 0FFFFFFF4h
0x180051942  mov     [rbp+57h+var_70], 0
0x180051949  mov     rcx, r15
0x18005194c  mov     [rbp+57h+var_68], 0
0x180051954  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180051958  mov     [rbp+57h+var_98], 3
0x18005195f  call    CCSendNotify
0x180051964  test    eax, 0FE01h
0x180051969  mov     ecx, 0
0x18005196e  cmovz   ecx, eax
0x180051971  mov     [rbx+4Ch], ecx
0x180051974  test    cl, 4
0x180051977  jnz     loc_180051B1D
0x18005197d  mov     rcx, [r15]; hWnd
0x180051980  lea     rdx, [rbp+57h+Rect]; lpRect
0x180051984  mov     r13d, r14d
0x180051987  xor     r12d, r12d
0x18005198a  and     r13d, 80h
0x180051991  and     r14d, 400h
0x180051998  mov     [rbp+57h+var_B8], r13d
0x18005199c  mov     [rbp+57h+var_BC], r14d
0x1800519a0  call    cs:__imp_GetClientRect
0x1800519a6  cmp     [rbx+150h], r12
0x1800519ad  jz      loc_180051B67
0x1800519b3  xorps   xmm0, xmm0
0x1800519b6  lea     rdx, [rbp+57h+rect]; lprect
0x1800519ba  mov     rcx, rsi; hdc
0x1800519bd  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800519c1  call    cs:__imp_GetClipBox
0x1800519c7  cmp     eax, 1
0x1800519ca  jnz     short loc_1800519D5
0x1800519cc  movaps  xmm0, xmmword ptr [rbp+57h+Rect.left]
0x1800519d0  movdqa  xmmword ptr [rbp+57h+rect.left], xmm0
0x1800519d5  test    byte ptr [rbx+58h], 20h
0x1800519d9  jnz     short loc_1800519F7
0x1800519db  mov     rcx, [rbx+150h]; hTheme
0x1800519e2  xor     r8d, r8d; iStateId
0x1800519e5  lea     edx, [r8+6]; iPartId
0x1800519e9  call    cs:__imp_IsThemeBackgroundPartiallyTransparent
0x1800519ef  test    eax, eax
0x1800519f1  jnz     loc_180051B53
0x1800519f7  mov     rcx, [rbx+150h]; hTheme
0x1800519fe  lea     rax, [rbp+57h+rect]
0x180051a02  mov     [rsp+110h+pClipRect], rax; pClipRect
0x180051a07  xor     r9d, r9d; iStateId
0x180051a0a  lea     rax, [rbp+57h+Rect]
0x180051a0e  mov     rdx, rsi; hdc
0x180051a11  mov     [rsp+110h+pRect], rax; pRect
0x180051a16  lea     r8d, [r9+6]; iPartId
0x180051a1a  call    cs:__imp_DrawThemeBackground
0x180051a20  xor     eax, eax
0x180051a22  mov     [rbp+57h+var_C0], eax
0x180051a25  cmp     [rbx+108h], eax
0x180051a2b  jbe     loc_180051B1D
0x180051a31  test    byte ptr [rdi], 8
0x180051a34  jnz     loc_180051AFC
0x180051a3a  test    r13d, r13d
0x180051a3d  jnz     loc_180051B8C
0x180051a43  mov     r8d, [rdi+34h]; yTop
0x180051a47  mov     edx, [rdi+30h]; xLeft
0x180051a4a  mov     ecx, [rdi+3Ch]
0x180051a4d  mov     r9d, [rdi+38h]
0x180051a51  add     ecx, r8d
0x180051a54  add     r9d, edx; xRight
0x180051a57  mov     dword ptr [rsp+110h+pRect], ecx; yBottom
0x180051a5b  lea     rcx, [rbp+57h+rc]; lprc
0x180051a5f  call    cs:__imp_SetRect
0x180051a65  test    r14d, r14d
0x180051a68  jnz     loc_180051B9F
0x180051a6e  test    byte ptr [r15+14h], 20h
0x180051a73  mov     eax, [rdi+68h]
0x180051a76  mov     [rbp+57h+var_78], rax
0x180051a7a  mov     [rbp+57h+var_70], 0
0x180051a81  jnz     short loc_180051A88
0x180051a83  xor     r14d, r14d
0x180051a86  jmp     short loc_180051AAE
0x180051a88  lea     r8, [rbp+57h+var_B0]
0x180051a8c  mov     [rbp+57h+var_98], 10003h
0x180051a93  mov     edx, 0FFFFFFF4h
0x180051a98  mov     rcx, r15
0x180051a9b  call    CCSendNotify
0x180051aa0  mov     r14, rax
0x180051aa3  test    eax, 0FE01h
0x180051aa8  jnz     short loc_180051A83
0x180051aaa  test    al, 4
0x180051aac  jnz     short loc_180051AEB
0x180051aae  cmp     qword ptr [rdi+60h], 0
0x180051ab3  jnz     loc_180051D01
0x180051ab9  mov     rcx, [rbx+150h]; hTheme
0x180051ac0  test    rcx, rcx
0x180051ac3  jz      loc_180051D70
0x180051ac9  xor     r9d, r9d; iStateId
0x180051acc  mov     [rsp+110h+pClipRect], 0; pClipRect
0x180051ad5  lea     rax, [rbp+57h+rc]
0x180051ad9  mov     rdx, rsi; hdc
0x180051adc  mov     [rsp+110h+pRect], rax; pRect
0x180051ae1  lea     r8d, [r9+3]; iPartId
0x180051ae5  call    cs:__imp_DrawThemeBackground
0x180051aeb  test    r14b, 40h
0x180051aef  jnz     loc_180051DA3
0x180051af5  mov     eax, [rbp+57h+var_C0]
0x180051af8  mov     r14d, [rbp+57h+var_BC]
0x180051afc  inc     eax
0x180051afe  add     rdi, 90h
0x180051b05  mov     [rbp+57h+var_C0], eax
0x180051b08  cmp     eax, [rbx+108h]
0x180051b0e  jb      loc_180051A31
0x180051b14  test    r12, r12
0x180051b17  jnz     loc_180051DB9
0x180051b1d  test    byte ptr [rbx+4Ch], 40h
0x180051b21  jnz     loc_180051DC7
0x180051b27  mov     eax, 1
0x180051b2c  mov     rcx, [rbp+57h+var_40]
0x180051b30  xor     rcx, rsp; StackCookie
0x180051b33  call    __security_check_cookie
0x180051b38  mov     rbx, [rsp+110h+arg_10]
0x180051b40  add     rsp, 0E0h
0x180051b47  pop     r15
0x180051b49  pop     r14
0x180051b4b  pop     r13
0x180051b4d  pop     r12
0x180051b4f  pop     rdi
0x180051b50  pop     rsi
0x180051b51  pop     rbp
0x180051b52  retn
0x180051b53  mov     rcx, [r15]; hwnd
0x180051b56  xor     r8d, r8d; prc
0x180051b59  mov     rdx, rsi; hdc
0x180051b5c  call    cs:__imp_DrawThemeParentBackground
0x180051b62  jmp     loc_1800519F7
0x180051b67  mov     rcx, rbx; this
0x180051b6a  call    ?_GetBkColor@CReBar@@AEAAKXZ; CReBar::_GetBkColor(void)
0x180051b6f  cmp     eax, 0FFFFFFFFh
0x180051b72  jz      loc_180051A20
0x180051b78  mov     r8d, eax; color
0x180051b7b  lea     rdx, [rbp+57h+Rect]; lprect
0x180051b7f  mov     rcx, rsi; hdc
0x180051b82  call    FillRectClr
0x180051b87  jmp     loc_180051A20
0x180051b8c  mov     r8d, [rdi+30h]
0x180051b90  mov     edx, [rdi+34h]
0x180051b93  mov     ecx, [rdi+38h]
0x180051b96  mov     r9d, [rdi+3Ch]
0x180051b9a  jmp     loc_180051A51
0x180051b9f  test    dword ptr [rdi], 20000000h
0x180051ba5  jz      short loc_180051BF5
0x180051ba7  xor     eax, eax
0x180051ba9  lea     r14, [rbx+134h]
0x180051bb0  cmp     [rdi+30h], eax
0x180051bb3  jnz     short loc_180051C22
0x180051bb5  test    r13d, r13d
0x180051bb8  jz      short loc_180051BFD
0x180051bba  mov     ecx, 2Dh ; '-'; nIndex
0x180051bbf  call    cs:__imp_GetSystemMetrics
0x180051bc5  mov     ecx, [rdi+3Ch]
0x180051bc8  add     ecx, [rdi+34h]
0x180051bcb  add     ecx, eax
0x180051bcd  mov     [rsp+110h+var_D8], r14
0x180051bd2  mov     [rbp+57h+Rect.right], ecx
0x180051bd5  mov     dword ptr [rsp+110h+hdc], 4
0x180051bdd  mov     rcx, [rbx+150h]
0x180051be4  lea     r8, [rbp+57h+Rect]
0x180051be8  mov     rdx, rsi
0x180051beb  call    CCThemeDrawEdge
0x180051bf0  jmp     loc_180051A6E
0x180051bf5  mov     eax, [rbx+0E4h]
0x180051bfb  jmp     short loc_180051BA9
0x180051bfd  mov     ecx, 2Eh ; '.'; nIndex
0x180051c02  call    cs:__imp_GetSystemMetrics
0x180051c08  mov     ecx, [rdi+3Ch]
0x180051c0b  add     ecx, [rdi+34h]
0x180051c0e  add     ecx, eax
0x180051c10  mov     [rsp+110h+var_D8], r14
0x180051c15  mov     [rbp+57h+Rect.bottom], ecx
0x180051c18  mov     dword ptr [rsp+110h+hdc], 8
0x180051c20  jmp     short loc_180051BDD
0x180051c22  test    r13d, r13d
0x180051c25  jz      short loc_180051C94
0x180051c27  mov     ecx, 2Dh ; '-'; nIndex
0x180051c2c  call    cs:__imp_GetSystemMetrics
0x180051c32  mov     ecx, 2
0x180051c37  cdq
0x180051c38  idiv    ecx
0x180051c3a  mov     ecx, 2Eh ; '.'; nIndex
0x180051c3f  add     [rbp+57h+rc.right], eax
0x180051c42  call    cs:__imp_GetSystemMetrics
0x180051c48  mov     rcx, [rbx+150h]
0x180051c4f  lea     r8, [rbp+57h+rc]
0x180051c53  sub     [rbp+57h+rc.top], eax
0x180051c56  mov     rdx, rsi
0x180051c59  mov     [rsp+110h+var_D8], r14
0x180051c5e  mov     dword ptr [rsp+110h+hdc], 2
0x180051c66  call    CCThemeDrawEdge
0x180051c6b  mov     ecx, 2Dh ; '-'; nIndex
0x180051c70  call    cs:__imp_GetSystemMetrics
0x180051c76  mov     ecx, 0FFFFFFFEh
0x180051c7b  cdq
0x180051c7c  idiv    ecx
0x180051c7e  mov     ecx, 2Eh ; '.'; nIndex
0x180051c83  add     [rbp+57h+rc.right], eax
0x180051c86  call    cs:__imp_GetSystemMetrics
0x180051c8c  add     [rbp+57h+rc.top], eax
0x180051c8f  jmp     loc_180051A6E
0x180051c94  mov     ecx, 2Eh ; '.'; nIndex
0x180051c99  call    cs:__imp_GetSystemMetrics
0x180051c9f  mov     ecx, 2
0x180051ca4  cdq
0x180051ca5  idiv    ecx
0x180051ca7  mov     ecx, 2Dh ; '-'; nIndex
0x180051cac  add     [rbp+57h+rc.bottom], eax
0x180051caf  call    cs:__imp_GetSystemMetrics
0x180051cb5  mov     rcx, [rbx+150h]
0x180051cbc  lea     r8, [rbp+57h+rc]
0x180051cc0  sub     [rbp+57h+rc.left], eax
0x180051cc3  mov     rdx, rsi
0x180051cc6  mov     [rsp+110h+var_D8], r14
0x180051ccb  mov     dword ptr [rsp+110h+hdc], 1
0x180051cd3  call    CCThemeDrawEdge
0x180051cd8  mov     ecx, 2Eh ; '.'; nIndex
0x180051cdd  call    cs:__imp_GetSystemMetrics
0x180051ce3  mov     ecx, 0FFFFFFFEh
0x180051ce8  cdq
0x180051ce9  idiv    ecx
0x180051ceb  mov     ecx, 2Dh ; '-'; nIndex
0x180051cf0  add     [rbp+57h+rc.bottom], eax
0x180051cf3  call    cs:__imp_GetSystemMetrics
0x180051cf9  add     [rbp+57h+rc.left], eax
0x180051cfc  jmp     loc_180051A6E
0x180051d01  test    r12, r12
0x180051d04  jnz     short loc_180051D2D
0x180051d06  mov     rcx, rsi; hdc
0x180051d09  call    cs:__imp_CreateCompatibleDC
0x180051d0f  mov     r12, rax
0x180051d12  test    rax, rax
0x180051d15  jz      loc_180051AF5
0x180051d1b  xor     r9d, r9d; int
0x180051d1e  mov     rdx, rsi; HDC
0x180051d21  mov     rcx, rbx; this
0x180051d24  lea     r8d, [r9+1]; int
0x180051d28  call    ?_Realize@CReBar@@AEAAXPEAUHDC__@@HH@Z; CReBar::_Realize(HDC__ *,int,int)
0x180051d2d  mov     rdx, [rdi+60h]; h
0x180051d31  mov     rcx, r12; hdc
0x180051d34  call    cs:__imp_SelectObject
0x180051d3a  mov     ecx, [rbp+57h+rc.bottom]
0x180051d3d  mov     rdx, rdi; struct tagREBARBAND *
0x180051d40  mov     r9d, [rbp+57h+rc.top]; int
0x180051d44  sub     ecx, r9d
0x180051d47  mov     eax, [rbp+57h+rc.right]
0x180051d4a  mov     r8d, [rbp+57h+rc.left]; int
0x180051d4e  sub     eax, r8d
0x180051d51  mov     [rsp+110h+var_D8], r12; HDC
0x180051d56  mov     [rsp+110h+hdc], rsi; hdc
0x180051d5b  mov     dword ptr [rsp+110h+pClipRect], ecx; int
0x180051d5f  mov     rcx, rbx; this
0x180051d62  mov     dword ptr [rsp+110h+pRect], eax; int
0x180051d66  call    ?_BandTileBlt@CReBar@@AEAAXPEAUtagREBARBAND@@HHHHPEAUHDC__@@1@Z; CReBar::_BandTileBlt(tagREBARBAND *,int,int,int,int,HDC__ *,HDC__ *)
0x180051d6b  jmp     loc_180051AEB
0x180051d70  mov     rdx, rdi; struct tagREBARBAND *
0x180051d73  mov     rcx, rbx; this
0x180051d76  call    ?_BandGetBkColor@CReBar@@AEAAKPEBUtagREBARBAND@@@Z; CReBar::_BandGetBkColor(tagREBARBAND const *)
0x180051d7b  mov     rcx, rbx; this
0x180051d7e  mov     r13d, eax
0x180051d81  call    ?_GetBkColor@CReBar@@AEAAKXZ; CReBar::_GetBkColor(void)
0x180051d86  cmp     r13d, eax
0x180051d89  jz      short loc_180051D9A
0x180051d8b  mov     r8d, r13d; color
0x180051d8e  lea     rdx, [rbp+57h+rc]; lprect
0x180051d92  mov     rcx, rsi; hdc
0x180051d95  call    FillRectClr
0x180051d9a  mov     r13d, [rbp+57h+var_B8]
0x180051d9e  jmp     loc_180051AEB
0x180051da3  lea     r8, [rbp+57h+var_B0]
0x180051da7  mov     edx, 10004h
0x180051dac  mov     rcx, r15
  ... truncated ...
```
