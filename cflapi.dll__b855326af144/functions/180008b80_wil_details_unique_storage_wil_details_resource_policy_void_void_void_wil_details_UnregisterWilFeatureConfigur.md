# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180008b80`
- end: `0x180008be5`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800090b8`

## callees

- `0x180008b80`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008bad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008bad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bc4`

## string_xrefs

- `0x180008ba6`: `ntdll.dll`
- `0x180008bba`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180008b80  push    rbx
0x180008b82  sub     rsp, 20h
0x180008b86  mov     rbx, [rcx]
0x180008b89  test    rbx, rbx
0x180008b8c  jz      short loc_180008BDF
0x180008b8e  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180008b95  test    rax, rax
0x180008b98  jnz     short loc_180008BD6
0x180008b9a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ba1  test    rax, rax
0x180008ba4  jnz     short loc_180008BBA
0x180008ba6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008bad  call    cs:__imp_GetModuleHandleW
0x180008bb3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008bba  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180008bc1  mov     rcx, rax; hModule
0x180008bc4  call    cs:__imp_GetProcAddress
0x180008bca  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180008bd1  test    rax, rax
0x180008bd4  jz      short loc_180008BDF
0x180008bd6  mov     rcx, rbx
0x180008bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bde  nop
0x180008bdf  add     rsp, 20h
0x180008be3  pop     rbx
0x180008be4  retn
```
