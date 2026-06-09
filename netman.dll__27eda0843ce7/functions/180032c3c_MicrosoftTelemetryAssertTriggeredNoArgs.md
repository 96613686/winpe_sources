# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x180032c3c`
- end: `0x180032cde`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `60`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800046f0`
- `0x180006d50`
- `0x18001ab80`
- `0x18001b1e8`
- `0x18001b570`
- `0x18001c148`
- `0x18001ccd0`
- `0x18001d4c0`
- `0x18001eb7c`
- `0x18001f328`
- `0x18001f710`
- `0x18001fe84`
- `0x180020020`
- `0x180020db0`
- `0x180020ed4`
- `0x1800212b4`
- `0x180021990`
- `0x180022098`
- `0x180022c70`
- `0x180023f40`
- `0x1800240d4`
- `0x1800241b8`
- `0x180024760`
- `0x180024b70`
- `0x180024c00`
- `0x180024db0`
- `0x180025734`
- `0x180025ab4`
- `0x180025b84`
- `0x180025e80`
- `0x180027930`
- `0x180027af0`
- `0x180028c30`
- `0x1800297a0`
- `0x180029e08`
- `0x18002a1b0`
- `0x18002a3f0`
- `0x18002a6d0`
- `0x18002a9c0`
- `0x18002ab94`
- `0x18002ac24`
- `0x18002b2d0`
- `0x18002b7a0`
- `0x18002b7d0`
- `0x18002bd30`
- `0x18002c48c`
- `0x18002ceb4`
- `0x18002cedc`
- `0x18002cf14`
- `0x18002cf50`

## callees

- `0x180032c3c`
- `0x180036010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180032c77`
- `KERNEL32!GetProcAddress` at `0x180032c77`
- `KERNEL32!GetModuleHandleExA` at `0x180032c5d`
- `KERNEL32!GetModuleHandleExA` at `0x180032c5d`

## string_xrefs

- `0x180032c51`: `ntdll.dll`

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
0x180032c3c  push    rbp
0x180032c3e  mov     rbp, rsp
0x180032c41  sub     rsp, 60h
0x180032c45  lea     r8, [rbp+phModule]; phModule
0x180032c49  mov     [rbp+phModule], 0
0x180032c51  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x180032c58  mov     ecx, 2; dwFlags
0x180032c5d  call    cs:__imp_GetModuleHandleExA
0x180032c63  test    eax, eax
0x180032c65  jz      short loc_180032CD8
0x180032c67  mov     rcx, [rbp+phModule]; hModule
0x180032c6b  test    rcx, rcx
0x180032c6e  jz      short loc_180032CD8
0x180032c70  lea     rdx, aMicrosofttelem; "MicrosoftTelemetryAssertTriggeredUM"
0x180032c77  call    cs:__imp_GetProcAddress
0x180032c7d  mov     rdx, rax
0x180032c80  test    rax, rax
0x180032c83  jz      short loc_180032CD8
0x180032c85  xor     eax, eax
0x180032c87  lea     rcx, [rbp+var_40]
0x180032c8b  mov     [rbp+var_10], eax
0x180032c8e  xorps   xmm0, xmm0
0x180032c91  movups  [rbp+var_20], xmm0
0x180032c95  lea     rax, __ImageBase
0x180032c9c  movups  [rbp+var_40], xmm0
0x180032ca0  mov     qword ptr [rbp+var_40+8], rax
0x180032ca4  mov     rax, [rbp+8]
0x180032ca8  movups  [rbp+var_30], xmm0
0x180032cac  mov     qword ptr [rbp+var_30], rax
0x180032cb0  or      eax, 0FFFFFFFFh
0x180032cb3  mov     dword ptr [rbp+var_20+8], eax
0x180032cb6  mov     dword ptr [rbp+var_20+0Ch], eax
0x180032cb9  mov     rax, rdx
0x180032cbc  mov     dword ptr [rbp+var_40], 0Bh
0x180032cc3  mov     byte ptr [rbp+var_10], 1
0x180032cc7  mov     byte ptr [rbp+var_30+8], 0
0x180032ccb  mov     qword ptr [rbp+var_20], 0
0x180032cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cd8  add     rsp, 60h
0x180032cdc  pop     rbp
0x180032cdd  retn
```
