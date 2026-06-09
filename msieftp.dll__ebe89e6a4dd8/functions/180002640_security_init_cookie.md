# __security_init_cookie

- ea: `0x180002640`
- end: `0x1800026f5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x180002640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000268f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000268f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002675`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002675`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000269f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000269f`

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
0x180002640  mov     [rsp-8+arg_10], rbx
0x180002645  push    rbp
0x180002646  mov     rbp, rsp
0x180002649  sub     rsp, 30h
0x18000264d  mov     rax, cs:__security_cookie
0x180002654  mov     rbx, 2B992DDFA232h
0x18000265e  cmp     rax, rbx
0x180002661  jnz     short loc_1800026E0
0x180002663  xor     eax, eax
0x180002665  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002669  mov     [rbp+var_10], rax
0x18000266d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002671  mov     qword ptr [rbp+PerformanceCount], rax
0x180002675  call    cs:__imp_GetSystemTimeAsFileTime
0x18000267b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000267f  mov     [rbp+var_10], rax
0x180002683  call    cs:__imp_GetCurrentThreadId
0x180002689  mov     eax, eax
0x18000268b  xor     [rbp+var_10], rax
0x18000268f  call    cs:__imp_GetCurrentProcessId
0x180002695  mov     eax, eax
0x180002697  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000269b  xor     [rbp+var_10], rax
0x18000269f  call    cs:__imp_QueryPerformanceCounter
0x1800026a5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026a8  lea     rcx, [rbp+var_10]
0x1800026ac  shl     rax, 20h
0x1800026b0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026b4  xor     rax, [rbp+var_10]
0x1800026b8  xor     rax, rcx
0x1800026bb  mov     rcx, 0FFFFFFFFFFFFh
0x1800026c5  and     rax, rcx
0x1800026c8  mov     rcx, 2B992DDFA233h
0x1800026d2  cmp     rax, rbx
0x1800026d5  cmovz   rax, rcx
0x1800026d9  mov     cs:__security_cookie, rax
0x1800026e0  mov     rbx, [rsp+30h+arg_10]
0x1800026e5  not     rax
0x1800026e8  mov     cs:__security_cookie_complement, rax
0x1800026ef  add     rsp, 30h
0x1800026f3  pop     rbp
0x1800026f4  retn
```
