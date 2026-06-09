# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000e59c`
- end: `0x18000e63e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `72`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009db4`
- `0x18000b4a4`
- `0x18000da48`
- `0x1800156ac`
- `0x18001645c`
- `0x1800183f8`
- `0x1800184f4`
- `0x180019074`
- `0x180019e2c`
- `0x18001a654`
- `0x18001c310`
- `0x18001fec0`
- `0x180022a98`
- `0x180022c2c`
- `0x1800272f0`
- `0x180027e8c`
- `0x18002cd10`
- `0x18002cf0c`
- `0x18002ecc8`
- `0x1800309dc`
- `0x1800311a0`
- `0x18003136c`
- `0x1800319a0`
- `0x1800349f0`
- `0x180036268`
- `0x18003a2e8`
- `0x18003b478`
- `0x18003bc20`
- `0x18003bd80`
- `0x18003c010`
- `0x18003c2b0`
- `0x18003c4c0`
- `0x18003d1a0`
- `0x18003f264`
- `0x18003f5d4`
- `0x180042cdc`
- `0x180044350`
- `0x180050180`
- `0x180050300`
- `0x180051f34`
- `0x1800524c0`
- `0x180054830`
- `0x18005a054`
- `0x18005a2b4`
- `0x18005c050`
- `0x18005c7cc`
- `0x18005c8b4`
- `0x18005c930`
- `0x18005cac0`
- `0x18005cef0`

## callees

- `0x18000e59c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000e5bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000e5bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e5d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e5d7`

## string_xrefs

- `0x18000e5b1`: `ntdll.dll`

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
0x18000e59c  push    rbp
0x18000e59e  mov     rbp, rsp
0x18000e5a1  sub     rsp, 60h
0x18000e5a5  lea     r8, [rbp+phModule]; phModule
0x18000e5a9  mov     [rbp+phModule], 0
0x18000e5b1  lea     rdx, ModuleName; "ntdll.dll"
0x18000e5b8  mov     ecx, 2; dwFlags
0x18000e5bd  call    cs:__imp_GetModuleHandleExA
0x18000e5c3  test    eax, eax
0x18000e5c5  jz      short loc_18000E638
0x18000e5c7  mov     rcx, [rbp+phModule]; hModule
0x18000e5cb  test    rcx, rcx
0x18000e5ce  jz      short loc_18000E638
0x18000e5d0  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000e5d7  call    cs:__imp_GetProcAddress
0x18000e5dd  mov     rdx, rax
0x18000e5e0  test    rax, rax
0x18000e5e3  jz      short loc_18000E638
0x18000e5e5  xor     eax, eax
0x18000e5e7  lea     rcx, [rbp+var_40]
0x18000e5eb  mov     [rbp+var_10], eax
0x18000e5ee  xorps   xmm0, xmm0
0x18000e5f1  movups  [rbp+var_20], xmm0
0x18000e5f5  lea     rax, __ImageBase
0x18000e5fc  movups  [rbp+var_40], xmm0
0x18000e600  mov     qword ptr [rbp+var_40+8], rax
0x18000e604  mov     rax, [rbp+8]
0x18000e608  movups  [rbp+var_30], xmm0
0x18000e60c  mov     qword ptr [rbp+var_30], rax
0x18000e610  or      eax, 0FFFFFFFFh
0x18000e613  mov     dword ptr [rbp+var_20+8], eax
0x18000e616  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000e619  mov     rax, rdx
0x18000e61c  mov     dword ptr [rbp+var_40], 0Bh
0x18000e623  mov     byte ptr [rbp+var_10], 1
0x18000e627  mov     byte ptr [rbp+var_30+8], 0
0x18000e62b  mov     qword ptr [rbp+var_20], 0
0x18000e633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e638  add     rsp, 60h
0x18000e63c  pop     rbp
0x18000e63d  retn
```
