# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x180013740`
- end: `0x1800137ac`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a30c`

## callees

- `0x180013740`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013768`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013768`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013785`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013785`

## string_xrefs

- `0x180013761`: `ntdll.dll`
- `0x18001377b`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180013740  push    rbx
0x180013742  sub     rsp, 20h
0x180013746  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18001374d  mov     rbx, rcx
0x180013750  test    rax, rax
0x180013753  jnz     short loc_18001379D
0x180013755  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001375c  test    rax, rax
0x18001375f  jnz     short loc_18001377B
0x180013761  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180013768  call    cs:__imp_GetModuleHandleW
0x18001376f  nop     dword ptr [rax+rax+00h]
0x180013774  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001377b  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180013782  mov     rcx, rax; hModule
0x180013785  call    cs:__imp_GetProcAddress
0x18001378c  nop     dword ptr [rax+rax+00h]
0x180013791  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180013798  test    rax, rax
0x18001379b  jz      short loc_1800137A5
0x18001379d  mov     rcx, rbx
0x1800137a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137a5  add     rsp, 20h
0x1800137a9  pop     rbx
0x1800137aa  retn
```
