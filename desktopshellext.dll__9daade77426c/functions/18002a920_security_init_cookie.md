# __security_init_cookie

- ea: `0x18002a920`
- end: `0x18002a9d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a380`

## callees

- `0x18002a920`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a96f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a96f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a97f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a97f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a955`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a955`

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
0x18002a920  mov     [rsp-8+arg_10], rbx
0x18002a925  push    rbp
0x18002a926  mov     rbp, rsp
0x18002a929  sub     rsp, 30h
0x18002a92d  mov     rax, cs:__security_cookie
0x18002a934  mov     rbx, 2B992DDFA232h
0x18002a93e  cmp     rax, rbx
0x18002a941  jnz     short loc_18002A9C0
0x18002a943  xor     eax, eax
0x18002a945  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002a949  mov     [rbp+var_10], rax
0x18002a94d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002a951  mov     qword ptr [rbp+PerformanceCount], rax
0x18002a955  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a95b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002a95f  mov     [rbp+var_10], rax
0x18002a963  call    cs:__imp_GetCurrentThreadId
0x18002a969  mov     eax, eax
0x18002a96b  xor     [rbp+var_10], rax
0x18002a96f  call    cs:__imp_GetCurrentProcessId
0x18002a975  mov     eax, eax
0x18002a977  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002a97b  xor     [rbp+var_10], rax
0x18002a97f  call    cs:__imp_QueryPerformanceCounter
0x18002a985  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002a988  lea     rcx, [rbp+var_10]
0x18002a98c  shl     rax, 20h
0x18002a990  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002a994  xor     rax, [rbp+var_10]
0x18002a998  xor     rax, rcx
0x18002a99b  mov     rcx, 0FFFFFFFFFFFFh
0x18002a9a5  and     rax, rcx
0x18002a9a8  mov     rcx, 2B992DDFA233h
0x18002a9b2  cmp     rax, rbx
0x18002a9b5  cmovz   rax, rcx
0x18002a9b9  mov     cs:__security_cookie, rax
0x18002a9c0  mov     rbx, [rsp+30h+arg_10]
0x18002a9c5  not     rax
0x18002a9c8  mov     cs:__security_cookie_complement, rax
0x18002a9cf  add     rsp, 30h
0x18002a9d3  pop     rbp
0x18002a9d4  retn
```
