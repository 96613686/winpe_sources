# __security_init_cookie

- ea: `0x18000e740`
- end: `0x18000e7f5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e6e4`

## callees

- `0x18000e740`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e79f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e79f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e78f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e78f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e783`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e783`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e775`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e775`

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
0x18000e740  mov     [rsp-8+arg_10], rbx
0x18000e745  push    rbp
0x18000e746  mov     rbp, rsp
0x18000e749  sub     rsp, 30h
0x18000e74d  mov     rax, cs:__security_cookie
0x18000e754  mov     rbx, 2B992DDFA232h
0x18000e75e  cmp     rax, rbx
0x18000e761  jnz     short loc_18000E7E0
0x18000e763  xor     eax, eax
0x18000e765  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000e769  mov     [rbp+var_10], rax
0x18000e76d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000e771  mov     qword ptr [rbp+PerformanceCount], rax
0x18000e775  call    cs:__imp_GetSystemTimeAsFileTime
0x18000e77b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000e77f  mov     [rbp+var_10], rax
0x18000e783  call    cs:__imp_GetCurrentThreadId
0x18000e789  mov     eax, eax
0x18000e78b  xor     [rbp+var_10], rax
0x18000e78f  call    cs:__imp_GetCurrentProcessId
0x18000e795  mov     eax, eax
0x18000e797  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000e79b  xor     [rbp+var_10], rax
0x18000e79f  call    cs:__imp_QueryPerformanceCounter
0x18000e7a5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000e7a8  lea     rcx, [rbp+var_10]
0x18000e7ac  shl     rax, 20h
0x18000e7b0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000e7b4  xor     rax, [rbp+var_10]
0x18000e7b8  xor     rax, rcx
0x18000e7bb  mov     rcx, 0FFFFFFFFFFFFh
0x18000e7c5  and     rax, rcx
0x18000e7c8  mov     rcx, 2B992DDFA233h
0x18000e7d2  cmp     rax, rbx
0x18000e7d5  cmovz   rax, rcx
0x18000e7d9  mov     cs:__security_cookie, rax
0x18000e7e0  mov     rbx, [rsp+30h+arg_10]
0x18000e7e5  not     rax
0x18000e7e8  mov     cs:__security_cookie_complement, rax
0x18000e7ef  add     rsp, 30h
0x18000e7f3  pop     rbp
0x18000e7f4  retn
```
