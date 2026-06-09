# __security_init_cookie

- ea: `0x180014e10`
- end: `0x180014ec5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014d70`

## callees

- `0x180014e10`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180014e6f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180014e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014e5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014e5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014e45`

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
0x180014e10  mov     [rsp-8+arg_10], rbx
0x180014e15  push    rbp
0x180014e16  mov     rbp, rsp
0x180014e19  sub     rsp, 30h
0x180014e1d  mov     rax, cs:__security_cookie
0x180014e24  mov     rbx, 2B992DDFA232h
0x180014e2e  cmp     rax, rbx
0x180014e31  jnz     short loc_180014EB0
0x180014e33  xor     eax, eax
0x180014e35  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014e39  mov     [rbp+var_10], rax
0x180014e3d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180014e41  mov     qword ptr [rbp+PerformanceCount], rax
0x180014e45  call    cs:__imp_GetSystemTimeAsFileTime
0x180014e4b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180014e4f  mov     [rbp+var_10], rax
0x180014e53  call    cs:__imp_GetCurrentThreadId
0x180014e59  mov     eax, eax
0x180014e5b  xor     [rbp+var_10], rax
0x180014e5f  call    cs:__imp_GetCurrentProcessId
0x180014e65  mov     eax, eax
0x180014e67  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180014e6b  xor     [rbp+var_10], rax
0x180014e6f  call    cs:__imp_QueryPerformanceCounter
0x180014e75  mov     eax, dword ptr [rbp+PerformanceCount]
0x180014e78  lea     rcx, [rbp+var_10]
0x180014e7c  shl     rax, 20h
0x180014e80  xor     rax, qword ptr [rbp+PerformanceCount]
0x180014e84  xor     rax, [rbp+var_10]
0x180014e88  xor     rax, rcx
0x180014e8b  mov     rcx, 0FFFFFFFFFFFFh
0x180014e95  and     rax, rcx
0x180014e98  mov     rcx, 2B992DDFA233h
0x180014ea2  cmp     rax, rbx
0x180014ea5  cmovz   rax, rcx
0x180014ea9  mov     cs:__security_cookie, rax
0x180014eb0  mov     rbx, [rsp+30h+arg_10]
0x180014eb5  not     rax
0x180014eb8  mov     cs:__security_cookie_complement, rax
0x180014ebf  add     rsp, 30h
0x180014ec3  pop     rbp
0x180014ec4  retn
```
