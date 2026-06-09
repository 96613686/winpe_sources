# __security_init_cookie

- ea: `0x1800aa630`
- end: `0x1800aa6e5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a9cd0`

## callees

- `0x1800aa630`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aa67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aa67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa673`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aa665`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aa665`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa68f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa68f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1800aa630  mov     [rsp-8+arg_10], rbx
0x1800aa635  push    rbp
0x1800aa636  mov     rbp, rsp
0x1800aa639  sub     rsp, 30h
0x1800aa63d  mov     rax, cs:__security_cookie
0x1800aa644  mov     rbx, 2B992DDFA232h
0x1800aa64e  cmp     rax, rbx
0x1800aa651  jnz     short loc_1800AA6D0
0x1800aa653  xor     eax, eax
0x1800aa655  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800aa659  mov     [rbp+var_10], rax
0x1800aa65d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800aa661  mov     qword ptr [rbp+PerformanceCount], rax
0x1800aa665  call    cs:__imp_GetSystemTimeAsFileTime
0x1800aa66b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800aa66f  mov     [rbp+var_10], rax
0x1800aa673  call    cs:__imp_GetCurrentThreadId
0x1800aa679  mov     eax, eax
0x1800aa67b  xor     [rbp+var_10], rax
0x1800aa67f  call    cs:__imp_GetCurrentProcessId
0x1800aa685  mov     eax, eax
0x1800aa687  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800aa68b  xor     [rbp+var_10], rax
0x1800aa68f  call    cs:__imp_QueryPerformanceCounter
0x1800aa695  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800aa698  lea     rcx, [rbp+var_10]
0x1800aa69c  shl     rax, 20h
0x1800aa6a0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800aa6a4  xor     rax, [rbp+var_10]
0x1800aa6a8  xor     rax, rcx
0x1800aa6ab  mov     rcx, 0FFFFFFFFFFFFh
0x1800aa6b5  and     rax, rcx
0x1800aa6b8  mov     rcx, 2B992DDFA233h
0x1800aa6c2  cmp     rax, rbx
0x1800aa6c5  cmovz   rax, rcx
0x1800aa6c9  mov     cs:__security_cookie, rax
0x1800aa6d0  mov     rbx, [rsp+30h+arg_10]
0x1800aa6d5  not     rax
0x1800aa6d8  mov     cs:__security_cookie_complement, rax
0x1800aa6df  add     rsp, 30h
0x1800aa6e3  pop     rbp
0x1800aa6e4  retn
```
