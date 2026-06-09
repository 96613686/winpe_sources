# __security_init_cookie

- ea: `0x180002934`
- end: `0x180002a11`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002460`

## callees

- `0x180002934`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000297b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000297b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002987`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002987`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800029be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800029be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000296d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000296d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002993`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002993`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800029a3`

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
0x180002934  mov     [rsp-8+arg_18], rbx
0x180002939  push    rbp
0x18000293a  mov     rbp, rsp
0x18000293d  sub     rsp, 20h
0x180002941  xor     eax, eax
0x180002943  mov     rbx, 2B992DDFA232h
0x18000294d  mov     [rbp+arg_0], rax
0x180002951  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002955  mov     qword ptr [rbp+PerformanceCount], rax
0x180002959  mov     rax, cs:__security_cookie
0x180002960  cmp     rax, rbx
0x180002963  jnz     loc_1800029FC
0x180002969  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000296d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002973  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002977  mov     [rbp+arg_0], rax
0x18000297b  call    cs:__imp_GetCurrentProcessId
0x180002981  mov     eax, eax
0x180002983  xor     [rbp+arg_0], rax
0x180002987  call    cs:__imp_GetCurrentThreadId
0x18000298d  mov     eax, eax
0x18000298f  xor     [rbp+arg_0], rax
0x180002993  call    cs:__imp_GetTickCount
0x180002999  mov     eax, eax
0x18000299b  shl     rax, 18h
0x18000299f  xor     [rbp+arg_0], rax
0x1800029a3  call    cs:__imp_GetTickCount
0x1800029a9  mov     eax, eax
0x1800029ab  lea     rcx, [rbp+arg_0]
0x1800029af  xor     rax, [rbp+arg_0]
0x1800029b3  xor     rax, rcx
0x1800029b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800029ba  mov     [rbp+arg_0], rax
0x1800029be  call    cs:__imp_QueryPerformanceCounter
0x1800029c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800029c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800029d1  shl     rax, 20h
0x1800029d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800029d9  xor     rax, [rbp+arg_0]
0x1800029dd  and     rax, rcx
0x1800029e0  mov     rcx, rax
0x1800029e3  cmp     rax, rbx
0x1800029e6  jnz     short loc_1800029F5
0x1800029e8  mov     rax, 2B992DDFA233h
0x1800029f2  mov     rcx, rax
0x1800029f5  mov     cs:__security_cookie, rcx
0x1800029fc  mov     rbx, [rsp+20h+arg_18]
0x180002a01  not     rax
0x180002a04  mov     cs:__security_cookie_complement, rax
0x180002a0b  add     rsp, 20h
0x180002a0f  pop     rbp
0x180002a10  retn
```
