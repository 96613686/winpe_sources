# __security_init_cookie

- ea: `0x180006870`
- end: `0x180006925`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800062d0`

## callees

- `0x180006870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068a5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800068cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800068cf`

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
0x180006870  mov     [rsp-8+arg_10], rbx
0x180006875  push    rbp
0x180006876  mov     rbp, rsp
0x180006879  sub     rsp, 30h
0x18000687d  mov     rax, cs:__security_cookie
0x180006884  mov     rbx, 2B992DDFA232h
0x18000688e  cmp     rax, rbx
0x180006891  jnz     short loc_180006910
0x180006893  xor     eax, eax
0x180006895  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006899  mov     [rbp+var_10], rax
0x18000689d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800068a1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800068a5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800068ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800068af  mov     [rbp+var_10], rax
0x1800068b3  call    cs:__imp_GetCurrentThreadId
0x1800068b9  mov     eax, eax
0x1800068bb  xor     [rbp+var_10], rax
0x1800068bf  call    cs:__imp_GetCurrentProcessId
0x1800068c5  mov     eax, eax
0x1800068c7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800068cb  xor     [rbp+var_10], rax
0x1800068cf  call    cs:__imp_QueryPerformanceCounter
0x1800068d5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800068d8  lea     rcx, [rbp+var_10]
0x1800068dc  shl     rax, 20h
0x1800068e0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800068e4  xor     rax, [rbp+var_10]
0x1800068e8  xor     rax, rcx
0x1800068eb  mov     rcx, 0FFFFFFFFFFFFh
0x1800068f5  and     rax, rcx
0x1800068f8  mov     rcx, 2B992DDFA233h
0x180006902  cmp     rax, rbx
0x180006905  cmovz   rax, rcx
0x180006909  mov     cs:__security_cookie, rax
0x180006910  mov     rbx, [rsp+30h+arg_10]
0x180006915  not     rax
0x180006918  mov     cs:__security_cookie_complement, rax
0x18000691f  add     rsp, 30h
0x180006923  pop     rbp
0x180006924  retn
```
