# __security_init_cookie

- ea: `0x140001844`
- end: `0x140001921`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400012f0`

## callees

- `0x140001844`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400018a3`
- `KERNEL32!GetTickCount` at `0x1400018b3`
- `KERNEL32!GetTickCount` at `0x1400018a3`
- `KERNEL32!GetTickCount` at `0x1400018b3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000187d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000187d`
- `KERNEL32!GetCurrentThreadId` at `0x140001897`
- `KERNEL32!GetCurrentThreadId` at `0x140001897`
- `KERNEL32!QueryPerformanceCounter` at `0x1400018ce`
- `KERNEL32!QueryPerformanceCounter` at `0x1400018ce`
- `KERNEL32!GetCurrentProcessId` at `0x14000188b`
- `KERNEL32!GetCurrentProcessId` at `0x14000188b`

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
0x140001844  mov     [rsp-8+arg_18], rbx
0x140001849  push    rbp
0x14000184a  mov     rbp, rsp
0x14000184d  sub     rsp, 20h
0x140001851  xor     eax, eax
0x140001853  mov     rbx, 2B992DDFA232h
0x14000185d  mov     [rbp+arg_0], rax
0x140001861  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001865  mov     qword ptr [rbp+PerformanceCount], rax
0x140001869  mov     rax, cs:__security_cookie
0x140001870  cmp     rax, rbx
0x140001873  jnz     loc_14000190C
0x140001879  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000187d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001883  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001887  mov     [rbp+arg_0], rax
0x14000188b  call    cs:__imp_GetCurrentProcessId
0x140001891  mov     eax, eax
0x140001893  xor     [rbp+arg_0], rax
0x140001897  call    cs:__imp_GetCurrentThreadId
0x14000189d  mov     eax, eax
0x14000189f  xor     [rbp+arg_0], rax
0x1400018a3  call    cs:__imp_GetTickCount
0x1400018a9  mov     eax, eax
0x1400018ab  shl     rax, 18h
0x1400018af  xor     [rbp+arg_0], rax
0x1400018b3  call    cs:__imp_GetTickCount
0x1400018b9  mov     eax, eax
0x1400018bb  lea     rcx, [rbp+arg_0]
0x1400018bf  xor     rax, [rbp+arg_0]
0x1400018c3  xor     rax, rcx
0x1400018c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400018ca  mov     [rbp+arg_0], rax
0x1400018ce  call    cs:__imp_QueryPerformanceCounter
0x1400018d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400018d7  mov     rcx, 0FFFFFFFFFFFFh
0x1400018e1  shl     rax, 20h
0x1400018e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400018e9  xor     rax, [rbp+arg_0]
0x1400018ed  and     rax, rcx
0x1400018f0  mov     rcx, rax
0x1400018f3  cmp     rax, rbx
0x1400018f6  jnz     short loc_140001905
0x1400018f8  mov     rax, 2B992DDFA233h
0x140001902  mov     rcx, rax
0x140001905  mov     cs:__security_cookie, rcx
0x14000190c  mov     rbx, [rsp+20h+arg_18]
0x140001911  not     rax
0x140001914  mov     cs:__security_cookie_complement, rax
0x14000191b  add     rsp, 20h
0x14000191f  pop     rbp
0x140001920  retn
```
