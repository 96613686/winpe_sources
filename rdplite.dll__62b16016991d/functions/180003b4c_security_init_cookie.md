# __security_init_cookie

- ea: `0x180003b4c`
- end: `0x180003c01`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800036a0`

## callees

- `0x180003b4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003bab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003bab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003b81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003b81`

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
0x180003b4c  mov     [rsp-8+arg_10], rbx
0x180003b51  push    rbp
0x180003b52  mov     rbp, rsp
0x180003b55  sub     rsp, 30h
0x180003b59  mov     rax, cs:__security_cookie
0x180003b60  mov     rbx, 2B992DDFA232h
0x180003b6a  cmp     rax, rbx
0x180003b6d  jnz     short loc_180003BEC
0x180003b6f  xor     eax, eax
0x180003b71  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003b75  mov     [rbp+var_10], rax
0x180003b79  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003b7d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003b81  call    cs:__imp_GetSystemTimeAsFileTime
0x180003b87  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003b8b  mov     [rbp+var_10], rax
0x180003b8f  call    cs:__imp_GetCurrentThreadId
0x180003b95  mov     eax, eax
0x180003b97  xor     [rbp+var_10], rax
0x180003b9b  call    cs:__imp_GetCurrentProcessId
0x180003ba1  mov     eax, eax
0x180003ba3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003ba7  xor     [rbp+var_10], rax
0x180003bab  call    cs:__imp_QueryPerformanceCounter
0x180003bb1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003bb4  lea     rcx, [rbp+var_10]
0x180003bb8  shl     rax, 20h
0x180003bbc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003bc0  xor     rax, [rbp+var_10]
0x180003bc4  xor     rax, rcx
0x180003bc7  mov     rcx, 0FFFFFFFFFFFFh
0x180003bd1  and     rax, rcx
0x180003bd4  mov     rcx, 2B992DDFA233h
0x180003bde  cmp     rax, rbx
0x180003be1  cmovz   rax, rcx
0x180003be5  mov     cs:__security_cookie, rax
0x180003bec  mov     rbx, [rsp+30h+arg_10]
0x180003bf1  not     rax
0x180003bf4  mov     cs:__security_cookie_complement, rax
0x180003bfb  add     rsp, 30h
0x180003bff  pop     rbp
0x180003c00  retn
```
