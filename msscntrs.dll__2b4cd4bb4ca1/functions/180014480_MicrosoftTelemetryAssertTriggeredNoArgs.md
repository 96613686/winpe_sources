# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180014480`
- end: `0x180014522`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014008`

## callees

- `0x180014480`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800144bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800144bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800144a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800144a1`

## string_xrefs

- `0x180014495`: `ntdll.dll`

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
0x180014480  push    rbp
0x180014482  mov     rbp, rsp
0x180014485  sub     rsp, 60h
0x180014489  lea     r8, [rbp+phModule]; phModule
0x18001448d  mov     [rbp+phModule], 0
0x180014495  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001449c  mov     ecx, 2; dwFlags
0x1800144a1  call    cs:__imp_GetModuleHandleExA
0x1800144a7  test    eax, eax
0x1800144a9  jz      short loc_18001451C
0x1800144ab  mov     rcx, [rbp+phModule]; hModule
0x1800144af  test    rcx, rcx
0x1800144b2  jz      short loc_18001451C
0x1800144b4  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800144bb  call    cs:__imp_GetProcAddress
0x1800144c1  mov     rdx, rax
0x1800144c4  test    rax, rax
0x1800144c7  jz      short loc_18001451C
0x1800144c9  xor     eax, eax
0x1800144cb  lea     rcx, [rbp+var_40]
0x1800144cf  mov     [rbp+var_10], eax
0x1800144d2  xorps   xmm0, xmm0
0x1800144d5  movups  [rbp+var_20], xmm0
0x1800144d9  lea     rax, cs:180000000h
0x1800144e0  movups  [rbp+var_40], xmm0
0x1800144e4  mov     qword ptr [rbp+var_40+8], rax
0x1800144e8  mov     rax, [rbp+8]
0x1800144ec  movups  [rbp+var_30], xmm0
0x1800144f0  mov     qword ptr [rbp+var_30], rax
0x1800144f4  or      eax, 0FFFFFFFFh
0x1800144f7  mov     dword ptr [rbp+var_20+8], eax
0x1800144fa  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800144fd  mov     rax, rdx
0x180014500  mov     dword ptr [rbp+var_40], 0Bh
0x180014507  mov     byte ptr [rbp+var_10], 1
0x18001450b  mov     byte ptr [rbp+var_30+8], 0
0x18001450f  mov     qword ptr [rbp+var_20], 0
0x180014517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001451c  add     rsp, 60h
0x180014520  pop     rbp
0x180014521  retn
```
