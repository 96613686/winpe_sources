# __security_init_cookie

- ea: `0x140001ed4`
- end: `0x140001f89`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001b70`

## callees

- `0x140001ed4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001f09`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001f09`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001f33`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001f33`

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
0x140001ed4  mov     [rsp-8+arg_10], rbx
0x140001ed9  push    rbp
0x140001eda  mov     rbp, rsp
0x140001edd  sub     rsp, 30h
0x140001ee1  mov     rax, cs:__security_cookie
0x140001ee8  mov     rbx, 2B992DDFA232h
0x140001ef2  cmp     rax, rbx
0x140001ef5  jnz     short loc_140001F74
0x140001ef7  xor     eax, eax
0x140001ef9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001efd  mov     [rbp+var_10], rax
0x140001f01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001f05  mov     qword ptr [rbp+PerformanceCount], rax
0x140001f09  call    cs:__imp_GetSystemTimeAsFileTime
0x140001f0f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001f13  mov     [rbp+var_10], rax
0x140001f17  call    cs:__imp_GetCurrentThreadId
0x140001f1d  mov     eax, eax
0x140001f1f  xor     [rbp+var_10], rax
0x140001f23  call    cs:__imp_GetCurrentProcessId
0x140001f29  mov     eax, eax
0x140001f2b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001f2f  xor     [rbp+var_10], rax
0x140001f33  call    cs:__imp_QueryPerformanceCounter
0x140001f39  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001f3c  lea     rcx, [rbp+var_10]
0x140001f40  shl     rax, 20h
0x140001f44  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001f48  xor     rax, [rbp+var_10]
0x140001f4c  xor     rax, rcx
0x140001f4f  mov     rcx, 0FFFFFFFFFFFFh
0x140001f59  and     rax, rcx
0x140001f5c  mov     rcx, 2B992DDFA233h
0x140001f66  cmp     rax, rbx
0x140001f69  cmovz   rax, rcx
0x140001f6d  mov     cs:__security_cookie, rax
0x140001f74  mov     rbx, [rsp+30h+arg_10]
0x140001f79  not     rax
0x140001f7c  mov     cs:__security_cookie_complement, rax
0x140001f83  add     rsp, 30h
0x140001f87  pop     rbp
0x140001f88  retn
```
