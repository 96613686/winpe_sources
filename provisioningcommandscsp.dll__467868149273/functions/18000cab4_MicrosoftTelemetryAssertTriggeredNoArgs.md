# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000cab4`
- end: `0x18000cb63`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008360`

## callees

- `0x18000cab4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000cad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000cad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000caf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000caf5`

## string_xrefs

- `0x18000cac9`: `ntdll.dll`

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
0x18000cab4  push    rbp
0x18000cab6  mov     rbp, rsp
0x18000cab9  sub     rsp, 60h
0x18000cabd  lea     r8, [rbp+phModule]; phModule
0x18000cac1  mov     [rbp+phModule], 0
0x18000cac9  lea     rdx, aNtdllDll; "ntdll.dll"
0x18000cad0  mov     ecx, 2; dwFlags
0x18000cad5  call    cs:__imp_GetModuleHandleExA
0x18000cadc  nop     dword ptr [rax+rax+00h]
0x18000cae1  test    eax, eax
0x18000cae3  jz      short loc_18000CB5C
0x18000cae5  mov     rcx, [rbp+phModule]; hModule
0x18000cae9  test    rcx, rcx
0x18000caec  jz      short loc_18000CB5C
0x18000caee  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000caf5  call    cs:__imp_GetProcAddress
0x18000cafc  nop     dword ptr [rax+rax+00h]
0x18000cb01  mov     rdx, rax
0x18000cb04  test    rax, rax
0x18000cb07  jz      short loc_18000CB5C
0x18000cb09  xor     eax, eax
0x18000cb0b  lea     rcx, [rbp+var_40]
0x18000cb0f  mov     [rbp+var_10], eax
0x18000cb12  xorps   xmm0, xmm0
0x18000cb15  movups  [rbp+var_20], xmm0
0x18000cb19  lea     rax, cs:180000000h
0x18000cb20  movups  [rbp+var_40], xmm0
0x18000cb24  mov     qword ptr [rbp+var_40+8], rax
0x18000cb28  mov     rax, [rbp+8]
0x18000cb2c  movups  [rbp+var_30], xmm0
0x18000cb30  mov     qword ptr [rbp+var_30], rax
0x18000cb34  or      eax, 0FFFFFFFFh
0x18000cb37  mov     dword ptr [rbp+var_20+8], eax
0x18000cb3a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000cb3d  mov     rax, rdx
0x18000cb40  mov     dword ptr [rbp+var_40], 0Bh
0x18000cb47  mov     byte ptr [rbp+var_10], 1
0x18000cb4b  mov     byte ptr [rbp+var_30+8], 0
0x18000cb4f  mov     qword ptr [rbp+var_20], 0
0x18000cb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb5c  add     rsp, 60h
0x18000cb60  pop     rbp
0x18000cb61  retn
```
