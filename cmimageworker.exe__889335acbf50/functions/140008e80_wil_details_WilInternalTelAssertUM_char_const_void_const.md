# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x140008e80`
- end: `0x140008f32`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `178`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140008e80`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008f09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008f09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008eec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008eec`

## string_xrefs

- `0x140008ee5`: `ntdll.dll`

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
  v5[1] = 0x140000000uLL;
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
0x140008e80  push    rbp
0x140008e82  mov     rbp, rsp
0x140008e85  sub     rsp, 60h
0x140008e89  xorps   xmm0, xmm0
0x140008e8c  xor     eax, eax
0x140008e8e  movups  [rbp+var_40], xmm0
0x140008e92  movups  [rbp+var_30], xmm0
0x140008e96  movups  [rbp+var_20], xmm0
0x140008e9a  mov     [rbp+var_10], rax
0x140008e9e  mov     dword ptr [rbp+var_40], 0Bh
0x140008ea5  lea     rax, cs:140000000h
0x140008eac  mov     qword ptr [rbp+var_40+8], rax
0x140008eb0  mov     qword ptr [rbp+var_30], rdx
0x140008eb4  mov     byte ptr [rbp+var_30+8], 0
0x140008eb8  mov     qword ptr [rbp+var_20], 0
0x140008ec0  or      eax, 0FFFFFFFFh
0x140008ec3  mov     dword ptr [rbp+var_20+8], eax
0x140008ec6  mov     dword ptr [rbp+var_20+0Ch], eax
0x140008ec9  mov     byte ptr [rbp+var_10], 1
0x140008ecd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x140008ed4  test    rax, rax
0x140008ed7  jnz     short loc_140008F21
0x140008ed9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008ee0  test    rax, rax
0x140008ee3  jnz     short loc_140008EFF
0x140008ee5  lea     rcx, ModuleName; "ntdll.dll"
0x140008eec  call    cs:__imp_GetModuleHandleW
0x140008ef3  nop     dword ptr [rax+rax+00h]
0x140008ef8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008eff  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x140008f06  mov     rcx, rax; hModule
0x140008f09  call    cs:__imp_GetProcAddress
0x140008f10  nop     dword ptr [rax+rax+00h]
0x140008f15  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x140008f1c  test    rax, rax
0x140008f1f  jz      short loc_140008F2B
0x140008f21  lea     rcx, [rbp+var_40]
0x140008f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f2a  nop
0x140008f2b  add     rsp, 60h
0x140008f2f  pop     rbp
0x140008f30  retn
```
