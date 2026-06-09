# __security_init_cookie

- ea: `0x180005a94`
- end: `0x180005b71`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005720`

## callees

- `0x180005a94`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005b1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005b1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005adb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005adb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005af3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005b03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005af3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005b03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005acd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005acd`

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
0x180005a94  mov     [rsp-8+arg_18], rbx
0x180005a99  push    rbp
0x180005a9a  mov     rbp, rsp
0x180005a9d  sub     rsp, 20h
0x180005aa1  xor     eax, eax
0x180005aa3  mov     rbx, 2B992DDFA232h
0x180005aad  mov     [rbp+arg_0], rax
0x180005ab1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005ab5  mov     qword ptr [rbp+PerformanceCount], rax
0x180005ab9  mov     rax, cs:__security_cookie
0x180005ac0  cmp     rax, rbx
0x180005ac3  jnz     loc_180005B5C
0x180005ac9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005acd  call    cs:__imp_GetSystemTimeAsFileTime
0x180005ad3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005ad7  mov     [rbp+arg_0], rax
0x180005adb  call    cs:__imp_GetCurrentProcessId
0x180005ae1  mov     eax, eax
0x180005ae3  xor     [rbp+arg_0], rax
0x180005ae7  call    cs:__imp_GetCurrentThreadId
0x180005aed  mov     eax, eax
0x180005aef  xor     [rbp+arg_0], rax
0x180005af3  call    cs:__imp_GetTickCount
0x180005af9  mov     eax, eax
0x180005afb  shl     rax, 18h
0x180005aff  xor     [rbp+arg_0], rax
0x180005b03  call    cs:__imp_GetTickCount
0x180005b09  mov     eax, eax
0x180005b0b  lea     rcx, [rbp+arg_0]
0x180005b0f  xor     rax, [rbp+arg_0]
0x180005b13  xor     rax, rcx
0x180005b16  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005b1a  mov     [rbp+arg_0], rax
0x180005b1e  call    cs:__imp_QueryPerformanceCounter
0x180005b24  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005b27  mov     rcx, 0FFFFFFFFFFFFh
0x180005b31  shl     rax, 20h
0x180005b35  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005b39  xor     rax, [rbp+arg_0]
0x180005b3d  and     rax, rcx
0x180005b40  mov     rcx, rax
0x180005b43  cmp     rax, rbx
0x180005b46  jnz     short loc_180005B55
0x180005b48  mov     rax, 2B992DDFA233h
0x180005b52  mov     rcx, rax
0x180005b55  mov     cs:__security_cookie, rcx
0x180005b5c  mov     rbx, [rsp+20h+arg_18]
0x180005b61  not     rax
0x180005b64  mov     cs:__security_cookie_complement, rax
0x180005b6b  add     rsp, 20h
0x180005b6f  pop     rbp
0x180005b70  retn
```
