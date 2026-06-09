# __security_init_cookie

- ea: `0x1800026ec`
- end: `0x1800027a1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002290`

## callees

- `0x1800026ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000273b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000273b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000272f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000272f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000274b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000274b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002721`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002721`

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
0x1800026ec  mov     [rsp-8+arg_10], rbx
0x1800026f1  push    rbp
0x1800026f2  mov     rbp, rsp
0x1800026f5  sub     rsp, 30h
0x1800026f9  mov     rax, cs:__security_cookie
0x180002700  mov     rbx, 2B992DDFA232h
0x18000270a  cmp     rax, rbx
0x18000270d  jnz     short loc_18000278C
0x18000270f  xor     eax, eax
0x180002711  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002715  mov     [rbp+var_10], rax
0x180002719  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000271d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002721  call    cs:__imp_GetSystemTimeAsFileTime
0x180002727  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000272b  mov     [rbp+var_10], rax
0x18000272f  call    cs:__imp_GetCurrentThreadId
0x180002735  mov     eax, eax
0x180002737  xor     [rbp+var_10], rax
0x18000273b  call    cs:__imp_GetCurrentProcessId
0x180002741  mov     eax, eax
0x180002743  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002747  xor     [rbp+var_10], rax
0x18000274b  call    cs:__imp_QueryPerformanceCounter
0x180002751  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002754  lea     rcx, [rbp+var_10]
0x180002758  shl     rax, 20h
0x18000275c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002760  xor     rax, [rbp+var_10]
0x180002764  xor     rax, rcx
0x180002767  mov     rcx, 0FFFFFFFFFFFFh
0x180002771  and     rax, rcx
0x180002774  mov     rcx, 2B992DDFA233h
0x18000277e  cmp     rax, rbx
0x180002781  cmovz   rax, rcx
0x180002785  mov     cs:__security_cookie, rax
0x18000278c  mov     rbx, [rsp+30h+arg_10]
0x180002791  not     rax
0x180002794  mov     cs:__security_cookie_complement, rax
0x18000279b  add     rsp, 30h
0x18000279f  pop     rbp
0x1800027a0  retn
```
