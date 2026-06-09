# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x14000ad90`
- end: `0x14000ae35`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000ad90`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000adfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000adfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ae13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ae13`

## string_xrefs

- `0x14000adf5`: `ntdll.dll`

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
  v5[1] = &_ImageBase;
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
0x14000ad90  push    rbp
0x14000ad92  mov     rbp, rsp
0x14000ad95  sub     rsp, 60h
0x14000ad99  xorps   xmm0, xmm0
0x14000ad9c  xor     eax, eax
0x14000ad9e  movups  [rbp+var_40], xmm0
0x14000ada2  movups  [rbp+var_30], xmm0
0x14000ada6  movups  [rbp+var_20], xmm0
0x14000adaa  mov     [rbp+var_10], rax
0x14000adae  mov     dword ptr [rbp+var_40], 0Bh
0x14000adb5  lea     rax, __ImageBase
0x14000adbc  mov     qword ptr [rbp+var_40+8], rax
0x14000adc0  mov     qword ptr [rbp+var_30], rdx
0x14000adc4  mov     byte ptr [rbp+var_30+8], 0
0x14000adc8  mov     qword ptr [rbp+var_20], 0
0x14000add0  or      eax, 0FFFFFFFFh
0x14000add3  mov     dword ptr [rbp+var_20+8], eax
0x14000add6  mov     dword ptr [rbp+var_20+0Ch], eax
0x14000add9  mov     byte ptr [rbp+var_10], 1
0x14000addd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000ade4  test    rax, rax
0x14000ade7  jnz     short loc_14000AE25
0x14000ade9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000adf0  test    rax, rax
0x14000adf3  jnz     short loc_14000AE09
0x14000adf5  lea     rcx, ModuleName; "ntdll.dll"
0x14000adfc  call    cs:__imp_GetModuleHandleW
0x14000ae02  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ae09  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14000ae10  mov     rcx, rax; hModule
0x14000ae13  call    cs:__imp_GetProcAddress
0x14000ae19  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000ae20  test    rax, rax
0x14000ae23  jz      short loc_14000AE2F
0x14000ae25  lea     rcx, [rbp+var_40]
0x14000ae29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae2e  nop
0x14000ae2f  add     rsp, 60h
0x14000ae33  pop     rbp
0x14000ae34  retn
```
