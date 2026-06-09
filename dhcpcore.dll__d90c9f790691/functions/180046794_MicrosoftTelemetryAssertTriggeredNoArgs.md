# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180046794`
- end: `0x180046836`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003d30`
- `0x180005330`
- `0x180006440`
- `0x18001c46c`
- `0x180023928`
- `0x1800317a4`

## callees

- `0x180046794`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800467b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800467b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800467cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800467cf`

## string_xrefs

- `0x1800467a9`: `ntdll.dll`

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
0x180046794  push    rbp
0x180046796  mov     rbp, rsp
0x180046799  sub     rsp, 60h
0x18004679d  lea     r8, [rbp+phModule]; phModule
0x1800467a1  mov     [rbp+phModule], 0
0x1800467a9  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800467b0  mov     ecx, 2; dwFlags
0x1800467b5  call    cs:__imp_GetModuleHandleExA
0x1800467bb  test    eax, eax
0x1800467bd  jz      short loc_180046830
0x1800467bf  mov     rcx, [rbp+phModule]; hModule
0x1800467c3  test    rcx, rcx
0x1800467c6  jz      short loc_180046830
0x1800467c8  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800467cf  call    cs:__imp_GetProcAddress
0x1800467d5  mov     rdx, rax
0x1800467d8  test    rax, rax
0x1800467db  jz      short loc_180046830
0x1800467dd  xor     eax, eax
0x1800467df  lea     rcx, [rbp+var_40]
0x1800467e3  mov     [rbp+var_10], eax
0x1800467e6  xorps   xmm0, xmm0
0x1800467e9  movups  [rbp+var_20], xmm0
0x1800467ed  lea     rax, __ImageBase
0x1800467f4  movups  [rbp+var_40], xmm0
0x1800467f8  mov     qword ptr [rbp+var_40+8], rax
0x1800467fc  mov     rax, [rbp+8]
0x180046800  movups  [rbp+var_30], xmm0
0x180046804  mov     qword ptr [rbp+var_30], rax
0x180046808  or      eax, 0FFFFFFFFh
0x18004680b  mov     dword ptr [rbp+var_20+8], eax
0x18004680e  mov     dword ptr [rbp+var_20+0Ch], eax
0x180046811  mov     rax, rdx
0x180046814  mov     dword ptr [rbp+var_40], 0Bh
0x18004681b  mov     byte ptr [rbp+var_10], 1
0x18004681f  mov     byte ptr [rbp+var_30+8], 0
0x180046823  mov     qword ptr [rbp+var_20], 0
0x18004682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046830  add     rsp, 60h
0x180046834  pop     rbp
0x180046835  retn
```
