# __security_init_cookie

- ea: `0x180002650`
- end: `0x18000272d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e30`

## callees

- `0x180002650`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002697`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002689`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002689`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026da`

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
0x180002650  mov     [rsp-8+arg_18], rbx
0x180002655  push    rbp
0x180002656  mov     rbp, rsp
0x180002659  sub     rsp, 20h
0x18000265d  xor     eax, eax
0x18000265f  mov     rbx, 2B992DDFA232h
0x180002669  mov     [rbp+arg_0], rax
0x18000266d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002671  mov     qword ptr [rbp+PerformanceCount], rax
0x180002675  mov     rax, cs:__security_cookie
0x18000267c  cmp     rax, rbx
0x18000267f  jnz     loc_180002718
0x180002685  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002689  call    cs:__imp_GetSystemTimeAsFileTime
0x18000268f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002693  mov     [rbp+arg_0], rax
0x180002697  call    cs:__imp_GetCurrentProcessId
0x18000269d  mov     eax, eax
0x18000269f  xor     [rbp+arg_0], rax
0x1800026a3  call    cs:__imp_GetCurrentThreadId
0x1800026a9  mov     eax, eax
0x1800026ab  xor     [rbp+arg_0], rax
0x1800026af  call    cs:__imp_GetTickCount
0x1800026b5  mov     eax, eax
0x1800026b7  shl     rax, 18h
0x1800026bb  xor     [rbp+arg_0], rax
0x1800026bf  call    cs:__imp_GetTickCount
0x1800026c5  mov     eax, eax
0x1800026c7  lea     rcx, [rbp+arg_0]
0x1800026cb  xor     rax, [rbp+arg_0]
0x1800026cf  xor     rax, rcx
0x1800026d2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800026d6  mov     [rbp+arg_0], rax
0x1800026da  call    cs:__imp_QueryPerformanceCounter
0x1800026e0  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026e3  mov     rcx, 0FFFFFFFFFFFFh
0x1800026ed  shl     rax, 20h
0x1800026f1  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026f5  xor     rax, [rbp+arg_0]
0x1800026f9  and     rax, rcx
0x1800026fc  mov     rcx, rax
0x1800026ff  cmp     rax, rbx
0x180002702  jnz     short loc_180002711
0x180002704  mov     rax, 2B992DDFA233h
0x18000270e  mov     rcx, rax
0x180002711  mov     cs:__security_cookie, rcx
0x180002718  mov     rbx, [rsp+20h+arg_18]
0x18000271d  not     rax
0x180002720  mov     cs:__security_cookie_complement, rax
0x180002727  add     rsp, 20h
0x18000272b  pop     rbp
0x18000272c  retn
```
