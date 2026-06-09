# __security_init_cookie

- ea: `0x1800036c0`
- end: `0x180003775`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003220`

## callees

- `0x1800036c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000370f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000370f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003703`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000371f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000371f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800036f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800036f5`

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
0x1800036c0  mov     [rsp-8+arg_10], rbx
0x1800036c5  push    rbp
0x1800036c6  mov     rbp, rsp
0x1800036c9  sub     rsp, 30h
0x1800036cd  mov     rax, cs:__security_cookie
0x1800036d4  mov     rbx, 2B992DDFA232h
0x1800036de  cmp     rax, rbx
0x1800036e1  jnz     short loc_180003760
0x1800036e3  xor     eax, eax
0x1800036e5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800036e9  mov     [rbp+var_10], rax
0x1800036ed  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800036f1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800036f5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800036fb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800036ff  mov     [rbp+var_10], rax
0x180003703  call    cs:__imp_GetCurrentThreadId
0x180003709  mov     eax, eax
0x18000370b  xor     [rbp+var_10], rax
0x18000370f  call    cs:__imp_GetCurrentProcessId
0x180003715  mov     eax, eax
0x180003717  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000371b  xor     [rbp+var_10], rax
0x18000371f  call    cs:__imp_QueryPerformanceCounter
0x180003725  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003728  lea     rcx, [rbp+var_10]
0x18000372c  shl     rax, 20h
0x180003730  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003734  xor     rax, [rbp+var_10]
0x180003738  xor     rax, rcx
0x18000373b  mov     rcx, 0FFFFFFFFFFFFh
0x180003745  and     rax, rcx
0x180003748  mov     rcx, 2B992DDFA233h
0x180003752  cmp     rax, rbx
0x180003755  cmovz   rax, rcx
0x180003759  mov     cs:__security_cookie, rax
0x180003760  mov     rbx, [rsp+30h+arg_10]
0x180003765  not     rax
0x180003768  mov     cs:__security_cookie_complement, rax
0x18000376f  add     rsp, 30h
0x180003773  pop     rbp
0x180003774  retn
```
