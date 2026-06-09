# __security_init_cookie

- ea: `0x180001894`
- end: `0x180001971`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001490`

## callees

- `0x180001894`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000191e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000191e`
- `KERNEL32!GetTickCount` at `0x1800018f3`
- `KERNEL32!GetTickCount` at `0x180001903`
- `KERNEL32!GetTickCount` at `0x1800018f3`
- `KERNEL32!GetTickCount` at `0x180001903`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800018cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800018cd`
- `KERNEL32!GetCurrentThreadId` at `0x1800018e7`
- `KERNEL32!GetCurrentThreadId` at `0x1800018e7`
- `KERNEL32!GetCurrentProcessId` at `0x1800018db`
- `KERNEL32!GetCurrentProcessId` at `0x1800018db`

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
0x180001894  mov     [rsp-8+arg_18], rbx
0x180001899  push    rbp
0x18000189a  mov     rbp, rsp
0x18000189d  sub     rsp, 20h
0x1800018a1  xor     eax, eax
0x1800018a3  mov     rbx, 2B992DDFA232h
0x1800018ad  mov     [rbp+arg_0], rax
0x1800018b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800018b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800018b9  mov     rax, cs:__security_cookie
0x1800018c0  cmp     rax, rbx
0x1800018c3  jnz     loc_18000195C
0x1800018c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800018cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800018d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800018d7  mov     [rbp+arg_0], rax
0x1800018db  call    cs:__imp_GetCurrentProcessId
0x1800018e1  mov     eax, eax
0x1800018e3  xor     [rbp+arg_0], rax
0x1800018e7  call    cs:__imp_GetCurrentThreadId
0x1800018ed  mov     eax, eax
0x1800018ef  xor     [rbp+arg_0], rax
0x1800018f3  call    cs:__imp_GetTickCount
0x1800018f9  mov     eax, eax
0x1800018fb  shl     rax, 18h
0x1800018ff  xor     [rbp+arg_0], rax
0x180001903  call    cs:__imp_GetTickCount
0x180001909  mov     eax, eax
0x18000190b  lea     rcx, [rbp+arg_0]
0x18000190f  xor     rax, [rbp+arg_0]
0x180001913  xor     rax, rcx
0x180001916  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000191a  mov     [rbp+arg_0], rax
0x18000191e  call    cs:__imp_QueryPerformanceCounter
0x180001924  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001927  mov     rcx, 0FFFFFFFFFFFFh
0x180001931  shl     rax, 20h
0x180001935  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001939  xor     rax, [rbp+arg_0]
0x18000193d  and     rax, rcx
0x180001940  mov     rcx, rax
0x180001943  cmp     rax, rbx
0x180001946  jnz     short loc_180001955
0x180001948  mov     rax, 2B992DDFA233h
0x180001952  mov     rcx, rax
0x180001955  mov     cs:__security_cookie, rcx
0x18000195c  mov     rbx, [rsp+20h+arg_18]
0x180001961  not     rax
0x180001964  mov     cs:__security_cookie_complement, rax
0x18000196b  add     rsp, 20h
0x18000196f  pop     rbp
0x180001970  retn
```
