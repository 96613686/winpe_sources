# __security_init_cookie

- ea: `0x180011e2c`
- end: `0x180011ee1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800118d0`

## callees

- `0x180011e2c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011e8b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011e8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011e7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011e7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011e6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011e61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011e61`

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
0x180011e2c  mov     [rsp-8+arg_10], rbx
0x180011e31  push    rbp
0x180011e32  mov     rbp, rsp
0x180011e35  sub     rsp, 30h
0x180011e39  mov     rax, cs:__security_cookie
0x180011e40  mov     rbx, 2B992DDFA232h
0x180011e4a  cmp     rax, rbx
0x180011e4d  jnz     short loc_180011ECC
0x180011e4f  xor     eax, eax
0x180011e51  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180011e55  mov     [rbp+var_10], rax
0x180011e59  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180011e5d  mov     qword ptr [rbp+PerformanceCount], rax
0x180011e61  call    cs:__imp_GetSystemTimeAsFileTime
0x180011e67  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180011e6b  mov     [rbp+var_10], rax
0x180011e6f  call    cs:__imp_GetCurrentThreadId
0x180011e75  mov     eax, eax
0x180011e77  xor     [rbp+var_10], rax
0x180011e7b  call    cs:__imp_GetCurrentProcessId
0x180011e81  mov     eax, eax
0x180011e83  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180011e87  xor     [rbp+var_10], rax
0x180011e8b  call    cs:__imp_QueryPerformanceCounter
0x180011e91  mov     eax, dword ptr [rbp+PerformanceCount]
0x180011e94  lea     rcx, [rbp+var_10]
0x180011e98  shl     rax, 20h
0x180011e9c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180011ea0  xor     rax, [rbp+var_10]
0x180011ea4  xor     rax, rcx
0x180011ea7  mov     rcx, 0FFFFFFFFFFFFh
0x180011eb1  and     rax, rcx
0x180011eb4  mov     rcx, 2B992DDFA233h
0x180011ebe  cmp     rax, rbx
0x180011ec1  cmovz   rax, rcx
0x180011ec5  mov     cs:__security_cookie, rax
0x180011ecc  mov     rbx, [rsp+30h+arg_10]
0x180011ed1  not     rax
0x180011ed4  mov     cs:__security_cookie_complement, rax
0x180011edb  add     rsp, 30h
0x180011edf  pop     rbp
0x180011ee0  retn
```
