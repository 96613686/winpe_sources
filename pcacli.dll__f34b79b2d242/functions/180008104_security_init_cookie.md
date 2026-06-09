# __security_init_cookie

- ea: `0x180008104`
- end: `0x1800081e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007aa0`

## callees

- `0x180008104`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000814b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000814b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008157`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000818e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000818e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000813d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000813d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008163`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008173`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008163`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180008173`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180008104  mov     [rsp-8+arg_18], rbx
0x180008109  push    rbp
0x18000810a  mov     rbp, rsp
0x18000810d  sub     rsp, 20h
0x180008111  xor     eax, eax
0x180008113  mov     rbx, 2B992DDFA232h
0x18000811d  mov     [rbp+arg_0], rax
0x180008121  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008125  mov     qword ptr [rbp+PerformanceCount], rax
0x180008129  mov     rax, cs:__security_cookie
0x180008130  cmp     rax, rbx
0x180008133  jnz     loc_1800081CC
0x180008139  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000813d  call    cs:__imp_GetSystemTimeAsFileTime
0x180008143  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008147  mov     [rbp+arg_0], rax
0x18000814b  call    cs:__imp_GetCurrentProcessId
0x180008151  mov     eax, eax
0x180008153  xor     [rbp+arg_0], rax
0x180008157  call    cs:__imp_GetCurrentThreadId
0x18000815d  mov     eax, eax
0x18000815f  xor     [rbp+arg_0], rax
0x180008163  call    cs:__imp_GetTickCount
0x180008169  mov     eax, eax
0x18000816b  shl     rax, 18h
0x18000816f  xor     [rbp+arg_0], rax
0x180008173  call    cs:__imp_GetTickCount
0x180008179  mov     eax, eax
0x18000817b  lea     rcx, [rbp+arg_0]
0x18000817f  xor     rax, [rbp+arg_0]
0x180008183  xor     rax, rcx
0x180008186  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000818a  mov     [rbp+arg_0], rax
0x18000818e  call    cs:__imp_QueryPerformanceCounter
0x180008194  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008197  mov     rcx, 0FFFFFFFFFFFFh
0x1800081a1  shl     rax, 20h
0x1800081a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800081a9  xor     rax, [rbp+arg_0]
0x1800081ad  and     rax, rcx
0x1800081b0  mov     rcx, rax
0x1800081b3  cmp     rax, rbx
0x1800081b6  jnz     short loc_1800081C5
0x1800081b8  mov     rax, 2B992DDFA233h
0x1800081c2  mov     rcx, rax
0x1800081c5  mov     cs:__security_cookie, rcx
0x1800081cc  mov     rbx, [rsp+20h+arg_18]
0x1800081d1  not     rax
0x1800081d4  mov     cs:__security_cookie_complement, rax
0x1800081db  add     rsp, 20h
0x1800081df  pop     rbp
0x1800081e0  retn
```
