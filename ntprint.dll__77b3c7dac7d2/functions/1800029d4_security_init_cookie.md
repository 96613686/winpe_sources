# __security_init_cookie

- ea: `0x1800029d4`
- end: `0x180002a89`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022b0`

## callees

- `0x1800029d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a09`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a09`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a33`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a33`

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
0x1800029d4  mov     [rsp-8+arg_10], rbx
0x1800029d9  push    rbp
0x1800029da  mov     rbp, rsp
0x1800029dd  sub     rsp, 30h
0x1800029e1  mov     rax, cs:__security_cookie
0x1800029e8  mov     rbx, 2B992DDFA232h
0x1800029f2  cmp     rax, rbx
0x1800029f5  jnz     short loc_180002A74
0x1800029f7  xor     eax, eax
0x1800029f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800029fd  mov     [rbp+var_10], rax
0x180002a01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002a05  mov     qword ptr [rbp+PerformanceCount], rax
0x180002a09  call    cs:__imp_GetSystemTimeAsFileTime
0x180002a0f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002a13  mov     [rbp+var_10], rax
0x180002a17  call    cs:__imp_GetCurrentThreadId
0x180002a1d  mov     eax, eax
0x180002a1f  xor     [rbp+var_10], rax
0x180002a23  call    cs:__imp_GetCurrentProcessId
0x180002a29  mov     eax, eax
0x180002a2b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002a2f  xor     [rbp+var_10], rax
0x180002a33  call    cs:__imp_QueryPerformanceCounter
0x180002a39  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a3c  lea     rcx, [rbp+var_10]
0x180002a40  shl     rax, 20h
0x180002a44  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002a48  xor     rax, [rbp+var_10]
0x180002a4c  xor     rax, rcx
0x180002a4f  mov     rcx, 0FFFFFFFFFFFFh
0x180002a59  and     rax, rcx
0x180002a5c  mov     rcx, 2B992DDFA233h
0x180002a66  cmp     rax, rbx
0x180002a69  cmovz   rax, rcx
0x180002a6d  mov     cs:__security_cookie, rax
0x180002a74  mov     rbx, [rsp+30h+arg_10]
0x180002a79  not     rax
0x180002a7c  mov     cs:__security_cookie_complement, rax
0x180002a83  add     rsp, 30h
0x180002a87  pop     rbp
0x180002a88  retn
```
