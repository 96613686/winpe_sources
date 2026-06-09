# __security_init_cookie

- ea: `0x18000202c`
- end: `0x1800020e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b90`

## callees

- `0x18000202c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000207b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000207b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000206f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000206f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000208b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000208b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002061`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002061`

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
0x18000202c  mov     [rsp-8+arg_10], rbx
0x180002031  push    rbp
0x180002032  mov     rbp, rsp
0x180002035  sub     rsp, 30h
0x180002039  mov     rax, cs:__security_cookie
0x180002040  mov     rbx, 2B992DDFA232h
0x18000204a  cmp     rax, rbx
0x18000204d  jnz     short loc_1800020CC
0x18000204f  xor     eax, eax
0x180002051  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002055  mov     [rbp+var_10], rax
0x180002059  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000205d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002061  call    cs:__imp_GetSystemTimeAsFileTime
0x180002067  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000206b  mov     [rbp+var_10], rax
0x18000206f  call    cs:__imp_GetCurrentThreadId
0x180002075  mov     eax, eax
0x180002077  xor     [rbp+var_10], rax
0x18000207b  call    cs:__imp_GetCurrentProcessId
0x180002081  mov     eax, eax
0x180002083  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002087  xor     [rbp+var_10], rax
0x18000208b  call    cs:__imp_QueryPerformanceCounter
0x180002091  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002094  lea     rcx, [rbp+var_10]
0x180002098  shl     rax, 20h
0x18000209c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800020a0  xor     rax, [rbp+var_10]
0x1800020a4  xor     rax, rcx
0x1800020a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800020b1  and     rax, rcx
0x1800020b4  mov     rcx, 2B992DDFA233h
0x1800020be  cmp     rax, rbx
0x1800020c1  cmovz   rax, rcx
0x1800020c5  mov     cs:__security_cookie, rax
0x1800020cc  mov     rbx, [rsp+30h+arg_10]
0x1800020d1  not     rax
0x1800020d4  mov     cs:__security_cookie_complement, rax
0x1800020db  add     rsp, 30h
0x1800020df  pop     rbp
0x1800020e0  retn
```
