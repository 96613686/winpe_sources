# __security_init_cookie

- ea: `0x180059014`
- end: `0x1800590f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800588a0`

## callees

- `0x180059014`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180059067`
- `KERNEL32!GetCurrentThreadId` at `0x180059067`
- `KERNEL32!GetCurrentProcessId` at `0x18005905b`
- `KERNEL32!GetCurrentProcessId` at `0x18005905b`
- `KERNEL32!GetTickCount` at `0x180059073`
- `KERNEL32!GetTickCount` at `0x180059083`
- `KERNEL32!GetTickCount` at `0x180059073`
- `KERNEL32!GetTickCount` at `0x180059083`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005904d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005904d`
- `KERNEL32!QueryPerformanceCounter` at `0x18005909e`
- `KERNEL32!QueryPerformanceCounter` at `0x18005909e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180059014  mov     [rsp-8+arg_18], rbx
0x180059019  push    rbp
0x18005901a  mov     rbp, rsp
0x18005901d  sub     rsp, 20h
0x180059021  xor     eax, eax
0x180059023  mov     rbx, 2B992DDFA232h
0x18005902d  mov     [rbp+arg_0], rax
0x180059031  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180059035  mov     qword ptr [rbp+PerformanceCount], rax
0x180059039  mov     rax, cs:__security_cookie
0x180059040  cmp     rax, rbx
0x180059043  jnz     loc_1800590DC
0x180059049  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005904d  call    cs:__imp_GetSystemTimeAsFileTime
0x180059053  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180059057  mov     [rbp+arg_0], rax
0x18005905b  call    cs:__imp_GetCurrentProcessId
0x180059061  mov     eax, eax
0x180059063  xor     [rbp+arg_0], rax
0x180059067  call    cs:__imp_GetCurrentThreadId
0x18005906d  mov     eax, eax
0x18005906f  xor     [rbp+arg_0], rax
0x180059073  call    cs:__imp_GetTickCount
0x180059079  mov     eax, eax
0x18005907b  shl     rax, 18h
0x18005907f  xor     [rbp+arg_0], rax
0x180059083  call    cs:__imp_GetTickCount
0x180059089  mov     eax, eax
0x18005908b  lea     rcx, [rbp+arg_0]
0x18005908f  xor     rax, [rbp+arg_0]
0x180059093  xor     rax, rcx
0x180059096  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005909a  mov     [rbp+arg_0], rax
0x18005909e  call    cs:__imp_QueryPerformanceCounter
0x1800590a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800590a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800590b1  shl     rax, 20h
0x1800590b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800590b9  xor     rax, [rbp+arg_0]
0x1800590bd  and     rax, rcx
0x1800590c0  mov     rcx, rax
0x1800590c3  cmp     rax, rbx
0x1800590c6  jnz     short loc_1800590D5
0x1800590c8  mov     rax, 2B992DDFA233h
0x1800590d2  mov     rcx, rax
0x1800590d5  mov     cs:__security_cookie, rcx
0x1800590dc  mov     rbx, [rsp+20h+arg_18]
0x1800590e1  not     rax
0x1800590e4  mov     cs:__security_cookie_complement, rax
0x1800590eb  add     rsp, 20h
0x1800590ef  pop     rbp
0x1800590f0  retn
```
