# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18002f38c`
- end: `0x18002f435`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `169`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b30`
- `0x180004750`
- `0x1800047e0`
- `0x1800048c0`
- `0x180006f50`
- `0x180011310`
- `0x180014cb0`
- `0x180016650`
- `0x1800169f0`
- `0x180017044`
- `0x180017718`
- `0x180017c20`
- `0x18001fb90`
- `0x1800205fc`

## callees

- `0x18002f38c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f3d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f3d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002f3b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002f3b8`

## string_xrefs

- `0x18002f3ac`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, int a2, int a3)
{
  FARPROC ProcAddress; // rax
  HMODULE phModule; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v9[5]; // [rsp+28h] [rbp-40h] BYREF
  int v10; // [rsp+50h] [rbp-18h]
  int v11; // [rsp+54h] [rbp-14h]
  int v12; // [rsp+58h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+20h]

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v12 = 1;
        v9[1] = &_ImageBase;
        v9[3] = 1;
        v9[2] = retaddr;
        v9[0] = 11;
        v9[4] = a1;
        v10 = a2;
        v11 = a3;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v9);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18002f38c  push    rbp
0x18002f38e  push    rbx
0x18002f38f  push    rsi
0x18002f390  push    rdi
0x18002f391  mov     rbp, rsp
0x18002f394  sub     rsp, 68h
0x18002f398  mov     ebx, r8d
0x18002f39b  mov     [rbp+phModule], 0
0x18002f3a3  mov     edi, edx
0x18002f3a5  lea     r8, [rbp+phModule]; phModule
0x18002f3a9  mov     rsi, rcx
0x18002f3ac  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18002f3b3  mov     ecx, 2; dwFlags
0x18002f3b8  call    cs:__imp_GetModuleHandleExA
0x18002f3be  test    eax, eax
0x18002f3c0  jz      short loc_18002F42C
0x18002f3c2  mov     rcx, [rbp+phModule]; hModule
0x18002f3c6  test    rcx, rcx
0x18002f3c9  jz      short loc_18002F42C
0x18002f3cb  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18002f3d2  call    cs:__imp_GetProcAddress
0x18002f3d8  mov     rdx, rax
0x18002f3db  test    rax, rax
0x18002f3de  jz      short loc_18002F42C
0x18002f3e0  xor     eax, eax
0x18002f3e2  lea     rcx, [rbp+var_40]
0x18002f3e6  mov     [rbp+var_10], eax
0x18002f3e9  xorps   xmm0, xmm0
0x18002f3ec  movups  [rbp+var_20], xmm0
0x18002f3f0  lea     rax, __ImageBase
0x18002f3f7  movups  [rbp+var_40], xmm0
0x18002f3fb  mov     qword ptr [rbp+var_40+8], rax
0x18002f3ff  mov     rax, [rbp+20h]
0x18002f403  movups  [rbp+var_30], xmm0
0x18002f407  mov     qword ptr [rbp+var_30], rax
0x18002f40b  mov     rax, rdx
0x18002f40e  mov     dword ptr [rbp+var_40], 0Bh
0x18002f415  mov     byte ptr [rbp+var_10], 1
0x18002f419  mov     byte ptr [rbp+var_30+8], 1
0x18002f41d  mov     qword ptr [rbp+var_20], rsi
0x18002f421  mov     dword ptr [rbp+var_20+8], edi
0x18002f424  mov     dword ptr [rbp+var_20+0Ch], ebx
0x18002f427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f42c  add     rsp, 68h
0x18002f430  pop     rdi
0x18002f431  pop     rsi
0x18002f432  pop     rbx
0x18002f433  pop     rbp
0x18002f434  retn
```
