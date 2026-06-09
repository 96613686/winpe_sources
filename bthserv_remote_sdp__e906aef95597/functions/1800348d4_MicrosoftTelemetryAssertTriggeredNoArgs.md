# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800348d4`
- end: `0x18003497d`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d498`
- `0x18000f0e0`
- `0x180018304`

## callees

- `0x1800348d4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800348f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800348f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034912`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034912`

## string_xrefs

- `0x1800348e6`: `ntdll.dll`

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
        v4 = 0;
        v3 = retaddr;
        v5 = -1;
        v2[0] = 11;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x1800348d4  push    rbp
0x1800348d6  mov     rbp, rsp
0x1800348d9  sub     rsp, 60h
0x1800348dd  and     [rbp+phModule], 0
0x1800348e2  lea     r8, [rbp+phModule]; phModule
0x1800348e6  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800348ed  mov     ecx, 2; dwFlags
0x1800348f2  call    cs:__imp_GetModuleHandleExA
0x1800348f9  nop     dword ptr [rax+rax+00h]
0x1800348fe  test    eax, eax
0x180034900  jz      short loc_180034976
0x180034902  mov     rcx, [rbp+phModule]; hModule
0x180034906  test    rcx, rcx
0x180034909  jz      short loc_180034976
0x18003490b  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180034912  call    cs:__imp_GetProcAddress
0x180034919  nop     dword ptr [rax+rax+00h]
0x18003491e  mov     rdx, rax
0x180034921  test    rax, rax
0x180034924  jz      short loc_180034976
0x180034926  xor     eax, eax
0x180034928  lea     rcx, [rbp+var_40]
0x18003492c  mov     [rbp+var_10], eax
0x18003492f  xorps   xmm0, xmm0
0x180034932  movups  [rbp+var_20], xmm0
0x180034936  lea     rax, __ImageBase
0x18003493d  movups  [rbp+var_40], xmm0
0x180034941  mov     qword ptr [rbp+var_40+8], rax
0x180034945  mov     rax, [rbp+8]
0x180034949  and     qword ptr [rbp+var_20], 0
0x18003494e  movups  [rbp+var_30], xmm0
0x180034952  mov     qword ptr [rbp+var_30], rax
0x180034956  or      eax, 0FFFFFFFFh
0x180034959  mov     dword ptr [rbp+var_20+8], eax
0x18003495c  mov     dword ptr [rbp+var_20+0Ch], eax
0x18003495f  mov     rax, rdx
0x180034962  mov     dword ptr [rbp+var_40], 0Bh
0x180034969  mov     byte ptr [rbp+var_10], 1
0x18003496d  mov     byte ptr [rbp+var_30+8], 0
0x180034971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034976  add     rsp, 60h
0x18003497a  pop     rbp
0x18003497b  retn
```
