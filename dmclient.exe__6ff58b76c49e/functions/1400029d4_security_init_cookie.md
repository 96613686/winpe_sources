# __security_init_cookie

- ea: `0x1400029d4`
- end: `0x140002ab1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400025d0`

## callees

- `0x1400029d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002a27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002a27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002a1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002a0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002a0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002a33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002a43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002a33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002a43`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002a5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002a5e`

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
0x1400029d4  mov     [rsp-8+arg_18], rbx
0x1400029d9  push    rbp
0x1400029da  mov     rbp, rsp
0x1400029dd  sub     rsp, 20h
0x1400029e1  xor     eax, eax
0x1400029e3  mov     rbx, 2B992DDFA232h
0x1400029ed  mov     [rbp+arg_0], rax
0x1400029f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400029f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400029f9  mov     rax, cs:__security_cookie
0x140002a00  cmp     rax, rbx
0x140002a03  jnz     loc_140002A9C
0x140002a09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002a0d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002a13  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002a17  mov     [rbp+arg_0], rax
0x140002a1b  call    cs:__imp_GetCurrentProcessId
0x140002a21  mov     eax, eax
0x140002a23  xor     [rbp+arg_0], rax
0x140002a27  call    cs:__imp_GetCurrentThreadId
0x140002a2d  mov     eax, eax
0x140002a2f  xor     [rbp+arg_0], rax
0x140002a33  call    cs:__imp_GetTickCount
0x140002a39  mov     eax, eax
0x140002a3b  shl     rax, 18h
0x140002a3f  xor     [rbp+arg_0], rax
0x140002a43  call    cs:__imp_GetTickCount
0x140002a49  mov     eax, eax
0x140002a4b  lea     rcx, [rbp+arg_0]
0x140002a4f  xor     rax, [rbp+arg_0]
0x140002a53  xor     rax, rcx
0x140002a56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002a5a  mov     [rbp+arg_0], rax
0x140002a5e  call    cs:__imp_QueryPerformanceCounter
0x140002a64  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002a67  mov     rcx, 0FFFFFFFFFFFFh
0x140002a71  shl     rax, 20h
0x140002a75  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002a79  xor     rax, [rbp+arg_0]
0x140002a7d  and     rax, rcx
0x140002a80  mov     rcx, rax
0x140002a83  cmp     rax, rbx
0x140002a86  jnz     short loc_140002A95
0x140002a88  mov     rax, 2B992DDFA233h
0x140002a92  mov     rcx, rax
0x140002a95  mov     cs:__security_cookie, rcx
0x140002a9c  mov     rbx, [rsp+20h+arg_18]
0x140002aa1  not     rax
0x140002aa4  mov     cs:__security_cookie_complement, rax
0x140002aab  add     rsp, 20h
0x140002aaf  pop     rbp
0x140002ab0  retn
```
