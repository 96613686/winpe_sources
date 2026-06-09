# __security_init_cookie

- ea: `0x18000c1d4`
- end: `0x18000c2b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b9d0`

## callees

- `0x18000c1d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c21b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c21b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c20d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c20d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c233`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c243`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c233`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c243`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c25e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c25e`

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
0x18000c1d4  mov     [rsp-8+arg_18], rbx
0x18000c1d9  push    rbp
0x18000c1da  mov     rbp, rsp
0x18000c1dd  sub     rsp, 20h
0x18000c1e1  xor     eax, eax
0x18000c1e3  mov     rbx, 2B992DDFA232h
0x18000c1ed  mov     [rbp+arg_0], rax
0x18000c1f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000c1f5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000c1f9  mov     rax, cs:__security_cookie
0x18000c200  cmp     rax, rbx
0x18000c203  jnz     loc_18000C29C
0x18000c209  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000c20d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c213  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000c217  mov     [rbp+arg_0], rax
0x18000c21b  call    cs:__imp_GetCurrentProcessId
0x18000c221  mov     eax, eax
0x18000c223  xor     [rbp+arg_0], rax
0x18000c227  call    cs:__imp_GetCurrentThreadId
0x18000c22d  mov     eax, eax
0x18000c22f  xor     [rbp+arg_0], rax
0x18000c233  call    cs:__imp_GetTickCount
0x18000c239  mov     eax, eax
0x18000c23b  shl     rax, 18h
0x18000c23f  xor     [rbp+arg_0], rax
0x18000c243  call    cs:__imp_GetTickCount
0x18000c249  mov     eax, eax
0x18000c24b  lea     rcx, [rbp+arg_0]
0x18000c24f  xor     rax, [rbp+arg_0]
0x18000c253  xor     rax, rcx
0x18000c256  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000c25a  mov     [rbp+arg_0], rax
0x18000c25e  call    cs:__imp_QueryPerformanceCounter
0x18000c264  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000c267  mov     rcx, 0FFFFFFFFFFFFh
0x18000c271  shl     rax, 20h
0x18000c275  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000c279  xor     rax, [rbp+arg_0]
0x18000c27d  and     rax, rcx
0x18000c280  mov     rcx, rax
0x18000c283  cmp     rax, rbx
0x18000c286  jnz     short loc_18000C295
0x18000c288  mov     rax, 2B992DDFA233h
0x18000c292  mov     rcx, rax
0x18000c295  mov     cs:__security_cookie, rcx
0x18000c29c  mov     rbx, [rsp+20h+arg_18]
0x18000c2a1  not     rax
0x18000c2a4  mov     cs:__security_cookie_complement, rax
0x18000c2ab  add     rsp, 20h
0x18000c2af  pop     rbp
0x18000c2b0  retn
```
