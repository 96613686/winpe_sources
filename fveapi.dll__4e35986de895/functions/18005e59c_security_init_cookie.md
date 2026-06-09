# __security_init_cookie

- ea: `0x18005e59c`
- end: `0x18005e679`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005de20`

## callees

- `0x18005e59c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005e5e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005e5e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e5ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e5ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005e626`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005e626`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e5fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e60b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e5fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005e60b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e5d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e5d5`

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
0x18005e59c  mov     [rsp-8+arg_18], rbx
0x18005e5a1  push    rbp
0x18005e5a2  mov     rbp, rsp
0x18005e5a5  sub     rsp, 20h
0x18005e5a9  xor     eax, eax
0x18005e5ab  mov     rbx, 2B992DDFA232h
0x18005e5b5  mov     [rbp+arg_0], rax
0x18005e5b9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005e5bd  mov     qword ptr [rbp+PerformanceCount], rax
0x18005e5c1  mov     rax, cs:__security_cookie
0x18005e5c8  cmp     rax, rbx
0x18005e5cb  jnz     loc_18005E664
0x18005e5d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005e5d5  call    cs:__imp_GetSystemTimeAsFileTime
0x18005e5db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005e5df  mov     [rbp+arg_0], rax
0x18005e5e3  call    cs:__imp_GetCurrentProcessId
0x18005e5e9  mov     eax, eax
0x18005e5eb  xor     [rbp+arg_0], rax
0x18005e5ef  call    cs:__imp_GetCurrentThreadId
0x18005e5f5  mov     eax, eax
0x18005e5f7  xor     [rbp+arg_0], rax
0x18005e5fb  call    cs:__imp_GetTickCount
0x18005e601  mov     eax, eax
0x18005e603  shl     rax, 18h
0x18005e607  xor     [rbp+arg_0], rax
0x18005e60b  call    cs:__imp_GetTickCount
0x18005e611  mov     eax, eax
0x18005e613  lea     rcx, [rbp+arg_0]
0x18005e617  xor     rax, [rbp+arg_0]
0x18005e61b  xor     rax, rcx
0x18005e61e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005e622  mov     [rbp+arg_0], rax
0x18005e626  call    cs:__imp_QueryPerformanceCounter
0x18005e62c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005e62f  mov     rcx, 0FFFFFFFFFFFFh
0x18005e639  shl     rax, 20h
0x18005e63d  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005e641  xor     rax, [rbp+arg_0]
0x18005e645  and     rax, rcx
0x18005e648  mov     rcx, rax
0x18005e64b  cmp     rax, rbx
0x18005e64e  jnz     short loc_18005E65D
0x18005e650  mov     rax, 2B992DDFA233h
0x18005e65a  mov     rcx, rax
0x18005e65d  mov     cs:__security_cookie, rcx
0x18005e664  mov     rbx, [rsp+20h+arg_18]
0x18005e669  not     rax
0x18005e66c  mov     cs:__security_cookie_complement, rax
0x18005e673  add     rsp, 20h
0x18005e677  pop     rbp
0x18005e678  retn
```
