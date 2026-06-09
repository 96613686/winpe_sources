# __security_init_cookie

- ea: `0x180002b1c`
- end: `0x180002bd1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002670`

## callees

- `0x180002b1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002b6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002b51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002b51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002b7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002b7b`

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
0x180002b1c  mov     [rsp-8+arg_10], rbx
0x180002b21  push    rbp
0x180002b22  mov     rbp, rsp
0x180002b25  sub     rsp, 30h
0x180002b29  mov     rax, cs:__security_cookie
0x180002b30  mov     rbx, 2B992DDFA232h
0x180002b3a  cmp     rax, rbx
0x180002b3d  jnz     short loc_180002BBC
0x180002b3f  xor     eax, eax
0x180002b41  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002b45  mov     [rbp+var_10], rax
0x180002b49  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002b4d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002b51  call    cs:__imp_GetSystemTimeAsFileTime
0x180002b57  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002b5b  mov     [rbp+var_10], rax
0x180002b5f  call    cs:__imp_GetCurrentThreadId
0x180002b65  mov     eax, eax
0x180002b67  xor     [rbp+var_10], rax
0x180002b6b  call    cs:__imp_GetCurrentProcessId
0x180002b71  mov     eax, eax
0x180002b73  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002b77  xor     [rbp+var_10], rax
0x180002b7b  call    cs:__imp_QueryPerformanceCounter
0x180002b81  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002b84  lea     rcx, [rbp+var_10]
0x180002b88  shl     rax, 20h
0x180002b8c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002b90  xor     rax, [rbp+var_10]
0x180002b94  xor     rax, rcx
0x180002b97  mov     rcx, 0FFFFFFFFFFFFh
0x180002ba1  and     rax, rcx
0x180002ba4  mov     rcx, 2B992DDFA233h
0x180002bae  cmp     rax, rbx
0x180002bb1  cmovz   rax, rcx
0x180002bb5  mov     cs:__security_cookie, rax
0x180002bbc  mov     rbx, [rsp+30h+arg_10]
0x180002bc1  not     rax
0x180002bc4  mov     cs:__security_cookie_complement, rax
0x180002bcb  add     rsp, 30h
0x180002bcf  pop     rbp
0x180002bd0  retn
```
