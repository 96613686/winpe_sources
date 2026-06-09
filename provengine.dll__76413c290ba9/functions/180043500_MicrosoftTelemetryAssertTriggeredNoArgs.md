# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180043500`
- end: `0x1800435a2`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025660`
- `0x1800318a4`
- `0x1800346d8`

## callees

- `0x180043500`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004353b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004353b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180043521`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180043521`

## string_xrefs

- `0x180043515`: `ntdll.dll`

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
0x180043500  push    rbp
0x180043502  mov     rbp, rsp
0x180043505  sub     rsp, 60h
0x180043509  lea     r8, [rbp+phModule]; phModule
0x18004350d  mov     [rbp+phModule], 0
0x180043515  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18004351c  mov     ecx, 2; dwFlags
0x180043521  call    cs:__imp_GetModuleHandleExA
0x180043527  test    eax, eax
0x180043529  jz      short loc_18004359C
0x18004352b  mov     rcx, [rbp+phModule]; hModule
0x18004352f  test    rcx, rcx
0x180043532  jz      short loc_18004359C
0x180043534  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18004353b  call    cs:__imp_GetProcAddress
0x180043541  mov     rdx, rax
0x180043544  test    rax, rax
0x180043547  jz      short loc_18004359C
0x180043549  xor     eax, eax
0x18004354b  lea     rcx, [rbp+var_40]
0x18004354f  mov     [rbp+var_10], eax
0x180043552  xorps   xmm0, xmm0
0x180043555  movups  [rbp+var_20], xmm0
0x180043559  lea     rax, __ImageBase
0x180043560  movups  [rbp+var_40], xmm0
0x180043564  mov     qword ptr [rbp+var_40+8], rax
0x180043568  mov     rax, [rbp+8]
0x18004356c  movups  [rbp+var_30], xmm0
0x180043570  mov     qword ptr [rbp+var_30], rax
0x180043574  or      eax, 0FFFFFFFFh
0x180043577  mov     dword ptr [rbp+var_20+8], eax
0x18004357a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18004357d  mov     rax, rdx
0x180043580  mov     dword ptr [rbp+var_40], 0Bh
0x180043587  mov     byte ptr [rbp+var_10], 1
0x18004358b  mov     byte ptr [rbp+var_30+8], 0
0x18004358f  mov     qword ptr [rbp+var_20], 0
0x180043597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004359c  add     rsp, 60h
0x1800435a0  pop     rbp
0x1800435a1  retn
```
