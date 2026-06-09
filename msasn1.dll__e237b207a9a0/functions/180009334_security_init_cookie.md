# __security_init_cookie

- ea: `0x180009334`
- end: `0x1800093e9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800092c0`

## callees

- `0x180009334`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009393`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009383`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009383`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009377`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009369`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009369`

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
0x180009334  mov     [rsp-8+arg_10], rbx
0x180009339  push    rbp
0x18000933a  mov     rbp, rsp
0x18000933d  sub     rsp, 30h
0x180009341  mov     rax, cs:__security_cookie
0x180009348  mov     rbx, 2B992DDFA232h
0x180009352  cmp     rax, rbx
0x180009355  jnz     short loc_1800093D4
0x180009357  xor     eax, eax
0x180009359  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000935d  mov     [rbp+var_10], rax
0x180009361  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180009365  mov     qword ptr [rbp+PerformanceCount], rax
0x180009369  call    cs:__imp_GetSystemTimeAsFileTime
0x18000936f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009373  mov     [rbp+var_10], rax
0x180009377  call    cs:__imp_GetCurrentThreadId
0x18000937d  mov     eax, eax
0x18000937f  xor     [rbp+var_10], rax
0x180009383  call    cs:__imp_GetCurrentProcessId
0x180009389  mov     eax, eax
0x18000938b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000938f  xor     [rbp+var_10], rax
0x180009393  call    cs:__imp_QueryPerformanceCounter
0x180009399  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000939c  lea     rcx, [rbp+var_10]
0x1800093a0  shl     rax, 20h
0x1800093a4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800093a8  xor     rax, [rbp+var_10]
0x1800093ac  xor     rax, rcx
0x1800093af  mov     rcx, 0FFFFFFFFFFFFh
0x1800093b9  and     rax, rcx
0x1800093bc  mov     rcx, 2B992DDFA233h
0x1800093c6  cmp     rax, rbx
0x1800093c9  cmovz   rax, rcx
0x1800093cd  mov     cs:__security_cookie, rax
0x1800093d4  mov     rbx, [rsp+30h+arg_10]
0x1800093d9  not     rax
0x1800093dc  mov     cs:__security_cookie_complement, rax
0x1800093e3  add     rsp, 30h
0x1800093e7  pop     rbp
0x1800093e8  retn
```
