# __security_init_cookie

- ea: `0x180001d4c`
- end: `0x180001e01`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800017b0`

## callees

- `0x180001d4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d8f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001dab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001dab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d81`

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
0x180001d4c  mov     [rsp-8+arg_10], rbx
0x180001d51  push    rbp
0x180001d52  mov     rbp, rsp
0x180001d55  sub     rsp, 30h
0x180001d59  mov     rax, cs:__security_cookie
0x180001d60  mov     rbx, 2B992DDFA232h
0x180001d6a  cmp     rax, rbx
0x180001d6d  jnz     short loc_180001DEC
0x180001d6f  xor     eax, eax
0x180001d71  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d75  mov     [rbp+var_10], rax
0x180001d79  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d7d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d81  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d87  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d8b  mov     [rbp+var_10], rax
0x180001d8f  call    cs:__imp_GetCurrentThreadId
0x180001d95  mov     eax, eax
0x180001d97  xor     [rbp+var_10], rax
0x180001d9b  call    cs:__imp_GetCurrentProcessId
0x180001da1  mov     eax, eax
0x180001da3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001da7  xor     [rbp+var_10], rax
0x180001dab  call    cs:__imp_QueryPerformanceCounter
0x180001db1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001db4  lea     rcx, [rbp+var_10]
0x180001db8  shl     rax, 20h
0x180001dbc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001dc0  xor     rax, [rbp+var_10]
0x180001dc4  xor     rax, rcx
0x180001dc7  mov     rcx, 0FFFFFFFFFFFFh
0x180001dd1  and     rax, rcx
0x180001dd4  mov     rcx, 2B992DDFA233h
0x180001dde  cmp     rax, rbx
0x180001de1  cmovz   rax, rcx
0x180001de5  mov     cs:__security_cookie, rax
0x180001dec  mov     rbx, [rsp+30h+arg_10]
0x180001df1  not     rax
0x180001df4  mov     cs:__security_cookie_complement, rax
0x180001dfb  add     rsp, 30h
0x180001dff  pop     rbp
0x180001e00  retn
```
