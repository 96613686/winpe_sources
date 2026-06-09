# __security_init_cookie

- ea: `0x1800055f4`
- end: `0x1800056d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005280`

## callees

- `0x1800055f4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000567e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000567e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000563b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000563b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000562d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000562d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005653`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005663`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005653`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005663`

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
0x1800055f4  mov     [rsp-8+arg_18], rbx
0x1800055f9  push    rbp
0x1800055fa  mov     rbp, rsp
0x1800055fd  sub     rsp, 20h
0x180005601  xor     eax, eax
0x180005603  mov     rbx, 2B992DDFA232h
0x18000560d  mov     [rbp+arg_0], rax
0x180005611  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005615  mov     qword ptr [rbp+PerformanceCount], rax
0x180005619  mov     rax, cs:__security_cookie
0x180005620  cmp     rax, rbx
0x180005623  jnz     loc_1800056BC
0x180005629  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000562d  call    cs:__imp_GetSystemTimeAsFileTime
0x180005633  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005637  mov     [rbp+arg_0], rax
0x18000563b  call    cs:__imp_GetCurrentProcessId
0x180005641  mov     eax, eax
0x180005643  xor     [rbp+arg_0], rax
0x180005647  call    cs:__imp_GetCurrentThreadId
0x18000564d  mov     eax, eax
0x18000564f  xor     [rbp+arg_0], rax
0x180005653  call    cs:__imp_GetTickCount
0x180005659  mov     eax, eax
0x18000565b  shl     rax, 18h
0x18000565f  xor     [rbp+arg_0], rax
0x180005663  call    cs:__imp_GetTickCount
0x180005669  mov     eax, eax
0x18000566b  lea     rcx, [rbp+arg_0]
0x18000566f  xor     rax, [rbp+arg_0]
0x180005673  xor     rax, rcx
0x180005676  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000567a  mov     [rbp+arg_0], rax
0x18000567e  call    cs:__imp_QueryPerformanceCounter
0x180005684  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005687  mov     rcx, 0FFFFFFFFFFFFh
0x180005691  shl     rax, 20h
0x180005695  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005699  xor     rax, [rbp+arg_0]
0x18000569d  and     rax, rcx
0x1800056a0  mov     rcx, rax
0x1800056a3  cmp     rax, rbx
0x1800056a6  jnz     short loc_1800056B5
0x1800056a8  mov     rax, 2B992DDFA233h
0x1800056b2  mov     rcx, rax
0x1800056b5  mov     cs:__security_cookie, rcx
0x1800056bc  mov     rbx, [rsp+20h+arg_18]
0x1800056c1  not     rax
0x1800056c4  mov     cs:__security_cookie_complement, rax
0x1800056cb  add     rsp, 20h
0x1800056cf  pop     rbp
0x1800056d0  retn
```
