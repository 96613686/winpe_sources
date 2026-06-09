# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x14000c794`
- end: `0x14000c800`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140006ad8`

## callees

- `0x14000c794`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c7d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c7d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c7bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c7bc`

## string_xrefs

- `0x14000c7b5`: `ntdll.dll`
- `0x14000c7cf`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14000c794  push    rbx
0x14000c796  sub     rsp, 20h
0x14000c79a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14000c7a1  mov     rbx, rcx
0x14000c7a4  test    rax, rax
0x14000c7a7  jnz     short loc_14000C7F1
0x14000c7a9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c7b0  test    rax, rax
0x14000c7b3  jnz     short loc_14000C7CF
0x14000c7b5  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000c7bc  call    cs:__imp_GetModuleHandleW
0x14000c7c3  nop     dword ptr [rax+rax+00h]
0x14000c7c8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c7cf  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000c7d6  mov     rcx, rax; hModule
0x14000c7d9  call    cs:__imp_GetProcAddress
0x14000c7e0  nop     dword ptr [rax+rax+00h]
0x14000c7e5  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14000c7ec  test    rax, rax
0x14000c7ef  jz      short loc_14000C7F9
0x14000c7f1  mov     rcx, rbx
0x14000c7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7f9  add     rsp, 20h
0x14000c7fd  pop     rbx
0x14000c7fe  retn
```
