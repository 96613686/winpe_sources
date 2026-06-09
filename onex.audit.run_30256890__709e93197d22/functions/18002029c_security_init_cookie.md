# __security_init_cookie

- ea: `0x18002029c`
- end: `0x180020351`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020200`

## callees

- `0x18002029c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800202df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800202df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800202eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800202eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800202d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800202d1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800202fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800202fb`

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
0x18002029c  mov     [rsp-8+arg_10], rbx
0x1800202a1  push    rbp
0x1800202a2  mov     rbp, rsp
0x1800202a5  sub     rsp, 30h
0x1800202a9  mov     rax, cs:__security_cookie
0x1800202b0  mov     rbx, 2B992DDFA232h
0x1800202ba  cmp     rax, rbx
0x1800202bd  jnz     short loc_18002033C
0x1800202bf  xor     eax, eax
0x1800202c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800202c5  mov     [rbp+var_10], rax
0x1800202c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800202cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800202d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800202d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800202db  mov     [rbp+var_10], rax
0x1800202df  call    cs:__imp_GetCurrentThreadId
0x1800202e5  mov     eax, eax
0x1800202e7  xor     [rbp+var_10], rax
0x1800202eb  call    cs:__imp_GetCurrentProcessId
0x1800202f1  mov     eax, eax
0x1800202f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800202f7  xor     [rbp+var_10], rax
0x1800202fb  call    cs:__imp_QueryPerformanceCounter
0x180020301  mov     eax, dword ptr [rbp+PerformanceCount]
0x180020304  lea     rcx, [rbp+var_10]
0x180020308  shl     rax, 20h
0x18002030c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180020310  xor     rax, [rbp+var_10]
0x180020314  xor     rax, rcx
0x180020317  mov     rcx, 0FFFFFFFFFFFFh
0x180020321  and     rax, rcx
0x180020324  mov     rcx, 2B992DDFA233h
0x18002032e  cmp     rax, rbx
0x180020331  cmovz   rax, rcx
0x180020335  mov     cs:__security_cookie, rax
0x18002033c  mov     rbx, [rsp+30h+arg_10]
0x180020341  not     rax
0x180020344  mov     cs:__security_cookie_complement, rax
0x18002034b  add     rsp, 30h
0x18002034f  pop     rbp
0x180020350  retn
```
