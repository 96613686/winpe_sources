# __security_init_cookie

- ea: `0x1400024ac`
- end: `0x140002561`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002160`

## callees

- `0x1400024ac`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400024ef`
- `KERNEL32!GetCurrentThreadId` at `0x1400024ef`
- `KERNEL32!GetCurrentProcessId` at `0x1400024fb`
- `KERNEL32!GetCurrentProcessId` at `0x1400024fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000250b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000250b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400024e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400024e1`

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
0x1400024ac  mov     [rsp-8+arg_10], rbx
0x1400024b1  push    rbp
0x1400024b2  mov     rbp, rsp
0x1400024b5  sub     rsp, 30h
0x1400024b9  mov     rax, cs:__security_cookie
0x1400024c0  mov     rbx, 2B992DDFA232h
0x1400024ca  cmp     rax, rbx
0x1400024cd  jnz     short loc_14000254C
0x1400024cf  xor     eax, eax
0x1400024d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400024d5  mov     [rbp+var_10], rax
0x1400024d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400024dd  mov     qword ptr [rbp+PerformanceCount], rax
0x1400024e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400024e7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400024eb  mov     [rbp+var_10], rax
0x1400024ef  call    cs:__imp_GetCurrentThreadId
0x1400024f5  mov     eax, eax
0x1400024f7  xor     [rbp+var_10], rax
0x1400024fb  call    cs:__imp_GetCurrentProcessId
0x140002501  mov     eax, eax
0x140002503  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002507  xor     [rbp+var_10], rax
0x14000250b  call    cs:__imp_QueryPerformanceCounter
0x140002511  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002514  lea     rcx, [rbp+var_10]
0x140002518  shl     rax, 20h
0x14000251c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002520  xor     rax, [rbp+var_10]
0x140002524  xor     rax, rcx
0x140002527  mov     rcx, 0FFFFFFFFFFFFh
0x140002531  and     rax, rcx
0x140002534  mov     rcx, 2B992DDFA233h
0x14000253e  cmp     rax, rbx
0x140002541  cmovz   rax, rcx
0x140002545  mov     cs:__security_cookie, rax
0x14000254c  mov     rbx, [rsp+30h+arg_10]
0x140002551  not     rax
0x140002554  mov     cs:__security_cookie_complement, rax
0x14000255b  add     rsp, 30h
0x14000255f  pop     rbp
0x140002560  retn
```
