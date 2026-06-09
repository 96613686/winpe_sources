# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x180018f50`
- end: `0x180018fbc`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001630c`

## callees

- `0x180018f50`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018f78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018f78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018f95`

## string_xrefs

- `0x180018f71`: `ntdll.dll`
- `0x180018f8b`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x180018f50  push    rbx
0x180018f52  sub     rsp, 20h
0x180018f56  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180018f5d  mov     rbx, rcx
0x180018f60  test    rax, rax
0x180018f63  jnz     short loc_180018FAD
0x180018f65  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018f6c  test    rax, rax
0x180018f6f  jnz     short loc_180018F8B
0x180018f71  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180018f78  call    cs:__imp_GetModuleHandleW
0x180018f7f  nop     dword ptr [rax+rax+00h]
0x180018f84  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018f8b  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180018f92  mov     rcx, rax; hModule
0x180018f95  call    cs:__imp_GetProcAddress
0x180018f9c  nop     dword ptr [rax+rax+00h]
0x180018fa1  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180018fa8  test    rax, rax
0x180018fab  jz      short loc_180018FB5
0x180018fad  mov     rcx, rbx
0x180018fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fb5  add     rsp, 20h
0x180018fb9  pop     rbx
0x180018fba  retn
```
