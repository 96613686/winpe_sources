# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1400350e4`
- end: `0x140035186`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140023034`
- `0x140023ba0`
- `0x140024220`
- `0x1400275a0`

## callees

- `0x1400350e4`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003511f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003511f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140035105`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x140035105`

## string_xrefs

- `0x1400350f9`: `ntdll.dll`

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
0x1400350e4  push    rbp
0x1400350e6  mov     rbp, rsp
0x1400350e9  sub     rsp, 60h
0x1400350ed  lea     r8, [rbp+phModule]; phModule
0x1400350f1  mov     [rbp+phModule], 0
0x1400350f9  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x140035100  mov     ecx, 2; dwFlags
0x140035105  call    cs:__imp_GetModuleHandleExA
0x14003510b  test    eax, eax
0x14003510d  jz      short loc_140035180
0x14003510f  mov     rcx, [rbp+phModule]; hModule
0x140035113  test    rcx, rcx
0x140035116  jz      short loc_140035180
0x140035118  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14003511f  call    cs:__imp_GetProcAddress
0x140035125  mov     rdx, rax
0x140035128  test    rax, rax
0x14003512b  jz      short loc_140035180
0x14003512d  xor     eax, eax
0x14003512f  lea     rcx, [rbp+var_40]
0x140035133  mov     [rbp+var_10], eax
0x140035136  xorps   xmm0, xmm0
0x140035139  movups  [rbp+var_20], xmm0
0x14003513d  lea     rax, __ImageBase
0x140035144  movups  [rbp+var_40], xmm0
0x140035148  mov     qword ptr [rbp+var_40+8], rax
0x14003514c  mov     rax, [rbp+8]
0x140035150  movups  [rbp+var_30], xmm0
0x140035154  mov     qword ptr [rbp+var_30], rax
0x140035158  or      eax, 0FFFFFFFFh
0x14003515b  mov     dword ptr [rbp+var_20+8], eax
0x14003515e  mov     dword ptr [rbp+var_20+0Ch], eax
0x140035161  mov     rax, rdx
0x140035164  mov     dword ptr [rbp+var_40], 0Bh
0x14003516b  mov     byte ptr [rbp+var_10], 1
0x14003516f  mov     byte ptr [rbp+var_30+8], 0
0x140035173  mov     qword ptr [rbp+var_20], 0
0x14003517b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035180  add     rsp, 60h
0x140035184  pop     rbp
0x140035185  retn
```
