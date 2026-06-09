# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001a178`
- end: `0x18001a21a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e170`
- `0x180017ac4`
- `0x180017c20`
- `0x180017e40`
- `0x180017ea0`
- `0x180017ef0`
- `0x180017f40`
- `0x180017fa0`
- `0x180017fe0`
- `0x180018040`
- `0x180018240`
- `0x1800184c8`
- `0x180018550`

## callees

- `0x18001a178`
- `0x18001c010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001a1b3`
- `KERNEL32!GetProcAddress` at `0x18001a1b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a199`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001a199`

## string_xrefs

- `0x18001a18d`: `ntdll.dll`

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
0x18001a178  push    rbp
0x18001a17a  mov     rbp, rsp
0x18001a17d  sub     rsp, 60h
0x18001a181  lea     r8, [rbp+phModule]; phModule
0x18001a185  mov     [rbp+phModule], 0
0x18001a18d  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001a194  mov     ecx, 2; dwFlags
0x18001a199  call    cs:__imp_GetModuleHandleExA
0x18001a19f  test    eax, eax
0x18001a1a1  jz      short loc_18001A214
0x18001a1a3  mov     rcx, [rbp+phModule]; hModule
0x18001a1a7  test    rcx, rcx
0x18001a1aa  jz      short loc_18001A214
0x18001a1ac  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001a1b3  call    cs:__imp_GetProcAddress
0x18001a1b9  mov     rdx, rax
0x18001a1bc  test    rax, rax
0x18001a1bf  jz      short loc_18001A214
0x18001a1c1  xor     eax, eax
0x18001a1c3  lea     rcx, [rbp+var_40]
0x18001a1c7  mov     [rbp+var_10], eax
0x18001a1ca  xorps   xmm0, xmm0
0x18001a1cd  movups  [rbp+var_20], xmm0
0x18001a1d1  lea     rax, cs:180000000h
0x18001a1d8  movups  [rbp+var_40], xmm0
0x18001a1dc  mov     qword ptr [rbp+var_40+8], rax
0x18001a1e0  mov     rax, [rbp+8]
0x18001a1e4  movups  [rbp+var_30], xmm0
0x18001a1e8  mov     qword ptr [rbp+var_30], rax
0x18001a1ec  or      eax, 0FFFFFFFFh
0x18001a1ef  mov     dword ptr [rbp+var_20+8], eax
0x18001a1f2  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001a1f5  mov     rax, rdx
0x18001a1f8  mov     dword ptr [rbp+var_40], 0Bh
0x18001a1ff  mov     byte ptr [rbp+var_10], 1
0x18001a203  mov     byte ptr [rbp+var_30+8], 0
0x18001a207  mov     qword ptr [rbp+var_20], 0
0x18001a20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a214  add     rsp, 60h
0x18001a218  pop     rbp
0x18001a219  retn
```
