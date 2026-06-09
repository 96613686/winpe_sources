# __security_init_cookie

- ea: `0x180001bec`
- end: `0x180001ca1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001720`

## callees

- `0x180001bec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001c3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001c3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001c2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001c2f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c4b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001c21`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001c21`

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
0x180001bec  mov     [rsp-8+arg_10], rbx
0x180001bf1  push    rbp
0x180001bf2  mov     rbp, rsp
0x180001bf5  sub     rsp, 30h
0x180001bf9  mov     rax, cs:__security_cookie
0x180001c00  mov     rbx, 2B992DDFA232h
0x180001c0a  cmp     rax, rbx
0x180001c0d  jnz     short loc_180001C8C
0x180001c0f  xor     eax, eax
0x180001c11  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001c15  mov     [rbp+var_10], rax
0x180001c19  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c1d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c21  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c27  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001c2b  mov     [rbp+var_10], rax
0x180001c2f  call    cs:__imp_GetCurrentThreadId
0x180001c35  mov     eax, eax
0x180001c37  xor     [rbp+var_10], rax
0x180001c3b  call    cs:__imp_GetCurrentProcessId
0x180001c41  mov     eax, eax
0x180001c43  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c47  xor     [rbp+var_10], rax
0x180001c4b  call    cs:__imp_QueryPerformanceCounter
0x180001c51  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c54  lea     rcx, [rbp+var_10]
0x180001c58  shl     rax, 20h
0x180001c5c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c60  xor     rax, [rbp+var_10]
0x180001c64  xor     rax, rcx
0x180001c67  mov     rcx, 0FFFFFFFFFFFFh
0x180001c71  and     rax, rcx
0x180001c74  mov     rcx, 2B992DDFA233h
0x180001c7e  cmp     rax, rbx
0x180001c81  cmovz   rax, rcx
0x180001c85  mov     cs:__security_cookie, rax
0x180001c8c  mov     rbx, [rsp+30h+arg_10]
0x180001c91  not     rax
0x180001c94  mov     cs:__security_cookie_complement, rax
0x180001c9b  add     rsp, 30h
0x180001c9f  pop     rbp
0x180001ca0  retn
```
