# __security_init_cookie

- ea: `0x18000267c`
- end: `0x180002759`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002320`

## callees

- `0x18000267c`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180002706`
- `KERNEL32!QueryPerformanceCounter` at `0x180002706`
- `KERNEL32!GetCurrentProcessId` at `0x1800026c3`
- `KERNEL32!GetCurrentProcessId` at `0x1800026c3`
- `KERNEL32!GetCurrentThreadId` at `0x1800026cf`
- `KERNEL32!GetCurrentThreadId` at `0x1800026cf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800026b5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800026b5`
- `KERNEL32!GetTickCount` at `0x1800026db`
- `KERNEL32!GetTickCount` at `0x1800026eb`
- `KERNEL32!GetTickCount` at `0x1800026db`
- `KERNEL32!GetTickCount` at `0x1800026eb`

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
0x18000267c  mov     [rsp-8+arg_18], rbx
0x180002681  push    rbp
0x180002682  mov     rbp, rsp
0x180002685  sub     rsp, 20h
0x180002689  xor     eax, eax
0x18000268b  mov     rbx, 2B992DDFA232h
0x180002695  mov     [rbp+arg_0], rax
0x180002699  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000269d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800026a1  mov     rax, cs:__security_cookie
0x1800026a8  cmp     rax, rbx
0x1800026ab  jnz     loc_180002744
0x1800026b1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800026b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800026bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800026bf  mov     [rbp+arg_0], rax
0x1800026c3  call    cs:__imp_GetCurrentProcessId
0x1800026c9  mov     eax, eax
0x1800026cb  xor     [rbp+arg_0], rax
0x1800026cf  call    cs:__imp_GetCurrentThreadId
0x1800026d5  mov     eax, eax
0x1800026d7  xor     [rbp+arg_0], rax
0x1800026db  call    cs:__imp_GetTickCount
0x1800026e1  mov     eax, eax
0x1800026e3  shl     rax, 18h
0x1800026e7  xor     [rbp+arg_0], rax
0x1800026eb  call    cs:__imp_GetTickCount
0x1800026f1  mov     eax, eax
0x1800026f3  lea     rcx, [rbp+arg_0]
0x1800026f7  xor     rax, [rbp+arg_0]
0x1800026fb  xor     rax, rcx
0x1800026fe  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002702  mov     [rbp+arg_0], rax
0x180002706  call    cs:__imp_QueryPerformanceCounter
0x18000270c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000270f  mov     rcx, 0FFFFFFFFFFFFh
0x180002719  shl     rax, 20h
0x18000271d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002721  xor     rax, [rbp+arg_0]
0x180002725  and     rax, rcx
0x180002728  mov     rcx, rax
0x18000272b  cmp     rax, rbx
0x18000272e  jnz     short loc_18000273D
0x180002730  mov     rax, 2B992DDFA233h
0x18000273a  mov     rcx, rax
0x18000273d  mov     cs:__security_cookie, rcx
0x180002744  mov     rbx, [rsp+20h+arg_18]
0x180002749  not     rax
0x18000274c  mov     cs:__security_cookie_complement, rax
0x180002753  add     rsp, 20h
0x180002757  pop     rbp
0x180002758  retn
```
