# __security_init_cookie

- ea: `0x180001a64`
- end: `0x180001b41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001420`

## callees

- `0x180001a64`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ac3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ac3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ad3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001aab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001aab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ab7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aee`

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
0x180001a64  mov     [rsp-8+arg_18], rbx
0x180001a69  push    rbp
0x180001a6a  mov     rbp, rsp
0x180001a6d  sub     rsp, 20h
0x180001a71  xor     eax, eax
0x180001a73  mov     rbx, 2B992DDFA232h
0x180001a7d  mov     [rbp+arg_0], rax
0x180001a81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a85  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a89  mov     rax, cs:__security_cookie
0x180001a90  cmp     rax, rbx
0x180001a93  jnz     loc_180001B2C
0x180001a99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001aa3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001aa7  mov     [rbp+arg_0], rax
0x180001aab  call    cs:__imp_GetCurrentProcessId
0x180001ab1  mov     eax, eax
0x180001ab3  xor     [rbp+arg_0], rax
0x180001ab7  call    cs:__imp_GetCurrentThreadId
0x180001abd  mov     eax, eax
0x180001abf  xor     [rbp+arg_0], rax
0x180001ac3  call    cs:__imp_GetTickCount
0x180001ac9  mov     eax, eax
0x180001acb  shl     rax, 18h
0x180001acf  xor     [rbp+arg_0], rax
0x180001ad3  call    cs:__imp_GetTickCount
0x180001ad9  mov     eax, eax
0x180001adb  lea     rcx, [rbp+arg_0]
0x180001adf  xor     rax, [rbp+arg_0]
0x180001ae3  xor     rax, rcx
0x180001ae6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001aea  mov     [rbp+arg_0], rax
0x180001aee  call    cs:__imp_QueryPerformanceCounter
0x180001af4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001af7  mov     rcx, 0FFFFFFFFFFFFh
0x180001b01  shl     rax, 20h
0x180001b05  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b09  xor     rax, [rbp+arg_0]
0x180001b0d  and     rax, rcx
0x180001b10  mov     rcx, rax
0x180001b13  cmp     rax, rbx
0x180001b16  jnz     short loc_180001B25
0x180001b18  mov     rax, 2B992DDFA233h
0x180001b22  mov     rcx, rax
0x180001b25  mov     cs:__security_cookie, rcx
0x180001b2c  mov     rbx, [rsp+20h+arg_18]
0x180001b31  not     rax
0x180001b34  mov     cs:__security_cookie_complement, rax
0x180001b3b  add     rsp, 20h
0x180001b3f  pop     rbp
0x180001b40  retn
```
