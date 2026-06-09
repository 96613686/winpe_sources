# __security_init_cookie

- ea: `0x1800092b0`
- end: `0x180009365`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009220`

## callees

- `0x1800092b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800092ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800092ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800092e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800092e5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000930f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000930f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1800092b0  mov     [rsp-8+arg_10], rbx
0x1800092b5  push    rbp
0x1800092b6  mov     rbp, rsp
0x1800092b9  sub     rsp, 30h
0x1800092bd  mov     rax, cs:__security_cookie
0x1800092c4  mov     rbx, 2B992DDFA232h
0x1800092ce  cmp     rax, rbx
0x1800092d1  jnz     short loc_180009350
0x1800092d3  xor     eax, eax
0x1800092d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800092d9  mov     [rbp+var_10], rax
0x1800092dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800092e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800092e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800092eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800092ef  mov     [rbp+var_10], rax
0x1800092f3  call    cs:__imp_GetCurrentThreadId
0x1800092f9  mov     eax, eax
0x1800092fb  xor     [rbp+var_10], rax
0x1800092ff  call    cs:__imp_GetCurrentProcessId
0x180009305  mov     eax, eax
0x180009307  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000930b  xor     [rbp+var_10], rax
0x18000930f  call    cs:__imp_QueryPerformanceCounter
0x180009315  mov     eax, dword ptr [rbp+PerformanceCount]
0x180009318  lea     rcx, [rbp+var_10]
0x18000931c  shl     rax, 20h
0x180009320  xor     rax, qword ptr [rbp+PerformanceCount]
0x180009324  xor     rax, [rbp+var_10]
0x180009328  xor     rax, rcx
0x18000932b  mov     rcx, 0FFFFFFFFFFFFh
0x180009335  and     rax, rcx
0x180009338  mov     rcx, 2B992DDFA233h
0x180009342  cmp     rax, rbx
0x180009345  cmovz   rax, rcx
0x180009349  mov     cs:__security_cookie, rax
0x180009350  mov     rbx, [rsp+30h+arg_10]
0x180009355  not     rax
0x180009358  mov     cs:__security_cookie_complement, rax
0x18000935f  add     rsp, 30h
0x180009363  pop     rbp
0x180009364  retn
```
