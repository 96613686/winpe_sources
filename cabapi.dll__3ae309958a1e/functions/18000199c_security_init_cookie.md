# __security_init_cookie

- ea: `0x18000199c`
- end: `0x180001a51`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014f0`

## callees

- `0x18000199c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019eb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019d1`

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
0x18000199c  mov     [rsp-8+arg_10], rbx
0x1800019a1  push    rbp
0x1800019a2  mov     rbp, rsp
0x1800019a5  sub     rsp, 30h
0x1800019a9  mov     rax, cs:__security_cookie
0x1800019b0  mov     rbx, 2B992DDFA232h
0x1800019ba  cmp     rax, rbx
0x1800019bd  jnz     short loc_180001A3C
0x1800019bf  xor     eax, eax
0x1800019c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019c5  mov     [rbp+var_10], rax
0x1800019c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019db  mov     [rbp+var_10], rax
0x1800019df  call    cs:__imp_GetCurrentThreadId
0x1800019e5  mov     eax, eax
0x1800019e7  xor     [rbp+var_10], rax
0x1800019eb  call    cs:__imp_GetCurrentProcessId
0x1800019f1  mov     eax, eax
0x1800019f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800019f7  xor     [rbp+var_10], rax
0x1800019fb  call    cs:__imp_QueryPerformanceCounter
0x180001a01  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a04  lea     rcx, [rbp+var_10]
0x180001a08  shl     rax, 20h
0x180001a0c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a10  xor     rax, [rbp+var_10]
0x180001a14  xor     rax, rcx
0x180001a17  mov     rcx, 0FFFFFFFFFFFFh
0x180001a21  and     rax, rcx
0x180001a24  mov     rcx, 2B992DDFA233h
0x180001a2e  cmp     rax, rbx
0x180001a31  cmovz   rax, rcx
0x180001a35  mov     cs:__security_cookie, rax
0x180001a3c  mov     rbx, [rsp+30h+arg_10]
0x180001a41  not     rax
0x180001a44  mov     cs:__security_cookie_complement, rax
0x180001a4b  add     rsp, 30h
0x180001a4f  pop     rbp
0x180001a50  retn
```
