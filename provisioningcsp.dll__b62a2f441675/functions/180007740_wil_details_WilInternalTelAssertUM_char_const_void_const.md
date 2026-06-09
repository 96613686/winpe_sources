# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x180007740`
- end: `0x1800077f2`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `178`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007740`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800077c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800077ac`

## string_xrefs

- `0x1800077a5`: `ntdll.dll`

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
0x180007740  push    rbp
0x180007742  mov     rbp, rsp
0x180007745  sub     rsp, 60h
0x180007749  xorps   xmm0, xmm0
0x18000774c  xor     eax, eax
0x18000774e  movups  [rbp+var_40], xmm0
0x180007752  movups  [rbp+var_30], xmm0
0x180007756  movups  [rbp+var_20], xmm0
0x18000775a  mov     [rbp+var_10], rax
0x18000775e  mov     dword ptr [rbp+var_40], 0Bh
0x180007765  lea     rax, __ImageBase
0x18000776c  mov     qword ptr [rbp+var_40+8], rax
0x180007770  mov     qword ptr [rbp+var_30], rdx
0x180007774  mov     byte ptr [rbp+var_30+8], 0
0x180007778  mov     qword ptr [rbp+var_20], 0
0x180007780  or      eax, 0FFFFFFFFh
0x180007783  mov     dword ptr [rbp+var_20+8], eax
0x180007786  mov     dword ptr [rbp+var_20+0Ch], eax
0x180007789  mov     byte ptr [rbp+var_10], 1
0x18000778d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x180007794  test    rax, rax
0x180007797  jnz     short loc_1800077E1
0x180007799  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800077a0  test    rax, rax
0x1800077a3  jnz     short loc_1800077BF
0x1800077a5  lea     rcx, ModuleName; "ntdll.dll"
0x1800077ac  call    cs:__imp_GetModuleHandleW
0x1800077b3  nop     dword ptr [rax+rax+00h]
0x1800077b8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800077bf  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800077c6  mov     rcx, rax; hModule
0x1800077c9  call    cs:__imp_GetProcAddress
0x1800077d0  nop     dword ptr [rax+rax+00h]
0x1800077d5  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x1800077dc  test    rax, rax
0x1800077df  jz      short loc_1800077EB
0x1800077e1  lea     rcx, [rbp+var_40]
0x1800077e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ea  nop
0x1800077eb  add     rsp, 60h
0x1800077ef  pop     rbp
0x1800077f0  retn
```
