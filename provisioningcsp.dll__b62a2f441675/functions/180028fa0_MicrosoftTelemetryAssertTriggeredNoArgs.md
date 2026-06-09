# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180028fa0`
- end: `0x18002904f`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a730`

## callees

- `0x180028fa0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028fe1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028fe1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180028fc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180028fc1`

## string_xrefs

- `0x180028fb5`: `ntdll.dll`

## pseudocode

```c
int MicrosoftTelemetryAssertTriggeredNoArgs()
{
  FARPROC ProcAddress; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-40h] BYREF
  __int128 v3; // [rsp+30h] [rbp-30h]
  __int64 v4; // [rsp+40h] [rbp-20h]
  __int64 v5; // [rsp+48h] [rbp-18h]
  int v6; // [rsp+50h] [rbp-10h]
  unsigned __int64 retaddr; // [rsp+68h] [rbp+8h]
  HMODULE phModule; // [rsp+70h] [rbp+10h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v6 = 1;
        v2[1] = &_ImageBase;
        v3 = retaddr;
        v5 = -1;
        v2[0] = 11;
        v4 = 0;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180028fa0  push    rbp
0x180028fa2  mov     rbp, rsp
0x180028fa5  sub     rsp, 60h
0x180028fa9  lea     r8, [rbp+phModule]; phModule
0x180028fad  mov     [rbp+phModule], 0
0x180028fb5  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180028fbc  mov     ecx, 2; dwFlags
0x180028fc1  call    cs:__imp_GetModuleHandleExA
0x180028fc8  nop     dword ptr [rax+rax+00h]
0x180028fcd  test    eax, eax
0x180028fcf  jz      short loc_180029048
0x180028fd1  mov     rcx, [rbp+phModule]; hModule
0x180028fd5  test    rcx, rcx
0x180028fd8  jz      short loc_180029048
0x180028fda  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180028fe1  call    cs:__imp_GetProcAddress
0x180028fe8  nop     dword ptr [rax+rax+00h]
0x180028fed  mov     rdx, rax
0x180028ff0  test    rax, rax
0x180028ff3  jz      short loc_180029048
0x180028ff5  xor     eax, eax
0x180028ff7  lea     rcx, [rbp+var_40]
0x180028ffb  mov     [rbp+var_10], eax
0x180028ffe  xorps   xmm0, xmm0
0x180029001  movups  [rbp+var_20], xmm0
0x180029005  lea     rax, __ImageBase
0x18002900c  movups  [rbp+var_40], xmm0
0x180029010  mov     qword ptr [rbp+var_40+8], rax
0x180029014  mov     rax, [rbp+8]
0x180029018  movups  [rbp+var_30], xmm0
0x18002901c  mov     qword ptr [rbp+var_30], rax
0x180029020  or      eax, 0FFFFFFFFh
0x180029023  mov     dword ptr [rbp+var_20+8], eax
0x180029026  mov     dword ptr [rbp+var_20+0Ch], eax
0x180029029  mov     rax, rdx
0x18002902c  mov     dword ptr [rbp+var_40], 0Bh
0x180029033  mov     byte ptr [rbp+var_10], 1
0x180029037  mov     byte ptr [rbp+var_30+8], 0
0x18002903b  mov     qword ptr [rbp+var_20], 0
0x180029043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029048  add     rsp, 60h
0x18002904c  pop     rbp
0x18002904d  retn
```
