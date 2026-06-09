# __security_init_cookie

- ea: `0x180001774`
- end: `0x180001851`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001350`

## callees

- `0x180001774`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800017ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800017ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800017fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800017fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800017c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800017c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800017bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800017bb`

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
0x180001774  mov     [rsp-8+arg_18], rbx
0x180001779  push    rbp
0x18000177a  mov     rbp, rsp
0x18000177d  sub     rsp, 20h
0x180001781  xor     eax, eax
0x180001783  mov     rbx, 2B992DDFA232h
0x18000178d  mov     [rbp+arg_0], rax
0x180001791  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001795  mov     qword ptr [rbp+PerformanceCount], rax
0x180001799  mov     rax, cs:__security_cookie
0x1800017a0  cmp     rax, rbx
0x1800017a3  jnz     loc_18000183C
0x1800017a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800017ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800017b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800017b7  mov     [rbp+arg_0], rax
0x1800017bb  call    cs:__imp_GetCurrentProcessId
0x1800017c1  mov     eax, eax
0x1800017c3  xor     [rbp+arg_0], rax
0x1800017c7  call    cs:__imp_GetCurrentThreadId
0x1800017cd  mov     eax, eax
0x1800017cf  xor     [rbp+arg_0], rax
0x1800017d3  call    cs:__imp_GetTickCount
0x1800017d9  mov     eax, eax
0x1800017db  shl     rax, 18h
0x1800017df  xor     [rbp+arg_0], rax
0x1800017e3  call    cs:__imp_GetTickCount
0x1800017e9  mov     eax, eax
0x1800017eb  lea     rcx, [rbp+arg_0]
0x1800017ef  xor     rax, [rbp+arg_0]
0x1800017f3  xor     rax, rcx
0x1800017f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800017fa  mov     [rbp+arg_0], rax
0x1800017fe  call    cs:__imp_QueryPerformanceCounter
0x180001804  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001807  mov     rcx, 0FFFFFFFFFFFFh
0x180001811  shl     rax, 20h
0x180001815  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001819  xor     rax, [rbp+arg_0]
0x18000181d  and     rax, rcx
0x180001820  mov     rcx, rax
0x180001823  cmp     rax, rbx
0x180001826  jnz     short loc_180001835
0x180001828  mov     rax, 2B992DDFA233h
0x180001832  mov     rcx, rax
0x180001835  mov     cs:__security_cookie, rcx
0x18000183c  mov     rbx, [rsp+20h+arg_18]
0x180001841  not     rax
0x180001844  mov     cs:__security_cookie_complement, rax
0x18000184b  add     rsp, 20h
0x18000184f  pop     rbp
0x180001850  retn
```
