# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1400185c4`
- end: `0x140018666`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011dec`

## callees

- `0x1400185c4`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400185e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400185e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400185ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400185ff`

## string_xrefs

- `0x1400185d9`: `ntdll.dll`

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
0x1400185c4  push    rbp
0x1400185c6  mov     rbp, rsp
0x1400185c9  sub     rsp, 60h
0x1400185cd  lea     r8, [rbp+phModule]; phModule
0x1400185d1  mov     [rbp+phModule], 0
0x1400185d9  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1400185e0  mov     ecx, 2; dwFlags
0x1400185e5  call    cs:__imp_GetModuleHandleExA
0x1400185eb  test    eax, eax
0x1400185ed  jz      short loc_140018660
0x1400185ef  mov     rcx, [rbp+phModule]; hModule
0x1400185f3  test    rcx, rcx
0x1400185f6  jz      short loc_140018660
0x1400185f8  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1400185ff  call    cs:__imp_GetProcAddress
0x140018605  mov     rdx, rax
0x140018608  test    rax, rax
0x14001860b  jz      short loc_140018660
0x14001860d  xor     eax, eax
0x14001860f  lea     rcx, [rbp+var_40]
0x140018613  mov     [rbp+var_10], eax
0x140018616  xorps   xmm0, xmm0
0x140018619  movups  [rbp+var_20], xmm0
0x14001861d  lea     rax, __ImageBase
0x140018624  movups  [rbp+var_40], xmm0
0x140018628  mov     qword ptr [rbp+var_40+8], rax
0x14001862c  mov     rax, [rbp+8]
0x140018630  movups  [rbp+var_30], xmm0
0x140018634  mov     qword ptr [rbp+var_30], rax
0x140018638  or      eax, 0FFFFFFFFh
0x14001863b  mov     dword ptr [rbp+var_20+8], eax
0x14001863e  mov     dword ptr [rbp+var_20+0Ch], eax
0x140018641  mov     rax, rdx
0x140018644  mov     dword ptr [rbp+var_40], 0Bh
0x14001864b  mov     byte ptr [rbp+var_10], 1
0x14001864f  mov     byte ptr [rbp+var_30+8], 0
0x140018653  mov     qword ptr [rbp+var_20], 0
0x14001865b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018660  add     rsp, 60h
0x140018664  pop     rbp
0x140018665  retn
```
