# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180007e6c`
- end: `0x180007f0e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002cf0`
- `0x1800068c8`
- `0x180008d38`
- `0x180008f40`
- `0x180009200`
- `0x180009b2c`
- `0x18000a688`
- `0x18000a72c`
- `0x18000d700`

## callees

- `0x180007e6c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ea7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007ea7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180007e8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180007e8d`

## string_xrefs

- `0x180007e81`: `ntdll.dll`

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
0x180007e6c  push    rbp
0x180007e6e  mov     rbp, rsp
0x180007e71  sub     rsp, 60h
0x180007e75  lea     r8, [rbp+phModule]; phModule
0x180007e79  mov     [rbp+phModule], 0
0x180007e81  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180007e88  mov     ecx, 2; dwFlags
0x180007e8d  call    cs:__imp_GetModuleHandleExA
0x180007e93  test    eax, eax
0x180007e95  jz      short loc_180007F08
0x180007e97  mov     rcx, [rbp+phModule]; hModule
0x180007e9b  test    rcx, rcx
0x180007e9e  jz      short loc_180007F08
0x180007ea0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180007ea7  call    cs:__imp_GetProcAddress
0x180007ead  mov     rdx, rax
0x180007eb0  test    rax, rax
0x180007eb3  jz      short loc_180007F08
0x180007eb5  xor     eax, eax
0x180007eb7  lea     rcx, [rbp+var_40]
0x180007ebb  mov     [rbp+var_10], eax
0x180007ebe  xorps   xmm0, xmm0
0x180007ec1  movups  [rbp+var_20], xmm0
0x180007ec5  lea     rax, __ImageBase
0x180007ecc  movups  [rbp+var_40], xmm0
0x180007ed0  mov     qword ptr [rbp+var_40+8], rax
0x180007ed4  mov     rax, [rbp+8]
0x180007ed8  movups  [rbp+var_30], xmm0
0x180007edc  mov     qword ptr [rbp+var_30], rax
0x180007ee0  or      eax, 0FFFFFFFFh
0x180007ee3  mov     dword ptr [rbp+var_20+8], eax
0x180007ee6  mov     dword ptr [rbp+var_20+0Ch], eax
0x180007ee9  mov     rax, rdx
0x180007eec  mov     dword ptr [rbp+var_40], 0Bh
0x180007ef3  mov     byte ptr [rbp+var_10], 1
0x180007ef7  mov     byte ptr [rbp+var_30+8], 0
0x180007efb  mov     qword ptr [rbp+var_20], 0
0x180007f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f08  add     rsp, 60h
0x180007f0c  pop     rbp
0x180007f0d  retn
```
