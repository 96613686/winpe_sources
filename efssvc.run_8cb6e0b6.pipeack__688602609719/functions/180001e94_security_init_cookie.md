# __security_init_cookie

- ea: `0x180001e94`
- end: `0x180001f71`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b20`

## callees

- `0x180001e94`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ee7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f03`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001e94  mov     [rsp-8+arg_18], rbx
0x180001e99  push    rbp
0x180001e9a  mov     rbp, rsp
0x180001e9d  sub     rsp, 20h
0x180001ea1  xor     eax, eax
0x180001ea3  mov     rbx, 2B992DDFA232h
0x180001ead  mov     [rbp+arg_0], rax
0x180001eb1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001eb5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001eb9  mov     rax, cs:__security_cookie
0x180001ec0  cmp     rax, rbx
0x180001ec3  jnz     loc_180001F5C
0x180001ec9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ecd  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ed3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ed7  mov     [rbp+arg_0], rax
0x180001edb  call    cs:__imp_GetCurrentProcessId
0x180001ee1  mov     eax, eax
0x180001ee3  xor     [rbp+arg_0], rax
0x180001ee7  call    cs:__imp_GetCurrentThreadId
0x180001eed  mov     eax, eax
0x180001eef  xor     [rbp+arg_0], rax
0x180001ef3  call    cs:__imp_GetTickCount
0x180001ef9  mov     eax, eax
0x180001efb  shl     rax, 18h
0x180001eff  xor     [rbp+arg_0], rax
0x180001f03  call    cs:__imp_GetTickCount
0x180001f09  mov     eax, eax
0x180001f0b  lea     rcx, [rbp+arg_0]
0x180001f0f  xor     rax, [rbp+arg_0]
0x180001f13  xor     rax, rcx
0x180001f16  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f1a  mov     [rbp+arg_0], rax
0x180001f1e  call    cs:__imp_QueryPerformanceCounter
0x180001f24  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f27  mov     rcx, 0FFFFFFFFFFFFh
0x180001f31  shl     rax, 20h
0x180001f35  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f39  xor     rax, [rbp+arg_0]
0x180001f3d  and     rax, rcx
0x180001f40  mov     rcx, rax
0x180001f43  cmp     rax, rbx
0x180001f46  jnz     short loc_180001F55
0x180001f48  mov     rax, 2B992DDFA233h
0x180001f52  mov     rcx, rax
0x180001f55  mov     cs:__security_cookie, rcx
0x180001f5c  mov     rbx, [rsp+20h+arg_18]
0x180001f61  not     rax
0x180001f64  mov     cs:__security_cookie_complement, rax
0x180001f6b  add     rsp, 20h
0x180001f6f  pop     rbp
0x180001f70  retn
```
