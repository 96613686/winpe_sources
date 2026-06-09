# __security_init_cookie

- ea: `0x140003be4`
- end: `0x140003cc1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400033d0`

## callees

- `0x140003be4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003c37`
- `KERNEL32!GetCurrentThreadId` at `0x140003c37`
- `KERNEL32!GetTickCount` at `0x140003c43`
- `KERNEL32!GetTickCount` at `0x140003c53`
- `KERNEL32!GetTickCount` at `0x140003c43`
- `KERNEL32!GetTickCount` at `0x140003c53`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140003c1d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140003c1d`
- `KERNEL32!QueryPerformanceCounter` at `0x140003c6e`
- `KERNEL32!QueryPerformanceCounter` at `0x140003c6e`
- `KERNEL32!GetCurrentProcessId` at `0x140003c2b`
- `KERNEL32!GetCurrentProcessId` at `0x140003c2b`

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
0x140003be4  mov     [rsp-8+arg_18], rbx
0x140003be9  push    rbp
0x140003bea  mov     rbp, rsp
0x140003bed  sub     rsp, 20h
0x140003bf1  xor     eax, eax
0x140003bf3  mov     rbx, 2B992DDFA232h
0x140003bfd  mov     [rbp+arg_0], rax
0x140003c01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140003c05  mov     qword ptr [rbp+PerformanceCount], rax
0x140003c09  mov     rax, cs:__security_cookie
0x140003c10  cmp     rax, rbx
0x140003c13  jnz     loc_140003CAC
0x140003c19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003c1d  call    cs:__imp_GetSystemTimeAsFileTime
0x140003c23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140003c27  mov     [rbp+arg_0], rax
0x140003c2b  call    cs:__imp_GetCurrentProcessId
0x140003c31  mov     eax, eax
0x140003c33  xor     [rbp+arg_0], rax
0x140003c37  call    cs:__imp_GetCurrentThreadId
0x140003c3d  mov     eax, eax
0x140003c3f  xor     [rbp+arg_0], rax
0x140003c43  call    cs:__imp_GetTickCount
0x140003c49  mov     eax, eax
0x140003c4b  shl     rax, 18h
0x140003c4f  xor     [rbp+arg_0], rax
0x140003c53  call    cs:__imp_GetTickCount
0x140003c59  mov     eax, eax
0x140003c5b  lea     rcx, [rbp+arg_0]
0x140003c5f  xor     rax, [rbp+arg_0]
0x140003c63  xor     rax, rcx
0x140003c66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140003c6a  mov     [rbp+arg_0], rax
0x140003c6e  call    cs:__imp_QueryPerformanceCounter
0x140003c74  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003c77  mov     rcx, 0FFFFFFFFFFFFh
0x140003c81  shl     rax, 20h
0x140003c85  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003c89  xor     rax, [rbp+arg_0]
0x140003c8d  and     rax, rcx
0x140003c90  mov     rcx, rax
0x140003c93  cmp     rax, rbx
0x140003c96  jnz     short loc_140003CA5
0x140003c98  mov     rax, 2B992DDFA233h
0x140003ca2  mov     rcx, rax
0x140003ca5  mov     cs:__security_cookie, rcx
0x140003cac  mov     rbx, [rsp+20h+arg_18]
0x140003cb1  not     rax
0x140003cb4  mov     cs:__security_cookie_complement, rax
0x140003cbb  add     rsp, 20h
0x140003cbf  pop     rbp
0x140003cc0  retn
```
