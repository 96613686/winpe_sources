# __security_init_cookie

- ea: `0x1800025c8`
- end: `0x18000269c`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800025a8`

## callees

- `0x1800025c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002614`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002614`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002620`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002657`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002657`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000262c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000263c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000262c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000263c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002606`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002606`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (_FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800025c8  mov     [rsp-8+arg_18], rbx
0x1800025cd  push    rbp
0x1800025ce  mov     rbp, rsp
0x1800025d1  sub     rsp, 20h
0x1800025d5  mov     rcx, cs:__security_cookie
0x1800025dc  xor     eax, eax
0x1800025de  mov     [rbp+arg_0], rax
0x1800025e2  mov     rbx, 2B992DDFA232h
0x1800025ec  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800025f0  mov     qword ptr [rbp+PerformanceCount], rax
0x1800025f4  test    rcx, rcx
0x1800025f7  jz      short loc_180002602
0x1800025f9  cmp     rcx, rbx
0x1800025fc  jnz     loc_180002687
0x180002602  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002606  call    cs:__imp_GetSystemTimeAsFileTime
0x18000260c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002610  mov     [rbp+arg_0], rax
0x180002614  call    cs:__imp_GetCurrentProcessId
0x18000261a  mov     eax, eax
0x18000261c  xor     [rbp+arg_0], rax
0x180002620  call    cs:__imp_GetCurrentThreadId
0x180002626  mov     eax, eax
0x180002628  xor     [rbp+arg_0], rax
0x18000262c  call    cs:__imp_GetTickCount
0x180002632  mov     eax, eax
0x180002634  shl     rax, 18h
0x180002638  xor     [rbp+arg_0], rax
0x18000263c  call    cs:__imp_GetTickCount
0x180002642  mov     eax, eax
0x180002644  lea     rcx, [rbp+arg_0]
0x180002648  xor     rax, [rbp+arg_0]
0x18000264c  xor     rax, rcx
0x18000264f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002653  mov     [rbp+arg_0], rax
0x180002657  call    cs:__imp_QueryPerformanceCounter
0x18000265d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002660  mov     rcx, 0FFFFFFFFFFFFh
0x18000266a  shl     rax, 20h
0x18000266e  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002672  xor     rax, [rbp+arg_0]
0x180002676  and     rax, rcx
0x180002679  mov     rcx, rbx
0x18000267c  cmovnz  rcx, rax
0x180002680  mov     cs:__security_cookie, rcx
0x180002687  mov     rbx, [rsp+20h+arg_18]
0x18000268c  not     rcx
0x18000268f  mov     cs:__security_cookie_complement, rcx
0x180002696  add     rsp, 20h
0x18000269a  pop     rbp
0x18000269b  retn
```
