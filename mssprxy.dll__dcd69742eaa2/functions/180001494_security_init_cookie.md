# __security_init_cookie

- ea: `0x180001494`
- end: `0x180001549`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001420`

## callees

- `0x180001494`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800014c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800014c9`

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
0x180001494  mov     [rsp-8+arg_10], rbx
0x180001499  push    rbp
0x18000149a  mov     rbp, rsp
0x18000149d  sub     rsp, 30h
0x1800014a1  mov     rax, cs:__security_cookie
0x1800014a8  mov     rbx, 2B992DDFA232h
0x1800014b2  cmp     rax, rbx
0x1800014b5  jnz     short loc_180001534
0x1800014b7  xor     eax, eax
0x1800014b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800014bd  mov     [rbp+var_10], rax
0x1800014c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800014c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800014c9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800014cf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800014d3  mov     [rbp+var_10], rax
0x1800014d7  call    cs:__imp_GetCurrentThreadId
0x1800014dd  mov     eax, eax
0x1800014df  xor     [rbp+var_10], rax
0x1800014e3  call    cs:__imp_GetCurrentProcessId
0x1800014e9  mov     eax, eax
0x1800014eb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800014ef  xor     [rbp+var_10], rax
0x1800014f3  call    cs:__imp_QueryPerformanceCounter
0x1800014f9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800014fc  lea     rcx, [rbp+var_10]
0x180001500  shl     rax, 20h
0x180001504  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001508  xor     rax, [rbp+var_10]
0x18000150c  xor     rax, rcx
0x18000150f  mov     rcx, 0FFFFFFFFFFFFh
0x180001519  and     rax, rcx
0x18000151c  mov     rcx, 2B992DDFA233h
0x180001526  cmp     rax, rbx
0x180001529  cmovz   rax, rcx
0x18000152d  mov     cs:__security_cookie, rax
0x180001534  mov     rbx, [rsp+30h+arg_10]
0x180001539  not     rax
0x18000153c  mov     cs:__security_cookie_complement, rax
0x180001543  add     rsp, 30h
0x180001547  pop     rbp
0x180001548  retn
```
