# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180003950`
- end: `0x1800039f2`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003118`

## callees

- `0x180003950`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000398b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000398b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180003971`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180003971`

## string_xrefs

- `0x180003965`: `ntdll.dll`

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
0x180003950  push    rbp
0x180003952  mov     rbp, rsp
0x180003955  sub     rsp, 60h
0x180003959  lea     r8, [rbp+phModule]; phModule
0x18000395d  mov     [rbp+phModule], 0
0x180003965  lea     rdx, ModuleName; "ntdll.dll"
0x18000396c  mov     ecx, 2; dwFlags
0x180003971  call    cs:__imp_GetModuleHandleExA
0x180003977  test    eax, eax
0x180003979  jz      short loc_1800039EC
0x18000397b  mov     rcx, [rbp+phModule]; hModule
0x18000397f  test    rcx, rcx
0x180003982  jz      short loc_1800039EC
0x180003984  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000398b  call    cs:__imp_GetProcAddress
0x180003991  mov     rdx, rax
0x180003994  test    rax, rax
0x180003997  jz      short loc_1800039EC
0x180003999  xor     eax, eax
0x18000399b  lea     rcx, [rbp+var_40]
0x18000399f  mov     [rbp+var_10], eax
0x1800039a2  xorps   xmm0, xmm0
0x1800039a5  movups  [rbp+var_20], xmm0
0x1800039a9  lea     rax, __ImageBase
0x1800039b0  movups  [rbp+var_40], xmm0
0x1800039b4  mov     qword ptr [rbp+var_40+8], rax
0x1800039b8  mov     rax, [rbp+8]
0x1800039bc  movups  [rbp+var_30], xmm0
0x1800039c0  mov     qword ptr [rbp+var_30], rax
0x1800039c4  or      eax, 0FFFFFFFFh
0x1800039c7  mov     dword ptr [rbp+var_20+8], eax
0x1800039ca  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800039cd  mov     rax, rdx
0x1800039d0  mov     dword ptr [rbp+var_40], 0Bh
0x1800039d7  mov     byte ptr [rbp+var_10], 1
0x1800039db  mov     byte ptr [rbp+var_30+8], 0
0x1800039df  mov     qword ptr [rbp+var_20], 0
0x1800039e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ec  add     rsp, 60h
0x1800039f0  pop     rbp
0x1800039f1  retn
```
