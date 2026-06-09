# CCcs::MakeFont(CHDC const &,CCharFormat const * const,IProvideFontInfo *,bool)

- ea: `0x1800aca44`
- end: `0x1800ad601`
- name: `?MakeFont@CCcs@@AEAA_NAEBVCHDC@@QEBVCCharFormat@@PEAUIProvideFontInfo@@_N@Z`
- size: `3005`
- prototype: `bool __usercall@<al>(CCcs *__hidden this@<rcx>, const struct CHDC *@<rdx>, const struct CCharFormat *const@<r8>, struct IProvideFontInfo *@<r9>, bool)`
- caller_count: `1`
- callee_count: `29`
- tags: ``

## callers

- `0x1800ac9bc`

## callees

- `0x18000f430`
- `0x180032444`
- `0x180034728`
- `0x1800382e0`
- `0x180044e1c`
- `0x18005674c`
- `0x180056d48`
- `0x18008a3dc`
- `0x1800ac83c`
- `0x1800aca44`
- `0x1800ad608`
- `0x1800ad628`
- `0x1800ad688`
- `0x1800ad6f4`
- `0x1800adadc`
- `0x1800adf98`
- `0x1800ae008`
- `0x1800ae058`
- `0x1800ae144`
- `0x1800aef78`
- `0x1800af038`
- `0x1800ebf28`
- `0x1800f0cb8`
- `0x1800fa8f8`
- `0x18013ce80`
- `0x18013dce6`
- `0x180147b4c`
- `0x18017da94`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800ad129`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800ad4d6`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800ad129`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800ad4d6`

## pseudocode

```c
char __fastcall CCcs::MakeFont(
        CCcs *this,
        const struct CHDC *a2,
        const struct CCharFormat *const a3,
        struct IProvideFontInfo *a4,
        bool a5)
{
  unsigned __int8 v5; // bl
  __int64 v7; // rcx
  __int16 v9; // r14
  char v11; // al
  unsigned __int8 v12; // dl
  BYTE v13; // r10
  CFont *v14; // r13
  int v15; // eax
  unsigned __int16 v16; // ax
  int v17; // ecx
  BYTE v18; // al
  int v19; // eax
  BYTE v20; // al
  BYTE v21; // cl
  BYTE v22; // al
  const unsigned __int16 *FontName; // rax
  bool v24; // r8
  __int64 v25; // r9
  bool v26; // zf
  BYTE lfOutPrecision; // al
  int v28; // ebx
  int v29; // eax
  unsigned __int8 v30; // al
  BYTE v31; // al
  struct IDWriteFont *v32; // rcx
  __int64 v33; // rax
  struct IDWriteFontFace *v34; // rbx
  struct IDWriteFont *DWrite; // rsi
  unsigned int v36; // eax
  unsigned __int8 v37; // al
  char v38; // dl
  __int64 v39; // rdx
  __int16 v40; // ax
  __int64 v41; // rax
  int v42; // eax
  __int128 v43; // xmm1
  struct IDWriteFont *v44; // r15
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  HFONT *v49; // rsi
  bool v50; // bl
  BOOL v52; // r11d
  __int16 v53; // ax
  unsigned __int16 v54; // dx
  WCHAR v55; // cx
  unsigned __int16 *v56; // r10
  WCHAR *lfFaceName; // r8
  HFONT v58; // rbx
  int v59; // eax
  BOOL v60; // r14d
  int v61; // eax
  BYTE v62; // dl
  int v63; // eax
  unsigned __int16 FontNameIndex; // ax
  char FontInfoFlags; // al
  int lfCharSet; // edx
  char v67; // bl
  signed __int16 v68; // r14
  struct IDWriteFontFace *SystemDWriteFontFace; // rax
  HDC ScreenDC; // rax
  void (__fastcall *v71)(struct ICustomTextOut *, __int64); // rbx
  __int64 v72; // rax
  int v73; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v74; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v75; // [rsp+50h] [rbp-B0h]
  char v76; // [rsp+51h] [rbp-AFh]
  __int16 v77; // [rsp+54h] [rbp-ACh]
  struct IDWriteFont *v78; // [rsp+58h] [rbp-A8h] BYREF
  int v79; // [rsp+60h] [rbp-A0h]
  __int128 v80; // [rsp+68h] [rbp-98h] BYREF
  __int64 v81; // [rsp+78h] [rbp-88h]
  struct tagLOGFONTW v82; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v83[128]; // [rsp+E0h] [rbp-20h] BYREF
  char v84; // [rsp+160h] [rbp+60h]
  unsigned __int16 v85[32]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 Src[32]; // [rsp+1B0h] [rbp+B0h] BYREF

  v5 = *((_BYTE *)a3 + 4);
  v7 = *(_QWORD *)a2;
  v9 = *((_WORD *)a3 + 3);
  v78 = a4;
  v75 = v5;
  v77 = v9;
  v76 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 80LL))(v7);
  memset_0(&v82, 0, sizeof(v82));
  CWidthCache::Free((CCcs *)((char *)this + 40));
  v11 = *((_BYTE *)this + 361) & 0xBF;
  *((_BYTE *)this + 352) = (*(_DWORD *)a3 >> 17) & 2;
  *((_BYTE *)this + 361) = v11 | *((_BYTE *)a3 + 2) & 0x40;
  v12 = CW32System::CharSetFromCharRep(v5);
  *((_BYTE *)this + 208) = v12;
  v14 = (CCcs *)((char *)this + 232);
  *((_BYTE *)this + 210) = v5;
  *((_BYTE *)this + 350) = 0;
  if ( v5 == 98 )
    *((_BYTE *)this + 350) = 1;
  v15 = *((__int16 *)a3 + 4);
  *((_WORD *)this + 6) = v15;
  v82.lfHeight = -v15;
  v16 = *((_WORD *)a3 + 8);
  *((_WORD *)this + 102) = v16;
  if ( !*((_WORD *)a3 + 8) )
  {
    v16 = (*(_DWORD *)a3 & 1) != 0 ? 700 : 400;
    *((_WORD *)this + 102) = v16;
  }
  v17 = *(_DWORD *)a3;
  *((_BYTE *)this + 361) &= 0xF3u;
  v82.lfWeight = v16;
  v82.lfItalic = (v17 & 2) != 0;
  *((_BYTE *)this + 361) |= 4 * v82.lfItalic;
  if ( *((_BYTE *)this + 352) == 2 )
  {
    v82.lfCharSet = 0;
  }
  else
  {
    v18 = v12;
    if ( v12 == 0xFE )
      v18 = 1;
    v82.lfCharSet = v18;
  }
  v19 = *((unsigned __int8 *)this + 356);
  v82.lfOutPrecision = 0;
  if ( (_BYTE)v19 )
  {
    v82.lfEscapement = 900 * (4 - v19);
    v82.lfOrientation = v82.lfEscapement;
  }
  v20 = v13;
  if ( (*((_BYTE *)a3 + 52) & 0x20) != 0 )
    v20 = -64;
  v21 = *((_BYTE *)a3 + 5);
  v82.lfClipPrecision = v20;
  *((_BYTE *)this + 355) = v21;
  v22 = *((_BYTE *)a3 + 43);
  *((_BYTE *)this + 357) = v22;
  v82.lfQuality = v22;
  *((_BYTE *)this + 354) = *((_BYTE *)a3 + 61);
  v82.lfPitchAndFamily = v21;
  if ( (v21 & 0xF0u) >= 0x70 )
    v82.lfPitchAndFamily = v21 & 0xF | 0x10;
  *((_WORD *)this + 103) = CW32System::CodePageFromCharRep(v5);
  FontName = CFICache::GetFontName(v9);
  v24 = *((char *)this + 361) < 0 && !v76 && (!FontName || *FontName != 64);
  CopyLFFontName(&v82, FontName, v24);
  v26 = (*((_BYTE *)this + 361) & 0x20) == 0;
  *(_QWORD *)&v80 = v78;
  BYTE8(v80) = v76;
  v81 = 0;
  if ( !v26
    || *((_BYTE *)this + 356)
    && (FontNameIndex = CFICache::GetFontNameIndex(v82.lfFaceName, 1),
        (CFICache::GetFontInfoFlags(FontNameIndex, &v80) & 8) != 0) )
  {
    v82.lfOutPrecision = 7;
    v26 = (CFICache::GetFontInfoFlags((unsigned __int16)v9, &v80) & 4) == 0;
    lfOutPrecision = v82.lfOutPrecision;
    if ( !v26 )
      lfOutPrecision = 9;
  }
  else
  {
    lfOutPrecision = v82.lfOutPrecision;
  }
  v28 = CW32System::_bCharSetSys;
  if ( v76 )
    lfOutPrecision = 7;
  v82.lfOutPrecision = lfOutPrecision;
  v29 = CW32System::_bCharSetSys - 177;
  LOBYTE(v29) = v82.lfCharSet;
  v79 = v29;
  if ( (unsigned int)CW32System::_bCharSetSys - 177 <= 1 && !v82.lfCharSet )
  {
    FontInfoFlags = CFICache::GetFontInfoFlags((unsigned __int16)v9, &v80);
    lfCharSet = v82.lfCharSet;
    if ( (FontInfoFlags & 0xA) == 8 )
      lfCharSet = v28;
    v79 = lfCharSet;
    v82.lfCharSet = lfCharSet;
  }
  if ( v76 )
  {
    v30 = *((_BYTE *)a3 + 63) & 0xF;
    *((_BYTE *)this + 354) = v30;
    v26 = (*(_BYTE *)a3 & 2) == 0;
    v82.lfWidth = v30;
    v31 = v26 ? (*((_WORD *)a3 + 26) & 0x200) != 0 : 2;
    *((_BYTE *)this + 361) &= 0xF3u;
    v32 = v78;
    v82.lfItalic = v31;
    *((_BYTE *)this + 361) |= 4 * v31;
    if ( v32 )
    {
      if ( *((_DWORD *)a3 + 7) )
      {
        v33 = (*(__int64 (__fastcall **)(struct IDWriteFont *))(*(_QWORD *)v32 + 40LL))(v32);
        v34 = (struct IDWriteFontFace *)v33;
        if ( v33 )
        {
          DWrite = (struct IDWriteFont *)GetDWriteFont<IDWriteFontFace>(v33);
          CFont::SetDWriteFontFace((CCcs *)((char *)this + 232), v34, DWrite);
          if ( DWrite )
            (*(void (__fastcall **)(struct IDWriteFont *))(*(_QWORD *)DWrite + 16LL))(DWrite);
          CWidthCache::Free((CCcs *)((char *)this + 40));
          *((_DWORD *)this + 50) = *((_DWORD *)a3 + 7);
          v36 = *(_DWORD *)a3;
          *((_BYTE *)this + 361) &= ~0x40u;
          *((_BYTE *)this + 352) = (v36 >> 17) & 2;
          v37 = CW32System::CharSetFromCharRep(v75);
          *((_BYTE *)this + 210) = v38;
          v39 = 0;
          *((_BYTE *)this + 208) = v37;
          *((_WORD *)this + 6) = *((_WORD *)a3 + 4);
          v40 = *((_WORD *)a3 + 8);
          *((_WORD *)this + 102) = v40;
          if ( !v40 )
            *((_WORD *)this + 102) = (*(_DWORD *)a3 & 1) != 0 ? 700 : 400;
          *((_BYTE *)this + 355) = *((_BYTE *)a3 + 5);
          *((_BYTE *)this + 357) = *((_BYTE *)a3 + 43);
          if ( a5 )
          {
            LODWORD(v81) = 0;
            v41 = *(_QWORD *)v34;
            v80 = 0;
            (*(void (__fastcall **)(struct IDWriteFontFace *, __int128 *))(v41 + 64))(v34, &v80);
            v42 = (__int16)v80;
            *((_WORD *)this + 6) = v80;
            v82.lfHeight = -v42;
          }
          (*(void (__fastcall **)(struct IDWriteFontFace *, __int64))(*(_QWORD *)v34 + 16LL))(v34, v39);
          v43 = *(_OWORD *)&v82.lfWeight;
          v44 = v78;
          *(_OWORD *)v14 = *(_OWORD *)&v82.lfHeight;
          v45 = *(_OWORD *)&v82.lfFaceName[2];
          *(_OWORD *)((char *)this + 248) = v43;
          v46 = *(_OWORD *)&v82.lfFaceName[10];
          *(_OWORD *)((char *)this + 264) = v45;
          v47 = *(_OWORD *)&v82.lfFaceName[18];
          *(_OWORD *)((char *)this + 280) = v46;
          v48 = *(_OWORD *)&v82.lfFaceName[24];
          *(_OWORD *)((char *)this + 296) = v47;
          *(_OWORD *)((char *)this + 308) = v48;
          CCcs::GetMetrics(this, a2, 0, 0, v44, v9);
          v49 = (HFONT *)((char *)this + 328);
          v50 = v76;
          goto LABEL_36;
        }
      }
    }
  }
  if ( (*(_BYTE *)a3 & 3) != 0 )
    v77 = -1;
  v49 = (HFONT *)((char *)this + 328);
  v85[0] = 0;
  if ( *((_QWORD *)this + 41) )
    CFont::Destroy((CCcs *)((char *)this + 232));
  v73 = (_DWORD)this + 360;
  LOBYTE(v25) = v75;
  (*(void (__fastcall **)(_QWORD, struct tagLOGFONTW *, char *, __int64))(**(_QWORD **)a2 + 128LL))(
    *(_QWORD *)a2,
    &v82,
    (char *)this + 232,
    v25);
  LOBYTE(v52) = 0;
  if ( *v49 )
  {
    CCcs::GetMetrics(this, a2, 32, v85, 0, 0xFFFF);
    LOBYTE(v52) = 0;
  }
  if ( !v76 && *((_BYTE *)a3 + 61) )
  {
    CFont::Destroy((CCcs *)((char *)this + 232));
    v82.lfWidth = CW32System::MulDivFunc(*((__int16 *)this + 16), *((unsigned __int8 *)a3 + 61), 100);
    CCcs::GetFontWithMetrics(this, a2, &v82, v75, v73, v85, 0);
    LOBYTE(v52) = 0;
  }
  if ( a5 )
  {
    CSelectFont::CSelectFont((CSelectFont *)v83, a2, (CCcs *)((char *)this + 232));
    v67 = v84;
    v68 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 328LL))(*(_QWORD *)a2);
    CSelectFont::~CSelectFont((CSelectFont *)v83);
    LOBYTE(v52) = 0;
    if ( v67 )
    {
      if ( *((_WORD *)this + 6) != v68 )
      {
        CFICache::SetFontEMSquare(*((_WORD *)a3 + 3), v68);
        CFont::Destroy((CCcs *)((char *)this + 232));
        v82.lfHeight = -v68;
        *((_WORD *)this + 6) = v68;
        CCcs::GetFontWithMetrics(this, a2, &v82, v75, v73, v85, 1);
        LOBYTE(v52) = 0;
      }
    }
  }
  v50 = v76;
  if ( !v76 )
  {
    v58 = 0;
    lfFaceName = v82.lfFaceName;
    v56 = v85;
    do
    {
      v54 = *v56;
      if ( *v56 <= 0x5Au && *lfFaceName >= 0x41u )
        v54 += 32;
      v55 = *lfFaceName;
      if ( (unsigned __int16)(*lfFaceName - 65) <= 0x19u )
        v55 += 32;
      if ( v54 != v55 )
        break;
      ++v56;
      ++lfFaceName;
    }
    while ( v55 );
    v14 = (CCcs *)((char *)this + 232);
    if ( v54 == v55 )
      goto LABEL_57;
    v9 = -1;
    v77 = -1;
    if ( v82.lfCharSet != 2 )
    {
      if ( v82.lfCharSet == 1 )
      {
        if ( *((_BYTE *)this + 209) == 1 )
        {
          v82.lfCharSet = 2;
          CopyLFFontName(&v82, v85, 0);
          v58 = 0;
          if ( !*((_BYTE *)this + 348) )
            v58 = *v49;
          *v49 = 0;
          *((_QWORD *)this + 42) = 0;
          CCcs::GetFontWithMetrics(this, a2, &v82, 0xAu, v73, v85, 0);
          v59 = CW32System::wcsicmp(v85, v82.lfFaceName);
          LOBYTE(v52) = 0;
          v82.lfCharSet = v79;
          v60 = v59 == 0;
LABEL_71:
          if ( v58 )
          {
            if ( v60 )
            {
              DeleteObject(v58);
            }
            else
            {
              CFont::Destroy((CCcs *)((char *)this + 232));
              CFont::SetHFont((CCcs *)((char *)this + 232), v58);
              CCcs::GetMetrics(this, a2, 0, 0, 0, 0xFFFF);
            }
            LOBYTE(v52) = 0;
          }
LABEL_57:
          v9 = v77;
LABEL_58:
          v53 = *((_WORD *)a3 + 3);
          v44 = v78;
          CCcs::TryCreateFontWithCharsetMatching(this, a2, &v82, *((_BYTE *)this + 209), v52, v78, v53, v75, v74, v85);
          v50 = 0;
          goto LABEL_36;
        }
      }
      else if ( (unsigned __int8)(v82.lfCharSet + 79) <= 1u )
      {
        CFont::Destroy((CCcs *)((char *)this + 232));
        CopyLFFontName(&v82, v85, 0);
        CCcs::GetFontWithMetrics(this, a2, &v82, v75, v73, v85, 0);
        LOBYTE(v52) = 0;
        goto LABEL_58;
      }
      if ( *((_BYTE *)this + 353) == 2
        || !(unsigned int)CW32System::IsFECharSet(v82.lfCharSet)
        || CW32System::IsFELCID(CW32System::_syslcid) )
      {
        goto LABEL_58;
      }
      v60 = v52;
      CopyLFFontName(&v82, v85, 0);
      v58 = 0;
      if ( !*((_BYTE *)this + 348) )
        v58 = *v49;
      *v49 = 0;
      *((_QWORD *)this + 42) = 0;
      CCcs::GetFontWithMetrics(this, a2, &v82, v75, v73, v85, 0);
      v63 = CW32System::wcsicmp(v85, v82.lfFaceName);
      LOBYTE(v52) = 0;
      if ( !v63 )
        v60 = 1;
      goto LABEL_71;
    }
    v82.lfCharSet = 0;
    if ( !*((_BYTE *)this + 348) )
      v58 = *v49;
    *v49 = 0;
    *((_QWORD *)this + 42) = 0;
    CCcs::GetFontWithMetrics(this, a2, &v82, 0, v73, v85, 0);
    v61 = CW32System::wcsicmp(v85, v82.lfFaceName);
    v62 = v82.lfCharSet;
    LOBYTE(v52) = 0;
    v60 = 0;
    if ( v61 )
      v62 = v79;
    LOBYTE(v60) = v61 == 0;
    v82.lfCharSet = v62;
    goto LABEL_71;
  }
  v9 = v77;
  v44 = v78;
  if ( *((_BYTE *)this + 349) && *((_BYTE *)this + 209) != v82.lfCharSet )
    *((_BYTE *)this + 209) = v82.lfCharSet;
LABEL_36:
  if ( *v49 )
    goto LABEL_38;
  v9 = 59;
  if ( v50 )
  {
    v78 = 0;
    SystemDWriteFontFace = CW32System::GetSystemDWriteFontFace(v44, &v78);
    CFont::SetDWriteFontFace(v14, SystemDWriteFontFace, v78);
  }
  else
  {
    CFont::SetHFont(v14, CW32System::_hSystemFont);
  }
  if ( *v49 )
  {
    CCcs::GetMetrics(this, a2, 32, v85, 0, 0xFFFF);
    if ( *v49 )
    {
LABEL_38:
      if ( v9 < 0 || (*((_BYTE *)this + 361) & 0x40) != 0 )
      {
        if ( v50 )
          ScreenDC = 0;
        else
          ScreenDC = CW32System::GetScreenDC();
        CHDC::CHDC((CHDC *)&v80, v50, 0, 0, ScreenDC, 0);
        CSelectFont::CSelectFont((CSelectFont *)v83, (struct CHDC *)&v80, v14);
        if ( v84 )
        {
          if ( (*((_BYTE *)this + 361) & 0x40) != 0 && g_pcto )
          {
            v71 = *(void (__fastcall **)(struct ICustomTextOut *, __int64))(*(_QWORD *)g_pcto + 16LL);
            v72 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v80 + 48LL))(v80);
            v71(g_pcto, v72);
          }
          if ( v9 < 0 )
          {
            (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(*(_QWORD *)v80 + 160LL))(v80, 32, Src);
            v9 = CFICache::GetFontNameIndex(Src, 1);
          }
        }
        CSelectFont::~CSelectFont((CSelectFont *)v83);
        CHDC::~CHDC((CHDC *)&v80);
      }
    }
  }
  *((_WORD *)this + 106) = v9;
  return 1;
}

```

## disassembly

```asm
0x1800aca44  push    rbp
0x1800aca46  push    rbx
0x1800aca47  push    rsi
0x1800aca48  push    rdi
0x1800aca49  push    r12
0x1800aca4b  push    r13
0x1800aca4d  push    r14
0x1800aca4f  push    r15
0x1800aca51  lea     rbp, [rsp-108h]
0x1800aca59  sub     rsp, 208h
0x1800aca60  mov     rax, cs:__security_cookie
0x1800aca67  xor     rax, rsp
0x1800aca6a  mov     [rbp+140h+var_50], rax
0x1800aca71  mov     bl, [r8+4]
0x1800aca75  mov     rdi, rcx
0x1800aca78  mov     rcx, [rdx]
0x1800aca7b  mov     r15, r8
0x1800aca7e  movzx   r14d, word ptr [r8+6]
0x1800aca83  mov     r12, rdx
0x1800aca86  mov     [rsp+240h+var_1E8], r9
0x1800aca8b  mov     [rsp+240h+var_1F0], bl
0x1800aca8f  mov     rax, [rcx]
0x1800aca92  mov     [rsp+240h+var_1EC], r14d
0x1800aca97  mov     rax, [rax+50h]
0x1800aca9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acaa0  xor     edx, edx; Val
0x1800acaa2  mov     [rsp+240h+var_1EF], al
0x1800acaa6  lea     rcx, [rbp+140h+var_1C0]; void *
0x1800acaaa  mov     sil, al
0x1800acaad  lea     r8d, [rdx+5Ch]; Size
0x1800acab1  call    memset_0
0x1800acab6  lea     rcx, [rdi+28h]; this
0x1800acaba  call    ?Free@CWidthCache@@QEAAXXZ; CWidthCache::Free(void)
0x1800acabf  mov     ecx, [r15]
0x1800acac2  mov     r10w, 40h ; '@'
0x1800acac7  mov     al, [rdi+169h]
0x1800acacd  shr     ecx, 11h
0x1800acad0  and     al, 0BFh
0x1800acad2  and     cl, 2
0x1800acad5  mov     [rdi+160h], cl
0x1800acadb  mov     cl, [r15+2]
0x1800acadf  and     cl, r10b
0x1800acae2  or      cl, al
0x1800acae4  mov     [rdi+169h], cl
0x1800acaea  mov     cl, bl; unsigned __int8
0x1800acaec  call    ?CharSetFromCharRep@CW32System@@SAEE@Z; CW32System::CharSetFromCharRep(uchar)
0x1800acaf1  xor     r8d, r8d
0x1800acaf4  movzx   edx, al
0x1800acaf7  mov     [rdi+0D0h], dl
0x1800acafd  lea     r13, [rdi+0E8h]
0x1800acb04  mov     [rdi+0D2h], bl
0x1800acb0a  mov     [r13+76h], r8b
0x1800acb0e  lea     r9d, [r8+1]
0x1800acb12  cmp     bl, 62h ; 'b'
0x1800acb15  jz      loc_1800AD234
0x1800acb1b  movsx   eax, word ptr [r15+8]
0x1800acb20  mov     [rdi+0Ch], ax
0x1800acb24  neg     eax
0x1800acb26  mov     [rbp+140h+var_1C0.lfHeight], eax
0x1800acb29  movzx   eax, word ptr [r15+10h]
0x1800acb2e  mov     [rdi+0CCh], ax
0x1800acb35  cmp     [r15+10h], r8w
0x1800acb3a  jz      loc_1800AD240
0x1800acb40  mov     ecx, [r15]
0x1800acb43  and     byte ptr [rdi+169h], 0F3h
0x1800acb4a  movzx   eax, ax
0x1800acb4d  shr     ecx, 1
0x1800acb4f  and     cl, r9b
0x1800acb52  mov     [rbp+140h+var_1C0.lfWeight], eax
0x1800acb55  mov     al, cl
0x1800acb57  mov     [rbp+140h+var_1C0.lfItalic], cl
0x1800acb5a  shl     al, 2
0x1800acb5d  or      [rdi+169h], al
0x1800acb63  cmp     byte ptr [rdi+160h], 2
0x1800acb6a  jz      loc_1800AD25F
0x1800acb70  cmp     dl, 0FEh
0x1800acb73  mov     eax, edx
0x1800acb75  cmovz   eax, r9d
0x1800acb79  mov     [rbp+140h+var_1C0.lfCharSet], al
0x1800acb7c  movzx   eax, byte ptr [rdi+164h]
0x1800acb83  mov     [rbp+140h+var_1C0.lfOutPrecision], r8b
0x1800acb87  test    al, al
0x1800acb89  jnz     loc_1800AD268
0x1800acb8f  test    byte ptr [r15+34h], 20h
0x1800acb94  mov     ecx, 0C0h
0x1800acb99  movzx   eax, r10b
0x1800acb9d  cmovnz  eax, ecx
0x1800acba0  mov     cl, [r15+5]
0x1800acba4  mov     [rbp+140h+var_1C0.lfClipPrecision], al
0x1800acba7  mov     [rdi+163h], cl
0x1800acbad  mov     al, [r15+2Bh]
0x1800acbb1  mov     [rdi+165h], al
0x1800acbb7  mov     [rbp+140h+var_1C0.lfQuality], al
0x1800acbba  mov     al, [r15+3Dh]
0x1800acbbe  mov     [rdi+162h], al
0x1800acbc4  mov     al, cl
0x1800acbc6  and     al, 0F0h
0x1800acbc8  mov     [rbp+140h+var_1C0.lfPitchAndFamily], cl
0x1800acbcb  cmp     al, 70h ; 'p'
0x1800acbcd  jnb     loc_1800AD280
0x1800acbd3  mov     cl, bl; unsigned __int8
0x1800acbd5  call    ?CodePageFromCharRep@CW32System@@SAGE@Z; CW32System::CodePageFromCharRep(uchar)
0x1800acbda  movzx   ecx, r14w; __int16
0x1800acbde  mov     [rdi+0CEh], ax
0x1800acbe5  call    ?GetFontName@CFICache@@SAPEBGF@Z; CFICache::GetFontName(short)
0x1800acbea  xor     ebx, ebx
0x1800acbec  cmp     [rdi+169h], bl
0x1800acbf2  jl      loc_1800AD28E
0x1800acbf8  mov     r8b, bl; bool
0x1800acbfb  mov     rdx, rax; unsigned __int16 *
0x1800acbfe  lea     rcx, [rbp+140h+var_1C0]; struct tagLOGFONTW *
0x1800acc02  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG_N@Z; CopyLFFontName(tagLOGFONTW &,ushort const *,bool)
0x1800acc07  test    byte ptr [rdi+169h], 20h
0x1800acc0e  mov     rax, [rsp+240h+var_1E8]
0x1800acc13  mov     qword ptr [rsp+240h+var_1D8], rax
0x1800acc18  mov     eax, 7
0x1800acc1d  mov     byte ptr [rsp+240h+var_1D8+8], sil
0x1800acc22  mov     [rsp+240h+var_1C8], rbx
0x1800acc27  jnz     loc_1800AD2D3
0x1800acc2d  cmp     [rdi+164h], bl
0x1800acc33  jnz     loc_1800AD2AE
0x1800acc39  mov     al, [rbp+140h+var_1C0.lfOutPrecision]
0x1800acc3c  movzx   ebx, cs:?_bCharSetSys@CW32System@@0EA; uchar CW32System::_bCharSetSys
0x1800acc43  test    sil, sil
0x1800acc46  movzx   eax, al
0x1800acc49  mov     ecx, 7
0x1800acc4e  cmovnz  eax, ecx
0x1800acc51  mov     [rbp+140h+var_1C0.lfOutPrecision], al
0x1800acc54  lea     eax, [rbx-0B1h]
0x1800acc5a  cmp     eax, 1
0x1800acc5d  mov     al, [rbp+140h+var_1C0.lfCharSet]
0x1800acc60  mov     [rsp+240h+var_1E0], eax
0x1800acc64  jbe     loc_1800AD2F7
0x1800acc6a  or      eax, 0FFFFFFFFh
0x1800acc6d  xor     ebx, ebx
0x1800acc6f  test    sil, sil
0x1800acc72  jz      loc_1800ACE80
0x1800acc78  mov     al, [r15+3Fh]
0x1800acc7c  and     al, 0Fh
0x1800acc7e  movzx   ecx, al
0x1800acc81  mov     [rdi+162h], cl
0x1800acc87  test    byte ptr [r15], 2
0x1800acc8b  mov     [rbp+140h+var_1C0.lfWidth], ecx
0x1800acc8e  jnz     loc_1800ACF97
0x1800acc94  movzx   eax, word ptr [r15+34h]
0x1800acc99  shr     ax, 9
0x1800acc9d  and     al, 1
0x1800acc9f  and     byte ptr [rdi+169h], 0F3h
0x1800acca6  mov     rcx, [rsp+240h+var_1E8]
0x1800accab  mov     [rbp+140h+var_1C0.lfItalic], al
0x1800accae  shl     al, 2
0x1800accb1  or      [rdi+169h], al
0x1800accb7  test    rcx, rcx
0x1800accba  jz      loc_1800AD346
0x1800accc0  mov     edx, [r15+1Ch]
0x1800accc4  test    edx, edx
0x1800accc6  jz      loc_1800AD346
0x1800acccc  mov     rax, [rcx]
0x1800acccf  mov     rax, [rax+28h]
0x1800accd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800accd8  mov     rbx, rax
0x1800accdb  test    rax, rax
0x1800accde  jz      loc_1800AD344
0x1800acce4  mov     rcx, rax
0x1800acce7  call    ??$GetDWriteFont@UIDWriteFontFace@@@@YAPEAUIDWriteFont@@PEAUIDWriteFontFace@@@Z; GetDWriteFont<IDWriteFontFace>(IDWriteFontFace *)
0x1800accec  mov     r8, rax; struct IDWriteFont *
0x1800accef  mov     rdx, rbx; struct IDWriteFontFace *
0x1800accf2  mov     rcx, r13; this
0x1800accf5  mov     rsi, rax
0x1800accf8  call    ?SetDWriteFontFace@CFont@@AEAAXPEAUIDWriteFontFace@@PEAUIDWriteFont@@@Z; CFont::SetDWriteFontFace(IDWriteFontFace *,IDWriteFont *)
0x1800accfd  test    rsi, rsi
0x1800acd00  jz      short loc_1800ACD11
0x1800acd02  mov     rdx, [rsi]
0x1800acd05  mov     rcx, rsi
0x1800acd08  mov     rax, [rdx+10h]
0x1800acd0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acd11  lea     rcx, [rdi+28h]; this
0x1800acd15  call    ?Free@CWidthCache@@QEAAXXZ; CWidthCache::Free(void)
0x1800acd1a  mov     eax, [r15+1Ch]
0x1800acd1e  mov     dl, [rsp+240h+var_1F0]
0x1800acd22  mov     [rdi+0C8h], eax
0x1800acd28  mov     cl, dl; unsigned __int8
0x1800acd2a  mov     eax, [r15]
0x1800acd2d  and     byte ptr [rdi+169h], 0BFh
0x1800acd34  shr     eax, 11h
0x1800acd37  and     al, 2
0x1800acd39  mov     [rdi+160h], al
0x1800acd3f  call    ?CharSetFromCharRep@CW32System@@SAEE@Z; CW32System::CharSetFromCharRep(uchar)
0x1800acd44  mov     [rdi+0D2h], dl
0x1800acd4a  xor     edx, edx
0x1800acd4c  mov     [rdi+0D0h], al
0x1800acd52  movzx   eax, word ptr [r15+8]
0x1800acd57  mov     [rdi+0Ch], ax
0x1800acd5b  movzx   eax, word ptr [r15+10h]
0x1800acd60  mov     [rdi+0CCh], ax
0x1800acd67  test    ax, ax
0x1800acd6a  jz      loc_1800AD324
0x1800acd70  mov     al, [r15+5]
0x1800acd74  mov     [rdi+163h], al
0x1800acd7a  mov     al, [r15+2Bh]
0x1800acd7e  mov     [rdi+165h], al
0x1800acd84  cmp     [rbp+140h+arg_20], dl
0x1800acd8a  jz      short loc_1800ACDBE
0x1800acd8c  xor     eax, eax
0x1800acd8e  lea     rdx, [rsp+240h+var_1D8]
0x1800acd93  mov     dword ptr [rsp+240h+var_1C8], eax
0x1800acd97  xorps   xmm0, xmm0
0x1800acd9a  mov     rax, [rbx]
0x1800acd9d  mov     rcx, rbx
0x1800acda0  movups  [rsp+240h+var_1D8], xmm0
0x1800acda5  mov     rax, [rax+40h]
0x1800acda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acdae  movsx   eax, word ptr [rsp+240h+var_1D8]
0x1800acdb3  mov     ecx, eax
0x1800acdb5  mov     [rdi+0Ch], ax
0x1800acdb9  neg     ecx
0x1800acdbb  mov     [rbp+140h+var_1C0.lfHeight], ecx
0x1800acdbe  mov     rax, [rbx]
0x1800acdc1  mov     rcx, rbx
0x1800acdc4  mov     rax, [rax+10h]
0x1800acdc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acdcd  movaps  xmm0, xmmword ptr [rbp+140h+var_1C0.lfHeight]
0x1800acdd1  xor     r9d, r9d; unsigned __int16 *
0x1800acdd4  movaps  xmm1, xmmword ptr [rbp+140h+var_1C0.lfWeight]
0x1800acdd8  xor     r8d, r8d; int
0x1800acddb  mov     r15, [rsp+240h+var_1E8]
0x1800acde0  mov     rdx, r12; struct CHDC *
0x1800acde3  movups  xmmword ptr [r13+0], xmm0
0x1800acde8  mov     rcx, rdi; this
0x1800acdeb  mov     word ptr [rsp+240h+var_218], r14w; __int16
0x1800acdf1  movaps  xmm0, xmmword ptr [rbp+140h+var_1C0.lfFaceName+4]
0x1800acdf5  movups  xmmword ptr [r13+10h], xmm1
0x1800acdfa  mov     [rsp+240h+var_220], r15; struct IProvideFontInfo *
0x1800acdff  movaps  xmm1, xmmword ptr [rbp+140h+var_1C0.lfFaceName+14h]
0x1800ace03  movups  xmmword ptr [r13+20h], xmm0
0x1800ace08  movaps  xmm0, xmmword ptr [rbp+140h+var_1C0.lfFaceName+24h]
0x1800ace0c  movups  xmmword ptr [r13+30h], xmm1
0x1800ace11  movups  xmm1, xmmword ptr [rbp+140h+var_1C0.lfFaceName+30h]
0x1800ace15  movups  xmmword ptr [r13+40h], xmm0
0x1800ace1a  movups  xmmword ptr [r13+4Ch], xmm1
0x1800ace1f  call    ?GetMetrics@CCcs@@AEAA_NAEBVCHDC@@JPEAGPEAUIProvideFontInfo@@F@Z; CCcs::GetMetrics(CHDC const &,long,ushort *,IProvideFontInfo *,short)
0x1800ace24  lea     rsi, [rdi+148h]
0x1800ace2b  mov     bl, [rsp+240h+var_1EF]
0x1800ace2f  xor     r11d, r11d
0x1800ace32  cmp     [rsi], r11
0x1800ace35  jz      loc_1800AD4E7
0x1800ace3b  test    r14w, r14w
0x1800ace3f  js      loc_1800AD52C
0x1800ace45  test    byte ptr [rdi+169h], 40h
0x1800ace4c  jnz     loc_1800AD52C
0x1800ace52  mov     [rdi+0D4h], r14w
0x1800ace5a  mov     al, 1
0x1800ace5c  mov     rcx, [rbp+140h+var_50]
0x1800ace63  xor     rcx, rsp; StackCookie
0x1800ace66  call    __security_check_cookie
0x1800ace6b  add     rsp, 208h
0x1800ace72  pop     r15
0x1800ace74  pop     r14
0x1800ace76  pop     r13
0x1800ace78  pop     r12
0x1800ace7a  pop     rdi
0x1800ace7b  pop     rsi
0x1800ace7c  pop     rbx
0x1800ace7d  pop     rbp
0x1800ace7e  retn
0x1800ace80  test    byte ptr [r15], 3
0x1800ace84  jnz     loc_1800AD34E
0x1800ace8a  lea     rsi, [rdi+148h]
0x1800ace91  mov     [rbp+140h+var_D0], bx
0x1800ace95  cmp     [rsi], rbx
0x1800ace98  jnz     loc_1800AD357
0x1800ace9e  mov     rcx, [r12]
0x1800acea2  lea     rdx, [rdi+168h]
0x1800acea9  mov     bl, [rsp+240h+var_1F0]
0x1800acead  mov     r8, r13
0x1800aceb0  mov     [rsp+240h+var_220], rdx; int
0x1800aceb5  mov     r9b, bl
0x1800aceb8  lea     rdx, [rbp+140h+var_1C0]
0x1800acebc  mov     rax, [rcx]
0x1800acebf  mov     rax, [rax+80h]
0x1800acec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acecb  xor     r11d, r11d
0x1800acece  cmp     [rsi], r11
0x1800aced1  jnz     short loc_1800ACF24
0x1800aced3  cmp     [rsp+240h+var_1EF], r11b
0x1800aced8  jz      short loc_1800ACF4A
0x1800aceda  cmp     [rbp+140h+arg_20], r11b
0x1800acee1  jnz     loc_1800AD364
0x1800acee7  mov     bl, [rsp+240h+var_1EF]
0x1800aceeb  test    bl, bl
0x1800aceed  jz      loc_1800AD3FA
0x1800acef3  mov     r14d, [rsp+240h+var_1EC]
0x1800acef8  mov     r15, [rsp+240h+var_1E8]
0x1800acefd  cmp     [rdi+15Dh], r11b
0x1800acf04  jz      loc_1800ACE32
0x1800acf0a  mov     al, [rbp+140h+var_1C0.lfCharSet]
0x1800acf0d  cmp     [rdi+0D1h], al
0x1800acf13  jz      loc_1800ACE32
0x1800acf19  mov     [rdi+0D1h], al
0x1800acf1f  jmp     loc_1800ACE32
  ... truncated ...
```
