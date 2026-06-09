# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001088c`
- end: `0x18001092e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f90`

## callees

- `0x18001088c`
- `0x180014010`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetModuleHandleExA` at `0x1800108ad`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetModuleHandleExA` at `0x1800108ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108c7`

## string_xrefs

- `0x1800108a1`: `ntdll.dll`

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
0x18001088c  push    rbp
0x18001088e  mov     rbp, rsp
0x180010891  sub     rsp, 60h
0x180010895  lea     r8, [rbp+phModule]; phModule
0x180010899  mov     [rbp+phModule], 0
0x1800108a1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800108a8  mov     ecx, 2; dwFlags
0x1800108ad  call    cs:__imp_GetModuleHandleExA
0x1800108b3  test    eax, eax
0x1800108b5  jz      short loc_180010928
0x1800108b7  mov     rcx, [rbp+phModule]; hModule
0x1800108bb  test    rcx, rcx
0x1800108be  jz      short loc_180010928
0x1800108c0  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x1800108c7  call    cs:__imp_GetProcAddress
0x1800108cd  mov     rdx, rax
0x1800108d0  test    rax, rax
0x1800108d3  jz      short loc_180010928
0x1800108d5  xor     eax, eax
0x1800108d7  lea     rcx, [rbp+var_40]
0x1800108db  mov     [rbp+var_10], eax
0x1800108de  xorps   xmm0, xmm0
0x1800108e1  movups  [rbp+var_20], xmm0
0x1800108e5  lea     rax, __ImageBase
0x1800108ec  movups  [rbp+var_40], xmm0
0x1800108f0  mov     qword ptr [rbp+var_40+8], rax
0x1800108f4  mov     rax, [rbp+8]
0x1800108f8  movups  [rbp+var_30], xmm0
0x1800108fc  mov     qword ptr [rbp+var_30], rax
0x180010900  or      eax, 0FFFFFFFFh
0x180010903  mov     dword ptr [rbp+var_20+8], eax
0x180010906  mov     dword ptr [rbp+var_20+0Ch], eax
0x180010909  mov     rax, rdx
0x18001090c  mov     dword ptr [rbp+var_40], 0Bh
0x180010913  mov     byte ptr [rbp+var_10], 1
0x180010917  mov     byte ptr [rbp+var_30+8], 0
0x18001091b  mov     qword ptr [rbp+var_20], 0
0x180010923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010928  add     rsp, 60h
0x18001092c  pop     rbp
0x18001092d  retn
```
