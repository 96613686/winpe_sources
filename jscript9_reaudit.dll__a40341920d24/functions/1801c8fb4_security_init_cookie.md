# __security_init_cookie

- ea: `0x1801c8fb4`
- end: `0x1801c9091`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801c8400`

## callees

- `0x1801c8fb4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1801c903e`
- `KERNEL32!QueryPerformanceCounter` at `0x1801c903e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801c8fed`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801c8fed`
- `KERNEL32!GetTickCount` at `0x1801c9013`
- `KERNEL32!GetTickCount` at `0x1801c9023`
- `KERNEL32!GetTickCount` at `0x1801c9013`
- `KERNEL32!GetTickCount` at `0x1801c9023`
- `KERNEL32!GetCurrentProcessId` at `0x1801c8ffb`
- `KERNEL32!GetCurrentProcessId` at `0x1801c8ffb`
- `KERNEL32!GetCurrentThreadId` at `0x1801c9007`
- `KERNEL32!GetCurrentThreadId` at `0x1801c9007`

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
0x1801c8fb4  mov     [rsp-8+arg_18], rbx
0x1801c8fb9  push    rbp
0x1801c8fba  mov     rbp, rsp
0x1801c8fbd  sub     rsp, 20h
0x1801c8fc1  xor     eax, eax
0x1801c8fc3  mov     rbx, 2B992DDFA232h
0x1801c8fcd  mov     [rbp+arg_0], rax
0x1801c8fd1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1801c8fd5  mov     qword ptr [rbp+PerformanceCount], rax
0x1801c8fd9  mov     rax, cs:__security_cookie
0x1801c8fe0  cmp     rax, rbx
0x1801c8fe3  jnz     loc_1801C907C
0x1801c8fe9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801c8fed  call    cs:__imp_GetSystemTimeAsFileTime
0x1801c8ff3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801c8ff7  mov     [rbp+arg_0], rax
0x1801c8ffb  call    cs:__imp_GetCurrentProcessId
0x1801c9001  mov     eax, eax
0x1801c9003  xor     [rbp+arg_0], rax
0x1801c9007  call    cs:__imp_GetCurrentThreadId
0x1801c900d  mov     eax, eax
0x1801c900f  xor     [rbp+arg_0], rax
0x1801c9013  call    cs:__imp_GetTickCount
0x1801c9019  mov     eax, eax
0x1801c901b  shl     rax, 18h
0x1801c901f  xor     [rbp+arg_0], rax
0x1801c9023  call    cs:__imp_GetTickCount
0x1801c9029  mov     eax, eax
0x1801c902b  lea     rcx, [rbp+arg_0]
0x1801c902f  xor     rax, [rbp+arg_0]
0x1801c9033  xor     rax, rcx
0x1801c9036  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1801c903a  mov     [rbp+arg_0], rax
0x1801c903e  call    cs:__imp_QueryPerformanceCounter
0x1801c9044  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801c9047  mov     rcx, 0FFFFFFFFFFFFh
0x1801c9051  shl     rax, 20h
0x1801c9055  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801c9059  xor     rax, [rbp+arg_0]
0x1801c905d  and     rax, rcx
0x1801c9060  mov     rcx, rax
0x1801c9063  cmp     rax, rbx
0x1801c9066  jnz     short loc_1801C9075
0x1801c9068  mov     rax, 2B992DDFA233h
0x1801c9072  mov     rcx, rax
0x1801c9075  mov     cs:__security_cookie, rcx
0x1801c907c  mov     rbx, [rsp+20h+arg_18]
0x1801c9081  not     rax
0x1801c9084  mov     cs:__security_cookie_complement, rax
0x1801c908b  add     rsp, 20h
0x1801c908f  pop     rbp
0x1801c9090  retn
```
