# __security_init_cookie

- ea: `0x180054868`
- end: `0x18005491d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800540f0`

## callees

- `0x180054868`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800548ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800548ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800548b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800548b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005489d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005489d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800548c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800548c7`

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
0x180054868  mov     [rsp-8+arg_10], rbx
0x18005486d  push    rbp
0x18005486e  mov     rbp, rsp
0x180054871  sub     rsp, 30h
0x180054875  mov     rax, cs:__security_cookie
0x18005487c  mov     rbx, 2B992DDFA232h
0x180054886  cmp     rax, rbx
0x180054889  jnz     short loc_180054908
0x18005488b  xor     eax, eax
0x18005488d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180054891  mov     [rbp+var_10], rax
0x180054895  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180054899  mov     qword ptr [rbp+PerformanceCount], rax
0x18005489d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800548a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800548a7  mov     [rbp+var_10], rax
0x1800548ab  call    cs:__imp_GetCurrentThreadId
0x1800548b1  mov     eax, eax
0x1800548b3  xor     [rbp+var_10], rax
0x1800548b7  call    cs:__imp_GetCurrentProcessId
0x1800548bd  mov     eax, eax
0x1800548bf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800548c3  xor     [rbp+var_10], rax
0x1800548c7  call    cs:__imp_QueryPerformanceCounter
0x1800548cd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800548d0  lea     rcx, [rbp+var_10]
0x1800548d4  shl     rax, 20h
0x1800548d8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800548dc  xor     rax, [rbp+var_10]
0x1800548e0  xor     rax, rcx
0x1800548e3  mov     rcx, 0FFFFFFFFFFFFh
0x1800548ed  and     rax, rcx
0x1800548f0  mov     rcx, 2B992DDFA233h
0x1800548fa  cmp     rax, rbx
0x1800548fd  cmovz   rax, rcx
0x180054901  mov     cs:__security_cookie, rax
0x180054908  mov     rbx, [rsp+30h+arg_10]
0x18005490d  not     rax
0x180054910  mov     cs:__security_cookie_complement, rax
0x180054917  add     rsp, 30h
0x18005491b  pop     rbp
0x18005491c  retn
```
