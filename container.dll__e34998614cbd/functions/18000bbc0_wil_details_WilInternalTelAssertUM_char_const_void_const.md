# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000bbc0`
- end: `0x18000bc72`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `178`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bbc0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bc2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc49`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000bc49`

## string_xrefs

- `0x18000bc25`: `ntdll.dll`

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
0x18000bbc0  push    rbp
0x18000bbc2  mov     rbp, rsp
0x18000bbc5  sub     rsp, 60h
0x18000bbc9  xorps   xmm0, xmm0
0x18000bbcc  xor     eax, eax
0x18000bbce  movups  [rbp+var_40], xmm0
0x18000bbd2  movups  [rbp+var_30], xmm0
0x18000bbd6  movups  [rbp+var_20], xmm0
0x18000bbda  mov     [rbp+var_10], rax
0x18000bbde  mov     dword ptr [rbp+var_40], 0Bh
0x18000bbe5  lea     rax, __ImageBase
0x18000bbec  mov     qword ptr [rbp+var_40+8], rax
0x18000bbf0  mov     qword ptr [rbp+var_30], rdx
0x18000bbf4  mov     byte ptr [rbp+var_30+8], 0
0x18000bbf8  mov     qword ptr [rbp+var_20], 0
0x18000bc00  or      eax, 0FFFFFFFFh
0x18000bc03  mov     dword ptr [rbp+var_20+8], eax
0x18000bc06  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000bc09  mov     byte ptr [rbp+var_10], 1
0x18000bc0d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000bc14  test    rax, rax
0x18000bc17  jnz     short loc_18000BC61
0x18000bc19  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bc20  test    rax, rax
0x18000bc23  jnz     short loc_18000BC3F
0x18000bc25  lea     rcx, ModuleName; "ntdll.dll"
0x18000bc2c  call    cs:__imp_GetModuleHandleW
0x18000bc33  nop     dword ptr [rax+rax+00h]
0x18000bc38  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bc3f  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000bc46  mov     rcx, rax; hModule
0x18000bc49  call    cs:__imp_GetProcAddress
0x18000bc50  nop     dword ptr [rax+rax+00h]
0x18000bc55  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000bc5c  test    rax, rax
0x18000bc5f  jz      short loc_18000BC6B
0x18000bc61  lea     rcx, [rbp+var_40]
0x18000bc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc6a  nop
0x18000bc6b  add     rsp, 60h
0x18000bc6f  pop     rbp
0x18000bc70  retn
```
