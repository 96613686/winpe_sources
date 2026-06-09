# __security_init_cookie

- ea: `0x180035eb8`
- end: `0x180035f6d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035620`

## callees

- `0x180035eb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035f07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035f07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035efb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035efb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035eed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180035eed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180035f17`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180035f17`

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
0x180035eb8  mov     [rsp-8+arg_10], rbx
0x180035ebd  push    rbp
0x180035ebe  mov     rbp, rsp
0x180035ec1  sub     rsp, 30h
0x180035ec5  mov     rax, cs:__security_cookie
0x180035ecc  mov     rbx, 2B992DDFA232h
0x180035ed6  cmp     rax, rbx
0x180035ed9  jnz     short loc_180035F58
0x180035edb  xor     eax, eax
0x180035edd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180035ee1  mov     [rbp+var_10], rax
0x180035ee5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180035ee9  mov     qword ptr [rbp+PerformanceCount], rax
0x180035eed  call    cs:__imp_GetSystemTimeAsFileTime
0x180035ef3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180035ef7  mov     [rbp+var_10], rax
0x180035efb  call    cs:__imp_GetCurrentThreadId
0x180035f01  mov     eax, eax
0x180035f03  xor     [rbp+var_10], rax
0x180035f07  call    cs:__imp_GetCurrentProcessId
0x180035f0d  mov     eax, eax
0x180035f0f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180035f13  xor     [rbp+var_10], rax
0x180035f17  call    cs:__imp_QueryPerformanceCounter
0x180035f1d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180035f20  lea     rcx, [rbp+var_10]
0x180035f24  shl     rax, 20h
0x180035f28  xor     rax, qword ptr [rbp+PerformanceCount]
0x180035f2c  xor     rax, [rbp+var_10]
0x180035f30  xor     rax, rcx
0x180035f33  mov     rcx, 0FFFFFFFFFFFFh
0x180035f3d  and     rax, rcx
0x180035f40  mov     rcx, 2B992DDFA233h
0x180035f4a  cmp     rax, rbx
0x180035f4d  cmovz   rax, rcx
0x180035f51  mov     cs:__security_cookie, rax
0x180035f58  mov     rbx, [rsp+30h+arg_10]
0x180035f5d  not     rax
0x180035f60  mov     cs:__security_cookie_complement, rax
0x180035f67  add     rsp, 30h
0x180035f6b  pop     rbp
0x180035f6c  retn
```
