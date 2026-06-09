# __security_init_cookie

- ea: `0x140002c58`
- end: `0x140002d0d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400025d0`

## callees

- `0x140002c58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002c9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002c9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002ca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002ca7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002cb7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002cb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002c8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002c8d`

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
0x140002c58  mov     [rsp-8+arg_10], rbx
0x140002c5d  push    rbp
0x140002c5e  mov     rbp, rsp
0x140002c61  sub     rsp, 30h
0x140002c65  mov     rax, cs:__security_cookie
0x140002c6c  mov     rbx, 2B992DDFA232h
0x140002c76  cmp     rax, rbx
0x140002c79  jnz     short loc_140002CF8
0x140002c7b  xor     eax, eax
0x140002c7d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002c81  mov     [rbp+var_10], rax
0x140002c85  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002c89  mov     qword ptr [rbp+PerformanceCount], rax
0x140002c8d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002c93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002c97  mov     [rbp+var_10], rax
0x140002c9b  call    cs:__imp_GetCurrentThreadId
0x140002ca1  mov     eax, eax
0x140002ca3  xor     [rbp+var_10], rax
0x140002ca7  call    cs:__imp_GetCurrentProcessId
0x140002cad  mov     eax, eax
0x140002caf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002cb3  xor     [rbp+var_10], rax
0x140002cb7  call    cs:__imp_QueryPerformanceCounter
0x140002cbd  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002cc0  lea     rcx, [rbp+var_10]
0x140002cc4  shl     rax, 20h
0x140002cc8  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002ccc  xor     rax, [rbp+var_10]
0x140002cd0  xor     rax, rcx
0x140002cd3  mov     rcx, 0FFFFFFFFFFFFh
0x140002cdd  and     rax, rcx
0x140002ce0  mov     rcx, 2B992DDFA233h
0x140002cea  cmp     rax, rbx
0x140002ced  cmovz   rax, rcx
0x140002cf1  mov     cs:__security_cookie, rax
0x140002cf8  mov     rbx, [rsp+30h+arg_10]
0x140002cfd  not     rax
0x140002d00  mov     cs:__security_cookie_complement, rax
0x140002d07  add     rsp, 30h
0x140002d0b  pop     rbp
0x140002d0c  retn
```
