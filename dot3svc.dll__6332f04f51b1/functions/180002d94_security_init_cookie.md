# __security_init_cookie

- ea: `0x180002d94`
- end: `0x180002e49`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002590`

## callees

- `0x180002d94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002dd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002dc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002dc9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002df3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002df3`

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
0x180002d94  mov     [rsp-8+arg_10], rbx
0x180002d99  push    rbp
0x180002d9a  mov     rbp, rsp
0x180002d9d  sub     rsp, 30h
0x180002da1  mov     rax, cs:__security_cookie
0x180002da8  mov     rbx, 2B992DDFA232h
0x180002db2  cmp     rax, rbx
0x180002db5  jnz     short loc_180002E34
0x180002db7  xor     eax, eax
0x180002db9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002dbd  mov     [rbp+var_10], rax
0x180002dc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002dc5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002dc9  call    cs:__imp_GetSystemTimeAsFileTime
0x180002dcf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002dd3  mov     [rbp+var_10], rax
0x180002dd7  call    cs:__imp_GetCurrentThreadId
0x180002ddd  mov     eax, eax
0x180002ddf  xor     [rbp+var_10], rax
0x180002de3  call    cs:__imp_GetCurrentProcessId
0x180002de9  mov     eax, eax
0x180002deb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002def  xor     [rbp+var_10], rax
0x180002df3  call    cs:__imp_QueryPerformanceCounter
0x180002df9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002dfc  lea     rcx, [rbp+var_10]
0x180002e00  shl     rax, 20h
0x180002e04  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002e08  xor     rax, [rbp+var_10]
0x180002e0c  xor     rax, rcx
0x180002e0f  mov     rcx, 0FFFFFFFFFFFFh
0x180002e19  and     rax, rcx
0x180002e1c  mov     rcx, 2B992DDFA233h
0x180002e26  cmp     rax, rbx
0x180002e29  cmovz   rax, rcx
0x180002e2d  mov     cs:__security_cookie, rax
0x180002e34  mov     rbx, [rsp+30h+arg_10]
0x180002e39  not     rax
0x180002e3c  mov     cs:__security_cookie_complement, rax
0x180002e43  add     rsp, 30h
0x180002e47  pop     rbp
0x180002e48  retn
```
