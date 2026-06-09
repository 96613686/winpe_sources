# __security_init_cookie

- ea: `0x180042b40`
- end: `0x180042bf5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800423c0`

## callees

- `0x180042b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042b8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180042b8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042b83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042b83`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180042b75`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180042b75`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180042b9f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180042b9f`

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
0x180042b40  mov     [rsp-8+arg_10], rbx
0x180042b45  push    rbp
0x180042b46  mov     rbp, rsp
0x180042b49  sub     rsp, 30h
0x180042b4d  mov     rax, cs:__security_cookie
0x180042b54  mov     rbx, 2B992DDFA232h
0x180042b5e  cmp     rax, rbx
0x180042b61  jnz     short loc_180042BE0
0x180042b63  xor     eax, eax
0x180042b65  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180042b69  mov     [rbp+var_10], rax
0x180042b6d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180042b71  mov     qword ptr [rbp+PerformanceCount], rax
0x180042b75  call    cs:__imp_GetSystemTimeAsFileTime
0x180042b7b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180042b7f  mov     [rbp+var_10], rax
0x180042b83  call    cs:__imp_GetCurrentThreadId
0x180042b89  mov     eax, eax
0x180042b8b  xor     [rbp+var_10], rax
0x180042b8f  call    cs:__imp_GetCurrentProcessId
0x180042b95  mov     eax, eax
0x180042b97  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180042b9b  xor     [rbp+var_10], rax
0x180042b9f  call    cs:__imp_QueryPerformanceCounter
0x180042ba5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180042ba8  lea     rcx, [rbp+var_10]
0x180042bac  shl     rax, 20h
0x180042bb0  xor     rax, qword ptr [rbp+PerformanceCount]
0x180042bb4  xor     rax, [rbp+var_10]
0x180042bb8  xor     rax, rcx
0x180042bbb  mov     rcx, 0FFFFFFFFFFFFh
0x180042bc5  and     rax, rcx
0x180042bc8  mov     rcx, 2B992DDFA233h
0x180042bd2  cmp     rax, rbx
0x180042bd5  cmovz   rax, rcx
0x180042bd9  mov     cs:__security_cookie, rax
0x180042be0  mov     rbx, [rsp+30h+arg_10]
0x180042be5  not     rax
0x180042be8  mov     cs:__security_cookie_complement, rax
0x180042bef  add     rsp, 30h
0x180042bf3  pop     rbp
0x180042bf4  retn
```
