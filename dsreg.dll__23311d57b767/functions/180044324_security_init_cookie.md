# __security_init_cookie

- ea: `0x180044324`
- end: `0x1800443d9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800442b0`

## callees

- `0x180044324`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180044383`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180044383`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044373`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044373`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044359`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044359`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180044324  mov     [rsp-8+arg_10], rbx
0x180044329  push    rbp
0x18004432a  mov     rbp, rsp
0x18004432d  sub     rsp, 30h
0x180044331  mov     rax, cs:__security_cookie
0x180044338  mov     rbx, 2B992DDFA232h
0x180044342  cmp     rax, rbx
0x180044345  jnz     short loc_1800443C4
0x180044347  xor     eax, eax
0x180044349  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004434d  mov     [rbp+var_10], rax
0x180044351  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180044355  mov     qword ptr [rbp+PerformanceCount], rax
0x180044359  call    cs:__imp_GetSystemTimeAsFileTime
0x18004435f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180044363  mov     [rbp+var_10], rax
0x180044367  call    cs:__imp_GetCurrentThreadId
0x18004436d  mov     eax, eax
0x18004436f  xor     [rbp+var_10], rax
0x180044373  call    cs:__imp_GetCurrentProcessId
0x180044379  mov     eax, eax
0x18004437b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004437f  xor     [rbp+var_10], rax
0x180044383  call    cs:__imp_QueryPerformanceCounter
0x180044389  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004438c  lea     rcx, [rbp+var_10]
0x180044390  shl     rax, 20h
0x180044394  xor     rax, qword ptr [rbp+PerformanceCount]
0x180044398  xor     rax, [rbp+var_10]
0x18004439c  xor     rax, rcx
0x18004439f  mov     rcx, 0FFFFFFFFFFFFh
0x1800443a9  and     rax, rcx
0x1800443ac  mov     rcx, 2B992DDFA233h
0x1800443b6  cmp     rax, rbx
0x1800443b9  cmovz   rax, rcx
0x1800443bd  mov     cs:__security_cookie, rax
0x1800443c4  mov     rbx, [rsp+30h+arg_10]
0x1800443c9  not     rax
0x1800443cc  mov     cs:__security_cookie_complement, rax
0x1800443d3  add     rsp, 30h
0x1800443d7  pop     rbp
0x1800443d8  retn
```
