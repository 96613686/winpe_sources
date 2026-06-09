# __security_init_cookie

- ea: `0x180001e84`
- end: `0x180001f61`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b10`

## callees

- `0x180001e84`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f0e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ed7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ebd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ebd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ee3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ee3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ef3`

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
0x180001e84  mov     [rsp-8+arg_18], rbx
0x180001e89  push    rbp
0x180001e8a  mov     rbp, rsp
0x180001e8d  sub     rsp, 20h
0x180001e91  xor     eax, eax
0x180001e93  mov     rbx, 2B992DDFA232h
0x180001e9d  mov     [rbp+arg_0], rax
0x180001ea1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ea5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ea9  mov     rax, cs:__security_cookie
0x180001eb0  cmp     rax, rbx
0x180001eb3  jnz     loc_180001F4C
0x180001eb9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ebd  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ec3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ec7  mov     [rbp+arg_0], rax
0x180001ecb  call    cs:__imp_GetCurrentProcessId
0x180001ed1  mov     eax, eax
0x180001ed3  xor     [rbp+arg_0], rax
0x180001ed7  call    cs:__imp_GetCurrentThreadId
0x180001edd  mov     eax, eax
0x180001edf  xor     [rbp+arg_0], rax
0x180001ee3  call    cs:__imp_GetTickCount
0x180001ee9  mov     eax, eax
0x180001eeb  shl     rax, 18h
0x180001eef  xor     [rbp+arg_0], rax
0x180001ef3  call    cs:__imp_GetTickCount
0x180001ef9  mov     eax, eax
0x180001efb  lea     rcx, [rbp+arg_0]
0x180001eff  xor     rax, [rbp+arg_0]
0x180001f03  xor     rax, rcx
0x180001f06  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f0a  mov     [rbp+arg_0], rax
0x180001f0e  call    cs:__imp_QueryPerformanceCounter
0x180001f14  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f17  mov     rcx, 0FFFFFFFFFFFFh
0x180001f21  shl     rax, 20h
0x180001f25  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f29  xor     rax, [rbp+arg_0]
0x180001f2d  and     rax, rcx
0x180001f30  mov     rcx, rax
0x180001f33  cmp     rax, rbx
0x180001f36  jnz     short loc_180001F45
0x180001f38  mov     rax, 2B992DDFA233h
0x180001f42  mov     rcx, rax
0x180001f45  mov     cs:__security_cookie, rcx
0x180001f4c  mov     rbx, [rsp+20h+arg_18]
0x180001f51  not     rax
0x180001f54  mov     cs:__security_cookie_complement, rax
0x180001f5b  add     rsp, 20h
0x180001f5f  pop     rbp
0x180001f60  retn
```
