# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x1800195c0`
- end: `0x180019ba7`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `1511`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018eb4`

## callees

- `0x180001800`
- `0x180007ea4`
- `0x18000938c`
- `0x180009e70`
- `0x18000ab4c`
- `0x18000c6e4`
- `0x18000c980`
- `0x18000c9a8`
- `0x180010f74`
- `0x180011b9c`
- `0x180011bc0`
- `0x180014508`
- `0x180014dec`
- `0x1800151f8`
- `0x180015f74`
- `0x180016c10`
- `0x180018514`
- `0x180019030`
- `0x18001934c`
- `0x1800195c0`
- `0x18001aab8`
- `0x18001b364`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180019a82`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180019a82`

## string_xrefs

- `0x180019917`: `_NT_SYMBOL_PATH`
- `0x180019603`: `mscoree.dll`
- `0x18001961f`: `CLRCreateInstance`
- `0x1800198eb`: `XPERF_NGenPdbsPath`
- `0x180019ae7`: `XPERF_NGenPdbsCachePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  int Error; // ebx
  __int64 (__fastcall *v3)(GUID *, GUID *, __int64 *); // rax
  void (__fastcall ***v4)(_QWORD, GUID *, _QWORD *); // rcx
  unsigned __int16 v6; // di
  void (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // r9
  __int64 v8; // rcx
  unsigned __int16 v9; // bx
  __int64 v10; // rbx
  ATL::CStringData *v11; // rsi
  __int64 v12; // r8
  __int64 *v13; // r15
  int *v14; // r14
  __int64 v15; // rdi
  __int64 *v16; // r12
  int *v17; // rdi
  __int64 v18; // rbx
  __int64 *v19; // r14
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rbx
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  int *v25; // rdi
  __int64 v26; // rbx
  int v27; // edi
  __int64 v28; // rdx
  unsigned __int64 v29; // rax
  _QWORD *v30; // rdi
  __int64 v31; // rdx
  int *v32; // rcx
  int *v33; // rsi
  __int64 v34; // rbx
  void (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall ***v42)(_QWORD, GUID *, _QWORD *); // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v44[3]; // [rsp+78h] [rbp-88h] BYREF
  char v45; // [rsp+90h] [rbp-70h]
  _BYTE v46[80]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v47; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v48; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v49; // [rsp+108h] [rbp+8h]
  int v50; // [rsp+110h] [rbp+10h]
  __int64 v51; // [rsp+118h] [rbp+18h]
  int v52; // [rsp+120h] [rbp+20h]
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v43);
  v44[0] = 0;
  v44[1] = L"mscoree.dll";
  v44[2] = 0;
  v45 = 0;
  v47 = v44;
  *(_QWORD *)&v48 = "CLRCreateInstance";
  *((_QWORD *)&v48 + 1) = 0;
  LOBYTE(v49) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v47) )
  {
    Error = -2147467259;
LABEL_7:
    Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(v44);
    v4 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v43;
LABEL_8:
    ATL::CStringData::Release((ATL::CStringData *)(v4 - 3));
    return (unsigned int)Error;
  }
  v41 = 0;
  v3 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v47);
  Error = v3(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v41);
  if ( Error < 0 )
  {
LABEL_6:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    goto LABEL_7;
  }
  v36 = 0;
  Error = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 40LL))(v41, &v36);
  if ( Error < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
    goto LABEL_6;
  }
  v35 = 0;
  v39 = 0;
  v6 = 0;
  while ( (*(int (__fastcall **)(__int64, __int64, void (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v36 + 24LL))(
            v36,
            1,
            &v35,
            &v39) >= 0
       && v39 == 1 )
  {
    v7 = v35;
    v35 = 0;
    v42 = v7;
    v8 = 0;
    v38 = 0;
    if ( v7 )
    {
      (**v7)(v7, &GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891, &v38);
      v8 = v38;
    }
    if ( v8 )
    {
      v40 = 30;
      if ( (*(int (__fastcall **)(__int64, _QWORD **, unsigned int *))(*(_QWORD *)v8 + 24LL))(v8, &v47, &v40) >= 0
        && v40 >= 3
        && (((_WORD)v47 - 86) & 0xFFDF) == 0 )
      {
        v9 = WORD1(v47);
        if ( (unsigned __int16)(WORD1(v47) - 52) <= 5u && WORD2(v47) == 46 && WORD1(v47) > v6 )
        {
          v37 = 260;
          if ( (*(int (__fastcall **)(__int64, WCHAR *, int *))(*(_QWORD *)v38 + 32LL))(v38, Buffer, &v37) >= 0 )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v43, Buffer);
            v6 = v9;
          }
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(v44);
  v10 = v43;
  v11 = (ATL::CStringData *)(v43 - 24);
  v12 = *(unsigned int *)(v43 - 24 + 8);
  if ( !(_DWORD)v12 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
    return 2147500037LL;
  }
  v13 = (__int64 *)((char *)this + 40);
  v14 = (int *)(*((_QWORD *)this + 5) - 24LL);
  if ( v11 != (ATL::CStringData *)v14 )
  {
    if ( v14[4] >= 0 && *(_QWORD *)v11 == *(_QWORD *)v14 )
    {
      v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v43 - 24);
      ATL::CStringData::Release((ATL::CStringData *)v14);
      *v13 = v15 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 40, v43, v12);
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace((char *)this + 40);
  v16 = (__int64 *)((char *)this + 48);
  v17 = (int *)(*((_QWORD *)this + 6) - 24LL);
  if ( v11 != (ATL::CStringData *)v17 )
  {
    if ( v17[4] >= 0 && *(_QWORD *)v11 == *(_QWORD *)v17 )
    {
      v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v11);
      ATL::CStringData::Release((ATL::CStringData *)v17);
      *v16 = v18 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 48, v10, *(unsigned int *)(v10 - 16));
    }
  }
  ATL::CStringData::Release(v11);
  v19 = (__int64 *)((char *)this + 56);
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 56,
                        L"XPERF_NGenPdbsPath")
    || !*(_DWORD *)(*v19 - 16) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v35);
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v35,
                         L"_NT_SYMBOL_PATH") )
    {
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v52 = 1;
      LODWORD(v47) = 0;
      v20 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v47);
      if ( v20 )
      {
        Error = -2147418113;
        if ( v20 == 1 )
          Error = -2147024882;
        ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(&v48);
        goto LABEL_69;
      }
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v46);
      v37 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v36);
      v22 = v36;
      while ( 1 )
      {
        v23 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                           &v35,
                           &v43,
                           v21,
                           &v37);
        v24 = (_QWORD *)(v23 - 24);
        v25 = (int *)(v22 - 24);
        if ( v23 - 24 != v22 - 24 )
        {
          if ( v25[4] >= 0 && *v24 == *(_QWORD *)v25 )
          {
            v26 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v24);
            ATL::CStringData::Release((ATL::CStringData *)v25);
            v22 = v26 + 24;
            v36 = v22;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v36, v23, *(unsigned int *)(v23 - 16));
            v22 = v36;
          }
        }
        v27 = *(_DWORD *)(v22 - 16);
        ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
        if ( !v27 )
          break;
        if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v47, v22, v46, 0) )
        {
          v43 = 0;
          ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(v46, v28, &v43);
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            (char *)this + 56,
            v43,
            (__int64)(*((_QWORD *)&v43 + 1) - v43) >> 1);
          break;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v46);
      ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(&v48);
    }
    if ( !*(_DWORD *)(*v19 - 16) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        Error = ATL::AtlHresultFromLastError();
LABEL_69:
        v4 = v35;
        goto LABEL_8;
      }
      v29 = -1;
      do
        ++v29;
      while ( Buffer[v29] );
      if ( v29 < 2 || Buffer[1] != 58 )
      {
        Error = -2147418113;
        goto LABEL_69;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 56,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 3));
  }
  v30 = (_QWORD *)((char *)this + 64);
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 64,
                        L"XPERF_NGenPdbsCachePath")
    || !*(_DWORD *)(*v30 - 16LL) )
  {
    v31 = *v19;
    v32 = (int *)(*v19 - 24);
    v33 = (int *)(*v30 - 24LL);
    if ( v32 != v33 )
    {
      if ( v33[4] >= 0 && *(_QWORD *)v32 == *(_QWORD *)v33 )
      {
        v34 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v32);
        ATL::CStringData::Release((ATL::CStringData *)v33);
        *v30 = v34 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 64, v31, *(unsigned int *)(v31 - 16));
      }
    }
  }
  *((_BYTE *)this + 32) = 1;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    McTemplateU0zzzz_EventWriteTransfer((_DWORD)v32, v31, *v19, *v30, *v13, *v16);
  return 0;
}

```

## disassembly

```asm
0x1800195c0  push    rbp
0x1800195c2  push    rbx
0x1800195c3  push    rsi
0x1800195c4  push    rdi
0x1800195c5  push    r12
0x1800195c7  push    r13
0x1800195c9  push    r14
0x1800195cb  push    r15
0x1800195cd  lea     rbp, [rsp-258h]
0x1800195d5  sub     rsp, 358h
0x1800195dc  mov     rax, cs:__security_cookie
0x1800195e3  xor     rax, rsp
0x1800195e6  mov     [rbp+290h+var_50], rax
0x1800195ed  mov     r13, rcx
0x1800195f0  lea     rcx, [rsp+390h+var_328]
0x1800195f5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800195fa  nop
0x1800195fb  xor     r12d, r12d
0x1800195fe  mov     [rsp+390h+var_318], r12
0x180019603  lea     rax, aMscoreeDll; "mscoree.dll"
0x18001960a  mov     [rbp+290h+var_310], rax
0x18001960e  mov     [rbp+290h+var_308], r12
0x180019612  mov     [rbp+290h+var_300], r12b
0x180019616  lea     rax, [rsp+390h+var_318]
0x18001961b  mov     [rbp+290h+var_2A0], rax
0x18001961f  lea     rax, aClrcreateinsta; "CLRCreateInstance"
0x180019626  mov     qword ptr [rbp+290h+var_298], rax
0x18001962a  mov     qword ptr [rbp+290h+var_298+8], r12
0x18001962e  mov     byte ptr [rbp+290h+var_288], r12b
0x180019632  lea     rcx, [rbp+290h+var_2A0]
0x180019636  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001963b  test    rax, rax
0x18001963e  jnz     short loc_180019647
0x180019640  mov     ebx, 80004005h
0x180019645  jmp     short loc_1800196AA
0x180019647  mov     [rsp+390h+var_338], r12
0x18001964c  lea     rcx, [rbp+290h+var_2A0]
0x180019650  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180019655  lea     r8, [rsp+390h+var_338]
0x18001965a  lea     rdx, IID_ICLRMetaHost
0x180019661  lea     rcx, CLSID_CLRMetaHost
0x180019668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001966d  mov     ebx, eax
0x18001966f  test    eax, eax
0x180019671  js      short loc_18001969F
0x180019673  mov     [rsp+390h+var_358], r12
0x180019678  mov     rcx, [rsp+390h+var_338]
0x18001967d  mov     rax, [rcx]
0x180019680  lea     rdx, [rsp+390h+var_358]
0x180019685  mov     rax, [rax+28h]
0x180019689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001968e  mov     ebx, eax
0x180019690  test    eax, eax
0x180019692  jns     short loc_1800196CA
0x180019694  lea     rcx, [rsp+390h+var_358]
0x180019699  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001969e  nop
0x18001969f  lea     rcx, [rsp+390h+var_338]
0x1800196a4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800196a9  nop
0x1800196aa  lea     rcx, [rsp+390h+var_318]
0x1800196af  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x1800196b4  nop
0x1800196b5  mov     rcx, qword ptr [rsp+390h+var_328]
0x1800196ba  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800196be  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800196c3  mov     eax, ebx
0x1800196c5  jmp     loc_180019B83
0x1800196ca  mov     [rsp+390h+var_360], r12
0x1800196cf  mov     [rsp+390h+var_340], r12d
0x1800196d4  mov     edi, r12d
0x1800196d7  mov     rcx, [rsp+390h+var_358]
0x1800196dc  mov     rax, [rcx]
0x1800196df  lea     r9, [rsp+390h+var_340]
0x1800196e4  lea     r8, [rsp+390h+var_360]
0x1800196e9  mov     edx, 1
0x1800196ee  mov     rax, [rax+18h]
0x1800196f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f7  test    eax, eax
0x1800196f9  js      loc_1800197F7
0x1800196ff  cmp     [rsp+390h+var_340], 1
0x180019704  jnz     loc_1800197F7
0x18001970a  mov     r9, [rsp+390h+var_360]
0x18001970f  mov     [rsp+390h+var_360], r12
0x180019714  mov     [rsp+390h+var_330], r9
0x180019719  mov     rcx, r12
0x18001971c  mov     [rsp+390h+var_348], rcx
0x180019721  test    r9, r9
0x180019724  jz      short loc_180019745
0x180019726  mov     rax, [r9]
0x180019729  lea     r8, [rsp+390h+var_348]
0x18001972e  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x180019735  mov     rcx, r9
0x180019738  mov     rax, [rax]
0x18001973b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019740  mov     rcx, [rsp+390h+var_348]
0x180019745  test    rcx, rcx
0x180019748  jnz     short loc_180019764
0x18001974a  lea     rcx, [rsp+390h+var_348]
0x18001974f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180019754  nop
0x180019755  lea     rcx, [rsp+390h+var_330]
0x18001975a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001975f  jmp     loc_1800196D7
0x180019764  mov     [rsp+390h+var_33C], 1Eh
0x18001976c  mov     rax, [rcx]
0x18001976f  lea     r8, [rsp+390h+var_33C]
0x180019774  lea     rdx, [rbp+290h+var_2A0]
0x180019778  mov     rax, [rax+18h]
0x18001977c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019781  test    eax, eax
0x180019783  js      short loc_18001974A
0x180019785  cmp     [rsp+390h+var_33C], 3
0x18001978a  jb      short loc_18001974A
0x18001978c  movzx   eax, word ptr [rbp+290h+var_2A0]
0x180019790  sub     ax, 56h ; 'V'
0x180019794  mov     ecx, 0FFDFh
0x180019799  test    cx, ax
0x18001979c  jnz     short loc_18001974A
0x18001979e  movzx   ebx, word ptr [rbp+290h+var_2A0+2]
0x1800197a2  lea     eax, [rbx-34h]
0x1800197a5  cmp     ax, 5
0x1800197a9  ja      short loc_18001974A
0x1800197ab  cmp     word ptr [rbp+290h+var_2A0+4], 2Eh ; '.'
0x1800197b0  jnz     short loc_18001974A
0x1800197b2  cmp     bx, di
0x1800197b5  jbe     short loc_18001974A
0x1800197b7  mov     [rsp+390h+var_350], 104h
0x1800197bf  mov     rcx, [rsp+390h+var_348]
0x1800197c4  mov     rax, [rcx]
0x1800197c7  lea     r8, [rsp+390h+var_350]
0x1800197cc  lea     rdx, [rbp+290h+Buffer]
0x1800197d0  mov     rax, [rax+20h]
0x1800197d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197d9  test    eax, eax
0x1800197db  js      loc_18001974A
0x1800197e1  lea     rdx, [rbp+290h+Buffer]
0x1800197e5  lea     rcx, [rsp+390h+var_328]
0x1800197ea  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800197ef  movzx   edi, bx
0x1800197f2  jmp     loc_18001974A
0x1800197f7  lea     rcx, [rsp+390h+var_360]
0x1800197fc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180019801  nop
0x180019802  lea     rcx, [rsp+390h+var_358]
0x180019807  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001980c  nop
0x18001980d  lea     rcx, [rsp+390h+var_338]
0x180019812  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180019817  nop
0x180019818  lea     rcx, [rsp+390h+var_318]
0x18001981d  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x180019822  mov     rbx, qword ptr [rsp+390h+var_328]
0x180019827  lea     rsi, [rbx-18h]
0x18001982b  mov     r8d, [rsi+8]
0x18001982f  test    r8d, r8d
0x180019832  jnz     short loc_180019846
0x180019834  mov     rcx, rsi; this
0x180019837  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001983c  mov     eax, 80004005h
0x180019841  jmp     loc_180019B83
0x180019846  lea     r15, [r13+28h]
0x18001984a  mov     r14, [r15]
0x18001984d  add     r14, 0FFFFFFFFFFFFFFE8h
0x180019851  cmp     rsi, r14
0x180019854  jz      short loc_18001988B
0x180019856  cmp     [r14+10h], r12d
0x18001985a  jl      short loc_180019880
0x18001985c  mov     rax, [r14]
0x18001985f  cmp     [rsi], rax
0x180019862  jnz     short loc_180019880
0x180019864  mov     rcx, rsi
0x180019867  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001986c  mov     rdi, rax
0x18001986f  mov     rcx, r14; this
0x180019872  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019877  lea     rax, [rdi+18h]
0x18001987b  mov     [r15], rax
0x18001987e  jmp     short loc_18001988B
0x180019880  mov     rdx, rbx
0x180019883  mov     rcx, r15
0x180019886  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001988b  mov     rcx, r15
0x18001988e  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180019893  lea     r12, [r13+30h]
0x180019897  mov     rdi, [r12]
0x18001989b  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18001989f  cmp     rsi, rdi
0x1800198a2  jz      short loc_1800198DF
0x1800198a4  cmp     dword ptr [rdi+10h], 0
0x1800198a8  jl      short loc_1800198CF
0x1800198aa  mov     rax, [rdi]
0x1800198ad  cmp     [rsi], rax
0x1800198b0  jnz     short loc_1800198CF
0x1800198b2  mov     rcx, rsi
0x1800198b5  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800198ba  mov     rbx, rax
0x1800198bd  mov     rcx, rdi; this
0x1800198c0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800198c5  lea     rax, [rbx+18h]
0x1800198c9  mov     [r12], rax
0x1800198cd  jmp     short loc_1800198DF
0x1800198cf  mov     r8d, [rbx-10h]
0x1800198d3  mov     rdx, rbx
0x1800198d6  mov     rcx, r12
0x1800198d9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800198de  nop
0x1800198df  mov     rcx, rsi; this
0x1800198e2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800198e7  lea     r14, [r13+38h]
0x1800198eb  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x1800198f2  mov     rcx, r14
0x1800198f5  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800198fa  xor     esi, esi
0x1800198fc  test    eax, eax
0x1800198fe  jz      short loc_18001990C
0x180019900  mov     rax, [r14]
0x180019903  cmp     [rax-10h], esi
0x180019906  jnz     loc_180019AE3
0x18001990c  lea     rcx, [rsp+390h+var_360]
0x180019911  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180019916  nop
0x180019917  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x18001991e  lea     rcx, [rsp+390h+var_360]
0x180019923  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180019928  test    eax, eax
0x18001992a  jz      loc_180019A71
0x180019930  xorps   xmm0, xmm0
0x180019933  movdqu  [rbp+290h+var_298], xmm0
0x180019938  mov     [rbp+290h+var_288], rsi
0x18001993c  mov     [rbp+290h+var_280], esi
0x18001993f  mov     [rbp+290h+var_278], rsi
0x180019943  mov     [rbp+290h+var_270], 1
0x18001994a  mov     dword ptr [rbp+290h+var_2A0], esi
0x18001994d  lea     rcx, [rbp+290h+var_2A0]
0x180019951  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x180019956  test    eax, eax
0x180019958  jz      short loc_180019977
0x18001995a  cmp     eax, 1
0x18001995d  mov     ebx, 8000FFFFh
0x180019962  jnz     short loc_180019969
0x180019964  mov     ebx, 8007000Eh
0x180019969  lea     rcx, [rbp+290h+var_298]
0x18001996d  call    ??1?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(void)
0x180019972  jmp     loc_180019B41
0x180019977  lea     rcx, [rbp+290h+var_2F0]
0x18001997b  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x180019980  nop
0x180019981  mov     [rsp+390h+var_350], esi
0x180019985  lea     rcx, [rsp+390h+var_358]
0x18001998a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001998f  nop
0x180019990  mov     rbx, [rsp+390h+var_358]
0x180019995  lea     r9, [rsp+390h+var_350]
0x18001999a  lea     rdx, [rsp+390h+var_328]
0x18001999f  lea     rcx, [rsp+390h+var_360]
0x1800199a4  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x1800199a9  nop
0x1800199aa  mov     rdx, [rax]
0x1800199ad  lea     rcx, [rdx-18h]
0x1800199b1  lea     rdi, [rbx-18h]
0x1800199b5  cmp     rcx, rdi
0x1800199b8  jz      short loc_1800199F5
0x1800199ba  cmp     [rdi+10h], esi
0x1800199bd  jl      short loc_1800199E2
0x1800199bf  mov     rax, [rdi]
0x1800199c2  cmp     [rcx], rax
0x1800199c5  jnz     short loc_1800199E2
0x1800199c7  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800199cc  mov     rbx, rax
0x1800199cf  mov     rcx, rdi; this
0x1800199d2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800199d7  add     rbx, 18h
0x1800199db  mov     [rsp+390h+var_358], rbx
0x1800199e0  jmp     short loc_1800199F5
0x1800199e2  mov     r8d, [rdx-10h]
0x1800199e6  lea     rcx, [rsp+390h+var_358]
0x1800199eb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800199f0  mov     rbx, [rsp+390h+var_358]
0x1800199f5  mov     edi, [rbx-10h]
0x1800199f8  mov     rcx, qword ptr [rsp+390h+var_328]
0x1800199fd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180019a01  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019a06  test    edi, edi
0x180019a08  jz      short loc_180019A54
0x180019a0a  xor     r9d, r9d
0x180019a0d  lea     r8, [rbp+290h+var_2F0]
0x180019a11  mov     rdx, rbx
0x180019a14  lea     rcx, [rbp+290h+var_2A0]
0x180019a18  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x180019a1d  test    eax, eax
0x180019a1f  jz      loc_180019995
0x180019a25  xorps   xmm0, xmm0
0x180019a28  movups  [rsp+390h+var_328], xmm0
0x180019a2d  lea     r8, [rsp+390h+var_328]
0x180019a32  lea     rcx, [rbp+290h+var_2F0]
0x180019a36  call    ?GetMatch@?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAXIPEAUMatchGroup@12@@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(uint,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::MatchGroup *)
0x180019a3b  mov     r8, qword ptr [rsp+390h+var_328+8]
0x180019a40  mov     rdx, qword ptr [rsp+390h+var_328]
0x180019a45  sub     r8, rdx
  ... truncated ...
```
