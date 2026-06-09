# CUIFButton2::OnPaintTheme(HDC__ *)

- ea: `0x18007af80`
- end: `0x18007b4fe`
- name: `?OnPaintTheme@CUIFButton2@@MEAAHPEAUHDC__@@@Z`
- size: `1406`
- prototype: `__int64 __fastcall(CUIFButton2 *__hidden this, HDC hdc)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18007af80`
- `0x180094504`
- `0x180094964`
- `0x1800d9e38`
- `0x1800da778`
- `0x1800e3360`
- `0x180101a1c`
- `0x180102eac`
- `0x180103130`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `USER32!GetSysColor` at `0x18007b2e7`
- `USER32!GetSysColor` at `0x18007b2e7`
- `GDI32!GetTextColor` at `0x18007b2f3`
- `GDI32!GetTextColor` at `0x18007b2f3`
- `GDI32!DeleteObject` at `0x18007b47c`
- `GDI32!DeleteObject` at `0x18007b485`
- `GDI32!DeleteObject` at `0x18007b47c`
- `GDI32!DeleteObject` at `0x18007b485`
- `GDI32!SelectObject` at `0x18007b001`
- `GDI32!SelectObject` at `0x18007b4ce`
- `GDI32!SelectObject` at `0x18007b001`
- `GDI32!SelectObject` at `0x18007b4ce`
- `GDI32!GetStockObject` at `0x18007b44f`
- `GDI32!GetStockObject` at `0x18007b44f`
- `GDI32!SetBkMode` at `0x18007b304`
- `GDI32!SetBkMode` at `0x18007b37f`
- `GDI32!SetBkMode` at `0x18007b304`
- `GDI32!SetBkMode` at `0x18007b37f`
- `GDI32!SetTextColor` at `0x18007b338`
- `GDI32!SetTextColor` at `0x18007b374`
- `GDI32!SetTextColor` at `0x18007b338`
- `GDI32!SetTextColor` at `0x18007b374`

## pseudocode

```c
__int64 __fastcall CUIFButton2::OnPaintTheme(CUIFButton2 *this, HDC hdc)
{
  unsigned int v2; // r14d
  unsigned __int64 v3; // rdi
  __int64 v4; // rbx
  void *v5; // rsi
  HWND v8; // rdx
  HGDIOBJ v9; // rax
  int v10; // r8d
  unsigned int v11; // r12d
  int v12; // eax
  int v13; // r10d
  int v14; // esi
  int v15; // edx
  int v16; // r9d
  int v17; // eax
  unsigned __int64 v18; // rcx
  int v19; // r8d
  LONG v20; // r10d
  LONG v21; // r11d
  int v22; // r9d
  int v23; // eax
  LONG v24; // r9d
  LONG v25; // esi
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // rax
  _QWORD *v29; // r10
  int (__fastcall *v30)(CUIFButton2 *, _QWORD, __int64, COLORREF *); // rax
  COLORREF TextColor; // r14d
  int v32; // esi
  LONG top; // edi
  int IsRTL; // eax
  int v35; // r8d
  int v36; // ebx
  int v37; // ebx
  int (__fastcall *v38)(CUIFButton2 *, HDC, _QWORD, struct tagRECT *, struct _IMAGELIST *, int); // rdi
  int v39; // eax
  CUIFIcon *v40; // r8
  struct _IMAGELIST *ImageList; // rax
  __int64 v42; // rcx
  HBITMAP v43; // r8
  HBRUSH UIFBrush; // rax
  HBITMAP v45; // rdi
  HBRUSH StockObject; // rax
  HBITMAP v47; // rbx
  const int *v49; // [rsp+38h] [rbp-31h]
  COLORREF color; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v51; // [rsp+54h] [rbp-15h]
  HGDIOBJ v52; // [rsp+58h] [rbp-11h]
  UINT v53[2]; // [rsp+60h] [rbp-9h]
  RECT v54; // [rsp+68h] [rbp-1h] BYREF
  struct tagRECT v55; // [rsp+78h] [rbp+Fh] BYREF

  v51 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v54 = 0;
  v55 = 0;
  if ( (unsigned int)CUIIsThemeActive()
    && (!*((_QWORD *)this + 5) || *((_QWORD *)this + 3) || (int)CUIFTheme::InternalOpenThemeData(this, v8) >= 0) )
  {
    v9 = SelectObject(hdc, *((HGDIOBJ *)this + 14));
    v10 = 0;
    v52 = v9;
    if ( *((_DWORD *)this + 26) )
    {
      if ( *((_DWORD *)this + 50) )
      {
        v11 = (*((_DWORD *)this + 21) & 0x800) != 0 ? 3 : 5;
      }
      else
      {
        v12 = *((_DWORD *)this + 36);
        if ( v12 == 1 )
        {
          v11 = 3;
        }
        else
        {
          v11 = 2;
          if ( v12 != 2 )
            v11 = 1;
        }
      }
    }
    else
    {
      v11 = (*((_DWORD *)this + 21) & 0x800) != 0 ? 1 : 4;
    }
    v13 = *((_DWORD *)this + 22);
    v14 = *((_DWORD *)this + 23);
    v15 = *((_DWORD *)this + 24);
    if ( *((_QWORD *)this + 19) )
      v3 = *(_QWORD *)((char *)this + 212);
    if ( *((_QWORD *)this + 20) )
    {
      v4 = *(_QWORD *)((char *)this + 204);
    }
    else if ( *((_QWORD *)this + 23) )
    {
      v4 = *(_QWORD *)((char *)this + 220);
    }
    v16 = *((_DWORD *)this + 21);
    v53[0] = v16 & 0x400;
    if ( (v16 & 0x400) != 0 )
    {
      if ( HIDWORD(v3) && HIDWORD(v4) )
        v10 = 2;
      LODWORD(v18) = v10 + HIDWORD(v4) + HIDWORD(v3);
      v19 = v4;
      if ( (int)v3 > (int)v4 )
        v19 = v3;
    }
    else
    {
      if ( !(_DWORD)v3 || (v17 = 2, !(_DWORD)v4) )
        v17 = 0;
      v18 = HIDWORD(v3);
      v19 = v3 + v17 + v4;
      if ( SHIDWORD(v3) <= SHIDWORD(v4) )
        LODWORD(v18) = HIDWORD(v4);
    }
    switch ( v16 & 3 )
    {
      case 0:
        goto LABEL_36;
      case 1:
        v20 = (v13 + v15 - v19) / 2;
        v21 = v19 + v20;
        goto LABEL_38;
      case 2:
        v20 = v15 - v3 - 2;
        break;
      default:
LABEL_36:
        v20 = v13 + 2;
        break;
    }
    v21 = v20 + v19;
LABEL_38:
    v22 = v16 & 0xC;
    if ( v22 )
    {
      v23 = *((_DWORD *)this + 25);
      if ( v22 == 4 )
      {
        color = 4;
        v24 = (v14 + v23 - (int)v18) / 2;
        v25 = v18 + v24;
        goto LABEL_44;
      }
      if ( v22 == 8 )
      {
        color = 8;
        v24 = v23 - v18 - 2;
        v25 = v23 - 2;
        goto LABEL_44;
      }
    }
    v24 = v14 + 2;
    color = 0;
    v25 = v14 + 2 + v18;
LABEL_44:
    if ( v53[0] )
    {
      v55.top = v24;
      v54.bottom = v25;
      v55.left = (v20 + v21 - (int)v4) / 2;
      v55.right = v4 + v55.left;
      v54.left = (v20 + v21 - (int)v3) / 2;
      v55.bottom = v24 + HIDWORD(v4);
      v54.top = v25 - HIDWORD(v3);
      v54.right = v54.left + v3;
    }
    else
    {
      v55.left = v20;
      v54.left = v21 - v3;
      v55.top = (v24 + v25 - HIDWORD(v4)) / 2;
      v55.right = v20 + v4;
      v55.bottom = HIDWORD(v4) + v55.top;
      v54.top = (v24 + v25 - HIDWORD(v3)) / 2;
      v54.right = v21;
      v54.bottom = HIDWORD(v3) + v54.top;
    }
    if ( (unsigned int)CUIFObject::IsRTL(this) )
      *(_DWORD *)(*((_QWORD *)this + 6) + 8LL) = 1;
    if ( (**(int (__fastcall ***)(__int64, HDC, _QWORD, char *, _QWORD))this)(v26, hdc, v11, (char *)this + 88, 0) < 0 )
      goto LABEL_68;
    v27 = *((_QWORD *)this + 19);
    if ( v27 )
    {
      v28 = -1;
      do
        ++v28;
      while ( *(_WORD *)(v27 + 2 * v28) );
      v29 = *(_QWORD **)this;
      *(_QWORD *)v53 = v28;
      if ( *((_DWORD *)this + 30) )
      {
        v30 = (int (__fastcall *)(CUIFButton2 *, _QWORD, __int64, COLORREF *))v29[9];
        color = 0;
        if ( v30(this, v11, 3803, &color) < 0 )
          color = GetSysColor(8);
        TextColor = GetTextColor(hdc);
        v32 = SetBkMode(hdc, 1);
        top = v54.top;
        IsRTL = CUIFObject::IsRTL(this);
        v36 = v35 - 2;
        if ( !IsRTL )
          v36 = v35;
        SetTextColor(hdc, color);
        FLExtTextOutW(hdc, v36, top, 4u, &v54, *((LPCWSTR *)this + 19), v53[0], v49);
        SetTextColor(hdc, TextColor);
        SetBkMode(hdc, v32);
      }
      else if ( ((int (__fastcall *)(CUIFButton2 *, HDC, _QWORD))v29[2])(this, hdc, v11) < 0 )
      {
LABEL_68:
        v5 = v52;
        goto LABEL_69;
      }
    }
    if ( *((_QWORD *)this + 20) )
    {
      v37 = *((_DWORD *)this + 44);
      v38 = *(int (__fastcall **)(CUIFButton2 *, HDC, _QWORD, struct tagRECT *, struct _IMAGELIST *, int))(*(_QWORD *)this + 24LL);
      v39 = CUIFObject::IsRTL(this);
      ImageList = CUIFIcon::GetImageList(v40, v39);
      if ( v38(this, hdc, v11, &v55, ImageList, v37) < 0 )
      {
        v2 = v51;
        goto LABEL_68;
      }
    }
    else if ( *((_QWORD *)this + 23) )
    {
      if ( (unsigned int)CUIFObject::IsRTL(this) )
      {
        UIFBrush = (HBRUSH)CUIFObject::GetUIFBrush(v42, 9);
        v45 = CUIMirrorBitmap(*((HBITMAP *)this + 23), UIFBrush);
        StockObject = (HBRUSH)GetStockObject(4);
        v47 = CUIMirrorBitmap(*((HBITMAP *)this + 24), StockObject);
        DrawMaskBmpOnDC(hdc, &v55, v45, v47);
        DeleteObject(v45);
        DeleteObject(v47);
      }
      else
      {
        DrawMaskBmpOnDC(hdc, &v55, v43, *((HBITMAP *)this + 24));
      }
    }
    v2 = 1;
    goto LABEL_68;
  }
LABEL_69:
  if ( (unsigned int)CUIFObject::IsRTL(this) )
    *(_DWORD *)(*((_QWORD *)this + 6) + 8LL) = 0;
  if ( v5 )
    SelectObject(hdc, v5);
  return v2;
}

```

## disassembly

```asm
0x18007af80  mov     [rsp-8+arg_10], rbx
0x18007af85  push    rbp
0x18007af86  push    rsi
0x18007af87  push    rdi
0x18007af88  push    r12
0x18007af8a  push    r13
0x18007af8c  push    r14
0x18007af8e  push    r15
0x18007af90  lea     rbp, [rsp-27h]
0x18007af95  sub     rsp, 90h
0x18007af9c  mov     rax, cs:__security_cookie
0x18007afa3  xor     rax, rsp
0x18007afa6  mov     [rbp+57h+var_38], rax
0x18007afaa  xor     r12d, r12d
0x18007afad  xorps   xmm0, xmm0
0x18007afb0  xorps   xmm1, xmm1
0x18007afb3  mov     [rbp+57h+var_6C], r12d
0x18007afb7  mov     r14d, r12d
0x18007afba  mov     edi, r12d
0x18007afbd  mov     ebx, r12d
0x18007afc0  mov     esi, r12d
0x18007afc3  movups  xmmword ptr [rbp+57h+var_58.left], xmm0
0x18007afc7  mov     r13, rdx
0x18007afca  mov     r15, rcx
0x18007afcd  movups  xmmword ptr [rbp+57h+var_48.left], xmm1
0x18007afd1  call    ?CUIIsThemeActive@@YAHXZ; CUIIsThemeActive(void)
0x18007afd6  test    eax, eax
0x18007afd8  jz      loc_18007B4AF
0x18007afde  cmp     [r15+28h], r12
0x18007afe2  jz      short loc_18007AFFA
0x18007afe4  cmp     [r15+18h], r12
0x18007afe8  jnz     short loc_18007AFFA
0x18007afea  mov     rcx, r15; this
0x18007afed  call    ?InternalOpenThemeData@CUIFTheme@@QEAAJPEAUHWND__@@@Z; CUIFTheme::InternalOpenThemeData(HWND__ *)
0x18007aff2  test    eax, eax
0x18007aff4  js      loc_18007B4AF
0x18007affa  mov     rdx, [r15+70h]; h
0x18007affe  mov     rcx, r13; hdc
0x18007b001  call    cs:__imp_SelectObject
0x18007b007  xor     r8d, r8d
0x18007b00a  mov     [rbp+57h+var_68], rax
0x18007b00e  mov     r11d, 2
0x18007b014  cmp     [r15+68h], r8d
0x18007b018  jnz     short loc_18007B032
0x18007b01a  mov     eax, [r15+54h]
0x18007b01e  and     eax, 800h
0x18007b023  neg     eax
0x18007b025  sbb     r12d, r12d
0x18007b028  and     r12d, 0FFFFFFFDh
0x18007b02c  add     r12d, 4
0x18007b030  jmp     short loc_18007B073
0x18007b032  cmp     [r15+0C8h], r8d
0x18007b039  jz      short loc_18007B053
0x18007b03b  mov     eax, [r15+54h]
0x18007b03f  and     eax, 800h
0x18007b044  neg     eax
0x18007b046  sbb     r12d, r12d
0x18007b049  and     r12d, 0FFFFFFFEh
0x18007b04d  add     r12d, 5
0x18007b051  jmp     short loc_18007B073
0x18007b053  mov     eax, [r15+90h]
0x18007b05a  cmp     eax, 1
0x18007b05d  jnz     short loc_18007B065
0x18007b05f  lea     r12d, [rax+2]
0x18007b063  jmp     short loc_18007B073
0x18007b065  mov     r12d, r11d
0x18007b068  cmp     eax, r11d
0x18007b06b  jz      short loc_18007B073
0x18007b06d  mov     r12d, 1
0x18007b073  mov     r10d, [r15+58h]
0x18007b077  mov     esi, [r15+5Ch]
0x18007b07b  mov     edx, [r15+60h]
0x18007b07f  cmp     [r15+98h], r8
0x18007b086  jz      short loc_18007B08F
0x18007b088  mov     rdi, [r15+0D4h]
0x18007b08f  cmp     [r15+0A0h], r8
0x18007b096  jz      short loc_18007B0A1
0x18007b098  mov     rbx, [r15+0CCh]
0x18007b09f  jmp     short loc_18007B0B1
0x18007b0a1  cmp     [r15+0B8h], r8
0x18007b0a8  jz      short loc_18007B0B1
0x18007b0aa  mov     rbx, [r15+0DCh]
0x18007b0b1  mov     r9d, [r15+54h]
0x18007b0b5  mov     eax, r9d
0x18007b0b8  and     eax, 400h
0x18007b0bd  mov     [rbp+57h+var_60], eax
0x18007b0c0  jnz     short loc_18007B0EC
0x18007b0c2  test    edi, edi
0x18007b0c4  jz      short loc_18007B0CD
0x18007b0c6  mov     eax, r11d
0x18007b0c9  test    ebx, ebx
0x18007b0cb  jnz     short loc_18007B0D0
0x18007b0cd  mov     eax, r8d
0x18007b0d0  lea     r8d, [rax+rbx]
0x18007b0d4  mov     rcx, rdi
0x18007b0d7  shr     rcx, 20h
0x18007b0db  mov     rax, rbx
0x18007b0de  shr     rax, 20h
0x18007b0e2  add     r8d, edi
0x18007b0e5  cmp     ecx, eax
0x18007b0e7  cmovle  ecx, eax
0x18007b0ea  jmp     short loc_18007B11A
0x18007b0ec  mov     rcx, rdi
0x18007b0ef  shr     rcx, 20h
0x18007b0f3  test    ecx, ecx
0x18007b0f5  jz      short loc_18007B105
0x18007b0f7  mov     rax, rbx
0x18007b0fa  shr     rax, 20h
0x18007b0fe  test    eax, eax
0x18007b100  jz      short loc_18007B105
0x18007b102  mov     r8d, r11d
0x18007b105  mov     rax, rbx
0x18007b108  shr     rax, 20h
0x18007b10c  add     ecx, eax
0x18007b10e  add     ecx, r8d
0x18007b111  mov     r8d, ebx
0x18007b114  cmp     edi, ebx
0x18007b116  cmovg   r8d, edi
0x18007b11a  mov     eax, r9d
0x18007b11d  and     eax, 3
0x18007b120  jz      short loc_18007B148
0x18007b122  sub     eax, 1
0x18007b125  jz      short loc_18007B134
0x18007b127  cmp     eax, 1
0x18007b12a  jnz     short loc_18007B148
0x18007b12c  sub     edx, edi
0x18007b12e  lea     r10d, [rdx-2]
0x18007b132  jmp     short loc_18007B14B
0x18007b134  sub     edx, r8d
0x18007b137  lea     eax, [r10+rdx]
0x18007b13b  cdq
0x18007b13c  idiv    r11d
0x18007b13f  mov     r10d, eax
0x18007b142  lea     r11d, [r8+rax]
0x18007b146  jmp     short loc_18007B14F
0x18007b148  add     r10d, r11d
0x18007b14b  lea     r11d, [r10+r8]
0x18007b14f  and     r9d, 0Ch
0x18007b153  jz      short loc_18007B195
0x18007b155  mov     eax, [r15+64h]
0x18007b159  cmp     r9d, 4
0x18007b15d  jz      short loc_18007B178
0x18007b15f  cmp     r9d, 8
0x18007b163  jnz     short loc_18007B195
0x18007b165  sub     eax, ecx
0x18007b167  mov     [rbp+57h+color], 8
0x18007b16e  lea     r9d, [rax-2]
0x18007b172  lea     esi, [rcx+r9]
0x18007b176  jmp     short loc_18007B1A1
0x18007b178  sub     eax, ecx
0x18007b17a  mov     [rbp+57h+color], 4
0x18007b181  add     eax, esi
0x18007b183  mov     r8d, 2
0x18007b189  cdq
0x18007b18a  idiv    r8d
0x18007b18d  mov     r9d, eax
0x18007b190  lea     esi, [rcx+rax]
0x18007b193  jmp     short loc_18007B1A7
0x18007b195  lea     r9d, [rsi+2]
0x18007b199  mov     [rbp+57h+color], r14d
0x18007b19d  lea     esi, [r9+rcx]
0x18007b1a1  mov     r8d, 2
0x18007b1a7  cmp     [rbp+57h+var_60], r14d
0x18007b1ab  jnz     short loc_18007B20D
0x18007b1ad  mov     eax, esi
0x18007b1af  mov     [rbp+57h+var_48.left], r10d
0x18007b1b3  mov     ecx, 2
0x18007b1b8  mov     r8, rbx
0x18007b1bb  shr     r8, 20h
0x18007b1bf  sub     r11d, edi
0x18007b1c2  sub     eax, r8d
0x18007b1c5  mov     [rbp+57h+var_58.left], r11d
0x18007b1c9  add     eax, r9d
0x18007b1cc  cdq
0x18007b1cd  idiv    ecx
0x18007b1cf  mov     ecx, eax
0x18007b1d1  mov     [rbp+57h+var_48.top], eax
0x18007b1d4  lea     eax, [r10+rbx]
0x18007b1d8  mov     [rbp+57h+var_48.right], eax
0x18007b1db  lea     eax, [r8+rcx]
0x18007b1df  mov     ecx, 2
0x18007b1e4  mov     [rbp+57h+var_48.bottom], eax
0x18007b1e7  mov     r8, rdi
0x18007b1ea  shr     r8, 20h
0x18007b1ee  sub     esi, r8d
0x18007b1f1  lea     eax, [r9+rsi]
0x18007b1f5  cdq
0x18007b1f6  idiv    ecx
0x18007b1f8  mov     ecx, eax
0x18007b1fa  mov     [rbp+57h+var_58.top], eax
0x18007b1fd  lea     eax, [r11+rdi]
0x18007b201  mov     [rbp+57h+var_58.right], eax
0x18007b204  lea     eax, [r8+rcx]
0x18007b208  mov     [rbp+57h+var_58.bottom], eax
0x18007b20b  jmp     short loc_18007B258
0x18007b20d  mov     eax, r11d
0x18007b210  mov     [rbp+57h+var_48.top], r9d
0x18007b214  sub     eax, ebx
0x18007b216  mov     [rbp+57h+var_58.bottom], esi
0x18007b219  add     eax, r10d
0x18007b21c  sub     r11d, edi
0x18007b21f  cdq
0x18007b220  mov     rcx, rdi
0x18007b223  idiv    r8d
0x18007b226  shr     rcx, 20h
0x18007b22a  mov     [rbp+57h+var_48.left], eax
0x18007b22d  add     eax, ebx
0x18007b22f  mov     [rbp+57h+var_48.right], eax
0x18007b232  lea     eax, [r10+r11]
0x18007b236  cdq
0x18007b237  shr     rbx, 20h
0x18007b23b  idiv    r8d
0x18007b23e  add     ebx, r9d
0x18007b241  mov     r8d, eax
0x18007b244  mov     [rbp+57h+var_58.left], eax
0x18007b247  mov     eax, esi
0x18007b249  mov     [rbp+57h+var_48.bottom], ebx
0x18007b24c  sub     eax, ecx
0x18007b24e  mov     [rbp+57h+var_58.top], eax
0x18007b251  lea     eax, [r8+rdi]
0x18007b255  mov     [rbp+57h+var_58.right], eax
0x18007b258  mov     rcx, r15; this
0x18007b25b  call    ?IsRTL@CUIFObject@@IEAAHXZ; CUIFObject::IsRTL(void)
0x18007b260  xor     esi, esi
0x18007b262  test    eax, eax
0x18007b264  jz      short loc_18007B271
0x18007b266  mov     rax, [r15+30h]
0x18007b26a  mov     dword ptr [rax+8], 1
0x18007b271  mov     rax, [r15]
0x18007b274  lea     r9, [r15+58h]
0x18007b278  mov     r8d, r12d
0x18007b27b  mov     [rsp+0C0h+var_A0], rsi
0x18007b280  mov     rdx, r13
0x18007b283  mov     rax, [rax]
0x18007b286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b28b  test    eax, eax
0x18007b28d  js      loc_18007B4A8
0x18007b293  mov     r9, [r15+98h]
0x18007b29a  test    r9, r9
0x18007b29d  jz      loc_18007B3BB
0x18007b2a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007b2a7  inc     rax
0x18007b2aa  cmp     [r9+rax*2], si
0x18007b2af  jnz     short loc_18007B2A7
0x18007b2b1  mov     r10, [r15]
0x18007b2b4  mov     qword ptr [rbp+57h+var_60], rax
0x18007b2b8  cmp     [r15+78h], esi
0x18007b2bc  jz      loc_18007B389
0x18007b2c2  mov     rax, [r10+48h]
0x18007b2c6  lea     r9, [rbp+57h+color]
0x18007b2ca  mov     r8d, 0EDBh
0x18007b2d0  mov     [rbp+57h+color], esi
0x18007b2d3  mov     edx, r12d
0x18007b2d6  mov     rcx, r15
0x18007b2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b2de  test    eax, eax
0x18007b2e0  jns     short loc_18007B2F0
0x18007b2e2  mov     ecx, 8; nIndex
0x18007b2e7  call    cs:__imp_GetSysColor
0x18007b2ed  mov     [rbp+57h+color], eax
0x18007b2f0  mov     rcx, r13; hdc
0x18007b2f3  call    cs:__imp_GetTextColor
0x18007b2f9  mov     edx, 1; mode
0x18007b2fe  mov     rcx, r13; hdc
0x18007b301  mov     r14d, eax
0x18007b304  call    cs:__imp_SetBkMode
0x18007b30a  test    dword ptr [r15+54h], 400h
0x18007b312  mov     rcx, r15; this
0x18007b315  mov     r8d, [rbp+57h+var_58.left]
0x18007b319  mov     esi, eax
0x18007b31b  cmovnz  r8d, [rbp+57h+var_58.right]
0x18007b320  mov     edi, [rbp+57h+var_58.top]
0x18007b323  call    ?IsRTL@CUIFObject@@IEAAHXZ; CUIFObject::IsRTL(void)
0x18007b328  mov     edx, [rbp+57h+color]; color
0x18007b32b  lea     ebx, [r8-2]
0x18007b32f  test    eax, eax
0x18007b331  mov     rcx, r13; hdc
0x18007b334  cmovz   ebx, r8d
0x18007b338  call    cs:__imp_SetTextColor
0x18007b33e  mov     rax, qword ptr [rbp+57h+var_60]
0x18007b342  mov     r9d, 4; options
0x18007b348  mov     [rsp+0C0h+var_90], eax; UINT
0x18007b34c  mov     r8d, edi; y
0x18007b34f  mov     rax, [r15+98h]
0x18007b356  mov     edx, ebx; x
0x18007b358  mov     [rsp+0C0h+var_98], rax; LPCWSTR
0x18007b35d  mov     rcx, r13; hdc
0x18007b360  lea     rax, [rbp+57h+var_58]
0x18007b364  mov     [rsp+0C0h+var_A0], rax; RECT *
0x18007b369  call    ?FLExtTextOutW@@YAHPEAUHDC__@@HHIPEBUtagRECT@@PEBGIPEBH@Z; FLExtTextOutW(HDC__ *,int,int,uint,tagRECT const *,ushort const *,uint,int const *)
0x18007b36e  mov     edx, r14d; color
0x18007b371  mov     rcx, r13; hdc
0x18007b374  call    cs:__imp_SetTextColor
0x18007b37a  mov     edx, esi; mode
0x18007b37c  mov     rcx, r13; hdc
0x18007b37f  call    cs:__imp_SetBkMode
0x18007b385  xor     esi, esi
0x18007b387  jmp     short loc_18007B3BB
0x18007b389  lea     rcx, [rbp+57h+var_58]
0x18007b38d  mov     r8d, r12d
  ... truncated ...
```
