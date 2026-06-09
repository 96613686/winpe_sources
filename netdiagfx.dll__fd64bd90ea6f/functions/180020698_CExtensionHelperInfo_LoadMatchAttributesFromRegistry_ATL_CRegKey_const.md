# CExtensionHelperInfo::LoadMatchAttributesFromRegistry(ATL::CRegKey const &)

- ea: `0x180020698`
- end: `0x180020ab6`
- name: `?LoadMatchAttributesFromRegistry@CExtensionHelperInfo@@AEAAJAEBVCRegKey@ATL@@@Z`
- size: `1054`
- prototype: `__int64 __fastcall(CExtensionHelperInfo *__hidden this, const struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f71c`

## callees

- `0x1800020d6`
- `0x180002798`
- `0x1800027e8`
- `0x180006d58`
- `0x180008248`
- `0x18001eb8c`
- `0x18001f0a4`
- `0x18001f188`
- `0x180020698`
- `0x180021094`
- `0x18002c840`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180020773`
- `ADVAPI32!RegEnumValueW` at `0x180020773`

## pseudocode

```c
__int64 __fastcall CExtensionHelperInfo::LoadMatchAttributesFromRegistry(CExtensionHelperInfo *this, HKEY *a2)
{
  int v3; // eax
  signed int v4; // ebx
  int v5; // edi
  DWORD i; // r14d
  int v7; // eax
  _BYTE *v8; // rax
  _BYTE *v9; // rsi
  __int64 v10; // rcx
  unsigned __int64 v11; // rax
  void *v12; // rcx
  __int64 v13; // rcx
  _BYTE *v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rax
  void *v17; // rcx
  void *v18; // rax
  struct tagHELPER_ATTRIBUTE *v19; // rax
  struct tagHELPER_ATTRIBUTE *v20; // rsi
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  WCHAR *v23; // rcx
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  void *v27; // rax
  __int64 v28; // r8
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey[3]; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v38; // [rsp+288h] [rbp+188h]
  WCHAR ValueName[264]; // [rsp+290h] [rbp+190h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = ATL::CRegKey::Open(hKey, *a2, L"MatchAttributes", 0x20019u);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_52;
  }
  Type = 0;
  v4 = 0;
  v5 = 0;
  v38 = 0;
  for ( i = 0; ; ++i )
  {
    cchValueName = 260;
    cbData = 520;
    v7 = RegEnumValueW(hKey[0], i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
    if ( v7 )
      break;
    if ( Type != 1 )
    {
      if ( Type == 3 )
      {
        v14 = operator new[](0x90u);
        v9 = v14;
        if ( v14 )
        {
          v15 = 144;
          do
          {
            *v14++ = 0;
            --v15;
          }
          while ( v15 );
          v16 = 2LL * (cchValueName + 1);
          if ( !is_mul_ok(cchValueName + 1, 2u) )
            v16 = -1;
          v17 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
          *(_QWORD *)v9 = v17;
          if ( v17 )
          {
            memcpy_0(v17, ValueName, 2LL * (cchValueName + 1));
            *((_DWORD *)v9 + 4) = cbData;
            v18 = operator new[](cbData);
            *((_QWORD *)v9 + 3) = v18;
            if ( v18 )
            {
              memcpy_0(v18, Data, cbData);
              *((_DWORD *)v9 + 2) = 14;
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64)&v34,
                *(_QWORD *)v9);
              *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,tagHELPER_ATTRIBUTE *>::operator[](
                           (char *)this + 72,
                           &v34) = v9;
              v13 = v34;
              goto LABEL_25;
            }
          }
        }
      }
      else
      {
        if ( Type != 4 )
          continue;
        v8 = operator new[](0x90u);
        v9 = v8;
        if ( v8 )
        {
          v10 = 144;
          do
          {
            *v8++ = 0;
            --v10;
          }
          while ( v10 );
          v11 = 2LL * (cchValueName + 1);
          if ( !is_mul_ok(cchValueName + 1, 2u) )
            v11 = -1;
          v12 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
          *(_QWORD *)v9 = v12;
          if ( v12 )
          {
            memcpy_0(v12, ValueName, 2LL * (cchValueName + 1));
            *((_DWORD *)v9 + 4) = *(_DWORD *)Data;
            *((_DWORD *)v9 + 2) = 7;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64)&v33,
              *(_QWORD *)v9);
            *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,tagHELPER_ATTRIBUTE *>::operator[](
                         (char *)this + 72,
                         &v33) = v9;
            v13 = v33;
LABEL_25:
            ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
            if ( v5 >= 0 )
              continue;
LABEL_26:
            FreeMatchValue((struct tagHELPER_ATTRIBUTE *)v9);
            if ( v4 >= 0 )
              v4 = v5;
            continue;
          }
        }
      }
      v5 = -2147024882;
      goto LABEL_26;
    }
    v19 = (struct tagHELPER_ATTRIBUTE *)operator new[](0x90u);
    v20 = v19;
    if ( !v19 )
      goto LABEL_29;
    v21 = 144;
    do
    {
      LOBYTE(v19->pwszName) = 0;
      v19 = (struct tagHELPER_ATTRIBUTE *)((char *)v19 + 1);
      --v21;
    }
    while ( v21 );
    v22 = 2LL * (cchValueName + 1);
    if ( !is_mul_ok(cchValueName + 1, 2u) )
      v22 = -1;
    v23 = (WCHAR *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
    v20->pwszName = v23;
    if ( !v23 )
      goto LABEL_29;
    memcpy_0(v23, ValueName, 2LL * (cchValueName + 1));
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)&Data[2 * v24] );
    v25 = v24 + 1;
    v26 = 2 * v25;
    if ( !is_mul_ok(v25, 2u) )
      v26 = -1;
    v27 = operator new[](v26, (const struct std::nothrow_t *)&std::nothrow);
    v20->Int64 = (LONGLONG)v27;
    if ( v27 )
    {
      v28 = -1;
      do
        ++v28;
      while ( *(_WORD *)&Data[2 * v28] );
      memcpy_0(v27, Data, 2 * v28 + 2);
      v20->type = AT_STRING;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v35,
        (__int64)v20->pwszName);
      *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,tagHELPER_ATTRIBUTE *>::operator[](
                   (char *)this + 72,
                   &v35) = v20;
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
      if ( v5 >= 0 )
        continue;
    }
    else
    {
LABEL_29:
      v5 = -2147024882;
    }
    FreeMatchValue(v20);
    if ( v4 >= 0 )
      v4 = v5;
  }
  if ( v7 != 259 )
  {
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 >= 0 )
      v4 = v7;
  }
  ATL::CRegKey::Close(hKey);
LABEL_52:
  ATL::CRegKey::Close(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180020698  mov     [rsp-8+arg_10], rbx
0x18002069d  push    rbp
0x18002069e  push    rsi
0x18002069f  push    rdi
0x1800206a0  push    r12
0x1800206a2  push    r13
0x1800206a4  push    r14
0x1800206a6  push    r15
0x1800206a8  lea     rbp, [rsp-3B0h]
0x1800206b0  sub     rsp, 4B0h
0x1800206b7  mov     rax, cs:__security_cookie
0x1800206be  xor     rax, rsp
0x1800206c1  mov     [rbp+3E0h+var_40], rax
0x1800206c8  mov     r15, rcx
0x1800206cb  xor     r12d, r12d
0x1800206ce  mov     [rsp+4E0h+hKey], r12
0x1800206d3  mov     [rsp+4E0h+var_470], r12
0x1800206d8  mov     [rsp+4E0h+var_468], r12
0x1800206dd  mov     r9d, 20019h; unsigned int
0x1800206e3  lea     r8, SubKey; "MatchAttributes"
0x1800206ea  mov     rdx, [rdx]; hKey
0x1800206ed  lea     rcx, [rsp+4E0h+hKey]; this
0x1800206f2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800206f7  mov     ebx, eax
0x1800206f9  test    eax, eax
0x1800206fb  jz      short loc_180020711
0x1800206fd  jle     loc_180020A80
0x180020703  movzx   ebx, ax
0x180020706  or      ebx, 80070000h
0x18002070c  jmp     loc_180020A80
0x180020711  mov     [rsp+4E0h+Type], r12d
0x180020716  mov     ebx, r12d
0x180020719  mov     edi, r12d
0x18002071c  mov     [rbp+3E0h+var_258], r12w
0x180020724  mov     r14d, r12d
0x180020727  mov     r13d, 8007000Eh
0x18002072d  mov     [rsp+4E0h+cchValueName], 104h
0x180020735  mov     [rsp+4E0h+cbData], 208h
0x18002073d  lea     rax, [rsp+4E0h+cbData]
0x180020742  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x180020747  lea     rax, [rbp+3E0h+Data]
0x18002074b  mov     [rsp+4E0h+lpData], rax; lpData
0x180020750  lea     rax, [rsp+4E0h+Type]
0x180020755  mov     [rsp+4E0h+lpType], rax; lpType
0x18002075a  mov     [rsp+4E0h+lpReserved], r12; lpReserved
0x18002075f  lea     r9, [rsp+4E0h+cchValueName]; lpcchValueName
0x180020764  lea     r8, [rbp+3E0h+ValueName]; lpValueName
0x18002076b  mov     edx, r14d; dwIndex
0x18002076e  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180020773  call    cs:__imp_RegEnumValueW
0x180020779  test    eax, eax
0x18002077b  jnz     loc_180020A5E
0x180020781  mov     eax, [rsp+4E0h+Type]
0x180020785  sub     eax, 1
0x180020788  jz      loc_180020937
0x18002078e  sub     eax, 2
0x180020791  jz      loc_180020846
0x180020797  cmp     eax, 1
0x18002079a  jnz     loc_180020A56
0x1800207a0  mov     ecx, 90h; unsigned __int64
0x1800207a5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800207aa  mov     rsi, rax
0x1800207ad  test    rax, rax
0x1800207b0  jz      loc_180020858
0x1800207b6  mov     ecx, 90h
0x1800207bb  mov     [rax], r12b
0x1800207be  inc     rax
0x1800207c1  sub     rcx, 1
0x1800207c5  jnz     short loc_1800207BB
0x1800207c7  mov     ecx, [rsp+4E0h+cchValueName]
0x1800207cb  inc     ecx
0x1800207cd  mov     eax, 2
0x1800207d2  mul     rcx
0x1800207d5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800207dc  cmovb   rax, rcx
0x1800207e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800207e7  mov     rcx, rax; unsigned __int64
0x1800207ea  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800207ef  mov     rcx, rax; void *
0x1800207f2  mov     [rsi], rax
0x1800207f5  test    rax, rax
0x1800207f8  jz      short loc_180020858
0x1800207fa  mov     r8d, [rsp+4E0h+cchValueName]
0x1800207ff  inc     r8d
0x180020802  add     r8, r8; Size
0x180020805  lea     rdx, [rbp+3E0h+ValueName]; Src
0x18002080c  call    memcpy_0
0x180020811  mov     eax, dword ptr [rbp+3E0h+Data]
0x180020814  mov     [rsi+10h], eax
0x180020817  mov     dword ptr [rsi+8], 7
0x18002081e  mov     rdx, [rsi]
0x180020821  lea     rcx, [rsp+4E0h+var_490]
0x180020826  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002082b  lea     rcx, [r15+48h]
0x18002082f  lea     rdx, [rsp+4E0h+var_490]
0x180020834  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@@5@@std@@QEAAAEAPEAUtagHELPER_ATTRIBUTE@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,tagHELPER_ATTRIBUTE *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x180020839  mov     [rax], rsi
0x18002083c  mov     rcx, [rsp+4E0h+var_490]
0x180020841  jmp     loc_18002090F
0x180020846  mov     ecx, 90h; unsigned __int64
0x18002084b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180020850  mov     rsi, rax
0x180020853  test    rax, rax
0x180020856  jnz     short loc_180020860
0x180020858  mov     edi, r13d
0x18002085b  jmp     loc_180020920
0x180020860  mov     ecx, 90h
0x180020865  mov     [rax], r12b
0x180020868  inc     rax
0x18002086b  sub     rcx, 1
0x18002086f  jnz     short loc_180020865
0x180020871  mov     ecx, [rsp+4E0h+cchValueName]
0x180020875  inc     ecx
0x180020877  mov     eax, 2
0x18002087c  mul     rcx
0x18002087f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020886  cmovb   rax, rcx
0x18002088a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020891  mov     rcx, rax; unsigned __int64
0x180020894  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020899  mov     rcx, rax; void *
0x18002089c  mov     [rsi], rax
0x18002089f  test    rax, rax
0x1800208a2  jz      short loc_180020858
0x1800208a4  mov     r8d, [rsp+4E0h+cchValueName]
0x1800208a9  inc     r8d
0x1800208ac  add     r8, r8; Size
0x1800208af  lea     rdx, [rbp+3E0h+ValueName]; Src
0x1800208b6  call    memcpy_0
0x1800208bb  mov     eax, [rsp+4E0h+cbData]
0x1800208bf  mov     [rsi+10h], eax
0x1800208c2  mov     ecx, [rsp+4E0h+cbData]; unsigned __int64
0x1800208c6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800208cb  mov     [rsi+18h], rax
0x1800208cf  test    rax, rax
0x1800208d2  jz      short loc_180020858
0x1800208d4  mov     r8d, [rsp+4E0h+cbData]; Size
0x1800208d9  lea     rdx, [rbp+3E0h+Data]; Src
0x1800208dd  mov     rcx, rax; void *
0x1800208e0  call    memcpy_0
0x1800208e5  mov     dword ptr [rsi+8], 0Eh
0x1800208ec  mov     rdx, [rsi]
0x1800208ef  lea     rcx, [rsp+4E0h+var_488]
0x1800208f4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800208f9  lea     rcx, [r15+48h]
0x1800208fd  lea     rdx, [rsp+4E0h+var_488]
0x180020902  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@@5@@std@@QEAAAEAPEAUtagHELPER_ATTRIBUTE@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,tagHELPER_ATTRIBUTE *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x180020907  mov     [rax], rsi
0x18002090a  mov     rcx, [rsp+4E0h+var_488]
0x18002090f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020913  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020918  test    edi, edi
0x18002091a  jns     loc_180020A56
0x180020920  mov     rcx, rsi; struct tagHELPER_ATTRIBUTE *
0x180020923  call    ?FreeMatchValue@@YAXPEAUtagHELPER_ATTRIBUTE@@@Z; FreeMatchValue(tagHELPER_ATTRIBUTE *)
0x180020928  test    ebx, ebx
0x18002092a  js      loc_180020A56
0x180020930  mov     ebx, edi
0x180020932  jmp     loc_180020A56
0x180020937  mov     ecx, 90h; unsigned __int64
0x18002093c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180020941  mov     rsi, rax
0x180020944  test    rax, rax
0x180020947  jnz     short loc_180020951
0x180020949  mov     edi, r13d
0x18002094c  jmp     loc_180020A49
0x180020951  mov     ecx, 90h
0x180020956  mov     [rax], r12b
0x180020959  inc     rax
0x18002095c  sub     rcx, 1
0x180020960  jnz     short loc_180020956
0x180020962  mov     ecx, [rsp+4E0h+cchValueName]
0x180020966  inc     ecx
0x180020968  mov     eax, 2
0x18002096d  mul     rcx
0x180020970  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180020977  cmovb   rax, rcx
0x18002097b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020982  mov     rcx, rax; unsigned __int64
0x180020985  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002098a  mov     rcx, rax; void *
0x18002098d  mov     [rsi], rax
0x180020990  test    rax, rax
0x180020993  jz      short loc_180020949
0x180020995  mov     r8d, [rsp+4E0h+cchValueName]
0x18002099a  inc     r8d
0x18002099d  add     r8, r8; Size
0x1800209a0  lea     rdx, [rbp+3E0h+ValueName]; Src
0x1800209a7  call    memcpy_0
0x1800209ac  lea     rax, [rbp+3E0h+Data]
0x1800209b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800209b4  mov     rcx, r8
0x1800209b7  inc     rcx
0x1800209ba  cmp     [rax+rcx*2], r12w
0x1800209bf  jnz     short loc_1800209B7
0x1800209c1  inc     rcx
0x1800209c4  mov     eax, 2
0x1800209c9  mul     rcx
0x1800209cc  cmovb   rax, r8
0x1800209d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800209d7  mov     rcx, rax; unsigned __int64
0x1800209da  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800209df  mov     [rsi+10h], rax
0x1800209e3  test    rax, rax
0x1800209e6  jz      loc_180020949
0x1800209ec  lea     rcx, [rbp+3E0h+Data]
0x1800209f0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800209f4  inc     r8
0x1800209f7  cmp     [rcx+r8*2], r12w
0x1800209fc  jnz     short loc_1800209F4
0x1800209fe  lea     r8, ds:2[r8*2]; Size
0x180020a06  lea     rdx, [rbp+3E0h+Data]; Src
0x180020a0a  mov     rcx, rax; void *
0x180020a0d  call    memcpy_0
0x180020a12  mov     dword ptr [rsi+8], 0Ah
0x180020a19  mov     rdx, [rsi]
0x180020a1c  lea     rcx, [rsp+4E0h+var_480]
0x180020a21  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180020a26  lea     rcx, [r15+48h]
0x180020a2a  lea     rdx, [rsp+4E0h+var_480]
0x180020a2f  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@@5@@std@@QEAAAEAPEAUtagHELPER_ATTRIBUTE@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,tagHELPER_ATTRIBUTE *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x180020a34  mov     [rax], rsi
0x180020a37  mov     rcx, [rsp+4E0h+var_480]
0x180020a3c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020a40  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020a45  test    edi, edi
0x180020a47  jns     short loc_180020A56
0x180020a49  mov     rcx, rsi; struct tagHELPER_ATTRIBUTE *
0x180020a4c  call    ?FreeMatchValue@@YAXPEAUtagHELPER_ATTRIBUTE@@@Z; FreeMatchValue(tagHELPER_ATTRIBUTE *)
0x180020a51  test    ebx, ebx
0x180020a53  cmovns  ebx, edi
0x180020a56  inc     r14d
0x180020a59  jmp     loc_18002072D
0x180020a5e  cmp     eax, 103h
0x180020a63  jz      short loc_180020A76
0x180020a65  test    eax, eax
0x180020a67  jle     short loc_180020A71
0x180020a69  movzx   eax, ax
0x180020a6c  or      eax, 80070000h
0x180020a71  test    ebx, ebx
0x180020a73  cmovns  ebx, eax
0x180020a76  lea     rcx, [rsp+4E0h+hKey]; this
0x180020a7b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020a80  lea     rcx, [rsp+4E0h+hKey]; this
0x180020a85  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180020a8a  mov     eax, ebx
0x180020a8c  mov     rcx, [rbp+3E0h+var_40]
0x180020a93  xor     rcx, rsp; StackCookie
0x180020a96  call    __security_check_cookie
0x180020a9b  mov     rbx, [rsp+4E0h+arg_10]
0x180020aa3  add     rsp, 4B0h
0x180020aaa  pop     r15
0x180020aac  pop     r14
0x180020aae  pop     r13
0x180020ab0  pop     r12
0x180020ab2  pop     rdi
0x180020ab3  pop     rsi
0x180020ab4  pop     rbp
0x180020ab5  retn
```
