# CClassCache::CDllPathEntry::Create(ushort const *,ulong,bool,bool,bool,bool,IImmediateCallback *,CClassCache::CDllPathEntry * &)

- ea: `0x18002c808`
- end: `0x18002ccef`
- name: `?Create@CDllPathEntry@CClassCache@@SAJPEBGK_N111PEAUIImmediateCallback@@AEAPEAV12@@Z`
- size: `1255`
- prototype: `__int64 __fastcall(wchar_t *dllPath, unsigned int dllPathHash, bool isSixteenBit, bool isOle32, bool delayedUnload, bool makeValidInCurrentApartment, IImmediateCallback *virtualizationCallback, CClassCache::CDllPathEntry **pDPE)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a8e0`
- `0x1801739e8`
- `0x1801d3be4`

## callees

- `0x18000712c`
- `0x180020e14`
- `0x18002b3b8`
- `0x18002c0b4`
- `0x18002c808`
- `0x18002ccf8`
- `0x18002d330`
- `0x18002e040`
- `0x18002e490`
- `0x18003a8bc`
- `0x180058e20`
- `0x180179024`
- `0x18019a5ea`
- `0x18019a654`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002ccd9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002ccd9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c97e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c97e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c9ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c9ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c876`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c88a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c8a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c876`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c88a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c8a7`

## string_xrefs

- `0x18002c86f`: `DllGetClassObject`
- `0x18002c880`: `DllGetActivationFactory`
- `0x18002c8a0`: `DllCanUnloadNow`
- `0x18002c9c2`: `onecore\com\combase\objact\dllcache.cxx`
- `0x18002cb49`: `onecore\com\combase\objact\dllcache.cxx`
- `0x18002cbc2`: `onecore\com\combase\objact\dllcache.cxx`
- `0x18002cbdd`: `onecore\com\combase\objact\dllcache.cxx`
- `0x18002cbf5`: `onecore\com\combase\objact\dllcache.cxx`
- `0x18002cc55`: `onecore\com\combase\objact\dllcache.cxx`
- `0x18002ccbd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002cba9`: `Dll path: %ls`

## pseudocode

```c
__int64 __fastcall CClassCache::CDllPathEntry::Create(
        wchar_t *dllPath,
        unsigned int dllPathHash,
        bool isSixteenBit,
        bool isOle32,
        bool delayedUnload,
        bool makeValidInCurrentApartment,
        IImmediateCallback *virtualizationCallback,
        CClassCache::CDllPathEntry **pDPE)
{
  HRESULT v10; // eax
  unsigned int v11; // ebx
  HRESULT (__fastcall *ProcAddress)(const _GUID *, const _GUID *, void **); // r13
  FARPROC v13; // rax
  HRESULT (__fastcall *v14)(HSTRING__ *, IActivationFactory **); // r12
  SHashChain *buckets; // rax
  __int64 v16; // rdi
  CClassCache::CDllPathEntry *pNext; // rbx
  const _GUID *v18; // rdx
  __int64 v19; // rcx
  wchar_t *v20; // rax
  size_t v21; // rdi
  size_t v22; // r15
  wchar_t *v23; // rax
  wchar_t *v24; // rbx
  CClassCache::CDllPathEntry *v25; // rax
  CClassCache::CDllPathEntry *v26; // rdi
  unsigned int v27; // edi
  LoadOrFreeWhy v28; // ecx
  HINSTANCE__ *v30; // rdx
  SHashChain *v31; // rdx
  HRESULT v32; // eax
  unsigned int v33; // edx
  HRESULT ValidInApartment_rl16; // eax
  HINSTANCE__ *hDll; // [rsp+30h] [rbp-20h] BYREF
  FARPROC v36; // [rsp+38h] [rbp-18h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&PrivMemFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > dllPathCopy; // [rsp+40h] [rbp-10h] BYREF
  HINSTANCE__ **p_hDll; // [rsp+48h] [rbp-8h]
  void *retaddr; // [rsp+88h] [rbp+38h]

  hDll = 0;
  if ( isOle32 )
  {
    v14 = 0;
    v36 = 0;
    if ( virtualizationCallback )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ProcAddress = (HRESULT (__fastcall *)(const _GUID *, const _GUID *, void **))DllGetClassObject;
  }
  else
  {
    dllPathCopy.m_ptr = dllPath;
    p_hDll = &hDll;
    if ( virtualizationCallback )
      v10 = virtualizationCallback->DoCallback(
              virtualizationCallback,
              ImmediateCallback__lambda_eebf69f5a3250f8786ebc7c3378db176___::CallbackFunction,
              &dllPathCopy);
    else
      v10 = lambda_eebf69f5a3250f8786ebc7c3378db176_::operator()((__int64)&dllPathCopy);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x8E8u, "onecore\\com\\combase\\objact\\dllcache.cxx", v10);
      goto LABEL_38;
    }
    ProcAddress = (HRESULT (__fastcall *)(const _GUID *, const _GUID *, void **))GetProcAddress(
                                                                                   hDll,
                                                                                   "DllGetClassObject");
    v13 = GetProcAddress(hDll, "DllGetActivationFactory");
    v14 = (HRESULT (__fastcall *)(HSTRING__ *, IActivationFactory **))v13;
    if ( !ProcAddress && !v13 )
    {
      FreeLibraryWithLogging(NoValidEntryPoint, hDll, dllPath);
      v11 = -2147220999;
      hDll = 0;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x8F6u,
        "onecore\\com\\combase\\objact\\dllcache.cxx",
        -2147220999,
        "Dll path: %ls",
        dllPath);
LABEL_38:
      wil::details::in1diag3::Return_Hr(retaddr, 0x88Eu, "onecore\\com\\combase\\objact\\dllcache.cxx", v11);
      return v11;
    }
    v36 = GetProcAddress(hDll, "DllCanUnloadNow");
  }
  CRWLock::AcquireWriterLock(&CClassCache::_mxs, 0xFFFFFFFF);
  dllPathCopy.m_ptr = dllPath;
  if ( CClassCache::_DllPathEntries.IsValid(&CClassCache::_DllPathEntries) )
  {
    buckets = CClassCache::_DllPathEntries._buckets;
    v16 = dllPathHash % 0x17;
    pNext = (CClassCache::CDllPathEntry *)CClassCache::_DllPathEntries._buckets[v16].pNext;
    while ( pNext != (CClassCache::CDllPathEntry *)&buckets[v16] )
    {
      if ( CClassCache::_DllPathEntries.Compare(
             &CClassCache::_DllPathEntries,
             &dllPathCopy,
             (SHashChain *)pNext,
             dllPathHash) )
      {
        if ( !pNext )
          break;
        if ( !makeValidInCurrentApartment
          || (ValidInApartment_rl16 = CClassCache::CDllPathEntry::MakeValidInApartment_rl16(pNext, v18),
              v27 = ValidInApartment_rl16,
              ValidInApartment_rl16 >= 0) )
        {
          _InterlockedIncrement((volatile signed __int32 *)&pNext->_cUsing);
          *pDPE = pNext;
          CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
          FreeLibraryWithLogging(AnotherThreadBeatUsHere, hDll, dllPath);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          0x8C7u,
          "onecore\\com\\combase\\objact\\dllcache.cxx",
          ValidInApartment_rl16);
        CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
        v28 = AnotherThreadBeatUsHere;
        goto LABEL_24;
      }
      pNext = pNext->_pNext;
      buckets = CClassCache::_DllPathEntries._buckets;
    }
  }
  if ( !dllPath )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      0xF89u,
      "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h");
  v19 = 0x7FFFFFFF;
  v20 = dllPath;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  v21 = 2 * (v20 - dllPath);
  v22 = v21 + 2;
  v23 = (wchar_t *)HeapAlloc(g_hHeap, 0, v21 + 2);
  v24 = v23;
  if ( v23 )
  {
    if ( v21 )
    {
      if ( v22 < v21 )
      {
        memset_0(v23, 0, v22);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v23, dllPath, v21);
      }
    }
    v24[v21 / 2] = 0;
  }
  v25 = (CClassCache::CDllPathEntry *)HeapAlloc(g_hHeap, 0, 0x88u);
  v26 = v25;
  if ( v25 )
  {
    v30 = hDll;
    v25->_pNext = v25;
    v25->_pPrev = v25;
    v25->_dllPathHash = dllPathHash;
    v25->_dllPath.m_ptr = v24;
    v25->_dwSig = CClassCache::CDllPathEntry::SIG;
    v25->_isSixteenBit = isSixteenBit;
    v25->_isOle32 = isOle32;
    v25->_pfnDllCanUnload = (HRESULT (__fastcall *)())v36;
    v25->_delayedUnload = delayedUnload;
    v25->_pfnGetClassObject = ProcAddress;
    v25->_pfnGetActivationFactory = v14;
    v25->_gcoWasHere._Storage._Value = 1;
    v25->_expirationTime._Storage._Value = 0;
    v25->_fGCO_WAS_HERE = 1;
    v25->_p1stClass = 0;
    dllPathCopy.m_ptr = 0;
    v25->_cUsing = 0;
    v25->_pAptEntryFront = (CClassCache::CDllAptEntry *)&v25->_pAptEntryFront;
    v25->_pAptEntryBack = (CClassCache::CDllAptEntry *)&v25->_pAptEntryFront;
    v25->_hDll32 = v30;
    v25->_expireTime = 0;
    if ( makeValidInCurrentApartment )
    {
      v32 = CClassCache::CDllPathEntry::MakeValidInApartment_rl16(v25, (const _GUID *)v30);
      v11 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x8B2u, "onecore\\com\\combase\\objact\\dllcache.cxx", v32);
        CClassCache::CDllPathEntry::`scalar deleting destructor'(v26, v33);
        Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<unsigned int>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<unsigned int,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,0,1,0>>::View>((std::unique_ptr<wchar_t const * [0]> *)&dllPathCopy);
        CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
        FreeLibraryWithLogging(FailedToCreateAPathEntry, hDll, dllPath);
        return v11;
      }
    }
    v31 = &CClassCache::_DllPathEntries._buckets[dllPathHash % 0x17];
    v26->_pPrev = (CClassCache::CDllPathEntry *)v31;
    v31->pNext->pPrev = (SHashChain *)v26;
    v26->_pNext = (CClassCache::CDllPathEntry *)v31->pNext;
    v31->pNext = (SHashChain *)v26;
    if ( ++CClassCache::_DllPathEntries._cCurEntries > CClassCache::_DllPathEntries._cMaxEntries )
      CClassCache::_DllPathEntries._cMaxEntries = CClassCache::_DllPathEntries._cCurEntries;
    _InterlockedIncrement((volatile signed __int32 *)&v26->_cUsing);
    *pDPE = v26;
    CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
    return 0;
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, 0x8AEu, "onecore\\com\\combase\\objact\\dllcache.cxx", -2147024882);
    if ( v24 )
      HeapFree(g_hHeap, 0, v24);
    CRWLock::ReleaseWriterLock(&CClassCache::_mxs);
    v28 = FailedToCreateAPathEntry;
LABEL_24:
    FreeLibraryWithLogging(v28, hDll, dllPath);
    return v27;
  }
}

```

## disassembly

```asm
0x18002c808  mov     [rsp-38h+arg_0], rbx
0x18002c80d  mov     [rsp-38h+arg_18], isOle32
0x18002c812  mov     [rsp-38h+arg_10], isSixteenBit
0x18002c817  push    rbp
0x18002c818  push    rsi
0x18002c819  push    rdi
0x18002c81a  push    r12
0x18002c81c  push    r13
0x18002c81e  push    r14
0x18002c820  push    r15
0x18002c822  mov     rbp, rsp
0x18002c825  sub     rsp, 50h
0x18002c829  xor     r15d, r15d
0x18002c82c  mov     r14d, dllPathHash
0x18002c82f  mov     [rbp+hDll], r15
0x18002c833  mov     rsi, dllPath
0x18002c836  test    isOle32, isOle32
0x18002c839  jnz     loc_18002CC9B
0x18002c83f  mov     [rbp+dllPathCopy.m_ptr], dllPath
0x18002c843  lea     rax, [rbp+hDll]
0x18002c847  mov     dllPath, [rbp+arg_30]
0x18002c84b  mov     [rbp+var_8], rax
0x18002c84f  test    dllPath, dllPath
0x18002c852  jnz     loc_18002CC7F
0x18002c858  lea     dllPath, [rbp+dllPathCopy]
0x18002c85c  call    _lambda_eebf69f5a3250f8786ebc7c3378db176___operator__
0x18002c861  mov     ebx, eax
0x18002c863  test    eax, eax
0x18002c865  js      loc_18002CBD9
0x18002c86b  mov     dllPath, [rbp+hDll]; hModule
0x18002c86f  lea     rdx, ?DLL_GET_CLASS_OBJECT_EP@CDllPathEntry@CClassCache@@0QBDB; "DllGetClassObject"
0x18002c876  call    cs:__imp_GetProcAddress
0x18002c87c  mov     dllPath, [rbp+hDll]; hModule
0x18002c880  lea     rdx, ?DLL_GET_ACTIVATION_FACTORY_EP@CDllPathEntry@CClassCache@@0QBDB; "DllGetActivationFactory"
0x18002c887  mov     r13, rax
0x18002c88a  call    cs:__imp_GetProcAddress
0x18002c890  mov     r12, rax
0x18002c893  test    r13, r13
0x18002c896  jz      loc_18002CB8D
0x18002c89c  mov     dllPath, [rbp+hDll]; hModule
0x18002c8a0  lea     rdx, ?DLL_CAN_UNLOAD_EP@CDllPathEntry@CClassCache@@0QBDB; "DllCanUnloadNow"
0x18002c8a7  call    cs:__imp_GetProcAddress
0x18002c8ad  mov     [rbp+var_18], rax
0x18002c8b1  or      dllPathHash, 0FFFFFFFFh; dwDesiredTimeout
0x18002c8b4  lea     dllPath, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002c8bb  call    ?AcquireWriterLock@CRWLock@@QEAAKK@Z; CRWLock::AcquireWriterLock(ulong)
0x18002c8c0  mov     dllPath, cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A.__vftable; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002c8c7  mov     [rbp+dllPathCopy.m_ptr], rsi
0x18002c8cb  mov     rax, [dllPath+20h]
0x18002c8cf  lea     dllPath, ?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A; CClassCache::CDPEHashTable CClassCache::_DllPathEntries
0x18002c8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8db  test    eax, eax
0x18002c8dd  jz      short loc_18002C943
0x18002c8df  mov     eax, 0B21642C9h
0x18002c8e4  mov     edi, r14d
0x18002c8e7  mul     r14d
0x18002c8ea  shr     dllPathHash, 4
0x18002c8ed  imul    eax, dllPathHash, 17h
0x18002c8f0  sub     edi, eax
0x18002c8f2  mov     rax, cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A._buckets; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002c8f9  shl     rdi, 4
0x18002c8fd  mov     rbx, [rdi+rax]
0x18002c901  add     rax, rdi
0x18002c904  cmp     rbx, rax
0x18002c907  jz      short loc_18002C943
0x18002c909  mov     rax, cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A.__vftable; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002c910  lea     rdx, [rbp+dllPathCopy]
0x18002c914  mov     r9d, r14d
0x18002c917  lea     dllPath, ?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A; CClassCache::CDPEHashTable CClassCache::_DllPathEntries
0x18002c91e  mov     r8, rbx
0x18002c921  mov     rax, [rax+30h]
0x18002c925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c92a  test    eax, eax
0x18002c92c  jnz     short loc_18002C93A
0x18002c92e  mov     rbx, [rbx]
0x18002c931  mov     rax, cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A._buckets; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002c938  jmp     short loc_18002C901
0x18002c93a  test    rbx, rbx
0x18002c93d  jnz     loc_18002CC10
0x18002c943  test    rsi, rsi
0x18002c946  jz      loc_18002CCB9
0x18002c94c  mov     ecx, 7FFFFFFFh
0x18002c951  mov     rax, rsi
0x18002c954  cmp     [rax], r15w
0x18002c958  jz      short loc_18002C964
0x18002c95a  add     rax, 2
0x18002c95e  sub     dllPath, 1
0x18002c962  jnz     short loc_18002C954
0x18002c964  mov     dllPath, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002c96b  sub     rax, rsi
0x18002c96e  sar     rax, 1
0x18002c971  xor     dllPathHash, dllPathHash; dwFlags
0x18002c973  lea     rdi, [rax+rax]
0x18002c977  lea     r15, [rdi+2]
0x18002c97b  mov     r8, r15; dwBytes
0x18002c97e  call    cs:__imp_HeapAlloc
0x18002c984  mov     rbx, rax
0x18002c987  test    rax, rax
0x18002c98a  jz      loc_18002CB2B
0x18002c990  test    rdi, rdi
0x18002c993  jnz     loc_18002CB0F
0x18002c999  xor     r15d, r15d
0x18002c99c  mov     [rdi+rbx], r15w
0x18002c9a1  mov     dllPath, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002c9a8  xor     dllPathHash, dllPathHash; dwFlags
0x18002c9aa  mov     r8d, 88h; dwBytes
0x18002c9b0  call    cs:__imp_HeapAlloc
0x18002c9b6  mov     rdi, rax
0x18002c9b9  test    rax, rax
0x18002c9bc  jnz     short loc_18002CA29
0x18002c9be  mov     dllPath, [rbp+38h]; callerReturnAddress
0x18002c9c2  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x18002c9c9  mov     edi, 8007000Eh
0x18002c9ce  mov     dllPathHash, 8AEh; lineNumber
0x18002c9d3  mov     r9d, edi; hr
0x18002c9d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c9db  test    rbx, rbx
0x18002c9de  jz      short loc_18002C9F2
0x18002c9e0  mov     dllPath, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002c9e7  mov     r8, rbx; lpMem
0x18002c9ea  xor     dllPathHash, dllPathHash; dwFlags
0x18002c9ec  call    cs:__imp_HeapFree
0x18002c9f2  lea     dllPath, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002c9f9  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x18002c9fe  mov     ecx, 3; why
0x18002ca03  mov     rdx, [rbp+hDll]; hMod
0x18002ca07  mov     r8, rsi; pswzOptionalFileName
0x18002ca0a  call    ?FreeLibraryWithLogging@@YAXW4LoadOrFreeWhy@@PEAUHINSTANCE__@@PEBG@Z; FreeLibraryWithLogging(LoadOrFreeWhy,HINSTANCE__ *,ushort const *)
0x18002ca0f  mov     eax, edi
0x18002ca11  mov     rbx, [rsp+50h+arg_0]
0x18002ca19  add     rsp, 50h
0x18002ca1d  pop     r15
0x18002ca1f  pop     r14
0x18002ca21  pop     r13
0x18002ca23  pop     r12
0x18002ca25  pop     rdi
0x18002ca26  pop     rsi
0x18002ca27  pop     rbp
0x18002ca28  retn
0x18002ca29  mov     rdx, [rbp+hDll]; pclsid
0x18002ca2d  mov     ecx, cs:?SIG@CDllPathEntry@CClassCache@@0KB; ulong const CClassCache::CDllPathEntry::SIG
0x18002ca33  mov     [rax], rdi
0x18002ca36  mov     [rax+8], rdi
0x18002ca3a  mov     [rax+10h], r14d
0x18002ca3e  mov     [rax+18h], rbx
0x18002ca42  mov     [rax+20h], ecx
0x18002ca45  mov     al, [rbp+arg_10]
0x18002ca48  mov     cl, [rbp+arg_20]
0x18002ca4b  mov     [rdi+24h], al
0x18002ca4e  mov     al, [rbp+arg_18]
0x18002ca51  mov     [rdi+25h], al
0x18002ca54  mov     rax, [rbp+var_18]
0x18002ca58  mov     [rdi+38h], rax
0x18002ca5c  lea     rax, [rdi+68h]
0x18002ca60  mov     [rdi+26h], cl
0x18002ca63  mov     [rdi+28h], r13
0x18002ca67  mov     [rdi+30h], r12
0x18002ca6b  mov     byte ptr [rdi+40h], 1
0x18002ca6f  mov     [rdi+48h], r15
0x18002ca73  mov     dword ptr [rdi+50h], 1
0x18002ca7a  mov     [rdi+58h], r15
0x18002ca7e  mov     [rbp+dllPathCopy.m_ptr], r15
0x18002ca82  mov     [rdi+60h], r15d
0x18002ca86  mov     [rax], rax
0x18002ca89  mov     [rdi+70h], rax
0x18002ca8d  mov     [rdi+78h], rdx
0x18002ca91  mov     [rdi+80h], r15
0x18002ca98  cmp     [rbp+arg_28], r15b
0x18002ca9c  jnz     loc_18002CB33
0x18002caa2  mov     eax, 0B21642C9h
0x18002caa7  mul     r14d
0x18002caaa  shr     dllPathHash, 4
0x18002caad  imul    eax, dllPathHash, 17h
0x18002cab0  sub     r14d, eax
0x18002cab3  mov     dllPathHash, r14d
0x18002cab6  shl     rdx, 4
0x18002caba  add     rdx, cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A._buckets; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002cac1  mov     [rdi+8], rdx
0x18002cac5  mov     rax, [rdx]
0x18002cac8  mov     [rax+8], rdi
0x18002cacc  mov     rax, [rdx]
0x18002cacf  mov     [rdi], rax
0x18002cad2  mov     [rdx], rdi
0x18002cad5  mov     eax, cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A._cCurEntries; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002cadb  inc     eax
0x18002cadd  cmp     eax, cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A._cMaxEntries; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002cae3  mov     cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A._cCurEntries, eax; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002cae9  jbe     short loc_18002CAF1
0x18002caeb  mov     cs:?_DllPathEntries@CClassCache@@2VCDPEHashTable@1@A._cMaxEntries, eax; CClassCache::CDPEHashTable CClassCache::_DllPathEntries ...
0x18002caf1  lock inc dword ptr [rdi+60h]
0x18002caf5  mov     rax, [rbp+arg_38]
0x18002caf9  lea     dllPath, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002cb00  mov     [rax], rdi
0x18002cb03  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x18002cb08  xor     eax, eax
0x18002cb0a  jmp     loc_18002CA11
0x18002cb0f  mov     dllPath, rbx; void *
0x18002cb12  cmp     r15, rdi
0x18002cb15  jb      loc_18002CCCF
0x18002cb1b  mov     r8, rdi; Size
0x18002cb1e  mov     rdx, rsi; Src
0x18002cb21  call    memcpy_0
0x18002cb26  jmp     loc_18002C999
0x18002cb2b  xor     r15d, r15d
0x18002cb2e  jmp     loc_18002C9A1
0x18002cb33  mov     dllPath, rdi; this
0x18002cb36  call    ?MakeValidInApartment_rl16@CDllPathEntry@CClassCache@@QEAAJPEBU_GUID@@@Z; CClassCache::CDllPathEntry::MakeValidInApartment_rl16(_GUID const *)
0x18002cb3b  mov     ebx, eax
0x18002cb3d  test    eax, eax
0x18002cb3f  jns     loc_18002CAA2
0x18002cb45  mov     dllPath, [rbp+38h]; callerReturnAddress
0x18002cb49  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x18002cb50  mov     r9d, eax; hr
0x18002cb53  mov     dllPathHash, 8B2h; lineNumber
0x18002cb58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cb5d  mov     dllPath, rdi; this
0x18002cb60  call    ??_GCDllPathEntry@CClassCache@@QEAAPEAXI@Z; CClassCache::CDllPathEntry::`scalar deleting destructor'(uint)
0x18002cb65  lea     dllPath, [rbp+dllPathCopy]; this
0x18002cb69  call    ??1?$MakeAllocator@VView@?$HashMap@IPEAUHSTRING__@@U?$DefaultHash@I@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@I@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$HashMapOptions@IPEAUHSTRING__@@U?$DefaultLifetimeTraits@I@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<uint>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<uint,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,0,1,0>>::View>(void)
0x18002cb6e  lea     dllPath, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002cb75  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x18002cb7a  mov     rdx, [rbp+hDll]; hMod
0x18002cb7e  mov     r8, rsi; pswzOptionalFileName
0x18002cb81  mov     ecx, 3; why
0x18002cb86  call    ?FreeLibraryWithLogging@@YAXW4LoadOrFreeWhy@@PEAUHINSTANCE__@@PEBG@Z; FreeLibraryWithLogging(LoadOrFreeWhy,HINSTANCE__ *,ushort const *)
0x18002cb8b  jmp     short loc_18002CC09
0x18002cb8d  test    rax, rax
0x18002cb90  jnz     loc_18002C89C
0x18002cb96  mov     rdx, [rbp+hDll]; hMod
0x18002cb9a  lea     ecx, [rax+5]; why
0x18002cb9d  mov     r8, rsi; pswzOptionalFileName
0x18002cba0  call    ?FreeLibraryWithLogging@@YAXW4LoadOrFreeWhy@@PEAUHINSTANCE__@@PEBG@Z; FreeLibraryWithLogging(LoadOrFreeWhy,HINSTANCE__ *,ushort const *)
0x18002cba5  mov     dllPath, [rbp+38h]; callerReturnAddress
0x18002cba9  lea     rax, aDllPathLs; "Dll path: %ls"
0x18002cbb0  mov     ebx, 800401F9h
0x18002cbb5  mov     [rsp+50h+var_28], rsi
0x18002cbba  mov     r9d, ebx; hr
0x18002cbbd  mov     [rsp+50h+formatString], rax; formatString
0x18002cbc2  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x18002cbc9  mov     [rbp+hDll], r15
0x18002cbcd  mov     dllPathHash, 8F6h; lineNumber
0x18002cbd2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002cbd7  jmp     short loc_18002CBF1
0x18002cbd9  mov     dllPath, [rbp+38h]; callerReturnAddress
0x18002cbdd  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x18002cbe4  mov     r9d, ebx; hr
0x18002cbe7  mov     dllPathHash, 8E8h; lineNumber
0x18002cbec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cbf1  mov     dllPath, [rbp+38h]; callerReturnAddress
0x18002cbf5  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x18002cbfc  mov     r9d, ebx; hr
0x18002cbff  mov     dllPathHash, 88Eh; lineNumber
0x18002cc04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc09  mov     eax, ebx
0x18002cc0b  jmp     loc_18002CA11
0x18002cc10  cmp     [rbp+arg_28], r15b
0x18002cc14  jnz     short loc_18002CC43
0x18002cc16  lock inc dword ptr [rbx+60h]
0x18002cc1a  mov     rax, [rbp+arg_38]
0x18002cc1e  lea     dllPath, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002cc25  mov     [rax], rbx
0x18002cc28  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x18002cc2d  mov     rdx, [rbp+hDll]; hMod
0x18002cc31  mov     r8, rsi; pswzOptionalFileName
0x18002cc34  mov     ecx, 4; why
0x18002cc39  call    ?FreeLibraryWithLogging@@YAXW4LoadOrFreeWhy@@PEAUHINSTANCE__@@PEBG@Z; FreeLibraryWithLogging(LoadOrFreeWhy,HINSTANCE__ *,ushort const *)
0x18002cc3e  jmp     loc_18002CB08
0x18002cc43  mov     dllPath, rbx; this
0x18002cc46  call    ?MakeValidInApartment_rl16@CDllPathEntry@CClassCache@@QEAAJPEBU_GUID@@@Z; CClassCache::CDllPathEntry::MakeValidInApartment_rl16(_GUID const *)
0x18002cc4b  mov     edi, eax
0x18002cc4d  test    eax, eax
0x18002cc4f  jns     short loc_18002CC16
0x18002cc51  mov     dllPath, [rbp+38h]; callerReturnAddress
0x18002cc55  lea     r8, aOnecoreComComb_60; "onecore\\com\\combase\\objact\\dllcache"...
0x18002cc5c  mov     r9d, eax; hr
0x18002cc5f  mov     dllPathHash, 8C7h; lineNumber
0x18002cc64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc69  lea     dllPath, ?_mxs@CClassCache@@2VCRWLock@@A; this
0x18002cc70  call    ?ReleaseWriterLock@CRWLock@@QEAAKXZ; CRWLock::ReleaseWriterLock(void)
0x18002cc75  mov     ecx, 4
0x18002cc7a  jmp     loc_18002CA03
0x18002cc7f  mov     rax, [dllPath]
0x18002cc82  lea     r8, [rbp+dllPathCopy]
0x18002cc86  lea     rdx, ImmediateCallback__lambda_eebf69f5a3250f8786ebc7c3378db176_____CallbackFunction
0x18002cc8d  mov     rax, [rax+18h]
0x18002cc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc96  jmp     loc_18002C861
0x18002cc9b  mov     r12, r15
0x18002cc9e  mov     [rbp+var_18], r15
0x18002cca2  cmp     [rbp+arg_30], r15
0x18002cca6  jz      short loc_18002CCAD
0x18002cca8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!virtualizationCallback")
0x18002ccad  lea     r13, DllGetClassObject
0x18002ccb4  jmp     loc_18002C8B1
0x18002ccb9  mov     dllPath, [rbp+38h]; callerReturnAddress
0x18002ccbd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002ccc4  mov     dllPathHash, 0F89h; lineNumber
0x18002ccc9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002cccf  mov     r8, r15; Size
0x18002ccd2  xor     dllPathHash, dllPathHash; Val
  ... truncated ...
```
