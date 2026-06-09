# __security_init_cookie

- ea: `0x180001a80`
- end: `0x180001b35`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001600`

## callees

- `0x180001a80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001acf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001adf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001adf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ab5`

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
0x180001a80  mov     [rsp-8+arg_10], rbx
0x180001a85  push    rbp
0x180001a86  mov     rbp, rsp
0x180001a89  sub     rsp, 30h
0x180001a8d  mov     rax, cs:__security_cookie
0x180001a94  mov     rbx, 2B992DDFA232h
0x180001a9e  cmp     rax, rbx
0x180001aa1  jnz     short loc_180001B20
0x180001aa3  xor     eax, eax
0x180001aa5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001aa9  mov     [rbp+var_10], rax
0x180001aad  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ab1  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ab5  call    cs:__imp_GetSystemTimeAsFileTime
0x180001abb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001abf  mov     [rbp+var_10], rax
0x180001ac3  call    cs:__imp_GetCurrentThreadId
0x180001ac9  mov     eax, eax
0x180001acb  xor     [rbp+var_10], rax
0x180001acf  call    cs:__imp_GetCurrentProcessId
0x180001ad5  mov     eax, eax
0x180001ad7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001adb  xor     [rbp+var_10], rax
0x180001adf  call    cs:__imp_QueryPerformanceCounter
0x180001ae5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ae8  lea     rcx, [rbp+var_10]
0x180001aec  shl     rax, 20h
0x180001af0  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001af4  xor     rax, [rbp+var_10]
0x180001af8  xor     rax, rcx
0x180001afb  mov     rcx, 0FFFFFFFFFFFFh
0x180001b05  and     rax, rcx
0x180001b08  mov     rcx, 2B992DDFA233h
0x180001b12  cmp     rax, rbx
0x180001b15  cmovz   rax, rcx
0x180001b19  mov     cs:__security_cookie, rax
0x180001b20  mov     rbx, [rsp+30h+arg_10]
0x180001b25  not     rax
0x180001b28  mov     cs:__security_cookie_complement, rax
0x180001b2f  add     rsp, 30h
0x180001b33  pop     rbp
0x180001b34  retn
```
