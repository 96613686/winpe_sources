# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180032388`
- end: `0x18003242a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024d6c`

## callees

- `0x180032388`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800323c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800323c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800323a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800323a9`

## string_xrefs

- `0x18003239d`: `ntdll.dll`

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
0x180032388  push    rbp
0x18003238a  mov     rbp, rsp
0x18003238d  sub     rsp, 60h
0x180032391  lea     r8, [rbp+phModule]; phModule
0x180032395  mov     [rbp+phModule], 0
0x18003239d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800323a4  mov     ecx, 2; dwFlags
0x1800323a9  call    cs:__imp_GetModuleHandleExA
0x1800323af  test    eax, eax
0x1800323b1  jz      short loc_180032424
0x1800323b3  mov     rcx, [rbp+phModule]; hModule
0x1800323b7  test    rcx, rcx
0x1800323ba  jz      short loc_180032424
0x1800323bc  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800323c3  call    cs:__imp_GetProcAddress
0x1800323c9  mov     rdx, rax
0x1800323cc  test    rax, rax
0x1800323cf  jz      short loc_180032424
0x1800323d1  xor     eax, eax
0x1800323d3  lea     rcx, [rbp+var_40]
0x1800323d7  mov     [rbp+var_10], eax
0x1800323da  xorps   xmm0, xmm0
0x1800323dd  movups  [rbp+var_20], xmm0
0x1800323e1  lea     rax, __ImageBase
0x1800323e8  movups  [rbp+var_40], xmm0
0x1800323ec  mov     qword ptr [rbp+var_40+8], rax
0x1800323f0  mov     rax, [rbp+8]
0x1800323f4  movups  [rbp+var_30], xmm0
0x1800323f8  mov     qword ptr [rbp+var_30], rax
0x1800323fc  or      eax, 0FFFFFFFFh
0x1800323ff  mov     dword ptr [rbp+var_20+8], eax
0x180032402  mov     dword ptr [rbp+var_20+0Ch], eax
0x180032405  mov     rax, rdx
0x180032408  mov     dword ptr [rbp+var_40], 0Bh
0x18003240f  mov     byte ptr [rbp+var_10], 1
0x180032413  mov     byte ptr [rbp+var_30+8], 0
0x180032417  mov     qword ptr [rbp+var_20], 0
0x18003241f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032424  add     rsp, 60h
0x180032428  pop     rbp
0x180032429  retn
```
