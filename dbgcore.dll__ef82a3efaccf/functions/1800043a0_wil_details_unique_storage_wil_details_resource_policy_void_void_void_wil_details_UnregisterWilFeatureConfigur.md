# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1800043a0`
- end: `0x18000440e`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004640`

## callees

- `0x1800043a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800043ed`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800043ed`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800043d6`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800043d6`

## string_xrefs

- `0x1800043cf`: `ntdll.dll`
- `0x1800043e3`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800043a0  push    rbx
0x1800043a2  sub     rsp, 30h
0x1800043a6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800043af  mov     rbx, [rcx]
0x1800043b2  test    rbx, rbx
0x1800043b5  jz      short loc_180004408
0x1800043b7  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800043be  test    rax, rax
0x1800043c1  jnz     short loc_1800043FF
0x1800043c3  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800043ca  test    rax, rax
0x1800043cd  jnz     short loc_1800043E3
0x1800043cf  lea     rcx, ModuleName; "ntdll.dll"
0x1800043d6  call    cs:__imp_GetModuleHandleW
0x1800043dc  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800043e3  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x1800043ea  mov     rcx, rax; hModule
0x1800043ed  call    cs:__imp_GetProcAddress
0x1800043f3  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800043fa  test    rax, rax
0x1800043fd  jz      short loc_180004408
0x1800043ff  mov     rcx, rbx
0x180004402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004407  nop
0x180004408  add     rsp, 30h
0x18000440c  pop     rbx
0x18000440d  retn
```
