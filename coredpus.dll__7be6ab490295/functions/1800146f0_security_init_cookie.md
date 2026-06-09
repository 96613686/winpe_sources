# __security_init_cookie

- ea: `0x1800146f0`
- end: `0x1800147a5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800142e0`

## callees

- `0x1800146f0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001474f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001474f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001473f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001473f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014733`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014733`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014725`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014725`

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
0x1800146f0  mov     [rsp-8+arg_10], rbx
0x1800146f5  push    rbp
0x1800146f6  mov     rbp, rsp
0x1800146f9  sub     rsp, 30h
0x1800146fd  mov     rax, cs:__security_cookie
0x180014704  mov     rbx, 2B992DDFA232h
0x18001470e  cmp     rax, rbx
0x180014711  jnz     short loc_180014790
0x180014713  xor     eax, eax
0x180014715  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014719  mov     [rbp+var_10], rax
0x18001471d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180014721  mov     qword ptr [rbp+PerformanceCount], rax
0x180014725  call    cs:__imp_GetSystemTimeAsFileTime
0x18001472b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001472f  mov     [rbp+var_10], rax
0x180014733  call    cs:__imp_GetCurrentThreadId
0x180014739  mov     eax, eax
0x18001473b  xor     [rbp+var_10], rax
0x18001473f  call    cs:__imp_GetCurrentProcessId
0x180014745  mov     eax, eax
0x180014747  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001474b  xor     [rbp+var_10], rax
0x18001474f  call    cs:__imp_QueryPerformanceCounter
0x180014755  mov     eax, dword ptr [rbp+PerformanceCount]
0x180014758  lea     rcx, [rbp+var_10]
0x18001475c  shl     rax, 20h
0x180014760  xor     rax, qword ptr [rbp+PerformanceCount]
0x180014764  xor     rax, [rbp+var_10]
0x180014768  xor     rax, rcx
0x18001476b  mov     rcx, 0FFFFFFFFFFFFh
0x180014775  and     rax, rcx
0x180014778  mov     rcx, 2B992DDFA233h
0x180014782  cmp     rax, rbx
0x180014785  cmovz   rax, rcx
0x180014789  mov     cs:__security_cookie, rax
0x180014790  mov     rbx, [rsp+30h+arg_10]
0x180014795  not     rax
0x180014798  mov     cs:__security_cookie_complement, rax
0x18001479f  add     rsp, 30h
0x1800147a3  pop     rbp
0x1800147a4  retn
```
