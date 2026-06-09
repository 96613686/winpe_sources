# SetPostSleepMainThreadInfo

- ea: `0x18002f2ec`
- end: `0x18002f389`
- name: `SetPostSleepMainThreadInfo`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cb0c`

## callees

- `0x180019ad0`
- `0x18002f390`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18002f329`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18002f329`

## pseudocode

```c
__int64 __fastcall SetPostSleepMainThreadInfo(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rdi
  _OWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF

  v3 = g_pDhcpv6MainThreadTraceArray;
  memset(v7, 0, 28);
  GetSystemTimePreciseAsFileTime(v7);
  DWORD2(v7[0]) = 1;
  DWORD2(v7[1]) = a3;
  DWORD1(v7[1]) = (*(_QWORD *)&v7[0] - a2) / 0x2710uLL;
  return TraceMainThreadInfo(v7, v3);
}

```

## disassembly

```asm
0x18002f2ec  mov     [rsp+arg_0], rbx
0x18002f2f1  mov     [rsp+arg_10], rsi
0x18002f2f6  push    rdi
0x18002f2f7  sub     rsp, 50h
0x18002f2fb  mov     rax, cs:__security_cookie
0x18002f302  xor     rax, rsp
0x18002f305  mov     [rsp+58h+var_18], rax
0x18002f30a  mov     rdi, cs:g_pDhcpv6MainThreadTraceArray
0x18002f311  lea     rcx, [rsp+58h+var_38]
0x18002f316  xorps   xmm0, xmm0
0x18002f319  mov     esi, r8d
0x18002f31c  movups  [rsp+58h+var_38], xmm0
0x18002f321  mov     rbx, rdx
0x18002f324  movups  [rsp+58h+var_38+0Ch], xmm0
0x18002f329  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18002f330  nop     dword ptr [rax+rax+00h]
0x18002f335  mov     rcx, qword ptr [rsp+58h+var_38]
0x18002f33a  mov     rax, 346DC5D63886594Bh
0x18002f344  sub     rcx, rbx
0x18002f347  mov     dword ptr [rsp+58h+var_38+8], 1
0x18002f34f  mul     rcx
0x18002f352  lea     rcx, [rsp+58h+var_38]
0x18002f357  mov     [rsp+58h+var_20], esi
0x18002f35b  shr     rdx, 0Bh
0x18002f35f  mov     [rsp+58h+var_24], edx
0x18002f363  mov     rdx, rdi
0x18002f366  call    TraceMainThreadInfo
0x18002f36b  mov     rcx, [rsp+58h+var_18]
0x18002f370  xor     rcx, rsp; StackCookie
0x18002f373  call    __security_check_cookie
0x18002f378  mov     rbx, [rsp+58h+arg_0]
0x18002f37d  mov     rsi, [rsp+58h+arg_10]
0x18002f382  add     rsp, 50h
0x18002f386  pop     rdi
0x18002f387  retn
```
