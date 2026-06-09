# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800200f8`
- end: `0x18002019a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a6d4`
- `0x1800139d0`
- `0x180014030`

## callees

- `0x1800200f8`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180020133`
- `KERNEL32!GetProcAddress` at `0x180020133`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180020119`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180020119`

## string_xrefs

- `0x18002010d`: `ntdll.dll`

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
0x1800200f8  push    rbp
0x1800200fa  mov     rbp, rsp
0x1800200fd  sub     rsp, 60h
0x180020101  lea     r8, [rbp+phModule]; phModule
0x180020105  mov     [rbp+phModule], 0
0x18002010d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180020114  mov     ecx, 2; dwFlags
0x180020119  call    cs:__imp_GetModuleHandleExA
0x18002011f  test    eax, eax
0x180020121  jz      short loc_180020194
0x180020123  mov     rcx, [rbp+phModule]; hModule
0x180020127  test    rcx, rcx
0x18002012a  jz      short loc_180020194
0x18002012c  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180020133  call    cs:__imp_GetProcAddress
0x180020139  mov     rdx, rax
0x18002013c  test    rax, rax
0x18002013f  jz      short loc_180020194
0x180020141  xor     eax, eax
0x180020143  lea     rcx, [rbp+var_40]
0x180020147  mov     [rbp+var_10], eax
0x18002014a  xorps   xmm0, xmm0
0x18002014d  movups  [rbp+var_20], xmm0
0x180020151  lea     rax, cs:180000000h
0x180020158  movups  [rbp+var_40], xmm0
0x18002015c  mov     qword ptr [rbp+var_40+8], rax
0x180020160  mov     rax, [rbp+8]
0x180020164  movups  [rbp+var_30], xmm0
0x180020168  mov     qword ptr [rbp+var_30], rax
0x18002016c  or      eax, 0FFFFFFFFh
0x18002016f  mov     dword ptr [rbp+var_20+8], eax
0x180020172  mov     dword ptr [rbp+var_20+0Ch], eax
0x180020175  mov     rax, rdx
0x180020178  mov     dword ptr [rbp+var_40], 0Bh
0x18002017f  mov     byte ptr [rbp+var_10], 1
0x180020183  mov     byte ptr [rbp+var_30+8], 0
0x180020187  mov     qword ptr [rbp+var_20], 0
0x18002018f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020194  add     rsp, 60h
0x180020198  pop     rbp
0x180020199  retn
```
