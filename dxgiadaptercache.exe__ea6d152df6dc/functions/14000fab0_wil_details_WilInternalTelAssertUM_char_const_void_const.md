# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x14000fab0`
- end: `0x14000fb55`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000fab0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fb33`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fb33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb1c`

## string_xrefs

- `0x14000fb15`: `ntdll.dll`

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
0x14000fab0  push    rbp
0x14000fab2  mov     rbp, rsp
0x14000fab5  sub     rsp, 60h
0x14000fab9  xorps   xmm0, xmm0
0x14000fabc  xor     eax, eax
0x14000fabe  movups  [rbp+var_40], xmm0
0x14000fac2  movups  [rbp+var_30], xmm0
0x14000fac6  movups  [rbp+var_20], xmm0
0x14000faca  mov     [rbp+var_10], rax
0x14000face  mov     dword ptr [rbp+var_40], 0Bh
0x14000fad5  lea     rax, __ImageBase
0x14000fadc  mov     qword ptr [rbp+var_40+8], rax
0x14000fae0  mov     qword ptr [rbp+var_30], rdx
0x14000fae4  mov     byte ptr [rbp+var_30+8], 0
0x14000fae8  mov     qword ptr [rbp+var_20], 0
0x14000faf0  or      eax, 0FFFFFFFFh
0x14000faf3  mov     dword ptr [rbp+var_20+8], eax
0x14000faf6  mov     dword ptr [rbp+var_20+0Ch], eax
0x14000faf9  mov     byte ptr [rbp+var_10], 1
0x14000fafd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000fb04  test    rax, rax
0x14000fb07  jnz     short loc_14000FB45
0x14000fb09  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fb10  test    rax, rax
0x14000fb13  jnz     short loc_14000FB29
0x14000fb15  lea     rcx, ModuleName; "ntdll.dll"
0x14000fb1c  call    cs:__imp_GetModuleHandleW
0x14000fb22  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fb29  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14000fb30  mov     rcx, rax; hModule
0x14000fb33  call    cs:__imp_GetProcAddress
0x14000fb39  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000fb40  test    rax, rax
0x14000fb43  jz      short loc_14000FB4F
0x14000fb45  lea     rcx, [rbp+var_40]
0x14000fb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb4e  nop
0x14000fb4f  add     rsp, 60h
0x14000fb53  pop     rbp
0x14000fb54  retn
```
