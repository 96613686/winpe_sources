# CiRegisterSiloMonitor

- ea: `0x180073b74`
- end: `0x180073c4c`
- name: `CiRegisterSiloMonitor`
- size: `216`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005ecdc`

## callees

- `0x18002bef0`
- `0x180073b74`

## import_xrefs

- `ntoskrnl!PsUnregisterSiloMonitor` at `0x180073c26`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x180073c26`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x180073bf4`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x180073bf4`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x180073bdd`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x180073bdd`
- `ntoskrnl!PsStartSiloMonitor` at `0x180073c0d`
- `ntoskrnl!PsStartSiloMonitor` at `0x180073c0d`

## string_xrefs

- `0x180073b8f`: `ci.dll`

## pseudocode

```c
__int64 CiRegisterSiloMonitor()
{
  __int64 result; // rax
  int started; // ebx
  _QWORD v2[2]; // [rsp+20h] [rbp-40h] BYREF
  __int16 v3; // [rsp+30h] [rbp-30h] BYREF
  char v4; // [rsp+32h] [rbp-2Eh]
  int v5; // [rsp+33h] [rbp-2Dh]
  char v6; // [rsp+37h] [rbp-29h]
  _QWORD *v7; // [rsp+38h] [rbp-28h]
  __int64 (__fastcall *v8)(__int64); // [rsp+40h] [rbp-20h]
  __int64 v9; // [rsp+48h] [rbp-18h]

  v2[0] = 917516;
  v2[1] = L"ci.dll";
  v5 = 0;
  v7 = v2;
  v6 = 0;
  v8 = CiCreateSiloNotification;
  v9 = 0;
  v3 = 257;
  v4 = 1;
  result = PsRegisterSiloMonitor(&v3, &g_CiSiloMonitor);
  if ( (int)result >= 0 )
  {
    g_CiSiloContextSlot = PsGetSiloMonitorContextSlot(g_CiSiloMonitor);
    started = PsStartSiloMonitor(g_CiSiloMonitor);
    if ( started < 0 )
      PsUnregisterSiloMonitor(g_CiSiloMonitor);
    return (unsigned int)started;
  }
  return result;
}

```

## disassembly

```asm
0x180073b74  mov     [rsp-8+arg_0], rbx
0x180073b79  push    rbp
0x180073b7a  mov     rbp, rsp
0x180073b7d  sub     rsp, 60h
0x180073b81  mov     rax, cs:__security_cookie
0x180073b88  xor     rax, rsp
0x180073b8b  mov     [rbp+var_10], rax
0x180073b8f  lea     rax, aCiDll; "ci.dll"
0x180073b96  mov     [rbp+var_40], 0E000Ch
0x180073b9e  mov     [rbp+var_38], rax
0x180073ba2  lea     rdx, g_CiSiloMonitor
0x180073ba9  lea     rax, [rbp+var_40]
0x180073bad  mov     [rbp+var_2D], 0
0x180073bb4  mov     [rbp+var_28], rax
0x180073bb8  lea     rcx, [rbp+var_30]
0x180073bbc  lea     rax, CiCreateSiloNotification
0x180073bc3  mov     [rbp+var_29], 0
0x180073bc7  mov     [rbp+var_20], rax
0x180073bcb  mov     [rbp+var_18], 0
0x180073bd3  mov     [rbp+var_30], 101h
0x180073bd9  mov     [rbp+var_2E], 1
0x180073bdd  call    cs:__imp_PsRegisterSiloMonitor
0x180073be4  nop     dword ptr [rax+rax+00h]
0x180073be9  test    eax, eax
0x180073beb  js      short loc_180073C34
0x180073bed  mov     rcx, cs:g_CiSiloMonitor
0x180073bf4  call    cs:__imp_PsGetSiloMonitorContextSlot
0x180073bfb  nop     dword ptr [rax+rax+00h]
0x180073c00  mov     rcx, cs:g_CiSiloMonitor
0x180073c07  mov     cs:g_CiSiloContextSlot, eax
0x180073c0d  call    cs:__imp_PsStartSiloMonitor
0x180073c14  nop     dword ptr [rax+rax+00h]
0x180073c19  mov     ebx, eax
0x180073c1b  test    eax, eax
0x180073c1d  jns     short loc_180073C32
0x180073c1f  mov     rcx, cs:g_CiSiloMonitor
0x180073c26  call    cs:__imp_PsUnregisterSiloMonitor
0x180073c2d  nop     dword ptr [rax+rax+00h]
0x180073c32  mov     eax, ebx
0x180073c34  mov     rcx, [rbp+var_10]
0x180073c38  xor     rcx, rsp; StackCookie
0x180073c3b  call    __security_check_cookie
0x180073c40  mov     rbx, [rsp+60h+arg_0]
0x180073c45  add     rsp, 60h
0x180073c49  pop     rbp
0x180073c4a  retn
```
