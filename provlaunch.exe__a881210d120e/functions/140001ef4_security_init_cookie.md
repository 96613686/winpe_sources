# __security_init_cookie

- ea: `0x140001ef4`
- end: `0x140001fd1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001b80`

## callees

- `0x140001ef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f47`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001f7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001f7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001f63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001f63`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001f2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001f2d`

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
0x140001ef4  mov     [rsp-8+arg_18], rbx
0x140001ef9  push    rbp
0x140001efa  mov     rbp, rsp
0x140001efd  sub     rsp, 20h
0x140001f01  xor     eax, eax
0x140001f03  mov     rbx, 2B992DDFA232h
0x140001f0d  mov     [rbp+arg_0], rax
0x140001f11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001f15  mov     qword ptr [rbp+PerformanceCount], rax
0x140001f19  mov     rax, cs:__security_cookie
0x140001f20  cmp     rax, rbx
0x140001f23  jnz     loc_140001FBC
0x140001f29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001f2d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001f33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001f37  mov     [rbp+arg_0], rax
0x140001f3b  call    cs:__imp_GetCurrentProcessId
0x140001f41  mov     eax, eax
0x140001f43  xor     [rbp+arg_0], rax
0x140001f47  call    cs:__imp_GetCurrentThreadId
0x140001f4d  mov     eax, eax
0x140001f4f  xor     [rbp+arg_0], rax
0x140001f53  call    cs:__imp_GetTickCount
0x140001f59  mov     eax, eax
0x140001f5b  shl     rax, 18h
0x140001f5f  xor     [rbp+arg_0], rax
0x140001f63  call    cs:__imp_GetTickCount
0x140001f69  mov     eax, eax
0x140001f6b  lea     rcx, [rbp+arg_0]
0x140001f6f  xor     rax, [rbp+arg_0]
0x140001f73  xor     rax, rcx
0x140001f76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001f7a  mov     [rbp+arg_0], rax
0x140001f7e  call    cs:__imp_QueryPerformanceCounter
0x140001f84  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001f87  mov     rcx, 0FFFFFFFFFFFFh
0x140001f91  shl     rax, 20h
0x140001f95  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001f99  xor     rax, [rbp+arg_0]
0x140001f9d  and     rax, rcx
0x140001fa0  mov     rcx, rax
0x140001fa3  cmp     rax, rbx
0x140001fa6  jnz     short loc_140001FB5
0x140001fa8  mov     rax, 2B992DDFA233h
0x140001fb2  mov     rcx, rax
0x140001fb5  mov     cs:__security_cookie, rcx
0x140001fbc  mov     rbx, [rsp+20h+arg_18]
0x140001fc1  not     rax
0x140001fc4  mov     cs:__security_cookie_complement, rax
0x140001fcb  add     rsp, 20h
0x140001fcf  pop     rbp
0x140001fd0  retn
```
