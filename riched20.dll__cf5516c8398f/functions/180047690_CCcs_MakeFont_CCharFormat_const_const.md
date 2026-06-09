# CCcs::MakeFont(CCharFormat const * const)

- ea: `0x180047690`
- end: `0x180047cc8`
- name: `?MakeFont@CCcs@@AEAAHQEBVCCharFormat@@@Z`
- size: `1592`
- prototype: `__int64 __fastcall(CCcs *__hidden this, const struct CCharFormat *const)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x18005f6ec`

## callees

- `0x180027d6c`
- `0x180029d38`
- `0x18002a144`
- `0x180031ff0`
- `0x18003ff74`
- `0x180047690`
- `0x180047cd0`
- `0x180047d08`
- `0x18005e85c`
- `0x18005f1f8`
- `0x18005f428`
- `0x18005f474`
- `0x18008de60`
- `0x180090ff0`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `GDI32!TranslateCharsetInfo` at `0x180047c81`
- `GDI32!TranslateCharsetInfo` at `0x180047c81`
- `GDI32!GetTextCharsetInfo` at `0x180047c65`
- `GDI32!GetTextCharsetInfo` at `0x180047c65`
- `GDI32!DeleteObject` at `0x180047aa1`
- `GDI32!DeleteObject` at `0x180047c1f`
- `GDI32!DeleteObject` at `0x180047aa1`
- `GDI32!DeleteObject` at `0x180047c1f`
- `GDI32!SelectObject` at `0x180047c51`
- `GDI32!SelectObject` at `0x180047c94`
- `GDI32!SelectObject` at `0x180047c51`
- `GDI32!SelectObject` at `0x180047c94`

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
0x180047690  mov     [rsp-8+arg_10], rbx
0x180047695  push    rbp
0x180047696  push    rsi
0x180047697  push    rdi
0x180047698  push    r12
0x18004769a  push    r13
0x18004769c  push    r14
0x18004769e  push    r15
0x1800476a0  lea     rbp, [rsp-10h]
0x1800476a5  sub     rsp, 110h
0x1800476ac  mov     rax, cs:__security_cookie
0x1800476b3  xor     rax, rsp
0x1800476b6  mov     [rbp+40h+var_40], rax
0x1800476ba  mov     r12, rdx
0x1800476bd  mov     rbx, rcx
0x1800476c0  xor     edx, edx; Val
0x1800476c2  lea     rcx, [rsp+140h+var_100]; void *
0x1800476c7  lea     r8d, [rdx+5Ch]; Size
0x1800476cb  call    memset_0
0x1800476d0  mov     edx, [r12]
0x1800476d4  mov     r15d, 1
0x1800476da  and     edx, 40000h
0x1800476e0  mov     eax, edx
0x1800476e2  neg     eax
0x1800476e4  sbb     cl, cl
0x1800476e6  xor     r13d, r13d
0x1800476e9  and     cl, 2
0x1800476ec  mov     [rbx+78h], cl
0x1800476ef  movsx   ecx, word ptr [r12+8]
0x1800476f5  mov     [rbx+58h], cx
0x1800476f9  mov     al, [r12+4]
0x1800476fe  mov     [rbx+76h], al
0x180047701  mov     eax, ecx
0x180047703  neg     eax
0x180047705  mov     [rsp+140h+var_100.lfHeight], eax
0x180047709  movzx   eax, word ptr [r12+10h]
0x18004770f  test    ax, ax
0x180047712  jnz     short loc_180047728
0x180047714  mov     eax, [r12]
0x180047718  and     al, r15b
0x18004771b  neg     al
0x18004771d  sbb     ax, ax
0x180047720  and     ax, 12Ch
0x180047724  add     ax, 190h
0x180047728  mov     [rbx+72h], ax
0x18004772c  mov     ecx, [r12]
0x180047730  and     byte ptr [rbx+7Bh], 0FBh
0x180047734  movzx   eax, ax
0x180047737  shr     ecx, 1
0x180047739  and     cl, r15b
0x18004773c  mov     [rsp+140h+var_100.lfWeight], eax
0x180047740  mov     al, cl
0x180047742  mov     [rsp+140h+var_100.lfItalic], cl
0x180047746  shl     al, 2
0x180047749  or      [rbx+7Bh], al
0x18004774c  test    edx, edx
0x18004774e  jz      short loc_180047755
0x180047750  mov     cl, r13b
0x180047753  jmp     short loc_180047765
0x180047755  movzx   ecx, byte ptr [r12+4]
0x18004775b  lea     eax, [rcx-78h]
0x18004775e  cmp     eax, 7
0x180047761  cmovbe  ecx, r15d
0x180047765  test    dword ptr [r12], 100000h
0x18004776d  mov     [rsp+140h+var_100.lfCharSet], cl
0x180047771  mov     [rsp+140h+var_100.lfOutPrecision], r13b
0x180047776  jz      short loc_1800477AE
0x180047778  cmp     cs:?_dwPlatformId@CW32System@@0KA, r15d; ulong CW32System::_dwPlatformId
0x18004777f  mov     [rsp+140h+var_100.lfOutPrecision], 7
0x180047784  jz      short loc_1800477AE
0x180047786  movsx   r8d, word ptr [r12+6]
0x18004778c  lea     rdx, [rsp+140h+var_110]
0x180047791  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x180047796  mov     ecx, 9
0x18004779b  test    byte ptr [rax], 4
0x18004779e  movzx   eax, [rsp+140h+var_100.lfOutPrecision]
0x1800477a3  cmovnz  eax, ecx
0x1800477a6  mov     cl, [rsp+140h+var_100.lfCharSet]; unsigned __int8
0x1800477aa  mov     [rsp+140h+var_100.lfOutPrecision], al
0x1800477ae  mov     dl, [r12+5]
0x1800477b3  mov     al, dl
0x1800477b5  mov     [rsp+140h+var_100.lfClipPrecision], 40h ; '@'
0x1800477ba  and     al, 0F0h
0x1800477bc  mov     [rbx+7Ah], dl
0x1800477bf  mov     [rsp+140h+var_100.lfPitchAndFamily], dl
0x1800477c3  cmp     al, 70h ; 'p'
0x1800477c5  jnz     short loc_1800477CE
0x1800477c7  and     dl, 0Fh
0x1800477ca  mov     [rsp+140h+var_100.lfPitchAndFamily], dl
0x1800477ce  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x1800477d3  mov     [rbx+74h], ax
0x1800477d7  movsx   ecx, word ptr [r12+6]; int
0x1800477dd  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x1800477e2  mov     rdx, rax; unsigned __int16 *
0x1800477e5  lea     rcx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x1800477ea  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x1800477ef  movzx   edi, cs:?_bSysCharSet@CW32System@@0EA; uchar CW32System::_bSysCharSet
0x1800477f6  lea     eax, [rdi-0B1h]
0x1800477fc  cmp     eax, r15d
0x1800477ff  ja      short loc_180047842
0x180047801  mov     sil, [rsp+140h+var_100.lfCharSet]
0x180047806  test    sil, sil
0x180047809  jnz     short loc_180047847
0x18004780b  movsx   r8d, word ptr [r12+6]
0x180047811  lea     rdx, [rsp+140h+var_110]
0x180047816  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x18004781b  test    byte ptr [rax], 8
0x18004781e  jz      short loc_180047842
0x180047820  movsx   r8d, word ptr [r12+6]
0x180047826  lea     rdx, [rsp+140h+var_110]
0x18004782b  call    ?GetInfoFlags@CFontCache@@QEAA?ATFONTINFO_FLAGS@@H@Z; CFontCache::GetInfoFlags(int)
0x180047830  movzx   esi, [rsp+140h+var_100.lfCharSet]
0x180047835  test    byte ptr [rax], 2
0x180047838  cmovz   esi, edi
0x18004783b  mov     [rsp+140h+var_100.lfCharSet], sil
0x180047840  jmp     short loc_180047847
0x180047842  mov     sil, [rsp+140h+var_100.lfCharSet]
0x180047847  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x18004784b  mov     rcx, rbx; this
0x18004784e  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x180047853  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x180047858  test    rax, rax
0x18004785b  jz      loc_180047C9F
0x180047861  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x180047866  mov     r14, r13
0x180047869  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x18004786d  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180047872  test    eax, eax
0x180047874  jz      loc_180047BDE
0x18004787a  movzx   r11d, [rsp+140h+var_100.lfCharSet]
0x180047880  cmp     r11b, 2
0x180047884  jnz     short loc_1800478DB
0x180047886  lea     rdi, [rbx+48h]
0x18004788a  mov     [rsp+140h+var_100.lfCharSet], r13b
0x18004788f  mov     r14, [rdi]
0x180047892  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x180047896  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x18004789b  mov     rcx, rbx; this
0x18004789e  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x1800478a3  test    rax, rax
0x1800478a6  jz      loc_180047C9F
0x1800478ac  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x1800478b1  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x1800478b5  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x1800478ba  movzx   r11d, [rsp+140h+var_100.lfCharSet]
0x1800478c0  test    eax, eax
0x1800478c2  movzx   ecx, sil
0x1800478c6  mov     r15d, r13d
0x1800478c9  cmovnz  r11d, ecx
0x1800478cd  setz    r15b
0x1800478d1  mov     [rsp+140h+var_100.lfCharSet], r11b
0x1800478d6  jmp     loc_180047A94
0x1800478db  cmp     r11b, r15b
0x1800478de  jnz     short loc_18004793E
0x1800478e0  cmp     [rbx+77h], r15b
0x1800478e4  jnz     short loc_18004794B
0x1800478e6  lea     rdx, [rbp+40h+var_80]; unsigned __int16 *
0x1800478ea  mov     [rsp+140h+var_100.lfCharSet], 2
0x1800478ef  lea     rcx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x1800478f4  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x1800478f9  lea     rdi, [rbx+48h]
0x1800478fd  mov     rcx, rbx; this
0x180047900  mov     r14, [rdi]
0x180047903  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x180047907  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x18004790c  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x180047911  test    rax, rax
0x180047914  jz      loc_180047C9F
0x18004791a  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x18004791f  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x180047923  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180047928  test    eax, eax
0x18004792a  mov     [rsp+140h+var_100.lfCharSet], sil
0x18004792f  mov     r15d, r13d
0x180047932  mov     r11b, sil
0x180047935  setz    r15b
0x180047939  jmp     loc_180047A94
0x18004793e  lea     eax, [r11+4Fh]
0x180047942  cmp     al, r15b
0x180047945  jbe     loc_180047B50
0x18004794b  cmp     byte ptr [rbx+79h], 2
0x18004794f  jz      loc_180047AD4
0x180047955  mov     cl, r11b; unsigned __int8
0x180047958  call    ?IsFECharSet@CW32System@@SAHE@Z; CW32System::IsFECharSet(uchar)
0x18004795d  test    eax, eax
0x18004795f  jz      loc_180047AD4
0x180047965  call    ?OnWinNTFE@CW32System@@SA_NXZ; CW32System::OnWinNTFE(void)
0x18004796a  test    al, al
0x18004796c  jnz     loc_180047AD4
0x180047972  call    ?OnWin9xFE@CW32System@@SA_NXZ; CW32System::OnWin9xFE(void)
0x180047977  test    al, al
0x180047979  jnz     loc_180047AD4
0x18004797f  mov     esi, 80h
0x180047984  cmp     [rbx+77h], r11b
0x180047988  jz      short loc_1800479D7
0x18004798a  cmp     cs:?_dwPlatformId@CW32System@@0KA, r15d; ulong CW32System::_dwPlatformId
0x180047991  jnz     short loc_1800479D7
0x180047993  mov     ecx, r11d
0x180047996  sub     ecx, esi
0x180047998  jz      short loc_1800479C4
0x18004799a  sub     ecx, r15d
0x18004799d  jz      short loc_1800479BB
0x18004799f  sub     ecx, 5
0x1800479a2  jz      short loc_1800479B2
0x1800479a4  cmp     ecx, 2
0x1800479a7  jnz     short loc_1800479E8
0x1800479a9  movsx   ecx, cs:?g_iFontBig5@@3FA; short g_iFontBig5
0x1800479b0  jmp     short loc_1800479CB
0x1800479b2  movsx   ecx, cs:?g_iFontGB2312@@3FA; short g_iFontGB2312
0x1800479b9  jmp     short loc_1800479CB
0x1800479bb  movsx   ecx, cs:?g_iFontHangul@@3FA; short g_iFontHangul
0x1800479c2  jmp     short loc_1800479CB
0x1800479c4  movsx   ecx, cs:?g_iFontJapanese@@3FA; int
0x1800479cb  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x1800479d0  test    rax, rax
0x1800479d3  jz      short loc_1800479E8
0x1800479d5  jmp     short loc_1800479DB
0x1800479d7  lea     rax, [rbp+40h+var_80]
0x1800479db  mov     rdx, rax; unsigned __int16 *
0x1800479de  lea     rcx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x1800479e3  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG@Z; CopyLFFontName(tagLOGFONTW &,ushort const *)
0x1800479e8  lea     rdi, [rbx+48h]
0x1800479ec  mov     rcx, rbx; this
0x1800479ef  mov     r14, [rdi]
0x1800479f2  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x1800479f6  lea     rdx, [rsp+140h+var_100]; struct tagLOGFONTW *
0x1800479fb  call    ?GetFontWithMetrics@CCcs@@AEAAPEAUHFONT__@@PEAUtagLOGFONTW@@PEAG@Z; CCcs::GetFontWithMetrics(tagLOGFONTW *,ushort *)
0x180047a00  test    rax, rax
0x180047a03  jz      loc_180047C9F
0x180047a09  lea     rdx, [rsp+140h+var_100.lfFaceName]; unsigned __int16 *
0x180047a0e  lea     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x180047a12  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x180047a17  test    eax, eax
0x180047a19  jnz     short loc_180047A8C
0x180047a1b  cmp     cs:?_dwPlatformId@CW32System@@0KA, r15d; ulong CW32System::_dwPlatformId
0x180047a22  jnz     short loc_180047A8F
0x180047a24  movzx   r11d, [rsp+140h+var_100.lfCharSet]
0x180047a2a  mov     ecx, r11d
0x180047a2d  sub     ecx, esi
0x180047a2f  jz      short loc_180047A79
0x180047a31  sub     ecx, r15d
0x180047a34  jz      short loc_180047A66
0x180047a36  sub     ecx, 5
0x180047a39  jz      short loc_180047A53
0x180047a3b  cmp     ecx, 2
0x180047a3e  jnz     short loc_180047A94
0x180047a40  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180047a45  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180047a4a  mov     cs:?g_iFontBig5@@3FA, ax; short g_iFontBig5
0x180047a51  jmp     short loc_180047A8F
0x180047a53  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180047a58  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180047a5d  mov     cs:?g_iFontGB2312@@3FA, ax; short g_iFontGB2312
0x180047a64  jmp     short loc_180047A8F
0x180047a66  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180047a6b  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180047a70  mov     cs:?g_iFontHangul@@3FA, ax; short g_iFontHangul
0x180047a77  jmp     short loc_180047A8F
0x180047a79  lea     rcx, [rsp+140h+var_100.lfFaceName]; Src
0x180047a7e  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x180047a83  mov     cs:?g_iFontJapanese@@3FA, ax; short g_iFontJapanese
0x180047a8a  jmp     short loc_180047A8F
0x180047a8c  mov     r15d, r13d
0x180047a8f  mov     r11b, [rsp+140h+var_100.lfCharSet]
0x180047a94  test    r14, r14
0x180047a97  jz      short loc_180047ACE
0x180047a99  test    r15d, r15d
0x180047a9c  jz      short loc_180047AA9
0x180047a9e  mov     rcx, r14; ho
0x180047aa1  call    cs:__imp_DeleteObject
0x180047aa7  jmp     short loc_180047AC6
0x180047aa9  mov     rcx, rbx; this
0x180047aac  call    ?DestroyFont@CCcs@@AEAAXXZ; CCcs::DestroyFont(void)
0x180047ab1  xor     edx, edx; unsigned __int16 *
0x180047ab3  mov     [rdi], r14
0x180047ab6  mov     rcx, rbx; this
0x180047ab9  call    ?GetMetrics@CCcs@@AEAAHPEAG@Z; CCcs::GetMetrics(ushort *)
0x180047abe  test    eax, eax
0x180047ac0  jz      loc_180047C9F
0x180047ac6  mov     r11b, [rsp+140h+var_100.lfCharSet]
0x180047acb  mov     r14, r13
0x180047ace  mov     r15d, 1
0x180047ad4  mov     al, [rbx+77h]
0x180047ad7  cmp     al, 2
0x180047ad9  jnz     short loc_180047AE3
0x180047adb  mov     ecx, r15d
0x180047ade  cmp     r11b, al
0x180047ae1  jnz     short loc_180047AE6
0x180047ae3  mov     ecx, r13d
0x180047ae6  cmp     al, r11b
0x180047ae9  jz      short loc_180047B5E
0x180047aeb  cmp     r11b, r15b
0x180047aee  jz      short loc_180047B5E
0x180047af0  cmp     r11b, 0DEh
0x180047af4  jnz     short loc_180047B66
0x180047af6  test    al, al
0x180047af8  jnz     short loc_180047B66
0x180047afa  lea     rax, [rsp+140h+var_10C]
0x180047aff  mov     [rsp+140h+var_110], r13w
0x180047b05  mov     [rsp+140h+var_118], rax; unsigned __int8 *
  ... truncated ...
```
