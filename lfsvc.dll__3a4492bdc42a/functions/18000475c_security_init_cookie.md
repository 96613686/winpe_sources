# __security_init_cookie

- ea: `0x18000475c`
- end: `0x180004811`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800042b0`

## callees

- `0x18000475c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000479f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000479f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800047ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800047ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800047bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800047bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004791`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004791`

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
0x18000475c  mov     [rsp-8+arg_10], rbx
0x180004761  push    rbp
0x180004762  mov     rbp, rsp
0x180004765  sub     rsp, 30h
0x180004769  mov     rax, cs:__security_cookie
0x180004770  mov     rbx, 2B992DDFA232h
0x18000477a  cmp     rax, rbx
0x18000477d  jnz     short loc_1800047FC
0x18000477f  xor     eax, eax
0x180004781  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004785  mov     [rbp+var_10], rax
0x180004789  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000478d  mov     qword ptr [rbp+PerformanceCount], rax
0x180004791  call    cs:__imp_GetSystemTimeAsFileTime
0x180004797  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000479b  mov     [rbp+var_10], rax
0x18000479f  call    cs:__imp_GetCurrentThreadId
0x1800047a5  mov     eax, eax
0x1800047a7  xor     [rbp+var_10], rax
0x1800047ab  call    cs:__imp_GetCurrentProcessId
0x1800047b1  mov     eax, eax
0x1800047b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800047b7  xor     [rbp+var_10], rax
0x1800047bb  call    cs:__imp_QueryPerformanceCounter
0x1800047c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800047c4  lea     rcx, [rbp+var_10]
0x1800047c8  shl     rax, 20h
0x1800047cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800047d0  xor     rax, [rbp+var_10]
0x1800047d4  xor     rax, rcx
0x1800047d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800047e1  and     rax, rcx
0x1800047e4  mov     rcx, 2B992DDFA233h
0x1800047ee  cmp     rax, rbx
0x1800047f1  cmovz   rax, rcx
0x1800047f5  mov     cs:__security_cookie, rax
0x1800047fc  mov     rbx, [rsp+30h+arg_10]
0x180004801  not     rax
0x180004804  mov     cs:__security_cookie_complement, rax
0x18000480b  add     rsp, 30h
0x18000480f  pop     rbp
0x180004810  retn
```
