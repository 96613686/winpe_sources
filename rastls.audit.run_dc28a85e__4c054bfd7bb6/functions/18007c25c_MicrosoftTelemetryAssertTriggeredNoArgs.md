# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18007c25c`
- end: `0x18007c30b`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009418`
- `0x18002471c`
- `0x180057c44`

## callees

- `0x18007c25c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c29d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c29d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18007c27d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18007c27d`

## string_xrefs

- `0x18007c271`: `ntdll.dll`

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
0x18007c25c  push    rbp
0x18007c25e  mov     rbp, rsp
0x18007c261  sub     rsp, 60h
0x18007c265  lea     r8, [rbp+phModule]; phModule
0x18007c269  mov     [rbp+phModule], 0
0x18007c271  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18007c278  mov     ecx, 2; dwFlags
0x18007c27d  call    cs:__imp_GetModuleHandleExA
0x18007c284  nop     dword ptr [rax+rax+00h]
0x18007c289  test    eax, eax
0x18007c28b  jz      short loc_18007C304
0x18007c28d  mov     rcx, [rbp+phModule]; hModule
0x18007c291  test    rcx, rcx
0x18007c294  jz      short loc_18007C304
0x18007c296  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18007c29d  call    cs:__imp_GetProcAddress
0x18007c2a4  nop     dword ptr [rax+rax+00h]
0x18007c2a9  mov     rdx, rax
0x18007c2ac  test    rax, rax
0x18007c2af  jz      short loc_18007C304
0x18007c2b1  xor     eax, eax
0x18007c2b3  lea     rcx, [rbp+var_40]
0x18007c2b7  mov     [rbp+var_10], eax
0x18007c2ba  xorps   xmm0, xmm0
0x18007c2bd  movups  [rbp+var_20], xmm0
0x18007c2c1  lea     rax, __ImageBase
0x18007c2c8  movups  [rbp+var_40], xmm0
0x18007c2cc  mov     qword ptr [rbp+var_40+8], rax
0x18007c2d0  mov     rax, [rbp+8]
0x18007c2d4  movups  [rbp+var_30], xmm0
0x18007c2d8  mov     qword ptr [rbp+var_30], rax
0x18007c2dc  or      eax, 0FFFFFFFFh
0x18007c2df  mov     dword ptr [rbp+var_20+8], eax
0x18007c2e2  mov     dword ptr [rbp+var_20+0Ch], eax
0x18007c2e5  mov     rax, rdx
0x18007c2e8  mov     dword ptr [rbp+var_40], 0Bh
0x18007c2ef  mov     byte ptr [rbp+var_10], 1
0x18007c2f3  mov     byte ptr [rbp+var_30+8], 0
0x18007c2f7  mov     qword ptr [rbp+var_20], 0
0x18007c2ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c304  add     rsp, 60h
0x18007c308  pop     rbp
0x18007c309  retn
```
