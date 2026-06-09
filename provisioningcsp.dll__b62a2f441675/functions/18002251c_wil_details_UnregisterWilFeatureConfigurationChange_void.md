# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x18002251c`
- end: `0x180022588`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180013e98`

## callees

- `0x18002251c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022561`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022561`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022544`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022544`

## string_xrefs

- `0x18002253d`: `ntdll.dll`
- `0x180022557`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x18002251c  push    rbx
0x18002251e  sub     rsp, 20h
0x180022522  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180022529  mov     rbx, rcx
0x18002252c  test    rax, rax
0x18002252f  jnz     short loc_180022579
0x180022531  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022538  test    rax, rax
0x18002253b  jnz     short loc_180022557
0x18002253d  lea     rcx, ModuleName; "ntdll.dll"
0x180022544  call    cs:__imp_GetModuleHandleW
0x18002254b  nop     dword ptr [rax+rax+00h]
0x180022550  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022557  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18002255e  mov     rcx, rax; hModule
0x180022561  call    cs:__imp_GetProcAddress
0x180022568  nop     dword ptr [rax+rax+00h]
0x18002256d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180022574  test    rax, rax
0x180022577  jz      short loc_180022581
0x180022579  mov     rcx, rbx
0x18002257c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022581  add     rsp, 20h
0x180022585  pop     rbx
0x180022586  retn
```
