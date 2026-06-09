# __security_init_cookie

- ea: `0x18001d16c`
- end: `0x18001d249`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ce00`

## callees

- `0x18001d16c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d1f6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d1f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d1b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d1b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d1cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d1db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d1cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001d1db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d1a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d1a5`

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
0x18001d16c  mov     [rsp-8+arg_18], rbx
0x18001d171  push    rbp
0x18001d172  mov     rbp, rsp
0x18001d175  sub     rsp, 20h
0x18001d179  xor     eax, eax
0x18001d17b  mov     rbx, 2B992DDFA232h
0x18001d185  mov     [rbp+arg_0], rax
0x18001d189  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001d18d  mov     qword ptr [rbp+PerformanceCount], rax
0x18001d191  mov     rax, cs:__security_cookie
0x18001d198  cmp     rax, rbx
0x18001d19b  jnz     loc_18001D234
0x18001d1a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001d1a5  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d1ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001d1af  mov     [rbp+arg_0], rax
0x18001d1b3  call    cs:__imp_GetCurrentProcessId
0x18001d1b9  mov     eax, eax
0x18001d1bb  xor     [rbp+arg_0], rax
0x18001d1bf  call    cs:__imp_GetCurrentThreadId
0x18001d1c5  mov     eax, eax
0x18001d1c7  xor     [rbp+arg_0], rax
0x18001d1cb  call    cs:__imp_GetTickCount
0x18001d1d1  mov     eax, eax
0x18001d1d3  shl     rax, 18h
0x18001d1d7  xor     [rbp+arg_0], rax
0x18001d1db  call    cs:__imp_GetTickCount
0x18001d1e1  mov     eax, eax
0x18001d1e3  lea     rcx, [rbp+arg_0]
0x18001d1e7  xor     rax, [rbp+arg_0]
0x18001d1eb  xor     rax, rcx
0x18001d1ee  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001d1f2  mov     [rbp+arg_0], rax
0x18001d1f6  call    cs:__imp_QueryPerformanceCounter
0x18001d1fc  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001d1ff  mov     rcx, 0FFFFFFFFFFFFh
0x18001d209  shl     rax, 20h
0x18001d20d  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001d211  xor     rax, [rbp+arg_0]
0x18001d215  and     rax, rcx
0x18001d218  mov     rcx, rax
0x18001d21b  cmp     rax, rbx
0x18001d21e  jnz     short loc_18001D22D
0x18001d220  mov     rax, 2B992DDFA233h
0x18001d22a  mov     rcx, rax
0x18001d22d  mov     cs:__security_cookie, rcx
0x18001d234  mov     rbx, [rsp+20h+arg_18]
0x18001d239  not     rax
0x18001d23c  mov     cs:__security_cookie_complement, rax
0x18001d243  add     rsp, 20h
0x18001d247  pop     rbp
0x18001d248  retn
```
