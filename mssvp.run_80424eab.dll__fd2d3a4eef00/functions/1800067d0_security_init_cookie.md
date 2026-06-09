# __security_init_cookie

- ea: `0x1800067d0`
- end: `0x180006885`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006220`

## callees

- `0x1800067d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000681f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000681f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006813`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006813`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000682f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000682f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006805`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006805`

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
0x1800067d0  mov     [rsp-8+arg_10], rbx
0x1800067d5  push    rbp
0x1800067d6  mov     rbp, rsp
0x1800067d9  sub     rsp, 30h
0x1800067dd  mov     rax, cs:__security_cookie
0x1800067e4  mov     rbx, 2B992DDFA232h
0x1800067ee  cmp     rax, rbx
0x1800067f1  jnz     short loc_180006870
0x1800067f3  xor     eax, eax
0x1800067f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800067f9  mov     [rbp+var_10], rax
0x1800067fd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006801  mov     qword ptr [rbp+PerformanceCount], rax
0x180006805  call    cs:__imp_GetSystemTimeAsFileTime
0x18000680b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000680f  mov     [rbp+var_10], rax
0x180006813  call    cs:__imp_GetCurrentThreadId
0x180006819  mov     eax, eax
0x18000681b  xor     [rbp+var_10], rax
0x18000681f  call    cs:__imp_GetCurrentProcessId
0x180006825  mov     eax, eax
0x180006827  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000682b  xor     [rbp+var_10], rax
0x18000682f  call    cs:__imp_QueryPerformanceCounter
0x180006835  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006838  lea     rcx, [rbp+var_10]
0x18000683c  shl     rax, 20h
0x180006840  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006844  xor     rax, [rbp+var_10]
0x180006848  xor     rax, rcx
0x18000684b  mov     rcx, 0FFFFFFFFFFFFh
0x180006855  and     rax, rcx
0x180006858  mov     rcx, 2B992DDFA233h
0x180006862  cmp     rax, rbx
0x180006865  cmovz   rax, rcx
0x180006869  mov     cs:__security_cookie, rax
0x180006870  mov     rbx, [rsp+30h+arg_10]
0x180006875  not     rax
0x180006878  mov     cs:__security_cookie_complement, rax
0x18000687f  add     rsp, 30h
0x180006883  pop     rbp
0x180006884  retn
```
