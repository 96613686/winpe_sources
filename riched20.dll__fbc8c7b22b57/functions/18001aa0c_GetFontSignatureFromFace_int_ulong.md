# GetFontSignatureFromFace(int,ulong *)

- ea: `0x18001aa0c`
- end: `0x18001aede`
- name: `?GetFontSignatureFromFace@@YAKHPEAK@Z`
- size: `1234`
- prototype: `unsigned int __fastcall(int, unsigned int *)`
- caller_count: `11`
- callee_count: `12`
- tags: ``

## callers

- `0x180005510`
- `0x180006a70`
- `0x18000b5e0`
- `0x18001a434`
- `0x18002b9bc`
- `0x18002da98`
- `0x1800445b4`
- `0x180048e30`
- `0x18005207c`
- `0x1800609e8`
- `0x180089500`

## callees

- `0x180005070`
- `0x180008fec`
- `0x18001aa0c`
- `0x18001e2e0`
- `0x180048df4`
- `0x180060d64`
- `0x180090024`
- `0x180090a6c`
- `0x180090bf4`
- `0x180093aa4`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `USER32!ReleaseDC` at `0x18001ae32`
- `USER32!ReleaseDC` at `0x18001ae8d`
- `USER32!ReleaseDC` at `0x18001ae32`
- `USER32!ReleaseDC` at `0x18001ae8d`
- `USER32!GetDC` at `0x18001aa90`
- `USER32!GetDC` at `0x18001aa90`
- `USP10!ScriptFreeCache` at `0x18001ad36`
- `USP10!ScriptFreeCache` at `0x18001ad36`
- `USP10!ScriptGetCMap` at `0x18001acb5`
- `USP10!ScriptGetCMap` at `0x18001acf0`
- `USP10!ScriptGetCMap` at `0x18001acb5`
- `USP10!ScriptGetCMap` at `0x18001acf0`
- `GDI32!TranslateCharsetInfo` at `0x18001ac10`
- `GDI32!TranslateCharsetInfo` at `0x18001ac10`
- `GDI32!DeleteObject` at `0x18001ae21`
- `GDI32!DeleteObject` at `0x18001ae7c`
- `GDI32!DeleteObject` at `0x18001ae21`
- `GDI32!DeleteObject` at `0x18001ae7c`
- `GDI32!SelectObject` at `0x18001ab51`
- `GDI32!SelectObject` at `0x18001ae12`
- `GDI32!SelectObject` at `0x18001ae6d`
- `GDI32!SelectObject` at `0x18001ab51`
- `GDI32!SelectObject` at `0x18001ae12`
- `GDI32!SelectObject` at `0x18001ae6d`
- `GDI32!EnumFontFamiliesExW` at `0x18001ab29`
- `GDI32!EnumFontFamiliesExW` at `0x18001ab29`

## pseudocode

```c
__int64 __fastcall GetFontSignatureFromFace(int a1, unsigned int *a2)
{
  int v2; // esi
  unsigned int *v4; // rax
  __int64 v5; // r12
  unsigned int v6; // edi
  __int16 v7; // bx
  HDC DC; // r14
  const unsigned __int16 *FontName; // rax
  HFONT v10; // rax
  HFONT v11; // r13
  __int16 v12; // si
  void *v13; // r15
  int v14; // edx
  unsigned int v15; // r8d
  unsigned int TextCharsetInfoPri; // eax
  DWORD v17; // r15d
  DWORD v18; // edx
  int v19; // ecx
  int v20; // edx
  int v21; // ecx
  int v22; // esi
  int v23; // edi
  HRESULT CMap; // eax
  unsigned int v25; // r15d
  _WORD *v26; // rcx
  WORD pwOutGlyphs[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v29; // [rsp+34h] [rbp-CCh]
  SCRIPT_CACHE psc; // [rsp+38h] [rbp-C8h] BYREF
  HGDIOBJ v31; // [rsp+40h] [rbp-C0h]
  unsigned int *v32; // [rsp+48h] [rbp-B8h]
  tagCHARSETINFO v33; // [rsp+50h] [rbp-B0h] BYREF
  tagLOGFONTW Logfont; // [rsp+70h] [rbp-90h] BYREF
  struct tagTEXTMETRICW v35; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v36[32]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  v32 = a2;
  v4 = a2;
  if ( a1 < 0 || a1 >= dword_1800A72B4 )
    return 0;
  v5 = 2LL * a1;
  v6 = *((_DWORD *)lpMem + 4 * a1 + 2);
  v7 = *((_WORD *)lpMem + 8 * a1 + 7);
  if ( (v7 & 1) != 0 )
    goto LABEL_57;
  memset_0(&Logfont, 0, sizeof(Logfont));
  DC = GetDC(0);
  memset_0(&Logfont, 0, sizeof(Logfont));
  FontName = GetFontName(a1);
  CopyLFFontName(&Logfont, FontName);
  if ( Logfont.lfFaceName[0] )
  {
    do
    {
      if ( Logfont.lfFaceName[v2] == 40 )
        break;
      ++v2;
    }
    while ( Logfont.lfFaceName[v2] );
  }
  if ( Logfont.lfFaceName[v2] && v2 > 0 )
  {
    do
    {
      if ( *((_WORD *)&Logfont.lfQuality + (unsigned int)v2) != 32 )
        break;
      --v2;
    }
    while ( v2 > 0 );
    Logfont.lfFaceName[v2] = 0;
  }
  Logfont.lfCharSet = 1;
  EnumFontFamiliesExW(DC, &Logfont, GetFacePriCharSetProc, (LPARAM)&Logfont.lfCharSet, 0);
  v10 = CW32System::CreateFontIndirect(&Logfont);
  v11 = v10;
  if ( v10 )
  {
    v12 = 64;
    v31 = SelectObject(DC, v10);
    v13 = v31;
    memset_0(v36, 0, sizeof(v36));
    if ( !(unsigned int)CW32System::GetTextFace(DC, v14, v36) )
    {
LABEL_59:
      SelectObject(DC, v13);
      DeleteObject(v11);
      ReleaseDC(0, DC);
      return 0;
    }
    if ( (unsigned int)CW32System::wcsicmp(v36, Logfont.lfFaceName)
      && ((GetCharFlags(v36[0], 0) & 0x1E000000) == 0 || (GetCharFlags(Logfont.lfFaceName[0], 0) & 0x300000) == 0) )
    {
      v7 |= 2u;
      goto LABEL_49;
    }
    memset(&v33, 0, sizeof(v33));
    TextCharsetInfoPri = GetTextCharsetInfoPri(DC, &v33.fs, v15);
    v17 = v33.fs.fsUsb[0];
    v18 = v33.fs.fsCsb[0];
    v29 = TextCharsetInfoPri;
    if ( CW32System::_dwPlatformId == 1 )
      v17 = 0;
    if ( !(v17 | v33.fs.fsCsb[0]) )
    {
      if ( !TranslateCharsetInfo((DWORD *)TextCharsetInfoPri, &v33, 1u) )
        goto LABEL_48;
      v18 = v33.fs.fsCsb[0];
    }
    v19 = v18 | 0x200000;
    psc = 0;
    pwOutGlyphs[0] = 0;
    if ( (v17 & 0x8000) == 0 )
      v19 = v18;
    v20 = v19 | 0x400000;
    if ( (v17 & 0x100000) == 0 )
      v20 = v19;
    v21 = v20 | 0x200;
    if ( (v17 & 0x400) == 0 )
      v21 = v20;
    v22 = v21 | 0x800000;
    if ( (v17 & 0x4000000) == 0 )
      v22 = v21;
    if ( (v22 & 0x610860) != 0 && (v22 & 1) == 0 && GetUniscribe() )
    {
      v23 = v22 | 0x1000;
      if ( ScriptGetCMap(DC, &psc, L"a", 1, 0, pwOutGlyphs) )
        v23 = v22;
      CMap = ScriptGetCMap(DC, &psc, L"0", 1, 0, pwOutGlyphs);
      v25 = v29;
      v22 = v23 | 0x2000;
      if ( CMap )
        v22 = v23;
      if ( v29 - 177 > 1 && (v22 & 0x3000) == 0x3000 )
        v7 |= 0x10u;
      if ( psc )
        ScriptFreeCache(&psc);
    }
    else
    {
      v25 = v29;
    }
    v6 = v22 | 0x3000;
    if ( (v22 & 1) == 0 )
      v6 = v22;
    v12 = 64;
    if ( v25 == 2 )
    {
      v13 = v31;
      if ( (v6 & 0x3FFFFFFF) == 0 )
        v6 |= 0x4000u;
LABEL_49:
      memset(&v35, 0, sizeof(v35));
      if ( (unsigned int)CW32System::GetTextMetrics(DC, &v35) )
      {
        v7 = ((v35.tmPitchAndFamily & 0xE) == 0 ? 8 : 0) | v35.tmPitchAndFamily & 4 | v7 & 0xFFF3;
        if ( (v7 & 2) == 0 && (v6 & 0x10000) != 0 )
        {
          if ( !v35.tmDescent || v35.tmAscent / v35.tmDescent >= 3 )
            v12 = 0;
          v7 = v12 | v7 & 0xFFBF;
        }
        SelectObject(DC, v13);
        DeleteObject(v11);
        goto LABEL_56;
      }
      goto LABEL_59;
    }
LABEL_48:
    v13 = v31;
    goto LABEL_49;
  }
LABEL_56:
  ReleaseDC(0, DC);
  v26 = lpMem;
  v7 |= 1u;
  v4 = v32;
  *((_DWORD *)lpMem + 2 * v5 + 2) = v6;
  v26[4 * v5 + 7] = v7;
LABEL_57:
  if ( !v4 )
    return v6;
  *v4 = v6;
  return !_bittest16(&v7, 1u) & (unsigned __int8)((v6 & 0x3FFFFFFF) != 0);
}

```

## disassembly

```asm
0x18001aa0c  mov     [rsp-8+arg_10], rbx
0x18001aa11  push    rbp
0x18001aa12  push    rsi
0x18001aa13  push    rdi
0x18001aa14  push    r12
0x18001aa16  push    r13
0x18001aa18  push    r14
0x18001aa1a  push    r15
0x18001aa1c  lea     rbp, [rsp-60h]
0x18001aa21  sub     rsp, 160h
0x18001aa28  mov     rax, cs:__security_cookie
0x18001aa2f  xor     rax, rsp
0x18001aa32  mov     [rbp+90h+var_40], rax
0x18001aa36  xor     esi, esi
0x18001aa38  mov     [rsp+190h+var_148], rdx
0x18001aa3d  movsxd  r15, ecx
0x18001aa40  mov     rax, rdx
0x18001aa43  test    ecx, ecx
0x18001aa45  js      loc_18001AE99
0x18001aa4b  cmp     r15d, cs:dword_1800A72B4
0x18001aa52  jge     loc_18001AE99
0x18001aa58  mov     rbx, cs:lpMem
0x18001aa5f  lea     ecx, [rsi+1]
0x18001aa62  mov     r12, r15
0x18001aa65  add     r12, r12
0x18001aa68  mov     edi, [rbx+r12*8+8]
0x18001aa6d  movzx   ebx, word ptr [rbx+r12*8+0Eh]
0x18001aa73  test    cl, bl
0x18001aa75  jnz     loc_18001AE5E
0x18001aa7b  lea     r13d, [rsi+5Ch]
0x18001aa7f  xor     edx, edx; Val
0x18001aa81  mov     r8d, r13d; Size
0x18001aa84  lea     rcx, [rsp+190h+Logfont]; void *
0x18001aa89  call    memset_0
0x18001aa8e  xor     ecx, ecx; hWnd
0x18001aa90  call    cs:__imp_GetDC
0x18001aa97  nop     dword ptr [rax+rax+00h]
0x18001aa9c  mov     r8d, r13d; Size
0x18001aa9f  lea     rcx, [rsp+190h+Logfont]; void *
0x18001aaa4  xor     edx, edx; Val
0x18001aaa6  mov     r14, rax
0x18001aaa9  call    memset_0
0x18001aaae  mov     ecx, r15d; int
0x18001aab1  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x18001aab6  mov     rdx, rax; unsigned __int16 *
0x18001aab9  lea     rcx, [rsp+190h+Logfont]; struct tagLOGFONTW *
0x18001aabe  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x18001aac3  xor     r15d, r15d
0x18001aac6  cmp     [rbp+90h+Logfont.lfFaceName], r15w
0x18001aacb  jz      short loc_18001AAE5
0x18001aacd  movsxd  rax, esi
0x18001aad0  cmp     [rbp+rax*2+90h+Logfont.lfFaceName], 28h ; '('
0x18001aad6  jz      short loc_18001AAE5
0x18001aad8  inc     esi
0x18001aada  movsxd  rax, esi
0x18001aadd  cmp     [rbp+rax*2+90h+Logfont.lfFaceName], r15w
0x18001aae3  jnz     short loc_18001AACD
0x18001aae5  movsxd  rax, esi
0x18001aae8  cmp     [rbp+rax*2+90h+Logfont.lfFaceName], r15w
0x18001aaee  jz      short loc_18001AB0D
0x18001aaf0  test    esi, esi
0x18001aaf2  jle     short loc_18001AB0D
0x18001aaf4  mov     eax, esi
0x18001aaf6  cmp     word ptr [rbp+rax*2+90h+Logfont.lfQuality], 20h ; ' '
0x18001aafc  jnz     short loc_18001AB04
0x18001aafe  dec     esi
0x18001ab00  test    esi, esi
0x18001ab02  jg      short loc_18001AAF4
0x18001ab04  movsxd  rcx, esi
0x18001ab07  mov     [rbp+rcx*2+90h+Logfont.lfFaceName], r15w
0x18001ab0d  lea     r9, [rbp+90h+Logfont.lfCharSet]; lParam
0x18001ab11  mov     [rbp+90h+Logfont.lfCharSet], 1
0x18001ab15  lea     r8, ?GetFacePriCharSetProc@@YAHPEAUtagENUMLOGFONTEXW@@PEAUtagNEWTEXTMETRICW@@H_J@Z; lpProc
0x18001ab1c  mov     [rsp+190h+dwFlags], r15d; dwFlags
0x18001ab21  lea     rdx, [rsp+190h+Logfont]; lpLogfont
0x18001ab26  mov     rcx, r14; hdc
0x18001ab29  call    cs:__imp_EnumFontFamiliesExW
0x18001ab30  nop     dword ptr [rax+rax+00h]
0x18001ab35  lea     rcx, [rsp+190h+Logfont]; struct tagLOGFONTW *
0x18001ab3a  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x18001ab3f  mov     r13, rax
0x18001ab42  test    rax, rax
0x18001ab45  jz      loc_18001AE2D
0x18001ab4b  mov     rdx, rax; h
0x18001ab4e  mov     rcx, r14; hdc
0x18001ab51  call    cs:__imp_SelectObject
0x18001ab58  nop     dword ptr [rax+rax+00h]
0x18001ab5d  mov     esi, 40h ; '@'
0x18001ab62  lea     rcx, [rbp+90h+var_80]; void *
0x18001ab66  mov     r8d, esi; Size
0x18001ab69  mov     [rsp+190h+var_150], rax
0x18001ab6e  xor     edx, edx; Val
0x18001ab70  mov     r15, rax
0x18001ab73  call    memset_0
0x18001ab78  lea     r8, [rbp+90h+var_80]; unsigned __int16 *
0x18001ab7c  mov     rcx, r14; hdc
0x18001ab7f  call    ?GetTextFace@CW32System@@SAHPEAUHDC__@@HPEAG@Z; CW32System::GetTextFace(HDC__ *,int,ushort *)
0x18001ab84  test    eax, eax
0x18001ab86  jz      loc_18001AE67
0x18001ab8c  lea     rdx, [rbp+90h+Logfont.lfFaceName]; unsigned __int16 *
0x18001ab90  lea     rcx, [rbp+90h+var_80]; unsigned __int16 *
0x18001ab94  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x18001ab99  test    eax, eax
0x18001ab9b  jz      short loc_18001ABCA
0x18001ab9d  movzx   ecx, [rbp+90h+var_80]; unsigned int
0x18001aba1  xor     edx, edx; unsigned __int8
0x18001aba3  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x18001aba8  test    eax, 1E000000h
0x18001abad  jz      short loc_18001ABC1
0x18001abaf  movzx   ecx, [rbp+90h+Logfont.lfFaceName]; unsigned int
0x18001abb3  xor     edx, edx; unsigned __int8
0x18001abb5  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x18001abba  test    eax, 300000h
0x18001abbf  jnz     short loc_18001ABCA
0x18001abc1  or      bx, 2
0x18001abc5  jmp     loc_18001AD7D
0x18001abca  xorps   xmm0, xmm0
0x18001abcd  lea     rdx, [rsp+190h+var_140.fs]; lpSig
0x18001abd2  mov     rcx, r14; hdc
0x18001abd5  movups  xmmword ptr [rsp+50h], xmm0
0x18001abda  movups  xmmword ptr [rsp+190h+var_140.fs.fsUsb+8], xmm0
0x18001abdf  call    ?GetTextCharsetInfoPri@@YAIPEAUHDC__@@PEAUtagFONTSIGNATURE@@K@Z; GetTextCharsetInfoPri(HDC__ *,tagFONTSIGNATURE *,ulong)
0x18001abe4  mov     r15d, [rsp+190h+var_140.fs.fsUsb]
0x18001abe9  mov     edx, [rsp+190h+var_140.fs.fsCsb]
0x18001abed  mov     ecx, eax; lpSrc
0x18001abef  xor     eax, eax
0x18001abf1  mov     [rsp+190h+var_15C], ecx
0x18001abf5  lea     r8d, [rax+1]; dwFlags
0x18001abf9  cmp     cs:?_dwPlatformId@CW32System@@0KA, r8d; ulong CW32System::_dwPlatformId
0x18001ac00  cmovz   r15d, eax
0x18001ac04  mov     eax, edx
0x18001ac06  or      eax, r15d
0x18001ac09  jnz     short loc_18001AC28
0x18001ac0b  lea     rdx, [rsp+190h+var_140]; lpCs
0x18001ac10  call    cs:__imp_TranslateCharsetInfo
0x18001ac17  nop     dword ptr [rax+rax+00h]
0x18001ac1c  test    eax, eax
0x18001ac1e  jz      loc_18001AD78
0x18001ac24  mov     edx, [rsp+190h+var_140.fs.fsCsb]
0x18001ac28  xor     edi, edi
0x18001ac2a  mov     ecx, edx
0x18001ac2c  bts     ecx, 15h
0x18001ac30  mov     [rsp+190h+psc], rdi
0x18001ac35  bt      r15d, 0Fh
0x18001ac3a  mov     [rsp+190h+var_160], di
0x18001ac3f  cmovnb  ecx, edx
0x18001ac42  mov     edx, ecx
0x18001ac44  bts     edx, 16h
0x18001ac48  bt      r15d, 14h
0x18001ac4d  cmovnb  edx, ecx
0x18001ac50  mov     ecx, edx
0x18001ac52  bts     ecx, 9
0x18001ac56  bt      r15d, 0Ah
0x18001ac5b  cmovnb  ecx, edx
0x18001ac5e  mov     esi, ecx
0x18001ac60  bts     esi, 17h
0x18001ac64  bt      r15d, 1Ah
0x18001ac69  lea     r15d, [rdi+1]
0x18001ac6d  cmovnb  esi, ecx
0x18001ac70  test    esi, 610860h
0x18001ac76  setnz   cl
0x18001ac79  test    r15b, sil
0x18001ac7c  setz    al
0x18001ac7f  test    al, cl
0x18001ac81  jz      loc_18001AD44
0x18001ac87  call    ?GetUniscribe@@YAPEAVCUniscribe@@XZ; GetUniscribe(void)
0x18001ac8c  test    rax, rax
0x18001ac8f  jz      loc_18001AD44
0x18001ac95  lea     rax, [rsp+190h+var_160]
0x18001ac9a  mov     r9d, r15d; cChars
0x18001ac9d  mov     [rsp+190h+pwOutGlyphs], rax; pwOutGlyphs
0x18001aca2  lea     r8, pwcInChars; "a"
0x18001aca9  lea     rdx, [rsp+190h+psc]; psc
0x18001acae  mov     [rsp+190h+dwFlags], edi; dwFlags
0x18001acb2  mov     rcx, r14; hdc
0x18001acb5  call    cs:__imp_ScriptGetCMap
0x18001acbc  nop     dword ptr [rax+rax+00h]
0x18001acc1  mov     edi, esi
0x18001acc3  lea     r8, a0; "0"
0x18001acca  bts     edi, 0Ch
0x18001acce  lea     rdx, [rsp+190h+psc]; psc
0x18001acd3  test    eax, eax
0x18001acd5  mov     r9d, r15d; cChars
0x18001acd8  lea     rax, [rsp+190h+var_160]
0x18001acdd  mov     rcx, r14; hdc
0x18001ace0  mov     [rsp+190h+pwOutGlyphs], rax; pwOutGlyphs
0x18001ace5  cmovnz  edi, esi
0x18001ace8  mov     [rsp+190h+dwFlags], 0; dwFlags
0x18001acf0  call    cs:__imp_ScriptGetCMap
0x18001acf7  nop     dword ptr [rax+rax+00h]
0x18001acfc  mov     r15d, [rsp+190h+var_15C]
0x18001ad01  mov     esi, edi
0x18001ad03  bts     esi, 0Dh
0x18001ad07  test    eax, eax
0x18001ad09  lea     eax, [r15-0B1h]
0x18001ad10  cmovnz  esi, edi
0x18001ad13  cmp     eax, 1
0x18001ad16  jbe     short loc_18001AD29
0x18001ad18  mov     ecx, 3000h
0x18001ad1d  mov     eax, esi
0x18001ad1f  and     eax, ecx
0x18001ad21  cmp     eax, ecx
0x18001ad23  jnz     short loc_18001AD29
0x18001ad25  or      bx, 10h
0x18001ad29  cmp     [rsp+190h+psc], 0
0x18001ad2f  jz      short loc_18001AD49
0x18001ad31  lea     rcx, [rsp+190h+psc]; psc
0x18001ad36  call    cs:__imp_ScriptFreeCache
0x18001ad3d  nop     dword ptr [rax+rax+00h]
0x18001ad42  jmp     short loc_18001AD49
0x18001ad44  mov     r15d, [rsp+190h+var_15C]
0x18001ad49  mov     edi, esi
0x18001ad4b  mov     eax, 2
0x18001ad50  or      edi, 3000h
0x18001ad56  test    sil, 1
0x18001ad5a  cmovz   edi, esi
0x18001ad5d  lea     esi, [rax+3Eh]
0x18001ad60  cmp     r15d, eax
0x18001ad63  jnz     short loc_18001AD78
0x18001ad65  mov     r15, [rsp+190h+var_150]
0x18001ad6a  test    edi, 3FFFFFFFh
0x18001ad70  jnz     short loc_18001AD7D
0x18001ad72  bts     edi, 0Eh
0x18001ad76  jmp     short loc_18001AD7D
0x18001ad78  mov     r15, [rsp+190h+var_150]
0x18001ad7d  xorps   xmm0, xmm0
0x18001ad80  lea     rdx, [rbp+90h+var_C0]; struct tagTEXTMETRICW *
0x18001ad84  movups  xmmword ptr [rbp+90h+var_C0.tmOverhang], xmm0
0x18001ad88  mov     rcx, r14; HDC
0x18001ad8b  movups  xmmword ptr [rbp+90h+var_C0.tmFirstChar], xmm0
0x18001ad8f  movups  xmmword ptr [rbp+90h+var_C0.tmHeight], xmm0
0x18001ad93  movups  xmmword ptr [rbp+90h+var_C0.tmExternalLeading], xmm0
0x18001ad97  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x18001ad9c  test    eax, eax
0x18001ad9e  jz      loc_18001AE67
0x18001ada4  mov     dl, [rbp+90h+var_C0.tmPitchAndFamily]
0x18001ada7  mov     al, dl
0x18001ada9  and     dl, 0Eh
0x18001adac  and     al, 4
0x18001adae  movzx   ecx, al
0x18001adb1  mov     eax, 0FFFBh
0x18001adb6  and     bx, ax
0x18001adb9  mov     eax, 0FFF7h
0x18001adbe  or      bx, cx
0x18001adc1  and     bx, ax
0x18001adc4  neg     dl
0x18001adc6  sbb     ax, ax
0x18001adc9  not     ax
0x18001adcc  and     ax, 8
0x18001add0  or      bx, ax
0x18001add3  mov     eax, 1
0x18001add8  bt      bx, ax
0x18001addc  setnb   cl
0x18001addf  bt      edi, 10h
0x18001ade3  setb    al
0x18001ade6  test    al, cl
0x18001ade8  jz      short loc_18001AE0C
0x18001adea  mov     ecx, [rbp+90h+var_C0.tmDescent]
0x18001aded  test    ecx, ecx
0x18001adef  jz      short loc_18001ADFC
0x18001adf1  mov     eax, [rbp+90h+var_C0.tmAscent]
0x18001adf4  cdq
0x18001adf5  idiv    ecx
0x18001adf7  cmp     eax, 3
0x18001adfa  jl      short loc_18001AE01
0x18001adfc  xor     eax, eax
0x18001adfe  movzx   esi, ax
0x18001ae01  mov     eax, 0FFBFh
0x18001ae06  and     bx, ax
0x18001ae09  or      bx, si
0x18001ae0c  mov     rdx, r15; h
0x18001ae0f  mov     rcx, r14; hdc
0x18001ae12  call    cs:__imp_SelectObject
0x18001ae19  nop     dword ptr [rax+rax+00h]
0x18001ae1e  mov     rcx, r13; ho
0x18001ae21  call    cs:__imp_DeleteObject
0x18001ae28  nop     dword ptr [rax+rax+00h]
0x18001ae2d  mov     rdx, r14; hDC
0x18001ae30  xor     ecx, ecx; hWnd
0x18001ae32  call    cs:__imp_ReleaseDC
0x18001ae39  nop     dword ptr [rax+rax+00h]
0x18001ae3e  mov     rcx, cs:lpMem
0x18001ae45  or      bx, 1
0x18001ae49  mov     rax, [rsp+190h+var_148]
0x18001ae4e  xor     esi, esi
0x18001ae50  mov     [rcx+r12*8+8], edi
0x18001ae55  mov     [rcx+r12*8+0Eh], bx
0x18001ae5b  lea     ecx, [rsi+1]
0x18001ae5e  test    rax, rax
0x18001ae61  jnz     short loc_18001AEC3
0x18001ae63  mov     eax, edi
0x18001ae65  jmp     short loc_18001AE9B
0x18001ae67  mov     rdx, r15; h
0x18001ae6a  mov     rcx, r14; hdc
0x18001ae6d  call    cs:__imp_SelectObject
0x18001ae74  nop     dword ptr [rax+rax+00h]
0x18001ae79  mov     rcx, r13; ho
0x18001ae7c  call    cs:__imp_DeleteObject
0x18001ae83  nop     dword ptr [rax+rax+00h]
0x18001ae88  mov     rdx, r14; hDC
  ... truncated ...
```
