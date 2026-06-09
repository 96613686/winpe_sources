# __security_init_cookie

- ea: `0x18004d804`
- end: `0x18004d8e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d0d0`

## callees

- `0x18004d804`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18004d88e`
- `KERNEL32!QueryPerformanceCounter` at `0x18004d88e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004d83d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004d83d`
- `KERNEL32!GetTickCount` at `0x18004d863`
- `KERNEL32!GetTickCount` at `0x18004d873`
- `KERNEL32!GetTickCount` at `0x18004d863`
- `KERNEL32!GetTickCount` at `0x18004d873`
- `KERNEL32!GetCurrentThreadId` at `0x18004d857`
- `KERNEL32!GetCurrentThreadId` at `0x18004d857`
- `KERNEL32!GetCurrentProcessId` at `0x18004d84b`
- `KERNEL32!GetCurrentProcessId` at `0x18004d84b`

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
0x18004d804  mov     [rsp-8+arg_18], rbx
0x18004d809  push    rbp
0x18004d80a  mov     rbp, rsp
0x18004d80d  sub     rsp, 20h
0x18004d811  xor     eax, eax
0x18004d813  mov     rbx, 2B992DDFA232h
0x18004d81d  mov     [rbp+arg_0], rax
0x18004d821  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004d825  mov     qword ptr [rbp+PerformanceCount], rax
0x18004d829  mov     rax, cs:__security_cookie
0x18004d830  cmp     rax, rbx
0x18004d833  jnz     loc_18004D8CC
0x18004d839  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004d83d  call    cs:__imp_GetSystemTimeAsFileTime
0x18004d843  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004d847  mov     [rbp+arg_0], rax
0x18004d84b  call    cs:__imp_GetCurrentProcessId
0x18004d851  mov     eax, eax
0x18004d853  xor     [rbp+arg_0], rax
0x18004d857  call    cs:__imp_GetCurrentThreadId
0x18004d85d  mov     eax, eax
0x18004d85f  xor     [rbp+arg_0], rax
0x18004d863  call    cs:__imp_GetTickCount
0x18004d869  mov     eax, eax
0x18004d86b  shl     rax, 18h
0x18004d86f  xor     [rbp+arg_0], rax
0x18004d873  call    cs:__imp_GetTickCount
0x18004d879  mov     eax, eax
0x18004d87b  lea     rcx, [rbp+arg_0]
0x18004d87f  xor     rax, [rbp+arg_0]
0x18004d883  xor     rax, rcx
0x18004d886  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004d88a  mov     [rbp+arg_0], rax
0x18004d88e  call    cs:__imp_QueryPerformanceCounter
0x18004d894  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004d897  mov     rcx, 0FFFFFFFFFFFFh
0x18004d8a1  shl     rax, 20h
0x18004d8a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004d8a9  xor     rax, [rbp+arg_0]
0x18004d8ad  and     rax, rcx
0x18004d8b0  mov     rcx, rax
0x18004d8b3  cmp     rax, rbx
0x18004d8b6  jnz     short loc_18004D8C5
0x18004d8b8  mov     rax, 2B992DDFA233h
0x18004d8c2  mov     rcx, rax
0x18004d8c5  mov     cs:__security_cookie, rcx
0x18004d8cc  mov     rbx, [rsp+20h+arg_18]
0x18004d8d1  not     rax
0x18004d8d4  mov     cs:__security_cookie_complement, rax
0x18004d8db  add     rsp, 20h
0x18004d8df  pop     rbp
0x18004d8e0  retn
```
