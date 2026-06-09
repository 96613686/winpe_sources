# DllMain

- ea: `0x18000acb0`
- end: `0x18000aded`
- name: `DllMain`
- size: `317`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800028b4`

## callees

- `0x180006f78`
- `0x18000847c`
- `0x180009d00`
- `0x18000acb0`
- `0x18000bd38`
- `0x18000c040`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ad31`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000ad31`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ada9`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x18000ada9`

## string_xrefs

- `0x18000ad12`: `Dll Init DLL_PROCESS_ATTACH`
- `0x18000aced`: `DllMain`
- `0x18000ad1f`: `DllMain`
- `0x18000ad61`: `DllMain`
- `0x18000ad54`: `Dll Init DLL_PROCESS_DETACH`
- `0x18000acfe`: `Dll Init DLL_THREAD_ATTACH`
- `0x18000ace0`: `Dll Init DLL_THREAD_DETACH`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v5; // rdx
  __int64 v6; // rdx
  DSLogger *v7; // rax
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // rdx
  DSLogger *v11; // rax
  __int64 v12; // rdx
  DSLogger *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v20; // [rsp+38h] [rbp+10h] BYREF

  if ( fdwReason )
  {
    v5 = fdwReason - 1;
    if ( (_DWORD)v5 )
    {
      v6 = (unsigned int)(v5 - 1);
      if ( !(_DWORD)v6 )
      {
        v7 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                           hinstDLL,
                           v6,
                           lpvReserved);
        v8 = L"Dll Init DLL_THREAD_ATTACH";
        v9 = 99;
        goto LABEL_6;
      }
      if ( (_DWORD)v6 == 1 )
      {
        v7 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                           hinstDLL,
                           v6,
                           lpvReserved);
        v8 = L"Dll Init DLL_THREAD_DETACH";
        v9 = 102;
LABEL_6:
        v10 = L"DllMain";
LABEL_13:
        DSLogger::LogInformation(v7, v10, v9, v8);
      }
    }
    else
    {
      v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          hinstDLL,
                          v5,
                          lpvReserved);
      DSLogger::LogInformation(v11, L"DllMain", 0x4Eu, L"Dll Init DLL_PROCESS_ATTACH");
      DisableThreadLibraryCalls(hinstDLL);
      LOBYTE(v12) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetImpl'::`2'::impl,
        v12);
      EnableMitigations();
    }
  }
  else
  {
    v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        hinstDLL,
                        *(_QWORD *)&fdwReason,
                        lpvReserved);
    DSLogger::LogInformation(v13, L"DllMain", 0x5Au, L"Dll Init DLL_PROCESS_DETACH");
    LOBYTE(v14) = lpvReserved != 0;
    CommonLibraryDllProcessDetach(v14);
    LOBYTE(v15) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetImpl'::`2'::impl,
      v15);
    if ( g_IsRedirectionMitigationEnabled )
    {
      v20 = 0;
      if ( !(unsigned int)SetProcessMitigationPolicy(16, &v20) )
      {
        v7 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                           v17,
                           v16,
                           v18);
        v8 = L"Failed to set process redirection guard from DisableMitigations";
        v9 = 64;
        v10 = L"DisableMitigations";
        goto LABEL_13;
      }
      g_IsRedirectionMitigationEnabled = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000acb0  mov     [rsp+arg_0], rbx
0x18000acb5  push    rdi
0x18000acb6  sub     rsp, 20h
0x18000acba  mov     rdi, r8
0x18000acbd  mov     rbx, rcx
0x18000acc0  test    edx, edx
0x18000acc2  jz      loc_18000AD4F
0x18000acc8  sub     edx, 1
0x18000accb  jz      short loc_18000AD0D
0x18000accd  sub     edx, 1
0x18000acd0  jz      short loc_18000ACF9
0x18000acd2  cmp     edx, 1
0x18000acd5  jnz     loc_18000ADDD
0x18000acdb  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000ace0  lea     r9, aDllInitDllThre; "Dll Init DLL_THREAD_DETACH"
0x18000ace7  mov     r8d, 66h ; 'f'
0x18000aced  lea     rdx, aDllmain; "DllMain"
0x18000acf4  jmp     loc_18000ADD5
0x18000acf9  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000acfe  lea     r9, aDllInitDllThre_0; "Dll Init DLL_THREAD_ATTACH"
0x18000ad05  mov     r8d, 63h ; 'c'
0x18000ad0b  jmp     short loc_18000ACED
0x18000ad0d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000ad12  lea     r9, aDllInitDllProc; "Dll Init DLL_PROCESS_ATTACH"
0x18000ad19  mov     r8d, 4Eh ; 'N'; unsigned int
0x18000ad1f  lea     rdx, aDllmain; "DllMain"
0x18000ad26  mov     rcx, rax; this
0x18000ad29  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x18000ad2e  mov     rcx, rbx; hLibModule
0x18000ad31  call    cs:__imp_DisableThreadLibraryCalls
0x18000ad37  mov     dl, 1
0x18000ad39  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard> `wil::Feature<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetImpl(void)'::`2'::impl
0x18000ad40  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ad45  call    ?EnableMitigations@@YAXXZ; EnableMitigations(void)
0x18000ad4a  jmp     loc_18000ADDD
0x18000ad4f  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000ad54  lea     r9, aDllInitDllProc_0; "Dll Init DLL_PROCESS_DETACH"
0x18000ad5b  mov     r8d, 5Ah ; 'Z'; unsigned int
0x18000ad61  lea     rdx, aDllmain; "DllMain"
0x18000ad68  mov     rcx, rax; this
0x18000ad6b  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x18000ad70  test    rdi, rdi
0x18000ad73  setnz   cl
0x18000ad76  call    CommonLibraryDllProcessDetach
0x18000ad7b  mov     dl, 1
0x18000ad7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard> `wil::Feature<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::GetImpl(void)'::`2'::impl
0x18000ad84  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DSSvc_RedirectionGuard@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DSSvc_RedirectionGuard>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ad89  cmp     cs:?g_IsRedirectionMitigationEnabled@@3_NA, 0; bool g_IsRedirectionMitigationEnabled
0x18000ad90  jz      short loc_18000ADDD
0x18000ad92  mov     r8d, 4
0x18000ad98  mov     [rsp+28h+arg_8], 0
0x18000ada0  lea     rdx, [rsp+28h+arg_8]
0x18000ada5  lea     ecx, [r8+0Ch]
0x18000ada9  call    cs:__imp_SetProcessMitigationPolicy
0x18000adaf  test    eax, eax
0x18000adb1  jz      short loc_18000ADBC
0x18000adb3  mov     cs:?g_IsRedirectionMitigationEnabled@@3_NA, 0; bool g_IsRedirectionMitigationEnabled
0x18000adba  jmp     short loc_18000ADDD
0x18000adbc  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000adc1  lea     r9, aFailedToSetPro; "Failed to set process redirection guard"...
0x18000adc8  mov     r8d, 40h ; '@'; unsigned int
0x18000adce  lea     rdx, aDisablemitigat; "DisableMitigations"
0x18000add5  mov     rcx, rax; this
0x18000add8  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x18000addd  mov     rbx, [rsp+28h+arg_0]
0x18000ade2  mov     eax, 1
0x18000ade7  add     rsp, 20h
0x18000adeb  pop     rdi
0x18000adec  retn
```
