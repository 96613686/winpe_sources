# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x180018bac`
- end: `0x18001918c`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `1504`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800185b0`

## callees

- `0x1800017e0`
- `0x180007b34`
- `0x180008f10`
- `0x180009994`
- `0x18000a5d4`
- `0x18000c120`
- `0x18000c3b0`
- `0x18000c3d8`
- `0x1800107ec`
- `0x1800113ec`
- `0x18001140c`
- `0x180013d00`
- `0x18001457c`
- `0x18001495c`
- `0x1800155d8`
- `0x180016230`
- `0x180017b04`
- `0x18001872c`
- `0x180018998`
- `0x180018bac`
- `0x18001a038`
- `0x18001a8b4`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001906e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001906e`

## string_xrefs

- `0x180018f03`: `_NT_SYMBOL_PATH`
- `0x180018bef`: `mscoree.dll`
- `0x180018c0b`: `CLRCreateInstance`
- `0x180018ed7`: `XPERF_NGenPdbsPath`
- `0x1800190cd`: `XPERF_NGenPdbsCachePath`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  signed int Error; // ebx
  FARPROC v3; // rax
  __int64 v4; // rcx
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
  void (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
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

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v43);
  v44[0] = 0;
  v44[1] = L"mscoree.dll";
  v44[2] = 0;
  v45 = 0;
  v47 = v44;
  *(_QWORD *)&v48 = "CLRCreateInstance";
  *((_QWORD *)&v48 + 1) = 0;
  LOBYTE(v49) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)&v47) )
  {
    Error = -2147467259;
LABEL_7:
    Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(v44);
    v4 = v43;
LABEL_8:
    ATL::CStringData::Release((ATL::CStringData *)(v4 - 24));
    return (unsigned int)Error;
  }
  v41 = 0;
  v3 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64)&v47);
  Error = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))v3)(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v41);
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
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v42);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v35);
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
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v35);
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
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v36);
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
        v4 = (__int64)v35;
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
0x180018bac  push    rbp
0x180018bae  push    rbx
0x180018baf  push    rsi
0x180018bb0  push    rdi
0x180018bb1  push    r12
0x180018bb3  push    r13
0x180018bb5  push    r14
0x180018bb7  push    r15
0x180018bb9  lea     rbp, [rsp-258h]
0x180018bc1  sub     rsp, 358h
0x180018bc8  mov     rax, cs:__security_cookie
0x180018bcf  xor     rax, rsp
0x180018bd2  mov     [rbp+290h+var_50], rax
0x180018bd9  mov     r13, rcx
0x180018bdc  lea     rcx, [rsp+390h+var_328]
0x180018be1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018be6  nop
0x180018be7  xor     r12d, r12d
0x180018bea  mov     [rsp+390h+var_318], r12
0x180018bef  lea     rax, aMscoreeDll; "mscoree.dll"
0x180018bf6  mov     [rbp+290h+var_310], rax
0x180018bfa  mov     [rbp+290h+var_308], r12
0x180018bfe  mov     [rbp+290h+var_300], r12b
0x180018c02  lea     rax, [rsp+390h+var_318]
0x180018c07  mov     [rbp+290h+var_2A0], rax
0x180018c0b  lea     rax, aClrcreateinsta; "CLRCreateInstance"
0x180018c12  mov     qword ptr [rbp+290h+var_298], rax
0x180018c16  mov     qword ptr [rbp+290h+var_298+8], r12
0x180018c1a  mov     byte ptr [rbp+290h+var_288], r12b
0x180018c1e  lea     rcx, [rbp+290h+var_2A0]
0x180018c22  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180018c27  test    rax, rax
0x180018c2a  jnz     short loc_180018C33
0x180018c2c  mov     ebx, 80004005h
0x180018c31  jmp     short loc_180018C96
0x180018c33  mov     [rsp+390h+var_338], r12
0x180018c38  lea     rcx, [rbp+290h+var_2A0]
0x180018c3c  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180018c41  lea     r8, [rsp+390h+var_338]
0x180018c46  lea     rdx, IID_ICLRMetaHost
0x180018c4d  lea     rcx, CLSID_CLRMetaHost
0x180018c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c59  mov     ebx, eax
0x180018c5b  test    eax, eax
0x180018c5d  js      short loc_180018C8B
0x180018c5f  mov     [rsp+390h+var_358], r12
0x180018c64  mov     rcx, [rsp+390h+var_338]
0x180018c69  mov     rax, [rcx]
0x180018c6c  lea     rdx, [rsp+390h+var_358]
0x180018c71  mov     rax, [rax+28h]
0x180018c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c7a  mov     ebx, eax
0x180018c7c  test    eax, eax
0x180018c7e  jns     short loc_180018CB6
0x180018c80  lea     rcx, [rsp+390h+var_358]
0x180018c85  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018c8a  nop
0x180018c8b  lea     rcx, [rsp+390h+var_338]
0x180018c90  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018c95  nop
0x180018c96  lea     rcx, [rsp+390h+var_318]
0x180018c9b  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x180018ca0  nop
0x180018ca1  mov     rcx, qword ptr [rsp+390h+var_328]
0x180018ca6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018caa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018caf  mov     eax, ebx
0x180018cb1  jmp     loc_180019169
0x180018cb6  mov     [rsp+390h+var_360], r12
0x180018cbb  mov     [rsp+390h+var_340], r12d
0x180018cc0  mov     edi, r12d
0x180018cc3  mov     rcx, [rsp+390h+var_358]
0x180018cc8  mov     rax, [rcx]
0x180018ccb  lea     r9, [rsp+390h+var_340]
0x180018cd0  lea     r8, [rsp+390h+var_360]
0x180018cd5  mov     edx, 1
0x180018cda  mov     rax, [rax+18h]
0x180018cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ce3  test    eax, eax
0x180018ce5  js      loc_180018DE3
0x180018ceb  cmp     [rsp+390h+var_340], 1
0x180018cf0  jnz     loc_180018DE3
0x180018cf6  mov     r9, [rsp+390h+var_360]
0x180018cfb  mov     [rsp+390h+var_360], r12
0x180018d00  mov     [rsp+390h+var_330], r9
0x180018d05  mov     rcx, r12
0x180018d08  mov     [rsp+390h+var_348], rcx
0x180018d0d  test    r9, r9
0x180018d10  jz      short loc_180018D31
0x180018d12  mov     rax, [r9]
0x180018d15  lea     r8, [rsp+390h+var_348]
0x180018d1a  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x180018d21  mov     rcx, r9
0x180018d24  mov     rax, [rax]
0x180018d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d2c  mov     rcx, [rsp+390h+var_348]
0x180018d31  test    rcx, rcx
0x180018d34  jnz     short loc_180018D50
0x180018d36  lea     rcx, [rsp+390h+var_348]
0x180018d3b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018d40  nop
0x180018d41  lea     rcx, [rsp+390h+var_330]
0x180018d46  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018d4b  jmp     loc_180018CC3
0x180018d50  mov     [rsp+390h+var_33C], 1Eh
0x180018d58  mov     rax, [rcx]
0x180018d5b  lea     r8, [rsp+390h+var_33C]
0x180018d60  lea     rdx, [rbp+290h+var_2A0]
0x180018d64  mov     rax, [rax+18h]
0x180018d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d6d  test    eax, eax
0x180018d6f  js      short loc_180018D36
0x180018d71  cmp     [rsp+390h+var_33C], 3
0x180018d76  jb      short loc_180018D36
0x180018d78  movzx   eax, word ptr [rbp+290h+var_2A0]
0x180018d7c  sub     ax, 56h ; 'V'
0x180018d80  mov     ecx, 0FFDFh
0x180018d85  test    cx, ax
0x180018d88  jnz     short loc_180018D36
0x180018d8a  movzx   ebx, word ptr [rbp+290h+var_2A0+2]
0x180018d8e  lea     eax, [rbx-34h]
0x180018d91  cmp     ax, 5
0x180018d95  ja      short loc_180018D36
0x180018d97  cmp     word ptr [rbp+290h+var_2A0+4], 2Eh ; '.'
0x180018d9c  jnz     short loc_180018D36
0x180018d9e  cmp     bx, di
0x180018da1  jbe     short loc_180018D36
0x180018da3  mov     [rsp+390h+var_350], 104h
0x180018dab  mov     rcx, [rsp+390h+var_348]
0x180018db0  mov     rax, [rcx]
0x180018db3  lea     r8, [rsp+390h+var_350]
0x180018db8  lea     rdx, [rbp+290h+Buffer]
0x180018dbc  mov     rax, [rax+20h]
0x180018dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dc5  test    eax, eax
0x180018dc7  js      loc_180018D36
0x180018dcd  lea     rdx, [rbp+290h+Buffer]
0x180018dd1  lea     rcx, [rsp+390h+var_328]
0x180018dd6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180018ddb  movzx   edi, bx
0x180018dde  jmp     loc_180018D36
0x180018de3  lea     rcx, [rsp+390h+var_360]
0x180018de8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018ded  nop
0x180018dee  lea     rcx, [rsp+390h+var_358]
0x180018df3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018df8  nop
0x180018df9  lea     rcx, [rsp+390h+var_338]
0x180018dfe  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018e03  nop
0x180018e04  lea     rcx, [rsp+390h+var_318]
0x180018e09  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x180018e0e  mov     rbx, qword ptr [rsp+390h+var_328]
0x180018e13  lea     rsi, [rbx-18h]
0x180018e17  mov     r8d, [rsi+8]
0x180018e1b  test    r8d, r8d
0x180018e1e  jnz     short loc_180018E32
0x180018e20  mov     rcx, rsi; this
0x180018e23  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018e28  mov     eax, 80004005h
0x180018e2d  jmp     loc_180019169
0x180018e32  lea     r15, [r13+28h]
0x180018e36  mov     r14, [r15]
0x180018e39  add     r14, 0FFFFFFFFFFFFFFE8h
0x180018e3d  cmp     rsi, r14
0x180018e40  jz      short loc_180018E77
0x180018e42  cmp     [r14+10h], r12d
0x180018e46  jl      short loc_180018E6C
0x180018e48  mov     rax, [r14]
0x180018e4b  cmp     [rsi], rax
0x180018e4e  jnz     short loc_180018E6C
0x180018e50  mov     rcx, rsi
0x180018e53  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180018e58  mov     rdi, rax
0x180018e5b  mov     rcx, r14; this
0x180018e5e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018e63  lea     rax, [rdi+18h]
0x180018e67  mov     [r15], rax
0x180018e6a  jmp     short loc_180018E77
0x180018e6c  mov     rdx, rbx
0x180018e6f  mov     rcx, r15
0x180018e72  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180018e77  mov     rcx, r15
0x180018e7a  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180018e7f  lea     r12, [r13+30h]
0x180018e83  mov     rdi, [r12]
0x180018e87  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180018e8b  cmp     rsi, rdi
0x180018e8e  jz      short loc_180018ECB
0x180018e90  cmp     dword ptr [rdi+10h], 0
0x180018e94  jl      short loc_180018EBB
0x180018e96  mov     rax, [rdi]
0x180018e99  cmp     [rsi], rax
0x180018e9c  jnz     short loc_180018EBB
0x180018e9e  mov     rcx, rsi
0x180018ea1  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180018ea6  mov     rbx, rax
0x180018ea9  mov     rcx, rdi; this
0x180018eac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018eb1  lea     rax, [rbx+18h]
0x180018eb5  mov     [r12], rax
0x180018eb9  jmp     short loc_180018ECB
0x180018ebb  mov     r8d, [rbx-10h]
0x180018ebf  mov     rdx, rbx
0x180018ec2  mov     rcx, r12
0x180018ec5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180018eca  nop
0x180018ecb  mov     rcx, rsi; this
0x180018ece  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018ed3  lea     r14, [r13+38h]
0x180018ed7  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x180018ede  mov     rcx, r14
0x180018ee1  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180018ee6  xor     esi, esi
0x180018ee8  test    eax, eax
0x180018eea  jz      short loc_180018EF8
0x180018eec  mov     rax, [r14]
0x180018eef  cmp     [rax-10h], esi
0x180018ef2  jnz     loc_1800190C9
0x180018ef8  lea     rcx, [rsp+390h+var_360]
0x180018efd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018f02  nop
0x180018f03  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x180018f0a  lea     rcx, [rsp+390h+var_360]
0x180018f0f  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180018f14  test    eax, eax
0x180018f16  jz      loc_18001905D
0x180018f1c  xorps   xmm0, xmm0
0x180018f1f  movdqu  [rbp+290h+var_298], xmm0
0x180018f24  mov     [rbp+290h+var_288], rsi
0x180018f28  mov     [rbp+290h+var_280], esi
0x180018f2b  mov     [rbp+290h+var_278], rsi
0x180018f2f  mov     [rbp+290h+var_270], 1
0x180018f36  mov     dword ptr [rbp+290h+var_2A0], esi
0x180018f39  lea     rcx, [rbp+290h+var_2A0]
0x180018f3d  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x180018f42  test    eax, eax
0x180018f44  jz      short loc_180018F63
0x180018f46  cmp     eax, 1
0x180018f49  mov     ebx, 8000FFFFh
0x180018f4e  jnz     short loc_180018F55
0x180018f50  mov     ebx, 8007000Eh
0x180018f55  lea     rcx, [rbp+290h+var_298]
0x180018f59  call    ??1?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(void)
0x180018f5e  jmp     loc_180019127
0x180018f63  lea     rcx, [rbp+290h+var_2F0]
0x180018f67  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x180018f6c  nop
0x180018f6d  mov     [rsp+390h+var_350], esi
0x180018f71  lea     rcx, [rsp+390h+var_358]
0x180018f76  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018f7b  nop
0x180018f7c  mov     rbx, [rsp+390h+var_358]
0x180018f81  lea     r9, [rsp+390h+var_350]
0x180018f86  lea     rdx, [rsp+390h+var_328]
0x180018f8b  lea     rcx, [rsp+390h+var_360]
0x180018f90  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x180018f95  nop
0x180018f96  mov     rdx, [rax]
0x180018f99  lea     rcx, [rdx-18h]
0x180018f9d  lea     rdi, [rbx-18h]
0x180018fa1  cmp     rcx, rdi
0x180018fa4  jz      short loc_180018FE1
0x180018fa6  cmp     [rdi+10h], esi
0x180018fa9  jl      short loc_180018FCE
0x180018fab  mov     rax, [rdi]
0x180018fae  cmp     [rcx], rax
0x180018fb1  jnz     short loc_180018FCE
0x180018fb3  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180018fb8  mov     rbx, rax
0x180018fbb  mov     rcx, rdi; this
0x180018fbe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018fc3  add     rbx, 18h
0x180018fc7  mov     [rsp+390h+var_358], rbx
0x180018fcc  jmp     short loc_180018FE1
0x180018fce  mov     r8d, [rdx-10h]
0x180018fd2  lea     rcx, [rsp+390h+var_358]
0x180018fd7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180018fdc  mov     rbx, [rsp+390h+var_358]
0x180018fe1  mov     edi, [rbx-10h]
0x180018fe4  mov     rcx, qword ptr [rsp+390h+var_328]
0x180018fe9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180018fed  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180018ff2  test    edi, edi
0x180018ff4  jz      short loc_180019040
0x180018ff6  xor     r9d, r9d
0x180018ff9  lea     r8, [rbp+290h+var_2F0]
0x180018ffd  mov     rdx, rbx
0x180019000  lea     rcx, [rbp+290h+var_2A0]
0x180019004  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x180019009  test    eax, eax
0x18001900b  jz      loc_180018F81
0x180019011  xorps   xmm0, xmm0
0x180019014  movups  [rsp+390h+var_328], xmm0
0x180019019  lea     r8, [rsp+390h+var_328]
0x18001901e  lea     rcx, [rbp+290h+var_2F0]
0x180019022  call    ?GetMatch@?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAXIPEAUMatchGroup@12@@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(uint,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::MatchGroup *)
0x180019027  mov     r8, qword ptr [rsp+390h+var_328+8]
0x18001902c  mov     rdx, qword ptr [rsp+390h+var_328]
0x180019031  sub     r8, rdx
  ... truncated ...
```
