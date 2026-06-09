# Button_DrawGlyph(tagBUTN *,HDC__ *,tagRECT const *,uint,int)

- ea: `0x180139e84`
- end: `0x18013a1b9`
- name: `?Button_DrawGlyph@@YAJPEAUtagBUTN@@PEAUHDC__@@PEBUtagRECT@@IH@Z`
- size: `821`
- prototype: `int(struct tagBUTN *, HDC, const struct tagRECT *, unsigned int, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800afcdc`
- `0x1800ddf08`

## callees

- `0x180019a80`
- `0x1800b07e0`
- `0x1800c4030`
- `0x180114520`
- `0x180139d44`
- `0x180139e84`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180139f48`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180139f48`
- `GDI32!DeleteObject` at `0x18013a18a`
- `GDI32!DeleteObject` at `0x18013a18a`
- `GDI32!SetBkMode` at `0x18013a0fd`
- `GDI32!SetBkMode` at `0x18013a174`
- `GDI32!SetBkMode` at `0x18013a0fd`
- `GDI32!SetBkMode` at `0x18013a174`
- `GDI32!SelectObject` at `0x18013a0eb`
- `GDI32!SelectObject` at `0x18013a181`
- `GDI32!SelectObject` at `0x18013a0eb`
- `GDI32!SelectObject` at `0x18013a181`
- `GDI32!CreateFontW` at `0x18013a081`
- `GDI32!CreateFontW` at `0x18013a0dc`
- `GDI32!CreateFontW` at `0x18013a081`
- `GDI32!CreateFontW` at `0x18013a0dc`
- `USER32!GetSystemMetrics` at `0x180139ed2`
- `USER32!GetSystemMetrics` at `0x180139ee9`
- `USER32!GetSystemMetrics` at `0x180139f63`
- `USER32!GetSystemMetrics` at `0x180139f82`
- `USER32!GetSystemMetrics` at `0x18013a003`
- `USER32!GetSystemMetrics` at `0x180139ed2`
- `USER32!GetSystemMetrics` at `0x180139ee9`
- `USER32!GetSystemMetrics` at `0x180139f63`
- `USER32!GetSystemMetrics` at `0x180139f82`
- `USER32!GetSystemMetrics` at `0x18013a003`
- `UxTheme!GetThemeColor` at `0x18013a13a`
- `UxTheme!GetThemeColor` at `0x18013a13a`

## pseudocode

```c
__int64 __fastcall Button_DrawGlyph(struct tagBUTN *a1, HDC a2, const struct tagRECT *a3, char a4, int a5)
{
  int v9; // ebx
  int v10; // r12d
  int SystemMetrics; // eax
  LONG bottom; // r13d
  struct _IMAGELIST *v13; // rdx
  int v14; // r13d
  int v15; // eax
  int v16; // r12d
  int y; // r15d
  int v18; // eax
  int v19; // ecx
  int v20; // edx
  int v21; // eax
  bool v22; // cc
  HFONT FontW; // rax
  int *v24; // r12
  HFONT v25; // r15
  int v26; // eax
  void *v27; // rcx
  COLORREF v28; // eax
  DWORD bItalic; // [rsp+28h] [rbp-49h]
  int dy; // [rsp+30h] [rbp-41h]
  int nDenominator; // [rsp+70h] [rbp-1h] BYREF
  COLORREF pColor; // [rsp+74h] [rbp+3h] BYREF
  int nNumber[2]; // [rsp+78h] [rbp+7h] BYREF

  if ( (*((_BYTE *)a1 + 176) & 8) != 0 )
  {
    v9 = 0;
    nDenominator = 0;
    nNumber[0] = 0;
    v10 = a3->right + ~(2 * GetSystemMetrics(45)) - a3->left;
    SystemMetrics = GetSystemMetrics(46);
    bottom = a3->bottom;
    v13 = (struct _IMAGELIST *)*((_QWORD *)a1 + 23);
    pColor = 1;
    v14 = bottom - 2 * SystemMetrics - a3->top;
    DPISCALEINFO::GetIconSize((struct tagBUTN *)((char *)a1 + 52), v13, &nDenominator, nNumber);
    if ( (*((_BYTE *)a1 + 176) & 2) != 0 )
    {
      v15 = *((_DWORD *)a1 + 43);
      pColor = 8193;
      if ( v15 )
      {
        nNumber[0] = v15;
      }
      else
      {
        nNumber[0] = MulDiv(nNumber[0], v10, nDenominator);
        if ( nNumber[0] >= v14 )
          nNumber[0] = v14;
      }
      nDenominator = v10;
    }
    v16 = a3->left + (v10 - nDenominator) / 2 + GetSystemMetrics(45);
    y = a3->top + (v14 - nNumber[0]) / 2 + GetSystemMetrics(46);
    if ( a5 && ImageList_GetImageCount(*((HIMAGELIST *)a1 + 23)) > 1 )
      v9 = a5 - 1;
    ImageList_DrawEx(
      *((HIMAGELIST *)a1 + 23),
      v9,
      a2,
      v16,
      y,
      nDenominator,
      nNumber[0],
      0xFFFFFFFF,
      0xFFFFFFFF,
      pColor | ((*((_DWORD *)a1 + 15) & 1) << 14));
  }
  else
  {
    v18 = GetSystemMetrics(46);
    if ( (*((_BYTE *)a1 + 176) & 2) != 0 )
    {
      v19 = *((_DWORD *)a1 + 43);
      v20 = a3->bottom + -2 * v18 - a3->top;
      v21 = a3->right - a3->left;
      if ( v19 )
      {
        if ( v21 >= v20 )
          v21 = v20;
        v22 = v21 < v19;
      }
      else
      {
        v19 = v20;
        v22 = v21 < v20;
      }
      if ( v22 )
        v19 = v21;
      FontW = CreateFontW(v19, 0, 0, 0, 400, 0, 0, 0, 2u, 0, 0, 0, 0, L"MARLETT");
      v24 = (int *)((char *)a1 + 172);
    }
    else
    {
      v24 = (int *)((char *)a1 + 172);
      FontW = CreateFontW(*((_DWORD *)a1 + 43), *((_DWORD *)a1 + 42), 0, 0, 400, 0, 0, 0, 2u, 0, 0, 0, 0, L"MARLETT");
    }
    v25 = FontW;
    *(_QWORD *)nNumber = SelectObject(a2, FontW);
    v26 = SetBkMode(a2, 1);
    v27 = (void *)*((_QWORD *)a1 + 24);
    nDenominator = v26;
    if ( v27 && (pColor = 0, GetThemeColor(v27, 11, (a4 < 0) + 1, 3803, &pColor) >= 0) )
      v28 = pColor;
    else
      v28 = -1;
    DrawChar(a2, *v24, bItalic, dy, v28);
    SetBkMode(a2, nDenominator);
    SelectObject(a2, *(HGDIOBJ *)nNumber);
    DeleteObject(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180139e84  mov     [rsp-8+arg_18], rbx
0x180139e89  push    rbp
0x180139e8a  push    rsi
0x180139e8b  push    rdi
0x180139e8c  push    r12
0x180139e8e  push    r13
0x180139e90  push    r14
0x180139e92  push    r15
0x180139e94  lea     rbp, [rsp-1Fh]
0x180139e99  sub     rsp, 90h
0x180139ea0  mov     rax, cs:__security_cookie
0x180139ea7  xor     rax, rsp
0x180139eaa  mov     [rbp+4Fh+var_40], rax
0x180139eae  test    byte ptr [rcx+0B0h], 8
0x180139eb5  mov     r13d, r9d
0x180139eb8  mov     rsi, r8
0x180139ebb  mov     r14, rdx
0x180139ebe  mov     rdi, rcx
0x180139ec1  jz      loc_180139FFE
0x180139ec7  xor     ebx, ebx
0x180139ec9  mov     [rbp+4Fh+nDenominator], ebx
0x180139ecc  mov     [rbp+4Fh+nNumber], ebx
0x180139ecf  lea     ecx, [rbx+2Dh]; nIndex
0x180139ed2  call    cs:__imp_GetSystemMetrics
0x180139ed8  lea     ecx, [rbx+2Eh]; nIndex
0x180139edb  lea     r12d, [rax+rax]
0x180139edf  not     r12d
0x180139ee2  add     r12d, [rsi+8]
0x180139ee6  sub     r12d, [rsi]
0x180139ee9  call    cs:__imp_GetSystemMetrics
0x180139eef  mov     r13d, [rsi+0Ch]
0x180139ef3  lea     rcx, [rdi+34h]; this
0x180139ef7  mov     rdx, [rdi+0B8h]; struct _IMAGELIST *
0x180139efe  lea     r9, [rbp+4Fh+nNumber]; int *
0x180139f02  add     eax, eax
0x180139f04  mov     [rbp+4Fh+pColor], 1
0x180139f0b  sub     r13d, eax
0x180139f0e  lea     r8, [rbp+4Fh+nDenominator]; int *
0x180139f12  sub     r13d, [rsi+4]
0x180139f16  call    ?GetIconSize@DPISCALEINFO@@QEBAHPEAU_IMAGELIST@@PEAH1@Z; DPISCALEINFO::GetIconSize(_IMAGELIST *,int *,int *)
0x180139f1b  lea     r15d, [rbx+2]
0x180139f1f  test    [rdi+0B0h], r15b
0x180139f26  jz      short loc_180139F5E
0x180139f28  mov     eax, [rdi+0ACh]
0x180139f2e  mov     [rbp+4Fh+pColor], 2001h
0x180139f35  test    eax, eax
0x180139f37  jz      short loc_180139F3E
0x180139f39  mov     [rbp+4Fh+nNumber], eax
0x180139f3c  jmp     short loc_180139F5A
0x180139f3e  mov     r8d, [rbp+4Fh+nDenominator]; nDenominator
0x180139f42  mov     edx, r12d; nNumerator
0x180139f45  mov     ecx, [rbp+4Fh+nNumber]; nNumber
0x180139f48  call    cs:__imp_MulDiv
0x180139f4e  mov     [rbp+4Fh+nNumber], eax
0x180139f51  cmp     eax, r13d
0x180139f54  jl      short loc_180139F5A
0x180139f56  mov     [rbp+4Fh+nNumber], r13d
0x180139f5a  mov     [rbp+4Fh+nDenominator], r12d
0x180139f5e  mov     ecx, 2Dh ; '-'; nIndex
0x180139f63  call    cs:__imp_GetSystemMetrics
0x180139f69  sub     r12d, [rbp+4Fh+nDenominator]
0x180139f6d  mov     ecx, 2Eh ; '.'; nIndex
0x180139f72  mov     r8d, eax
0x180139f75  mov     eax, r12d
0x180139f78  cdq
0x180139f79  idiv    r15d
0x180139f7c  add     eax, [rsi]
0x180139f7e  lea     r12d, [rax+r8]
0x180139f82  call    cs:__imp_GetSystemMetrics
0x180139f88  sub     r13d, [rbp+4Fh+nNumber]
0x180139f8c  mov     ecx, eax
0x180139f8e  mov     eax, r13d
0x180139f91  cdq
0x180139f92  idiv    r15d
0x180139f95  add     eax, [rsi+4]
0x180139f98  mov     esi, [rbp+4Fh+arg_20]
0x180139f9b  lea     r15d, [rax+rcx]
0x180139f9f  test    esi, esi
0x180139fa1  jz      short loc_180139FB7
0x180139fa3  mov     rcx, [rdi+0B8h]; himl
0x180139faa  call    ImageList_GetImageCount
0x180139faf  cmp     eax, 1
0x180139fb2  jle     short loc_180139FB7
0x180139fb4  lea     ebx, [rsi-1]
0x180139fb7  mov     eax, [rdi+3Ch]
0x180139fba  mov     r9d, r12d; x
0x180139fbd  mov     rcx, [rdi+0B8h]; himl
0x180139fc4  and     eax, 1
0x180139fc7  shl     eax, 0Eh
0x180139fca  mov     r8, r14; hdcDst
0x180139fcd  or      eax, [rbp+4Fh+pColor]
0x180139fd0  mov     edx, ebx; i
0x180139fd2  mov     [rsp+0C0h+fStyle], eax; fStyle
0x180139fd6  or      eax, 0FFFFFFFFh
0x180139fd9  mov     [rsp+0C0h+rgbFg], eax; rgbFg
0x180139fdd  mov     [rsp+0C0h+rgbBk], eax; rgbBk
0x180139fe1  mov     eax, [rbp+4Fh+nNumber]
0x180139fe4  mov     [rsp+0C0h+dy], eax; dy
0x180139fe8  mov     eax, [rbp+4Fh+nDenominator]
0x180139feb  mov     [rsp+0C0h+bItalic], eax; dx
0x180139fef  mov     [rsp+0C0h+y], r15d; y
0x180139ff4  call    ImageList_DrawEx
0x180139ff9  jmp     loc_18013A190
0x180139ffe  mov     ecx, 2Eh ; '.'; nIndex
0x18013a003  call    cs:__imp_GetSystemMetrics
0x18013a009  mov     r15d, 2
0x18013a00f  xor     ebx, ebx
0x18013a011  test    [rdi+0B0h], r15b
0x18013a018  jz      short loc_18013A090
0x18013a01a  mov     ecx, [rdi+0ACh]
0x18013a020  neg     eax
0x18013a022  lea     edx, [rax+rax]
0x18013a025  mov     eax, [rsi+8]
0x18013a028  sub     edx, [rsi+4]
0x18013a02b  add     edx, [rsi+0Ch]
0x18013a02e  sub     eax, [rsi]
0x18013a030  test    ecx, ecx
0x18013a032  jz      short loc_18013A03D
0x18013a034  cmp     eax, edx
0x18013a036  cmovge  eax, edx
0x18013a039  cmp     eax, ecx
0x18013a03b  jmp     short loc_18013A041
0x18013a03d  mov     ecx, edx
0x18013a03f  cmp     eax, edx
0x18013a041  cmovl   ecx, eax; cHeight
0x18013a044  lea     rax, aMarlett; "MARLETT"
0x18013a04b  mov     [rsp+0C0h+pszFaceName], rax; pszFaceName
0x18013a050  xor     r9d, r9d; cOrientation
0x18013a053  mov     [rsp+0C0h+iPitchAndFamily], ebx; iPitchAndFamily
0x18013a057  xor     r8d, r8d; cEscapement
0x18013a05a  mov     [rsp+0C0h+iQuality], ebx; iQuality
0x18013a05e  xor     edx, edx; cWidth
0x18013a060  mov     [rsp+0C0h+iClipPrecision], ebx; iClipPrecision
0x18013a064  mov     [rsp+0C0h+fStyle], ebx; iOutPrecision
0x18013a068  mov     [rsp+0C0h+rgbFg], r15d; iCharSet
0x18013a06d  mov     [rsp+0C0h+rgbBk], ebx; bStrikeOut
0x18013a071  mov     [rsp+0C0h+dy], ebx; bUnderline
0x18013a075  mov     [rsp+0C0h+bItalic], ebx; bItalic
0x18013a079  mov     [rsp+0C0h+y], 190h; cWeight
0x18013a081  call    cs:__imp_CreateFontW
0x18013a087  lea     r12, [rdi+0ACh]
0x18013a08e  jmp     short loc_18013A0E2
0x18013a090  mov     edx, [rdi+0A8h]; cWidth
0x18013a096  lea     rax, aMarlett; "MARLETT"
0x18013a09d  mov     [rsp+0C0h+pszFaceName], rax; pszFaceName
0x18013a0a2  lea     r12, [rdi+0ACh]
0x18013a0a9  mov     ecx, [r12]; cHeight
0x18013a0ad  xor     r9d, r9d; cOrientation
0x18013a0b0  mov     [rsp+0C0h+iPitchAndFamily], ebx; iPitchAndFamily
0x18013a0b4  xor     r8d, r8d; cEscapement
0x18013a0b7  mov     [rsp+0C0h+iQuality], ebx; iQuality
0x18013a0bb  mov     [rsp+0C0h+iClipPrecision], ebx; iClipPrecision
0x18013a0bf  mov     [rsp+0C0h+fStyle], ebx; iOutPrecision
0x18013a0c3  mov     [rsp+0C0h+rgbFg], r15d; iCharSet
0x18013a0c8  mov     [rsp+0C0h+rgbBk], ebx; bStrikeOut
0x18013a0cc  mov     [rsp+0C0h+dy], ebx; int
0x18013a0d0  mov     [rsp+0C0h+bItalic], ebx; int
0x18013a0d4  mov     [rsp+0C0h+y], 190h; cWeight
0x18013a0dc  call    cs:__imp_CreateFontW
0x18013a0e2  mov     rdx, rax; h
0x18013a0e5  mov     rcx, r14; hdc
0x18013a0e8  mov     r15, rax
0x18013a0eb  call    cs:__imp_SelectObject
0x18013a0f1  mov     edx, 1; mode
0x18013a0f6  mov     rcx, r14; hdc
0x18013a0f9  mov     qword ptr [rbp+4Fh+nNumber], rax
0x18013a0fd  call    cs:__imp_SetBkMode
0x18013a103  mov     rcx, [rdi+0C0h]; hTheme
0x18013a10a  mov     [rbp+4Fh+nDenominator], eax
0x18013a10d  test    rcx, rcx
0x18013a110  jz      short loc_18013A149
0x18013a112  mov     edx, r13d
0x18013a115  mov     [rbp+4Fh+pColor], ebx
0x18013a118  and     dl, 80h
0x18013a11b  lea     rax, [rbp+4Fh+pColor]
0x18013a11f  neg     dl
0x18013a121  mov     qword ptr [rsp+0C0h+y], rax; pColor
0x18013a126  mov     edx, 0Bh; iPartId
0x18013a12b  mov     r9d, 0EDBh; iPropId
0x18013a131  sbb     r8d, r8d
0x18013a134  neg     r8d
0x18013a137  inc     r8d; iStateId
0x18013a13a  call    cs:__imp_GetThemeColor
0x18013a140  test    eax, eax
0x18013a142  js      short loc_18013A149
0x18013a144  mov     eax, [rbp+4Fh+pColor]
0x18013a147  jmp     short loc_18013A14C
0x18013a149  or      eax, 0FFFFFFFFh
0x18013a14c  movzx   r9d, word ptr [rdi+0B8h]
0x18013a154  mov     r8d, r13d
0x18013a157  mov     [rsp+0C0h+rgbBk], eax; color
0x18013a15b  mov     rdx, rsi
0x18013a15e  mov     eax, [r12]
0x18013a162  mov     rcx, r14; hdc
0x18013a165  mov     [rsp+0C0h+y], eax; int
0x18013a169  call    DrawChar
0x18013a16e  mov     edx, [rbp+4Fh+nDenominator]; mode
0x18013a171  mov     rcx, r14; hdc
0x18013a174  call    cs:__imp_SetBkMode
0x18013a17a  mov     rdx, qword ptr [rbp+4Fh+nNumber]; h
0x18013a17e  mov     rcx, r14; hdc
0x18013a181  call    cs:__imp_SelectObject
0x18013a187  mov     rcx, r15; ho
0x18013a18a  call    cs:__imp_DeleteObject
0x18013a190  xor     eax, eax
0x18013a192  mov     rcx, [rbp+4Fh+var_40]
0x18013a196  xor     rcx, rsp; StackCookie
0x18013a199  call    __security_check_cookie
0x18013a19e  mov     rbx, [rsp+0C0h+arg_18]
0x18013a1a6  add     rsp, 90h
0x18013a1ad  pop     r15
0x18013a1af  pop     r14
0x18013a1b1  pop     r13
0x18013a1b3  pop     r12
0x18013a1b5  pop     rdi
0x18013a1b6  pop     rsi
0x18013a1b7  pop     rbp
0x18013a1b8  retn
```
