# __security_init_cookie

- ea: `0x180001534`
- end: `0x1800015e9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x180001534`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001593`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001577`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001569`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001569`

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
0x180001534  mov     [rsp-8+arg_10], rbx
0x180001539  push    rbp
0x18000153a  mov     rbp, rsp
0x18000153d  sub     rsp, 30h
0x180001541  mov     rax, cs:__security_cookie
0x180001548  mov     rbx, 2B992DDFA232h
0x180001552  cmp     rax, rbx
0x180001555  jnz     short loc_1800015D4
0x180001557  xor     eax, eax
0x180001559  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000155d  mov     [rbp+var_10], rax
0x180001561  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001565  mov     qword ptr [rbp+PerformanceCount], rax
0x180001569  call    cs:__imp_GetSystemTimeAsFileTime
0x18000156f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001573  mov     [rbp+var_10], rax
0x180001577  call    cs:__imp_GetCurrentThreadId
0x18000157d  mov     eax, eax
0x18000157f  xor     [rbp+var_10], rax
0x180001583  call    cs:__imp_GetCurrentProcessId
0x180001589  mov     eax, eax
0x18000158b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000158f  xor     [rbp+var_10], rax
0x180001593  call    cs:__imp_QueryPerformanceCounter
0x180001599  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000159c  lea     rcx, [rbp+var_10]
0x1800015a0  shl     rax, 20h
0x1800015a4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800015a8  xor     rax, [rbp+var_10]
0x1800015ac  xor     rax, rcx
0x1800015af  mov     rcx, 0FFFFFFFFFFFFh
0x1800015b9  and     rax, rcx
0x1800015bc  mov     rcx, 2B992DDFA233h
0x1800015c6  cmp     rax, rbx
0x1800015c9  cmovz   rax, rcx
0x1800015cd  mov     cs:__security_cookie, rax
0x1800015d4  mov     rbx, [rsp+30h+arg_10]
0x1800015d9  not     rax
0x1800015dc  mov     cs:__security_cookie_complement, rax
0x1800015e3  add     rsp, 30h
0x1800015e7  pop     rbp
0x1800015e8  retn
```
