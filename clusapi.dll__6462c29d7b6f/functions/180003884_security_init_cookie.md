# __security_init_cookie

- ea: `0x180003884`
- end: `0x180003939`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ef0`

## callees

- `0x180003884`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800038d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800038d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800038b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800038b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800038e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800038e3`

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
0x180003884  mov     [rsp-8+arg_10], rbx
0x180003889  push    rbp
0x18000388a  mov     rbp, rsp
0x18000388d  sub     rsp, 30h
0x180003891  mov     rax, cs:__security_cookie
0x180003898  mov     rbx, 2B992DDFA232h
0x1800038a2  cmp     rax, rbx
0x1800038a5  jnz     short loc_180003924
0x1800038a7  xor     eax, eax
0x1800038a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800038ad  mov     [rbp+var_10], rax
0x1800038b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800038b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800038b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800038bf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800038c3  mov     [rbp+var_10], rax
0x1800038c7  call    cs:__imp_GetCurrentThreadId
0x1800038cd  mov     eax, eax
0x1800038cf  xor     [rbp+var_10], rax
0x1800038d3  call    cs:__imp_GetCurrentProcessId
0x1800038d9  mov     eax, eax
0x1800038db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800038df  xor     [rbp+var_10], rax
0x1800038e3  call    cs:__imp_QueryPerformanceCounter
0x1800038e9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800038ec  lea     rcx, [rbp+var_10]
0x1800038f0  shl     rax, 20h
0x1800038f4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800038f8  xor     rax, [rbp+var_10]
0x1800038fc  xor     rax, rcx
0x1800038ff  mov     rcx, 0FFFFFFFFFFFFh
0x180003909  and     rax, rcx
0x18000390c  mov     rcx, 2B992DDFA233h
0x180003916  cmp     rax, rbx
0x180003919  cmovz   rax, rcx
0x18000391d  mov     cs:__security_cookie, rax
0x180003924  mov     rbx, [rsp+30h+arg_10]
0x180003929  not     rax
0x18000392c  mov     cs:__security_cookie_complement, rax
0x180003933  add     rsp, 30h
0x180003937  pop     rbp
0x180003938  retn
```
