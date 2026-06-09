# __security_init_cookie

- ea: `0x18004b928`
- end: `0x18004b9dd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004b410`

## callees

- `0x18004b928`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b96b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b96b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004b977`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004b95d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004b95d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004b987`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004b987`

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
0x18004b928  mov     [rsp-8+arg_10], rbx
0x18004b92d  push    rbp
0x18004b92e  mov     rbp, rsp
0x18004b931  sub     rsp, 30h
0x18004b935  mov     rax, cs:__security_cookie
0x18004b93c  mov     rbx, 2B992DDFA232h
0x18004b946  cmp     rax, rbx
0x18004b949  jnz     short loc_18004B9C8
0x18004b94b  xor     eax, eax
0x18004b94d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004b951  mov     [rbp+var_10], rax
0x18004b955  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004b959  mov     qword ptr [rbp+PerformanceCount], rax
0x18004b95d  call    cs:__imp_GetSystemTimeAsFileTime
0x18004b963  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004b967  mov     [rbp+var_10], rax
0x18004b96b  call    cs:__imp_GetCurrentThreadId
0x18004b971  mov     eax, eax
0x18004b973  xor     [rbp+var_10], rax
0x18004b977  call    cs:__imp_GetCurrentProcessId
0x18004b97d  mov     eax, eax
0x18004b97f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004b983  xor     [rbp+var_10], rax
0x18004b987  call    cs:__imp_QueryPerformanceCounter
0x18004b98d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004b990  lea     rcx, [rbp+var_10]
0x18004b994  shl     rax, 20h
0x18004b998  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004b99c  xor     rax, [rbp+var_10]
0x18004b9a0  xor     rax, rcx
0x18004b9a3  mov     rcx, 0FFFFFFFFFFFFh
0x18004b9ad  and     rax, rcx
0x18004b9b0  mov     rcx, 2B992DDFA233h
0x18004b9ba  cmp     rax, rbx
0x18004b9bd  cmovz   rax, rcx
0x18004b9c1  mov     cs:__security_cookie, rax
0x18004b9c8  mov     rbx, [rsp+30h+arg_10]
0x18004b9cd  not     rax
0x18004b9d0  mov     cs:__security_cookie_complement, rax
0x18004b9d7  add     rsp, 30h
0x18004b9db  pop     rbp
0x18004b9dc  retn
```
