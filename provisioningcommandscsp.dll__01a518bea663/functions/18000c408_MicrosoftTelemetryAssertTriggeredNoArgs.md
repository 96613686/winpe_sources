# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000c408`
- end: `0x18000c4aa`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007fa0`

## callees

- `0x18000c408`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000c429`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000c429`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c443`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c443`

## string_xrefs

- `0x18000c41d`: `ntdll.dll`

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
0x18000c408  push    rbp
0x18000c40a  mov     rbp, rsp
0x18000c40d  sub     rsp, 60h
0x18000c411  lea     r8, [rbp+phModule]; phModule
0x18000c415  mov     [rbp+phModule], 0
0x18000c41d  lea     rdx, aNtdllDll; "ntdll.dll"
0x18000c424  mov     ecx, 2; dwFlags
0x18000c429  call    cs:__imp_GetModuleHandleExA
0x18000c42f  test    eax, eax
0x18000c431  jz      short loc_18000C4A4
0x18000c433  mov     rcx, [rbp+phModule]; hModule
0x18000c437  test    rcx, rcx
0x18000c43a  jz      short loc_18000C4A4
0x18000c43c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000c443  call    cs:__imp_GetProcAddress
0x18000c449  mov     rdx, rax
0x18000c44c  test    rax, rax
0x18000c44f  jz      short loc_18000C4A4
0x18000c451  xor     eax, eax
0x18000c453  lea     rcx, [rbp+var_40]
0x18000c457  mov     [rbp+var_10], eax
0x18000c45a  xorps   xmm0, xmm0
0x18000c45d  movups  [rbp+var_20], xmm0
0x18000c461  lea     rax, cs:180000000h
0x18000c468  movups  [rbp+var_40], xmm0
0x18000c46c  mov     qword ptr [rbp+var_40+8], rax
0x18000c470  mov     rax, [rbp+8]
0x18000c474  movups  [rbp+var_30], xmm0
0x18000c478  mov     qword ptr [rbp+var_30], rax
0x18000c47c  or      eax, 0FFFFFFFFh
0x18000c47f  mov     dword ptr [rbp+var_20+8], eax
0x18000c482  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000c485  mov     rax, rdx
0x18000c488  mov     dword ptr [rbp+var_40], 0Bh
0x18000c48f  mov     byte ptr [rbp+var_10], 1
0x18000c493  mov     byte ptr [rbp+var_30+8], 0
0x18000c497  mov     qword ptr [rbp+var_20], 0
0x18000c49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4a4  add     rsp, 60h
0x18000c4a8  pop     rbp
0x18000c4a9  retn
```
