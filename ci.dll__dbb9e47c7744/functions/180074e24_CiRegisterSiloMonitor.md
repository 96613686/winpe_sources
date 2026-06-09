# CiRegisterSiloMonitor

- ea: `0x180074e24`
- end: `0x180074efc`
- name: `CiRegisterSiloMonitor`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005f428`

## callees

- `0x18002bf20`
- `0x180074e24`

## import_xrefs

- `ntoskrnl!PsUnregisterSiloMonitor` at `0x180074ed6`
- `ntoskrnl!PsUnregisterSiloMonitor` at `0x180074ed6`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x180074ea4`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x180074ea4`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x180074e8d`
- `ntoskrnl!PsRegisterSiloMonitor` at `0x180074e8d`
- `ntoskrnl!PsStartSiloMonitor` at `0x180074ebd`
- `ntoskrnl!PsStartSiloMonitor` at `0x180074ebd`

## string_xrefs

- `0x180074e3f`: `ci.dll`

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
0x180074e24  mov     [rsp-8+arg_0], rbx
0x180074e29  push    rbp
0x180074e2a  mov     rbp, rsp
0x180074e2d  sub     rsp, 60h
0x180074e31  mov     rax, cs:__security_cookie
0x180074e38  xor     rax, rsp
0x180074e3b  mov     [rbp+var_10], rax
0x180074e3f  lea     rax, aCiDll; "ci.dll"
0x180074e46  mov     [rbp+var_40], 0E000Ch
0x180074e4e  mov     [rbp+var_38], rax
0x180074e52  lea     rdx, g_CiSiloMonitor
0x180074e59  lea     rax, [rbp+var_40]
0x180074e5d  mov     [rbp+var_2D], 0
0x180074e64  mov     [rbp+var_28], rax
0x180074e68  lea     rcx, [rbp+var_30]
0x180074e6c  lea     rax, CiCreateSiloNotification
0x180074e73  mov     [rbp+var_29], 0
0x180074e77  mov     [rbp+var_20], rax
0x180074e7b  mov     [rbp+var_18], 0
0x180074e83  mov     [rbp+var_30], 101h
0x180074e89  mov     [rbp+var_2E], 1
0x180074e8d  call    cs:__imp_PsRegisterSiloMonitor
0x180074e94  nop     dword ptr [rax+rax+00h]
0x180074e99  test    eax, eax
0x180074e9b  js      short loc_180074EE4
0x180074e9d  mov     rcx, cs:g_CiSiloMonitor
0x180074ea4  call    cs:__imp_PsGetSiloMonitorContextSlot
0x180074eab  nop     dword ptr [rax+rax+00h]
0x180074eb0  mov     rcx, cs:g_CiSiloMonitor
0x180074eb7  mov     cs:g_CiSiloContextSlot, eax
0x180074ebd  call    cs:__imp_PsStartSiloMonitor
0x180074ec4  nop     dword ptr [rax+rax+00h]
0x180074ec9  mov     ebx, eax
0x180074ecb  test    eax, eax
0x180074ecd  jns     short loc_180074EE2
0x180074ecf  mov     rcx, cs:g_CiSiloMonitor
0x180074ed6  call    cs:__imp_PsUnregisterSiloMonitor
0x180074edd  nop     dword ptr [rax+rax+00h]
0x180074ee2  mov     eax, ebx
0x180074ee4  mov     rcx, [rbp+var_10]
0x180074ee8  xor     rcx, rsp; StackCookie
0x180074eeb  call    __security_check_cookie
0x180074ef0  mov     rbx, [rsp+60h+arg_0]
0x180074ef5  add     rsp, 60h
0x180074ef9  pop     rbp
0x180074efa  retn
```
