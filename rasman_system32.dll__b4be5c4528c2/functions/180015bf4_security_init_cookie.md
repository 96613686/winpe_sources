# __security_init_cookie

- ea: `0x180015bf4`
- end: `0x180015cd1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800158a0`

## callees

- `0x180015bf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015c3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180015c3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180015c7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180015c7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015c2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015c2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015c53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015c63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015c53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015c63`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180015bf4  mov     [rsp-8+arg_18], rbx
0x180015bf9  push    rbp
0x180015bfa  mov     rbp, rsp
0x180015bfd  sub     rsp, 20h
0x180015c01  xor     eax, eax
0x180015c03  mov     rbx, 2B992DDFA232h
0x180015c0d  mov     [rbp+arg_0], rax
0x180015c11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180015c15  mov     qword ptr [rbp+PerformanceCount], rax
0x180015c19  mov     rax, cs:__security_cookie
0x180015c20  cmp     rax, rbx
0x180015c23  jnz     loc_180015CBC
0x180015c29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015c2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180015c33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180015c37  mov     [rbp+arg_0], rax
0x180015c3b  call    cs:__imp_GetCurrentProcessId
0x180015c41  mov     eax, eax
0x180015c43  xor     [rbp+arg_0], rax
0x180015c47  call    cs:__imp_GetCurrentThreadId
0x180015c4d  mov     eax, eax
0x180015c4f  xor     [rbp+arg_0], rax
0x180015c53  call    cs:__imp_GetTickCount
0x180015c59  mov     eax, eax
0x180015c5b  shl     rax, 18h
0x180015c5f  xor     [rbp+arg_0], rax
0x180015c63  call    cs:__imp_GetTickCount
0x180015c69  mov     eax, eax
0x180015c6b  lea     rcx, [rbp+arg_0]
0x180015c6f  xor     rax, [rbp+arg_0]
0x180015c73  xor     rax, rcx
0x180015c76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180015c7a  mov     [rbp+arg_0], rax
0x180015c7e  call    cs:__imp_QueryPerformanceCounter
0x180015c84  mov     eax, dword ptr [rbp+PerformanceCount]
0x180015c87  mov     rcx, 0FFFFFFFFFFFFh
0x180015c91  shl     rax, 20h
0x180015c95  xor     rax, qword ptr [rbp+PerformanceCount]
0x180015c99  xor     rax, [rbp+arg_0]
0x180015c9d  and     rax, rcx
0x180015ca0  mov     rcx, rax
0x180015ca3  cmp     rax, rbx
0x180015ca6  jnz     short loc_180015CB5
0x180015ca8  mov     rax, 2B992DDFA233h
0x180015cb2  mov     rcx, rax
0x180015cb5  mov     cs:__security_cookie, rcx
0x180015cbc  mov     rbx, [rsp+20h+arg_18]
0x180015cc1  not     rax
0x180015cc4  mov     cs:__security_cookie_complement, rax
0x180015ccb  add     rsp, 20h
0x180015ccf  pop     rbp
0x180015cd0  retn
```
