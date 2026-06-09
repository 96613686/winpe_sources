# __security_init_cookie

- ea: `0x180001e7c`
- end: `0x180001f31`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a00`

## callees

- `0x180001e7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ebf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ebf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001edb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001edb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001eb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001eb1`

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
0x180001e7c  mov     [rsp-8+arg_10], rbx
0x180001e81  push    rbp
0x180001e82  mov     rbp, rsp
0x180001e85  sub     rsp, 30h
0x180001e89  mov     rax, cs:__security_cookie
0x180001e90  mov     rbx, 2B992DDFA232h
0x180001e9a  cmp     rax, rbx
0x180001e9d  jnz     short loc_180001F1C
0x180001e9f  xor     eax, eax
0x180001ea1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ea5  mov     [rbp+var_10], rax
0x180001ea9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ead  mov     qword ptr [rbp+PerformanceCount], rax
0x180001eb1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001eb7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ebb  mov     [rbp+var_10], rax
0x180001ebf  call    cs:__imp_GetCurrentThreadId
0x180001ec5  mov     eax, eax
0x180001ec7  xor     [rbp+var_10], rax
0x180001ecb  call    cs:__imp_GetCurrentProcessId
0x180001ed1  mov     eax, eax
0x180001ed3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001ed7  xor     [rbp+var_10], rax
0x180001edb  call    cs:__imp_QueryPerformanceCounter
0x180001ee1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ee4  lea     rcx, [rbp+var_10]
0x180001ee8  shl     rax, 20h
0x180001eec  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ef0  xor     rax, [rbp+var_10]
0x180001ef4  xor     rax, rcx
0x180001ef7  mov     rcx, 0FFFFFFFFFFFFh
0x180001f01  and     rax, rcx
0x180001f04  mov     rcx, 2B992DDFA233h
0x180001f0e  cmp     rax, rbx
0x180001f11  cmovz   rax, rcx
0x180001f15  mov     cs:__security_cookie, rax
0x180001f1c  mov     rbx, [rsp+30h+arg_10]
0x180001f21  not     rax
0x180001f24  mov     cs:__security_cookie_complement, rax
0x180001f2b  add     rsp, 30h
0x180001f2f  pop     rbp
0x180001f30  retn
```
