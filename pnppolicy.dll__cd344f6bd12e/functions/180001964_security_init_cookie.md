# __security_init_cookie

- ea: `0x180001964`
- end: `0x180001a41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012d0`

## callees

- `0x180001964`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000199d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000199d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019d3`

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
0x180001964  mov     [rsp-8+arg_18], rbx
0x180001969  push    rbp
0x18000196a  mov     rbp, rsp
0x18000196d  sub     rsp, 20h
0x180001971  xor     eax, eax
0x180001973  mov     rbx, 2B992DDFA232h
0x18000197d  mov     [rbp+arg_0], rax
0x180001981  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001985  mov     qword ptr [rbp+PerformanceCount], rax
0x180001989  mov     rax, cs:__security_cookie
0x180001990  cmp     rax, rbx
0x180001993  jnz     loc_180001A2C
0x180001999  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000199d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019a7  mov     [rbp+arg_0], rax
0x1800019ab  call    cs:__imp_GetCurrentProcessId
0x1800019b1  mov     eax, eax
0x1800019b3  xor     [rbp+arg_0], rax
0x1800019b7  call    cs:__imp_GetCurrentThreadId
0x1800019bd  mov     eax, eax
0x1800019bf  xor     [rbp+arg_0], rax
0x1800019c3  call    cs:__imp_GetTickCount
0x1800019c9  mov     eax, eax
0x1800019cb  shl     rax, 18h
0x1800019cf  xor     [rbp+arg_0], rax
0x1800019d3  call    cs:__imp_GetTickCount
0x1800019d9  mov     eax, eax
0x1800019db  lea     rcx, [rbp+arg_0]
0x1800019df  xor     rax, [rbp+arg_0]
0x1800019e3  xor     rax, rcx
0x1800019e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800019ea  mov     [rbp+arg_0], rax
0x1800019ee  call    cs:__imp_QueryPerformanceCounter
0x1800019f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019f7  mov     rcx, 0FFFFFFFFFFFFh
0x180001a01  shl     rax, 20h
0x180001a05  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a09  xor     rax, [rbp+arg_0]
0x180001a0d  and     rax, rcx
0x180001a10  mov     rcx, rax
0x180001a13  cmp     rax, rbx
0x180001a16  jnz     short loc_180001A25
0x180001a18  mov     rax, 2B992DDFA233h
0x180001a22  mov     rcx, rax
0x180001a25  mov     cs:__security_cookie, rcx
0x180001a2c  mov     rbx, [rsp+20h+arg_18]
0x180001a31  not     rax
0x180001a34  mov     cs:__security_cookie_complement, rax
0x180001a3b  add     rsp, 20h
0x180001a3f  pop     rbp
0x180001a40  retn
```
