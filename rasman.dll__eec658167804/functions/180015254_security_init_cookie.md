# __security_init_cookie

- ea: `0x180015254`
- end: `0x180015331`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014f00`

## callees

- `0x180015254`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800152a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800152a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001529b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001529b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800152de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800152de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001528d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001528d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800152b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800152c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800152b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800152c3`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180015254  mov     [rsp-8+arg_18], rbx
0x180015259  push    rbp
0x18001525a  mov     rbp, rsp
0x18001525d  sub     rsp, 20h
0x180015261  xor     eax, eax
0x180015263  mov     rbx, 2B992DDFA232h
0x18001526d  mov     [rbp+arg_0], rax
0x180015271  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180015275  mov     qword ptr [rbp+PerformanceCount], rax
0x180015279  mov     rax, cs:__security_cookie
0x180015280  cmp     rax, rbx
0x180015283  jnz     loc_18001531C
0x180015289  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001528d  call    cs:__imp_GetSystemTimeAsFileTime
0x180015293  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180015297  mov     [rbp+arg_0], rax
0x18001529b  call    cs:__imp_GetCurrentProcessId
0x1800152a1  mov     eax, eax
0x1800152a3  xor     [rbp+arg_0], rax
0x1800152a7  call    cs:__imp_GetCurrentThreadId
0x1800152ad  mov     eax, eax
0x1800152af  xor     [rbp+arg_0], rax
0x1800152b3  call    cs:__imp_GetTickCount
0x1800152b9  mov     eax, eax
0x1800152bb  shl     rax, 18h
0x1800152bf  xor     [rbp+arg_0], rax
0x1800152c3  call    cs:__imp_GetTickCount
0x1800152c9  mov     eax, eax
0x1800152cb  lea     rcx, [rbp+arg_0]
0x1800152cf  xor     rax, [rbp+arg_0]
0x1800152d3  xor     rax, rcx
0x1800152d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800152da  mov     [rbp+arg_0], rax
0x1800152de  call    cs:__imp_QueryPerformanceCounter
0x1800152e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800152e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800152f1  shl     rax, 20h
0x1800152f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800152f9  xor     rax, [rbp+arg_0]
0x1800152fd  and     rax, rcx
0x180015300  mov     rcx, rax
0x180015303  cmp     rax, rbx
0x180015306  jnz     short loc_180015315
0x180015308  mov     rax, 2B992DDFA233h
0x180015312  mov     rcx, rax
0x180015315  mov     cs:__security_cookie, rcx
0x18001531c  mov     rbx, [rsp+20h+arg_18]
0x180015321  not     rax
0x180015324  mov     cs:__security_cookie_complement, rax
0x18001532b  add     rsp, 20h
0x18001532f  pop     rbp
0x180015330  retn
```
