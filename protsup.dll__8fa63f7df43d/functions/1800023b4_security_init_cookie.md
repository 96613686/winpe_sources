# __security_init_cookie

- ea: `0x1800023b4`
- end: `0x180002491`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002040`

## callees

- `0x1800023b4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000243e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000243e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002413`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002423`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002413`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002423`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023ed`

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
0x1800023b4  mov     [rsp-8+arg_18], rbx
0x1800023b9  push    rbp
0x1800023ba  mov     rbp, rsp
0x1800023bd  sub     rsp, 20h
0x1800023c1  xor     eax, eax
0x1800023c3  mov     rbx, 2B992DDFA232h
0x1800023cd  mov     [rbp+arg_0], rax
0x1800023d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800023d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800023d9  mov     rax, cs:__security_cookie
0x1800023e0  cmp     rax, rbx
0x1800023e3  jnz     loc_18000247C
0x1800023e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800023ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800023f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800023f7  mov     [rbp+arg_0], rax
0x1800023fb  call    cs:__imp_GetCurrentProcessId
0x180002401  mov     eax, eax
0x180002403  xor     [rbp+arg_0], rax
0x180002407  call    cs:__imp_GetCurrentThreadId
0x18000240d  mov     eax, eax
0x18000240f  xor     [rbp+arg_0], rax
0x180002413  call    cs:__imp_GetTickCount
0x180002419  mov     eax, eax
0x18000241b  shl     rax, 18h
0x18000241f  xor     [rbp+arg_0], rax
0x180002423  call    cs:__imp_GetTickCount
0x180002429  mov     eax, eax
0x18000242b  lea     rcx, [rbp+arg_0]
0x18000242f  xor     rax, [rbp+arg_0]
0x180002433  xor     rax, rcx
0x180002436  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000243a  mov     [rbp+arg_0], rax
0x18000243e  call    cs:__imp_QueryPerformanceCounter
0x180002444  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002447  mov     rcx, 0FFFFFFFFFFFFh
0x180002451  shl     rax, 20h
0x180002455  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002459  xor     rax, [rbp+arg_0]
0x18000245d  and     rax, rcx
0x180002460  mov     rcx, rax
0x180002463  cmp     rax, rbx
0x180002466  jnz     short loc_180002475
0x180002468  mov     rax, 2B992DDFA233h
0x180002472  mov     rcx, rax
0x180002475  mov     cs:__security_cookie, rcx
0x18000247c  mov     rbx, [rsp+20h+arg_18]
0x180002481  not     rax
0x180002484  mov     cs:__security_cookie_complement, rax
0x18000248b  add     rsp, 20h
0x18000248f  pop     rbp
0x180002490  retn
```
