# __security_init_cookie

- ea: `0x18001e610`
- end: `0x18001e6c5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e190`

## callees

- `0x18001e610`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e653`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e653`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e65f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e65f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e645`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e645`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e66f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e66f`

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
0x18001e610  mov     [rsp-8+arg_10], rbx
0x18001e615  push    rbp
0x18001e616  mov     rbp, rsp
0x18001e619  sub     rsp, 30h
0x18001e61d  mov     rax, cs:__security_cookie
0x18001e624  mov     rbx, 2B992DDFA232h
0x18001e62e  cmp     rax, rbx
0x18001e631  jnz     short loc_18001E6B0
0x18001e633  xor     eax, eax
0x18001e635  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001e639  mov     [rbp+var_10], rax
0x18001e63d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001e641  mov     qword ptr [rbp+PerformanceCount], rax
0x18001e645  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e64b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001e64f  mov     [rbp+var_10], rax
0x18001e653  call    cs:__imp_GetCurrentThreadId
0x18001e659  mov     eax, eax
0x18001e65b  xor     [rbp+var_10], rax
0x18001e65f  call    cs:__imp_GetCurrentProcessId
0x18001e665  mov     eax, eax
0x18001e667  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001e66b  xor     [rbp+var_10], rax
0x18001e66f  call    cs:__imp_QueryPerformanceCounter
0x18001e675  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001e678  lea     rcx, [rbp+var_10]
0x18001e67c  shl     rax, 20h
0x18001e680  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001e684  xor     rax, [rbp+var_10]
0x18001e688  xor     rax, rcx
0x18001e68b  mov     rcx, 0FFFFFFFFFFFFh
0x18001e695  and     rax, rcx
0x18001e698  mov     rcx, 2B992DDFA233h
0x18001e6a2  cmp     rax, rbx
0x18001e6a5  cmovz   rax, rcx
0x18001e6a9  mov     cs:__security_cookie, rax
0x18001e6b0  mov     rbx, [rsp+30h+arg_10]
0x18001e6b5  not     rax
0x18001e6b8  mov     cs:__security_cookie_complement, rax
0x18001e6bf  add     rsp, 30h
0x18001e6c3  pop     rbp
0x18001e6c4  retn
```
