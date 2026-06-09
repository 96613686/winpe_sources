# __security_init_cookie

- ea: `0x180001674`
- end: `0x18000174d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012e0`

## callees

- `0x180001674`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016fa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800016a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800016a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016df`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180001674  mov     [rsp-8+arg_18], rbx
0x180001679  push    rbp
0x18000167a  mov     rbp, rsp
0x18000167d  sub     rsp, 20h
0x180001681  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001686  mov     rbx, 2B992DDFA232h
0x180001690  and     qword ptr [rbp+PerformanceCount], 0
0x180001695  mov     rax, cs:__security_cookie
0x18000169c  cmp     rax, rbx
0x18000169f  jnz     loc_180001738
0x1800016a5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800016a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800016af  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800016b3  mov     [rbp+arg_0], rax
0x1800016b7  call    cs:__imp_GetCurrentProcessId
0x1800016bd  mov     eax, eax
0x1800016bf  xor     [rbp+arg_0], rax
0x1800016c3  call    cs:__imp_GetCurrentThreadId
0x1800016c9  mov     eax, eax
0x1800016cb  xor     [rbp+arg_0], rax
0x1800016cf  call    cs:__imp_GetTickCount
0x1800016d5  mov     eax, eax
0x1800016d7  shl     rax, 18h
0x1800016db  xor     [rbp+arg_0], rax
0x1800016df  call    cs:__imp_GetTickCount
0x1800016e5  mov     eax, eax
0x1800016e7  lea     rcx, [rbp+arg_0]
0x1800016eb  xor     rax, [rbp+arg_0]
0x1800016ef  xor     rax, rcx
0x1800016f2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800016f6  mov     [rbp+arg_0], rax
0x1800016fa  call    cs:__imp_QueryPerformanceCounter
0x180001700  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001703  mov     rcx, 0FFFFFFFFFFFFh
0x18000170d  shl     rax, 20h
0x180001711  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001715  xor     rax, [rbp+arg_0]
0x180001719  and     rax, rcx
0x18000171c  mov     rcx, rax
0x18000171f  cmp     rax, rbx
0x180001722  jnz     short loc_180001731
0x180001724  mov     rax, 2B992DDFA233h
0x18000172e  mov     rcx, rax
0x180001731  mov     cs:__security_cookie, rcx
0x180001738  mov     rbx, [rsp+20h+arg_18]
0x18000173d  not     rax
0x180001740  mov     cs:__security_cookie_complement, rax
0x180001747  add     rsp, 20h
0x18000174b  pop     rbp
0x18000174c  retn
```
