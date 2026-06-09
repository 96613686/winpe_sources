# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x180025d6c`
- end: `0x180025dd8`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c224`

## callees

- `0x180025d6c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025db1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025db1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025d94`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025d94`

## string_xrefs

- `0x180025d8d`: `ntdll.dll`
- `0x180025da7`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180025d6c  push    rbx
0x180025d6e  sub     rsp, 20h
0x180025d72  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180025d79  mov     rbx, rcx
0x180025d7c  test    rax, rax
0x180025d7f  jnz     short loc_180025DC9
0x180025d81  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025d88  test    rax, rax
0x180025d8b  jnz     short loc_180025DA7
0x180025d8d  lea     rcx, ModuleName; "ntdll.dll"
0x180025d94  call    cs:__imp_GetModuleHandleW
0x180025d9b  nop     dword ptr [rax+rax+00h]
0x180025da0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025da7  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180025dae  mov     rcx, rax; hModule
0x180025db1  call    cs:__imp_GetProcAddress
0x180025db8  nop     dword ptr [rax+rax+00h]
0x180025dbd  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180025dc4  test    rax, rax
0x180025dc7  jz      short loc_180025DD1
0x180025dc9  mov     rcx, rbx
0x180025dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dd1  add     rsp, 20h
0x180025dd5  pop     rbx
0x180025dd6  retn
```
