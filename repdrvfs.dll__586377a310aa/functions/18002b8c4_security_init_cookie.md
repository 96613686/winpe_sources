# __security_init_cookie

- ea: `0x18002b8c4`
- end: `0x18002b9a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002af50`

## callees

- `0x18002b8c4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b923`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b933`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b923`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b933`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b8fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b8fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b917`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b917`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b90b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002b90b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002b94e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002b94e`

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
0x18002b8c4  mov     [rsp-8+arg_18], rbx
0x18002b8c9  push    rbp
0x18002b8ca  mov     rbp, rsp
0x18002b8cd  sub     rsp, 20h
0x18002b8d1  xor     eax, eax
0x18002b8d3  mov     rbx, 2B992DDFA232h
0x18002b8dd  mov     [rbp+arg_0], rax
0x18002b8e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002b8e5  mov     qword ptr [rbp+PerformanceCount], rax
0x18002b8e9  mov     rax, cs:__security_cookie
0x18002b8f0  cmp     rax, rbx
0x18002b8f3  jnz     loc_18002B98C
0x18002b8f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002b8fd  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b903  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002b907  mov     [rbp+arg_0], rax
0x18002b90b  call    cs:__imp_GetCurrentProcessId
0x18002b911  mov     eax, eax
0x18002b913  xor     [rbp+arg_0], rax
0x18002b917  call    cs:__imp_GetCurrentThreadId
0x18002b91d  mov     eax, eax
0x18002b91f  xor     [rbp+arg_0], rax
0x18002b923  call    cs:__imp_GetTickCount
0x18002b929  mov     eax, eax
0x18002b92b  shl     rax, 18h
0x18002b92f  xor     [rbp+arg_0], rax
0x18002b933  call    cs:__imp_GetTickCount
0x18002b939  mov     eax, eax
0x18002b93b  lea     rcx, [rbp+arg_0]
0x18002b93f  xor     rax, [rbp+arg_0]
0x18002b943  xor     rax, rcx
0x18002b946  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002b94a  mov     [rbp+arg_0], rax
0x18002b94e  call    cs:__imp_QueryPerformanceCounter
0x18002b954  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002b957  mov     rcx, 0FFFFFFFFFFFFh
0x18002b961  shl     rax, 20h
0x18002b965  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002b969  xor     rax, [rbp+arg_0]
0x18002b96d  and     rax, rcx
0x18002b970  mov     rcx, rax
0x18002b973  cmp     rax, rbx
0x18002b976  jnz     short loc_18002B985
0x18002b978  mov     rax, 2B992DDFA233h
0x18002b982  mov     rcx, rax
0x18002b985  mov     cs:__security_cookie, rcx
0x18002b98c  mov     rbx, [rsp+20h+arg_18]
0x18002b991  not     rax
0x18002b994  mov     cs:__security_cookie_complement, rax
0x18002b99b  add     rsp, 20h
0x18002b99f  pop     rbp
0x18002b9a0  retn
```
