# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18003a1ec`
- end: `0x18003a28e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c96c`

## callees

- `0x18003a1ec`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18003a20d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18003a20d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a227`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a227`

## string_xrefs

- `0x18003a201`: `ntdll.dll`

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
0x18003a1ec  push    rbp
0x18003a1ee  mov     rbp, rsp
0x18003a1f1  sub     rsp, 60h
0x18003a1f5  lea     r8, [rbp+phModule]; phModule
0x18003a1f9  mov     [rbp+phModule], 0
0x18003a201  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18003a208  mov     ecx, 2; dwFlags
0x18003a20d  call    cs:__imp_GetModuleHandleExA
0x18003a213  test    eax, eax
0x18003a215  jz      short loc_18003A288
0x18003a217  mov     rcx, [rbp+phModule]; hModule
0x18003a21b  test    rcx, rcx
0x18003a21e  jz      short loc_18003A288
0x18003a220  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18003a227  call    cs:__imp_GetProcAddress
0x18003a22d  mov     rdx, rax
0x18003a230  test    rax, rax
0x18003a233  jz      short loc_18003A288
0x18003a235  xor     eax, eax
0x18003a237  lea     rcx, [rbp+var_40]
0x18003a23b  mov     [rbp+var_10], eax
0x18003a23e  xorps   xmm0, xmm0
0x18003a241  movups  [rbp+var_20], xmm0
0x18003a245  lea     rax, __ImageBase
0x18003a24c  movups  [rbp+var_40], xmm0
0x18003a250  mov     qword ptr [rbp+var_40+8], rax
0x18003a254  mov     rax, [rbp+8]
0x18003a258  movups  [rbp+var_30], xmm0
0x18003a25c  mov     qword ptr [rbp+var_30], rax
0x18003a260  or      eax, 0FFFFFFFFh
0x18003a263  mov     dword ptr [rbp+var_20+8], eax
0x18003a266  mov     dword ptr [rbp+var_20+0Ch], eax
0x18003a269  mov     rax, rdx
0x18003a26c  mov     dword ptr [rbp+var_40], 0Bh
0x18003a273  mov     byte ptr [rbp+var_10], 1
0x18003a277  mov     byte ptr [rbp+var_30+8], 0
0x18003a27b  mov     qword ptr [rbp+var_20], 0
0x18003a283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a288  add     rsp, 60h
0x18003a28c  pop     rbp
0x18003a28d  retn
```
