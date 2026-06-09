# __security_init_cookie

- ea: `0x180001654`
- end: `0x180001731`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012d0`

## callees

- `0x180001654`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800016de`
- `KERNEL32!QueryPerformanceCounter` at `0x1800016de`
- `KERNEL32!GetCurrentProcessId` at `0x18000169b`
- `KERNEL32!GetCurrentProcessId` at `0x18000169b`
- `KERNEL32!GetCurrentThreadId` at `0x1800016a7`
- `KERNEL32!GetCurrentThreadId` at `0x1800016a7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000168d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000168d`
- `KERNEL32!GetTickCount` at `0x1800016b3`
- `KERNEL32!GetTickCount` at `0x1800016c3`
- `KERNEL32!GetTickCount` at `0x1800016b3`
- `KERNEL32!GetTickCount` at `0x1800016c3`

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
0x180001654  mov     [rsp-8+arg_18], rbx
0x180001659  push    rbp
0x18000165a  mov     rbp, rsp
0x18000165d  sub     rsp, 20h
0x180001661  xor     eax, eax
0x180001663  mov     rbx, 2B992DDFA232h
0x18000166d  mov     [rbp+arg_0], rax
0x180001671  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001675  mov     qword ptr [rbp+PerformanceCount], rax
0x180001679  mov     rax, cs:__security_cookie
0x180001680  cmp     rax, rbx
0x180001683  jnz     loc_18000171C
0x180001689  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000168d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001693  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001697  mov     [rbp+arg_0], rax
0x18000169b  call    cs:__imp_GetCurrentProcessId
0x1800016a1  mov     eax, eax
0x1800016a3  xor     [rbp+arg_0], rax
0x1800016a7  call    cs:__imp_GetCurrentThreadId
0x1800016ad  mov     eax, eax
0x1800016af  xor     [rbp+arg_0], rax
0x1800016b3  call    cs:__imp_GetTickCount
0x1800016b9  mov     eax, eax
0x1800016bb  shl     rax, 18h
0x1800016bf  xor     [rbp+arg_0], rax
0x1800016c3  call    cs:__imp_GetTickCount
0x1800016c9  mov     eax, eax
0x1800016cb  lea     rcx, [rbp+arg_0]
0x1800016cf  xor     rax, [rbp+arg_0]
0x1800016d3  xor     rax, rcx
0x1800016d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800016da  mov     [rbp+arg_0], rax
0x1800016de  call    cs:__imp_QueryPerformanceCounter
0x1800016e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800016e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800016f1  shl     rax, 20h
0x1800016f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800016f9  xor     rax, [rbp+arg_0]
0x1800016fd  and     rax, rcx
0x180001700  mov     rcx, rax
0x180001703  cmp     rax, rbx
0x180001706  jnz     short loc_180001715
0x180001708  mov     rax, 2B992DDFA233h
0x180001712  mov     rcx, rax
0x180001715  mov     cs:__security_cookie, rcx
0x18000171c  mov     rbx, [rsp+20h+arg_18]
0x180001721  not     rax
0x180001724  mov     cs:__security_cookie_complement, rax
0x18000172b  add     rsp, 20h
0x18000172f  pop     rbp
0x180001730  retn
```
