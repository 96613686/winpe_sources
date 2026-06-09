# __security_init_cookie

- ea: `0x180018d34`
- end: `0x180018e11`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800186c0`

## callees

- `0x180018d34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018d7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180018d7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018d87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018d6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018d6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018d93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018da3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018d93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018da3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180018dbe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180018dbe`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180018d34  mov     [rsp-8+arg_18], rbx
0x180018d39  push    rbp
0x180018d3a  mov     rbp, rsp
0x180018d3d  sub     rsp, 20h
0x180018d41  xor     eax, eax
0x180018d43  mov     rbx, 2B992DDFA232h
0x180018d4d  mov     [rbp+arg_0], rax
0x180018d51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180018d55  mov     qword ptr [rbp+PerformanceCount], rax
0x180018d59  mov     rax, cs:__security_cookie
0x180018d60  cmp     rax, rbx
0x180018d63  jnz     loc_180018DFC
0x180018d69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180018d6d  call    cs:__imp_GetSystemTimeAsFileTime
0x180018d73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180018d77  mov     [rbp+arg_0], rax
0x180018d7b  call    cs:__imp_GetCurrentProcessId
0x180018d81  mov     eax, eax
0x180018d83  xor     [rbp+arg_0], rax
0x180018d87  call    cs:__imp_GetCurrentThreadId
0x180018d8d  mov     eax, eax
0x180018d8f  xor     [rbp+arg_0], rax
0x180018d93  call    cs:__imp_GetTickCount
0x180018d99  mov     eax, eax
0x180018d9b  shl     rax, 18h
0x180018d9f  xor     [rbp+arg_0], rax
0x180018da3  call    cs:__imp_GetTickCount
0x180018da9  mov     eax, eax
0x180018dab  lea     rcx, [rbp+arg_0]
0x180018daf  xor     rax, [rbp+arg_0]
0x180018db3  xor     rax, rcx
0x180018db6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180018dba  mov     [rbp+arg_0], rax
0x180018dbe  call    cs:__imp_QueryPerformanceCounter
0x180018dc4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180018dc7  mov     rcx, 0FFFFFFFFFFFFh
0x180018dd1  shl     rax, 20h
0x180018dd5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180018dd9  xor     rax, [rbp+arg_0]
0x180018ddd  and     rax, rcx
0x180018de0  mov     rcx, rax
0x180018de3  cmp     rax, rbx
0x180018de6  jnz     short loc_180018DF5
0x180018de8  mov     rax, 2B992DDFA233h
0x180018df2  mov     rcx, rax
0x180018df5  mov     cs:__security_cookie, rcx
0x180018dfc  mov     rbx, [rsp+20h+arg_18]
0x180018e01  not     rax
0x180018e04  mov     cs:__security_cookie_complement, rax
0x180018e0b  add     rsp, 20h
0x180018e0f  pop     rbp
0x180018e10  retn
```
