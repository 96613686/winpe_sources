# __security_init_cookie

- ea: `0x180002f90`
- end: `0x180003045`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ac0`

## callees

- `0x180002f90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002fdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002fdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002fd3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fc5`

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
0x180002f90  mov     [rsp-8+arg_10], rbx
0x180002f95  push    rbp
0x180002f96  mov     rbp, rsp
0x180002f99  sub     rsp, 30h
0x180002f9d  mov     rax, cs:__security_cookie
0x180002fa4  mov     rbx, 2B992DDFA232h
0x180002fae  cmp     rax, rbx
0x180002fb1  jnz     short loc_180003030
0x180002fb3  xor     eax, eax
0x180002fb5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002fb9  mov     [rbp+var_10], rax
0x180002fbd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002fc1  mov     qword ptr [rbp+PerformanceCount], rax
0x180002fc5  call    cs:__imp_GetSystemTimeAsFileTime
0x180002fcb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002fcf  mov     [rbp+var_10], rax
0x180002fd3  call    cs:__imp_GetCurrentThreadId
0x180002fd9  mov     eax, eax
0x180002fdb  xor     [rbp+var_10], rax
0x180002fdf  call    cs:__imp_GetCurrentProcessId
0x180002fe5  mov     eax, eax
0x180002fe7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002feb  xor     [rbp+var_10], rax
0x180002fef  call    cs:__imp_QueryPerformanceCounter
0x180002ff5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ff8  lea     rcx, [rbp+var_10]
0x180002ffc  shl     rax, 20h
0x180003000  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003004  xor     rax, [rbp+var_10]
0x180003008  xor     rax, rcx
0x18000300b  mov     rcx, 0FFFFFFFFFFFFh
0x180003015  and     rax, rcx
0x180003018  mov     rcx, 2B992DDFA233h
0x180003022  cmp     rax, rbx
0x180003025  cmovz   rax, rcx
0x180003029  mov     cs:__security_cookie, rax
0x180003030  mov     rbx, [rsp+30h+arg_10]
0x180003035  not     rax
0x180003038  mov     cs:__security_cookie_complement, rax
0x18000303f  add     rsp, 30h
0x180003043  pop     rbp
0x180003044  retn
```
