# __security_init_cookie

- ea: `0x1400018d4`
- end: `0x1400019b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001680`

## callees

- `0x1400018d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000191b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000191b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000195e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000195e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001933`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001943`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001933`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001943`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000190d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000190d`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1400018d4  mov     [rsp-8+arg_18], rbx
0x1400018d9  push    rbp
0x1400018da  mov     rbp, rsp
0x1400018dd  sub     rsp, 20h
0x1400018e1  xor     eax, eax
0x1400018e3  mov     rbx, 2B992DDFA232h
0x1400018ed  mov     [rbp+arg_0], rax
0x1400018f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400018f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400018f9  mov     rax, cs:__security_cookie
0x140001900  cmp     rax, rbx
0x140001903  jnz     loc_14000199C
0x140001909  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000190d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001913  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001917  mov     [rbp+arg_0], rax
0x14000191b  call    cs:__imp_GetCurrentProcessId
0x140001921  mov     eax, eax
0x140001923  xor     [rbp+arg_0], rax
0x140001927  call    cs:__imp_GetCurrentThreadId
0x14000192d  mov     eax, eax
0x14000192f  xor     [rbp+arg_0], rax
0x140001933  call    cs:__imp_GetTickCount
0x140001939  mov     eax, eax
0x14000193b  shl     rax, 18h
0x14000193f  xor     [rbp+arg_0], rax
0x140001943  call    cs:__imp_GetTickCount
0x140001949  mov     eax, eax
0x14000194b  lea     rcx, [rbp+arg_0]
0x14000194f  xor     rax, [rbp+arg_0]
0x140001953  xor     rax, rcx
0x140001956  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000195a  mov     [rbp+arg_0], rax
0x14000195e  call    cs:__imp_QueryPerformanceCounter
0x140001964  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001967  mov     rcx, 0FFFFFFFFFFFFh
0x140001971  shl     rax, 20h
0x140001975  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001979  xor     rax, [rbp+arg_0]
0x14000197d  and     rax, rcx
0x140001980  mov     rcx, rax
0x140001983  cmp     rax, rbx
0x140001986  jnz     short loc_140001995
0x140001988  mov     rax, 2B992DDFA233h
0x140001992  mov     rcx, rax
0x140001995  mov     cs:__security_cookie, rcx
0x14000199c  mov     rbx, [rsp+20h+arg_18]
0x1400019a1  not     rax
0x1400019a4  mov     cs:__security_cookie_complement, rax
0x1400019ab  add     rsp, 20h
0x1400019af  pop     rbp
0x1400019b0  retn
```
