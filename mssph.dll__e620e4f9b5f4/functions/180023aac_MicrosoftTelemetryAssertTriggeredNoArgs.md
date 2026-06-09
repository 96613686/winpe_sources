# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180023aac`
- end: `0x180023b4e`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ff2c`
- `0x180021770`

## callees

- `0x180023aac`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180023acd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180023acd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023ae7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023ae7`

## string_xrefs

- `0x180023ac1`: `ntdll.dll`

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
0x180023aac  push    rbp
0x180023aae  mov     rbp, rsp
0x180023ab1  sub     rsp, 60h
0x180023ab5  lea     r8, [rbp+phModule]; phModule
0x180023ab9  mov     [rbp+phModule], 0
0x180023ac1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180023ac8  mov     ecx, 2; dwFlags
0x180023acd  call    cs:__imp_GetModuleHandleExA
0x180023ad3  test    eax, eax
0x180023ad5  jz      short loc_180023B48
0x180023ad7  mov     rcx, [rbp+phModule]; hModule
0x180023adb  test    rcx, rcx
0x180023ade  jz      short loc_180023B48
0x180023ae0  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180023ae7  call    cs:__imp_GetProcAddress
0x180023aed  mov     rdx, rax
0x180023af0  test    rax, rax
0x180023af3  jz      short loc_180023B48
0x180023af5  xor     eax, eax
0x180023af7  lea     rcx, [rbp+var_40]
0x180023afb  mov     [rbp+var_10], eax
0x180023afe  xorps   xmm0, xmm0
0x180023b01  movups  [rbp+var_20], xmm0
0x180023b05  lea     rax, __ImageBase
0x180023b0c  movups  [rbp+var_40], xmm0
0x180023b10  mov     qword ptr [rbp+var_40+8], rax
0x180023b14  mov     rax, [rbp+8]
0x180023b18  movups  [rbp+var_30], xmm0
0x180023b1c  mov     qword ptr [rbp+var_30], rax
0x180023b20  or      eax, 0FFFFFFFFh
0x180023b23  mov     dword ptr [rbp+var_20+8], eax
0x180023b26  mov     dword ptr [rbp+var_20+0Ch], eax
0x180023b29  mov     rax, rdx
0x180023b2c  mov     dword ptr [rbp+var_40], 0Bh
0x180023b33  mov     byte ptr [rbp+var_10], 1
0x180023b37  mov     byte ptr [rbp+var_30+8], 0
0x180023b3b  mov     qword ptr [rbp+var_20], 0
0x180023b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b48  add     rsp, 60h
0x180023b4c  pop     rbp
0x180023b4d  retn
```
