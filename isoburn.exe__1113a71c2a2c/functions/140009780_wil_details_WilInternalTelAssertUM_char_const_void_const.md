# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x140009780`
- end: `0x140009824`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `164`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009780`
- `0x140010010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140009803`
- `KERNEL32!GetProcAddress` at `0x140009803`
- `KERNEL32!GetModuleHandleW` at `0x1400097ec`
- `KERNEL32!GetModuleHandleW` at `0x1400097ec`

## string_xrefs

- `0x1400097e5`: `ntdll.dll`

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
  v7 = 0;
  v5[1] = 0x140000000uLL;
  v8 = -1;
  ProcAddress = (FARPROC)`wil::details::WilInternalTelAssertUM'::`2'::pfnTelAssert;
  v5[0] = 11;
  v6 = (unsigned __int64)a2;
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
0x140009780  push    rbp
0x140009782  mov     rbp, rsp
0x140009785  sub     rsp, 60h
0x140009789  xor     eax, eax
0x14000978b  xorps   xmm0, xmm0
0x14000978e  mov     [rbp+var_10], rax
0x140009792  lea     rax, cs:140000000h
0x140009799  movups  [rbp+var_20], xmm0
0x14000979d  mov     qword ptr [rbp+var_20], 0
0x1400097a5  movups  [rbp+var_40], xmm0
0x1400097a9  mov     qword ptr [rbp+var_40+8], rax
0x1400097ad  or      eax, 0FFFFFFFFh
0x1400097b0  movups  [rbp+var_30], xmm0
0x1400097b4  mov     dword ptr [rbp+var_20+8], eax
0x1400097b7  mov     dword ptr [rbp+var_20+0Ch], eax
0x1400097ba  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1400097c1  mov     dword ptr [rbp+var_40], 0Bh
0x1400097c8  mov     qword ptr [rbp+var_30], rdx
0x1400097cc  mov     byte ptr [rbp+var_30+8], 0
0x1400097d0  mov     byte ptr [rbp+var_10], 1
0x1400097d4  test    rax, rax
0x1400097d7  jnz     short loc_140009815
0x1400097d9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400097e0  test    rax, rax
0x1400097e3  jnz     short loc_1400097F9
0x1400097e5  lea     rcx, aNtdllDll; "ntdll.dll"
0x1400097ec  call    cs:__imp_GetModuleHandleW
0x1400097f2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400097f9  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140009800  mov     rcx, rax; hModule
0x140009803  call    cs:__imp_GetProcAddress
0x140009809  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x140009810  test    rax, rax
0x140009813  jz      short loc_14000981E
0x140009815  lea     rcx, [rbp+var_40]
0x140009819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000981e  add     rsp, 60h
0x140009822  pop     rbp
0x140009823  retn
```
