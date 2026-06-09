# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1800035a0`
- end: `0x180003648`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `168`
- prototype: `int()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001e70`

## callees

- `0x1800035a0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800035d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800035be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800035be`

## string_xrefs

- `0x1800035ad`: `ntdll.dll`

## pseudocode

```c
int MicrosoftTelemetryAssertTriggeredNoArgs()
{
  FARPROC ProcAddress; // rax
  _QWORD v2[3]; // [rsp+20h] [rbp-48h] BYREF
  char v3; // [rsp+38h] [rbp-30h]
  int v4; // [rsp+39h] [rbp-2Fh]
  __int16 v5; // [rsp+3Dh] [rbp-2Bh]
  char v6; // [rsp+3Fh] [rbp-29h]
  __int64 v7; // [rsp+40h] [rbp-28h]
  __int64 v8; // [rsp+48h] [rbp-20h]
  char v9; // [rsp+50h] [rbp-18h]
  __int16 v10; // [rsp+51h] [rbp-17h]
  char v11; // [rsp+53h] [rbp-15h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  HMODULE phModule; // [rsp+70h] [rbp+8h] BYREF

  phModule = 0;
  LODWORD(ProcAddress) = GetModuleHandleExA(2u, "ntdll.dll", &phModule);
  if ( (_DWORD)ProcAddress )
  {
    if ( phModule )
    {
      ProcAddress = GetProcAddress(phModule, "MicrosoftTelemetryAssertTriggeredUM");
      if ( ProcAddress )
      {
        v2[0] = 11;
        v6 = 0;
        v11 = 0;
        v2[1] = &_ImageBase;
        v2[2] = retaddr;
        v4 = 0;
        v5 = 0;
        v10 = 0;
        v9 = 1;
        v3 = 0;
        v7 = 0;
        v8 = -1;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v2);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x1800035a0  push    rbx
0x1800035a2  sub     rsp, 60h
0x1800035a6  xor     ebx, ebx
0x1800035a8  lea     r8, [rsp+68h+phModule]; phModule
0x1800035ad  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800035b4  mov     [rsp+68h+phModule], rbx
0x1800035b9  mov     ecx, 2; dwFlags
0x1800035be  call    cs:__imp_GetModuleHandleExA
0x1800035c4  test    eax, eax
0x1800035c6  jz      short loc_180003642
0x1800035c8  mov     rcx, [rsp+68h+phModule]; hModule
0x1800035cd  test    rcx, rcx
0x1800035d0  jz      short loc_180003642
0x1800035d2  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x1800035d9  call    cs:__imp_GetProcAddress
0x1800035df  mov     rdx, rax
0x1800035e2  test    rax, rax
0x1800035e5  jz      short loc_180003642
0x1800035e7  xor     eax, eax
0x1800035e9  mov     [rsp+68h+var_48], 0Bh
0x1800035f2  mov     [rsp+68h+var_29], al
0x1800035f6  lea     rcx, [rsp+68h+var_48]
0x1800035fb  mov     [rsp+68h+var_15], al
0x1800035ff  lea     rax, __ImageBase
0x180003606  mov     [rsp+68h+var_40], rax
0x18000360b  mov     rax, [rsp+68h]
0x180003610  mov     [rsp+68h+var_38], rax
0x180003615  mov     rax, rdx
0x180003618  mov     [rsp+68h+var_2F], ebx
0x18000361c  mov     [rsp+68h+var_2B], bx
0x180003621  mov     [rsp+68h+var_17], bx
0x180003626  mov     [rsp+68h+var_18], 1
0x18000362b  mov     [rsp+68h+var_30], bl
0x18000362f  mov     [rsp+68h+var_28], rbx
0x180003634  mov     [rsp+68h+var_20], 0FFFFFFFFFFFFFFFFh
0x18000363d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003642  add     rsp, 60h
0x180003646  pop     rbx
0x180003647  retn
```
