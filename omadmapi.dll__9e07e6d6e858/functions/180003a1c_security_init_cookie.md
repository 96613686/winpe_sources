# __security_init_cookie

- ea: `0x180003a1c`
- end: `0x180003ad1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003160`

## callees

- `0x180003a1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003a51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003a51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003a7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003a7b`

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
0x180003a1c  mov     [rsp-8+arg_10], rbx
0x180003a21  push    rbp
0x180003a22  mov     rbp, rsp
0x180003a25  sub     rsp, 30h
0x180003a29  mov     rax, cs:__security_cookie
0x180003a30  mov     rbx, 2B992DDFA232h
0x180003a3a  cmp     rax, rbx
0x180003a3d  jnz     short loc_180003ABC
0x180003a3f  xor     eax, eax
0x180003a41  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003a45  mov     [rbp+var_10], rax
0x180003a49  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003a4d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003a51  call    cs:__imp_GetSystemTimeAsFileTime
0x180003a57  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003a5b  mov     [rbp+var_10], rax
0x180003a5f  call    cs:__imp_GetCurrentThreadId
0x180003a65  mov     eax, eax
0x180003a67  xor     [rbp+var_10], rax
0x180003a6b  call    cs:__imp_GetCurrentProcessId
0x180003a71  mov     eax, eax
0x180003a73  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003a77  xor     [rbp+var_10], rax
0x180003a7b  call    cs:__imp_QueryPerformanceCounter
0x180003a81  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003a84  lea     rcx, [rbp+var_10]
0x180003a88  shl     rax, 20h
0x180003a8c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003a90  xor     rax, [rbp+var_10]
0x180003a94  xor     rax, rcx
0x180003a97  mov     rcx, 0FFFFFFFFFFFFh
0x180003aa1  and     rax, rcx
0x180003aa4  mov     rcx, 2B992DDFA233h
0x180003aae  cmp     rax, rbx
0x180003ab1  cmovz   rax, rcx
0x180003ab5  mov     cs:__security_cookie, rax
0x180003abc  mov     rbx, [rsp+30h+arg_10]
0x180003ac1  not     rax
0x180003ac4  mov     cs:__security_cookie_complement, rax
0x180003acb  add     rsp, 30h
0x180003acf  pop     rbp
0x180003ad0  retn
```
