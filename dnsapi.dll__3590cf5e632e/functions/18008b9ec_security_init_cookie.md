# __security_init_cookie

- ea: `0x18008b9ec`
- end: `0x18008baa1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008b5a0`

## callees

- `0x18008b9ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008ba2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008ba2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008ba3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008ba3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008ba4b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18008ba4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ba21`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ba21`

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
0x18008b9ec  mov     [rsp-8+arg_10], rbx
0x18008b9f1  push    rbp
0x18008b9f2  mov     rbp, rsp
0x18008b9f5  sub     rsp, 30h
0x18008b9f9  mov     rax, cs:__security_cookie
0x18008ba00  mov     rbx, 2B992DDFA232h
0x18008ba0a  cmp     rax, rbx
0x18008ba0d  jnz     short loc_18008BA8C
0x18008ba0f  xor     eax, eax
0x18008ba11  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008ba15  mov     [rbp+var_10], rax
0x18008ba19  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18008ba1d  mov     qword ptr [rbp+PerformanceCount], rax
0x18008ba21  call    cs:__imp_GetSystemTimeAsFileTime
0x18008ba27  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18008ba2b  mov     [rbp+var_10], rax
0x18008ba2f  call    cs:__imp_GetCurrentThreadId
0x18008ba35  mov     eax, eax
0x18008ba37  xor     [rbp+var_10], rax
0x18008ba3b  call    cs:__imp_GetCurrentProcessId
0x18008ba41  mov     eax, eax
0x18008ba43  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18008ba47  xor     [rbp+var_10], rax
0x18008ba4b  call    cs:__imp_QueryPerformanceCounter
0x18008ba51  mov     eax, dword ptr [rbp+PerformanceCount]
0x18008ba54  lea     rcx, [rbp+var_10]
0x18008ba58  shl     rax, 20h
0x18008ba5c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18008ba60  xor     rax, [rbp+var_10]
0x18008ba64  xor     rax, rcx
0x18008ba67  mov     rcx, 0FFFFFFFFFFFFh
0x18008ba71  and     rax, rcx
0x18008ba74  mov     rcx, 2B992DDFA233h
0x18008ba7e  cmp     rax, rbx
0x18008ba81  cmovz   rax, rcx
0x18008ba85  mov     cs:__security_cookie, rax
0x18008ba8c  mov     rbx, [rsp+30h+arg_10]
0x18008ba91  not     rax
0x18008ba94  mov     cs:__security_cookie_complement, rax
0x18008ba9b  add     rsp, 30h
0x18008ba9f  pop     rbp
0x18008baa0  retn
```
