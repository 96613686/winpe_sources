# __security_init_cookie

- ea: `0x180005af4`
- end: `0x180005bd1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800055b0`

## callees

- `0x180005af4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005b63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005b53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005b63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005b7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005b7e`

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
0x180005af4  mov     [rsp-8+arg_18], rbx
0x180005af9  push    rbp
0x180005afa  mov     rbp, rsp
0x180005afd  sub     rsp, 20h
0x180005b01  xor     eax, eax
0x180005b03  mov     rbx, 2B992DDFA232h
0x180005b0d  mov     [rbp+arg_0], rax
0x180005b11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005b15  mov     qword ptr [rbp+PerformanceCount], rax
0x180005b19  mov     rax, cs:__security_cookie
0x180005b20  cmp     rax, rbx
0x180005b23  jnz     loc_180005BBC
0x180005b29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005b2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180005b33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005b37  mov     [rbp+arg_0], rax
0x180005b3b  call    cs:__imp_GetCurrentProcessId
0x180005b41  mov     eax, eax
0x180005b43  xor     [rbp+arg_0], rax
0x180005b47  call    cs:__imp_GetCurrentThreadId
0x180005b4d  mov     eax, eax
0x180005b4f  xor     [rbp+arg_0], rax
0x180005b53  call    cs:__imp_GetTickCount
0x180005b59  mov     eax, eax
0x180005b5b  shl     rax, 18h
0x180005b5f  xor     [rbp+arg_0], rax
0x180005b63  call    cs:__imp_GetTickCount
0x180005b69  mov     eax, eax
0x180005b6b  lea     rcx, [rbp+arg_0]
0x180005b6f  xor     rax, [rbp+arg_0]
0x180005b73  xor     rax, rcx
0x180005b76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005b7a  mov     [rbp+arg_0], rax
0x180005b7e  call    cs:__imp_QueryPerformanceCounter
0x180005b84  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005b87  mov     rcx, 0FFFFFFFFFFFFh
0x180005b91  shl     rax, 20h
0x180005b95  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005b99  xor     rax, [rbp+arg_0]
0x180005b9d  and     rax, rcx
0x180005ba0  mov     rcx, rax
0x180005ba3  cmp     rax, rbx
0x180005ba6  jnz     short loc_180005BB5
0x180005ba8  mov     rax, 2B992DDFA233h
0x180005bb2  mov     rcx, rax
0x180005bb5  mov     cs:__security_cookie, rcx
0x180005bbc  mov     rbx, [rsp+20h+arg_18]
0x180005bc1  not     rax
0x180005bc4  mov     cs:__security_cookie_complement, rax
0x180005bcb  add     rsp, 20h
0x180005bcf  pop     rbp
0x180005bd0  retn
```
