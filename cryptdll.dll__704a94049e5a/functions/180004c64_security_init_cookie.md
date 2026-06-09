# __security_init_cookie

- ea: `0x180004c64`
- end: `0x180004d19`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004bf0`

## callees

- `0x180004c64`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004cc3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004cc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004cb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004cb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ca7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004c99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004c99`

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
0x180004c64  mov     [rsp-8+arg_10], rbx
0x180004c69  push    rbp
0x180004c6a  mov     rbp, rsp
0x180004c6d  sub     rsp, 30h
0x180004c71  mov     rax, cs:__security_cookie
0x180004c78  mov     rbx, 2B992DDFA232h
0x180004c82  cmp     rax, rbx
0x180004c85  jnz     short loc_180004D04
0x180004c87  xor     eax, eax
0x180004c89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004c8d  mov     [rbp+var_10], rax
0x180004c91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004c95  mov     qword ptr [rbp+PerformanceCount], rax
0x180004c99  call    cs:__imp_GetSystemTimeAsFileTime
0x180004c9f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004ca3  mov     [rbp+var_10], rax
0x180004ca7  call    cs:__imp_GetCurrentThreadId
0x180004cad  mov     eax, eax
0x180004caf  xor     [rbp+var_10], rax
0x180004cb3  call    cs:__imp_GetCurrentProcessId
0x180004cb9  mov     eax, eax
0x180004cbb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004cbf  xor     [rbp+var_10], rax
0x180004cc3  call    cs:__imp_QueryPerformanceCounter
0x180004cc9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004ccc  lea     rcx, [rbp+var_10]
0x180004cd0  shl     rax, 20h
0x180004cd4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004cd8  xor     rax, [rbp+var_10]
0x180004cdc  xor     rax, rcx
0x180004cdf  mov     rcx, 0FFFFFFFFFFFFh
0x180004ce9  and     rax, rcx
0x180004cec  mov     rcx, 2B992DDFA233h
0x180004cf6  cmp     rax, rbx
0x180004cf9  cmovz   rax, rcx
0x180004cfd  mov     cs:__security_cookie, rax
0x180004d04  mov     rbx, [rsp+30h+arg_10]
0x180004d09  not     rax
0x180004d0c  mov     cs:__security_cookie_complement, rax
0x180004d13  add     rsp, 30h
0x180004d17  pop     rbp
0x180004d18  retn
```
