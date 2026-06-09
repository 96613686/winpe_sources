# __security_init_cookie

- ea: `0x180002734`
- end: `0x180002811`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d30`

## callees

- `0x180002734`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002793`
- `KERNEL32!GetTickCount` at `0x1800027a3`
- `KERNEL32!GetTickCount` at `0x180002793`
- `KERNEL32!GetTickCount` at `0x1800027a3`
- `KERNEL32!GetCurrentThreadId` at `0x180002787`
- `KERNEL32!GetCurrentThreadId` at `0x180002787`
- `KERNEL32!GetCurrentProcessId` at `0x18000277b`
- `KERNEL32!GetCurrentProcessId` at `0x18000277b`
- `KERNEL32!QueryPerformanceCounter` at `0x1800027be`
- `KERNEL32!QueryPerformanceCounter` at `0x1800027be`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000276d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000276d`

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
0x180002734  mov     [rsp-8+arg_18], rbx
0x180002739  push    rbp
0x18000273a  mov     rbp, rsp
0x18000273d  sub     rsp, 20h
0x180002741  xor     eax, eax
0x180002743  mov     rbx, 2B992DDFA232h
0x18000274d  mov     [rbp+arg_0], rax
0x180002751  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002755  mov     qword ptr [rbp+PerformanceCount], rax
0x180002759  mov     rax, cs:__security_cookie
0x180002760  cmp     rax, rbx
0x180002763  jnz     loc_1800027FC
0x180002769  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000276d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002773  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002777  mov     [rbp+arg_0], rax
0x18000277b  call    cs:__imp_GetCurrentProcessId
0x180002781  mov     eax, eax
0x180002783  xor     [rbp+arg_0], rax
0x180002787  call    cs:__imp_GetCurrentThreadId
0x18000278d  mov     eax, eax
0x18000278f  xor     [rbp+arg_0], rax
0x180002793  call    cs:__imp_GetTickCount
0x180002799  mov     eax, eax
0x18000279b  shl     rax, 18h
0x18000279f  xor     [rbp+arg_0], rax
0x1800027a3  call    cs:__imp_GetTickCount
0x1800027a9  mov     eax, eax
0x1800027ab  lea     rcx, [rbp+arg_0]
0x1800027af  xor     rax, [rbp+arg_0]
0x1800027b3  xor     rax, rcx
0x1800027b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800027ba  mov     [rbp+arg_0], rax
0x1800027be  call    cs:__imp_QueryPerformanceCounter
0x1800027c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800027c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800027d1  shl     rax, 20h
0x1800027d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800027d9  xor     rax, [rbp+arg_0]
0x1800027dd  and     rax, rcx
0x1800027e0  mov     rcx, rax
0x1800027e3  cmp     rax, rbx
0x1800027e6  jnz     short loc_1800027F5
0x1800027e8  mov     rax, 2B992DDFA233h
0x1800027f2  mov     rcx, rax
0x1800027f5  mov     cs:__security_cookie, rcx
0x1800027fc  mov     rbx, [rsp+20h+arg_18]
0x180002801  not     rax
0x180002804  mov     cs:__security_cookie_complement, rax
0x18000280b  add     rsp, 20h
0x18000280f  pop     rbp
0x180002810  retn
```
