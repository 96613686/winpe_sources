# __security_init_cookie

- ea: `0x140002c90`
- end: `0x140002d45`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002970`

## callees

- `0x140002c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002cd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002cd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002cdf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002cc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002cc5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002cef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002cef`

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
0x140002c90  mov     [rsp-8+arg_10], rbx
0x140002c95  push    rbp
0x140002c96  mov     rbp, rsp
0x140002c99  sub     rsp, 30h
0x140002c9d  mov     rax, cs:__security_cookie
0x140002ca4  mov     rbx, 2B992DDFA232h
0x140002cae  cmp     rax, rbx
0x140002cb1  jnz     short loc_140002D30
0x140002cb3  xor     eax, eax
0x140002cb5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002cb9  mov     [rbp+var_10], rax
0x140002cbd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002cc1  mov     qword ptr [rbp+PerformanceCount], rax
0x140002cc5  call    cs:__imp_GetSystemTimeAsFileTime
0x140002ccb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002ccf  mov     [rbp+var_10], rax
0x140002cd3  call    cs:__imp_GetCurrentThreadId
0x140002cd9  mov     eax, eax
0x140002cdb  xor     [rbp+var_10], rax
0x140002cdf  call    cs:__imp_GetCurrentProcessId
0x140002ce5  mov     eax, eax
0x140002ce7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002ceb  xor     [rbp+var_10], rax
0x140002cef  call    cs:__imp_QueryPerformanceCounter
0x140002cf5  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002cf8  lea     rcx, [rbp+var_10]
0x140002cfc  shl     rax, 20h
0x140002d00  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002d04  xor     rax, [rbp+var_10]
0x140002d08  xor     rax, rcx
0x140002d0b  mov     rcx, 0FFFFFFFFFFFFh
0x140002d15  and     rax, rcx
0x140002d18  mov     rcx, 2B992DDFA233h
0x140002d22  cmp     rax, rbx
0x140002d25  cmovz   rax, rcx
0x140002d29  mov     cs:__security_cookie, rax
0x140002d30  mov     rbx, [rsp+30h+arg_10]
0x140002d35  not     rax
0x140002d38  mov     cs:__security_cookie_complement, rax
0x140002d3f  add     rsp, 30h
0x140002d43  pop     rbp
0x140002d44  retn
```
