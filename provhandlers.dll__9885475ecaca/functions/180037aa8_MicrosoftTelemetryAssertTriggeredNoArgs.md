# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180037aa8`
- end: `0x180037b4a`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a59c`
- `0x18000eb00`
- `0x18000eb90`
- `0x18000ec20`
- `0x18000eca0`
- `0x18000ecf0`
- `0x18000ed40`
- `0x18000efa0`
- `0x180011c90`
- `0x180013e50`
- `0x18001504c`
- `0x180016a28`
- `0x180021e9c`
- `0x180036414`

## callees

- `0x180037aa8`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180037ac9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180037ac9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037ae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037ae3`

## string_xrefs

- `0x180037abd`: `ntdll.dll`

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
0x180037aa8  push    rbp
0x180037aaa  mov     rbp, rsp
0x180037aad  sub     rsp, 60h
0x180037ab1  lea     r8, [rbp+phModule]; phModule
0x180037ab5  mov     [rbp+phModule], 0
0x180037abd  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180037ac4  mov     ecx, 2; dwFlags
0x180037ac9  call    cs:__imp_GetModuleHandleExA
0x180037acf  test    eax, eax
0x180037ad1  jz      short loc_180037B44
0x180037ad3  mov     rcx, [rbp+phModule]; hModule
0x180037ad7  test    rcx, rcx
0x180037ada  jz      short loc_180037B44
0x180037adc  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180037ae3  call    cs:__imp_GetProcAddress
0x180037ae9  mov     rdx, rax
0x180037aec  test    rax, rax
0x180037aef  jz      short loc_180037B44
0x180037af1  xor     eax, eax
0x180037af3  lea     rcx, [rbp+var_40]
0x180037af7  mov     [rbp+var_10], eax
0x180037afa  xorps   xmm0, xmm0
0x180037afd  movups  [rbp+var_20], xmm0
0x180037b01  lea     rax, cs:180000000h
0x180037b08  movups  [rbp+var_40], xmm0
0x180037b0c  mov     qword ptr [rbp+var_40+8], rax
0x180037b10  mov     rax, [rbp+8]
0x180037b14  movups  [rbp+var_30], xmm0
0x180037b18  mov     qword ptr [rbp+var_30], rax
0x180037b1c  or      eax, 0FFFFFFFFh
0x180037b1f  mov     dword ptr [rbp+var_20+8], eax
0x180037b22  mov     dword ptr [rbp+var_20+0Ch], eax
0x180037b25  mov     rax, rdx
0x180037b28  mov     dword ptr [rbp+var_40], 0Bh
0x180037b2f  mov     byte ptr [rbp+var_10], 1
0x180037b33  mov     byte ptr [rbp+var_30+8], 0
0x180037b37  mov     qword ptr [rbp+var_20], 0
0x180037b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b44  add     rsp, 60h
0x180037b48  pop     rbp
0x180037b49  retn
```
