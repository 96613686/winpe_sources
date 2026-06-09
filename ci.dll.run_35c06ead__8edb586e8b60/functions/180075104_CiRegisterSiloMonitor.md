# CiRegisterSiloMonitor

- ea: `0x180075104`
- end: `0x1800751dc`
- name: `CiRegisterSiloMonitor`
- size: `216`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005f3c8`

## callees

- `0x18002c0d0`
- `0x180075104`

## import_xrefs

- `ntoskrnl!PsUnregisterSiloMonitor` at `0x1800751b6`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x1800751b6`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x180075184`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x180075184`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18007516d`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x18007516d`
- `ntoskrnl!PsStartSiloMonitor` at `0x18007519d`
- `ntoskrnl!PsStartSiloMonitor` at `0x18007519d`

## string_xrefs

- `0x18007511f`: `ci.dll`

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
0x180075104  mov     [rsp-8+arg_0], rbx
0x180075109  push    rbp
0x18007510a  mov     rbp, rsp
0x18007510d  sub     rsp, 60h
0x180075111  mov     rax, cs:__security_cookie
0x180075118  xor     rax, rsp
0x18007511b  mov     [rbp+var_10], rax
0x18007511f  lea     rax, aCiDll; "ci.dll"
0x180075126  mov     [rbp+var_40], 0E000Ch
0x18007512e  mov     [rbp+var_38], rax
0x180075132  lea     rdx, g_CiSiloMonitor
0x180075139  lea     rax, [rbp+var_40]
0x18007513d  mov     [rbp+var_2D], 0
0x180075144  mov     [rbp+var_28], rax
0x180075148  lea     rcx, [rbp+var_30]
0x18007514c  lea     rax, CiCreateSiloNotification
0x180075153  mov     [rbp+var_29], 0
0x180075157  mov     [rbp+var_20], rax
0x18007515b  mov     [rbp+var_18], 0
0x180075163  mov     [rbp+var_30], 101h
0x180075169  mov     [rbp+var_2E], 1
0x18007516d  call    cs:__imp_PsRegisterSiloMonitor
0x180075174  nop     dword ptr [rax+rax+00h]
0x180075179  test    eax, eax
0x18007517b  js      short loc_1800751C4
0x18007517d  mov     rcx, cs:g_CiSiloMonitor
0x180075184  call    cs:__imp_PsGetSiloMonitorContextSlot
0x18007518b  nop     dword ptr [rax+rax+00h]
0x180075190  mov     rcx, cs:g_CiSiloMonitor
0x180075197  mov     cs:g_CiSiloContextSlot, eax
0x18007519d  call    cs:__imp_PsStartSiloMonitor
0x1800751a4  nop     dword ptr [rax+rax+00h]
0x1800751a9  mov     ebx, eax
0x1800751ab  test    eax, eax
0x1800751ad  jns     short loc_1800751C2
0x1800751af  mov     rcx, cs:g_CiSiloMonitor
0x1800751b6  call    cs:__imp_PsUnregisterSiloMonitor
0x1800751bd  nop     dword ptr [rax+rax+00h]
0x1800751c2  mov     eax, ebx
0x1800751c4  mov     rcx, [rbp+var_10]
0x1800751c8  xor     rcx, rsp; StackCookie
0x1800751cb  call    __security_check_cookie
0x1800751d0  mov     rbx, [rsp+60h+arg_0]
0x1800751d5  add     rsp, 60h
0x1800751d9  pop     rbp
0x1800751da  retn
```
