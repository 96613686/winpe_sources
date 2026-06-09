# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x180009314`
- end: `0x180009380`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003d68`

## callees

- `0x180009314`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000933c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000933c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009359`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009359`

## string_xrefs

- `0x180009335`: `ntdll.dll`
- `0x18000934f`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180009314  push    rbx
0x180009316  sub     rsp, 20h
0x18000931a  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180009321  mov     rbx, rcx
0x180009324  test    rax, rax
0x180009327  jnz     short loc_180009371
0x180009329  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009330  test    rax, rax
0x180009333  jnz     short loc_18000934F
0x180009335  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000933c  call    cs:__imp_GetModuleHandleW
0x180009343  nop     dword ptr [rax+rax+00h]
0x180009348  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000934f  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180009356  mov     rcx, rax; hModule
0x180009359  call    cs:__imp_GetProcAddress
0x180009360  nop     dword ptr [rax+rax+00h]
0x180009365  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000936c  test    rax, rax
0x18000936f  jz      short loc_180009379
0x180009371  mov     rcx, rbx
0x180009374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009379  add     rsp, 20h
0x18000937d  pop     rbx
0x18000937e  retn
```
