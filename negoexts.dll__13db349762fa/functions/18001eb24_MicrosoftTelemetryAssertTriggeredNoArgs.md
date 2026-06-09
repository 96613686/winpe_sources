# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001eb24`
- end: `0x18001ebc6`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a390`

## callees

- `0x18001eb24`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eb5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eb5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001eb45`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001eb45`

## string_xrefs

- `0x18001eb39`: `ntdll.dll`

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
0x18001eb24  push    rbp
0x18001eb26  mov     rbp, rsp
0x18001eb29  sub     rsp, 60h
0x18001eb2d  lea     r8, [rbp+phModule]; phModule
0x18001eb31  mov     [rbp+phModule], 0
0x18001eb39  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001eb40  mov     ecx, 2; dwFlags
0x18001eb45  call    cs:__imp_GetModuleHandleExA
0x18001eb4b  test    eax, eax
0x18001eb4d  jz      short loc_18001EBC0
0x18001eb4f  mov     rcx, [rbp+phModule]; hModule
0x18001eb53  test    rcx, rcx
0x18001eb56  jz      short loc_18001EBC0
0x18001eb58  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001eb5f  call    cs:__imp_GetProcAddress
0x18001eb65  mov     rdx, rax
0x18001eb68  test    rax, rax
0x18001eb6b  jz      short loc_18001EBC0
0x18001eb6d  xor     eax, eax
0x18001eb6f  lea     rcx, [rbp+var_40]
0x18001eb73  mov     [rbp+var_10], eax
0x18001eb76  xorps   xmm0, xmm0
0x18001eb79  movups  [rbp+var_20], xmm0
0x18001eb7d  lea     rax, __ImageBase
0x18001eb84  movups  [rbp+var_40], xmm0
0x18001eb88  mov     qword ptr [rbp+var_40+8], rax
0x18001eb8c  mov     rax, [rbp+8]
0x18001eb90  movups  [rbp+var_30], xmm0
0x18001eb94  mov     qword ptr [rbp+var_30], rax
0x18001eb98  or      eax, 0FFFFFFFFh
0x18001eb9b  mov     dword ptr [rbp+var_20+8], eax
0x18001eb9e  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001eba1  mov     rax, rdx
0x18001eba4  mov     dword ptr [rbp+var_40], 0Bh
0x18001ebab  mov     byte ptr [rbp+var_10], 1
0x18001ebaf  mov     byte ptr [rbp+var_30+8], 0
0x18001ebb3  mov     qword ptr [rbp+var_20], 0
0x18001ebbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebc0  add     rsp, 60h
0x18001ebc4  pop     rbp
0x18001ebc5  retn
```
