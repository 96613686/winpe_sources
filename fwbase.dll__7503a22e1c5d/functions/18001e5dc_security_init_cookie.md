# __security_init_cookie

- ea: `0x18001e5dc`
- end: `0x18001e691`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e170`

## callees

- `0x18001e5dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e611`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001e611`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e62b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e62b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e63b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001e63b`

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
0x18001e5dc  mov     [rsp-8+arg_10], rbx
0x18001e5e1  push    rbp
0x18001e5e2  mov     rbp, rsp
0x18001e5e5  sub     rsp, 30h
0x18001e5e9  mov     rax, cs:__security_cookie
0x18001e5f0  mov     rbx, 2B992DDFA232h
0x18001e5fa  cmp     rax, rbx
0x18001e5fd  jnz     short loc_18001E67C
0x18001e5ff  xor     eax, eax
0x18001e601  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001e605  mov     [rbp+var_10], rax
0x18001e609  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001e60d  mov     qword ptr [rbp+PerformanceCount], rax
0x18001e611  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e617  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001e61b  mov     [rbp+var_10], rax
0x18001e61f  call    cs:__imp_GetCurrentThreadId
0x18001e625  mov     eax, eax
0x18001e627  xor     [rbp+var_10], rax
0x18001e62b  call    cs:__imp_GetCurrentProcessId
0x18001e631  mov     eax, eax
0x18001e633  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001e637  xor     [rbp+var_10], rax
0x18001e63b  call    cs:__imp_QueryPerformanceCounter
0x18001e641  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001e644  lea     rcx, [rbp+var_10]
0x18001e648  shl     rax, 20h
0x18001e64c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001e650  xor     rax, [rbp+var_10]
0x18001e654  xor     rax, rcx
0x18001e657  mov     rcx, 0FFFFFFFFFFFFh
0x18001e661  and     rax, rcx
0x18001e664  mov     rcx, 2B992DDFA233h
0x18001e66e  cmp     rax, rbx
0x18001e671  cmovz   rax, rcx
0x18001e675  mov     cs:__security_cookie, rax
0x18001e67c  mov     rbx, [rsp+30h+arg_10]
0x18001e681  not     rax
0x18001e684  mov     cs:__security_cookie_complement, rax
0x18001e68b  add     rsp, 30h
0x18001e68f  pop     rbp
0x18001e690  retn
```
