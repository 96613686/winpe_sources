# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180014f30`
- end: `0x180014fd5`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014f30`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180014f9c`
- `KERNEL32!GetModuleHandleW` at `0x180014f9c`
- `KERNEL32!GetProcAddress` at `0x180014fb3`
- `KERNEL32!GetProcAddress` at `0x180014fb3`

## string_xrefs

- `0x180014f95`: `ntdll.dll`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180014f30  push    rbp
0x180014f32  mov     rbp, rsp
0x180014f35  sub     rsp, 60h
0x180014f39  xorps   xmm0, xmm0
0x180014f3c  xor     eax, eax
0x180014f3e  movups  [rbp+var_40], xmm0
0x180014f42  movups  [rbp+var_30], xmm0
0x180014f46  movups  [rbp+var_20], xmm0
0x180014f4a  mov     [rbp+var_10], rax
0x180014f4e  mov     dword ptr [rbp+var_40], 0Bh
0x180014f55  lea     rax, cs:180000000h
0x180014f5c  mov     qword ptr [rbp+var_40+8], rax
0x180014f60  mov     qword ptr [rbp+var_30], rdx
0x180014f64  mov     byte ptr [rbp+var_30+8], 0
0x180014f68  mov     qword ptr [rbp+var_20], 0
0x180014f70  or      eax, 0FFFFFFFFh
0x180014f73  mov     dword ptr [rbp+var_20+8], eax
0x180014f76  mov     dword ptr [rbp+var_20+0Ch], eax
0x180014f79  mov     byte ptr [rbp+var_10], 1
0x180014f7d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180014f84  test    rax, rax
0x180014f87  jnz     short loc_180014FC5
0x180014f89  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014f90  test    rax, rax
0x180014f93  jnz     short loc_180014FA9
0x180014f95  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180014f9c  call    cs:__imp_GetModuleHandleW
0x180014fa2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014fa9  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180014fb0  mov     rcx, rax; hModule
0x180014fb3  call    cs:__imp_GetProcAddress
0x180014fb9  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180014fc0  test    rax, rax
0x180014fc3  jz      short loc_180014FCF
0x180014fc5  lea     rcx, [rbp+var_40]
0x180014fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fce  nop
0x180014fcf  add     rsp, 60h
0x180014fd3  pop     rbp
0x180014fd4  retn
```
