# __security_init_cookie

- ea: `0x18013d8fc`
- end: `0x18013d9b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18013ce30`

## callees

- `0x18013d8fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013d93f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013d93f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013d94b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013d94b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18013d931`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18013d931`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18013d95b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18013d95b`

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
0x18013d8fc  mov     [rsp-8+arg_10], rbx
0x18013d901  push    rbp
0x18013d902  mov     rbp, rsp
0x18013d905  sub     rsp, 30h
0x18013d909  mov     rax, cs:__security_cookie
0x18013d910  mov     rbx, 2B992DDFA232h
0x18013d91a  cmp     rax, rbx
0x18013d91d  jnz     short loc_18013D99C
0x18013d91f  xor     eax, eax
0x18013d921  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18013d925  mov     [rbp+var_10], rax
0x18013d929  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18013d92d  mov     qword ptr [rbp+PerformanceCount], rax
0x18013d931  call    cs:__imp_GetSystemTimeAsFileTime
0x18013d937  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18013d93b  mov     [rbp+var_10], rax
0x18013d93f  call    cs:__imp_GetCurrentThreadId
0x18013d945  mov     eax, eax
0x18013d947  xor     [rbp+var_10], rax
0x18013d94b  call    cs:__imp_GetCurrentProcessId
0x18013d951  mov     eax, eax
0x18013d953  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18013d957  xor     [rbp+var_10], rax
0x18013d95b  call    cs:__imp_QueryPerformanceCounter
0x18013d961  mov     eax, dword ptr [rbp+PerformanceCount]
0x18013d964  lea     rcx, [rbp+var_10]
0x18013d968  shl     rax, 20h
0x18013d96c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18013d970  xor     rax, [rbp+var_10]
0x18013d974  xor     rax, rcx
0x18013d977  mov     rcx, 0FFFFFFFFFFFFh
0x18013d981  and     rax, rcx
0x18013d984  mov     rcx, 2B992DDFA233h
0x18013d98e  cmp     rax, rbx
0x18013d991  cmovz   rax, rcx
0x18013d995  mov     cs:__security_cookie, rax
0x18013d99c  mov     rbx, [rsp+30h+arg_10]
0x18013d9a1  not     rax
0x18013d9a4  mov     cs:__security_cookie_complement, rax
0x18013d9ab  add     rsp, 30h
0x18013d9af  pop     rbp
0x18013d9b0  retn
```
