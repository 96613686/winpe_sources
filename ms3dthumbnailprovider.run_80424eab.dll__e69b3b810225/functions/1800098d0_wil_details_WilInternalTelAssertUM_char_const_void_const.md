# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x1800098d0`
- end: `0x180009975`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800098d0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180009953`
- `KERNEL32!GetProcAddress` at `0x180009953`
- `KERNEL32!GetModuleHandleW` at `0x18000993c`
- `KERNEL32!GetModuleHandleW` at `0x18000993c`

## string_xrefs

- `0x180009935`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilInternalTelAssertUM(wil::details *this, const char *a2, const void *a3)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD v5[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v6; // [rsp+30h] [rbp-30h]
  __int64 v7; // [rsp+40h] [rbp-20h]
  __int64 v8; // [rsp+48h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp-10h]

  v9 = 1;
  v5[0] = 11;
  v5[1] = 0x180000000uLL;
  v6 = (unsigned __int64)a2;
  v7 = 0;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  if ( `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert )
    goto LABEL_5;
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "MicrosoftTelemetryAssertTriggeredUM");
  `wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert = (__int64)ProcAddress;
  if ( ProcAddress )
LABEL_5:
    ((void (__fastcall *)(_QWORD *, const char *, const void *))ProcAddress)(v5, a2, a3);
}

```

## disassembly

```asm
0x1800098d0  push    rbp
0x1800098d2  mov     rbp, rsp
0x1800098d5  sub     rsp, 60h
0x1800098d9  xorps   xmm0, xmm0
0x1800098dc  xor     eax, eax
0x1800098de  movups  [rbp+var_40], xmm0
0x1800098e2  movups  [rbp+var_30], xmm0
0x1800098e6  movups  [rbp+var_20], xmm0
0x1800098ea  mov     [rbp+var_10], rax
0x1800098ee  mov     dword ptr [rbp+var_40], 0Bh
0x1800098f5  lea     rax, cs:180000000h
0x1800098fc  mov     qword ptr [rbp+var_40+8], rax
0x180009900  mov     qword ptr [rbp+var_30], rdx
0x180009904  mov     byte ptr [rbp+var_30+8], 0
0x180009908  mov     qword ptr [rbp+var_20], 0
0x180009910  or      eax, 0FFFFFFFFh
0x180009913  mov     dword ptr [rbp+var_20+8], eax
0x180009916  mov     dword ptr [rbp+var_20+0Ch], eax
0x180009919  mov     byte ptr [rbp+var_10], 1
0x18000991d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180009924  test    rax, rax
0x180009927  jnz     short loc_180009965
0x180009929  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009930  test    rax, rax
0x180009933  jnz     short loc_180009949
0x180009935  lea     rcx, ModuleName; "ntdll.dll"
0x18000993c  call    cs:__imp_GetModuleHandleW
0x180009942  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009949  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180009950  mov     rcx, rax; hModule
0x180009953  call    cs:__imp_GetProcAddress
0x180009959  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180009960  test    rax, rax
0x180009963  jz      short loc_18000996F
0x180009965  lea     rcx, [rbp+var_40]
0x180009969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996e  nop
0x18000996f  add     rsp, 60h
0x180009973  pop     rbp
0x180009974  retn
```
