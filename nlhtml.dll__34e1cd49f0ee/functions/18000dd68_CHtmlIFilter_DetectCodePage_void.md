# CHtmlIFilter::DetectCodePage(void)

- ea: `0x18000dd68`
- end: `0x18000e1ad`
- name: `?DetectCodePage@CHtmlIFilter@@AEAAKXZ`
- size: `1093`
- prototype: `__int64 __fastcall(CHtmlIFilter *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18000db00`

## callees

- `0x1800064a0`
- `0x18000b68c`
- `0x18000d6fc`
- `0x18000dd68`
- `0x18000e24c`
- `0x18000e278`
- `0x18000e344`
- `0x18000e664`
- `0x18000f98c`
- `0x18000fab0`
- `0x1800121b4`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000de9c`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000e014`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000e067`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000e15d`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000de9c`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000e014`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000e067`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18000e15d`

## string_xrefs

- `0x18000e022`: `[HTML] not filtering doc because its code page is not installed\n`

## pseudocode

```c
__int64 __fastcall CHtmlIFilter::DetectCodePage(CHtmlIFilter *this)
{
  const wchar_t *v2; // rdx
  CSerialStream *v3; // rsi
  char *v4; // r15
  CMemoryMappedInputStream *v5; // r14
  struct IStream *v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // ecx
  CMemoryMappedInputStream *v10; // rcx
  unsigned int v11; // edx
  __int64 result; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  const wchar_t *v25; // r9
  const wchar_t *v26; // r8
  __int64 v27; // rdx
  struct IMultiLanguage2 *v28; // rsi
  int v29; // eax
  unsigned int v30; // edx

  *((_DWORD *)this + 1266) = 0;
  v2 = (const wchar_t *)*((_QWORD *)this + 10);
  v3 = (CHtmlIFilter *)((char *)this + 616);
  v4 = (char *)this + 658;
  v5 = (CHtmlIFilter *)((char *)this + 712);
  if ( v2 )
  {
    *(_OWORD *)v3 = 0;
    *(_OWORD *)((char *)this + 632) = 0;
    *((_QWORD *)this + 81) = 0;
    *((_WORD *)this + 328) = 0;
    *((_DWORD *)this + 175) = 0;
    *((_QWORD *)this + 88) = v4;
    CMemoryMappedInputStream::Init((CHtmlIFilter *)((char *)this + 712), v2);
  }
  else
  {
    v6 = (struct IStream *)*((_QWORD *)this + 11);
    *(_OWORD *)v3 = 0;
    *(_OWORD *)((char *)this + 632) = 0;
    *((_QWORD *)this + 81) = 0;
    *((_WORD *)this + 328) = 0;
    *((_DWORD *)this + 175) = 0;
    *((_QWORD *)this + 88) = v4;
    CMemoryMappedInputStream::Init((CHtmlIFilter *)((char *)this + 712), v6);
  }
  CSerialStream::CheckForUnicodeStream(v3);
  CSerialStream::InitAsUnicodeIfUnicode(v3);
  CCodePageRecognizer::Init((CHtmlIFilter *)((char *)this + 5144), this, v3);
  if ( *((_DWORD *)this + 1286) )
  {
    result = 0;
    goto LABEL_51;
  }
  v7 = 0;
  if ( *((_DWORD *)this + 1287) )
    v7 = *((_DWORD *)this + 1288);
  if ( (unsigned int)CSerialStream::InitAsUnicodeIfUnicode(v3) )
    return IsValidOrFallbackLocale(v7) ? v7 : 0;
  if ( *((_DWORD *)this + 1289) )
    *((_DWORD *)this + 1266) = *((_DWORD *)this + 1290);
  v8 = *((_DWORD *)this + 1266);
  switch ( v8 )
  {
    case 50220:
      *((_DWORD *)this + 1266) = 1;
      break;
    case 51932:
      *((_DWORD *)this + 1266) = 2;
      break;
    case 50000:
      *((_DWORD *)this + 1266) = 0;
LABEL_13:
      if ( !v7 )
        goto LABEL_14;
      goto LABEL_44;
    case 0:
      goto LABEL_13;
  }
  if ( v7 && IsValidOrFallbackLocale(v7) )
  {
LABEL_44:
    v7 &= -IsValidOrFallbackLocale(v7);
    goto LABEL_14;
  }
  v13 = *((_DWORD *)this + 1266);
  if ( v13 <= 0x4E3 )
  {
    if ( v13 != 1251 )
    {
      v14 = v13 - 1;
      if ( !v14 )
        goto LABEL_58;
      v15 = v14 - 1;
      if ( !v15 )
        goto LABEL_58;
      v16 = v15 - 872;
      if ( !v16 )
      {
        v7 = 1054;
        goto LABEL_59;
      }
      v17 = v16 - 58;
      if ( !v17 )
      {
LABEL_58:
        v7 = 1041;
        goto LABEL_59;
      }
      v18 = v17 - 4;
      if ( !v18 )
      {
        v7 = 2052;
        goto LABEL_59;
      }
      v19 = v18 - 13;
      if ( v19 )
      {
        if ( v19 == 1 )
        {
          v7 = 1028;
          goto LABEL_59;
        }
        goto LABEL_40;
      }
LABEL_68:
      v7 = 1042;
      goto LABEL_59;
    }
    goto LABEL_67;
  }
  v20 = v13 - 1253;
  if ( !v20 )
  {
    v7 = 1032;
    goto LABEL_59;
  }
  v21 = v20 - 2;
  if ( !v21 )
  {
    v7 = 1037;
    goto LABEL_59;
  }
  v22 = v21 - 106;
  if ( !v22 )
    goto LABEL_68;
  v23 = v22 - 19505;
  if ( !v23 || (v24 = v23 - 7729) == 0 )
  {
LABEL_67:
    v7 = 1049;
    goto LABEL_59;
  }
  if ( v24 == 23354 )
    goto LABEL_68;
LABEL_40:
  if ( !v7 )
    goto LABEL_14;
LABEL_59:
  if ( IsValidOrFallbackLocale(v7) )
    goto LABEL_13;
  v7 = 0;
LABEL_14:
  v9 = *((_DWORD *)this + 1266);
  if ( !v9 )
  {
    *((_DWORD *)this + 1266) = 65001;
    goto LABEL_18;
  }
  if ( (unsigned int)(v9 - 1) <= 1 )
  {
    if ( !IsValidCodePage(0x3A4u) || (v28 = (struct IMultiLanguage2 *)*((_QWORD *)this + 671)) == 0 )
    {
      v26 = L"[HTML] Cannot apply conversion to S-JIS\n";
      v27 = 1136;
      goto LABEL_48;
    }
    ((void (__fastcall *)(_QWORD))v28->lpVtbl->AddRef)(*((_QWORD *)this + 671));
    v29 = *((_DWORD *)this + 1266);
    if ( v29 == 1 )
    {
      v30 = 50220;
    }
    else
    {
      if ( v29 != 2 )
        goto LABEL_57;
      v30 = 51932;
    }
    CHtmlIFilter::InternalConvertToSJISUsingMLang(this, v30, v28);
LABEL_57:
    *((_DWORD *)this + 1266) = 932;
    ((void (__fastcall *)(struct IMultiLanguage2 *))v28->lpVtbl->Release)(v28);
    return v7;
  }
  if ( v9 == 28591 )
  {
    *((_DWORD *)this + 1266) = 1252;
  }
  else if ( v9 == 28599 && IsValidCodePage(0x4E6u) )
  {
    *((_DWORD *)this + 1266) = 1254;
  }
LABEL_18:
  if ( !IsValidCodePage(*((_DWORD *)this + 1266)) && *((_DWORD *)this + 1266) == 20127 )
    *((_DWORD *)this + 1266) = 1252;
  v10 = (CMemoryMappedInputStream *)*((unsigned int *)this + 1266);
  if ( (_DWORD)v10 == 65001 || IsValidCodePage((UINT)v10) )
  {
    v11 = *((_DWORD *)this + 1266);
    *(_OWORD *)v3 = 0;
    *((_OWORD *)v3 + 1) = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_WORD *)v3 + 20) = 0;
    *((_DWORD *)v3 + 21) = 0;
    *((_QWORD *)v3 + 11) = v4;
    *((_DWORD *)v5 + 4) = v11;
    *((_DWORD *)v5 + 7) = CMemoryMappedInputStream::IsDBCSCodePage(v10, v11);
    CMemoryMappedInputStream::InternalInitNoCodePage(v5);
    return v7;
  }
  v26 = (const wchar_t *)L"[HTML] not filtering doc because its code page is not installed\n";
  v27 = 1185;
LABEL_48:
  SearchIndexerDebug::Error(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\htmlfilt.cxx",
    (const wchar_t *)v27,
    (unsigned int)v26,
    v25);
  result = v7;
LABEL_51:
  *((_DWORD *)this + 14) = 1;
  return result;
}

```

## disassembly

```asm
0x18000dd68  mov     [rsp+arg_8], rbx
0x18000dd6d  mov     [rsp+arg_10], rsi
0x18000dd72  push    rdi
0x18000dd73  push    r14
0x18000dd75  push    r15
0x18000dd77  sub     rsp, 20h
0x18000dd7b  mov     rdi, rcx
0x18000dd7e  mov     dword ptr [rcx+13C8h], 0
0x18000dd88  mov     rdx, [rcx+50h]; wchar_t *
0x18000dd8c  lea     rsi, [rcx+268h]
0x18000dd93  lea     r15, [rsi+2Ah]
0x18000dd97  lea     r14, [rsi+60h]
0x18000dd9b  xorps   xmm0, xmm0
0x18000dd9e  xor     eax, eax
0x18000dda0  test    rdx, rdx
0x18000dda3  jnz     loc_18000DFF1
0x18000dda9  mov     rdx, [rcx+58h]; struct IStream *
0x18000ddad  movups  xmmword ptr [rsi], xmm0
0x18000ddb0  movups  xmmword ptr [rsi+10h], xmm0
0x18000ddb4  mov     [rsi+20h], rax
0x18000ddb8  mov     [rsi+28h], ax
0x18000ddbc  mov     [rsi+54h], eax
0x18000ddbf  mov     [rsi+58h], r15
0x18000ddc3  mov     rcx, r14; this
0x18000ddc6  call    ?Init@CMemoryMappedInputStream@@QEAAXPEAUIStream@@@Z; CMemoryMappedInputStream::Init(IStream *)
0x18000ddcb  mov     rcx, rsi; this
0x18000ddce  call    ?CheckForUnicodeStream@CSerialStream@@QEAAXXZ; CSerialStream::CheckForUnicodeStream(void)
0x18000ddd3  mov     rcx, rsi; this
0x18000ddd6  call    ?InitAsUnicodeIfUnicode@CSerialStream@@QEAAHXZ; CSerialStream::InitAsUnicodeIfUnicode(void)
0x18000dddb  lea     rbx, [rdi+1418h]
0x18000dde2  mov     r8, rsi; struct CSerialStream *
0x18000dde5  mov     rdx, rdi; struct CHtmlIFilter *
0x18000dde8  mov     rcx, rbx; this
0x18000ddeb  call    ?Init@CCodePageRecognizer@@QEAAXAEAVCHtmlIFilter@@AEAVCSerialStream@@@Z; CCodePageRecognizer::Init(CHtmlIFilter &,CSerialStream &)
0x18000ddf0  cmp     dword ptr [rbx], 0
0x18000ddf3  jnz     loc_18000E050
0x18000ddf9  xor     ebx, ebx
0x18000ddfb  cmp     [rdi+141Ch], ebx
0x18000de01  jz      short loc_18000DE09
0x18000de03  mov     ebx, [rdi+1420h]
0x18000de09  mov     rcx, rsi; this
0x18000de0c  call    ?InitAsUnicodeIfUnicode@CSerialStream@@QEAAHXZ; CSerialStream::InitAsUnicodeIfUnicode(void)
0x18000de11  test    eax, eax
0x18000de13  jnz     loc_18000E03E
0x18000de19  cmp     [rdi+1424h], eax
0x18000de1f  jz      short loc_18000DE2D
0x18000de21  mov     eax, [rdi+1428h]
0x18000de27  mov     [rdi+13C8h], eax
0x18000de2d  mov     eax, [rdi+13C8h]
0x18000de33  cmp     eax, 0C42Ch
0x18000de38  jz      loc_18000DF08
0x18000de3e  cmp     eax, 0CADCh
0x18000de43  jz      loc_18000E117
0x18000de49  cmp     eax, 0C350h
0x18000de4e  jz      loc_18000E126
0x18000de54  test    eax, eax
0x18000de56  jnz     loc_18000DF12
0x18000de5c  test    ebx, ebx
0x18000de5e  jnz     loc_18000DFDF
0x18000de64  mov     ecx, [rdi+13C8h]
0x18000de6a  test    ecx, ecx
0x18000de6c  jz      loc_18000E0F7
0x18000de72  lea     eax, [rcx-1]
0x18000de75  cmp     eax, 1
0x18000de78  jbe     loc_18000E05E
0x18000de7e  cmp     ecx, 6FAFh
0x18000de84  jz      loc_18000DFC1
0x18000de8a  cmp     ecx, 6FB7h
0x18000de90  jz      loc_18000E158
0x18000de96  mov     ecx, [rdi+13C8h]; CodePage
0x18000de9c  call    cs:__imp_IsValidCodePage
0x18000dea2  test    eax, eax
0x18000dea4  jz      loc_18000E17A
0x18000deaa  mov     ecx, [rdi+13C8h]; this
0x18000deb0  cmp     ecx, 0FDE9h
0x18000deb6  jnz     loc_18000E014
0x18000debc  mov     edx, [rdi+13C8h]; unsigned int
0x18000dec2  xorps   xmm0, xmm0
0x18000dec5  xor     eax, eax
0x18000dec7  movups  xmmword ptr [rsi], xmm0
0x18000deca  movups  xmmword ptr [rsi+10h], xmm0
0x18000dece  mov     [rsi+20h], rax
0x18000ded2  mov     [rsi+28h], ax
0x18000ded6  mov     [rsi+54h], eax
0x18000ded9  mov     [rsi+58h], r15
0x18000dedd  mov     [r14+10h], edx
0x18000dee1  call    ?IsDBCSCodePage@CMemoryMappedInputStream@@AEAAHK@Z; CMemoryMappedInputStream::IsDBCSCodePage(ulong)
0x18000dee6  mov     [r14+1Ch], eax
0x18000deea  mov     rcx, r14; this
0x18000deed  call    ?InternalInitNoCodePage@CMemoryMappedInputStream@@AEAAXXZ; CMemoryMappedInputStream::InternalInitNoCodePage(void)
0x18000def2  mov     eax, ebx
0x18000def4  mov     rbx, [rsp+38h+arg_8]
0x18000def9  mov     rsi, [rsp+38h+arg_10]
0x18000defe  add     rsp, 20h
0x18000df02  pop     r15
0x18000df04  pop     r14
0x18000df06  pop     rdi
0x18000df07  retn
0x18000df08  mov     dword ptr [rdi+13C8h], 1
0x18000df12  test    ebx, ebx
0x18000df14  jnz     loc_18000DFD0
0x18000df1a  mov     eax, [rdi+13C8h]
0x18000df20  mov     ecx, 4E3h
0x18000df25  cmp     eax, ecx
0x18000df27  ja      short loc_18000DF76
0x18000df29  jz      loc_18000E13C
0x18000df2f  sub     eax, 1
0x18000df32  jz      loc_18000E0D5
0x18000df38  sub     eax, 1
0x18000df3b  jz      loc_18000E0D5
0x18000df41  sub     eax, 368h
0x18000df46  jz      loc_18000E135
0x18000df4c  sub     eax, 3Ah ; ':'
0x18000df4f  jz      loc_18000E0D5
0x18000df55  sub     eax, 4
0x18000df58  jz      loc_18000E0F0
0x18000df5e  sub     eax, 0Dh
0x18000df61  jz      loc_18000E143
0x18000df67  cmp     eax, 1
0x18000df6a  jnz     short loc_18000DFB4
0x18000df6c  mov     ebx, 404h
0x18000df71  jmp     loc_18000E0DA
0x18000df76  sub     eax, 4E5h
0x18000df7b  jz      loc_18000E151
0x18000df81  sub     eax, 2
0x18000df84  jz      loc_18000E14A
0x18000df8a  sub     eax, 6Ah ; 'j'
0x18000df8d  jz      loc_18000E143
0x18000df93  sub     eax, 4C31h
0x18000df98  jz      loc_18000E13C
0x18000df9e  sub     eax, 1E31h
0x18000dfa3  jz      loc_18000E13C
0x18000dfa9  cmp     eax, 5B3Ah
0x18000dfae  jz      loc_18000E143
0x18000dfb4  test    ebx, ebx
0x18000dfb6  jz      loc_18000DE64
0x18000dfbc  jmp     loc_18000E0DA
0x18000dfc1  mov     dword ptr [rdi+13C8h], 4E4h
0x18000dfcb  jmp     loc_18000DE96
0x18000dfd0  mov     ecx, ebx; unsigned int
0x18000dfd2  call    ?IsValidOrFallbackLocale@@YA_NK@Z; IsValidOrFallbackLocale(ulong)
0x18000dfd7  test    al, al
0x18000dfd9  jz      loc_18000DF1A
0x18000dfdf  mov     ecx, ebx; unsigned int
0x18000dfe1  call    ?IsValidOrFallbackLocale@@YA_NK@Z; IsValidOrFallbackLocale(ulong)
0x18000dfe6  neg     al
0x18000dfe8  sbb     ecx, ecx
0x18000dfea  and     ebx, ecx
0x18000dfec  jmp     loc_18000DE64
0x18000dff1  movups  xmmword ptr [rsi], xmm0
0x18000dff4  movups  xmmword ptr [rsi+10h], xmm0
0x18000dff8  mov     [rsi+20h], rax
0x18000dffc  mov     [rsi+28h], ax
0x18000e000  mov     [rsi+54h], eax
0x18000e003  mov     [rsi+58h], r15
0x18000e007  mov     rcx, r14; this
0x18000e00a  call    ?Init@CMemoryMappedInputStream@@QEAAXPEB_W@Z; CMemoryMappedInputStream::Init(wchar_t const *)
0x18000e00f  jmp     loc_18000DDCB
0x18000e014  call    cs:__imp_IsValidCodePage
0x18000e01a  test    eax, eax
0x18000e01c  jnz     loc_18000DEBC
0x18000e022  lea     r8, aHtmlNotFilteri; "[HTML] not filtering doc because its co"...
0x18000e029  mov     edx, 4A1h; wchar_t *
0x18000e02e  lea     rcx, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000e035  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000e03a  mov     eax, ebx
0x18000e03c  jmp     short loc_18000E052
0x18000e03e  mov     ecx, ebx; unsigned int
0x18000e040  call    ?IsValidOrFallbackLocale@@YA_NK@Z; IsValidOrFallbackLocale(ulong)
0x18000e045  neg     al
0x18000e047  sbb     eax, eax
0x18000e049  and     eax, ebx
0x18000e04b  jmp     loc_18000DEF4
0x18000e050  xor     eax, eax
0x18000e052  mov     dword ptr [rdi+38h], 1
0x18000e059  jmp     loc_18000DEF4
0x18000e05e  mov     r14d, 3A4h
0x18000e064  mov     ecx, r14d; CodePage
0x18000e067  call    cs:__imp_IsValidCodePage
0x18000e06d  test    eax, eax
0x18000e06f  jz      loc_18000E106
0x18000e075  mov     rsi, [rdi+14F8h]
0x18000e07c  test    rsi, rsi
0x18000e07f  jz      loc_18000E106
0x18000e085  mov     rax, [rsi]
0x18000e088  mov     rcx, rsi
0x18000e08b  mov     rax, [rax+8]
0x18000e08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e094  nop
0x18000e095  mov     [rsp+38h+arg_0], rsi
0x18000e09a  mov     eax, [rdi+13C8h]
0x18000e0a0  cmp     eax, 1
0x18000e0a3  jnz     loc_18000E199
0x18000e0a9  mov     edx, 0C42Ch; unsigned int
0x18000e0ae  mov     r8, rsi; struct IMultiLanguage2 *
0x18000e0b1  mov     rcx, rdi; this
0x18000e0b4  call    ?InternalConvertToSJISUsingMLang@CHtmlIFilter@@AEAAXKPEAUIMultiLanguage2@@@Z; CHtmlIFilter::InternalConvertToSJISUsingMLang(ulong,IMultiLanguage2 *)
0x18000e0b9  mov     [rdi+13C8h], r14d
0x18000e0c0  mov     rax, [rsi]
0x18000e0c3  mov     rcx, rsi
0x18000e0c6  mov     rax, [rax+10h]
0x18000e0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0cf  nop
0x18000e0d0  jmp     loc_18000DEF2
0x18000e0d5  mov     ebx, 411h
0x18000e0da  mov     ecx, ebx; unsigned int
0x18000e0dc  call    ?IsValidOrFallbackLocale@@YA_NK@Z; IsValidOrFallbackLocale(ulong)
0x18000e0e1  test    al, al
0x18000e0e3  jnz     loc_18000DE5C
0x18000e0e9  xor     ebx, ebx
0x18000e0eb  jmp     loc_18000DE64
0x18000e0f0  mov     ebx, 804h
0x18000e0f5  jmp     short loc_18000E0DA
0x18000e0f7  mov     dword ptr [rdi+13C8h], 0FDE9h
0x18000e101  jmp     loc_18000DE96
0x18000e106  lea     r8, aHtmlCannotAppl; "[HTML] Cannot apply conversion to S-JIS"...
0x18000e10d  mov     edx, 470h
0x18000e112  jmp     loc_18000E02E
0x18000e117  mov     dword ptr [rdi+13C8h], 2
0x18000e121  jmp     loc_18000DF12
0x18000e126  mov     dword ptr [rdi+13C8h], 0
0x18000e130  jmp     loc_18000DE5C
0x18000e135  mov     ebx, 41Eh
0x18000e13a  jmp     short loc_18000E0DA
0x18000e13c  mov     ebx, 419h
0x18000e141  jmp     short loc_18000E0DA
0x18000e143  mov     ebx, 412h
0x18000e148  jmp     short loc_18000E0DA
0x18000e14a  mov     ebx, 40Dh
0x18000e14f  jmp     short loc_18000E0DA
0x18000e151  mov     ebx, 408h
0x18000e156  jmp     short loc_18000E0DA
0x18000e158  mov     ecx, 4E6h; CodePage
0x18000e15d  call    cs:__imp_IsValidCodePage
0x18000e163  test    eax, eax
0x18000e165  jz      loc_18000DE96
0x18000e16b  mov     dword ptr [rdi+13C8h], 4E6h
0x18000e175  jmp     loc_18000DE96
0x18000e17a  cmp     dword ptr [rdi+13C8h], 4E9Fh
0x18000e184  jnz     loc_18000DEAA
0x18000e18a  mov     dword ptr [rdi+13C8h], 4E4h
0x18000e194  jmp     loc_18000DEAA
0x18000e199  cmp     eax, 2
0x18000e19c  jnz     loc_18000E0B9
0x18000e1a2  mov     edx, 0CADCh
0x18000e1a7  jmp     loc_18000E0AE
```
