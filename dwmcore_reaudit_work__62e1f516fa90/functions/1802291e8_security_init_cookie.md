# __security_init_cookie

- ea: `0x1802291e8`
- end: `0x18022929d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180228b84`

## callees

- `0x1802291e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180229237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180229237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18022922b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18022922b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180229247`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180229247`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18022921d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18022921d`

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
0x1802291e8  mov     [rsp-8+arg_10], rbx
0x1802291ed  push    rbp
0x1802291ee  mov     rbp, rsp
0x1802291f1  sub     rsp, 30h
0x1802291f5  mov     rax, cs:__security_cookie
0x1802291fc  mov     rbx, 2B992DDFA232h
0x180229206  cmp     rax, rbx
0x180229209  jnz     short loc_180229288
0x18022920b  xor     eax, eax
0x18022920d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180229211  mov     [rbp+var_10], rax
0x180229215  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180229219  mov     qword ptr [rbp+PerformanceCount], rax
0x18022921d  call    cs:__imp_GetSystemTimeAsFileTime
0x180229223  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180229227  mov     [rbp+var_10], rax
0x18022922b  call    cs:__imp_GetCurrentThreadId
0x180229231  mov     eax, eax
0x180229233  xor     [rbp+var_10], rax
0x180229237  call    cs:__imp_GetCurrentProcessId
0x18022923d  mov     eax, eax
0x18022923f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180229243  xor     [rbp+var_10], rax
0x180229247  call    cs:__imp_QueryPerformanceCounter
0x18022924d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180229250  lea     rcx, [rbp+var_10]
0x180229254  shl     rax, 20h
0x180229258  xor     rax, qword ptr [rbp+PerformanceCount]
0x18022925c  xor     rax, [rbp+var_10]
0x180229260  xor     rax, rcx
0x180229263  mov     rcx, 0FFFFFFFFFFFFh
0x18022926d  and     rax, rcx
0x180229270  mov     rcx, 2B992DDFA233h
0x18022927a  cmp     rax, rbx
0x18022927d  cmovz   rax, rcx
0x180229281  mov     cs:__security_cookie, rax
0x180229288  mov     rbx, [rsp+30h+arg_10]
0x18022928d  not     rax
0x180229290  mov     cs:__security_cookie_complement, rax
0x180229297  add     rsp, 30h
0x18022929b  pop     rbp
0x18022929c  retn
```
