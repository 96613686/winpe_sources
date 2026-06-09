# __security_init_cookie

- ea: `0x180001ba8`
- end: `0x180001c5d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001750`

## callees

- `0x180001ba8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001bf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001bf7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c07`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001bdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001bdd`

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
0x180001ba8  mov     [rsp-8+arg_10], rbx
0x180001bad  push    rbp
0x180001bae  mov     rbp, rsp
0x180001bb1  sub     rsp, 30h
0x180001bb5  mov     rax, cs:__security_cookie
0x180001bbc  mov     rbx, 2B992DDFA232h
0x180001bc6  cmp     rax, rbx
0x180001bc9  jnz     short loc_180001C48
0x180001bcb  xor     eax, eax
0x180001bcd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001bd1  mov     [rbp+var_10], rax
0x180001bd5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001bd9  mov     qword ptr [rbp+PerformanceCount], rax
0x180001bdd  call    cs:__imp_GetSystemTimeAsFileTime
0x180001be3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001be7  mov     [rbp+var_10], rax
0x180001beb  call    cs:__imp_GetCurrentThreadId
0x180001bf1  mov     eax, eax
0x180001bf3  xor     [rbp+var_10], rax
0x180001bf7  call    cs:__imp_GetCurrentProcessId
0x180001bfd  mov     eax, eax
0x180001bff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c03  xor     [rbp+var_10], rax
0x180001c07  call    cs:__imp_QueryPerformanceCounter
0x180001c0d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c10  lea     rcx, [rbp+var_10]
0x180001c14  shl     rax, 20h
0x180001c18  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c1c  xor     rax, [rbp+var_10]
0x180001c20  xor     rax, rcx
0x180001c23  mov     rcx, 0FFFFFFFFFFFFh
0x180001c2d  and     rax, rcx
0x180001c30  mov     rcx, 2B992DDFA233h
0x180001c3a  cmp     rax, rbx
0x180001c3d  cmovz   rax, rcx
0x180001c41  mov     cs:__security_cookie, rax
0x180001c48  mov     rbx, [rsp+30h+arg_10]
0x180001c4d  not     rax
0x180001c50  mov     cs:__security_cookie_complement, rax
0x180001c57  add     rsp, 30h
0x180001c5b  pop     rbp
0x180001c5c  retn
```
