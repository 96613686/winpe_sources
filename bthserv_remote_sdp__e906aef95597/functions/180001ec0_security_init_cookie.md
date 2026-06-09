# __security_init_cookie

- ea: `0x180001ec0`
- end: `0x180001f71`
- name: `__security_init_cookie`
- size: `177`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001750`

## callees

- `0x180001ec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001eff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001eff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ef1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ef1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f1b`

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
0x180001ec0  mov     [rsp-8+arg_10], rbx
0x180001ec5  push    rbp
0x180001ec6  mov     rbp, rsp
0x180001ec9  sub     rsp, 30h
0x180001ecd  mov     rax, cs:__security_cookie
0x180001ed4  mov     rbx, 2B992DDFA232h
0x180001ede  cmp     rax, rbx
0x180001ee1  jnz     short loc_180001F5C
0x180001ee3  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001ee8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001eec  and     qword ptr [rbp+PerformanceCount], 0
0x180001ef1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ef7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001efb  mov     [rbp+var_10], rax
0x180001eff  call    cs:__imp_GetCurrentThreadId
0x180001f05  mov     eax, eax
0x180001f07  xor     [rbp+var_10], rax
0x180001f0b  call    cs:__imp_GetCurrentProcessId
0x180001f11  mov     eax, eax
0x180001f13  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f17  xor     [rbp+var_10], rax
0x180001f1b  call    cs:__imp_QueryPerformanceCounter
0x180001f21  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f24  lea     rcx, [rbp+var_10]
0x180001f28  shl     rax, 20h
0x180001f2c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f30  xor     rax, [rbp+var_10]
0x180001f34  xor     rax, rcx
0x180001f37  mov     rcx, 0FFFFFFFFFFFFh
0x180001f41  and     rax, rcx
0x180001f44  mov     rcx, 2B992DDFA233h
0x180001f4e  cmp     rax, rbx
0x180001f51  cmovz   rax, rcx
0x180001f55  mov     cs:__security_cookie, rax
0x180001f5c  mov     rbx, [rsp+30h+arg_10]
0x180001f61  not     rax
0x180001f64  mov     cs:__security_cookie_complement, rax
0x180001f6b  add     rsp, 30h
0x180001f6f  pop     rbp
0x180001f70  retn
```
