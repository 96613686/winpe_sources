# __security_init_cookie

- ea: `0x180002f48`
- end: `0x180002ffd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002aa0`

## callees

- `0x180002f48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002f97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f7d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fa7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fa7`

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
0x180002f48  mov     [rsp-8+arg_10], rbx
0x180002f4d  push    rbp
0x180002f4e  mov     rbp, rsp
0x180002f51  sub     rsp, 30h
0x180002f55  mov     rax, cs:__security_cookie
0x180002f5c  mov     rbx, 2B992DDFA232h
0x180002f66  cmp     rax, rbx
0x180002f69  jnz     short loc_180002FE8
0x180002f6b  xor     eax, eax
0x180002f6d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002f71  mov     [rbp+var_10], rax
0x180002f75  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002f79  mov     qword ptr [rbp+PerformanceCount], rax
0x180002f7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002f83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002f87  mov     [rbp+var_10], rax
0x180002f8b  call    cs:__imp_GetCurrentThreadId
0x180002f91  mov     eax, eax
0x180002f93  xor     [rbp+var_10], rax
0x180002f97  call    cs:__imp_GetCurrentProcessId
0x180002f9d  mov     eax, eax
0x180002f9f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002fa3  xor     [rbp+var_10], rax
0x180002fa7  call    cs:__imp_QueryPerformanceCounter
0x180002fad  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002fb0  lea     rcx, [rbp+var_10]
0x180002fb4  shl     rax, 20h
0x180002fb8  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002fbc  xor     rax, [rbp+var_10]
0x180002fc0  xor     rax, rcx
0x180002fc3  mov     rcx, 0FFFFFFFFFFFFh
0x180002fcd  and     rax, rcx
0x180002fd0  mov     rcx, 2B992DDFA233h
0x180002fda  cmp     rax, rbx
0x180002fdd  cmovz   rax, rcx
0x180002fe1  mov     cs:__security_cookie, rax
0x180002fe8  mov     rbx, [rsp+30h+arg_10]
0x180002fed  not     rax
0x180002ff0  mov     cs:__security_cookie_complement, rax
0x180002ff7  add     rsp, 30h
0x180002ffb  pop     rbp
0x180002ffc  retn
```
