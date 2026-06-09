# __security_init_cookie

- ea: `0x1800640f4`
- end: `0x1800641d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800637d0`

## callees

- `0x1800640f4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180064153`
- `KERNEL32!GetTickCount` at `0x180064163`
- `KERNEL32!GetTickCount` at `0x180064153`
- `KERNEL32!GetTickCount` at `0x180064163`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18006412d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18006412d`
- `KERNEL32!QueryPerformanceCounter` at `0x18006417e`
- `KERNEL32!QueryPerformanceCounter` at `0x18006417e`
- `KERNEL32!GetCurrentProcessId` at `0x18006413b`
- `KERNEL32!GetCurrentProcessId` at `0x18006413b`
- `KERNEL32!GetCurrentThreadId` at `0x180064147`
- `KERNEL32!GetCurrentThreadId` at `0x180064147`

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
0x1800640f4  mov     [rsp-8+arg_18], rbx
0x1800640f9  push    rbp
0x1800640fa  mov     rbp, rsp
0x1800640fd  sub     rsp, 20h
0x180064101  xor     eax, eax
0x180064103  mov     rbx, 2B992DDFA232h
0x18006410d  mov     [rbp+arg_0], rax
0x180064111  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180064115  mov     qword ptr [rbp+PerformanceCount], rax
0x180064119  mov     rax, cs:__security_cookie
0x180064120  cmp     rax, rbx
0x180064123  jnz     loc_1800641BC
0x180064129  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006412d  call    cs:__imp_GetSystemTimeAsFileTime
0x180064133  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180064137  mov     [rbp+arg_0], rax
0x18006413b  call    cs:__imp_GetCurrentProcessId
0x180064141  mov     eax, eax
0x180064143  xor     [rbp+arg_0], rax
0x180064147  call    cs:__imp_GetCurrentThreadId
0x18006414d  mov     eax, eax
0x18006414f  xor     [rbp+arg_0], rax
0x180064153  call    cs:__imp_GetTickCount
0x180064159  mov     eax, eax
0x18006415b  shl     rax, 18h
0x18006415f  xor     [rbp+arg_0], rax
0x180064163  call    cs:__imp_GetTickCount
0x180064169  mov     eax, eax
0x18006416b  lea     rcx, [rbp+arg_0]
0x18006416f  xor     rax, [rbp+arg_0]
0x180064173  xor     rax, rcx
0x180064176  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18006417a  mov     [rbp+arg_0], rax
0x18006417e  call    cs:__imp_QueryPerformanceCounter
0x180064184  mov     eax, dword ptr [rbp+PerformanceCount]
0x180064187  mov     rcx, 0FFFFFFFFFFFFh
0x180064191  shl     rax, 20h
0x180064195  xor     rax, qword ptr [rbp+PerformanceCount]
0x180064199  xor     rax, [rbp+arg_0]
0x18006419d  and     rax, rcx
0x1800641a0  mov     rcx, rax
0x1800641a3  cmp     rax, rbx
0x1800641a6  jnz     short loc_1800641B5
0x1800641a8  mov     rax, 2B992DDFA233h
0x1800641b2  mov     rcx, rax
0x1800641b5  mov     cs:__security_cookie, rcx
0x1800641bc  mov     rbx, [rsp+20h+arg_18]
0x1800641c1  not     rax
0x1800641c4  mov     cs:__security_cookie_complement, rax
0x1800641cb  add     rsp, 20h
0x1800641cf  pop     rbp
0x1800641d0  retn
```
