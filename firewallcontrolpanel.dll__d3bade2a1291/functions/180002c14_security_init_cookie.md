# __security_init_cookie

- ea: `0x180002c14`
- end: `0x180002cf1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022f0`

## callees

- `0x180002c14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c83`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002c9e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002c9e`

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
0x180002c14  mov     [rsp-8+arg_18], rbx
0x180002c19  push    rbp
0x180002c1a  mov     rbp, rsp
0x180002c1d  sub     rsp, 20h
0x180002c21  xor     eax, eax
0x180002c23  mov     rbx, 2B992DDFA232h
0x180002c2d  mov     [rbp+arg_0], rax
0x180002c31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002c35  mov     qword ptr [rbp+PerformanceCount], rax
0x180002c39  mov     rax, cs:__security_cookie
0x180002c40  cmp     rax, rbx
0x180002c43  jnz     loc_180002CDC
0x180002c49  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002c4d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002c53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002c57  mov     [rbp+arg_0], rax
0x180002c5b  call    cs:__imp_GetCurrentProcessId
0x180002c61  mov     eax, eax
0x180002c63  xor     [rbp+arg_0], rax
0x180002c67  call    cs:__imp_GetCurrentThreadId
0x180002c6d  mov     eax, eax
0x180002c6f  xor     [rbp+arg_0], rax
0x180002c73  call    cs:__imp_GetTickCount
0x180002c79  mov     eax, eax
0x180002c7b  shl     rax, 18h
0x180002c7f  xor     [rbp+arg_0], rax
0x180002c83  call    cs:__imp_GetTickCount
0x180002c89  mov     eax, eax
0x180002c8b  lea     rcx, [rbp+arg_0]
0x180002c8f  xor     rax, [rbp+arg_0]
0x180002c93  xor     rax, rcx
0x180002c96  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002c9a  mov     [rbp+arg_0], rax
0x180002c9e  call    cs:__imp_QueryPerformanceCounter
0x180002ca4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ca7  mov     rcx, 0FFFFFFFFFFFFh
0x180002cb1  shl     rax, 20h
0x180002cb5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002cb9  xor     rax, [rbp+arg_0]
0x180002cbd  and     rax, rcx
0x180002cc0  mov     rcx, rax
0x180002cc3  cmp     rax, rbx
0x180002cc6  jnz     short loc_180002CD5
0x180002cc8  mov     rax, 2B992DDFA233h
0x180002cd2  mov     rcx, rax
0x180002cd5  mov     cs:__security_cookie, rcx
0x180002cdc  mov     rbx, [rsp+20h+arg_18]
0x180002ce1  not     rax
0x180002ce4  mov     cs:__security_cookie_complement, rax
0x180002ceb  add     rsp, 20h
0x180002cef  pop     rbp
0x180002cf0  retn
```
