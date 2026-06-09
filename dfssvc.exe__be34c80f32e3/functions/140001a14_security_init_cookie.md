# __security_init_cookie

- ea: `0x140001a14`
- end: `0x140001aed`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001500`

## callees

- `0x140001a14`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001a9a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001a9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001a49`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001a49`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001a6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001a7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001a6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001a57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001a57`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x140001a14  mov     [rsp-8+arg_18], rbx
0x140001a19  push    rbp
0x140001a1a  mov     rbp, rsp
0x140001a1d  sub     rsp, 20h
0x140001a21  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x140001a26  mov     rbx, 2B992DDFA232h
0x140001a30  and     qword ptr [rbp+PerformanceCount], 0
0x140001a35  mov     rax, cs:__security_cookie
0x140001a3c  cmp     rax, rbx
0x140001a3f  jnz     loc_140001AD8
0x140001a45  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001a49  call    cs:__imp_GetSystemTimeAsFileTime
0x140001a4f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001a53  mov     [rbp+arg_0], rax
0x140001a57  call    cs:__imp_GetCurrentProcessId
0x140001a5d  mov     eax, eax
0x140001a5f  xor     [rbp+arg_0], rax
0x140001a63  call    cs:__imp_GetCurrentThreadId
0x140001a69  mov     eax, eax
0x140001a6b  xor     [rbp+arg_0], rax
0x140001a6f  call    cs:__imp_GetTickCount
0x140001a75  mov     eax, eax
0x140001a77  shl     rax, 18h
0x140001a7b  xor     [rbp+arg_0], rax
0x140001a7f  call    cs:__imp_GetTickCount
0x140001a85  mov     eax, eax
0x140001a87  lea     rcx, [rbp+arg_0]
0x140001a8b  xor     rax, [rbp+arg_0]
0x140001a8f  xor     rax, rcx
0x140001a92  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001a96  mov     [rbp+arg_0], rax
0x140001a9a  call    cs:__imp_QueryPerformanceCounter
0x140001aa0  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001aa3  mov     rcx, 0FFFFFFFFFFFFh
0x140001aad  shl     rax, 20h
0x140001ab1  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001ab5  xor     rax, [rbp+arg_0]
0x140001ab9  and     rax, rcx
0x140001abc  mov     rcx, rax
0x140001abf  cmp     rax, rbx
0x140001ac2  jnz     short loc_140001AD1
0x140001ac4  mov     rax, 2B992DDFA233h
0x140001ace  mov     rcx, rax
0x140001ad1  mov     cs:__security_cookie, rcx
0x140001ad8  mov     rbx, [rsp+20h+arg_18]
0x140001add  not     rax
0x140001ae0  mov     cs:__security_cookie_complement, rax
0x140001ae7  add     rsp, 20h
0x140001aeb  pop     rbp
0x140001aec  retn
```
