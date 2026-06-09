# __security_init_cookie

- ea: `0x1800035d0`
- end: `0x180003685`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003030`

## callees

- `0x1800035d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000361f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000361f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003613`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000362f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000362f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003605`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003605`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1800035d0  mov     [rsp-8+arg_10], rbx
0x1800035d5  push    rbp
0x1800035d6  mov     rbp, rsp
0x1800035d9  sub     rsp, 30h
0x1800035dd  mov     rax, cs:__security_cookie
0x1800035e4  mov     rbx, 2B992DDFA232h
0x1800035ee  cmp     rax, rbx
0x1800035f1  jnz     short loc_180003670
0x1800035f3  xor     eax, eax
0x1800035f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800035f9  mov     [rbp+var_10], rax
0x1800035fd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003601  mov     qword ptr [rbp+PerformanceCount], rax
0x180003605  call    cs:__imp_GetSystemTimeAsFileTime
0x18000360b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000360f  mov     [rbp+var_10], rax
0x180003613  call    cs:__imp_GetCurrentThreadId
0x180003619  mov     eax, eax
0x18000361b  xor     [rbp+var_10], rax
0x18000361f  call    cs:__imp_GetCurrentProcessId
0x180003625  mov     eax, eax
0x180003627  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000362b  xor     [rbp+var_10], rax
0x18000362f  call    cs:__imp_QueryPerformanceCounter
0x180003635  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003638  lea     rcx, [rbp+var_10]
0x18000363c  shl     rax, 20h
0x180003640  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003644  xor     rax, [rbp+var_10]
0x180003648  xor     rax, rcx
0x18000364b  mov     rcx, 0FFFFFFFFFFFFh
0x180003655  and     rax, rcx
0x180003658  mov     rcx, 2B992DDFA233h
0x180003662  cmp     rax, rbx
0x180003665  cmovz   rax, rcx
0x180003669  mov     cs:__security_cookie, rax
0x180003670  mov     rbx, [rsp+30h+arg_10]
0x180003675  not     rax
0x180003678  mov     cs:__security_cookie_complement, rax
0x18000367f  add     rsp, 30h
0x180003683  pop     rbp
0x180003684  retn
```
