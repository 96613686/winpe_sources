# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x1800078b8`
- end: `0x180007924`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800033c0`

## callees

- `0x1800078b8`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800078fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800078e0`

## string_xrefs

- `0x1800078d9`: `ntdll.dll`
- `0x1800078f3`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::UnregisterWilFeatureConfigurationChange(wil::details *this, void *a2)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification )
    goto LABEL_5;
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlUnregisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    ((void (__fastcall *)(wil::details *, void *))ProcAddress)(this, a2);
}

```

## disassembly

```asm
0x1800078b8  push    rbx
0x1800078ba  sub     rsp, 20h
0x1800078be  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800078c5  mov     rbx, rcx
0x1800078c8  test    rax, rax
0x1800078cb  jnz     short loc_180007915
0x1800078cd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078d4  test    rax, rax
0x1800078d7  jnz     short loc_1800078F3
0x1800078d9  lea     rcx, ModuleName; "ntdll.dll"
0x1800078e0  call    cs:__imp_GetModuleHandleW
0x1800078e7  nop     dword ptr [rax+rax+00h]
0x1800078ec  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800078f3  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800078fa  mov     rcx, rax; hModule
0x1800078fd  call    cs:__imp_GetProcAddress
0x180007904  nop     dword ptr [rax+rax+00h]
0x180007909  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180007910  test    rax, rax
0x180007913  jz      short loc_18000791D
0x180007915  mov     rcx, rbx
0x180007918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000791d  add     rsp, 20h
0x180007921  pop     rbx
0x180007922  retn
```
