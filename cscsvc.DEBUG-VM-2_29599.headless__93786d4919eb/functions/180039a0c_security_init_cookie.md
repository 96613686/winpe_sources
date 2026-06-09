# __security_init_cookie

- ea: `0x180039a0c`
- end: `0x180039ac1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800395c0`

## callees

- `0x180039a0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039a5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039a5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039a4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039a4f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180039a6b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180039a6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180039a41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180039a41`

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
0x180039a0c  mov     [rsp-8+arg_10], rbx
0x180039a11  push    rbp
0x180039a12  mov     rbp, rsp
0x180039a15  sub     rsp, 30h
0x180039a19  mov     rax, cs:__security_cookie
0x180039a20  mov     rbx, 2B992DDFA232h
0x180039a2a  cmp     rax, rbx
0x180039a2d  jnz     short loc_180039AAC
0x180039a2f  xor     eax, eax
0x180039a31  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180039a35  mov     [rbp+var_10], rax
0x180039a39  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180039a3d  mov     qword ptr [rbp+PerformanceCount], rax
0x180039a41  call    cs:__imp_GetSystemTimeAsFileTime
0x180039a47  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180039a4b  mov     [rbp+var_10], rax
0x180039a4f  call    cs:__imp_GetCurrentThreadId
0x180039a55  mov     eax, eax
0x180039a57  xor     [rbp+var_10], rax
0x180039a5b  call    cs:__imp_GetCurrentProcessId
0x180039a61  mov     eax, eax
0x180039a63  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180039a67  xor     [rbp+var_10], rax
0x180039a6b  call    cs:__imp_QueryPerformanceCounter
0x180039a71  mov     eax, dword ptr [rbp+PerformanceCount]
0x180039a74  lea     rcx, [rbp+var_10]
0x180039a78  shl     rax, 20h
0x180039a7c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180039a80  xor     rax, [rbp+var_10]
0x180039a84  xor     rax, rcx
0x180039a87  mov     rcx, 0FFFFFFFFFFFFh
0x180039a91  and     rax, rcx
0x180039a94  mov     rcx, 2B992DDFA233h
0x180039a9e  cmp     rax, rbx
0x180039aa1  cmovz   rax, rcx
0x180039aa5  mov     cs:__security_cookie, rax
0x180039aac  mov     rbx, [rsp+30h+arg_10]
0x180039ab1  not     rax
0x180039ab4  mov     cs:__security_cookie_complement, rax
0x180039abb  add     rsp, 30h
0x180039abf  pop     rbp
0x180039ac0  retn
```
