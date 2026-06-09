# __security_init_cookie

- ea: `0x180002688`
- end: `0x18000273d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002644`

## callees

- `0x180002688`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800026e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800026bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800026bd`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180002688  mov     [rsp-8+arg_10], rbx
0x18000268d  push    rbp
0x18000268e  mov     rbp, rsp
0x180002691  sub     rsp, 30h
0x180002695  mov     rax, cs:__security_cookie
0x18000269c  mov     rbx, 2B992DDFA232h
0x1800026a6  cmp     rax, rbx
0x1800026a9  jnz     short loc_180002728
0x1800026ab  xor     eax, eax
0x1800026ad  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800026b1  mov     [rbp+var_10], rax
0x1800026b5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800026b9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800026bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800026c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800026c7  mov     [rbp+var_10], rax
0x1800026cb  call    cs:__imp_GetCurrentThreadId
0x1800026d1  mov     eax, eax
0x1800026d3  xor     [rbp+var_10], rax
0x1800026d7  call    cs:__imp_GetCurrentProcessId
0x1800026dd  mov     eax, eax
0x1800026df  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800026e3  xor     [rbp+var_10], rax
0x1800026e7  call    cs:__imp_QueryPerformanceCounter
0x1800026ed  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026f0  lea     rcx, [rbp+var_10]
0x1800026f4  shl     rax, 20h
0x1800026f8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026fc  xor     rax, [rbp+var_10]
0x180002700  xor     rax, rcx
0x180002703  mov     rcx, 0FFFFFFFFFFFFh
0x18000270d  and     rax, rcx
0x180002710  mov     rcx, 2B992DDFA233h
0x18000271a  cmp     rax, rbx
0x18000271d  cmovz   rax, rcx
0x180002721  mov     cs:__security_cookie, rax
0x180002728  mov     rbx, [rsp+30h+arg_10]
0x18000272d  not     rax
0x180002730  mov     cs:__security_cookie_complement, rax
0x180002737  add     rsp, 30h
0x18000273b  pop     rbp
0x18000273c  retn
```
