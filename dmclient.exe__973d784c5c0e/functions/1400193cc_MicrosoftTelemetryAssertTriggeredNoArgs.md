# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x1400193cc`
- end: `0x14001947b`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400126c4`

## callees

- `0x1400193cc`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400193ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400193ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001940d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001940d`

## string_xrefs

- `0x1400193e1`: `ntdll.dll`

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
0x1400193cc  push    rbp
0x1400193ce  mov     rbp, rsp
0x1400193d1  sub     rsp, 60h
0x1400193d5  lea     r8, [rbp+phModule]; phModule
0x1400193d9  mov     [rbp+phModule], 0
0x1400193e1  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1400193e8  mov     ecx, 2; dwFlags
0x1400193ed  call    cs:__imp_GetModuleHandleExA
0x1400193f4  nop     dword ptr [rax+rax+00h]
0x1400193f9  test    eax, eax
0x1400193fb  jz      short loc_140019474
0x1400193fd  mov     rcx, [rbp+phModule]; hModule
0x140019401  test    rcx, rcx
0x140019404  jz      short loc_140019474
0x140019406  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x14001940d  call    cs:__imp_GetProcAddress
0x140019414  nop     dword ptr [rax+rax+00h]
0x140019419  mov     rdx, rax
0x14001941c  test    rax, rax
0x14001941f  jz      short loc_140019474
0x140019421  xor     eax, eax
0x140019423  lea     rcx, [rbp+var_40]
0x140019427  mov     [rbp+var_10], eax
0x14001942a  xorps   xmm0, xmm0
0x14001942d  movups  [rbp+var_20], xmm0
0x140019431  lea     rax, __ImageBase
0x140019438  movups  [rbp+var_40], xmm0
0x14001943c  mov     qword ptr [rbp+var_40+8], rax
0x140019440  mov     rax, [rbp+8]
0x140019444  movups  [rbp+var_30], xmm0
0x140019448  mov     qword ptr [rbp+var_30], rax
0x14001944c  or      eax, 0FFFFFFFFh
0x14001944f  mov     dword ptr [rbp+var_20+8], eax
0x140019452  mov     dword ptr [rbp+var_20+0Ch], eax
0x140019455  mov     rax, rdx
0x140019458  mov     dword ptr [rbp+var_40], 0Bh
0x14001945f  mov     byte ptr [rbp+var_10], 1
0x140019463  mov     byte ptr [rbp+var_30+8], 0
0x140019467  mov     qword ptr [rbp+var_20], 0
0x14001946f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019474  add     rsp, 60h
0x140019478  pop     rbp
0x140019479  retn
```
