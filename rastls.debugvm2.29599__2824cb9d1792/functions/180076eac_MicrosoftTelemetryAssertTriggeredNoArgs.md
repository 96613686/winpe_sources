# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180076eac`
- end: `0x180076f4e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008b28`
- `0x180021bdc`
- `0x180054cf4`

## callees

- `0x180076eac`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076ee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076ee7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180076ecd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180076ecd`

## string_xrefs

- `0x180076ec1`: `ntdll.dll`

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
0x180076eac  push    rbp
0x180076eae  mov     rbp, rsp
0x180076eb1  sub     rsp, 60h
0x180076eb5  lea     r8, [rbp+phModule]; phModule
0x180076eb9  mov     [rbp+phModule], 0
0x180076ec1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180076ec8  mov     ecx, 2; dwFlags
0x180076ecd  call    cs:__imp_GetModuleHandleExA
0x180076ed3  test    eax, eax
0x180076ed5  jz      short loc_180076F48
0x180076ed7  mov     rcx, [rbp+phModule]; hModule
0x180076edb  test    rcx, rcx
0x180076ede  jz      short loc_180076F48
0x180076ee0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180076ee7  call    cs:__imp_GetProcAddress
0x180076eed  mov     rdx, rax
0x180076ef0  test    rax, rax
0x180076ef3  jz      short loc_180076F48
0x180076ef5  xor     eax, eax
0x180076ef7  lea     rcx, [rbp+var_40]
0x180076efb  mov     [rbp+var_10], eax
0x180076efe  xorps   xmm0, xmm0
0x180076f01  movups  [rbp+var_20], xmm0
0x180076f05  lea     rax, __ImageBase
0x180076f0c  movups  [rbp+var_40], xmm0
0x180076f10  mov     qword ptr [rbp+var_40+8], rax
0x180076f14  mov     rax, [rbp+8]
0x180076f18  movups  [rbp+var_30], xmm0
0x180076f1c  mov     qword ptr [rbp+var_30], rax
0x180076f20  or      eax, 0FFFFFFFFh
0x180076f23  mov     dword ptr [rbp+var_20+8], eax
0x180076f26  mov     dword ptr [rbp+var_20+0Ch], eax
0x180076f29  mov     rax, rdx
0x180076f2c  mov     dword ptr [rbp+var_40], 0Bh
0x180076f33  mov     byte ptr [rbp+var_10], 1
0x180076f37  mov     byte ptr [rbp+var_30+8], 0
0x180076f3b  mov     qword ptr [rbp+var_20], 0
0x180076f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076f48  add     rsp, 60h
0x180076f4c  pop     rbp
0x180076f4d  retn
```
