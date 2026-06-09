# __security_init_cookie

- ea: `0x1400024f0`
- end: `0x1400025a5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001f70`

## callees

- `0x1400024f0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000253f`
- `KERNEL32!GetCurrentProcessId` at `0x14000253f`
- `KERNEL32!GetCurrentThreadId` at `0x140002533`
- `KERNEL32!GetCurrentThreadId` at `0x140002533`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000254f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000254f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002525`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002525`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1400024f0  mov     [rsp-8+arg_10], rbx
0x1400024f5  push    rbp
0x1400024f6  mov     rbp, rsp
0x1400024f9  sub     rsp, 30h
0x1400024fd  mov     rax, cs:__security_cookie
0x140002504  mov     rbx, 2B992DDFA232h
0x14000250e  cmp     rax, rbx
0x140002511  jnz     short loc_140002590
0x140002513  xor     eax, eax
0x140002515  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002519  mov     [rbp+var_10], rax
0x14000251d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002521  mov     qword ptr [rbp+PerformanceCount], rax
0x140002525  call    cs:__imp_GetSystemTimeAsFileTime
0x14000252b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000252f  mov     [rbp+var_10], rax
0x140002533  call    cs:__imp_GetCurrentThreadId
0x140002539  mov     eax, eax
0x14000253b  xor     [rbp+var_10], rax
0x14000253f  call    cs:__imp_GetCurrentProcessId
0x140002545  mov     eax, eax
0x140002547  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000254b  xor     [rbp+var_10], rax
0x14000254f  call    cs:__imp_QueryPerformanceCounter
0x140002555  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002558  lea     rcx, [rbp+var_10]
0x14000255c  shl     rax, 20h
0x140002560  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002564  xor     rax, [rbp+var_10]
0x140002568  xor     rax, rcx
0x14000256b  mov     rcx, 0FFFFFFFFFFFFh
0x140002575  and     rax, rcx
0x140002578  mov     rcx, 2B992DDFA233h
0x140002582  cmp     rax, rbx
0x140002585  cmovz   rax, rcx
0x140002589  mov     cs:__security_cookie, rax
0x140002590  mov     rbx, [rsp+30h+arg_10]
0x140002595  not     rax
0x140002598  mov     cs:__security_cookie_complement, rax
0x14000259f  add     rsp, 30h
0x1400025a3  pop     rbp
0x1400025a4  retn
```
