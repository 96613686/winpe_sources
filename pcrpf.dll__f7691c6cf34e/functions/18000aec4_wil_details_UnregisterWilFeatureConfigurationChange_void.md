# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000aec4`
- end: `0x18000af30`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800052e8`

## callees

- `0x18000aec4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aeec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aeec`

## string_xrefs

- `0x18000aee5`: `ntdll.dll`
- `0x18000aeff`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000aec4  push    rbx
0x18000aec6  sub     rsp, 20h
0x18000aeca  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000aed1  mov     rbx, rcx
0x18000aed4  test    rax, rax
0x18000aed7  jnz     short loc_18000AF21
0x18000aed9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aee0  test    rax, rax
0x18000aee3  jnz     short loc_18000AEFF
0x18000aee5  lea     rcx, ModuleName; "ntdll.dll"
0x18000aeec  call    cs:__imp_GetModuleHandleW
0x18000aef3  nop     dword ptr [rax+rax+00h]
0x18000aef8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aeff  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000af06  mov     rcx, rax; hModule
0x18000af09  call    cs:__imp_GetProcAddress
0x18000af10  nop     dword ptr [rax+rax+00h]
0x18000af15  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000af1c  test    rax, rax
0x18000af1f  jz      short loc_18000AF29
0x18000af21  mov     rcx, rbx
0x18000af24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af29  add     rsp, 20h
0x18000af2d  pop     rbx
0x18000af2e  retn
```
