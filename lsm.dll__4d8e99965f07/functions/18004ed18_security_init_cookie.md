# __security_init_cookie

- ea: `0x18004ed18`
- end: `0x18004edcd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e800`

## callees

- `0x18004ed18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ed5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ed5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ed67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ed67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004ed4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004ed4d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004ed77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004ed77`

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
0x18004ed18  mov     [rsp-8+arg_10], rbx
0x18004ed1d  push    rbp
0x18004ed1e  mov     rbp, rsp
0x18004ed21  sub     rsp, 30h
0x18004ed25  mov     rax, cs:__security_cookie
0x18004ed2c  mov     rbx, 2B992DDFA232h
0x18004ed36  cmp     rax, rbx
0x18004ed39  jnz     short loc_18004EDB8
0x18004ed3b  xor     eax, eax
0x18004ed3d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004ed41  mov     [rbp+var_10], rax
0x18004ed45  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004ed49  mov     qword ptr [rbp+PerformanceCount], rax
0x18004ed4d  call    cs:__imp_GetSystemTimeAsFileTime
0x18004ed53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004ed57  mov     [rbp+var_10], rax
0x18004ed5b  call    cs:__imp_GetCurrentThreadId
0x18004ed61  mov     eax, eax
0x18004ed63  xor     [rbp+var_10], rax
0x18004ed67  call    cs:__imp_GetCurrentProcessId
0x18004ed6d  mov     eax, eax
0x18004ed6f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004ed73  xor     [rbp+var_10], rax
0x18004ed77  call    cs:__imp_QueryPerformanceCounter
0x18004ed7d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004ed80  lea     rcx, [rbp+var_10]
0x18004ed84  shl     rax, 20h
0x18004ed88  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004ed8c  xor     rax, [rbp+var_10]
0x18004ed90  xor     rax, rcx
0x18004ed93  mov     rcx, 0FFFFFFFFFFFFh
0x18004ed9d  and     rax, rcx
0x18004eda0  mov     rcx, 2B992DDFA233h
0x18004edaa  cmp     rax, rbx
0x18004edad  cmovz   rax, rcx
0x18004edb1  mov     cs:__security_cookie, rax
0x18004edb8  mov     rbx, [rsp+30h+arg_10]
0x18004edbd  not     rax
0x18004edc0  mov     cs:__security_cookie_complement, rax
0x18004edc7  add     rsp, 30h
0x18004edcb  pop     rbp
0x18004edcc  retn
```
