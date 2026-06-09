# __security_init_cookie

- ea: `0x180002150`
- end: `0x180002205`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ca0`

## callees

- `0x180002150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000219f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000219f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002193`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800021af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800021af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002185`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002185`

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
0x180002150  mov     [rsp-8+arg_10], rbx
0x180002155  push    rbp
0x180002156  mov     rbp, rsp
0x180002159  sub     rsp, 30h
0x18000215d  mov     rax, cs:__security_cookie
0x180002164  mov     rbx, 2B992DDFA232h
0x18000216e  cmp     rax, rbx
0x180002171  jnz     short loc_1800021F0
0x180002173  xor     eax, eax
0x180002175  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002179  mov     [rbp+var_10], rax
0x18000217d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002181  mov     qword ptr [rbp+PerformanceCount], rax
0x180002185  call    cs:__imp_GetSystemTimeAsFileTime
0x18000218b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000218f  mov     [rbp+var_10], rax
0x180002193  call    cs:__imp_GetCurrentThreadId
0x180002199  mov     eax, eax
0x18000219b  xor     [rbp+var_10], rax
0x18000219f  call    cs:__imp_GetCurrentProcessId
0x1800021a5  mov     eax, eax
0x1800021a7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800021ab  xor     [rbp+var_10], rax
0x1800021af  call    cs:__imp_QueryPerformanceCounter
0x1800021b5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800021b8  lea     rcx, [rbp+var_10]
0x1800021bc  shl     rax, 20h
0x1800021c0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800021c4  xor     rax, [rbp+var_10]
0x1800021c8  xor     rax, rcx
0x1800021cb  mov     rcx, 0FFFFFFFFFFFFh
0x1800021d5  and     rax, rcx
0x1800021d8  mov     rcx, 2B992DDFA233h
0x1800021e2  cmp     rax, rbx
0x1800021e5  cmovz   rax, rcx
0x1800021e9  mov     cs:__security_cookie, rax
0x1800021f0  mov     rbx, [rsp+30h+arg_10]
0x1800021f5  not     rax
0x1800021f8  mov     cs:__security_cookie_complement, rax
0x1800021ff  add     rsp, 30h
0x180002203  pop     rbp
0x180002204  retn
```
