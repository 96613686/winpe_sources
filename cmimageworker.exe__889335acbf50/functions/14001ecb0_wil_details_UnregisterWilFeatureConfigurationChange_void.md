# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x14001ecb0`
- end: `0x14001ed1c`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140015dcc`

## callees

- `0x14001ecb0`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001ecf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001ecf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001ecd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001ecd8`

## string_xrefs

- `0x14001ecd1`: `ntdll.dll`
- `0x14001eceb`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x14001ecb0  push    rbx
0x14001ecb2  sub     rsp, 20h
0x14001ecb6  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14001ecbd  mov     rbx, rcx
0x14001ecc0  test    rax, rax
0x14001ecc3  jnz     short loc_14001ED0D
0x14001ecc5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001eccc  test    rax, rax
0x14001eccf  jnz     short loc_14001ECEB
0x14001ecd1  lea     rcx, ModuleName; "ntdll.dll"
0x14001ecd8  call    cs:__imp_GetModuleHandleW
0x14001ecdf  nop     dword ptr [rax+rax+00h]
0x14001ece4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001eceb  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14001ecf2  mov     rcx, rax; hModule
0x14001ecf5  call    cs:__imp_GetProcAddress
0x14001ecfc  nop     dword ptr [rax+rax+00h]
0x14001ed01  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14001ed08  test    rax, rax
0x14001ed0b  jz      short loc_14001ED15
0x14001ed0d  mov     rcx, rbx
0x14001ed10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ed15  add     rsp, 20h
0x14001ed19  pop     rbx
0x14001ed1a  retn
```
