# __security_init_cookie

- ea: `0x18000329c`
- end: `0x180003351`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x18000329c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800032eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800032eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800032d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800032d1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800032fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800032fb`

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
0x18000329c  mov     [rsp-8+arg_10], rbx
0x1800032a1  push    rbp
0x1800032a2  mov     rbp, rsp
0x1800032a5  sub     rsp, 30h
0x1800032a9  mov     rax, cs:__security_cookie
0x1800032b0  mov     rbx, 2B992DDFA232h
0x1800032ba  cmp     rax, rbx
0x1800032bd  jnz     short loc_18000333C
0x1800032bf  xor     eax, eax
0x1800032c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800032c5  mov     [rbp+var_10], rax
0x1800032c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800032cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800032d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800032d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800032db  mov     [rbp+var_10], rax
0x1800032df  call    cs:__imp_GetCurrentThreadId
0x1800032e5  mov     eax, eax
0x1800032e7  xor     [rbp+var_10], rax
0x1800032eb  call    cs:__imp_GetCurrentProcessId
0x1800032f1  mov     eax, eax
0x1800032f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800032f7  xor     [rbp+var_10], rax
0x1800032fb  call    cs:__imp_QueryPerformanceCounter
0x180003301  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003304  lea     rcx, [rbp+var_10]
0x180003308  shl     rax, 20h
0x18000330c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003310  xor     rax, [rbp+var_10]
0x180003314  xor     rax, rcx
0x180003317  mov     rcx, 0FFFFFFFFFFFFh
0x180003321  and     rax, rcx
0x180003324  mov     rcx, 2B992DDFA233h
0x18000332e  cmp     rax, rbx
0x180003331  cmovz   rax, rcx
0x180003335  mov     cs:__security_cookie, rax
0x18000333c  mov     rbx, [rsp+30h+arg_10]
0x180003341  not     rax
0x180003344  mov     cs:__security_cookie_complement, rax
0x18000334b  add     rsp, 30h
0x18000334f  pop     rbp
0x180003350  retn
```
