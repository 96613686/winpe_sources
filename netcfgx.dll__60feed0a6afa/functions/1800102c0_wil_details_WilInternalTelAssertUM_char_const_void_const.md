# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x1800102c0`
- end: `0x180010365`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800102c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001032c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001032c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010343`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010343`

## string_xrefs

- `0x180010325`: `ntdll.dll`

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
0x1800102c0  push    rbp
0x1800102c2  mov     rbp, rsp
0x1800102c5  sub     rsp, 60h
0x1800102c9  xorps   xmm0, xmm0
0x1800102cc  xor     eax, eax
0x1800102ce  movups  [rbp+var_40], xmm0
0x1800102d2  movups  [rbp+var_30], xmm0
0x1800102d6  movups  [rbp+var_20], xmm0
0x1800102da  mov     [rbp+var_10], rax
0x1800102de  mov     dword ptr [rbp+var_40], 0Bh
0x1800102e5  lea     rax, __ImageBase
0x1800102ec  mov     qword ptr [rbp+var_40+8], rax
0x1800102f0  mov     qword ptr [rbp+var_30], rdx
0x1800102f4  mov     byte ptr [rbp+var_30+8], 0
0x1800102f8  mov     qword ptr [rbp+var_20], 0
0x180010300  or      eax, 0FFFFFFFFh
0x180010303  mov     dword ptr [rbp+var_20+8], eax
0x180010306  mov     dword ptr [rbp+var_20+0Ch], eax
0x180010309  mov     byte ptr [rbp+var_10], 1
0x18001030d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180010314  test    rax, rax
0x180010317  jnz     short loc_180010355
0x180010319  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010320  test    rax, rax
0x180010323  jnz     short loc_180010339
0x180010325  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001032c  call    cs:__imp_GetModuleHandleW
0x180010332  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010339  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180010340  mov     rcx, rax; hModule
0x180010343  call    cs:__imp_GetProcAddress
0x180010349  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180010350  test    rax, rax
0x180010353  jz      short loc_18001035F
0x180010355  lea     rcx, [rbp+var_40]
0x180010359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001035e  nop
0x18001035f  add     rsp, 60h
0x180010363  pop     rbp
0x180010364  retn
```
