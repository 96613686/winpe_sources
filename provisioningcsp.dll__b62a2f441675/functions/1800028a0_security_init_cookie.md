# __security_init_cookie

- ea: `0x1800028a0`
- end: `0x18000297d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002520`

## callees

- `0x1800028a0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000292a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000292a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800028e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800028e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000290f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000290f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800028d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800028d9`

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
0x1800028a0  mov     [rsp-8+arg_18], rbx
0x1800028a5  push    rbp
0x1800028a6  mov     rbp, rsp
0x1800028a9  sub     rsp, 20h
0x1800028ad  xor     eax, eax
0x1800028af  mov     rbx, 2B992DDFA232h
0x1800028b9  mov     [rbp+arg_0], rax
0x1800028bd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800028c1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800028c5  mov     rax, cs:__security_cookie
0x1800028cc  cmp     rax, rbx
0x1800028cf  jnz     loc_180002968
0x1800028d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800028d9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800028df  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800028e3  mov     [rbp+arg_0], rax
0x1800028e7  call    cs:__imp_GetCurrentProcessId
0x1800028ed  mov     eax, eax
0x1800028ef  xor     [rbp+arg_0], rax
0x1800028f3  call    cs:__imp_GetCurrentThreadId
0x1800028f9  mov     eax, eax
0x1800028fb  xor     [rbp+arg_0], rax
0x1800028ff  call    cs:__imp_GetTickCount
0x180002905  mov     eax, eax
0x180002907  shl     rax, 18h
0x18000290b  xor     [rbp+arg_0], rax
0x18000290f  call    cs:__imp_GetTickCount
0x180002915  mov     eax, eax
0x180002917  lea     rcx, [rbp+arg_0]
0x18000291b  xor     rax, [rbp+arg_0]
0x18000291f  xor     rax, rcx
0x180002922  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002926  mov     [rbp+arg_0], rax
0x18000292a  call    cs:__imp_QueryPerformanceCounter
0x180002930  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002933  mov     rcx, 0FFFFFFFFFFFFh
0x18000293d  shl     rax, 20h
0x180002941  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002945  xor     rax, [rbp+arg_0]
0x180002949  and     rax, rcx
0x18000294c  mov     rcx, rax
0x18000294f  cmp     rax, rbx
0x180002952  jnz     short loc_180002961
0x180002954  mov     rax, 2B992DDFA233h
0x18000295e  mov     rcx, rax
0x180002961  mov     cs:__security_cookie, rcx
0x180002968  mov     rbx, [rsp+20h+arg_18]
0x18000296d  not     rax
0x180002970  mov     cs:__security_cookie_complement, rax
0x180002977  add     rsp, 20h
0x18000297b  pop     rbp
0x18000297c  retn
```
