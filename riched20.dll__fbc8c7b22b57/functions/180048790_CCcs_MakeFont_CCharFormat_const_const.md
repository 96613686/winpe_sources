# CCcs::MakeFont(CCharFormat const * const)

- ea: `0x180048790`
- end: `0x180048ded`
- name: `?MakeFont@CCcs@@AEAAHQEBVCCharFormat@@@Z`
- size: `1629`
- prototype: `__int64 __fastcall(CCcs *__hidden this, const struct CCharFormat *const)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180060e44`

## callees

- `0x18001c1d4`
- `0x18001e2e0`
- `0x18002cc48`
- `0x180037b48`
- `0x180040ae0`
- `0x180048790`
- `0x180048df4`
- `0x180048e30`
- `0x18005ff78`
- `0x180060928`
- `0x180060b64`
- `0x180060bb0`
- `0x1800906a4`
- `0x180093aa4`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `GDI32!TranslateCharsetInfo` at `0x180048d99`
- `GDI32!TranslateCharsetInfo` at `0x180048d99`
- `GDI32!GetTextCharsetInfo` at `0x180048d77`
- `GDI32!GetTextCharsetInfo` at `0x180048d77`
- `GDI32!DeleteObject` at `0x180048ba1`
- `GDI32!DeleteObject` at `0x180048d25`
- `GDI32!DeleteObject` at `0x180048ba1`
- `GDI32!DeleteObject` at `0x180048d25`
- `GDI32!SelectObject` at `0x180048d5d`
- `GDI32!SelectObject` at `0x180048db2`
- `GDI32!SelectObject` at `0x180048d5d`
- `GDI32!SelectObject` at `0x180048db2`

## pseudocode

```c
__int64 __fastcall CCcs::MakeFont(CCcs *this, const struct CCharFormat *const a2)
{
  BOOL v4; // r15d
  int v5; // edx
  int v6; // ecx
  unsigned __int16 v7; // ax
  unsigned int v8; // ecx
  __int64 v9; // rcx
  bool v10; // zf
  BYTE lfOutPrecision; // al
  BYTE v12; // dl
  const unsigned __int16 *FontName; // rax
  __int64 v14; // rcx
  unsigned __int8 v15; // di
  BYTE lfCharSet; // si
  __int64 v17; // rcx
  _BYTE *InfoFlags; // rax
  int v19; // r11d
  _QWORD *v20; // rdi
  void *v21; // r14
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  unsigned __int16 *v25; // rax
  char v26; // al
  int v27; // ecx
  const unsigned __int16 *v28; // rdi
  unsigned __int16 *v29; // rdx
  char v30; // r11
  const unsigned __int16 *v31; // rax
  HGDIOBJ v32; // rdx
  HDC v33; // rcx
  HGDIOBJ v34; // rdi
  unsigned int TextCharsetInfo; // eax
  DWORD v36; // edx
  HDC v37; // rcx
  __int16 v39[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v40; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 v41[11]; // [rsp+35h] [rbp-CBh] BYREF
  struct tagLOGFONTW v42; // [rsp+40h] [rbp-C0h] BYREF
  struct tagCHARSETINFO Sig; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v44[32]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&v42, 0, sizeof(v42));
  v4 = 1;
  v5 = *(_DWORD *)a2 & 0x40000;
  *((_BYTE *)this + 120) = v5 != 0 ? 2 : 0;
  v6 = *((__int16 *)a2 + 4);
  *((_WORD *)this + 44) = *((_WORD *)a2 + 4);
  *((_BYTE *)this + 118) = *((_BYTE *)a2 + 4);
  v42.lfHeight = -v6;
  v7 = *((_WORD *)a2 + 8);
  if ( !v7 )
    v7 = (*(_DWORD *)a2 & 1) != 0 ? 700 : 400;
  *((_WORD *)this + 57) = v7;
  v8 = *(_DWORD *)a2;
  *((_BYTE *)this + 123) &= ~4u;
  v9 = v8 >> 1;
  v42.lfWeight = v7;
  v42.lfItalic = v9 & 1;
  *((_BYTE *)this + 123) |= 4 * (v9 & 1);
  if ( v5 )
  {
    LOBYTE(v9) = 0;
  }
  else
  {
    v9 = *((unsigned __int8 *)a2 + 4);
    if ( (unsigned int)(v9 - 120) <= 7 )
      v9 = 1;
  }
  v10 = (*(_DWORD *)a2 & 0x100000) == 0;
  v42.lfCharSet = v9;
  v42.lfOutPrecision = 0;
  if ( !v10 )
  {
    v42.lfOutPrecision = 7;
    if ( CW32System::_dwPlatformId != 1 )
    {
      v10 = (*(_BYTE *)CFontCache::GetInfoFlags(v9, v39, (unsigned int)*((__int16 *)a2 + 3)) & 4) == 0;
      lfOutPrecision = v42.lfOutPrecision;
      if ( !v10 )
        lfOutPrecision = 9;
      LOBYTE(v9) = v42.lfCharSet;
      v42.lfOutPrecision = lfOutPrecision;
    }
  }
  v12 = *((_BYTE *)a2 + 5);
  v42.lfClipPrecision = 64;
  *((_BYTE *)this + 122) = v12;
  v42.lfPitchAndFamily = v12;
  if ( (v12 & 0xF0) == 0x70 )
    v42.lfPitchAndFamily = v12 & 0xF;
  *((_WORD *)this + 58) = CW32System::GetCodePage(v9);
  FontName = GetFontName(*((__int16 *)a2 + 3));
  CopyLFFontName(&v42, FontName);
  v15 = CW32System::_bSysCharSet;
  if ( (unsigned int)CW32System::_bSysCharSet - 177 > 1 )
    goto LABEL_20;
  lfCharSet = v42.lfCharSet;
  if ( v42.lfCharSet )
    goto LABEL_21;
  if ( (*(_BYTE *)CFontCache::GetInfoFlags(v14, v39, (unsigned int)*((__int16 *)a2 + 3)) & 8) != 0 )
  {
    InfoFlags = (_BYTE *)CFontCache::GetInfoFlags(v17, v39, (unsigned int)*((__int16 *)a2 + 3));
    lfCharSet = v42.lfCharSet;
    if ( (*InfoFlags & 2) == 0 )
      lfCharSet = v15;
    v42.lfCharSet = lfCharSet;
  }
  else
  {
LABEL_20:
    lfCharSet = v42.lfCharSet;
  }
LABEL_21:
  if ( !CCcs::GetFontWithMetrics(this, &v42, v44) )
    return 0;
  if ( !(unsigned int)CW32System::wcsicmp(v44, v42.lfFaceName) )
    goto LABEL_86;
  LOBYTE(v19) = v42.lfCharSet;
  if ( v42.lfCharSet == 2 )
  {
    v20 = (_QWORD *)((char *)this + 72);
    v42.lfCharSet = 0;
    v21 = (void *)*((_QWORD *)this + 9);
    if ( !CCcs::GetFontWithMetrics(this, &v42, v44) )
      return 0;
    v22 = CW32System::wcsicmp(v44, v42.lfFaceName);
    LOBYTE(v19) = v42.lfCharSet;
    v4 = 0;
    if ( v22 )
      LOBYTE(v19) = lfCharSet;
    LOBYTE(v4) = v22 == 0;
    v42.lfCharSet = v19;
    goto LABEL_64;
  }
  if ( v42.lfCharSet == 1 )
  {
    if ( *((_BYTE *)this + 119) == 1 )
    {
      v42.lfCharSet = 2;
      CopyLFFontName(&v42, v44);
      v20 = (_QWORD *)((char *)this + 72);
      v21 = (void *)*((_QWORD *)this + 9);
      if ( !CCcs::GetFontWithMetrics(this, &v42, v44) )
        return 0;
      v23 = CW32System::wcsicmp(v44, v42.lfFaceName);
      v42.lfCharSet = lfCharSet;
      LOBYTE(v19) = lfCharSet;
      v4 = v23 == 0;
      goto LABEL_64;
    }
  }
  else if ( (unsigned __int8)(v42.lfCharSet + 79) <= 1u )
  {
    CCcs::DestroyFont(this);
    v29 = v44;
    goto LABEL_84;
  }
  if ( *((_BYTE *)this + 121) != 2
    && (unsigned int)CW32System::IsFECharSet(v42.lfCharSet)
    && !CW32System::OnWinNTFE()
    && !CW32System::OnWin9xFE() )
  {
    if ( *((_BYTE *)this + 119) == (_BYTE)v19 || CW32System::_dwPlatformId != 1 )
    {
      v25 = v44;
    }
    else
    {
      switch ( v19 )
      {
        case 128:
          v24 = g_iFontJapanese;
          break;
        case 129:
          v24 = g_iFontHangul;
          break;
        case 134:
          v24 = g_iFontGB2312;
          break;
        case 136:
          v24 = g_iFontBig5;
          break;
        default:
          goto LABEL_51;
      }
      v25 = (unsigned __int16 *)GetFontName(v24);
      if ( !v25 )
      {
LABEL_51:
        v20 = (_QWORD *)((char *)this + 72);
        v21 = (void *)*((_QWORD *)this + 9);
        if ( !CCcs::GetFontWithMetrics(this, &v42, v44) )
          return 0;
        if ( (unsigned int)CW32System::wcsicmp(v44, v42.lfFaceName) )
        {
          v4 = 0;
        }
        else if ( CW32System::_dwPlatformId == 1 )
        {
          LOBYTE(v19) = v42.lfCharSet;
          switch ( v42.lfCharSet )
          {
            case 0x80u:
              g_iFontJapanese = GetFontNameIndex(v42.lfFaceName);
              break;
            case 0x81u:
              g_iFontHangul = GetFontNameIndex(v42.lfFaceName);
              break;
            case 0x86u:
              g_iFontGB2312 = GetFontNameIndex(v42.lfFaceName);
              break;
            case 0x88u:
              g_iFontBig5 = GetFontNameIndex(v42.lfFaceName);
              break;
            default:
LABEL_64:
              if ( !v21 )
                goto LABEL_69;
              if ( v4 )
              {
                DeleteObject(v21);
LABEL_68:
                LOBYTE(v19) = v42.lfCharSet;
                goto LABEL_69;
              }
              CCcs::DestroyFont(this);
              *v20 = v21;
              if ( (unsigned int)CCcs::GetMetrics(this, 0) )
                goto LABEL_68;
              return 0;
          }
        }
        LOBYTE(v19) = v42.lfCharSet;
        goto LABEL_64;
      }
    }
    CopyLFFontName(&v42, v25);
    goto LABEL_51;
  }
  while ( 1 )
  {
LABEL_69:
    v26 = *((_BYTE *)this + 119);
    if ( v26 != 2 || (v27 = 1, (_BYTE)v19 == 2) )
      v27 = 0;
    if ( v26 != (_BYTE)v19 && (_BYTE)v19 != 1 )
      break;
    if ( !v27 )
      goto LABEL_88;
LABEL_80:
    if ( (unsigned int)CW32System::wcsicmp(v42.lfFaceName, L"Arial") )
    {
      CCcs::DestroyFont(this);
      v29 = L"Arial";
LABEL_84:
      CopyLFFontName(&v42, v29);
    }
    else
    {
      if ( !v30 )
        goto LABEL_88;
      CCcs::DestroyFont(this);
      v31 = GetFontName(*((__int16 *)a2 + 3));
      CopyLFFontName(&v42, v31);
      v42.lfCharSet = 0;
    }
    if ( !CCcs::GetFontWithMetrics(this, &v42, v44) )
      return 0;
LABEL_86:
    LOBYTE(v19) = v42.lfCharSet;
  }
  if ( (_BYTE)v19 != 0xDE )
    goto LABEL_80;
  if ( v26 )
    goto LABEL_80;
  v39[0] = 0;
  v41[0] = 0;
  v40 = 0;
  CW32System::GetPreferredFontInfo(874, 1, 0, v39, v41, &v40);
  v28 = GetFontName(v39[0]);
  if ( !v28 )
    goto LABEL_80;
  CCcs::DestroyFont(this);
  CopyLFFontName(&v42, v28);
  if ( !CCcs::GetFontWithMetrics(this, &v42, v44) )
    return 0;
LABEL_88:
  v32 = (HGDIOBJ)*((_QWORD *)this + 9);
  if ( !v32 )
  {
    v32 = CW32System::_hSystemFont;
    *((_QWORD *)this + 9) = CW32System::_hSystemFont;
  }
  *((_DWORD *)this + 14) = 0;
  if ( v32 )
  {
    v33 = (HDC)*((_QWORD *)this + 8);
    memset(&Sig, 0, sizeof(Sig));
    v34 = SelectObject(v33, v32);
    TextCharsetInfo = GetTextCharsetInfo(*((HDC *)this + 8), &Sig.fs, 0);
    v36 = Sig.fs.fsCsb[0];
    if ( !(Sig.fs.fsCsb[1] | Sig.fs.fsCsb[0] | Sig.fs.fsUsb[0]) )
    {
      TranslateCharsetInfo((DWORD *)TextCharsetInfo, &Sig, 1u);
      v36 = Sig.fs.fsCsb[0];
    }
    v37 = (HDC)*((_QWORD *)this + 8);
    *((_DWORD *)this + 14) = v36;
    SelectObject(v37, v34);
  }
  return 1;
}

```

## disassembly

```asm
0x180048790  mov     [rsp-8+arg_10], rbx
0x180048795  push    rbp
0x180048796  push    rsi
0x180048797  push    rdi
0x180048798  push    r12
0x18004879a  push    r13
0x18004879c  push    r14
0x18004879e  push    r15
0x1800487a0  lea     rbp, [rsp-10h]
0x1800487a5  sub     rsp, 110h
0x1800487ac  mov     rax, cs:__security_cookie
0x1800487b3  xor     rax, rsp
0x1800487b6  mov     [rbp+40h+var_40], rax
0x1800487ba  mov     r12, rdx
0x1800487bd  mov     rbx, rcx
0x1800487c0  xor     edx, edx; Val
0x1800487c2  lea     rcx, [rsp+140h+var_100]; void *
0x1800487c7  lea     r8d, [rdx+5Ch]; Size
0x1800487cb  call    memset_0
0x1800487d0  mov     edx, [r12]
0x1800487d4  mov     r15d, 1
0x1800487da  and     edx, 40000h
0x1800487e0  mov     eax, edx
0x1800487e2  neg     eax
0x1800487e4  sbb     cl, cl
0x1800487e6  xor     r13d, r13d
0x1800487e9  and     cl, 2
0x1800487ec  mov     [rbx+78h], cl
0x1800487ef  movsx   ecx, word ptr [r12+8]
0x1800487f5  mov     [rbx+58h], cx
0x1800487f9  mov     al, [r12+4]
0x1800487fe  mov     [rbx+76h], al
0x180048801  mov     eax, ecx
0x180048803  neg     eax
0x180048805  mov     [rsp+140h+var_100.lfHeight], eax
0x180048809  movzx   eax, word ptr [r12+10h]
0x18004880f  test    ax, ax
0x180048812  jnz     short loc_180048828
0x180048814  mov     eax, [r12]
0x180048818  and     al, r15b
0x18004881b  neg     al
0x18004881d  sbb     ax, ax
0x180048820  and     ax, 12Ch
0x180048824  add     ax, 190h
0x180048828  mov     [rbx+72h], ax
0x18004882c  mov     ecx, [r12]
0x180048830  and     byte ptr [rbx+7Bh], 0FBh
0x180048834  movzx   eax, ax
0x180048837  shr     ecx, 1
0x180048839  and     cl, r15b
0x18004883c  mov     [rsp+140h+var_100.lfWeight], eax
0x180048840  mov     al, cl
0x180048842  mov     [rsp+140h+var_100.lfItalic], cl
0x180048846  shl     al, 2
0x180048849  or      [rbx+7Bh], al
0x18004884c  test    edx, edx
0x18004884e  jz      short loc_180048855
0x180048850  mov     cl, r13b
0x180048853  jmp     short loc_180048865
0x180048855  movzx   ecx, byte ptr [r12+4]
0x18004885b  lea     eax, [rcx-78h]
0x18004885e  cmp     eax, 7
0x180048861  cmovbe  ecx, r15d
0x180048865  test    dword ptr [r12], 100000h
0x18004886d  mov     [rsp+140h+var_100.lfCharSet], cl
0x180048871  mov     [rsp+140h+var_100.lfOutPrecision], r13b
0x180048876  jz      short loc_1800488AE
0x180048878  cmp     cs:?_dwPlatformId@CW32System@@0KA, r15d; ulong CW32System::_dwPlatformId
0x18004887f  mov     [rsp+140h+var_100.lfOutPrecision], 7
0x180048884  jz      short loc_1800488AE
0x180048886  movsx   r8d, word ptr [r12+6]
0x18004888c  lea     rdx, [rsp+140h+var_110]
0x180048891  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x180048896  mov     ecx, 9
0x18004889b  test    byte ptr [rax], 4
0x18004889e  movzx   eax, [rsp+140h+var_100.lfOutPrecision]
0x1800488a3  cmovnz  eax, ecx
0x1800488a6  mov     cl, [rsp+140h+var_100.lfCharSet]; unsigned __int8
0x1800488aa  mov     [rsp+140h+var_100.lfOutPrecision], al
0x1800488ae  mov     dl, [r12+5]
0x1800488b3  mov     al, dl
0x1800488b5  mov     [rsp+140h+var_100.lfClipPrecision], 40h ; '@'
0x1800488ba  and     al, 0F0h
0x1800488bc  mov     [rbx+7Ah], dl
0x1800488bf  mov     [rsp+140h+var_100.lfPitchAndFamily], dl
0x1800488c3  cmp     al, 70h ; 'p'
0x1800488c5  jnz     short loc_1800488CE
0x1800488c7  and     dl, 0Fh
0x1800488ca  mov     [rsp+140h+var_100.lfPitchAndFamily], dl
0x1800488ce  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x1800488d3  mov     [rbx+74h], ax
0x1800488d7  movsx   ecx, word ptr [r12+6]; int
0x1800488dd  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x1800488e2  mov     rdx, rax; unsigned __int16 *
0x1800488e5  lea     rcx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x1800488ea  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x1800488ef  movzx   edi, cs:?_bSysCharSet@CW32System@@0EA; uchar CW32System::_bSysCharSet
0x1800488f6  lea     eax, [rdi-0B1h]
0x1800488fc  cmp     eax, r15d
0x1800488ff  ja      short loc_180048942
0x180048901  mov     sil, [rsp+140h+var_100.lfCharSet]
0x180048906  test    sil, sil
0x180048909  jnz     short loc_180048947
0x18004890b  movsx   r8d, word ptr [r12+6]
0x180048911  lea     rdx, [rsp+140h+var_110]
0x180048916  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x18004891b  test    byte ptr [rax], 8
0x18004891e  jz      short loc_180048942
0x180048920  movsx   r8d, word ptr [r12+6]
0x180048926  lea     rdx, [rsp+140h+var_110]
0x18004892b  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x180048930  movzx   esi, [rsp+140h+var_100.lfCharSet]
0x180048935  test    byte ptr [rax], 2
0x180048938  cmovz   esi, edi
0x18004893b  mov     [rsp+140h+var_100.lfCharSet], sil
0x180048940  jmp     short loc_180048947
0x180048942  mov     sil, [rsp+140h+var_100.lfCharSet]
0x180048947  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x18004894b  mov     rcx, rbx; this
0x18004894e  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x180048953  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x180048958  test    rax, rax
0x18004895b  jz      loc_180048DC3
0x180048961  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x180048966  mov     r14, r13
0x180048969  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x18004896d  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180048972  test    eax, eax
0x180048974  jz      loc_180048CE4
0x18004897a  movzx   r11d, [rsp+140h+var_100.lfCharSet]
0x180048980  cmp     r11b, 2
0x180048984  jnz     short loc_1800489DB
0x180048986  lea     rdi, [rbx+48h]
0x18004898a  mov     [rsp+140h+var_100.lfCharSet], r13b
0x18004898f  mov     r14, [rdi]
0x180048992  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x180048996  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x18004899b  mov     rcx, rbx; this
0x18004899e  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x1800489a3  test    rax, rax
0x1800489a6  jz      loc_180048DC3
0x1800489ac  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x1800489b1  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x1800489b5  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x1800489ba  movzx   r11d, [rsp+140h+var_100.lfCharSet]
0x1800489c0  test    eax, eax
0x1800489c2  movzx   ecx, sil
0x1800489c6  mov     r15d, r13d
0x1800489c9  cmovnz  r11d, ecx
0x1800489cd  setz    r15b
0x1800489d1  mov     [rsp+140h+var_100.lfCharSet], r11b
0x1800489d6  jmp     loc_180048B94
0x1800489db  cmp     r11b, r15b
0x1800489de  jnz     short loc_180048A3E
0x1800489e0  cmp     [rbx+77h], r15b
0x1800489e4  jnz     short loc_180048A4B
0x1800489e6  lea     rdx, [rbp+40h+var_80]; unsigned __int16 *
0x1800489ea  mov     [rsp+140h+var_100.lfCharSet], 2
0x1800489ef  lea     rcx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x1800489f4  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x1800489f9  lea     rdi, [rbx+48h]
0x1800489fd  mov     rcx, rbx; this
0x180048a00  mov     r14, [rdi]
0x180048a03  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x180048a07  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x180048a0c  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x180048a11  test    rax, rax
0x180048a14  jz      loc_180048DC3
0x180048a1a  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x180048a1f  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x180048a23  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180048a28  test    eax, eax
0x180048a2a  mov     [rsp+140h+var_100.lfCharSet], sil
0x180048a2f  mov     r15d, r13d
0x180048a32  mov     r11b, sil
0x180048a35  setz    r15b
0x180048a39  jmp     loc_180048B94
0x180048a3e  lea     eax, [r11+4Fh]
0x180048a42  cmp     al, r15b
0x180048a45  jbe     loc_180048C56
0x180048a4b  cmp     byte ptr [rbx+79h], 2
0x180048a4f  jz      loc_180048BDA
0x180048a55  mov     cl, r11b; unsigned __int8
0x180048a58  call    ?IsFECharSet@CW32System@@SAHE@Z; CW32System::IsFECharSet(uchar)
0x180048a5d  test    eax, eax
0x180048a5f  jz      loc_180048BDA
0x180048a65  call    ?OnWinNTFE@CW32System@@SA_NXZ; CW32System::OnWinNTFE(void)
0x180048a6a  test    al, al
0x180048a6c  jnz     loc_180048BDA
0x180048a72  call    ?OnWin9xFE@CW32System@@SA_NXZ; CW32System::OnWin9xFE(void)
0x180048a77  test    al, al
0x180048a79  jnz     loc_180048BDA
0x180048a7f  mov     esi, 80h
0x180048a84  cmp     [rbx+77h], r11b
0x180048a88  jz      short loc_180048AD7
0x180048a8a  cmp     cs:?_dwPlatformId@CW32System@@0KA, r15d; ulong CW32System::_dwPlatformId
0x180048a91  jnz     short loc_180048AD7
0x180048a93  mov     ecx, r11d
0x180048a96  sub     ecx, esi
0x180048a98  jz      short loc_180048AC4
0x180048a9a  sub     ecx, r15d
0x180048a9d  jz      short loc_180048ABB
0x180048a9f  sub     ecx, 5
0x180048aa2  jz      short loc_180048AB2
0x180048aa4  cmp     ecx, 2
0x180048aa7  jnz     short loc_180048AE8
0x180048aa9  movsx   ecx, cs:?g_iFontBig5@@3FA; short g_iFontBig5
0x180048ab0  jmp     short loc_180048ACB
0x180048ab2  movsx   ecx, cs:?g_iFontGB2312@@3FA; short g_iFontGB2312
0x180048ab9  jmp     short loc_180048ACB
0x180048abb  movsx   ecx, cs:?g_iFontHangul@@3FA; short g_iFontHangul
0x180048ac2  jmp     short loc_180048ACB
0x180048ac4  movsx   ecx, cs:?g_iFontJapanese@@3FA; int
0x180048acb  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x180048ad0  test    rax, rax
0x180048ad3  jz      short loc_180048AE8
0x180048ad5  jmp     short loc_180048ADB
0x180048ad7  lea     rax, [rbp+40h+var_80]
0x180048adb  mov     rdx, rax; unsigned __int16 *
0x180048ade  lea     rcx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x180048ae3  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x180048ae8  lea     rdi, [rbx+48h]
0x180048aec  mov     rcx, rbx; this
0x180048aef  mov     r14, [rdi]
0x180048af2  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x180048af6  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x180048afb  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x180048b00  test    rax, rax
0x180048b03  jz      loc_180048DC3
0x180048b09  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x180048b0e  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x180048b12  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180048b17  test    eax, eax
0x180048b19  jnz     short loc_180048B8C
0x180048b1b  cmp     cs:?_dwPlatformId@CW32System@@0KA, r15d; ulong CW32System::_dwPlatformId
0x180048b22  jnz     short loc_180048B8F
0x180048b24  movzx   r11d, [rsp+140h+var_100.lfCharSet]
0x180048b2a  mov     ecx, r11d
0x180048b2d  sub     ecx, esi
0x180048b2f  jz      short loc_180048B79
0x180048b31  sub     ecx, r15d
0x180048b34  jz      short loc_180048B66
0x180048b36  sub     ecx, 5
0x180048b39  jz      short loc_180048B53
0x180048b3b  cmp     ecx, 2
0x180048b3e  jnz     short loc_180048B94
0x180048b40  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180048b45  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180048b4a  mov     cs:?g_iFontBig5@@3FA, ax; short g_iFontBig5
0x180048b51  jmp     short loc_180048B8F
0x180048b53  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180048b58  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180048b5d  mov     cs:?g_iFontGB2312@@3FA, ax; short g_iFontGB2312
0x180048b64  jmp     short loc_180048B8F
0x180048b66  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180048b6b  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180048b70  mov     cs:?g_iFontHangul@@3FA, ax; short g_iFontHangul
0x180048b77  jmp     short loc_180048B8F
0x180048b79  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180048b7e  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180048b83  mov     cs:?g_iFontJapanese@@3FA, ax; short g_iFontJapanese
0x180048b8a  jmp     short loc_180048B8F
0x180048b8c  mov     r15d, r13d
0x180048b8f  mov     r11b, [rsp+140h+var_100.lfCharSet]
0x180048b94  test    r14, r14
0x180048b97  jz      short loc_180048BD4
0x180048b99  test    r15d, r15d
0x180048b9c  jz      short loc_180048BAF
0x180048b9e  mov     rcx, r14; ho
0x180048ba1  call    cs:__imp_DeleteObject
0x180048ba8  nop     dword ptr [rax+rax+00h]
0x180048bad  jmp     short loc_180048BCC
0x180048baf  mov     rcx, rbx; this
0x180048bb2  call    ?DestroyFont@CCcs@@AEAAXXZ; CCcs::DestroyFont(void)
0x180048bb7  xor     edx, edx; unsigned __int16 *
0x180048bb9  mov     [rdi], r14
0x180048bbc  mov     rcx, rbx; this
0x180048bbf  call    ?GetMetrics@CCcs@@AEAAHPEAG@Z; CCcs::GetMetrics(ushort *)
0x180048bc4  test    eax, eax
0x180048bc6  jz      loc_180048DC3
0x180048bcc  mov     r11b, [rsp+140h+var_100.lfCharSet]
0x180048bd1  mov     r14, r13
0x180048bd4  mov     r15d, 1
0x180048bda  mov     al, [rbx+77h]
0x180048bdd  cmp     al, 2
0x180048bdf  jnz     short loc_180048BE9
0x180048be1  mov     ecx, r15d
0x180048be4  cmp     r11b, al
0x180048be7  jnz     short loc_180048BEC
0x180048be9  mov     ecx, r13d
0x180048bec  cmp     al, r11b
0x180048bef  jz      short loc_180048C64
0x180048bf1  cmp     r11b, r15b
0x180048bf4  jz      short loc_180048C64
0x180048bf6  cmp     r11b, 0DEh
0x180048bfa  jnz     short loc_180048C6C
0x180048bfc  test    al, al
0x180048bfe  jnz     short loc_180048C6C
0x180048c00  lea     rax, [rsp+140h+var_10C]
0x180048c05  mov     [rsp+140h+var_110], r13w
  ... truncated ...
```
