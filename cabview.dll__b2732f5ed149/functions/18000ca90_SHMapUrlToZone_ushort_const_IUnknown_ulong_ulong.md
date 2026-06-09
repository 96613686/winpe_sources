# SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)

- ea: `0x18000ca90`
- end: `0x18000cc77`
- name: `?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z`
- size: `487`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IUnknown *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c714`

## callees

- `0x180002620`
- `0x18000ae54`
- `0x18000ae78`
- `0x18000ca90`
- `0x18000d084`
- `0x180013010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000caf9`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000cbe7`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000caf9`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000cbe7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cb2f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000cb16`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000cb16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cba9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cc0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cba9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cc0e`

## string_xrefs

- `0x18000cb09`: `urlmon.dll`
- `0x18000cb25`: `CoInternetCreateSecurityManager`

## pseudocode

```c
__int64 __fastcall SHMapUrlToZone(const unsigned __int16 *a1, struct IUnknown *a2, __int64 a3, unsigned int *a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rbx
  void *v8; // rcx
  void *v9; // rcx
  HRESULT v10; // ebx
  HRESULT v11; // eax
  void *v12; // rcx
  HMODULE v14; // [rsp+30h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-18h] BYREF

  if ( a1 && a4 )
  {
    ppvOut = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl'::`2'::impl,
                            a2) )
    {
      v14 = 0;
      if ( IUnknown_QueryService(0, &IID_IInternetSecurityManager, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut) >= 0 )
        goto LABEL_13;
      Library = LoadLibraryExW(L"urlmon.dll", 0, 0x800u);
      v14 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "CoInternetCreateSecurityManager");
        if ( ProcAddress )
        {
          v8 = ppvOut;
          ppvOut = 0;
          if ( v8 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
          if ( ((int (__fastcall *)(_QWORD, void **, _QWORD))ProcAddress)(0, &ppvOut, 0) >= 0 )
            goto LABEL_13;
        }
      }
      v9 = ppvOut;
      ppvOut = 0;
      if ( v9 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      v10 = CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b, &ppvOut);
      if ( v10 >= 0 )
LABEL_13:
        v10 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut + 40LL))(
                ppvOut,
                a1,
                a4,
                5120);
      wil::com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>::~com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>(&ppvOut);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v14);
    }
    else if ( IUnknown_QueryService(
                0,
                &IID_IInternetSecurityManager,
                &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                &ppvOut) >= 0
           || (v10 = CoCreateInstance(
                       &CLSID_InternetSecurityManager,
                       0,
                       1u,
                       &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
                       &ppvOut),
               v10 >= 0) )
    {
      v11 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, unsigned int *, __int64))(*(_QWORD *)ppvOut
                                                                                                 + 40LL))(
              ppvOut,
              a1,
              a4,
              5120);
      v12 = ppvOut;
      v10 = v11;
      ppvOut = 0;
      if ( v12 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ca90  mov     [rsp-18h+arg_8], rbx
0x18000ca95  push    rbp
0x18000ca96  push    rsi
0x18000ca97  push    rdi
0x18000ca98  mov     rbp, rsp
0x18000ca9b  sub     rsp, 50h
0x18000ca9f  mov     rax, cs:__security_cookie
0x18000caa6  xor     rax, rsp
0x18000caa9  mov     [rbp+var_10], rax
0x18000caad  mov     rdi, r9
0x18000cab0  mov     rsi, rcx
0x18000cab3  test    rcx, rcx
0x18000cab6  jz      loc_18000CC57
0x18000cabc  test    r9, r9
0x18000cabf  jz      loc_18000CC57
0x18000cac5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell> `wil::Feature<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::GetImpl(void)'::`2'::impl
0x18000cacc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeSecMgrCreationInShell>::__private_IsEnabled(void)
0x18000cad1  xor     ecx, ecx; punk
0x18000cad3  mov     [rbp+ppvOut], 0
0x18000cadb  lea     r9, [rbp+ppvOut]; ppvOut
0x18000cadf  lea     r8, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18000cae6  lea     rdx, IID_IInternetSecurityManager; guidService
0x18000caed  test    al, al
0x18000caef  jz      loc_18000CBE7
0x18000caf5  mov     [rbp+var_20], rcx
0x18000caf9  call    cs:__imp_IUnknown_QueryService
0x18000caff  test    eax, eax
0x18000cb01  jns     loc_18000CBB5
0x18000cb07  xor     edx, edx; hFile
0x18000cb09  lea     rcx, LibFileName; "urlmon.dll"
0x18000cb10  mov     r8d, 800h; dwFlags
0x18000cb16  call    cs:__imp_LoadLibraryExW
0x18000cb1c  mov     [rbp+var_20], rax
0x18000cb20  test    rax, rax
0x18000cb23  jz      short loc_18000CB6F
0x18000cb25  lea     rdx, ProcName; "CoInternetCreateSecurityManager"
0x18000cb2c  mov     rcx, rax; hModule
0x18000cb2f  call    cs:__imp_GetProcAddress
0x18000cb35  mov     rbx, rax
0x18000cb38  test    rax, rax
0x18000cb3b  jz      short loc_18000CB6F
0x18000cb3d  mov     rcx, [rbp+ppvOut]
0x18000cb41  mov     [rbp+ppvOut], 0
0x18000cb49  test    rcx, rcx
0x18000cb4c  jz      short loc_18000CB5A
0x18000cb4e  mov     rdx, [rcx]
0x18000cb51  mov     rax, [rdx+10h]
0x18000cb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5a  xor     r8d, r8d
0x18000cb5d  lea     rdx, [rbp+ppvOut]
0x18000cb61  xor     ecx, ecx
0x18000cb63  mov     rax, rbx
0x18000cb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb6b  test    eax, eax
0x18000cb6d  jns     short loc_18000CBB5
0x18000cb6f  mov     rcx, [rbp+ppvOut]
0x18000cb73  mov     [rbp+ppvOut], 0
0x18000cb7b  test    rcx, rcx
0x18000cb7e  jz      short loc_18000CB8C
0x18000cb80  mov     rax, [rcx]
0x18000cb83  mov     rax, [rax+10h]
0x18000cb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb8c  xor     edx, edx; pUnkOuter
0x18000cb8e  lea     rax, [rbp+ppvOut]
0x18000cb92  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18000cb99  mov     [rsp+50h+ppv], rax; ppv
0x18000cb9e  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18000cba5  lea     r8d, [rdx+1]; dwClsContext
0x18000cba9  call    cs:__imp_CoCreateInstance
0x18000cbaf  mov     ebx, eax
0x18000cbb1  test    eax, eax
0x18000cbb3  js      short loc_18000CBD3
0x18000cbb5  mov     rcx, [rbp+ppvOut]
0x18000cbb9  mov     r9d, 1400h
0x18000cbbf  mov     r8, rdi
0x18000cbc2  mov     rdx, rsi
0x18000cbc5  mov     rax, [rcx]
0x18000cbc8  mov     rax, [rax+28h]
0x18000cbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbd1  mov     ebx, eax
0x18000cbd3  lea     rcx, [rbp+ppvOut]
0x18000cbd7  call    ??1?$com_ptr_t@UIInternetSecurityManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>::~com_ptr_t<IInternetSecurityManager,wil::err_returncode_policy>(void)
0x18000cbdc  lea     rcx, [rbp+var_20]
0x18000cbe0  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18000cbe5  jmp     short loc_18000CC5C
0x18000cbe7  call    cs:__imp_IUnknown_QueryService
0x18000cbed  test    eax, eax
0x18000cbef  jns     short loc_18000CC1A
0x18000cbf1  xor     edx, edx; pUnkOuter
0x18000cbf3  lea     rax, [rbp+ppvOut]
0x18000cbf7  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x18000cbfe  mov     [rsp+50h+ppv], rax; ppv
0x18000cc03  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18000cc0a  lea     r8d, [rdx+1]; dwClsContext
0x18000cc0e  call    cs:__imp_CoCreateInstance
0x18000cc14  mov     ebx, eax
0x18000cc16  test    eax, eax
0x18000cc18  js      short loc_18000CC5C
0x18000cc1a  mov     rcx, [rbp+ppvOut]
0x18000cc1e  mov     r9d, 1400h
0x18000cc24  mov     r8, rdi
0x18000cc27  mov     rdx, rsi
0x18000cc2a  mov     rax, [rcx]
0x18000cc2d  mov     rax, [rax+28h]
0x18000cc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc36  mov     rcx, [rbp+ppvOut]
0x18000cc3a  mov     ebx, eax
0x18000cc3c  mov     [rbp+ppvOut], 0
0x18000cc44  test    rcx, rcx
0x18000cc47  jz      short loc_18000CC5C
0x18000cc49  mov     rax, [rcx]
0x18000cc4c  mov     rax, [rax+10h]
0x18000cc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc55  jmp     short loc_18000CC5C
0x18000cc57  mov     ebx, 80070057h
0x18000cc5c  mov     eax, ebx
0x18000cc5e  mov     rcx, [rbp+var_10]
0x18000cc62  xor     rcx, rsp; StackCookie
0x18000cc65  call    __security_check_cookie
0x18000cc6a  mov     rbx, [rsp+50h+arg_8]
0x18000cc6f  add     rsp, 50h
0x18000cc73  pop     rdi
0x18000cc74  pop     rsi
0x18000cc75  pop     rbp
0x18000cc76  retn
```
