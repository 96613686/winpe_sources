# __security_init_cookie

- ea: `0x18000198c`
- end: `0x180001a41`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x18000198c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019eb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019c1`

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
0x18000198c  mov     [rsp-8+arg_10], rbx
0x180001991  push    rbp
0x180001992  mov     rbp, rsp
0x180001995  sub     rsp, 30h
0x180001999  mov     rax, cs:__security_cookie
0x1800019a0  mov     rbx, 2B992DDFA232h
0x1800019aa  cmp     rax, rbx
0x1800019ad  jnz     short loc_180001A2C
0x1800019af  xor     eax, eax
0x1800019b1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019b5  mov     [rbp+var_10], rax
0x1800019b9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019bd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019c1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019c7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019cb  mov     [rbp+var_10], rax
0x1800019cf  call    cs:__imp_GetCurrentThreadId
0x1800019d5  mov     eax, eax
0x1800019d7  xor     [rbp+var_10], rax
0x1800019db  call    cs:__imp_GetCurrentProcessId
0x1800019e1  mov     eax, eax
0x1800019e3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800019e7  xor     [rbp+var_10], rax
0x1800019eb  call    cs:__imp_QueryPerformanceCounter
0x1800019f1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019f4  lea     rcx, [rbp+var_10]
0x1800019f8  shl     rax, 20h
0x1800019fc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a00  xor     rax, [rbp+var_10]
0x180001a04  xor     rax, rcx
0x180001a07  mov     rcx, 0FFFFFFFFFFFFh
0x180001a11  and     rax, rcx
0x180001a14  mov     rcx, 2B992DDFA233h
0x180001a1e  cmp     rax, rbx
0x180001a21  cmovz   rax, rcx
0x180001a25  mov     cs:__security_cookie, rax
0x180001a2c  mov     rbx, [rsp+30h+arg_10]
0x180001a31  not     rax
0x180001a34  mov     cs:__security_cookie_complement, rax
0x180001a3b  add     rsp, 30h
0x180001a3f  pop     rbp
0x180001a40  retn
```
