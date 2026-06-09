# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x140012e8c`
- end: `0x140012ef1`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140012fd0`

## callees

- `0x140012e8c`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012eb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012eb9`

## string_xrefs

- `0x140012eb2`: `ntdll.dll`
- `0x140012ec6`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
      goto LABEL_6;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlUnregisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_6:
      ((void (__fastcall *)(__int64))ProcAddress)(v1);
  }
}

```

## disassembly

```asm
0x140012e8c  push    rbx
0x140012e8e  sub     rsp, 20h
0x140012e92  mov     rbx, [rcx]
0x140012e95  test    rbx, rbx
0x140012e98  jz      short loc_140012EEB
0x140012e9a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140012ea1  test    rax, rax
0x140012ea4  jnz     short loc_140012EE2
0x140012ea6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012ead  test    rax, rax
0x140012eb0  jnz     short loc_140012EC6
0x140012eb2  lea     rcx, ModuleName; "ntdll.dll"
0x140012eb9  call    cs:__imp_GetModuleHandleW
0x140012ebf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012ec6  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140012ecd  mov     rcx, rax; hModule
0x140012ed0  call    cs:__imp_GetProcAddress
0x140012ed6  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140012edd  test    rax, rax
0x140012ee0  jz      short loc_140012EEB
0x140012ee2  mov     rcx, rbx
0x140012ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012eea  nop
0x140012eeb  add     rsp, 20h
0x140012eef  pop     rbx
0x140012ef0  retn
```
