# __security_init_cookie

- ea: `0x18025b500`
- end: `0x18025b5b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18025b0b0`

## callees

- `0x18025b500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18025b54f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18025b54f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18025b543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18025b543`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18025b535`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18025b535`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18025b55f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18025b55f`

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
0x18025b500  mov     [rsp-8+arg_10], rbx
0x18025b505  push    rbp
0x18025b506  mov     rbp, rsp
0x18025b509  sub     rsp, 30h
0x18025b50d  mov     rax, cs:__security_cookie
0x18025b514  mov     rbx, 2B992DDFA232h
0x18025b51e  cmp     rax, rbx
0x18025b521  jnz     short loc_18025B5A0
0x18025b523  xor     eax, eax
0x18025b525  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18025b529  mov     [rbp+var_10], rax
0x18025b52d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18025b531  mov     qword ptr [rbp+PerformanceCount], rax
0x18025b535  call    cs:__imp_GetSystemTimeAsFileTime
0x18025b53b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18025b53f  mov     [rbp+var_10], rax
0x18025b543  call    cs:__imp_GetCurrentThreadId
0x18025b549  mov     eax, eax
0x18025b54b  xor     [rbp+var_10], rax
0x18025b54f  call    cs:__imp_GetCurrentProcessId
0x18025b555  mov     eax, eax
0x18025b557  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18025b55b  xor     [rbp+var_10], rax
0x18025b55f  call    cs:__imp_QueryPerformanceCounter
0x18025b565  mov     eax, dword ptr [rbp+PerformanceCount]
0x18025b568  lea     rcx, [rbp+var_10]
0x18025b56c  shl     rax, 20h
0x18025b570  xor     rax, qword ptr [rbp+PerformanceCount]
0x18025b574  xor     rax, [rbp+var_10]
0x18025b578  xor     rax, rcx
0x18025b57b  mov     rcx, 0FFFFFFFFFFFFh
0x18025b585  and     rax, rcx
0x18025b588  mov     rcx, 2B992DDFA233h
0x18025b592  cmp     rax, rbx
0x18025b595  cmovz   rax, rcx
0x18025b599  mov     cs:__security_cookie, rax
0x18025b5a0  mov     rbx, [rsp+30h+arg_10]
0x18025b5a5  not     rax
0x18025b5a8  mov     cs:__security_cookie_complement, rax
0x18025b5af  add     rsp, 30h
0x18025b5b3  pop     rbp
0x18025b5b4  retn
```
