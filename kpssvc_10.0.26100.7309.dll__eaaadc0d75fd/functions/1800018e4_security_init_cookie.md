# __security_init_cookie

- ea: `0x1800018e4`
- end: `0x1800019bd`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014b0`

## callees

- `0x1800018e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001933`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001933`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000196a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000196a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000193f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000194f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000193f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000194f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001919`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001919`

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
0x1800018e4  mov     [rsp-8+arg_18], rbx
0x1800018e9  push    rbp
0x1800018ea  mov     rbp, rsp
0x1800018ed  sub     rsp, 20h
0x1800018f1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800018f6  mov     rbx, 2B992DDFA232h
0x180001900  and     qword ptr [rbp+PerformanceCount], 0
0x180001905  mov     rax, cs:__security_cookie
0x18000190c  cmp     rax, rbx
0x18000190f  jnz     loc_1800019A8
0x180001915  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001919  call    cs:__imp_GetSystemTimeAsFileTime
0x18000191f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001923  mov     [rbp+arg_0], rax
0x180001927  call    cs:__imp_GetCurrentProcessId
0x18000192d  mov     eax, eax
0x18000192f  xor     [rbp+arg_0], rax
0x180001933  call    cs:__imp_GetCurrentThreadId
0x180001939  mov     eax, eax
0x18000193b  xor     [rbp+arg_0], rax
0x18000193f  call    cs:__imp_GetTickCount
0x180001945  mov     eax, eax
0x180001947  shl     rax, 18h
0x18000194b  xor     [rbp+arg_0], rax
0x18000194f  call    cs:__imp_GetTickCount
0x180001955  mov     eax, eax
0x180001957  lea     rcx, [rbp+arg_0]
0x18000195b  xor     rax, [rbp+arg_0]
0x18000195f  xor     rax, rcx
0x180001962  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001966  mov     [rbp+arg_0], rax
0x18000196a  call    cs:__imp_QueryPerformanceCounter
0x180001970  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001973  mov     rcx, 0FFFFFFFFFFFFh
0x18000197d  shl     rax, 20h
0x180001981  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001985  xor     rax, [rbp+arg_0]
0x180001989  and     rax, rcx
0x18000198c  mov     rcx, rax
0x18000198f  cmp     rax, rbx
0x180001992  jnz     short loc_1800019A1
0x180001994  mov     rax, 2B992DDFA233h
0x18000199e  mov     rcx, rax
0x1800019a1  mov     cs:__security_cookie, rcx
0x1800019a8  mov     rbx, [rsp+20h+arg_18]
0x1800019ad  not     rax
0x1800019b0  mov     cs:__security_cookie_complement, rax
0x1800019b7  add     rsp, 20h
0x1800019bb  pop     rbp
0x1800019bc  retn
```
