# __security_init_cookie

- ea: `0x140004614`
- end: `0x1400046f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003ca0`

## callees

- `0x140004614`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140004673`
- `KERNEL32!GetTickCount` at `0x140004683`
- `KERNEL32!GetTickCount` at `0x140004673`
- `KERNEL32!GetTickCount` at `0x140004683`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000464d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000464d`
- `KERNEL32!QueryPerformanceCounter` at `0x14000469e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000469e`
- `KERNEL32!GetCurrentProcessId` at `0x14000465b`
- `KERNEL32!GetCurrentProcessId` at `0x14000465b`
- `KERNEL32!GetCurrentThreadId` at `0x140004667`
- `KERNEL32!GetCurrentThreadId` at `0x140004667`

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
0x140004614  mov     [rsp-8+arg_18], rbx
0x140004619  push    rbp
0x14000461a  mov     rbp, rsp
0x14000461d  sub     rsp, 20h
0x140004621  xor     eax, eax
0x140004623  mov     rbx, 2B992DDFA232h
0x14000462d  mov     [rbp+arg_0], rax
0x140004631  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140004635  mov     qword ptr [rbp+PerformanceCount], rax
0x140004639  mov     rax, cs:__security_cookie
0x140004640  cmp     rax, rbx
0x140004643  jnz     loc_1400046DC
0x140004649  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000464d  call    cs:__imp_GetSystemTimeAsFileTime
0x140004653  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140004657  mov     [rbp+arg_0], rax
0x14000465b  call    cs:__imp_GetCurrentProcessId
0x140004661  mov     eax, eax
0x140004663  xor     [rbp+arg_0], rax
0x140004667  call    cs:__imp_GetCurrentThreadId
0x14000466d  mov     eax, eax
0x14000466f  xor     [rbp+arg_0], rax
0x140004673  call    cs:__imp_GetTickCount
0x140004679  mov     eax, eax
0x14000467b  shl     rax, 18h
0x14000467f  xor     [rbp+arg_0], rax
0x140004683  call    cs:__imp_GetTickCount
0x140004689  mov     eax, eax
0x14000468b  lea     rcx, [rbp+arg_0]
0x14000468f  xor     rax, [rbp+arg_0]
0x140004693  xor     rax, rcx
0x140004696  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000469a  mov     [rbp+arg_0], rax
0x14000469e  call    cs:__imp_QueryPerformanceCounter
0x1400046a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400046a7  mov     rcx, 0FFFFFFFFFFFFh
0x1400046b1  shl     rax, 20h
0x1400046b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400046b9  xor     rax, [rbp+arg_0]
0x1400046bd  and     rax, rcx
0x1400046c0  mov     rcx, rax
0x1400046c3  cmp     rax, rbx
0x1400046c6  jnz     short loc_1400046D5
0x1400046c8  mov     rax, 2B992DDFA233h
0x1400046d2  mov     rcx, rax
0x1400046d5  mov     cs:__security_cookie, rcx
0x1400046dc  mov     rbx, [rsp+20h+arg_18]
0x1400046e1  not     rax
0x1400046e4  mov     cs:__security_cookie_complement, rax
0x1400046eb  add     rsp, 20h
0x1400046ef  pop     rbp
0x1400046f0  retn
```
