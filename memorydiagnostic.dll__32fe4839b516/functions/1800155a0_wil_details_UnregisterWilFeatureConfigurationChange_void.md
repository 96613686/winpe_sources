# wil::details::UnregisterWilFeatureConfigurationChange(void *)

- ea: `0x1800155a0`
- end: `0x18001560c`
- name: `?UnregisterWilFeatureConfigurationChange@details@wil@@YAXPEAX@Z`
- size: `108`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800081f8`

## callees

- `0x1800155a0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800155c8`
- `KERNEL32!GetModuleHandleW` at `0x1800155c8`
- `KERNEL32!GetProcAddress` at `0x1800155e5`
- `KERNEL32!GetProcAddress` at `0x1800155e5`

## string_xrefs

- `0x1800155c1`: `ntdll.dll`
- `0x1800155db`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
0x1800155a0  push    rbx
0x1800155a2  sub     rsp, 20h
0x1800155a6  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800155ad  mov     rbx, rcx
0x1800155b0  test    rax, rax
0x1800155b3  jnz     short loc_1800155FD
0x1800155b5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800155bc  test    rax, rax
0x1800155bf  jnz     short loc_1800155DB
0x1800155c1  lea     rcx, ModuleName; "ntdll.dll"
0x1800155c8  call    cs:__imp_GetModuleHandleW
0x1800155cf  nop     dword ptr [rax+rax+00h]
0x1800155d4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800155db  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800155e2  mov     rcx, rax; hModule
0x1800155e5  call    cs:__imp_GetProcAddress
0x1800155ec  nop     dword ptr [rax+rax+00h]
0x1800155f1  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800155f8  test    rax, rax
0x1800155fb  jz      short loc_180015605
0x1800155fd  mov     rcx, rbx
0x180015600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015605  add     rsp, 20h
0x180015609  pop     rbx
0x18001560a  retn
```
