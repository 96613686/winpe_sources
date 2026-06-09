# __security_init_cookie

- ea: `0x180002594`
- end: `0x180002671`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f20`

## callees

- `0x180002594`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800025f3`
- `KERNEL32!GetTickCount` at `0x180002603`
- `KERNEL32!GetTickCount` at `0x1800025f3`
- `KERNEL32!GetTickCount` at `0x180002603`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800025cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800025cd`
- `KERNEL32!GetCurrentThreadId` at `0x1800025e7`
- `KERNEL32!GetCurrentThreadId` at `0x1800025e7`
- `KERNEL32!GetCurrentProcessId` at `0x1800025db`
- `KERNEL32!GetCurrentProcessId` at `0x1800025db`
- `KERNEL32!QueryPerformanceCounter` at `0x18000261e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000261e`

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
0x180002594  mov     [rsp-8+arg_18], rbx
0x180002599  push    rbp
0x18000259a  mov     rbp, rsp
0x18000259d  sub     rsp, 20h
0x1800025a1  xor     eax, eax
0x1800025a3  mov     rbx, 2B992DDFA232h
0x1800025ad  mov     [rbp+arg_0], rax
0x1800025b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800025b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800025b9  mov     rax, cs:__security_cookie
0x1800025c0  cmp     rax, rbx
0x1800025c3  jnz     loc_18000265C
0x1800025c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800025cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800025d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800025d7  mov     [rbp+arg_0], rax
0x1800025db  call    cs:__imp_GetCurrentProcessId
0x1800025e1  mov     eax, eax
0x1800025e3  xor     [rbp+arg_0], rax
0x1800025e7  call    cs:__imp_GetCurrentThreadId
0x1800025ed  mov     eax, eax
0x1800025ef  xor     [rbp+arg_0], rax
0x1800025f3  call    cs:__imp_GetTickCount
0x1800025f9  mov     eax, eax
0x1800025fb  shl     rax, 18h
0x1800025ff  xor     [rbp+arg_0], rax
0x180002603  call    cs:__imp_GetTickCount
0x180002609  mov     eax, eax
0x18000260b  lea     rcx, [rbp+arg_0]
0x18000260f  xor     rax, [rbp+arg_0]
0x180002613  xor     rax, rcx
0x180002616  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000261a  mov     [rbp+arg_0], rax
0x18000261e  call    cs:__imp_QueryPerformanceCounter
0x180002624  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002627  mov     rcx, 0FFFFFFFFFFFFh
0x180002631  shl     rax, 20h
0x180002635  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002639  xor     rax, [rbp+arg_0]
0x18000263d  and     rax, rcx
0x180002640  mov     rcx, rax
0x180002643  cmp     rax, rbx
0x180002646  jnz     short loc_180002655
0x180002648  mov     rax, 2B992DDFA233h
0x180002652  mov     rcx, rax
0x180002655  mov     cs:__security_cookie, rcx
0x18000265c  mov     rbx, [rsp+20h+arg_18]
0x180002661  not     rax
0x180002664  mov     cs:__security_cookie_complement, rax
0x18000266b  add     rsp, 20h
0x18000266f  pop     rbp
0x180002670  retn
```
