# __security_init_cookie

- ea: `0x180006ee4`
- end: `0x180006fc1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006b30`

## callees

- `0x180006ee4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f37`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006f6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006f6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006f1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006f1d`

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
0x180006ee4  mov     [rsp-8+arg_18], rbx
0x180006ee9  push    rbp
0x180006eea  mov     rbp, rsp
0x180006eed  sub     rsp, 20h
0x180006ef1  xor     eax, eax
0x180006ef3  mov     rbx, 2B992DDFA232h
0x180006efd  mov     [rbp+arg_0], rax
0x180006f01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006f05  mov     qword ptr [rbp+PerformanceCount], rax
0x180006f09  mov     rax, cs:__security_cookie
0x180006f10  cmp     rax, rbx
0x180006f13  jnz     loc_180006FAC
0x180006f19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006f1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180006f23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180006f27  mov     [rbp+arg_0], rax
0x180006f2b  call    cs:__imp_GetCurrentProcessId
0x180006f31  mov     eax, eax
0x180006f33  xor     [rbp+arg_0], rax
0x180006f37  call    cs:__imp_GetCurrentThreadId
0x180006f3d  mov     eax, eax
0x180006f3f  xor     [rbp+arg_0], rax
0x180006f43  call    cs:__imp_GetTickCount
0x180006f49  mov     eax, eax
0x180006f4b  shl     rax, 18h
0x180006f4f  xor     [rbp+arg_0], rax
0x180006f53  call    cs:__imp_GetTickCount
0x180006f59  mov     eax, eax
0x180006f5b  lea     rcx, [rbp+arg_0]
0x180006f5f  xor     rax, [rbp+arg_0]
0x180006f63  xor     rax, rcx
0x180006f66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180006f6a  mov     [rbp+arg_0], rax
0x180006f6e  call    cs:__imp_QueryPerformanceCounter
0x180006f74  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006f77  mov     rcx, 0FFFFFFFFFFFFh
0x180006f81  shl     rax, 20h
0x180006f85  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006f89  xor     rax, [rbp+arg_0]
0x180006f8d  and     rax, rcx
0x180006f90  mov     rcx, rax
0x180006f93  cmp     rax, rbx
0x180006f96  jnz     short loc_180006FA5
0x180006f98  mov     rax, 2B992DDFA233h
0x180006fa2  mov     rcx, rax
0x180006fa5  mov     cs:__security_cookie, rcx
0x180006fac  mov     rbx, [rsp+20h+arg_18]
0x180006fb1  not     rax
0x180006fb4  mov     cs:__security_cookie_complement, rax
0x180006fbb  add     rsp, 20h
0x180006fbf  pop     rbp
0x180006fc0  retn
```
