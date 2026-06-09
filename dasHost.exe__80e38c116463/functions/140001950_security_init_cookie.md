# __security_init_cookie

- ea: `0x140001950`
- end: `0x140001a05`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001540`

## callees

- `0x140001950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000199f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000199f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400019af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400019af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001985`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001985`

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
0x140001950  mov     [rsp-8+arg_10], rbx
0x140001955  push    rbp
0x140001956  mov     rbp, rsp
0x140001959  sub     rsp, 30h
0x14000195d  mov     rax, cs:__security_cookie
0x140001964  mov     rbx, 2B992DDFA232h
0x14000196e  cmp     rax, rbx
0x140001971  jnz     short loc_1400019F0
0x140001973  xor     eax, eax
0x140001975  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001979  mov     [rbp+var_10], rax
0x14000197d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001981  mov     qword ptr [rbp+PerformanceCount], rax
0x140001985  call    cs:__imp_GetSystemTimeAsFileTime
0x14000198b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000198f  mov     [rbp+var_10], rax
0x140001993  call    cs:__imp_GetCurrentThreadId
0x140001999  mov     eax, eax
0x14000199b  xor     [rbp+var_10], rax
0x14000199f  call    cs:__imp_GetCurrentProcessId
0x1400019a5  mov     eax, eax
0x1400019a7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400019ab  xor     [rbp+var_10], rax
0x1400019af  call    cs:__imp_QueryPerformanceCounter
0x1400019b5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400019b8  lea     rcx, [rbp+var_10]
0x1400019bc  shl     rax, 20h
0x1400019c0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400019c4  xor     rax, [rbp+var_10]
0x1400019c8  xor     rax, rcx
0x1400019cb  mov     rcx, 0FFFFFFFFFFFFh
0x1400019d5  and     rax, rcx
0x1400019d8  mov     rcx, 2B992DDFA233h
0x1400019e2  cmp     rax, rbx
0x1400019e5  cmovz   rax, rcx
0x1400019e9  mov     cs:__security_cookie, rax
0x1400019f0  mov     rbx, [rsp+30h+arg_10]
0x1400019f5  not     rax
0x1400019f8  mov     cs:__security_cookie_complement, rax
0x1400019ff  add     rsp, 30h
0x140001a03  pop     rbp
0x140001a04  retn
```
