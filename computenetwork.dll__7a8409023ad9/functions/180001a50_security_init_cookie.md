# __security_init_cookie

- ea: `0x180001a50`
- end: `0x180001b05`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015b0`

## callees

- `0x180001a50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a93`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aaf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a85`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a85`

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
0x180001a50  mov     [rsp-8+arg_10], rbx
0x180001a55  push    rbp
0x180001a56  mov     rbp, rsp
0x180001a59  sub     rsp, 30h
0x180001a5d  mov     rax, cs:__security_cookie
0x180001a64  mov     rbx, 2B992DDFA232h
0x180001a6e  cmp     rax, rbx
0x180001a71  jnz     short loc_180001AF0
0x180001a73  xor     eax, eax
0x180001a75  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a79  mov     [rbp+var_10], rax
0x180001a7d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a81  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a85  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a8b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a8f  mov     [rbp+var_10], rax
0x180001a93  call    cs:__imp_GetCurrentThreadId
0x180001a99  mov     eax, eax
0x180001a9b  xor     [rbp+var_10], rax
0x180001a9f  call    cs:__imp_GetCurrentProcessId
0x180001aa5  mov     eax, eax
0x180001aa7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001aab  xor     [rbp+var_10], rax
0x180001aaf  call    cs:__imp_QueryPerformanceCounter
0x180001ab5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ab8  lea     rcx, [rbp+var_10]
0x180001abc  shl     rax, 20h
0x180001ac0  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ac4  xor     rax, [rbp+var_10]
0x180001ac8  xor     rax, rcx
0x180001acb  mov     rcx, 0FFFFFFFFFFFFh
0x180001ad5  and     rax, rcx
0x180001ad8  mov     rcx, 2B992DDFA233h
0x180001ae2  cmp     rax, rbx
0x180001ae5  cmovz   rax, rcx
0x180001ae9  mov     cs:__security_cookie, rax
0x180001af0  mov     rbx, [rsp+30h+arg_10]
0x180001af5  not     rax
0x180001af8  mov     cs:__security_cookie_complement, rax
0x180001aff  add     rsp, 30h
0x180001b03  pop     rbp
0x180001b04  retn
```
