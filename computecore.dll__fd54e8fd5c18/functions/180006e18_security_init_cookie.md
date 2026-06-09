# __security_init_cookie

- ea: `0x180006e18`
- end: `0x180006ecd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006770`

## callees

- `0x180006e18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006e67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006e67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006e4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006e4d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006e77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006e77`

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
0x180006e18  mov     [rsp-8+arg_10], rbx
0x180006e1d  push    rbp
0x180006e1e  mov     rbp, rsp
0x180006e21  sub     rsp, 30h
0x180006e25  mov     rax, cs:__security_cookie
0x180006e2c  mov     rbx, 2B992DDFA232h
0x180006e36  cmp     rax, rbx
0x180006e39  jnz     short loc_180006EB8
0x180006e3b  xor     eax, eax
0x180006e3d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006e41  mov     [rbp+var_10], rax
0x180006e45  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006e49  mov     qword ptr [rbp+PerformanceCount], rax
0x180006e4d  call    cs:__imp_GetSystemTimeAsFileTime
0x180006e53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180006e57  mov     [rbp+var_10], rax
0x180006e5b  call    cs:__imp_GetCurrentThreadId
0x180006e61  mov     eax, eax
0x180006e63  xor     [rbp+var_10], rax
0x180006e67  call    cs:__imp_GetCurrentProcessId
0x180006e6d  mov     eax, eax
0x180006e6f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180006e73  xor     [rbp+var_10], rax
0x180006e77  call    cs:__imp_QueryPerformanceCounter
0x180006e7d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006e80  lea     rcx, [rbp+var_10]
0x180006e84  shl     rax, 20h
0x180006e88  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006e8c  xor     rax, [rbp+var_10]
0x180006e90  xor     rax, rcx
0x180006e93  mov     rcx, 0FFFFFFFFFFFFh
0x180006e9d  and     rax, rcx
0x180006ea0  mov     rcx, 2B992DDFA233h
0x180006eaa  cmp     rax, rbx
0x180006ead  cmovz   rax, rcx
0x180006eb1  mov     cs:__security_cookie, rax
0x180006eb8  mov     rbx, [rsp+30h+arg_10]
0x180006ebd  not     rax
0x180006ec0  mov     cs:__security_cookie_complement, rax
0x180006ec7  add     rsp, 30h
0x180006ecb  pop     rbp
0x180006ecc  retn
```
