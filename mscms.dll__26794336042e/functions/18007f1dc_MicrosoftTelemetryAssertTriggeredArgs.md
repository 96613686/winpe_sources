# MicrosoftTelemetryAssertTriggeredArgs

- ea: `0x18007f1dc`
- end: `0x18007f292`
- name: `MicrosoftTelemetryAssertTriggeredArgs`
- size: `182`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047f20`

## callees

- `0x18007f1dc`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18007f208`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18007f208`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f222`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007f222`

## string_xrefs

- `0x18007f25b`: `mscms.dll`
- `0x18007f1f8`: `ntdll.dll`

## pseudocode

```c
int __fastcall MicrosoftTelemetryAssertTriggeredArgs(__int64 a1, unsigned int a2)
{
  FARPROC ProcAddress; // rax
  _QWORD v5[6]; // [rsp+20h] [rbp-40h] BYREF
  int v6; // [rsp+50h] [rbp-10h]
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
        v6 = 1;
        v5[1] = &_ImageBase;
        v5[3] = 1;
        v5[2] = retaddr;
        v5[4] = "mscms.dll";
        v5[0] = 11;
        v5[5] = a2;
        LODWORD(ProcAddress) = ((__int64 (__fastcall *)(_QWORD *))ProcAddress)(v5);
      }
    }
  }
  return (int)ProcAddress;
}

```

## disassembly

```asm
0x18007f1dc  mov     [rsp-8+arg_8], rbx
0x18007f1e1  mov     [rsp-8+phModule], rcx
0x18007f1e6  push    rbp
0x18007f1e7  mov     rbp, rsp
0x18007f1ea  sub     rsp, 60h
0x18007f1ee  mov     ebx, edx
0x18007f1f0  mov     [rbp+phModule], 0
0x18007f1f8  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18007f1ff  mov     ecx, 2; dwFlags
0x18007f204  lea     r8, [rbp+phModule]; phModule
0x18007f208  call    cs:__imp_GetModuleHandleExA
0x18007f20e  test    eax, eax
0x18007f210  jz      short loc_18007F287
0x18007f212  mov     rcx, [rbp+phModule]; hModule
0x18007f216  test    rcx, rcx
0x18007f219  jz      short loc_18007F287
0x18007f21b  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18007f222  call    cs:__imp_GetProcAddress
0x18007f228  mov     rdx, rax
0x18007f22b  test    rax, rax
0x18007f22e  jz      short loc_18007F287
0x18007f230  xor     eax, eax
0x18007f232  lea     rcx, [rbp+var_40]
0x18007f236  mov     [rbp+var_10], eax
0x18007f239  xorps   xmm0, xmm0
0x18007f23c  movups  [rbp+var_20], xmm0
0x18007f240  lea     rax, __ImageBase
0x18007f247  movups  [rbp+var_40], xmm0
0x18007f24b  mov     qword ptr [rbp+var_40+8], rax
0x18007f24f  mov     rax, [rbp+8]
0x18007f253  movups  [rbp+var_30], xmm0
0x18007f257  mov     qword ptr [rbp+var_30], rax
0x18007f25b  lea     rax, aMscmsDll_1; "mscms.dll"
0x18007f262  mov     qword ptr [rbp+var_20], rax
0x18007f266  mov     rax, rdx
0x18007f269  mov     dword ptr [rbp+var_40], 0Bh
0x18007f270  mov     byte ptr [rbp+var_10], 1
0x18007f274  mov     byte ptr [rbp+var_30+8], 1
0x18007f278  mov     dword ptr [rbp+var_20+8], ebx
0x18007f27b  mov     dword ptr [rbp+var_20+0Ch], 0
0x18007f282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f287  mov     rbx, [rsp+60h+arg_8]
0x18007f28c  add     rsp, 60h
0x18007f290  pop     rbp
0x18007f291  retn
```
