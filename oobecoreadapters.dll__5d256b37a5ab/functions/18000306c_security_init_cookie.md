# __security_init_cookie

- ea: `0x18000306c`
- end: `0x180003121`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b10`

## callees

- `0x18000306c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800030cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800030cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800030a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800030a1`

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
0x18000306c  mov     [rsp-8+arg_10], rbx
0x180003071  push    rbp
0x180003072  mov     rbp, rsp
0x180003075  sub     rsp, 30h
0x180003079  mov     rax, cs:__security_cookie
0x180003080  mov     rbx, 2B992DDFA232h
0x18000308a  cmp     rax, rbx
0x18000308d  jnz     short loc_18000310C
0x18000308f  xor     eax, eax
0x180003091  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003095  mov     [rbp+var_10], rax
0x180003099  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000309d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800030a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800030a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800030ab  mov     [rbp+var_10], rax
0x1800030af  call    cs:__imp_GetCurrentThreadId
0x1800030b5  mov     eax, eax
0x1800030b7  xor     [rbp+var_10], rax
0x1800030bb  call    cs:__imp_GetCurrentProcessId
0x1800030c1  mov     eax, eax
0x1800030c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800030c7  xor     [rbp+var_10], rax
0x1800030cb  call    cs:__imp_QueryPerformanceCounter
0x1800030d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800030d4  lea     rcx, [rbp+var_10]
0x1800030d8  shl     rax, 20h
0x1800030dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800030e0  xor     rax, [rbp+var_10]
0x1800030e4  xor     rax, rcx
0x1800030e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800030f1  and     rax, rcx
0x1800030f4  mov     rcx, 2B992DDFA233h
0x1800030fe  cmp     rax, rbx
0x180003101  cmovz   rax, rcx
0x180003105  mov     cs:__security_cookie, rax
0x18000310c  mov     rbx, [rsp+30h+arg_10]
0x180003111  not     rax
0x180003114  mov     cs:__security_cookie_complement, rax
0x18000311b  add     rsp, 30h
0x18000311f  pop     rbp
0x180003120  retn
```
