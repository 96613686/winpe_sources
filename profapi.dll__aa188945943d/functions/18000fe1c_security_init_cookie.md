# __security_init_cookie

- ea: `0x18000fe1c`
- end: `0x18000fed1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f9c0`

## callees

- `0x18000fe1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fe6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fe51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fe51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fe7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fe7b`

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
0x18000fe1c  mov     [rsp-8+arg_10], rbx
0x18000fe21  push    rbp
0x18000fe22  mov     rbp, rsp
0x18000fe25  sub     rsp, 30h
0x18000fe29  mov     rax, cs:__security_cookie
0x18000fe30  mov     rbx, 2B992DDFA232h
0x18000fe3a  cmp     rax, rbx
0x18000fe3d  jnz     short loc_18000FEBC
0x18000fe3f  xor     eax, eax
0x18000fe41  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fe45  mov     [rbp+var_10], rax
0x18000fe49  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000fe4d  mov     qword ptr [rbp+PerformanceCount], rax
0x18000fe51  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fe57  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000fe5b  mov     [rbp+var_10], rax
0x18000fe5f  call    cs:__imp_GetCurrentThreadId
0x18000fe65  mov     eax, eax
0x18000fe67  xor     [rbp+var_10], rax
0x18000fe6b  call    cs:__imp_GetCurrentProcessId
0x18000fe71  mov     eax, eax
0x18000fe73  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000fe77  xor     [rbp+var_10], rax
0x18000fe7b  call    cs:__imp_QueryPerformanceCounter
0x18000fe81  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000fe84  lea     rcx, [rbp+var_10]
0x18000fe88  shl     rax, 20h
0x18000fe8c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000fe90  xor     rax, [rbp+var_10]
0x18000fe94  xor     rax, rcx
0x18000fe97  mov     rcx, 0FFFFFFFFFFFFh
0x18000fea1  and     rax, rcx
0x18000fea4  mov     rcx, 2B992DDFA233h
0x18000feae  cmp     rax, rbx
0x18000feb1  cmovz   rax, rcx
0x18000feb5  mov     cs:__security_cookie, rax
0x18000febc  mov     rbx, [rsp+30h+arg_10]
0x18000fec1  not     rax
0x18000fec4  mov     cs:__security_cookie_complement, rax
0x18000fecb  add     rsp, 30h
0x18000fecf  pop     rbp
0x18000fed0  retn
```
