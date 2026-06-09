# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000c5dc`
- end: `0x18000c648`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000693c`

## callees

- `0x18000c5dc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c604`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c604`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c621`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c621`

## string_xrefs

- `0x18000c5fd`: `ntdll.dll`
- `0x18000c617`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000c5dc  push    rbx
0x18000c5de  sub     rsp, 20h
0x18000c5e2  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000c5e9  mov     rbx, rcx
0x18000c5ec  test    rax, rax
0x18000c5ef  jnz     short loc_18000C639
0x18000c5f1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c5f8  test    rax, rax
0x18000c5fb  jnz     short loc_18000C617
0x18000c5fd  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000c604  call    cs:__imp_GetModuleHandleW
0x18000c60b  nop     dword ptr [rax+rax+00h]
0x18000c610  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c617  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000c61e  mov     rcx, rax; hModule
0x18000c621  call    cs:__imp_GetProcAddress
0x18000c628  nop     dword ptr [rax+rax+00h]
0x18000c62d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000c634  test    rax, rax
0x18000c637  jz      short loc_18000C641
0x18000c639  mov     rcx, rbx
0x18000c63c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c641  add     rsp, 20h
0x18000c645  pop     rbx
0x18000c646  retn
```
