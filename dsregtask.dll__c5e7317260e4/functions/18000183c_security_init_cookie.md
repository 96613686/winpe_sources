# __security_init_cookie

- ea: `0x18000183c`
- end: `0x1800018f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001410`

## callees

- `0x18000183c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000187f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000187f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000188b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000188b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000189b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000189b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001871`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001871`

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
0x18000183c  mov     [rsp-8+arg_10], rbx
0x180001841  push    rbp
0x180001842  mov     rbp, rsp
0x180001845  sub     rsp, 30h
0x180001849  mov     rax, cs:__security_cookie
0x180001850  mov     rbx, 2B992DDFA232h
0x18000185a  cmp     rax, rbx
0x18000185d  jnz     short loc_1800018DC
0x18000185f  xor     eax, eax
0x180001861  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001865  mov     [rbp+var_10], rax
0x180001869  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000186d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001871  call    cs:__imp_GetSystemTimeAsFileTime
0x180001877  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000187b  mov     [rbp+var_10], rax
0x18000187f  call    cs:__imp_GetCurrentThreadId
0x180001885  mov     eax, eax
0x180001887  xor     [rbp+var_10], rax
0x18000188b  call    cs:__imp_GetCurrentProcessId
0x180001891  mov     eax, eax
0x180001893  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001897  xor     [rbp+var_10], rax
0x18000189b  call    cs:__imp_QueryPerformanceCounter
0x1800018a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800018a4  lea     rcx, [rbp+var_10]
0x1800018a8  shl     rax, 20h
0x1800018ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800018b0  xor     rax, [rbp+var_10]
0x1800018b4  xor     rax, rcx
0x1800018b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800018c1  and     rax, rcx
0x1800018c4  mov     rcx, 2B992DDFA233h
0x1800018ce  cmp     rax, rbx
0x1800018d1  cmovz   rax, rcx
0x1800018d5  mov     cs:__security_cookie, rax
0x1800018dc  mov     rbx, [rsp+30h+arg_10]
0x1800018e1  not     rax
0x1800018e4  mov     cs:__security_cookie_complement, rax
0x1800018eb  add     rsp, 30h
0x1800018ef  pop     rbp
0x1800018f0  retn
```
