# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x14000f608`
- end: `0x14000f6c9`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `193`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000381c`
- `0x14000e1f4`
- `0x14000e324`
- `0x14000e534`
- `0x14000e994`
- `0x14000ef18`
- `0x14000f444`
- `0x14000f4a8`

## callees

- `0x14000f608`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f656`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f656`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14000f63c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14000f63c`

## string_xrefs

- `0x14000f630`: `ntdll.dll`

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
        v7[4] = "dwm.exe";
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
0x14000f608  mov     [rsp-8+arg_8], rbx
0x14000f60d  mov     [rsp-8+arg_10], rdi
0x14000f612  mov     [rsp-8+phModule], rcx
0x14000f617  push    rbp
0x14000f618  mov     rbp, rsp
0x14000f61b  sub     rsp, 60h
0x14000f61f  mov     ebx, r8d
0x14000f622  mov     [rbp+phModule], 0
0x14000f62a  mov     edi, edx
0x14000f62c  lea     r8, [rbp+phModule]; phModule
0x14000f630  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x14000f637  mov     ecx, 2; dwFlags
0x14000f63c  call    cs:__imp_GetModuleHandleExA
0x14000f642  test    eax, eax
0x14000f644  jz      short loc_14000F6B7
0x14000f646  mov     rcx, [rbp+phModule]; hModule
0x14000f64a  test    rcx, rcx
0x14000f64d  jz      short loc_14000F6B7
0x14000f64f  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x14000f656  call    cs:__imp_GetProcAddress
0x14000f65c  mov     rdx, rax
0x14000f65f  test    rax, rax
0x14000f662  jz      short loc_14000F6B7
0x14000f664  xor     eax, eax
0x14000f666  lea     rcx, [rbp+var_40]
0x14000f66a  mov     [rbp+var_10], eax
0x14000f66d  xorps   xmm0, xmm0
0x14000f670  movups  [rbp+var_20], xmm0
0x14000f674  lea     rax, __ImageBase
0x14000f67b  movups  [rbp+var_40], xmm0
0x14000f67f  mov     qword ptr [rbp+var_40+8], rax
0x14000f683  mov     rax, [rbp+8]
0x14000f687  movups  [rbp+var_30], xmm0
0x14000f68b  mov     qword ptr [rbp+var_30], rax
0x14000f68f  lea     rax, aDwmExe; "dwm.exe"
0x14000f696  mov     qword ptr [rbp+var_20], rax
0x14000f69a  mov     rax, rdx
0x14000f69d  mov     dword ptr [rbp+var_40], 0Bh
0x14000f6a4  mov     byte ptr [rbp+var_10], 1
0x14000f6a8  mov     byte ptr [rbp+var_30+8], 1
0x14000f6ac  mov     dword ptr [rbp+var_20+8], edi
0x14000f6af  mov     dword ptr [rbp+var_20+0Ch], ebx
0x14000f6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6b7  lea     r11, [rsp+60h+var_s0]
0x14000f6bc  mov     rbx, [r11+18h]
0x14000f6c0  mov     rdi, [r11+20h]
0x14000f6c4  mov     rsp, r11
0x14000f6c7  pop     rbp
0x14000f6c8  retn
```
