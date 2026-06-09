# __security_init_cookie

- ea: `0x18041c214`
- end: `0x18041c2f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18041b7e0`

## callees

- `0x18041c214`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18041c25b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18041c25b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18041c267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18041c267`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18041c273`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18041c283`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18041c273`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18041c283`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18041c24d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18041c24d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18041c29e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18041c29e`

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
0x18041c214  mov     [rsp-8+arg_18], rbx
0x18041c219  push    rbp
0x18041c21a  mov     rbp, rsp
0x18041c21d  sub     rsp, 20h
0x18041c221  xor     eax, eax
0x18041c223  mov     rbx, 2B992DDFA232h
0x18041c22d  mov     [rbp+arg_0], rax
0x18041c231  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18041c235  mov     qword ptr [rbp+PerformanceCount], rax
0x18041c239  mov     rax, cs:__security_cookie
0x18041c240  cmp     rax, rbx
0x18041c243  jnz     loc_18041C2DC
0x18041c249  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18041c24d  call    cs:__imp_GetSystemTimeAsFileTime
0x18041c253  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18041c257  mov     [rbp+arg_0], rax
0x18041c25b  call    cs:__imp_GetCurrentProcessId
0x18041c261  mov     eax, eax
0x18041c263  xor     [rbp+arg_0], rax
0x18041c267  call    cs:__imp_GetCurrentThreadId
0x18041c26d  mov     eax, eax
0x18041c26f  xor     [rbp+arg_0], rax
0x18041c273  call    cs:__imp_GetTickCount
0x18041c279  mov     eax, eax
0x18041c27b  shl     rax, 18h
0x18041c27f  xor     [rbp+arg_0], rax
0x18041c283  call    cs:__imp_GetTickCount
0x18041c289  mov     eax, eax
0x18041c28b  lea     rcx, [rbp+arg_0]
0x18041c28f  xor     rax, [rbp+arg_0]
0x18041c293  xor     rax, rcx
0x18041c296  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18041c29a  mov     [rbp+arg_0], rax
0x18041c29e  call    cs:__imp_QueryPerformanceCounter
0x18041c2a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18041c2a7  mov     rcx, 0FFFFFFFFFFFFh
0x18041c2b1  shl     rax, 20h
0x18041c2b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18041c2b9  xor     rax, [rbp+arg_0]
0x18041c2bd  and     rax, rcx
0x18041c2c0  mov     rcx, rax
0x18041c2c3  cmp     rax, rbx
0x18041c2c6  jnz     short loc_18041C2D5
0x18041c2c8  mov     rax, 2B992DDFA233h
0x18041c2d2  mov     rcx, rax
0x18041c2d5  mov     cs:__security_cookie, rcx
0x18041c2dc  mov     rbx, [rsp+20h+arg_18]
0x18041c2e1  not     rax
0x18041c2e4  mov     cs:__security_cookie_complement, rax
0x18041c2eb  add     rsp, 20h
0x18041c2ef  pop     rbp
0x18041c2f0  retn
```
