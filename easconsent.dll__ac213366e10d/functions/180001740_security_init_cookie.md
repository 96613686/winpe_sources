# __security_init_cookie

- ea: `0x180001740`
- end: `0x18000181d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012f0`

## callees

- `0x180001740`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800017ca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800017ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001793`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001787`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000179f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000179f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001779`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001779`

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
0x180001740  mov     [rsp-8+arg_18], rbx
0x180001745  push    rbp
0x180001746  mov     rbp, rsp
0x180001749  sub     rsp, 20h
0x18000174d  xor     eax, eax
0x18000174f  mov     rbx, 2B992DDFA232h
0x180001759  mov     [rbp+arg_0], rax
0x18000175d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001761  mov     qword ptr [rbp+PerformanceCount], rax
0x180001765  mov     rax, cs:__security_cookie
0x18000176c  cmp     rax, rbx
0x18000176f  jnz     loc_180001808
0x180001775  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001779  call    cs:__imp_GetSystemTimeAsFileTime
0x18000177f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001783  mov     [rbp+arg_0], rax
0x180001787  call    cs:__imp_GetCurrentProcessId
0x18000178d  mov     eax, eax
0x18000178f  xor     [rbp+arg_0], rax
0x180001793  call    cs:__imp_GetCurrentThreadId
0x180001799  mov     eax, eax
0x18000179b  xor     [rbp+arg_0], rax
0x18000179f  call    cs:__imp_GetTickCount
0x1800017a5  mov     eax, eax
0x1800017a7  shl     rax, 18h
0x1800017ab  xor     [rbp+arg_0], rax
0x1800017af  call    cs:__imp_GetTickCount
0x1800017b5  mov     eax, eax
0x1800017b7  lea     rcx, [rbp+arg_0]
0x1800017bb  xor     rax, [rbp+arg_0]
0x1800017bf  xor     rax, rcx
0x1800017c2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800017c6  mov     [rbp+arg_0], rax
0x1800017ca  call    cs:__imp_QueryPerformanceCounter
0x1800017d0  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800017d3  mov     rcx, 0FFFFFFFFFFFFh
0x1800017dd  shl     rax, 20h
0x1800017e1  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800017e5  xor     rax, [rbp+arg_0]
0x1800017e9  and     rax, rcx
0x1800017ec  mov     rcx, rax
0x1800017ef  cmp     rax, rbx
0x1800017f2  jnz     short loc_180001801
0x1800017f4  mov     rax, 2B992DDFA233h
0x1800017fe  mov     rcx, rax
0x180001801  mov     cs:__security_cookie, rcx
0x180001808  mov     rbx, [rsp+20h+arg_18]
0x18000180d  not     rax
0x180001810  mov     cs:__security_cookie_complement, rax
0x180001817  add     rsp, 20h
0x18000181b  pop     rbp
0x18000181c  retn
```
