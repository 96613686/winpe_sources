# __security_init_cookie

- ea: `0x180009908`
- end: `0x1800099bd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008d80`

## callees

- `0x180009908`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000994b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000994b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000993d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000993d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009967`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009967`

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
0x180009908  mov     [rsp-8+arg_10], rbx
0x18000990d  push    rbp
0x18000990e  mov     rbp, rsp
0x180009911  sub     rsp, 30h
0x180009915  mov     rax, cs:__security_cookie
0x18000991c  mov     rbx, 2B992DDFA232h
0x180009926  cmp     rax, rbx
0x180009929  jnz     short loc_1800099A8
0x18000992b  xor     eax, eax
0x18000992d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009931  mov     [rbp+var_10], rax
0x180009935  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180009939  mov     qword ptr [rbp+PerformanceCount], rax
0x18000993d  call    cs:__imp_GetSystemTimeAsFileTime
0x180009943  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009947  mov     [rbp+var_10], rax
0x18000994b  call    cs:__imp_GetCurrentThreadId
0x180009951  mov     eax, eax
0x180009953  xor     [rbp+var_10], rax
0x180009957  call    cs:__imp_GetCurrentProcessId
0x18000995d  mov     eax, eax
0x18000995f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180009963  xor     [rbp+var_10], rax
0x180009967  call    cs:__imp_QueryPerformanceCounter
0x18000996d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180009970  lea     rcx, [rbp+var_10]
0x180009974  shl     rax, 20h
0x180009978  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000997c  xor     rax, [rbp+var_10]
0x180009980  xor     rax, rcx
0x180009983  mov     rcx, 0FFFFFFFFFFFFh
0x18000998d  and     rax, rcx
0x180009990  mov     rcx, 2B992DDFA233h
0x18000999a  cmp     rax, rbx
0x18000999d  cmovz   rax, rcx
0x1800099a1  mov     cs:__security_cookie, rax
0x1800099a8  mov     rbx, [rsp+30h+arg_10]
0x1800099ad  not     rax
0x1800099b0  mov     cs:__security_cookie_complement, rax
0x1800099b7  add     rsp, 30h
0x1800099bb  pop     rbp
0x1800099bc  retn
```
