# __security_init_cookie

- ea: `0x180001c40`
- end: `0x180001cf5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001680`

## callees

- `0x180001c40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001c8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001c8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001c83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001c83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c9f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001c75`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001c75`

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
0x180001c40  mov     [rsp-8+arg_10], rbx
0x180001c45  push    rbp
0x180001c46  mov     rbp, rsp
0x180001c49  sub     rsp, 30h
0x180001c4d  mov     rax, cs:__security_cookie
0x180001c54  mov     rbx, 2B992DDFA232h
0x180001c5e  cmp     rax, rbx
0x180001c61  jnz     short loc_180001CE0
0x180001c63  xor     eax, eax
0x180001c65  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001c69  mov     [rbp+var_10], rax
0x180001c6d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c71  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c75  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c7b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001c7f  mov     [rbp+var_10], rax
0x180001c83  call    cs:__imp_GetCurrentThreadId
0x180001c89  mov     eax, eax
0x180001c8b  xor     [rbp+var_10], rax
0x180001c8f  call    cs:__imp_GetCurrentProcessId
0x180001c95  mov     eax, eax
0x180001c97  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c9b  xor     [rbp+var_10], rax
0x180001c9f  call    cs:__imp_QueryPerformanceCounter
0x180001ca5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ca8  lea     rcx, [rbp+var_10]
0x180001cac  shl     rax, 20h
0x180001cb0  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001cb4  xor     rax, [rbp+var_10]
0x180001cb8  xor     rax, rcx
0x180001cbb  mov     rcx, 0FFFFFFFFFFFFh
0x180001cc5  and     rax, rcx
0x180001cc8  mov     rcx, 2B992DDFA233h
0x180001cd2  cmp     rax, rbx
0x180001cd5  cmovz   rax, rcx
0x180001cd9  mov     cs:__security_cookie, rax
0x180001ce0  mov     rbx, [rsp+30h+arg_10]
0x180001ce5  not     rax
0x180001ce8  mov     cs:__security_cookie_complement, rax
0x180001cef  add     rsp, 30h
0x180001cf3  pop     rbp
0x180001cf4  retn
```
