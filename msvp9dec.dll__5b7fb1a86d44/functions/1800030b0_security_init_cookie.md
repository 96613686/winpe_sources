# __security_init_cookie

- ea: `0x1800030b0`
- end: `0x180003165`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002c60`

## callees

- `0x1800030b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800030ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000310f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000310f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800030e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800030e5`

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
0x1800030b0  mov     [rsp-8+arg_10], rbx
0x1800030b5  push    rbp
0x1800030b6  mov     rbp, rsp
0x1800030b9  sub     rsp, 30h
0x1800030bd  mov     rax, cs:__security_cookie
0x1800030c4  mov     rbx, 2B992DDFA232h
0x1800030ce  cmp     rax, rbx
0x1800030d1  jnz     short loc_180003150
0x1800030d3  xor     eax, eax
0x1800030d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800030d9  mov     [rbp+var_10], rax
0x1800030dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800030e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800030e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800030eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800030ef  mov     [rbp+var_10], rax
0x1800030f3  call    cs:__imp_GetCurrentThreadId
0x1800030f9  mov     eax, eax
0x1800030fb  xor     [rbp+var_10], rax
0x1800030ff  call    cs:__imp_GetCurrentProcessId
0x180003105  mov     eax, eax
0x180003107  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000310b  xor     [rbp+var_10], rax
0x18000310f  call    cs:__imp_QueryPerformanceCounter
0x180003115  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003118  lea     rcx, [rbp+var_10]
0x18000311c  shl     rax, 20h
0x180003120  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003124  xor     rax, [rbp+var_10]
0x180003128  xor     rax, rcx
0x18000312b  mov     rcx, 0FFFFFFFFFFFFh
0x180003135  and     rax, rcx
0x180003138  mov     rcx, 2B992DDFA233h
0x180003142  cmp     rax, rbx
0x180003145  cmovz   rax, rcx
0x180003149  mov     cs:__security_cookie, rax
0x180003150  mov     rbx, [rsp+30h+arg_10]
0x180003155  not     rax
0x180003158  mov     cs:__security_cookie_complement, rax
0x18000315f  add     rsp, 30h
0x180003163  pop     rbp
0x180003164  retn
```
