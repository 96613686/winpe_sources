# __security_init_cookie

- ea: `0x18000fa64`
- end: `0x18000fb41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f1b0`

## callees

- `0x18000fa64`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fac3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fac3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fa9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fa9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000faab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000faab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fab7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000faee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000faee`

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
0x18000fa64  mov     [rsp-8+arg_18], rbx
0x18000fa69  push    rbp
0x18000fa6a  mov     rbp, rsp
0x18000fa6d  sub     rsp, 20h
0x18000fa71  xor     eax, eax
0x18000fa73  mov     rbx, 2B992DDFA232h
0x18000fa7d  mov     [rbp+arg_0], rax
0x18000fa81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000fa85  mov     qword ptr [rbp+PerformanceCount], rax
0x18000fa89  mov     rax, cs:__security_cookie
0x18000fa90  cmp     rax, rbx
0x18000fa93  jnz     loc_18000FB2C
0x18000fa99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fa9d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000faa3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000faa7  mov     [rbp+arg_0], rax
0x18000faab  call    cs:__imp_GetCurrentProcessId
0x18000fab1  mov     eax, eax
0x18000fab3  xor     [rbp+arg_0], rax
0x18000fab7  call    cs:__imp_GetCurrentThreadId
0x18000fabd  mov     eax, eax
0x18000fabf  xor     [rbp+arg_0], rax
0x18000fac3  call    cs:__imp_GetTickCount
0x18000fac9  mov     eax, eax
0x18000facb  shl     rax, 18h
0x18000facf  xor     [rbp+arg_0], rax
0x18000fad3  call    cs:__imp_GetTickCount
0x18000fad9  mov     eax, eax
0x18000fadb  lea     rcx, [rbp+arg_0]
0x18000fadf  xor     rax, [rbp+arg_0]
0x18000fae3  xor     rax, rcx
0x18000fae6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000faea  mov     [rbp+arg_0], rax
0x18000faee  call    cs:__imp_QueryPerformanceCounter
0x18000faf4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000faf7  mov     rcx, 0FFFFFFFFFFFFh
0x18000fb01  shl     rax, 20h
0x18000fb05  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000fb09  xor     rax, [rbp+arg_0]
0x18000fb0d  and     rax, rcx
0x18000fb10  mov     rcx, rax
0x18000fb13  cmp     rax, rbx
0x18000fb16  jnz     short loc_18000FB25
0x18000fb18  mov     rax, 2B992DDFA233h
0x18000fb22  mov     rcx, rax
0x18000fb25  mov     cs:__security_cookie, rcx
0x18000fb2c  mov     rbx, [rsp+20h+arg_18]
0x18000fb31  not     rax
0x18000fb34  mov     cs:__security_cookie_complement, rax
0x18000fb3b  add     rsp, 20h
0x18000fb3f  pop     rbp
0x18000fb40  retn
```
