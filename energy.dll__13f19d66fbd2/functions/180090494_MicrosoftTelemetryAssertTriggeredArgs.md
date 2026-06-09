# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x180090494`
- end: `0x180090555`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005ee50`

## callees

- `0x180090494`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800904e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800904e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800904c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1800904c8`

## string_xrefs

- `0x1800904bc`: `ntdll.dll`
- `0x18009051b`: `energy.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, int a2, int a3)
{
  FARPROC ProcAddress; // rax
  _QWORD v7[5]; // [rsp+20h] [rbp-40h] BYREF
  int v8; // [rsp+48h] [rbp-18h]
  int v9; // [rsp+4Ch] [rbp-14h]
  int v10; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+8h]
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
        v10 = 1;
        v7[1] = &_ImageBase;
        v7[3] = 1;
        v7[2] = retaddr;
        v7[4] = "energy.dll";
        v7[0] = 11;
        v8 = a2;
        v9 = a3;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v7);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x180090494  mov     [rsp-8+arg_8], rbx
0x180090499  mov     [rsp-8+arg_10], rdi
0x18009049e  mov     [rsp-8+phModule], rcx
0x1800904a3  push    rbp
0x1800904a4  mov     rbp, rsp
0x1800904a7  sub     rsp, 60h
0x1800904ab  mov     ebx, r8d
0x1800904ae  mov     [rbp+phModule], 0
0x1800904b6  mov     edi, edx
0x1800904b8  lea     r8, [rbp+phModule]; phModule
0x1800904bc  lea     rdx, ModuleName; "ntdll.dll"
0x1800904c3  mov     ecx, 2; dwFlags
0x1800904c8  call    cs:__imp_GetModuleHandleExA
0x1800904ce  test    eax, eax
0x1800904d0  jz      short loc_180090543
0x1800904d2  mov     rcx, [rbp+phModule]; hModule
0x1800904d6  test    rcx, rcx
0x1800904d9  jz      short loc_180090543
0x1800904db  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x1800904e2  call    cs:__imp_GetProcAddress
0x1800904e8  mov     rdx, rax
0x1800904eb  test    rax, rax
0x1800904ee  jz      short loc_180090543
0x1800904f0  xor     eax, eax
0x1800904f2  lea     rcx, [rbp+var_40]
0x1800904f6  mov     [rbp+var_10], eax
0x1800904f9  xorps   xmm0, xmm0
0x1800904fc  movups  [rbp+var_20], xmm0
0x180090500  lea     rax, __ImageBase
0x180090507  movups  [rbp+var_40], xmm0
0x18009050b  mov     qword ptr [rbp+var_40+8], rax
0x18009050f  mov     rax, [rbp+8]
0x180090513  movups  [rbp+var_30], xmm0
0x180090517  mov     qword ptr [rbp+var_30], rax
0x18009051b  lea     rax, aEnergyDll_1; "energy.dll"
0x180090522  mov     qword ptr [rbp+var_20], rax
0x180090526  mov     rax, rdx
0x180090529  mov     dword ptr [rbp+var_40], 0Bh
0x180090530  mov     byte ptr [rbp+var_10], 1
0x180090534  mov     byte ptr [rbp+var_30+8], 1
0x180090538  mov     dword ptr [rbp+var_20+8], edi
0x18009053b  mov     dword ptr [rbp+var_20+0Ch], ebx
0x18009053e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090543  lea     r11, [rsp+60h+var_s0]
0x180090548  mov     rbx, [r11+18h]
0x18009054c  mov     rdi, [r11+20h]
0x180090550  mov     rsp, r11
0x180090553  pop     rbp
0x180090554  retn
```
