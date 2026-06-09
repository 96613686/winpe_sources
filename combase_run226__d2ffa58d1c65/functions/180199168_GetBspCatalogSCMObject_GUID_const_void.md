# GetBspCatalogSCMObject(_GUID const &,void * *)

- ea: `0x180199168`
- end: `0x18019955a`
- name: `?GetBspCatalogSCMObject@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `1010`
- prototype: `HRESULT __fastcall(const _GUID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18013ceac`

## callees

- `0x180022f94`
- `0x18003a8bc`
- `0x18003c7ec`
- `0x18006474c`
- `0x1800a5708`
- `0x1800bcd9c`
- `0x1800bd75c`
- `0x1801237f8`
- `0x18018909c`
- `0x18018ab84`
- `0x180199168`
- `0x180199560`
- `0x1801e10c8`
- `0x1801e1c64`
- `0x1801e1da0`
- `0x1801e1e50`

## import_xrefs

- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x180199253`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x180199330`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x180199253`
- `ntdll!RtlWow64IsWowGuestMachineSupported` at `0x180199330`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801991d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801992c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801993c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180199415`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801991d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801992c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801993c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180199415`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801992ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801993a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801992ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801993a9`

## string_xrefs

- `0x1801991ab`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x180199210`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x180199261`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1801992f9`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x18019933e`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x180199360`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1801994a6`: `onecore\com\combase\catalog\bspcatalog.cpp`
- `0x1801994fe`: `onecore\com\combase\catalog\bspcatalog.cpp`

## pseudocode

```c
__int64 __fastcall GetBspCatalogSCMObject(const _GUID *riid, void **ppv)
{
  unsigned int ClassesRootFromBspAPI; // eax
  HRESULT Interface; // ebx
  IUserTokenInternal *v6; // rax
  MachineWideRegCatalog *v7; // rbx
  unsigned __int16 NativeArchitecture; // ax
  HKEY__ *m_ptr; // r14
  IUserTokenInternal *v10; // rdi
  int IsWowGuestMachineSupported; // eax
  HRESULT v12; // eax
  LSTATUS v13; // eax
  MachineWideRegCatalog *v14; // rax
  IUserTokenInternal *v15; // rbx
  int v16; // eax
  HRESULT v17; // eax
  LSTATUS v18; // eax
  MachineWideRegCatalog *v19; // rax
  unsigned int v20; // edx
  IComCatalogInternalImpl *v21; // rax
  IComCatalogInternalImpl *v22; // r14
  IUserTokenInternal *v23; // rdx
  wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> nativeCatalog; // [rsp+30h] [rbp-30h] BYREF
  wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> x86WowCatalog; // [rsp+38h] [rbp-28h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > classesRootWowAA32Key; // [rsp+40h] [rbp-20h] BYREF
  wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy> arm32WowCatalog; // [rsp+48h] [rbp-18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > classesRootKey; // [rsp+50h] [rbp-10h] BYREF
  void *retaddr; // [rsp+88h] [rbp+28h]
  unsigned __int8 isWowArchitectureSupported; // [rsp+A0h] [rbp+40h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > classesRootWow6432Key; // [rsp+A8h] [rbp+48h] BYREF

  classesRootKey.m_ptr = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &classesRootKey,
    0);
  ClassesRootFromBspAPI = GetClassesRootFromBspAPI(&classesRootKey.m_ptr);
  if ( !ClassesRootFromBspAPI )
  {
    v6 = (IUserTokenInternal *)HeapAlloc(g_hHeap, 0, 0x30u);
    v7 = (MachineWideRegCatalog *)v6;
    if ( v6 )
    {
      NativeArchitecture = GetNativeArchitecture();
      MachineWideRegCatalog::MachineWideRegCatalog(v7, classesRootKey.m_ptr, NativeArchitecture);
    }
    wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
      (wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy> *)&nativeCatalog,
      v6);
    if ( !nativeCatalog.m_ptr )
    {
      Interface = -2147024882;
      wil::details::in1diag3::Return_Hr(retaddr, 0x67u, "onecore\\com\\combase\\catalog\\bspcatalog.cpp", -2147024882);
LABEL_42:
      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&nativeCatalog);
      goto LABEL_43;
    }
    m_ptr = classesRootKey.m_ptr;
    v10 = 0;
    classesRootKey.m_ptr = 0;
    isWowArchitectureSupported = 0;
    x86WowCatalog.m_ptr = 0;
    classesRootWow6432Key.m_ptr = 0;
    IsWowGuestMachineSupported = RtlWow64IsWowGuestMachineSupported(332, &isWowArchitectureSupported);
    if ( IsWowGuestMachineSupported < 0 )
    {
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              0x6Du,
              "onecore\\com\\combase\\catalog\\bspcatalog.cpp",
              IsWowGuestMachineSupported);
LABEL_11:
      Interface = v12;
LABEL_41:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&classesRootWow6432Key);
      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&x86WowCatalog);
      goto LABEL_42;
    }
    if ( isWowArchitectureSupported )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &classesRootWow6432Key,
        0);
      v13 = RegOpenKeyExW(m_ptr, L"WOW6432Node", 0, 0x20019u, &classesRootWow6432Key.m_ptr);
      if ( v13 )
      {
        if ( v13 != 2 )
        {
          v12 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  0x79u,
                  "onecore\\com\\combase\\catalog\\bspcatalog.cpp",
                  v13);
          goto LABEL_11;
        }
      }
      else
      {
        v14 = (MachineWideRegCatalog *)HeapAlloc(g_hHeap, 0, 0x30u);
        if ( v14 )
          MachineWideRegCatalog::MachineWideRegCatalog(v14, classesRootWow6432Key.m_ptr, 0x14Cu);
        wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(&x86WowCatalog, v14);
        v10 = (IUserTokenInternal *)x86WowCatalog.m_ptr;
        if ( !x86WowCatalog.m_ptr )
        {
          Interface = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            0x74u,
            "onecore\\com\\combase\\catalog\\bspcatalog.cpp",
            -2147024882);
          goto LABEL_41;
        }
        classesRootWow6432Key.m_ptr = 0;
      }
    }
    v15 = 0;
    arm32WowCatalog.m_ptr = 0;
    classesRootWowAA32Key.m_ptr = 0;
    v16 = RtlWow64IsWowGuestMachineSupported(452, &isWowArchitectureSupported);
    if ( v16 < 0 )
    {
      v17 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              0x7Fu,
              "onecore\\com\\combase\\catalog\\bspcatalog.cpp",
              v16);
LABEL_21:
      Interface = v17;
LABEL_40:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&classesRootWowAA32Key);
      wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&arm32WowCatalog);
      goto LABEL_41;
    }
    if ( isWowArchitectureSupported )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &classesRootWowAA32Key,
        0);
      v18 = RegOpenKeyExW(m_ptr, L"WowAA32Node", 0, 0x20019u, &classesRootWowAA32Key.m_ptr);
      if ( v18 )
      {
        if ( v18 != 2 )
        {
          v17 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  0x8Bu,
                  "onecore\\com\\combase\\catalog\\bspcatalog.cpp",
                  v18);
          goto LABEL_21;
        }
      }
      else
      {
        v19 = (MachineWideRegCatalog *)HeapAlloc(g_hHeap, 0, 0x30u);
        if ( v19 )
          MachineWideRegCatalog::MachineWideRegCatalog(v19, classesRootWowAA32Key.m_ptr, 0x1C4u);
        wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(&arm32WowCatalog, v19);
        v15 = (IUserTokenInternal *)arm32WowCatalog.m_ptr;
        if ( !arm32WowCatalog.m_ptr )
        {
          v20 = 134;
          goto LABEL_38;
        }
        classesRootWowAA32Key.m_ptr = 0;
      }
    }
    v21 = (IComCatalogInternalImpl *)HeapAlloc(g_hHeap, 0, 0x30u);
    v22 = v21;
    if ( v21 )
    {
      IComCatalogInternalImpl::IComCatalogInternalImpl(v21);
      v23 = (IUserTokenInternal *)nativeCatalog.m_ptr;
      v22->__vftable = (IComCatalogInternalImpl_vtbl *)BspCatalogSCM::`vftable'{for `IComCatalogInternalImpl'};
      v22[1].__vftable = (IComCatalogInternalImpl_vtbl *)BspCatalogSCM::`vftable'{for `IGetProcessInfoInternal'};
      LODWORD(v22[2].__vftable) = 0;
      wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
        (wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy> *)&v22[3],
        v23);
      wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
        (wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy> *)&v22[4],
        v10);
      wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(
        (wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy> *)&v22[5],
        v15);
      _InterlockedIncrement((volatile signed __int32 *)&v22[2]);
      Interface = BspCatalogSCM::QueryInterface((BspCatalogSCM *)v22, riid, ppv);
      BspCatalogSCM::Release((BspCatalogSCM *)v22);
      if ( Interface >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&classesRootWowAA32Key);
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&arm32WowCatalog);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&classesRootWow6432Key);
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&x86WowCatalog);
        wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>((wil::com_ptr_t<IRestrictedErrorRpcMarshal,wil::err_returncode_policy> *)&nativeCatalog);
        Interface = 0;
        goto LABEL_43;
      }
      v20 = 148;
      goto LABEL_39;
    }
    v20 = 144;
LABEL_38:
    Interface = -2147024882;
LABEL_39:
    wil::details::in1diag3::Return_Hr(retaddr, v20, "onecore\\com\\combase\\catalog\\bspcatalog.cpp", Interface);
    goto LABEL_40;
  }
  if ( ClassesRootFromBspAPI != 2 )
    wil::details::in1diag3::Log_Win32(
      retaddr,
      0x60u,
      "onecore\\com\\combase\\catalog\\bspcatalog.cpp",
      ClassesRootFromBspAPI);
  Interface = -2147467231;
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&classesRootKey);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180199168  mov     [rsp-28h+arg_0], rbx
0x18019916d  push    rbp
0x18019916e  push    rdi
0x18019916f  push    r12
0x180199171  push    r14
0x180199173  push    r15
0x180199175  mov     rbp, rsp
0x180199178  sub     rsp, 60h
0x18019917c  mov     r15, ppv
0x18019917f  mov     [rbp+classesRootKey.m_ptr], 0
0x180199187  mov     r12, riid
0x18019918a  xor     edx, edx; ptr
0x18019918c  lea     riid, [rbp+classesRootKey]; this
0x180199190  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180199195  lea     riid, [rbp+classesRootKey]; classesRootKey
0x180199199  call    ?GetClassesRootFromBspAPI@@YAJPEAPEAUHKEY__@@@Z; GetClassesRootFromBspAPI(HKEY__ * *)
0x18019919e  test    eax, eax
0x1801991a0  jz      short loc_1801991C9
0x1801991a2  cmp     eax, 2
0x1801991a5  jz      short loc_1801991BF
0x1801991a7  mov     riid, [rbp+28h]; callerReturnAddress
0x1801991ab  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x1801991b2  mov     r9d, eax; err
0x1801991b5  mov     edx, 60h ; '`'; lineNumber
0x1801991ba  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1801991bf  mov     ebx, 80004021h
0x1801991c4  jmp     loc_18019953A
0x1801991c9  mov     riid, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801991d0  xor     edx, edx; dwFlags
0x1801991d2  lea     r8d, [ppv+30h]; dwBytes
0x1801991d6  call    cs:__imp_HeapAlloc
0x1801991dc  mov     rbx, rax
0x1801991df  test    rax, rax
0x1801991e2  jz      short loc_1801991F9
0x1801991e4  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x1801991e9  mov     ppv, [rbp+classesRootKey.m_ptr]; classesRootKey
0x1801991ed  movzx   r8d, ax; architecture
0x1801991f1  mov     riid, rbx; this
0x1801991f4  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1801991f9  mov     ppv, rax; ptr
0x1801991fc  lea     riid, [rbp+nativeCatalog]; this
0x180199200  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x180199205  cmp     [rbp+nativeCatalog.m_ptr], 0
0x18019920a  jnz     short loc_18019922E
0x18019920c  mov     riid, [rbp+28h]; callerReturnAddress
0x180199210  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x180199217  mov     ebx, 8007000Eh
0x18019921c  mov     edx, 67h ; 'g'; lineNumber
0x180199221  mov     r9d, ebx; hr
0x180199224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199229  jmp     loc_180199531
0x18019922e  mov     r14, [rbp+classesRootKey.m_ptr]
0x180199232  lea     ppv, [rbp+isWowArchitectureSupported]
0x180199236  xor     edi, edi
0x180199238  mov     [rbp+classesRootKey.m_ptr], 0
0x180199240  mov     ebx, 14Ch
0x180199245  mov     [rbp+isWowArchitectureSupported], 0
0x180199249  mov     ecx, ebx
0x18019924b  mov     [rbp+x86WowCatalog.m_ptr], rdi
0x18019924f  mov     [rbp+classesRootWow6432Key.m_ptr], rdi
0x180199253  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x180199259  test    eax, eax
0x18019925b  jns     short loc_18019927A
0x18019925d  mov     riid, [rbp+28h]; callerReturnAddress
0x180199261  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x180199268  mov     r9d, eax; status
0x18019926b  lea     edx, [rdi+6Dh]; lineNumber
0x18019926e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180199273  mov     ebx, eax
0x180199275  jmp     loc_18019951F
0x18019927a  cmp     [rbp+isWowArchitectureSupported], dil
0x18019927e  jz      loc_18019931D
0x180199284  xor     edx, edx; ptr
0x180199286  lea     riid, [rbp+classesRootWow6432Key]; this
0x18019928a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18019928f  lea     rax, [rbp+classesRootWow6432Key]
0x180199293  mov     r9d, 20019h; samDesired
0x180199299  xor     r8d, r8d; ulOptions
0x18019929c  mov     [rsp+60h+phkResult], rax; phkResult
0x1801992a1  lea     ppv, aWow6432node; "WOW6432Node"
0x1801992a8  mov     riid, r14; hKey
0x1801992ab  call    cs:__imp_RegOpenKeyExW
0x1801992b1  test    eax, eax
0x1801992b3  jnz     loc_180199357
0x1801992b9  mov     riid, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801992c0  lea     r8d, [rax+30h]; dwBytes
0x1801992c4  xor     edx, edx; dwFlags
0x1801992c6  call    cs:__imp_HeapAlloc
0x1801992cc  test    rax, rax
0x1801992cf  jz      short loc_1801992E0
0x1801992d1  mov     ppv, [rbp+classesRootWow6432Key.m_ptr]; classesRootKey
0x1801992d5  mov     r8d, ebx; architecture
0x1801992d8  mov     riid, rax; this
0x1801992db  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1801992e0  mov     ppv, rax; other
0x1801992e3  lea     riid, [rbp+x86WowCatalog]; this
0x1801992e7  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIComCatalogInternal@@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(IComCatalogInternal *)
0x1801992ec  mov     rdi, [rbp+x86WowCatalog.m_ptr]
0x1801992f0  test    rdi, rdi
0x1801992f3  jnz     short loc_180199315
0x1801992f5  mov     riid, [rbp+28h]; callerReturnAddress
0x1801992f9  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x180199300  mov     ebx, 8007000Eh
0x180199305  lea     edx, [rdi+74h]; lineNumber
0x180199308  mov     r9d, ebx; hr
0x18019930b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199310  jmp     loc_18019951F
0x180199315  mov     [rbp+classesRootWow6432Key.m_ptr], 0
0x18019931d  xor     ebx, ebx
0x18019931f  lea     ppv, [rbp+isWowArchitectureSupported]
0x180199323  mov     ecx, 1C4h
0x180199328  mov     [rbp+arm32WowCatalog.m_ptr], rbx
0x18019932c  mov     [rbp+classesRootWowAA32Key.m_ptr], rbx
0x180199330  call    cs:__imp_RtlWow64IsWowGuestMachineSupported
0x180199336  test    eax, eax
0x180199338  jns     short loc_180199379
0x18019933a  mov     riid, [rbp+28h]; callerReturnAddress
0x18019933e  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x180199345  mov     r9d, eax; status
0x180199348  lea     edx, [rbx+7Fh]; lineNumber
0x18019934b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180199350  mov     ebx, eax
0x180199352  jmp     loc_18019950D
0x180199357  cmp     eax, 2
0x18019935a  jz      short loc_18019931D
0x18019935c  mov     riid, [rbp+28h]; callerReturnAddress
0x180199360  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x180199367  mov     r9d, eax; err
0x18019936a  mov     edx, 79h ; 'y'; lineNumber
0x18019936f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180199374  jmp     loc_180199273
0x180199379  cmp     [rbp+isWowArchitectureSupported], bl
0x18019937c  jz      loc_180199408
0x180199382  xor     edx, edx; ptr
0x180199384  lea     riid, [rbp+classesRootWowAA32Key]; this
0x180199388  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18019938d  lea     rax, [rbp+classesRootWowAA32Key]
0x180199391  mov     r9d, 20019h; samDesired
0x180199397  xor     r8d, r8d; ulOptions
0x18019939a  mov     [rsp+60h+phkResult], rax; phkResult
0x18019939f  lea     ppv, aWowaa32node; "WowAA32Node"
0x1801993a6  mov     riid, r14; hKey
0x1801993a9  call    cs:__imp_RegOpenKeyExW
0x1801993af  test    eax, eax
0x1801993b1  jnz     loc_180199499
0x1801993b7  mov     riid, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801993be  lea     r8d, [rax+30h]; dwBytes
0x1801993c2  xor     edx, edx; dwFlags
0x1801993c4  call    cs:__imp_HeapAlloc
0x1801993ca  test    rax, rax
0x1801993cd  jz      short loc_1801993E1
0x1801993cf  mov     ppv, [rbp+classesRootWowAA32Key.m_ptr]; classesRootKey
0x1801993d3  mov     r8d, 1C4h; architecture
0x1801993d9  mov     riid, rax; this
0x1801993dc  call    ??0MachineWideRegCatalog@@QEAA@PEAUHKEY__@@G@Z; MachineWideRegCatalog::MachineWideRegCatalog(HKEY__ *,ushort)
0x1801993e1  mov     ppv, rax; other
0x1801993e4  lea     riid, [rbp+arm32WowCatalog]; this
0x1801993e8  call    ??4?$com_ptr_t@UIComCatalogInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIComCatalogInternal@@@Z; wil::com_ptr_t<IComCatalogInternal,wil::err_returncode_policy>::operator=(IComCatalogInternal *)
0x1801993ed  mov     rbx, [rbp+arm32WowCatalog.m_ptr]
0x1801993f1  test    rbx, rbx
0x1801993f4  jnz     short loc_180199400
0x1801993f6  mov     edx, 86h
0x1801993fb  jmp     loc_1801994F5
0x180199400  mov     [rbp+classesRootWowAA32Key.m_ptr], 0
0x180199408  mov     riid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18019940f  xor     edx, edx; dwFlags
0x180199411  lea     r8d, [ppv+30h]; dwBytes
0x180199415  call    cs:__imp_HeapAlloc
0x18019941b  mov     r14, rax
0x18019941e  test    rax, rax
0x180199421  jz      loc_1801994F0
0x180199427  mov     riid, rax; this
0x18019942a  call    ??0IComCatalogInternalImpl@@QEAA@XZ; IComCatalogInternalImpl::IComCatalogInternalImpl(void)
0x18019942f  mov     ppv, [rbp+nativeCatalog.m_ptr]; ptr
0x180199433  lea     riid, ??_7BspCatalogSCM@@6BIComCatalogInternalImpl@@@; const BspCatalogSCM::`vftable'{for `IComCatalogInternalImpl'}
0x18019943a  mov     [r14], riid
0x18019943d  lea     rax, ??_7BspCatalogSCM@@6BIGetProcessInfoInternal@@@; const BspCatalogSCM::`vftable'{for `IGetProcessInfoInternal'}
0x180199444  lea     riid, [r14+18h]; this
0x180199448  mov     [r14+8], rax
0x18019944c  mov     dword ptr [r14+10h], 0
0x180199454  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x180199459  lea     riid, [r14+20h]; this
0x18019945d  mov     ppv, rdi; ptr
0x180199460  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x180199465  lea     riid, [r14+28h]; this
0x180199469  mov     ppv, rbx; ptr
0x18019946c  call    ??0?$com_ptr_t@UIUserTokenInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAUIUserTokenInternal@@@Z; wil::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>::com_ptr_t<IUserTokenInternal,wil::err_returncode_policy>(IUserTokenInternal *)
0x180199471  lock inc dword ptr [r14+10h]
0x180199476  mov     r8, r15; ppvObj
0x180199479  mov     ppv, r12; riid
0x18019947c  mov     riid, r14; this
0x18019947f  call    ?QueryInterface@BspCatalogSCM@@UEAAJAEBU_GUID@@PEAPEAX@Z; BspCatalogSCM::QueryInterface(_GUID const &,void * *)
0x180199484  mov     riid, r14; this
0x180199487  mov     ebx, eax
0x180199489  call    ?Release@BspCatalogSCM@@UEAAKXZ; BspCatalogSCM::Release(void)
0x18019948e  test    ebx, ebx
0x180199490  jns     short loc_1801994BF
0x180199492  mov     edx, 94h
0x180199497  jmp     short loc_1801994FA
0x180199499  cmp     eax, 2
0x18019949c  jz      loc_180199408
0x1801994a2  mov     riid, [rbp+28h]; callerReturnAddress
0x1801994a6  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x1801994ad  mov     r9d, eax; err
0x1801994b0  mov     edx, 8Bh; lineNumber
0x1801994b5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801994ba  jmp     loc_180199350
0x1801994bf  lea     riid, [rbp+classesRootWowAA32Key]; this
0x1801994c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801994c8  lea     riid, [rbp+arm32WowCatalog]; this
0x1801994cc  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x1801994d1  lea     riid, [rbp+classesRootWow6432Key]; this
0x1801994d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801994da  lea     riid, [rbp+x86WowCatalog]; this
0x1801994de  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x1801994e3  lea     riid, [rbp+nativeCatalog]; this
0x1801994e7  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x1801994ec  xor     ebx, ebx
0x1801994ee  jmp     short loc_18019953A
0x1801994f0  mov     edx, 90h; lineNumber
0x1801994f5  mov     ebx, 8007000Eh
0x1801994fa  mov     riid, [rbp+28h]; callerReturnAddress
0x1801994fe  lea     r8, aOnecoreComComb_144; "onecore\\com\\combase\\catalog\\bspcata"...
0x180199505  mov     r9d, ebx; hr
0x180199508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019950d  lea     riid, [rbp+classesRootWowAA32Key]; this
0x180199511  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180199516  lea     riid, [rbp+arm32WowCatalog]; this
0x18019951a  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x18019951f  lea     riid, [rbp+classesRootWow6432Key]; this
0x180199523  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180199528  lea     riid, [rbp+x86WowCatalog]; this
0x18019952c  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x180199531  lea     riid, [rbp+nativeCatalog]; this
0x180199535  call    ??1?$com_ptr_t@VCMachineGlobalObjectTable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>::~com_ptr_t<CMachineGlobalObjectTable,wil::err_returncode_policy>(void)
0x18019953a  lea     riid, [rbp+classesRootKey]; this
0x18019953e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180199543  mov     eax, ebx
0x180199545  mov     rbx, [rsp+60h+arg_0]
0x18019954d  add     rsp, 60h
0x180199551  pop     r15
0x180199553  pop     r14
0x180199555  pop     r12
0x180199557  pop     rdi
0x180199558  pop     rbp
0x180199559  retn
```
