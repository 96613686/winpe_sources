# __security_init_cookie

- ea: `0x180002f14`
- end: `0x180002ff1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ba0`

## callees

- `0x180002f14`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002f73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002f73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002f83`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f9e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f9e`

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
0x180002f14  mov     [rsp-8+arg_18], rbx
0x180002f19  push    rbp
0x180002f1a  mov     rbp, rsp
0x180002f1d  sub     rsp, 20h
0x180002f21  xor     eax, eax
0x180002f23  mov     rbx, 2B992DDFA232h
0x180002f2d  mov     [rbp+arg_0], rax
0x180002f31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002f35  mov     qword ptr [rbp+PerformanceCount], rax
0x180002f39  mov     rax, cs:__security_cookie
0x180002f40  cmp     rax, rbx
0x180002f43  jnz     loc_180002FDC
0x180002f49  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002f4d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002f53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002f57  mov     [rbp+arg_0], rax
0x180002f5b  call    cs:__imp_GetCurrentProcessId
0x180002f61  mov     eax, eax
0x180002f63  xor     [rbp+arg_0], rax
0x180002f67  call    cs:__imp_GetCurrentThreadId
0x180002f6d  mov     eax, eax
0x180002f6f  xor     [rbp+arg_0], rax
0x180002f73  call    cs:__imp_GetTickCount
0x180002f79  mov     eax, eax
0x180002f7b  shl     rax, 18h
0x180002f7f  xor     [rbp+arg_0], rax
0x180002f83  call    cs:__imp_GetTickCount
0x180002f89  mov     eax, eax
0x180002f8b  lea     rcx, [rbp+arg_0]
0x180002f8f  xor     rax, [rbp+arg_0]
0x180002f93  xor     rax, rcx
0x180002f96  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002f9a  mov     [rbp+arg_0], rax
0x180002f9e  call    cs:__imp_QueryPerformanceCounter
0x180002fa4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002fa7  mov     rcx, 0FFFFFFFFFFFFh
0x180002fb1  shl     rax, 20h
0x180002fb5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002fb9  xor     rax, [rbp+arg_0]
0x180002fbd  and     rax, rcx
0x180002fc0  mov     rcx, rax
0x180002fc3  cmp     rax, rbx
0x180002fc6  jnz     short loc_180002FD5
0x180002fc8  mov     rax, 2B992DDFA233h
0x180002fd2  mov     rcx, rax
0x180002fd5  mov     cs:__security_cookie, rcx
0x180002fdc  mov     rbx, [rsp+20h+arg_18]
0x180002fe1  not     rax
0x180002fe4  mov     cs:__security_cookie_complement, rax
0x180002feb  add     rsp, 20h
0x180002fef  pop     rbp
0x180002ff0  retn
```
