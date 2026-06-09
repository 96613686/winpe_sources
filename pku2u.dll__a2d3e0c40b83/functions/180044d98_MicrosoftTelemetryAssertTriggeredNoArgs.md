# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180044d98`
- end: `0x180044e3a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001bf0`
- `0x180005840`
- `0x180006250`
- `0x18000a370`
- `0x180017820`
- `0x180017880`
- `0x18001e368`
- `0x1800394b8`
- `0x180039dac`
- `0x18003a688`
- `0x18003ab04`
- `0x18003ac00`

## callees

- `0x180044d98`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180044db9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180044db9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044dd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180044dd3`

## string_xrefs

- `0x180044dad`: `ntdll.dll`

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
0x180044d98  push    rbp
0x180044d9a  mov     rbp, rsp
0x180044d9d  sub     rsp, 60h
0x180044da1  lea     r8, [rbp+phModule]; phModule
0x180044da5  mov     [rbp+phModule], 0
0x180044dad  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180044db4  mov     ecx, 2; dwFlags
0x180044db9  call    cs:__imp_GetModuleHandleExA
0x180044dbf  test    eax, eax
0x180044dc1  jz      short loc_180044E34
0x180044dc3  mov     rcx, [rbp+phModule]; hModule
0x180044dc7  test    rcx, rcx
0x180044dca  jz      short loc_180044E34
0x180044dcc  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180044dd3  call    cs:__imp_GetProcAddress
0x180044dd9  mov     rdx, rax
0x180044ddc  test    rax, rax
0x180044ddf  jz      short loc_180044E34
0x180044de1  xor     eax, eax
0x180044de3  lea     rcx, [rbp+var_40]
0x180044de7  mov     [rbp+var_10], eax
0x180044dea  xorps   xmm0, xmm0
0x180044ded  movups  [rbp+var_20], xmm0
0x180044df1  lea     rax, __ImageBase
0x180044df8  movups  [rbp+var_40], xmm0
0x180044dfc  mov     qword ptr [rbp+var_40+8], rax
0x180044e00  mov     rax, [rbp+8]
0x180044e04  movups  [rbp+var_30], xmm0
0x180044e08  mov     qword ptr [rbp+var_30], rax
0x180044e0c  or      eax, 0FFFFFFFFh
0x180044e0f  mov     dword ptr [rbp+var_20+8], eax
0x180044e12  mov     dword ptr [rbp+var_20+0Ch], eax
0x180044e15  mov     rax, rdx
0x180044e18  mov     dword ptr [rbp+var_40], 0Bh
0x180044e1f  mov     byte ptr [rbp+var_10], 1
0x180044e23  mov     byte ptr [rbp+var_30+8], 0
0x180044e27  mov     qword ptr [rbp+var_20], 0
0x180044e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e34  add     rsp, 60h
0x180044e38  pop     rbp
0x180044e39  retn
```
