# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18001cba8`
- end: `0x18001cc6b`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002d00`
- `0x1800049e0`

## callees

- `0x18001cba8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001cbd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001cbd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cbf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cbf4`

## string_xrefs

- `0x18001cc33`: `cldapi.dll`
- `0x18001cbc4`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, unsigned int a2)
{
  FARPROC ProcAddress; // rax
  _QWORD v5[6]; // [rsp+20h] [rbp-40h] BYREF
  int v6; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+8h]
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
        v5[1] = &_ImageBase;
        v5[3] = 1;
        v5[2] = retaddr;
        v5[4] = "cldapi.dll";
        v5[0] = 11;
        v5[5] = a2;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v5);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18001cba8  mov     [rsp-8+arg_8], rbx
0x18001cbad  mov     [rsp-8+phModule], rcx
0x18001cbb2  push    rbp
0x18001cbb3  mov     rbp, rsp
0x18001cbb6  sub     rsp, 60h
0x18001cbba  mov     ebx, edx
0x18001cbbc  mov     [rbp+phModule], 0
0x18001cbc4  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001cbcb  mov     ecx, 2; dwFlags
0x18001cbd0  lea     r8, [rbp+phModule]; phModule
0x18001cbd4  call    cs:__imp_GetModuleHandleExA
0x18001cbdb  nop     dword ptr [rax+rax+00h]
0x18001cbe0  test    eax, eax
0x18001cbe2  jz      short loc_18001CC5F
0x18001cbe4  mov     rcx, [rbp+phModule]; hModule
0x18001cbe8  test    rcx, rcx
0x18001cbeb  jz      short loc_18001CC5F
0x18001cbed  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001cbf4  call    cs:__imp_GetProcAddress
0x18001cbfb  nop     dword ptr [rax+rax+00h]
0x18001cc00  mov     rdx, rax
0x18001cc03  test    rax, rax
0x18001cc06  jz      short loc_18001CC5F
0x18001cc08  xor     eax, eax
0x18001cc0a  lea     rcx, [rbp+var_40]
0x18001cc0e  mov     [rbp+var_10], eax
0x18001cc11  xorps   xmm0, xmm0
0x18001cc14  movups  [rbp+var_20], xmm0
0x18001cc18  lea     rax, __ImageBase
0x18001cc1f  movups  [rbp+var_40], xmm0
0x18001cc23  mov     qword ptr [rbp+var_40+8], rax
0x18001cc27  mov     rax, [rbp+8]
0x18001cc2b  movups  [rbp+var_30], xmm0
0x18001cc2f  mov     qword ptr [rbp+var_30], rax
0x18001cc33  lea     rax, aCldapiDll_0; "cldapi.dll"
0x18001cc3a  mov     qword ptr [rbp+var_20], rax
0x18001cc3e  mov     rax, rdx
0x18001cc41  mov     dword ptr [rbp+var_40], 0Bh
0x18001cc48  mov     byte ptr [rbp+var_10], 1
0x18001cc4c  mov     byte ptr [rbp+var_30+8], 1
0x18001cc50  mov     dword ptr [rbp+var_20+8], ebx
0x18001cc53  mov     dword ptr [rbp+var_20+0Ch], 0
0x18001cc5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc5f  mov     rbx, [rsp+60h+arg_8]
0x18001cc64  add     rsp, 60h
0x18001cc68  pop     rbp
0x18001cc69  retn
```
