# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000edb8`
- end: `0x18000ee5a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a208`
- `0x18000a370`
- `0x18000a7f0`
- `0x18000a850`
- `0x18000a8a0`
- `0x18000a8f0`
- `0x18000aa20`
- `0x18000aa60`
- `0x18000aac0`
- `0x18000ad00`
- `0x18000ad84`
- `0x18000af1c`

## callees

- `0x18000edb8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000edf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000edf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000edd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000edd9`

## string_xrefs

- `0x18000edcd`: `ntdll.dll`

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
0x18000edb8  push    rbp
0x18000edba  mov     rbp, rsp
0x18000edbd  sub     rsp, 60h
0x18000edc1  lea     r8, [rbp+phModule]; phModule
0x18000edc5  mov     [rbp+phModule], 0
0x18000edcd  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18000edd4  mov     ecx, 2; dwFlags
0x18000edd9  call    cs:__imp_GetModuleHandleExA
0x18000eddf  test    eax, eax
0x18000ede1  jz      short loc_18000EE54
0x18000ede3  mov     rcx, [rbp+phModule]; hModule
0x18000ede7  test    rcx, rcx
0x18000edea  jz      short loc_18000EE54
0x18000edec  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000edf3  call    cs:__imp_GetProcAddress
0x18000edf9  mov     rdx, rax
0x18000edfc  test    rax, rax
0x18000edff  jz      short loc_18000EE54
0x18000ee01  xor     eax, eax
0x18000ee03  lea     rcx, [rbp+var_40]
0x18000ee07  mov     [rbp+var_10], eax
0x18000ee0a  xorps   xmm0, xmm0
0x18000ee0d  movups  [rbp+var_20], xmm0
0x18000ee11  lea     rax, cs:180000000h
0x18000ee18  movups  [rbp+var_40], xmm0
0x18000ee1c  mov     qword ptr [rbp+var_40+8], rax
0x18000ee20  mov     rax, [rbp+8]
0x18000ee24  movups  [rbp+var_30], xmm0
0x18000ee28  mov     qword ptr [rbp+var_30], rax
0x18000ee2c  or      eax, 0FFFFFFFFh
0x18000ee2f  mov     dword ptr [rbp+var_20+8], eax
0x18000ee32  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000ee35  mov     rax, rdx
0x18000ee38  mov     dword ptr [rbp+var_40], 0Bh
0x18000ee3f  mov     byte ptr [rbp+var_10], 1
0x18000ee43  mov     byte ptr [rbp+var_30+8], 0
0x18000ee47  mov     qword ptr [rbp+var_20], 0
0x18000ee4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee54  add     rsp, 60h
0x18000ee58  pop     rbp
0x18000ee59  retn
```
