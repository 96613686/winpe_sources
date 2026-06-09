# __security_init_cookie

- ea: `0x180003694`
- end: `0x180003771`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800031f0`

## callees

- `0x180003694`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000371e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000371e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800036cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800036cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800036f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003703`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800036f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003703`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180003694  mov     [rsp-8+arg_18], rbx
0x180003699  push    rbp
0x18000369a  mov     rbp, rsp
0x18000369d  sub     rsp, 20h
0x1800036a1  xor     eax, eax
0x1800036a3  mov     rbx, 2B992DDFA232h
0x1800036ad  mov     [rbp+arg_0], rax
0x1800036b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800036b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800036b9  mov     rax, cs:__security_cookie
0x1800036c0  cmp     rax, rbx
0x1800036c3  jnz     loc_18000375C
0x1800036c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800036cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800036d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800036d7  mov     [rbp+arg_0], rax
0x1800036db  call    cs:__imp_GetCurrentProcessId
0x1800036e1  mov     eax, eax
0x1800036e3  xor     [rbp+arg_0], rax
0x1800036e7  call    cs:__imp_GetCurrentThreadId
0x1800036ed  mov     eax, eax
0x1800036ef  xor     [rbp+arg_0], rax
0x1800036f3  call    cs:__imp_GetTickCount
0x1800036f9  mov     eax, eax
0x1800036fb  shl     rax, 18h
0x1800036ff  xor     [rbp+arg_0], rax
0x180003703  call    cs:__imp_GetTickCount
0x180003709  mov     eax, eax
0x18000370b  lea     rcx, [rbp+arg_0]
0x18000370f  xor     rax, [rbp+arg_0]
0x180003713  xor     rax, rcx
0x180003716  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000371a  mov     [rbp+arg_0], rax
0x18000371e  call    cs:__imp_QueryPerformanceCounter
0x180003724  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003727  mov     rcx, 0FFFFFFFFFFFFh
0x180003731  shl     rax, 20h
0x180003735  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003739  xor     rax, [rbp+arg_0]
0x18000373d  and     rax, rcx
0x180003740  mov     rcx, rax
0x180003743  cmp     rax, rbx
0x180003746  jnz     short loc_180003755
0x180003748  mov     rax, 2B992DDFA233h
0x180003752  mov     rcx, rax
0x180003755  mov     cs:__security_cookie, rcx
0x18000375c  mov     rbx, [rsp+20h+arg_18]
0x180003761  not     rax
0x180003764  mov     cs:__security_cookie_complement, rax
0x18000376b  add     rsp, 20h
0x18000376f  pop     rbp
0x180003770  retn
```
