# __security_init_cookie

- ea: `0x180001b24`
- end: `0x180001c01`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001380`

## callees

- `0x180001b24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001bae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001bae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b5d`

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
0x180001b24  mov     [rsp-8+arg_18], rbx
0x180001b29  push    rbp
0x180001b2a  mov     rbp, rsp
0x180001b2d  sub     rsp, 20h
0x180001b31  xor     eax, eax
0x180001b33  mov     rbx, 2B992DDFA232h
0x180001b3d  mov     [rbp+arg_0], rax
0x180001b41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001b45  mov     qword ptr [rbp+PerformanceCount], rax
0x180001b49  mov     rax, cs:__security_cookie
0x180001b50  cmp     rax, rbx
0x180001b53  jnz     loc_180001BEC
0x180001b59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b67  mov     [rbp+arg_0], rax
0x180001b6b  call    cs:__imp_GetCurrentProcessId
0x180001b71  mov     eax, eax
0x180001b73  xor     [rbp+arg_0], rax
0x180001b77  call    cs:__imp_GetCurrentThreadId
0x180001b7d  mov     eax, eax
0x180001b7f  xor     [rbp+arg_0], rax
0x180001b83  call    cs:__imp_GetTickCount
0x180001b89  mov     eax, eax
0x180001b8b  shl     rax, 18h
0x180001b8f  xor     [rbp+arg_0], rax
0x180001b93  call    cs:__imp_GetTickCount
0x180001b99  mov     eax, eax
0x180001b9b  lea     rcx, [rbp+arg_0]
0x180001b9f  xor     rax, [rbp+arg_0]
0x180001ba3  xor     rax, rcx
0x180001ba6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001baa  mov     [rbp+arg_0], rax
0x180001bae  call    cs:__imp_QueryPerformanceCounter
0x180001bb4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001bb7  mov     rcx, 0FFFFFFFFFFFFh
0x180001bc1  shl     rax, 20h
0x180001bc5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001bc9  xor     rax, [rbp+arg_0]
0x180001bcd  and     rax, rcx
0x180001bd0  mov     rcx, rax
0x180001bd3  cmp     rax, rbx
0x180001bd6  jnz     short loc_180001BE5
0x180001bd8  mov     rax, 2B992DDFA233h
0x180001be2  mov     rcx, rax
0x180001be5  mov     cs:__security_cookie, rcx
0x180001bec  mov     rbx, [rsp+20h+arg_18]
0x180001bf1  not     rax
0x180001bf4  mov     cs:__security_cookie_complement, rax
0x180001bfb  add     rsp, 20h
0x180001bff  pop     rbp
0x180001c00  retn
```
