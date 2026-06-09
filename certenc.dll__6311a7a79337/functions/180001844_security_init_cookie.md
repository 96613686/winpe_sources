# __security_init_cookie

- ea: `0x180001844`
- end: `0x180001921`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012d0`

## callees

- `0x180001844`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000187d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000187d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000188b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000188b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001897`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800018ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800018ce`

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
0x180001844  mov     [rsp-8+arg_18], rbx
0x180001849  push    rbp
0x18000184a  mov     rbp, rsp
0x18000184d  sub     rsp, 20h
0x180001851  xor     eax, eax
0x180001853  mov     rbx, 2B992DDFA232h
0x18000185d  mov     [rbp+arg_0], rax
0x180001861  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001865  mov     qword ptr [rbp+PerformanceCount], rax
0x180001869  mov     rax, cs:__security_cookie
0x180001870  cmp     rax, rbx
0x180001873  jnz     loc_18000190C
0x180001879  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000187d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001883  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001887  mov     [rbp+arg_0], rax
0x18000188b  call    cs:__imp_GetCurrentProcessId
0x180001891  mov     eax, eax
0x180001893  xor     [rbp+arg_0], rax
0x180001897  call    cs:__imp_GetCurrentThreadId
0x18000189d  mov     eax, eax
0x18000189f  xor     [rbp+arg_0], rax
0x1800018a3  call    cs:__imp_GetTickCount
0x1800018a9  mov     eax, eax
0x1800018ab  shl     rax, 18h
0x1800018af  xor     [rbp+arg_0], rax
0x1800018b3  call    cs:__imp_GetTickCount
0x1800018b9  mov     eax, eax
0x1800018bb  lea     rcx, [rbp+arg_0]
0x1800018bf  xor     rax, [rbp+arg_0]
0x1800018c3  xor     rax, rcx
0x1800018c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800018ca  mov     [rbp+arg_0], rax
0x1800018ce  call    cs:__imp_QueryPerformanceCounter
0x1800018d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800018d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800018e1  shl     rax, 20h
0x1800018e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800018e9  xor     rax, [rbp+arg_0]
0x1800018ed  and     rax, rcx
0x1800018f0  mov     rcx, rax
0x1800018f3  cmp     rax, rbx
0x1800018f6  jnz     short loc_180001905
0x1800018f8  mov     rax, 2B992DDFA233h
0x180001902  mov     rcx, rax
0x180001905  mov     cs:__security_cookie, rcx
0x18000190c  mov     rbx, [rsp+20h+arg_18]
0x180001911  not     rax
0x180001914  mov     cs:__security_cookie_complement, rax
0x18000191b  add     rsp, 20h
0x18000191f  pop     rbp
0x180001920  retn
```
