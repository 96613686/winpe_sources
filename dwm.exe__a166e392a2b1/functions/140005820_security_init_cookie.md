# __security_init_cookie

- ea: `0x140005820`
- end: `0x1400058d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005500`

## callees

- `0x140005820`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000586f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000586f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000587f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000587f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005855`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005855`

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
0x140005820  mov     [rsp-8+arg_10], rbx
0x140005825  push    rbp
0x140005826  mov     rbp, rsp
0x140005829  sub     rsp, 30h
0x14000582d  mov     rax, cs:__security_cookie
0x140005834  mov     rbx, 2B992DDFA232h
0x14000583e  cmp     rax, rbx
0x140005841  jnz     short loc_1400058C0
0x140005843  xor     eax, eax
0x140005845  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140005849  mov     [rbp+var_10], rax
0x14000584d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140005851  mov     qword ptr [rbp+PerformanceCount], rax
0x140005855  call    cs:__imp_GetSystemTimeAsFileTime
0x14000585b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000585f  mov     [rbp+var_10], rax
0x140005863  call    cs:__imp_GetCurrentThreadId
0x140005869  mov     eax, eax
0x14000586b  xor     [rbp+var_10], rax
0x14000586f  call    cs:__imp_GetCurrentProcessId
0x140005875  mov     eax, eax
0x140005877  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000587b  xor     [rbp+var_10], rax
0x14000587f  call    cs:__imp_QueryPerformanceCounter
0x140005885  mov     eax, dword ptr [rbp+PerformanceCount]
0x140005888  lea     rcx, [rbp+var_10]
0x14000588c  shl     rax, 20h
0x140005890  xor     rax, qword ptr [rbp+PerformanceCount]
0x140005894  xor     rax, [rbp+var_10]
0x140005898  xor     rax, rcx
0x14000589b  mov     rcx, 0FFFFFFFFFFFFh
0x1400058a5  and     rax, rcx
0x1400058a8  mov     rcx, 2B992DDFA233h
0x1400058b2  cmp     rax, rbx
0x1400058b5  cmovz   rax, rcx
0x1400058b9  mov     cs:__security_cookie, rax
0x1400058c0  mov     rbx, [rsp+30h+arg_10]
0x1400058c5  not     rax
0x1400058c8  mov     cs:__security_cookie_complement, rax
0x1400058cf  add     rsp, 30h
0x1400058d3  pop     rbp
0x1400058d4  retn
```
