# __security_init_cookie

- ea: `0x180001834`
- end: `0x180001911`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012d0`

## callees

- `0x180001834`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001893`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001893`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000186d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000186d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000187b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000187b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001887`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800018be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800018be`

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
0x180001834  mov     [rsp-8+arg_18], rbx
0x180001839  push    rbp
0x18000183a  mov     rbp, rsp
0x18000183d  sub     rsp, 20h
0x180001841  xor     eax, eax
0x180001843  mov     rbx, 2B992DDFA232h
0x18000184d  mov     [rbp+arg_0], rax
0x180001851  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001855  mov     qword ptr [rbp+PerformanceCount], rax
0x180001859  mov     rax, cs:__security_cookie
0x180001860  cmp     rax, rbx
0x180001863  jnz     loc_1800018FC
0x180001869  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000186d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001873  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001877  mov     [rbp+arg_0], rax
0x18000187b  call    cs:__imp_GetCurrentProcessId
0x180001881  mov     eax, eax
0x180001883  xor     [rbp+arg_0], rax
0x180001887  call    cs:__imp_GetCurrentThreadId
0x18000188d  mov     eax, eax
0x18000188f  xor     [rbp+arg_0], rax
0x180001893  call    cs:__imp_GetTickCount
0x180001899  mov     eax, eax
0x18000189b  shl     rax, 18h
0x18000189f  xor     [rbp+arg_0], rax
0x1800018a3  call    cs:__imp_GetTickCount
0x1800018a9  mov     eax, eax
0x1800018ab  lea     rcx, [rbp+arg_0]
0x1800018af  xor     rax, [rbp+arg_0]
0x1800018b3  xor     rax, rcx
0x1800018b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800018ba  mov     [rbp+arg_0], rax
0x1800018be  call    cs:__imp_QueryPerformanceCounter
0x1800018c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800018c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800018d1  shl     rax, 20h
0x1800018d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800018d9  xor     rax, [rbp+arg_0]
0x1800018dd  and     rax, rcx
0x1800018e0  mov     rcx, rax
0x1800018e3  cmp     rax, rbx
0x1800018e6  jnz     short loc_1800018F5
0x1800018e8  mov     rax, 2B992DDFA233h
0x1800018f2  mov     rcx, rax
0x1800018f5  mov     cs:__security_cookie, rcx
0x1800018fc  mov     rbx, [rsp+20h+arg_18]
0x180001901  not     rax
0x180001904  mov     cs:__security_cookie_complement, rax
0x18000190b  add     rsp, 20h
0x18000190f  pop     rbp
0x180001910  retn
```
