# __security_init_cookie

- ea: `0x1800149e0`
- end: `0x180014a95`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800140d0`

## callees

- `0x1800149e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014a2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014a15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014a15`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180014a3f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180014a3f`

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
0x1800149e0  mov     [rsp-8+arg_10], rbx
0x1800149e5  push    rbp
0x1800149e6  mov     rbp, rsp
0x1800149e9  sub     rsp, 30h
0x1800149ed  mov     rax, cs:__security_cookie
0x1800149f4  mov     rbx, 2B992DDFA232h
0x1800149fe  cmp     rax, rbx
0x180014a01  jnz     short loc_180014A80
0x180014a03  xor     eax, eax
0x180014a05  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014a09  mov     [rbp+var_10], rax
0x180014a0d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180014a11  mov     qword ptr [rbp+PerformanceCount], rax
0x180014a15  call    cs:__imp_GetSystemTimeAsFileTime
0x180014a1b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180014a1f  mov     [rbp+var_10], rax
0x180014a23  call    cs:__imp_GetCurrentThreadId
0x180014a29  mov     eax, eax
0x180014a2b  xor     [rbp+var_10], rax
0x180014a2f  call    cs:__imp_GetCurrentProcessId
0x180014a35  mov     eax, eax
0x180014a37  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180014a3b  xor     [rbp+var_10], rax
0x180014a3f  call    cs:__imp_QueryPerformanceCounter
0x180014a45  mov     eax, dword ptr [rbp+PerformanceCount]
0x180014a48  lea     rcx, [rbp+var_10]
0x180014a4c  shl     rax, 20h
0x180014a50  xor     rax, qword ptr [rbp+PerformanceCount]
0x180014a54  xor     rax, [rbp+var_10]
0x180014a58  xor     rax, rcx
0x180014a5b  mov     rcx, 0FFFFFFFFFFFFh
0x180014a65  and     rax, rcx
0x180014a68  mov     rcx, 2B992DDFA233h
0x180014a72  cmp     rax, rbx
0x180014a75  cmovz   rax, rcx
0x180014a79  mov     cs:__security_cookie, rax
0x180014a80  mov     rbx, [rsp+30h+arg_10]
0x180014a85  not     rax
0x180014a88  mov     cs:__security_cookie_complement, rax
0x180014a8f  add     rsp, 30h
0x180014a93  pop     rbp
0x180014a94  retn
```
