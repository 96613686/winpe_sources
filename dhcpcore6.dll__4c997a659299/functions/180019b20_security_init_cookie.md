# __security_init_cookie

- ea: `0x180019b20`
- end: `0x180019bd5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019a80`

## callees

- `0x180019b20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019b63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019b63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019b6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019b6f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019b7f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019b7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019b55`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019b55`

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
0x180019b20  mov     [rsp-8+arg_10], rbx
0x180019b25  push    rbp
0x180019b26  mov     rbp, rsp
0x180019b29  sub     rsp, 30h
0x180019b2d  mov     rax, cs:__security_cookie
0x180019b34  mov     rbx, 2B992DDFA232h
0x180019b3e  cmp     rax, rbx
0x180019b41  jnz     short loc_180019BC0
0x180019b43  xor     eax, eax
0x180019b45  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019b49  mov     [rbp+var_10], rax
0x180019b4d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180019b51  mov     qword ptr [rbp+PerformanceCount], rax
0x180019b55  call    cs:__imp_GetSystemTimeAsFileTime
0x180019b5b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180019b5f  mov     [rbp+var_10], rax
0x180019b63  call    cs:__imp_GetCurrentThreadId
0x180019b69  mov     eax, eax
0x180019b6b  xor     [rbp+var_10], rax
0x180019b6f  call    cs:__imp_GetCurrentProcessId
0x180019b75  mov     eax, eax
0x180019b77  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180019b7b  xor     [rbp+var_10], rax
0x180019b7f  call    cs:__imp_QueryPerformanceCounter
0x180019b85  mov     eax, dword ptr [rbp+PerformanceCount]
0x180019b88  lea     rcx, [rbp+var_10]
0x180019b8c  shl     rax, 20h
0x180019b90  xor     rax, qword ptr [rbp+PerformanceCount]
0x180019b94  xor     rax, [rbp+var_10]
0x180019b98  xor     rax, rcx
0x180019b9b  mov     rcx, 0FFFFFFFFFFFFh
0x180019ba5  and     rax, rcx
0x180019ba8  mov     rcx, 2B992DDFA233h
0x180019bb2  cmp     rax, rbx
0x180019bb5  cmovz   rax, rcx
0x180019bb9  mov     cs:__security_cookie, rax
0x180019bc0  mov     rbx, [rsp+30h+arg_10]
0x180019bc5  not     rax
0x180019bc8  mov     cs:__security_cookie_complement, rax
0x180019bcf  add     rsp, 30h
0x180019bd3  pop     rbp
0x180019bd4  retn
```
