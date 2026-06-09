# __security_init_cookie

- ea: `0x1800041b4`
- end: `0x180004291`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a40`
- `0x180003c98`

## callees

- `0x1800041b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800041fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800041fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004207`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004213`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004223`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004213`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004223`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800041ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800041ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000423e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000423e`

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
0x1800041b4  mov     [rsp-8+arg_18], rbx
0x1800041b9  push    rbp
0x1800041ba  mov     rbp, rsp
0x1800041bd  sub     rsp, 20h
0x1800041c1  xor     eax, eax
0x1800041c3  mov     rbx, 2B992DDFA232h
0x1800041cd  mov     [rbp+arg_0], rax
0x1800041d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800041d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800041d9  mov     rax, cs:__security_cookie
0x1800041e0  cmp     rax, rbx
0x1800041e3  jnz     loc_18000427C
0x1800041e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800041ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800041f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800041f7  mov     [rbp+arg_0], rax
0x1800041fb  call    cs:__imp_GetCurrentProcessId
0x180004201  mov     eax, eax
0x180004203  xor     [rbp+arg_0], rax
0x180004207  call    cs:__imp_GetCurrentThreadId
0x18000420d  mov     eax, eax
0x18000420f  xor     [rbp+arg_0], rax
0x180004213  call    cs:__imp_GetTickCount
0x180004219  mov     eax, eax
0x18000421b  shl     rax, 18h
0x18000421f  xor     [rbp+arg_0], rax
0x180004223  call    cs:__imp_GetTickCount
0x180004229  mov     eax, eax
0x18000422b  lea     rcx, [rbp+arg_0]
0x18000422f  xor     rax, [rbp+arg_0]
0x180004233  xor     rax, rcx
0x180004236  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000423a  mov     [rbp+arg_0], rax
0x18000423e  call    cs:__imp_QueryPerformanceCounter
0x180004244  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004247  mov     rcx, 0FFFFFFFFFFFFh
0x180004251  shl     rax, 20h
0x180004255  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004259  xor     rax, [rbp+arg_0]
0x18000425d  and     rax, rcx
0x180004260  mov     rcx, rax
0x180004263  cmp     rax, rbx
0x180004266  jnz     short loc_180004275
0x180004268  mov     rax, 2B992DDFA233h
0x180004272  mov     rcx, rax
0x180004275  mov     cs:__security_cookie, rcx
0x18000427c  mov     rbx, [rsp+20h+arg_18]
0x180004281  not     rax
0x180004284  mov     cs:__security_cookie_complement, rax
0x18000428b  add     rsp, 20h
0x18000428f  pop     rbp
0x180004290  retn
```
