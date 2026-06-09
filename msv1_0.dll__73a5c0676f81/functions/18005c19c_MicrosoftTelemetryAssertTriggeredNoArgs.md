# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18005c19c`
- end: `0x18005c23e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ffb0`
- `0x18002f120`
- `0x18003ca8c`
- `0x18004e098`
- `0x18005546c`
- `0x1800558c8`
- `0x180067f24`

## callees

- `0x18005c19c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18005c1bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18005c1bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005c1d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005c1d7`

## string_xrefs

- `0x18005c1b1`: `ntdll.dll`

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
0x18005c19c  push    rbp
0x18005c19e  mov     rbp, rsp
0x18005c1a1  sub     rsp, 60h
0x18005c1a5  lea     r8, [rbp+phModule]; phModule
0x18005c1a9  mov     [rbp+phModule], 0
0x18005c1b1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18005c1b8  mov     ecx, 2; dwFlags
0x18005c1bd  call    cs:__imp_GetModuleHandleExA
0x18005c1c3  test    eax, eax
0x18005c1c5  jz      short loc_18005C238
0x18005c1c7  mov     rcx, [rbp+phModule]; hModule
0x18005c1cb  test    rcx, rcx
0x18005c1ce  jz      short loc_18005C238
0x18005c1d0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18005c1d7  call    cs:__imp_GetProcAddress
0x18005c1dd  mov     rdx, rax
0x18005c1e0  test    rax, rax
0x18005c1e3  jz      short loc_18005C238
0x18005c1e5  xor     eax, eax
0x18005c1e7  lea     rcx, [rbp+var_40]
0x18005c1eb  mov     [rbp+var_10], eax
0x18005c1ee  xorps   xmm0, xmm0
0x18005c1f1  movups  [rbp+var_20], xmm0
0x18005c1f5  lea     rax, __ImageBase
0x18005c1fc  movups  [rbp+var_40], xmm0
0x18005c200  mov     qword ptr [rbp+var_40+8], rax
0x18005c204  mov     rax, [rbp+8]
0x18005c208  movups  [rbp+var_30], xmm0
0x18005c20c  mov     qword ptr [rbp+var_30], rax
0x18005c210  or      eax, 0FFFFFFFFh
0x18005c213  mov     dword ptr [rbp+var_20+8], eax
0x18005c216  mov     dword ptr [rbp+var_20+0Ch], eax
0x18005c219  mov     rax, rdx
0x18005c21c  mov     dword ptr [rbp+var_40], 0Bh
0x18005c223  mov     byte ptr [rbp+var_10], 1
0x18005c227  mov     byte ptr [rbp+var_30+8], 0
0x18005c22b  mov     qword ptr [rbp+var_20], 0
0x18005c233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c238  add     rsp, 60h
0x18005c23c  pop     rbp
0x18005c23d  retn
```
