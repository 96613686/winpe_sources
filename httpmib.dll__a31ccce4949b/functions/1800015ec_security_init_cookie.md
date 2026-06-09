# __security_init_cookie

- ea: `0x1800015ec`
- end: `0x1800016c9`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001280`

## callees

- `0x1800015ec`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001676`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001676`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001633`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001633`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000163f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000163f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000164b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000165b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000164b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000165b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001625`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001625`

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
0x1800015ec  mov     [rsp-8+arg_18], rbx
0x1800015f1  push    rbp
0x1800015f2  mov     rbp, rsp
0x1800015f5  sub     rsp, 20h
0x1800015f9  xor     eax, eax
0x1800015fb  mov     rbx, 2B992DDFA232h
0x180001605  mov     [rbp+arg_0], rax
0x180001609  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000160d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001611  mov     rax, cs:__security_cookie
0x180001618  cmp     rax, rbx
0x18000161b  jnz     loc_1800016B4
0x180001621  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001625  call    cs:__imp_GetSystemTimeAsFileTime
0x18000162b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000162f  mov     [rbp+arg_0], rax
0x180001633  call    cs:__imp_GetCurrentProcessId
0x180001639  mov     eax, eax
0x18000163b  xor     [rbp+arg_0], rax
0x18000163f  call    cs:__imp_GetCurrentThreadId
0x180001645  mov     eax, eax
0x180001647  xor     [rbp+arg_0], rax
0x18000164b  call    cs:__imp_GetTickCount
0x180001651  mov     eax, eax
0x180001653  shl     rax, 18h
0x180001657  xor     [rbp+arg_0], rax
0x18000165b  call    cs:__imp_GetTickCount
0x180001661  mov     eax, eax
0x180001663  lea     rcx, [rbp+arg_0]
0x180001667  xor     rax, [rbp+arg_0]
0x18000166b  xor     rax, rcx
0x18000166e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001672  mov     [rbp+arg_0], rax
0x180001676  call    cs:__imp_QueryPerformanceCounter
0x18000167c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000167f  mov     rcx, 0FFFFFFFFFFFFh
0x180001689  shl     rax, 20h
0x18000168d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001691  xor     rax, [rbp+arg_0]
0x180001695  and     rax, rcx
0x180001698  mov     rcx, rax
0x18000169b  cmp     rax, rbx
0x18000169e  jnz     short loc_1800016AD
0x1800016a0  mov     rax, 2B992DDFA233h
0x1800016aa  mov     rcx, rax
0x1800016ad  mov     cs:__security_cookie, rcx
0x1800016b4  mov     rbx, [rsp+20h+arg_18]
0x1800016b9  not     rax
0x1800016bc  mov     cs:__security_cookie_complement, rax
0x1800016c3  add     rsp, 20h
0x1800016c7  pop     rbp
0x1800016c8  retn
```
