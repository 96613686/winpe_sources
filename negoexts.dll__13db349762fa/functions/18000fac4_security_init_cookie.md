# __security_init_cookie

- ea: `0x18000fac4`
- end: `0x18000fba1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f490`

## callees

- `0x18000fac4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fb17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fb0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fb0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fb4e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fb4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fafd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fafd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fb23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fb33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fb23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fb33`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18000fac4  mov     [rsp-8+arg_18], rbx
0x18000fac9  push    rbp
0x18000faca  mov     rbp, rsp
0x18000facd  sub     rsp, 20h
0x18000fad1  xor     eax, eax
0x18000fad3  mov     rbx, 2B992DDFA232h
0x18000fadd  mov     [rbp+arg_0], rax
0x18000fae1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000fae5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000fae9  mov     rax, cs:__security_cookie
0x18000faf0  cmp     rax, rbx
0x18000faf3  jnz     loc_18000FB8C
0x18000faf9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fafd  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fb03  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000fb07  mov     [rbp+arg_0], rax
0x18000fb0b  call    cs:__imp_GetCurrentProcessId
0x18000fb11  mov     eax, eax
0x18000fb13  xor     [rbp+arg_0], rax
0x18000fb17  call    cs:__imp_GetCurrentThreadId
0x18000fb1d  mov     eax, eax
0x18000fb1f  xor     [rbp+arg_0], rax
0x18000fb23  call    cs:__imp_GetTickCount
0x18000fb29  mov     eax, eax
0x18000fb2b  shl     rax, 18h
0x18000fb2f  xor     [rbp+arg_0], rax
0x18000fb33  call    cs:__imp_GetTickCount
0x18000fb39  mov     eax, eax
0x18000fb3b  lea     rcx, [rbp+arg_0]
0x18000fb3f  xor     rax, [rbp+arg_0]
0x18000fb43  xor     rax, rcx
0x18000fb46  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000fb4a  mov     [rbp+arg_0], rax
0x18000fb4e  call    cs:__imp_QueryPerformanceCounter
0x18000fb54  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000fb57  mov     rcx, 0FFFFFFFFFFFFh
0x18000fb61  shl     rax, 20h
0x18000fb65  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000fb69  xor     rax, [rbp+arg_0]
0x18000fb6d  and     rax, rcx
0x18000fb70  mov     rcx, rax
0x18000fb73  cmp     rax, rbx
0x18000fb76  jnz     short loc_18000FB85
0x18000fb78  mov     rax, 2B992DDFA233h
0x18000fb82  mov     rcx, rax
0x18000fb85  mov     cs:__security_cookie, rcx
0x18000fb8c  mov     rbx, [rsp+20h+arg_18]
0x18000fb91  not     rax
0x18000fb94  mov     cs:__security_cookie_complement, rax
0x18000fb9b  add     rsp, 20h
0x18000fb9f  pop     rbp
0x18000fba0  retn
```
