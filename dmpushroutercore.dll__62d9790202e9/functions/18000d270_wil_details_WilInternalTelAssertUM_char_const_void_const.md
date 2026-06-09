# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000d270`
- end: `0x18000d315`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d270`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d2dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d2f3`

## string_xrefs

- `0x18000d2d5`: `ntdll.dll`

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
0x18000d270  push    rbp
0x18000d272  mov     rbp, rsp
0x18000d275  sub     rsp, 60h
0x18000d279  xorps   xmm0, xmm0
0x18000d27c  xor     eax, eax
0x18000d27e  movups  [rbp+var_40], xmm0
0x18000d282  movups  [rbp+var_30], xmm0
0x18000d286  movups  [rbp+var_20], xmm0
0x18000d28a  mov     [rbp+var_10], rax
0x18000d28e  mov     dword ptr [rbp+var_40], 0Bh
0x18000d295  lea     rax, __ImageBase
0x18000d29c  mov     qword ptr [rbp+var_40+8], rax
0x18000d2a0  mov     qword ptr [rbp+var_30], rdx
0x18000d2a4  mov     byte ptr [rbp+var_30+8], 0
0x18000d2a8  mov     qword ptr [rbp+var_20], 0
0x18000d2b0  or      eax, 0FFFFFFFFh
0x18000d2b3  mov     dword ptr [rbp+var_20+8], eax
0x18000d2b6  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000d2b9  mov     byte ptr [rbp+var_10], 1
0x18000d2bd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000d2c4  test    rax, rax
0x18000d2c7  jnz     short loc_18000D305
0x18000d2c9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d2d0  test    rax, rax
0x18000d2d3  jnz     short loc_18000D2E9
0x18000d2d5  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000d2dc  call    cs:__imp_GetModuleHandleW
0x18000d2e2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d2e9  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000d2f0  mov     rcx, rax; hModule
0x18000d2f3  call    cs:__imp_GetProcAddress
0x18000d2f9  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000d300  test    rax, rax
0x18000d303  jz      short loc_18000D30F
0x18000d305  lea     rcx, [rbp+var_40]
0x18000d309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d30e  nop
0x18000d30f  add     rsp, 60h
0x18000d313  pop     rbp
0x18000d314  retn
```
