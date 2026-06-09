# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x1400096f8`
- end: `0x140009764`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140003cb4`

## callees

- `0x1400096f8`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009720`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009720`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000973d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000973d`

## string_xrefs

- `0x140009719`: `ntdll.dll`
- `0x140009733`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1400096f8  push    rbx
0x1400096fa  sub     rsp, 20h
0x1400096fe  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140009705  mov     rbx, rcx
0x140009708  test    rax, rax
0x14000970b  jnz     short loc_140009755
0x14000970d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009714  test    rax, rax
0x140009717  jnz     short loc_140009733
0x140009719  lea     rcx, ModuleName; "ntdll.dll"
0x140009720  call    cs:__imp_GetModuleHandleW
0x140009727  nop     dword ptr [rax+rax+00h]
0x14000972c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009733  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14000973a  mov     rcx, rax; hModule
0x14000973d  call    cs:__imp_GetProcAddress
0x140009744  nop     dword ptr [rax+rax+00h]
0x140009749  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140009750  test    rax, rax
0x140009753  jz      short loc_14000975D
0x140009755  mov     rcx, rbx
0x140009758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000975d  add     rsp, 20h
0x140009761  pop     rbx
0x140009762  retn
```
