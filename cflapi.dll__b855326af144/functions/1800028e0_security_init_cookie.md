# __security_init_cookie

- ea: `0x1800028e0`
- end: `0x180002995`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x1800028e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000292f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000292f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002923`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000293f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000293f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002915`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002915`

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
0x1800028e0  mov     [rsp-8+arg_10], rbx
0x1800028e5  push    rbp
0x1800028e6  mov     rbp, rsp
0x1800028e9  sub     rsp, 30h
0x1800028ed  mov     rax, cs:__security_cookie
0x1800028f4  mov     rbx, 2B992DDFA232h
0x1800028fe  cmp     rax, rbx
0x180002901  jnz     short loc_180002980
0x180002903  xor     eax, eax
0x180002905  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002909  mov     [rbp+var_10], rax
0x18000290d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002911  mov     qword ptr [rbp+PerformanceCount], rax
0x180002915  call    cs:__imp_GetSystemTimeAsFileTime
0x18000291b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000291f  mov     [rbp+var_10], rax
0x180002923  call    cs:__imp_GetCurrentThreadId
0x180002929  mov     eax, eax
0x18000292b  xor     [rbp+var_10], rax
0x18000292f  call    cs:__imp_GetCurrentProcessId
0x180002935  mov     eax, eax
0x180002937  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000293b  xor     [rbp+var_10], rax
0x18000293f  call    cs:__imp_QueryPerformanceCounter
0x180002945  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002948  lea     rcx, [rbp+var_10]
0x18000294c  shl     rax, 20h
0x180002950  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002954  xor     rax, [rbp+var_10]
0x180002958  xor     rax, rcx
0x18000295b  mov     rcx, 0FFFFFFFFFFFFh
0x180002965  and     rax, rcx
0x180002968  mov     rcx, 2B992DDFA233h
0x180002972  cmp     rax, rbx
0x180002975  cmovz   rax, rcx
0x180002979  mov     cs:__security_cookie, rax
0x180002980  mov     rbx, [rsp+30h+arg_10]
0x180002985  not     rax
0x180002988  mov     cs:__security_cookie_complement, rax
0x18000298f  add     rsp, 30h
0x180002993  pop     rbp
0x180002994  retn
```
