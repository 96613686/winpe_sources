# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18002f648`
- end: `0x18002f6f7`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007564`
- `0x1800193a0`
- `0x1800206ac`

## callees

- `0x18002f648`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002f669`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18002f669`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f689`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f689`

## string_xrefs

- `0x18002f65d`: `ntdll.dll`

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
0x18002f648  push    rbp
0x18002f64a  mov     rbp, rsp
0x18002f64d  sub     rsp, 60h
0x18002f651  lea     r8, [rbp+phModule]; phModule
0x18002f655  mov     [rbp+phModule], 0
0x18002f65d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18002f664  mov     ecx, 2; dwFlags
0x18002f669  call    cs:__imp_GetModuleHandleExA
0x18002f670  nop     dword ptr [rax+rax+00h]
0x18002f675  test    eax, eax
0x18002f677  jz      short loc_18002F6F0
0x18002f679  mov     rcx, [rbp+phModule]; hModule
0x18002f67d  test    rcx, rcx
0x18002f680  jz      short loc_18002F6F0
0x18002f682  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18002f689  call    cs:__imp_GetProcAddress
0x18002f690  nop     dword ptr [rax+rax+00h]
0x18002f695  mov     rdx, rax
0x18002f698  test    rax, rax
0x18002f69b  jz      short loc_18002F6F0
0x18002f69d  xor     eax, eax
0x18002f69f  lea     rcx, [rbp+var_40]
0x18002f6a3  mov     [rbp+var_10], eax
0x18002f6a6  xorps   xmm0, xmm0
0x18002f6a9  movups  [rbp+var_20], xmm0
0x18002f6ad  lea     rax, __ImageBase
0x18002f6b4  movups  [rbp+var_40], xmm0
0x18002f6b8  mov     qword ptr [rbp+var_40+8], rax
0x18002f6bc  mov     rax, [rbp+8]
0x18002f6c0  movups  [rbp+var_30], xmm0
0x18002f6c4  mov     qword ptr [rbp+var_30], rax
0x18002f6c8  or      eax, 0FFFFFFFFh
0x18002f6cb  mov     dword ptr [rbp+var_20+8], eax
0x18002f6ce  mov     dword ptr [rbp+var_20+0Ch], eax
0x18002f6d1  mov     rax, rdx
0x18002f6d4  mov     dword ptr [rbp+var_40], 0Bh
0x18002f6db  mov     byte ptr [rbp+var_10], 1
0x18002f6df  mov     byte ptr [rbp+var_30+8], 0
0x18002f6e3  mov     qword ptr [rbp+var_20], 0
0x18002f6eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6f0  add     rsp, 60h
0x18002f6f4  pop     rbp
0x18002f6f5  retn
```
