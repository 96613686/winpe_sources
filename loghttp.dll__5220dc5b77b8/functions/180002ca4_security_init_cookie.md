# __security_init_cookie

- ea: `0x180002ca4`
- end: `0x180002d81`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002870`

## callees

- `0x180002ca4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002d03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002d13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002d03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002d13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002cdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002cdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002cf7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002d2e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002d2e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180002ca4  mov     [rsp-8+arg_18], rbx
0x180002ca9  push    rbp
0x180002caa  mov     rbp, rsp
0x180002cad  sub     rsp, 20h
0x180002cb1  xor     eax, eax
0x180002cb3  mov     rbx, 2B992DDFA232h
0x180002cbd  mov     [rbp+arg_0], rax
0x180002cc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002cc5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002cc9  mov     rax, cs:__security_cookie
0x180002cd0  cmp     rax, rbx
0x180002cd3  jnz     loc_180002D6C
0x180002cd9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002cdd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ce3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002ce7  mov     [rbp+arg_0], rax
0x180002ceb  call    cs:__imp_GetCurrentProcessId
0x180002cf1  mov     eax, eax
0x180002cf3  xor     [rbp+arg_0], rax
0x180002cf7  call    cs:__imp_GetCurrentThreadId
0x180002cfd  mov     eax, eax
0x180002cff  xor     [rbp+arg_0], rax
0x180002d03  call    cs:__imp_GetTickCount
0x180002d09  mov     eax, eax
0x180002d0b  shl     rax, 18h
0x180002d0f  xor     [rbp+arg_0], rax
0x180002d13  call    cs:__imp_GetTickCount
0x180002d19  mov     eax, eax
0x180002d1b  lea     rcx, [rbp+arg_0]
0x180002d1f  xor     rax, [rbp+arg_0]
0x180002d23  xor     rax, rcx
0x180002d26  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002d2a  mov     [rbp+arg_0], rax
0x180002d2e  call    cs:__imp_QueryPerformanceCounter
0x180002d34  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002d37  mov     rcx, 0FFFFFFFFFFFFh
0x180002d41  shl     rax, 20h
0x180002d45  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002d49  xor     rax, [rbp+arg_0]
0x180002d4d  and     rax, rcx
0x180002d50  mov     rcx, rax
0x180002d53  cmp     rax, rbx
0x180002d56  jnz     short loc_180002D65
0x180002d58  mov     rax, 2B992DDFA233h
0x180002d62  mov     rcx, rax
0x180002d65  mov     cs:__security_cookie, rcx
0x180002d6c  mov     rbx, [rsp+20h+arg_18]
0x180002d71  not     rax
0x180002d74  mov     cs:__security_cookie_complement, rax
0x180002d7b  add     rsp, 20h
0x180002d7f  pop     rbp
0x180002d80  retn
```
