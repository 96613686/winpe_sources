# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180038654`
- end: `0x1800386f6`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003833c`

## callees

- `0x180038654`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003868f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003868f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180038675`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180038675`

## string_xrefs

- `0x180038669`: `ntdll.dll`

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
0x180038654  push    rbp
0x180038656  mov     rbp, rsp
0x180038659  sub     rsp, 60h
0x18003865d  lea     r8, [rbp+phModule]; phModule
0x180038661  mov     [rbp+phModule], 0
0x180038669  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180038670  mov     ecx, 2; dwFlags
0x180038675  call    cs:__imp_GetModuleHandleExA
0x18003867b  test    eax, eax
0x18003867d  jz      short loc_1800386F0
0x18003867f  mov     rcx, [rbp+phModule]; hModule
0x180038683  test    rcx, rcx
0x180038686  jz      short loc_1800386F0
0x180038688  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18003868f  call    cs:__imp_GetProcAddress
0x180038695  mov     rdx, rax
0x180038698  test    rax, rax
0x18003869b  jz      short loc_1800386F0
0x18003869d  xor     eax, eax
0x18003869f  lea     rcx, [rbp+var_40]
0x1800386a3  mov     [rbp+var_10], eax
0x1800386a6  xorps   xmm0, xmm0
0x1800386a9  movups  [rbp+var_20], xmm0
0x1800386ad  lea     rax, __ImageBase
0x1800386b4  movups  [rbp+var_40], xmm0
0x1800386b8  mov     qword ptr [rbp+var_40+8], rax
0x1800386bc  mov     rax, [rbp+8]
0x1800386c0  movups  [rbp+var_30], xmm0
0x1800386c4  mov     qword ptr [rbp+var_30], rax
0x1800386c8  or      eax, 0FFFFFFFFh
0x1800386cb  mov     dword ptr [rbp+var_20+8], eax
0x1800386ce  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800386d1  mov     rax, rdx
0x1800386d4  mov     dword ptr [rbp+var_40], 0Bh
0x1800386db  mov     byte ptr [rbp+var_10], 1
0x1800386df  mov     byte ptr [rbp+var_30+8], 0
0x1800386e3  mov     qword ptr [rbp+var_20], 0
0x1800386eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386f0  add     rsp, 60h
0x1800386f4  pop     rbp
0x1800386f5  retn
```
