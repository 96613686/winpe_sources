# __security_init_cookie

- ea: `0x180001038`
- end: `0x18000110c`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001038`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800010c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800010c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001090`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001090`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000109c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800010ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000109c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800010ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001076`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001076`

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
0x180001038  mov     [rsp-8+arg_18], rbx
0x18000103d  push    rbp
0x18000103e  mov     rbp, rsp
0x180001041  sub     rsp, 20h
0x180001045  mov     rcx, cs:__security_cookie
0x18000104c  xor     eax, eax
0x18000104e  mov     [rbp+arg_0], rax
0x180001052  mov     rbx, 2B992DDFA232h
0x18000105c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001060  mov     qword ptr [rbp+PerformanceCount], rax
0x180001064  test    rcx, rcx
0x180001067  jz      short loc_180001072
0x180001069  cmp     rcx, rbx
0x18000106c  jnz     loc_1800010F7
0x180001072  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001076  call    cs:__imp_GetSystemTimeAsFileTime
0x18000107c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001080  mov     [rbp+arg_0], rax
0x180001084  call    cs:__imp_GetCurrentProcessId
0x18000108a  mov     eax, eax
0x18000108c  xor     [rbp+arg_0], rax
0x180001090  call    cs:__imp_GetCurrentThreadId
0x180001096  mov     eax, eax
0x180001098  xor     [rbp+arg_0], rax
0x18000109c  call    cs:__imp_GetTickCount
0x1800010a2  mov     eax, eax
0x1800010a4  shl     rax, 18h
0x1800010a8  xor     [rbp+arg_0], rax
0x1800010ac  call    cs:__imp_GetTickCount
0x1800010b2  mov     eax, eax
0x1800010b4  lea     rcx, [rbp+arg_0]
0x1800010b8  xor     rax, [rbp+arg_0]
0x1800010bc  xor     rax, rcx
0x1800010bf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800010c3  mov     [rbp+arg_0], rax
0x1800010c7  call    cs:__imp_QueryPerformanceCounter
0x1800010cd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800010d0  mov     rcx, 0FFFFFFFFFFFFh
0x1800010da  shl     rax, 20h
0x1800010de  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800010e2  xor     rax, [rbp+arg_0]
0x1800010e6  and     rax, rcx
0x1800010e9  mov     rcx, rbx
0x1800010ec  cmovnz  rcx, rax
0x1800010f0  mov     cs:__security_cookie, rcx
0x1800010f7  mov     rbx, [rsp+20h+arg_18]
0x1800010fc  not     rcx
0x1800010ff  mov     cs:__security_cookie_complement, rcx
0x180001106  add     rsp, 20h
0x18000110a  pop     rbp
0x18000110b  retn
```
