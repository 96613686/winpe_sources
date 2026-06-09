# __security_init_cookie

- ea: `0x1800fea80`
- end: `0x1800feb35`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800fe630`

## callees

- `0x1800fea80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800feac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800feac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800feacf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800feacf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800feab5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800feab5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800feadf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800feadf`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800fea80  mov     [rsp-8+arg_10], rbx
0x1800fea85  push    rbp
0x1800fea86  mov     rbp, rsp
0x1800fea89  sub     rsp, 30h
0x1800fea8d  mov     rax, cs:__security_cookie
0x1800fea94  mov     rbx, 2B992DDFA232h
0x1800fea9e  cmp     rax, rbx
0x1800feaa1  jnz     short loc_1800FEB20
0x1800feaa3  xor     eax, eax
0x1800feaa5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800feaa9  mov     [rbp+var_10], rax
0x1800feaad  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800feab1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800feab5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800feabb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800feabf  mov     [rbp+var_10], rax
0x1800feac3  call    cs:__imp_GetCurrentThreadId
0x1800feac9  mov     eax, eax
0x1800feacb  xor     [rbp+var_10], rax
0x1800feacf  call    cs:__imp_GetCurrentProcessId
0x1800fead5  mov     eax, eax
0x1800fead7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800feadb  xor     [rbp+var_10], rax
0x1800feadf  call    cs:__imp_QueryPerformanceCounter
0x1800feae5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800feae8  lea     rcx, [rbp+var_10]
0x1800feaec  shl     rax, 20h
0x1800feaf0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800feaf4  xor     rax, [rbp+var_10]
0x1800feaf8  xor     rax, rcx
0x1800feafb  mov     rcx, 0FFFFFFFFFFFFh
0x1800feb05  and     rax, rcx
0x1800feb08  mov     rcx, 2B992DDFA233h
0x1800feb12  cmp     rax, rbx
0x1800feb15  cmovz   rax, rcx
0x1800feb19  mov     cs:__security_cookie, rax
0x1800feb20  mov     rbx, [rsp+30h+arg_10]
0x1800feb25  not     rax
0x1800feb28  mov     cs:__security_cookie_complement, rax
0x1800feb2f  add     rsp, 30h
0x1800feb33  pop     rbp
0x1800feb34  retn
```
