# wil::details::WilInternalTelAssertUM(char const *,void const *)

- ea: `0x14000cb80`
- end: `0x14000cc25`
- name: `?WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z`
- size: `165`
- prototype: `void __fastcall(wil::details *__hidden this, const char *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000cb80`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000cbec`
- `KERNEL32!GetModuleHandleW` at `0x14000cbec`
- `KERNEL32!GetProcAddress` at `0x14000cc03`
- `KERNEL32!GetProcAddress` at `0x14000cc03`

## string_xrefs

- `0x14000cbe5`: `ntdll.dll`

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
0x14000cb80  push    rbp
0x14000cb82  mov     rbp, rsp
0x14000cb85  sub     rsp, 60h
0x14000cb89  xorps   xmm0, xmm0
0x14000cb8c  xor     eax, eax
0x14000cb8e  movups  [rbp+var_40], xmm0
0x14000cb92  movups  [rbp+var_30], xmm0
0x14000cb96  movups  [rbp+var_20], xmm0
0x14000cb9a  mov     [rbp+var_10], rax
0x14000cb9e  mov     dword ptr [rbp+var_40], 0Bh
0x14000cba5  lea     rax, __ImageBase
0x14000cbac  mov     qword ptr [rbp+var_40+8], rax
0x14000cbb0  mov     qword ptr [rbp+var_30], rdx
0x14000cbb4  mov     byte ptr [rbp+var_30+8], 0
0x14000cbb8  mov     qword ptr [rbp+var_20], 0
0x14000cbc0  or      eax, 0FFFFFFFFh
0x14000cbc3  mov     dword ptr [rbp+var_20+8], eax
0x14000cbc6  mov     dword ptr [rbp+var_20+0Ch], eax
0x14000cbc9  mov     byte ptr [rbp+var_10], 1
0x14000cbcd  mov     rax, cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000cbd4  test    rax, rax
0x14000cbd7  jnz     short loc_14000CC15
0x14000cbd9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cbe0  test    rax, rax
0x14000cbe3  jnz     short loc_14000CBF9
0x14000cbe5  lea     rcx, ModuleName; "ntdll.dll"
0x14000cbec  call    cs:__imp_GetModuleHandleW
0x14000cbf2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cbf9  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14000cc00  mov     rcx, rax; hModule
0x14000cc03  call    cs:__imp_GetProcAddress
0x14000cc09  mov     cs:?pfnTelAssert@?1??WilInternalTelAssertUM@details@wil@@YAXPEBDPEBX@Z@4P6AXPEAUMicrosoftTelemetryAssertArgs@23@@ZEA, rax; void (*`wil::details::WilInternalTelAssertUM(char const *,void const *)'::`2'::pfnTelAssert)(wil::details::MicrosoftTelemetryAssertArgs *)
0x14000cc10  test    rax, rax
0x14000cc13  jz      short loc_14000CC1F
0x14000cc15  lea     rcx, [rbp+var_40]
0x14000cc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc1e  nop
0x14000cc1f  add     rsp, 60h
0x14000cc23  pop     rbp
0x14000cc24  retn
```
