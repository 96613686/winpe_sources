# __security_init_cookie

- ea: `0x180019b64`
- end: `0x180019c41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800194f0`

## callees

- `0x180019b64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019bab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019bab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019b9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019b9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019bc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019bd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019bc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019bd3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019bee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019bee`

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
0x180019b64  mov     [rsp-8+arg_18], rbx
0x180019b69  push    rbp
0x180019b6a  mov     rbp, rsp
0x180019b6d  sub     rsp, 20h
0x180019b71  xor     eax, eax
0x180019b73  mov     rbx, 2B992DDFA232h
0x180019b7d  mov     [rbp+arg_0], rax
0x180019b81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180019b85  mov     qword ptr [rbp+PerformanceCount], rax
0x180019b89  mov     rax, cs:__security_cookie
0x180019b90  cmp     rax, rbx
0x180019b93  jnz     loc_180019C2C
0x180019b99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019b9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180019ba3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180019ba7  mov     [rbp+arg_0], rax
0x180019bab  call    cs:__imp_GetCurrentProcessId
0x180019bb1  mov     eax, eax
0x180019bb3  xor     [rbp+arg_0], rax
0x180019bb7  call    cs:__imp_GetCurrentThreadId
0x180019bbd  mov     eax, eax
0x180019bbf  xor     [rbp+arg_0], rax
0x180019bc3  call    cs:__imp_GetTickCount
0x180019bc9  mov     eax, eax
0x180019bcb  shl     rax, 18h
0x180019bcf  xor     [rbp+arg_0], rax
0x180019bd3  call    cs:__imp_GetTickCount
0x180019bd9  mov     eax, eax
0x180019bdb  lea     rcx, [rbp+arg_0]
0x180019bdf  xor     rax, [rbp+arg_0]
0x180019be3  xor     rax, rcx
0x180019be6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180019bea  mov     [rbp+arg_0], rax
0x180019bee  call    cs:__imp_QueryPerformanceCounter
0x180019bf4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180019bf7  mov     rcx, 0FFFFFFFFFFFFh
0x180019c01  shl     rax, 20h
0x180019c05  xor     rax, qword ptr [rbp+PerformanceCount]
0x180019c09  xor     rax, [rbp+arg_0]
0x180019c0d  and     rax, rcx
0x180019c10  mov     rcx, rax
0x180019c13  cmp     rax, rbx
0x180019c16  jnz     short loc_180019C25
0x180019c18  mov     rax, 2B992DDFA233h
0x180019c22  mov     rcx, rax
0x180019c25  mov     cs:__security_cookie, rcx
0x180019c2c  mov     rbx, [rsp+20h+arg_18]
0x180019c31  not     rax
0x180019c34  mov     cs:__security_cookie_complement, rax
0x180019c3b  add     rsp, 20h
0x180019c3f  pop     rbp
0x180019c40  retn
```
