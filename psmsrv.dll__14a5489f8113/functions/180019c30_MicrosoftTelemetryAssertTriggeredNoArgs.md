# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180019c30`
- end: `0x180019cd2`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `27`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800017b0`
- `0x180002740`
- `0x180003700`
- `0x1800049a0`
- `0x1800053a4`
- `0x180007fd0`
- `0x180008360`
- `0x180008840`
- `0x180008cc0`
- `0x180008f10`
- `0x1800092b4`
- `0x180009630`
- `0x180009b40`
- `0x18000abf0`
- `0x18000b894`
- `0x18000c5b8`
- `0x18000cb7c`
- `0x18000e0f4`
- `0x18000e640`
- `0x1800140bc`
- `0x180014530`
- `0x180014974`
- `0x180015d60`
- `0x180016254`
- `0x180017da0`
- `0x180019bfc`
- `0x18002478c`

## callees

- `0x180019c30`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019c6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019c6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180019c51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180019c51`

## string_xrefs

- `0x180019c45`: `ntdll.dll`

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
0x180019c30  push    rbp
0x180019c32  mov     rbp, rsp
0x180019c35  sub     rsp, 60h
0x180019c39  lea     r8, [rbp+phModule]; phModule
0x180019c3d  mov     [rbp+phModule], 0
0x180019c45  lea     rdx, ModuleName; "ntdll.dll"
0x180019c4c  mov     ecx, 2; dwFlags
0x180019c51  call    cs:__imp_GetModuleHandleExA
0x180019c57  test    eax, eax
0x180019c59  jz      short loc_180019CCC
0x180019c5b  mov     rcx, [rbp+phModule]; hModule
0x180019c5f  test    rcx, rcx
0x180019c62  jz      short loc_180019CCC
0x180019c64  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x180019c6b  call    cs:__imp_GetProcAddress
0x180019c71  mov     rdx, rax
0x180019c74  test    rax, rax
0x180019c77  jz      short loc_180019CCC
0x180019c79  xor     eax, eax
0x180019c7b  lea     rcx, [rbp+var_40]
0x180019c7f  mov     [rbp+var_10], eax
0x180019c82  xorps   xmm0, xmm0
0x180019c85  movups  [rbp+var_20], xmm0
0x180019c89  lea     rax, __ImageBase
0x180019c90  movups  [rbp+var_40], xmm0
0x180019c94  mov     qword ptr [rbp+var_40+8], rax
0x180019c98  mov     rax, [rbp+8]
0x180019c9c  movups  [rbp+var_30], xmm0
0x180019ca0  mov     qword ptr [rbp+var_30], rax
0x180019ca4  or      eax, 0FFFFFFFFh
0x180019ca7  mov     dword ptr [rbp+var_20+8], eax
0x180019caa  mov     dword ptr [rbp+var_20+0Ch], eax
0x180019cad  mov     rax, rdx
0x180019cb0  mov     dword ptr [rbp+var_40], 0Bh
0x180019cb7  mov     byte ptr [rbp+var_10], 1
0x180019cbb  mov     byte ptr [rbp+var_30+8], 0
0x180019cbf  mov     qword ptr [rbp+var_20], 0
0x180019cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ccc  add     rsp, 60h
0x180019cd0  pop     rbp
0x180019cd1  retn
```
