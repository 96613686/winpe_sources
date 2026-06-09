# __security_init_cookie

- ea: `0x18000165c`
- end: `0x180001711`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001560`

## callees

- `0x18000165c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000169f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000169f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001691`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001691`

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
0x18000165c  mov     [rsp-8+arg_10], rbx
0x180001661  push    rbp
0x180001662  mov     rbp, rsp
0x180001665  sub     rsp, 30h
0x180001669  mov     rax, cs:__security_cookie
0x180001670  mov     rbx, 2B992DDFA232h
0x18000167a  cmp     rax, rbx
0x18000167d  jnz     short loc_1800016FC
0x18000167f  xor     eax, eax
0x180001681  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001685  mov     [rbp+var_10], rax
0x180001689  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000168d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001691  call    cs:__imp_GetSystemTimeAsFileTime
0x180001697  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000169b  mov     [rbp+var_10], rax
0x18000169f  call    cs:__imp_GetCurrentThreadId
0x1800016a5  mov     eax, eax
0x1800016a7  xor     [rbp+var_10], rax
0x1800016ab  call    cs:__imp_GetCurrentProcessId
0x1800016b1  mov     eax, eax
0x1800016b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800016b7  xor     [rbp+var_10], rax
0x1800016bb  call    cs:__imp_QueryPerformanceCounter
0x1800016c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800016c4  lea     rcx, [rbp+var_10]
0x1800016c8  shl     rax, 20h
0x1800016cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800016d0  xor     rax, [rbp+var_10]
0x1800016d4  xor     rax, rcx
0x1800016d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800016e1  and     rax, rcx
0x1800016e4  mov     rcx, 2B992DDFA233h
0x1800016ee  cmp     rax, rbx
0x1800016f1  cmovz   rax, rcx
0x1800016f5  mov     cs:__security_cookie, rax
0x1800016fc  mov     rbx, [rsp+30h+arg_10]
0x180001701  not     rax
0x180001704  mov     cs:__security_cookie_complement, rax
0x18000170b  add     rsp, 30h
0x18000170f  pop     rbp
0x180001710  retn
```
