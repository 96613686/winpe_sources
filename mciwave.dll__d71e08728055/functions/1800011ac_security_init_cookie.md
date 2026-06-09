# __security_init_cookie

- ea: `0x1800011ac`
- end: `0x180001280`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000118c`

## callees

- `0x1800011ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001204`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001204`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800011f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800011f8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000123b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000123b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001210`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001220`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001210`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001220`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800011ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800011ea`

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
0x1800011ac  mov     [rsp-8+arg_18], rbx
0x1800011b1  push    rbp
0x1800011b2  mov     rbp, rsp
0x1800011b5  sub     rsp, 20h
0x1800011b9  mov     rcx, cs:__security_cookie
0x1800011c0  xor     eax, eax
0x1800011c2  mov     [rbp+arg_0], rax
0x1800011c6  mov     rbx, 2B992DDFA232h
0x1800011d0  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800011d4  mov     qword ptr [rbp+PerformanceCount], rax
0x1800011d8  test    rcx, rcx
0x1800011db  jz      short loc_1800011E6
0x1800011dd  cmp     rcx, rbx
0x1800011e0  jnz     loc_18000126B
0x1800011e6  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800011ea  call    cs:__imp_GetSystemTimeAsFileTime
0x1800011f0  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800011f4  mov     [rbp+arg_0], rax
0x1800011f8  call    cs:__imp_GetCurrentProcessId
0x1800011fe  mov     eax, eax
0x180001200  xor     [rbp+arg_0], rax
0x180001204  call    cs:__imp_GetCurrentThreadId
0x18000120a  mov     eax, eax
0x18000120c  xor     [rbp+arg_0], rax
0x180001210  call    cs:__imp_GetTickCount
0x180001216  mov     eax, eax
0x180001218  shl     rax, 18h
0x18000121c  xor     [rbp+arg_0], rax
0x180001220  call    cs:__imp_GetTickCount
0x180001226  mov     eax, eax
0x180001228  lea     rcx, [rbp+arg_0]
0x18000122c  xor     rax, [rbp+arg_0]
0x180001230  xor     rax, rcx
0x180001233  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001237  mov     [rbp+arg_0], rax
0x18000123b  call    cs:__imp_QueryPerformanceCounter
0x180001241  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001244  mov     rcx, 0FFFFFFFFFFFFh
0x18000124e  shl     rax, 20h
0x180001252  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001256  xor     rax, [rbp+arg_0]
0x18000125a  and     rax, rcx
0x18000125d  mov     rcx, rbx
0x180001260  cmovnz  rcx, rax
0x180001264  mov     cs:__security_cookie, rcx
0x18000126b  mov     rbx, [rsp+20h+arg_18]
0x180001270  not     rcx
0x180001273  mov     cs:__security_cookie_complement, rcx
0x18000127a  add     rsp, 20h
0x18000127e  pop     rbp
0x18000127f  retn
```
