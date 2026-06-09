# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x140018310`
- end: `0x14001837c`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140015c3c`

## callees

- `0x140018310`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018355`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018355`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140018338`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140018338`

## string_xrefs

- `0x140018331`: `ntdll.dll`
- `0x14001834b`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x140018310  push    rbx
0x140018312  sub     rsp, 20h
0x140018316  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14001831d  mov     rbx, rcx
0x140018320  test    rax, rax
0x140018323  jnz     short loc_14001836D
0x140018325  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001832c  test    rax, rax
0x14001832f  jnz     short loc_14001834B
0x140018331  lea     rcx, ModuleName; "ntdll.dll"
0x140018338  call    cs:__imp_GetModuleHandleW
0x14001833f  nop     dword ptr [rax+rax+00h]
0x140018344  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001834b  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x140018352  mov     rcx, rax; hModule
0x140018355  call    cs:__imp_GetProcAddress
0x14001835c  nop     dword ptr [rax+rax+00h]
0x140018361  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140018368  test    rax, rax
0x14001836b  jz      short loc_140018375
0x14001836d  mov     rcx, rbx
0x140018370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018375  add     rsp, 20h
0x140018379  pop     rbx
0x14001837a  retn
```
