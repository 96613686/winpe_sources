# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180003cec`
- end: `0x180003d50`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003f7c`

## callees

- `0x180003cec`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003d19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003d30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003d30`

## string_xrefs

- `0x180003d12`: `ntdll.dll`
- `0x180003d26`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180003cec  push    rbx
0x180003cee  sub     rsp, 20h
0x180003cf2  mov     rbx, [rcx]
0x180003cf5  test    rbx, rbx
0x180003cf8  jz      short loc_180003D4A
0x180003cfa  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180003d01  test    rax, rax
0x180003d04  jnz     short loc_180003D42
0x180003d06  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003d0d  test    rax, rax
0x180003d10  jnz     short loc_180003D26
0x180003d12  lea     rcx, ModuleName; "ntdll.dll"
0x180003d19  call    cs:__imp_GetModuleHandleW
0x180003d1f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180003d26  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x180003d2d  mov     rcx, rax; hModule
0x180003d30  call    cs:__imp_GetProcAddress
0x180003d36  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180003d3d  test    rax, rax
0x180003d40  jz      short loc_180003D4A
0x180003d42  mov     rcx, rbx
0x180003d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4a  add     rsp, 20h
0x180003d4e  pop     rbx
0x180003d4f  retn
```
