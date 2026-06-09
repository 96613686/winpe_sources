# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18001cc74`
- end: `0x18001cd23`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004804`

## callees

- `0x18001cc74`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001cc95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001cc95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccb5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccb5`

## string_xrefs

- `0x18001cc89`: `ntdll.dll`

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
0x18001cc74  push    rbp
0x18001cc76  mov     rbp, rsp
0x18001cc79  sub     rsp, 60h
0x18001cc7d  lea     r8, [rbp+phModule]; phModule
0x18001cc81  mov     [rbp+phModule], 0
0x18001cc89  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18001cc90  mov     ecx, 2; dwFlags
0x18001cc95  call    cs:__imp_GetModuleHandleExA
0x18001cc9c  nop     dword ptr [rax+rax+00h]
0x18001cca1  test    eax, eax
0x18001cca3  jz      short loc_18001CD1C
0x18001cca5  mov     rcx, [rbp+phModule]; hModule
0x18001cca9  test    rcx, rcx
0x18001ccac  jz      short loc_18001CD1C
0x18001ccae  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18001ccb5  call    cs:__imp_GetProcAddress
0x18001ccbc  nop     dword ptr [rax+rax+00h]
0x18001ccc1  mov     rdx, rax
0x18001ccc4  test    rax, rax
0x18001ccc7  jz      short loc_18001CD1C
0x18001ccc9  xor     eax, eax
0x18001cccb  lea     rcx, [rbp+var_40]
0x18001cccf  mov     [rbp+var_10], eax
0x18001ccd2  xorps   xmm0, xmm0
0x18001ccd5  movups  [rbp+var_20], xmm0
0x18001ccd9  lea     rax, __ImageBase
0x18001cce0  movups  [rbp+var_40], xmm0
0x18001cce4  mov     qword ptr [rbp+var_40+8], rax
0x18001cce8  mov     rax, [rbp+8]
0x18001ccec  movups  [rbp+var_30], xmm0
0x18001ccf0  mov     qword ptr [rbp+var_30], rax
0x18001ccf4  or      eax, 0FFFFFFFFh
0x18001ccf7  mov     dword ptr [rbp+var_20+8], eax
0x18001ccfa  mov     dword ptr [rbp+var_20+0Ch], eax
0x18001ccfd  mov     rax, rdx
0x18001cd00  mov     dword ptr [rbp+var_40], 0Bh
0x18001cd07  mov     byte ptr [rbp+var_10], 1
0x18001cd0b  mov     byte ptr [rbp+var_30+8], 0
0x18001cd0f  mov     qword ptr [rbp+var_20], 0
0x18001cd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd1c  add     rsp, 60h
0x18001cd20  pop     rbp
0x18001cd21  retn
```
