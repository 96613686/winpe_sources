# __security_init_cookie

- ea: `0x18001dc4c`
- end: `0x18001dd01`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d7c0`

## callees

- `0x18001dc4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dc9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dc9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dc8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dc8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001dc81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001dc81`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001dcab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001dcab`

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
0x18001dc4c  mov     [rsp-8+arg_10], rbx
0x18001dc51  push    rbp
0x18001dc52  mov     rbp, rsp
0x18001dc55  sub     rsp, 30h
0x18001dc59  mov     rax, cs:__security_cookie
0x18001dc60  mov     rbx, 2B992DDFA232h
0x18001dc6a  cmp     rax, rbx
0x18001dc6d  jnz     short loc_18001DCEC
0x18001dc6f  xor     eax, eax
0x18001dc71  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001dc75  mov     [rbp+var_10], rax
0x18001dc79  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001dc7d  mov     qword ptr [rbp+PerformanceCount], rax
0x18001dc81  call    cs:__imp_GetSystemTimeAsFileTime
0x18001dc87  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001dc8b  mov     [rbp+var_10], rax
0x18001dc8f  call    cs:__imp_GetCurrentThreadId
0x18001dc95  mov     eax, eax
0x18001dc97  xor     [rbp+var_10], rax
0x18001dc9b  call    cs:__imp_GetCurrentProcessId
0x18001dca1  mov     eax, eax
0x18001dca3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001dca7  xor     [rbp+var_10], rax
0x18001dcab  call    cs:__imp_QueryPerformanceCounter
0x18001dcb1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001dcb4  lea     rcx, [rbp+var_10]
0x18001dcb8  shl     rax, 20h
0x18001dcbc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001dcc0  xor     rax, [rbp+var_10]
0x18001dcc4  xor     rax, rcx
0x18001dcc7  mov     rcx, 0FFFFFFFFFFFFh
0x18001dcd1  and     rax, rcx
0x18001dcd4  mov     rcx, 2B992DDFA233h
0x18001dcde  cmp     rax, rbx
0x18001dce1  cmovz   rax, rcx
0x18001dce5  mov     cs:__security_cookie, rax
0x18001dcec  mov     rbx, [rsp+30h+arg_10]
0x18001dcf1  not     rax
0x18001dcf4  mov     cs:__security_cookie_complement, rax
0x18001dcfb  add     rsp, 30h
0x18001dcff  pop     rbp
0x18001dd00  retn
```
