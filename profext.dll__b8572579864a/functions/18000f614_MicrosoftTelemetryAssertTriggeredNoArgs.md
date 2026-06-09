# MicrosoftTelemetryAssertTriggeredNoArgs

- ea: `0x18000f614`
- end: `0x18000f6c3`
- name: `MicrosoftTelemetryAssertTriggeredNoArgs`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002a80`
- `0x1800045bc`
- `0x180009504`
- `0x18000ca58`
- `0x18000d980`
- `0x18000ea1c`
- `0x18000f214`
- `0x180014d5c`
- `0x1800153b8`

## callees

- `0x18000f614`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000f635`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18000f635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f655`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f655`

## string_xrefs

- `0x18000f629`: `ntdll.dll`

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
0x18000f614  push    rbp
0x18000f616  mov     rbp, rsp
0x18000f619  sub     rsp, 60h
0x18000f61d  lea     r8, [rbp+phModule]; phModule
0x18000f621  mov     [rbp+phModule], 0
0x18000f629  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x18000f630  mov     ecx, 2; dwFlags
0x18000f635  call    cs:__imp_GetModuleHandleExA
0x18000f63c  nop     dword ptr [rax+rax+00h]
0x18000f641  test    eax, eax
0x18000f643  jz      short loc_18000F6BC
0x18000f645  mov     rcx, [rbp+phModule]; hModule
0x18000f649  test    rcx, rcx
0x18000f64c  jz      short loc_18000F6BC
0x18000f64e  lea     rdx, ProcName; "MicrosoftTelemetryAssertTriggeredUM"
0x18000f655  call    cs:__imp_GetProcAddress
0x18000f65c  nop     dword ptr [rax+rax+00h]
0x18000f661  mov     rdx, rax
0x18000f664  test    rax, rax
0x18000f667  jz      short loc_18000F6BC
0x18000f669  xor     eax, eax
0x18000f66b  lea     rcx, [rbp+var_40]
0x18000f66f  mov     [rbp+var_10], eax
0x18000f672  xorps   xmm0, xmm0
0x18000f675  movups  [rbp+var_20], xmm0
0x18000f679  lea     rax, __ImageBase
0x18000f680  movups  [rbp+var_40], xmm0
0x18000f684  mov     qword ptr [rbp+var_40+8], rax
0x18000f688  mov     rax, [rbp+8]
0x18000f68c  movups  [rbp+var_30], xmm0
0x18000f690  mov     qword ptr [rbp+var_30], rax
0x18000f694  or      eax, 0FFFFFFFFh
0x18000f697  mov     dword ptr [rbp+var_20+8], eax
0x18000f69a  mov     dword ptr [rbp+var_20+0Ch], eax
0x18000f69d  mov     rax, rdx
0x18000f6a0  mov     dword ptr [rbp+var_40], 0Bh
0x18000f6a7  mov     byte ptr [rbp+var_10], 1
0x18000f6ab  mov     byte ptr [rbp+var_30+8], 0
0x18000f6af  mov     qword ptr [rbp+var_20], 0
0x18000f6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6bc  add     rsp, 60h
0x18000f6c0  pop     rbp
0x18000f6c1  retn
```
