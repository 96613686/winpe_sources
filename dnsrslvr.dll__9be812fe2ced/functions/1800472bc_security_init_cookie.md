# __security_init_cookie

- ea: `0x1800472bc`
- end: `0x180047371`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046e70`

## callees

- `0x1800472bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800472ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800472ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004730b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004730b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800472f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800472f1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004731b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004731b`

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
0x1800472bc  mov     [rsp-8+arg_10], rbx
0x1800472c1  push    rbp
0x1800472c2  mov     rbp, rsp
0x1800472c5  sub     rsp, 30h
0x1800472c9  mov     rax, cs:__security_cookie
0x1800472d0  mov     rbx, 2B992DDFA232h
0x1800472da  cmp     rax, rbx
0x1800472dd  jnz     short loc_18004735C
0x1800472df  xor     eax, eax
0x1800472e1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800472e5  mov     [rbp+var_10], rax
0x1800472e9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800472ed  mov     qword ptr [rbp+PerformanceCount], rax
0x1800472f1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800472f7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800472fb  mov     [rbp+var_10], rax
0x1800472ff  call    cs:__imp_GetCurrentThreadId
0x180047305  mov     eax, eax
0x180047307  xor     [rbp+var_10], rax
0x18004730b  call    cs:__imp_GetCurrentProcessId
0x180047311  mov     eax, eax
0x180047313  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180047317  xor     [rbp+var_10], rax
0x18004731b  call    cs:__imp_QueryPerformanceCounter
0x180047321  mov     eax, dword ptr [rbp+PerformanceCount]
0x180047324  lea     rcx, [rbp+var_10]
0x180047328  shl     rax, 20h
0x18004732c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180047330  xor     rax, [rbp+var_10]
0x180047334  xor     rax, rcx
0x180047337  mov     rcx, 0FFFFFFFFFFFFh
0x180047341  and     rax, rcx
0x180047344  mov     rcx, 2B992DDFA233h
0x18004734e  cmp     rax, rbx
0x180047351  cmovz   rax, rcx
0x180047355  mov     cs:__security_cookie, rax
0x18004735c  mov     rbx, [rsp+30h+arg_10]
0x180047361  not     rax
0x180047364  mov     cs:__security_cookie_complement, rax
0x18004736b  add     rsp, 30h
0x18004736f  pop     rbp
0x180047370  retn
```
