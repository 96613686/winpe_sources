# __security_init_cookie

- ea: `0x18000a92c`
- end: `0x18000a9e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a4d0`

## callees

- `0x18000a92c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a97b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a97b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a96f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a96f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a98b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a98b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a961`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a961`

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
0x18000a92c  mov     [rsp-8+arg_10], rbx
0x18000a931  push    rbp
0x18000a932  mov     rbp, rsp
0x18000a935  sub     rsp, 30h
0x18000a939  mov     rax, cs:__security_cookie
0x18000a940  mov     rbx, 2B992DDFA232h
0x18000a94a  cmp     rax, rbx
0x18000a94d  jnz     short loc_18000A9CC
0x18000a94f  xor     eax, eax
0x18000a951  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a955  mov     [rbp+var_10], rax
0x18000a959  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000a95d  mov     qword ptr [rbp+PerformanceCount], rax
0x18000a961  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a967  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000a96b  mov     [rbp+var_10], rax
0x18000a96f  call    cs:__imp_GetCurrentThreadId
0x18000a975  mov     eax, eax
0x18000a977  xor     [rbp+var_10], rax
0x18000a97b  call    cs:__imp_GetCurrentProcessId
0x18000a981  mov     eax, eax
0x18000a983  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000a987  xor     [rbp+var_10], rax
0x18000a98b  call    cs:__imp_QueryPerformanceCounter
0x18000a991  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000a994  lea     rcx, [rbp+var_10]
0x18000a998  shl     rax, 20h
0x18000a99c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000a9a0  xor     rax, [rbp+var_10]
0x18000a9a4  xor     rax, rcx
0x18000a9a7  mov     rcx, 0FFFFFFFFFFFFh
0x18000a9b1  and     rax, rcx
0x18000a9b4  mov     rcx, 2B992DDFA233h
0x18000a9be  cmp     rax, rbx
0x18000a9c1  cmovz   rax, rcx
0x18000a9c5  mov     cs:__security_cookie, rax
0x18000a9cc  mov     rbx, [rsp+30h+arg_10]
0x18000a9d1  not     rax
0x18000a9d4  mov     cs:__security_cookie_complement, rax
0x18000a9db  add     rsp, 30h
0x18000a9df  pop     rbp
0x18000a9e0  retn
```
