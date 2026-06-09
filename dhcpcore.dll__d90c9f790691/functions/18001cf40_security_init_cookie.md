# __security_init_cookie

- ea: `0x18001cf40`
- end: `0x18001cff5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cea0`

## callees

- `0x18001cf40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cf8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001cf8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cf83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cf83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001cf9f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001cf9f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cf75`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cf75`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18001cf40  mov     [rsp-8+arg_10], rbx
0x18001cf45  push    rbp
0x18001cf46  mov     rbp, rsp
0x18001cf49  sub     rsp, 30h
0x18001cf4d  mov     rax, cs:__security_cookie
0x18001cf54  mov     rbx, 2B992DDFA232h
0x18001cf5e  cmp     rax, rbx
0x18001cf61  jnz     short loc_18001CFE0
0x18001cf63  xor     eax, eax
0x18001cf65  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001cf69  mov     [rbp+var_10], rax
0x18001cf6d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001cf71  mov     qword ptr [rbp+PerformanceCount], rax
0x18001cf75  call    cs:__imp_GetSystemTimeAsFileTime
0x18001cf7b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001cf7f  mov     [rbp+var_10], rax
0x18001cf83  call    cs:__imp_GetCurrentThreadId
0x18001cf89  mov     eax, eax
0x18001cf8b  xor     [rbp+var_10], rax
0x18001cf8f  call    cs:__imp_GetCurrentProcessId
0x18001cf95  mov     eax, eax
0x18001cf97  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001cf9b  xor     [rbp+var_10], rax
0x18001cf9f  call    cs:__imp_QueryPerformanceCounter
0x18001cfa5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001cfa8  lea     rcx, [rbp+var_10]
0x18001cfac  shl     rax, 20h
0x18001cfb0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001cfb4  xor     rax, [rbp+var_10]
0x18001cfb8  xor     rax, rcx
0x18001cfbb  mov     rcx, 0FFFFFFFFFFFFh
0x18001cfc5  and     rax, rcx
0x18001cfc8  mov     rcx, 2B992DDFA233h
0x18001cfd2  cmp     rax, rbx
0x18001cfd5  cmovz   rax, rcx
0x18001cfd9  mov     cs:__security_cookie, rax
0x18001cfe0  mov     rbx, [rsp+30h+arg_10]
0x18001cfe5  not     rax
0x18001cfe8  mov     cs:__security_cookie_complement, rax
0x18001cfef  add     rsp, 30h
0x18001cff3  pop     rbp
0x18001cff4  retn
```
