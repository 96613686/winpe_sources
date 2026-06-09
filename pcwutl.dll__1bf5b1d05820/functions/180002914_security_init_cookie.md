# __security_init_cookie

- ea: `0x180002914`
- end: `0x1800029f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800020f0`

## callees

- `0x180002914`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002973`
- `KERNEL32!GetTickCount` at `0x180002983`
- `KERNEL32!GetTickCount` at `0x180002973`
- `KERNEL32!GetTickCount` at `0x180002983`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000294d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000294d`
- `KERNEL32!QueryPerformanceCounter` at `0x18000299e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000299e`
- `KERNEL32!GetCurrentProcessId` at `0x18000295b`
- `KERNEL32!GetCurrentProcessId` at `0x18000295b`
- `KERNEL32!GetCurrentThreadId` at `0x180002967`
- `KERNEL32!GetCurrentThreadId` at `0x180002967`

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
0x180002914  mov     [rsp-8+arg_18], rbx
0x180002919  push    rbp
0x18000291a  mov     rbp, rsp
0x18000291d  sub     rsp, 20h
0x180002921  xor     eax, eax
0x180002923  mov     rbx, 2B992DDFA232h
0x18000292d  mov     [rbp+arg_0], rax
0x180002931  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002935  mov     qword ptr [rbp+PerformanceCount], rax
0x180002939  mov     rax, cs:__security_cookie
0x180002940  cmp     rax, rbx
0x180002943  jnz     loc_1800029DC
0x180002949  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000294d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002953  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002957  mov     [rbp+arg_0], rax
0x18000295b  call    cs:__imp_GetCurrentProcessId
0x180002961  mov     eax, eax
0x180002963  xor     [rbp+arg_0], rax
0x180002967  call    cs:__imp_GetCurrentThreadId
0x18000296d  mov     eax, eax
0x18000296f  xor     [rbp+arg_0], rax
0x180002973  call    cs:__imp_GetTickCount
0x180002979  mov     eax, eax
0x18000297b  shl     rax, 18h
0x18000297f  xor     [rbp+arg_0], rax
0x180002983  call    cs:__imp_GetTickCount
0x180002989  mov     eax, eax
0x18000298b  lea     rcx, [rbp+arg_0]
0x18000298f  xor     rax, [rbp+arg_0]
0x180002993  xor     rax, rcx
0x180002996  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000299a  mov     [rbp+arg_0], rax
0x18000299e  call    cs:__imp_QueryPerformanceCounter
0x1800029a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800029a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800029b1  shl     rax, 20h
0x1800029b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800029b9  xor     rax, [rbp+arg_0]
0x1800029bd  and     rax, rcx
0x1800029c0  mov     rcx, rax
0x1800029c3  cmp     rax, rbx
0x1800029c6  jnz     short loc_1800029D5
0x1800029c8  mov     rax, 2B992DDFA233h
0x1800029d2  mov     rcx, rax
0x1800029d5  mov     cs:__security_cookie, rcx
0x1800029dc  mov     rbx, [rsp+20h+arg_18]
0x1800029e1  not     rax
0x1800029e4  mov     cs:__security_cookie_complement, rax
0x1800029eb  add     rsp, 20h
0x1800029ef  pop     rbp
0x1800029f0  retn
```
