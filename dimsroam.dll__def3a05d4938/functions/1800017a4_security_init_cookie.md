# __security_init_cookie

- ea: `0x1800017a4`
- end: `0x180001881`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001450`

## callees

- `0x1800017a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800017eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800017eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800017f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800017f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800017dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800017dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001803`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001813`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001803`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001813`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000182e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000182e`

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
0x1800017a4  mov     [rsp-8+arg_18], rbx
0x1800017a9  push    rbp
0x1800017aa  mov     rbp, rsp
0x1800017ad  sub     rsp, 20h
0x1800017b1  xor     eax, eax
0x1800017b3  mov     rbx, 2B992DDFA232h
0x1800017bd  mov     [rbp+arg_0], rax
0x1800017c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800017c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800017c9  mov     rax, cs:__security_cookie
0x1800017d0  cmp     rax, rbx
0x1800017d3  jnz     loc_18000186C
0x1800017d9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800017dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800017e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800017e7  mov     [rbp+arg_0], rax
0x1800017eb  call    cs:__imp_GetCurrentProcessId
0x1800017f1  mov     eax, eax
0x1800017f3  xor     [rbp+arg_0], rax
0x1800017f7  call    cs:__imp_GetCurrentThreadId
0x1800017fd  mov     eax, eax
0x1800017ff  xor     [rbp+arg_0], rax
0x180001803  call    cs:__imp_GetTickCount
0x180001809  mov     eax, eax
0x18000180b  shl     rax, 18h
0x18000180f  xor     [rbp+arg_0], rax
0x180001813  call    cs:__imp_GetTickCount
0x180001819  mov     eax, eax
0x18000181b  lea     rcx, [rbp+arg_0]
0x18000181f  xor     rax, [rbp+arg_0]
0x180001823  xor     rax, rcx
0x180001826  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000182a  mov     [rbp+arg_0], rax
0x18000182e  call    cs:__imp_QueryPerformanceCounter
0x180001834  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001837  mov     rcx, 0FFFFFFFFFFFFh
0x180001841  shl     rax, 20h
0x180001845  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001849  xor     rax, [rbp+arg_0]
0x18000184d  and     rax, rcx
0x180001850  mov     rcx, rax
0x180001853  cmp     rax, rbx
0x180001856  jnz     short loc_180001865
0x180001858  mov     rax, 2B992DDFA233h
0x180001862  mov     rcx, rax
0x180001865  mov     cs:__security_cookie, rcx
0x18000186c  mov     rbx, [rsp+20h+arg_18]
0x180001871  not     rax
0x180001874  mov     cs:__security_cookie_complement, rax
0x18000187b  add     rsp, 20h
0x18000187f  pop     rbp
0x180001880  retn
```
