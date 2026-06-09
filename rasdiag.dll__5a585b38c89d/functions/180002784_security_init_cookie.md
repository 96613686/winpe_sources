# __security_init_cookie

- ea: `0x180002784`
- end: `0x180002861`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001db0`

## callees

- `0x180002784`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800027e3`
- `KERNEL32!GetTickCount` at `0x1800027f3`
- `KERNEL32!GetTickCount` at `0x1800027e3`
- `KERNEL32!GetTickCount` at `0x1800027f3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800027bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800027bd`
- `KERNEL32!GetCurrentThreadId` at `0x1800027d7`
- `KERNEL32!GetCurrentThreadId` at `0x1800027d7`
- `KERNEL32!GetCurrentProcessId` at `0x1800027cb`
- `KERNEL32!GetCurrentProcessId` at `0x1800027cb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000280e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000280e`

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
0x180002784  mov     [rsp-8+arg_18], rbx
0x180002789  push    rbp
0x18000278a  mov     rbp, rsp
0x18000278d  sub     rsp, 20h
0x180002791  xor     eax, eax
0x180002793  mov     rbx, 2B992DDFA232h
0x18000279d  mov     [rbp+arg_0], rax
0x1800027a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800027a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800027a9  mov     rax, cs:__security_cookie
0x1800027b0  cmp     rax, rbx
0x1800027b3  jnz     loc_18000284C
0x1800027b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800027bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800027c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800027c7  mov     [rbp+arg_0], rax
0x1800027cb  call    cs:__imp_GetCurrentProcessId
0x1800027d1  mov     eax, eax
0x1800027d3  xor     [rbp+arg_0], rax
0x1800027d7  call    cs:__imp_GetCurrentThreadId
0x1800027dd  mov     eax, eax
0x1800027df  xor     [rbp+arg_0], rax
0x1800027e3  call    cs:__imp_GetTickCount
0x1800027e9  mov     eax, eax
0x1800027eb  shl     rax, 18h
0x1800027ef  xor     [rbp+arg_0], rax
0x1800027f3  call    cs:__imp_GetTickCount
0x1800027f9  mov     eax, eax
0x1800027fb  lea     rcx, [rbp+arg_0]
0x1800027ff  xor     rax, [rbp+arg_0]
0x180002803  xor     rax, rcx
0x180002806  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000280a  mov     [rbp+arg_0], rax
0x18000280e  call    cs:__imp_QueryPerformanceCounter
0x180002814  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002817  mov     rcx, 0FFFFFFFFFFFFh
0x180002821  shl     rax, 20h
0x180002825  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002829  xor     rax, [rbp+arg_0]
0x18000282d  and     rax, rcx
0x180002830  mov     rcx, rax
0x180002833  cmp     rax, rbx
0x180002836  jnz     short loc_180002845
0x180002838  mov     rax, 2B992DDFA233h
0x180002842  mov     rcx, rax
0x180002845  mov     cs:__security_cookie, rcx
0x18000284c  mov     rbx, [rsp+20h+arg_18]
0x180002851  not     rax
0x180002854  mov     cs:__security_cookie_complement, rax
0x18000285b  add     rsp, 20h
0x18000285f  pop     rbp
0x180002860  retn
```
