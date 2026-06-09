# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x18000b3c0`
- end: `0x18000b472`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `178`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b3c0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b449`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b449`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b42c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b42c`

## string_xrefs

- `0x18000b425`: `ntdll.dll`

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
0x18000b3c0  push    rbp
0x18000b3c2  mov     rbp, rsp
0x18000b3c5  sub     rsp, 60h
0x18000b3c9  xorps   xmm0, xmm0
0x18000b3cc  xor     eax, eax
0x18000b3ce  movups  [rbp+var_40], xmm0
0x18000b3d2  movups  [rbp+var_30], xmm0
0x18000b3d6  movups  [rbp+var_20], xmm0
0x18000b3da  mov     [rbp+var_10], rax
0x18000b3de  mov     dword ptr [rbp+var_40], 0Bh
0x18000b3e5  lea     rax, __ImageBase
0x18000b3ec  mov     qword ptr [rbp+var_40+8], rax
0x18000b3f0  mov     qword ptr [rbp+var_30], rdx
0x18000b3f4  mov     byte ptr [rbp+var_30+8], 0
0x18000b3f8  mov     qword ptr [rbp+var_20], 0
0x18000b400  or      eax, 0FFFFFFFFh
0x18000b403  mov     dword ptr [rbp+var_20+8], eax
0x18000b406  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000b409  mov     byte ptr [rbp+var_10], 1
0x18000b40d  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000b414  test    rax, rax
0x18000b417  jnz     short loc_18000B461
0x18000b419  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b420  test    rax, rax
0x18000b423  jnz     short loc_18000B43F
0x18000b425  lea     rcx, ModuleName; "ntdll.dll"
0x18000b42c  call    cs:__imp_GetModuleHandleW
0x18000b433  nop     dword ptr [rax+rax+00h]
0x18000b438  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b43f  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000b446  mov     rcx, rax; hModule
0x18000b449  call    cs:__imp_GetProcAddress
0x18000b450  nop     dword ptr [rax+rax+00h]
0x18000b455  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x18000b45c  test    rax, rax
0x18000b45f  jz      short loc_18000B46B
0x18000b461  lea     rcx, [rbp+var_40]
0x18000b465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b46a  nop
0x18000b46b  add     rsp, 60h
0x18000b46f  pop     rbp
0x18000b470  retn
```
