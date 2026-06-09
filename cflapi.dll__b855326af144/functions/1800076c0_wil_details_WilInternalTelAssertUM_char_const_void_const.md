# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x1800076c0`
- end: `0x180007765`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076c0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000772c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000772c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007743`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007743`

## string_xrefs

- `0x180007725`: `ntdll.dll`

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
0x1800076c0  push    rbp
0x1800076c2  mov     rbp, rsp
0x1800076c5  sub     rsp, 60h
0x1800076c9  xorps   xmm0, xmm0
0x1800076cc  xor     eax, eax
0x1800076ce  movups  [rbp+var_40], xmm0
0x1800076d2  movups  [rbp+var_30], xmm0
0x1800076d6  movups  [rbp+var_20], xmm0
0x1800076da  mov     [rbp+var_10], rax
0x1800076de  mov     dword ptr [rbp+var_40], 0Bh
0x1800076e5  lea     rax, __ImageBase
0x1800076ec  mov     qword ptr [rbp+var_40+8], rax
0x1800076f0  mov     qword ptr [rbp+var_30], rdx
0x1800076f4  mov     byte ptr [rbp+var_30+8], 0
0x1800076f8  mov     qword ptr [rbp+var_20], 0
0x180007700  or      eax, 0FFFFFFFFh
0x180007703  mov     dword ptr [rbp+var_20+8], eax
0x180007706  mov     dword ptr [rbp+var_20+0Ch], eax
0x180007709  mov     byte ptr [rbp+var_10], 1
0x18000770d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180007714  test    rax, rax
0x180007717  jnz     short loc_180007755
0x180007719  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007720  test    rax, rax
0x180007723  jnz     short loc_180007739
0x180007725  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000772c  call    cs:__imp_GetModuleHandleW
0x180007732  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007739  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180007740  mov     rcx, rax; hModule
0x180007743  call    cs:__imp_GetProcAddress
0x180007749  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180007750  test    rax, rax
0x180007753  jz      short loc_18000775F
0x180007755  lea     rcx, [rbp+var_40]
0x180007759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000775e  nop
0x18000775f  add     rsp, 60h
0x180007763  pop     rbp
0x180007764  retn
```
