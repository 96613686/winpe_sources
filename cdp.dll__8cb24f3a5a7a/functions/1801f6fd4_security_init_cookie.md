# __security_init_cookie

- ea: `0x1801f6fd4`
- end: `0x1801f7089`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801f6f60`

## callees

- `0x1801f6fd4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801f7033`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801f7033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801f7023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801f7023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f7017`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801f7017`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801f7009`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801f7009`

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
0x1801f6fd4  mov     [rsp-8+arg_10], rbx
0x1801f6fd9  push    rbp
0x1801f6fda  mov     rbp, rsp
0x1801f6fdd  sub     rsp, 30h
0x1801f6fe1  mov     rax, cs:__security_cookie
0x1801f6fe8  mov     rbx, 2B992DDFA232h
0x1801f6ff2  cmp     rax, rbx
0x1801f6ff5  jnz     short loc_1801F7074
0x1801f6ff7  xor     eax, eax
0x1801f6ff9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801f6ffd  mov     [rbp+var_10], rax
0x1801f7001  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1801f7005  mov     qword ptr [rbp+PerformanceCount], rax
0x1801f7009  call    cs:__imp_GetSystemTimeAsFileTime
0x1801f700f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801f7013  mov     [rbp+var_10], rax
0x1801f7017  call    cs:__imp_GetCurrentThreadId
0x1801f701d  mov     eax, eax
0x1801f701f  xor     [rbp+var_10], rax
0x1801f7023  call    cs:__imp_GetCurrentProcessId
0x1801f7029  mov     eax, eax
0x1801f702b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1801f702f  xor     [rbp+var_10], rax
0x1801f7033  call    cs:__imp_QueryPerformanceCounter
0x1801f7039  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801f703c  lea     rcx, [rbp+var_10]
0x1801f7040  shl     rax, 20h
0x1801f7044  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801f7048  xor     rax, [rbp+var_10]
0x1801f704c  xor     rax, rcx
0x1801f704f  mov     rcx, 0FFFFFFFFFFFFh
0x1801f7059  and     rax, rcx
0x1801f705c  mov     rcx, 2B992DDFA233h
0x1801f7066  cmp     rax, rbx
0x1801f7069  cmovz   rax, rcx
0x1801f706d  mov     cs:__security_cookie, rax
0x1801f7074  mov     rbx, [rsp+30h+arg_10]
0x1801f7079  not     rax
0x1801f707c  mov     cs:__security_cookie_complement, rax
0x1801f7083  add     rsp, 30h
0x1801f7087  pop     rbp
0x1801f7088  retn
```
