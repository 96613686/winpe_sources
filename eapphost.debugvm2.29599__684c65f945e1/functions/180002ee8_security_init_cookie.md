# __security_init_cookie

- ea: `0x180002ee8`
- end: `0x180002f9d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a40`

## callees

- `0x180002ee8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f1d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f47`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002f47`

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
0x180002ee8  mov     [rsp-8+arg_10], rbx
0x180002eed  push    rbp
0x180002eee  mov     rbp, rsp
0x180002ef1  sub     rsp, 30h
0x180002ef5  mov     rax, cs:__security_cookie
0x180002efc  mov     rbx, 2B992DDFA232h
0x180002f06  cmp     rax, rbx
0x180002f09  jnz     short loc_180002F88
0x180002f0b  xor     eax, eax
0x180002f0d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002f11  mov     [rbp+var_10], rax
0x180002f15  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002f19  mov     qword ptr [rbp+PerformanceCount], rax
0x180002f1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002f23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002f27  mov     [rbp+var_10], rax
0x180002f2b  call    cs:__imp_GetCurrentThreadId
0x180002f31  mov     eax, eax
0x180002f33  xor     [rbp+var_10], rax
0x180002f37  call    cs:__imp_GetCurrentProcessId
0x180002f3d  mov     eax, eax
0x180002f3f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002f43  xor     [rbp+var_10], rax
0x180002f47  call    cs:__imp_QueryPerformanceCounter
0x180002f4d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002f50  lea     rcx, [rbp+var_10]
0x180002f54  shl     rax, 20h
0x180002f58  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002f5c  xor     rax, [rbp+var_10]
0x180002f60  xor     rax, rcx
0x180002f63  mov     rcx, 0FFFFFFFFFFFFh
0x180002f6d  and     rax, rcx
0x180002f70  mov     rcx, 2B992DDFA233h
0x180002f7a  cmp     rax, rbx
0x180002f7d  cmovz   rax, rcx
0x180002f81  mov     cs:__security_cookie, rax
0x180002f88  mov     rbx, [rsp+30h+arg_10]
0x180002f8d  not     rax
0x180002f90  mov     cs:__security_cookie_complement, rax
0x180002f97  add     rsp, 30h
0x180002f9b  pop     rbp
0x180002f9c  retn
```
