# __security_init_cookie

- ea: `0x1800025c4`
- end: `0x1800026a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ad0`

## callees

- `0x1800025c4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000264e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000264e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800025fd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800025fd`
- `KERNEL32!GetTickCount` at `0x180002623`
- `KERNEL32!GetTickCount` at `0x180002633`
- `KERNEL32!GetTickCount` at `0x180002623`
- `KERNEL32!GetTickCount` at `0x180002633`
- `KERNEL32!GetCurrentThreadId` at `0x180002617`
- `KERNEL32!GetCurrentThreadId` at `0x180002617`
- `KERNEL32!GetCurrentProcessId` at `0x18000260b`
- `KERNEL32!GetCurrentProcessId` at `0x18000260b`

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
0x1800025c4  mov     [rsp-8+arg_18], rbx
0x1800025c9  push    rbp
0x1800025ca  mov     rbp, rsp
0x1800025cd  sub     rsp, 20h
0x1800025d1  xor     eax, eax
0x1800025d3  mov     rbx, 2B992DDFA232h
0x1800025dd  mov     [rbp+arg_0], rax
0x1800025e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800025e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800025e9  mov     rax, cs:__security_cookie
0x1800025f0  cmp     rax, rbx
0x1800025f3  jnz     loc_18000268C
0x1800025f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800025fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002603  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002607  mov     [rbp+arg_0], rax
0x18000260b  call    cs:__imp_GetCurrentProcessId
0x180002611  mov     eax, eax
0x180002613  xor     [rbp+arg_0], rax
0x180002617  call    cs:__imp_GetCurrentThreadId
0x18000261d  mov     eax, eax
0x18000261f  xor     [rbp+arg_0], rax
0x180002623  call    cs:__imp_GetTickCount
0x180002629  mov     eax, eax
0x18000262b  shl     rax, 18h
0x18000262f  xor     [rbp+arg_0], rax
0x180002633  call    cs:__imp_GetTickCount
0x180002639  mov     eax, eax
0x18000263b  lea     rcx, [rbp+arg_0]
0x18000263f  xor     rax, [rbp+arg_0]
0x180002643  xor     rax, rcx
0x180002646  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000264a  mov     [rbp+arg_0], rax
0x18000264e  call    cs:__imp_QueryPerformanceCounter
0x180002654  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002657  mov     rcx, 0FFFFFFFFFFFFh
0x180002661  shl     rax, 20h
0x180002665  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002669  xor     rax, [rbp+arg_0]
0x18000266d  and     rax, rcx
0x180002670  mov     rcx, rax
0x180002673  cmp     rax, rbx
0x180002676  jnz     short loc_180002685
0x180002678  mov     rax, 2B992DDFA233h
0x180002682  mov     rcx, rax
0x180002685  mov     cs:__security_cookie, rcx
0x18000268c  mov     rbx, [rsp+20h+arg_18]
0x180002691  not     rax
0x180002694  mov     cs:__security_cookie_complement, rax
0x18000269b  add     rsp, 20h
0x18000269f  pop     rbp
0x1800026a0  retn
```
