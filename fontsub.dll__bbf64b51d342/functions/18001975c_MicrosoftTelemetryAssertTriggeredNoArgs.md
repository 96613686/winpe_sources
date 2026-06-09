# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001975c`
- end: `0x1800197fe`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012640`
- `0x180013364`
- `0x180013c38`
- `0x180013ee0`

## callees

- `0x18001975c`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x18001977d`
- `KERNEL32!GetModuleHandleExA` at `0x18001977d`
- `KERNEL32!GetProcAddress` at `0x180019797`
- `KERNEL32!GetProcAddress` at `0x180019797`

## string_xrefs

- `0x180019771`: `ntdll.dll`

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
        v2[1] = 0x180000000uLL;
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
0x18001975c  push    rbp
0x18001975e  mov     rbp, rsp
0x180019761  sub     rsp, 60h
0x180019765  lea     r8, [rbp+phModule]; phModule
0x180019769  mov     [rbp+phModule], 0
0x180019771  lea     rdx, aNtdllDll; "ntdll.dll"
0x180019778  mov     ecx, 2; dwFlags
0x18001977d  call    cs:__imp_GetModuleHandleExA
0x180019783  test    eax, eax
0x180019785  jz      short loc_1800197F8
0x180019787  mov     rcx, [rbp+phModule]; hModule
0x18001978b  test    rcx, rcx
0x18001978e  jz      short loc_1800197F8
0x180019790  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180019797  call    cs:__imp_GetProcAddress
0x18001979d  mov     rdx, rax
0x1800197a0  test    rax, rax
0x1800197a3  jz      short loc_1800197F8
0x1800197a5  xor     eax, eax
0x1800197a7  lea     rcx, [rbp+var_40]
0x1800197ab  mov     [rbp+var_10], eax
0x1800197ae  xorps   xmm0, xmm0
0x1800197b1  movups  [rbp+var_20], xmm0
0x1800197b5  lea     rax, cs:180000000h
0x1800197bc  movups  [rbp+var_40], xmm0
0x1800197c0  mov     qword ptr [rbp+var_40+8], rax
0x1800197c4  mov     rax, [rbp+8]
0x1800197c8  movups  [rbp+var_30], xmm0
0x1800197cc  mov     qword ptr [rbp+var_30], rax
0x1800197d0  or      eax, 0FFFFFFFFh
0x1800197d3  mov     dword ptr [rbp+var_20+8], eax
0x1800197d6  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800197d9  mov     rax, rdx
0x1800197dc  mov     dword ptr [rbp+var_40], 0Bh
0x1800197e3  mov     byte ptr [rbp+var_10], 1
0x1800197e7  mov     byte ptr [rbp+var_30+8], 0
0x1800197eb  mov     qword ptr [rbp+var_20], 0
0x1800197f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197f8  add     rsp, 60h
0x1800197fc  pop     rbp
0x1800197fd  retn
```
