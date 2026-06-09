# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000dd64`
- end: `0x18000de13`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: `int()`
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f20`
- `0x180009250`
- `0x18000cf64`
- `0x18000d0e0`
- `0x18000d450`
- `0x18000d4b0`
- `0x18000d500`
- `0x18000d560`
- `0x18000d670`
- `0x18000d6c0`
- `0x18000d720`
- `0x18000d980`
- `0x18000dab4`
- `0x18000db44`

## callees

- `0x18000dd64`
- `0x18000f010`

## import_xrefs

- `KERNEL32!GetModuleHandleExA` at `0x18000dd85`
- `KERNEL32!GetModuleHandleExA` at `0x18000dd85`
- `KERNEL32!GetProcAddress` at `0x18000dda5`
- `KERNEL32!GetProcAddress` at `0x18000dda5`

## string_xrefs

- `0x18000dd79`: `ntdll.dll`

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
0x18000dd64  push    rbp
0x18000dd66  mov     rbp, rsp
0x18000dd69  sub     rsp, 60h
0x18000dd6d  lea     r8, [rbp+phModule]; phModule
0x18000dd71  mov     [rbp+phModule], 0
0x18000dd79  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18000dd80  mov     ecx, 2; dwFlags
0x18000dd85  call    cs:__imp_GetModuleHandleExA
0x18000dd8c  nop     dword ptr [rax+rax+00h]
0x18000dd91  test    eax, eax
0x18000dd93  jz      short loc_18000DE0C
0x18000dd95  mov     rcx, [rbp+phModule]; hModule
0x18000dd99  test    rcx, rcx
0x18000dd9c  jz      short loc_18000DE0C
0x18000dd9e  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x18000dda5  call    cs:__imp_GetProcAddress
0x18000ddac  nop     dword ptr [rax+rax+00h]
0x18000ddb1  mov     rdx, rax
0x18000ddb4  test    rax, rax
0x18000ddb7  jz      short loc_18000DE0C
0x18000ddb9  xor     eax, eax
0x18000ddbb  lea     rcx, [rbp+var_40]
0x18000ddbf  mov     [rbp+var_10], eax
0x18000ddc2  xorps   xmm0, xmm0
0x18000ddc5  movups  [rbp+var_20], xmm0
0x18000ddc9  lea     rax, cs:180000000h
0x18000ddd0  movups  [rbp+var_40], xmm0
0x18000ddd4  mov     qword ptr [rbp+var_40+8], rax
0x18000ddd8  mov     rax, [rbp+8]
0x18000dddc  movups  [rbp+var_30], xmm0
0x18000dde0  mov     qword ptr [rbp+var_30], rax
0x18000dde4  or      eax, 0FFFFFFFFh
0x18000dde7  mov     dword ptr [rbp+var_20+8], eax
0x18000ddea  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000dded  mov     rax, rdx
0x18000ddf0  mov     dword ptr [rbp+var_40], 0Bh
0x18000ddf7  mov     byte ptr [rbp+var_10], 1
0x18000ddfb  mov     byte ptr [rbp+var_30+8], 0
0x18000ddff  mov     qword ptr [rbp+var_20], 0
0x18000de07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0c  add     rsp, 60h
0x18000de10  pop     rbp
0x18000de11  retn
```
