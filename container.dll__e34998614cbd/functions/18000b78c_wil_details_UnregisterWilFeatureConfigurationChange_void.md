# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18000b78c`
- end: `0x18000b7f8`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005518`

## callees

- `0x18000b78c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b7b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b7b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b7d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b7d1`

## string_xrefs

- `0x18000b7ad`: `ntdll.dll`
- `0x18000b7c7`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18000b78c  push    rbx
0x18000b78e  sub     rsp, 20h
0x18000b792  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000b799  mov     rbx, rcx
0x18000b79c  test    rax, rax
0x18000b79f  jnz     short loc_18000B7E9
0x18000b7a1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b7a8  test    rax, rax
0x18000b7ab  jnz     short loc_18000B7C7
0x18000b7ad  lea     rcx, ModuleName; "ntdll.dll"
0x18000b7b4  call    cs:__imp_GetModuleHandleW
0x18000b7bb  nop     dword ptr [rax+rax+00h]
0x18000b7c0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b7c7  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000b7ce  mov     rcx, rax; hModule
0x18000b7d1  call    cs:__imp_GetProcAddress
0x18000b7d8  nop     dword ptr [rax+rax+00h]
0x18000b7dd  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000b7e4  test    rax, rax
0x18000b7e7  jz      short loc_18000B7F1
0x18000b7e9  mov     rcx, rbx
0x18000b7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f1  add     rsp, 20h
0x18000b7f5  pop     rbx
0x18000b7f6  retn
```
