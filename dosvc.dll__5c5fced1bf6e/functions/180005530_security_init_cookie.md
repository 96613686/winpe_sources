# __security_init_cookie

- ea: `0x180005530`
- end: `0x1800055e5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004fd0`

## callees

- `0x180005530`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000557f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000557f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000558f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000558f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005565`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005565`

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
0x180005530  mov     [rsp-8+arg_10], rbx
0x180005535  push    rbp
0x180005536  mov     rbp, rsp
0x180005539  sub     rsp, 30h
0x18000553d  mov     rax, cs:__security_cookie
0x180005544  mov     rbx, 2B992DDFA232h
0x18000554e  cmp     rax, rbx
0x180005551  jnz     short loc_1800055D0
0x180005553  xor     eax, eax
0x180005555  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005559  mov     [rbp+var_10], rax
0x18000555d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005561  mov     qword ptr [rbp+PerformanceCount], rax
0x180005565  call    cs:__imp_GetSystemTimeAsFileTime
0x18000556b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000556f  mov     [rbp+var_10], rax
0x180005573  call    cs:__imp_GetCurrentThreadId
0x180005579  mov     eax, eax
0x18000557b  xor     [rbp+var_10], rax
0x18000557f  call    cs:__imp_GetCurrentProcessId
0x180005585  mov     eax, eax
0x180005587  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000558b  xor     [rbp+var_10], rax
0x18000558f  call    cs:__imp_QueryPerformanceCounter
0x180005595  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005598  lea     rcx, [rbp+var_10]
0x18000559c  shl     rax, 20h
0x1800055a0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800055a4  xor     rax, [rbp+var_10]
0x1800055a8  xor     rax, rcx
0x1800055ab  mov     rcx, 0FFFFFFFFFFFFh
0x1800055b5  and     rax, rcx
0x1800055b8  mov     rcx, 2B992DDFA233h
0x1800055c2  cmp     rax, rbx
0x1800055c5  cmovz   rax, rcx
0x1800055c9  mov     cs:__security_cookie, rax
0x1800055d0  mov     rbx, [rsp+30h+arg_10]
0x1800055d5  not     rax
0x1800055d8  mov     cs:__security_cookie_complement, rax
0x1800055df  add     rsp, 30h
0x1800055e3  pop     rbp
0x1800055e4  retn
```
