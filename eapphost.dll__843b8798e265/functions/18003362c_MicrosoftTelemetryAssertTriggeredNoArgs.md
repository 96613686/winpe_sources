# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18003362c`
- end: `0x1800336db`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025a58`

## callees

- `0x18003362c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003366d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003366d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18003364d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18003364d`

## string_xrefs

- `0x180033641`: `ntdll.dll`

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
0x18003362c  push    rbp
0x18003362e  mov     rbp, rsp
0x180033631  sub     rsp, 60h
0x180033635  lea     r8, [rbp+phModule]; phModule
0x180033639  mov     [rbp+phModule], 0
0x180033641  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180033648  mov     ecx, 2; dwFlags
0x18003364d  call    cs:__imp_GetModuleHandleExA
0x180033654  nop     dword ptr [rax+rax+00h]
0x180033659  test    eax, eax
0x18003365b  jz      short loc_1800336D4
0x18003365d  mov     rcx, [rbp+phModule]; hModule
0x180033661  test    rcx, rcx
0x180033664  jz      short loc_1800336D4
0x180033666  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18003366d  call    cs:__imp_GetProcAddress
0x180033674  nop     dword ptr [rax+rax+00h]
0x180033679  mov     rdx, rax
0x18003367c  test    rax, rax
0x18003367f  jz      short loc_1800336D4
0x180033681  xor     eax, eax
0x180033683  lea     rcx, [rbp+var_40]
0x180033687  mov     [rbp+var_10], eax
0x18003368a  xorps   xmm0, xmm0
0x18003368d  movups  [rbp+var_20], xmm0
0x180033691  lea     rax, __ImageBase
0x180033698  movups  [rbp+var_40], xmm0
0x18003369c  mov     qword ptr [rbp+var_40+8], rax
0x1800336a0  mov     rax, [rbp+8]
0x1800336a4  movups  [rbp+var_30], xmm0
0x1800336a8  mov     qword ptr [rbp+var_30], rax
0x1800336ac  or      eax, 0FFFFFFFFh
0x1800336af  mov     dword ptr [rbp+var_20+8], eax
0x1800336b2  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800336b5  mov     rax, rdx
0x1800336b8  mov     dword ptr [rbp+var_40], 0Bh
0x1800336bf  mov     byte ptr [rbp+var_10], 1
0x1800336c3  mov     byte ptr [rbp+var_30+8], 0
0x1800336c7  mov     qword ptr [rbp+var_20], 0
0x1800336cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336d4  add     rsp, 60h
0x1800336d8  pop     rbp
0x1800336d9  retn
```
