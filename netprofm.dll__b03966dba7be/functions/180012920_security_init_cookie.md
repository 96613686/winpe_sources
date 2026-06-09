# __security_init_cookie

- ea: `0x180012920`
- end: `0x1800129d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012070`

## callees

- `0x180012920`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001296f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001296f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001297f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001297f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012955`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012955`

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
0x180012920  mov     [rsp-8+arg_10], rbx
0x180012925  push    rbp
0x180012926  mov     rbp, rsp
0x180012929  sub     rsp, 30h
0x18001292d  mov     rax, cs:__security_cookie
0x180012934  mov     rbx, 2B992DDFA232h
0x18001293e  cmp     rax, rbx
0x180012941  jnz     short loc_1800129C0
0x180012943  xor     eax, eax
0x180012945  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012949  mov     [rbp+var_10], rax
0x18001294d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180012951  mov     qword ptr [rbp+PerformanceCount], rax
0x180012955  call    cs:__imp_GetSystemTimeAsFileTime
0x18001295b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001295f  mov     [rbp+var_10], rax
0x180012963  call    cs:__imp_GetCurrentThreadId
0x180012969  mov     eax, eax
0x18001296b  xor     [rbp+var_10], rax
0x18001296f  call    cs:__imp_GetCurrentProcessId
0x180012975  mov     eax, eax
0x180012977  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001297b  xor     [rbp+var_10], rax
0x18001297f  call    cs:__imp_QueryPerformanceCounter
0x180012985  mov     eax, dword ptr [rbp+PerformanceCount]
0x180012988  lea     rcx, [rbp+var_10]
0x18001298c  shl     rax, 20h
0x180012990  xor     rax, qword ptr [rbp+PerformanceCount]
0x180012994  xor     rax, [rbp+var_10]
0x180012998  xor     rax, rcx
0x18001299b  mov     rcx, 0FFFFFFFFFFFFh
0x1800129a5  and     rax, rcx
0x1800129a8  mov     rcx, 2B992DDFA233h
0x1800129b2  cmp     rax, rbx
0x1800129b5  cmovz   rax, rcx
0x1800129b9  mov     cs:__security_cookie, rax
0x1800129c0  mov     rbx, [rsp+30h+arg_10]
0x1800129c5  not     rax
0x1800129c8  mov     cs:__security_cookie_complement, rax
0x1800129cf  add     rsp, 30h
0x1800129d3  pop     rbp
0x1800129d4  retn
```
