# __security_init_cookie

- ea: `0x180003df8`
- end: `0x180003ead`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800039a0`

## callees

- `0x180003df8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003e57`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003e57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003e2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003e2d`

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
0x180003df8  mov     [rsp-8+arg_10], rbx
0x180003dfd  push    rbp
0x180003dfe  mov     rbp, rsp
0x180003e01  sub     rsp, 30h
0x180003e05  mov     rax, cs:__security_cookie
0x180003e0c  mov     rbx, 2B992DDFA232h
0x180003e16  cmp     rax, rbx
0x180003e19  jnz     short loc_180003E98
0x180003e1b  xor     eax, eax
0x180003e1d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003e21  mov     [rbp+var_10], rax
0x180003e25  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003e29  mov     qword ptr [rbp+PerformanceCount], rax
0x180003e2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003e33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003e37  mov     [rbp+var_10], rax
0x180003e3b  call    cs:__imp_GetCurrentThreadId
0x180003e41  mov     eax, eax
0x180003e43  xor     [rbp+var_10], rax
0x180003e47  call    cs:__imp_GetCurrentProcessId
0x180003e4d  mov     eax, eax
0x180003e4f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003e53  xor     [rbp+var_10], rax
0x180003e57  call    cs:__imp_QueryPerformanceCounter
0x180003e5d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003e60  lea     rcx, [rbp+var_10]
0x180003e64  shl     rax, 20h
0x180003e68  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003e6c  xor     rax, [rbp+var_10]
0x180003e70  xor     rax, rcx
0x180003e73  mov     rcx, 0FFFFFFFFFFFFh
0x180003e7d  and     rax, rcx
0x180003e80  mov     rcx, 2B992DDFA233h
0x180003e8a  cmp     rax, rbx
0x180003e8d  cmovz   rax, rcx
0x180003e91  mov     cs:__security_cookie, rax
0x180003e98  mov     rbx, [rsp+30h+arg_10]
0x180003e9d  not     rax
0x180003ea0  mov     cs:__security_cookie_complement, rax
0x180003ea7  add     rsp, 30h
0x180003eab  pop     rbp
0x180003eac  retn
```
