# __security_init_cookie

- ea: `0x1800038e4`
- end: `0x1800039c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003270`

## callees

- `0x1800038e4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000396e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000396e`
- `KERNEL32!GetCurrentProcessId` at `0x18000392b`
- `KERNEL32!GetCurrentProcessId` at `0x18000392b`
- `KERNEL32!GetCurrentThreadId` at `0x180003937`
- `KERNEL32!GetCurrentThreadId` at `0x180003937`
- `KERNEL32!GetTickCount` at `0x180003943`
- `KERNEL32!GetTickCount` at `0x180003953`
- `KERNEL32!GetTickCount` at `0x180003943`
- `KERNEL32!GetTickCount` at `0x180003953`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000391d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000391d`

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
0x1800038e4  mov     [rsp-8+arg_18], rbx
0x1800038e9  push    rbp
0x1800038ea  mov     rbp, rsp
0x1800038ed  sub     rsp, 20h
0x1800038f1  xor     eax, eax
0x1800038f3  mov     rbx, 2B992DDFA232h
0x1800038fd  mov     [rbp+arg_0], rax
0x180003901  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003905  mov     qword ptr [rbp+PerformanceCount], rax
0x180003909  mov     rax, cs:__security_cookie
0x180003910  cmp     rax, rbx
0x180003913  jnz     loc_1800039AC
0x180003919  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000391d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003923  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003927  mov     [rbp+arg_0], rax
0x18000392b  call    cs:__imp_GetCurrentProcessId
0x180003931  mov     eax, eax
0x180003933  xor     [rbp+arg_0], rax
0x180003937  call    cs:__imp_GetCurrentThreadId
0x18000393d  mov     eax, eax
0x18000393f  xor     [rbp+arg_0], rax
0x180003943  call    cs:__imp_GetTickCount
0x180003949  mov     eax, eax
0x18000394b  shl     rax, 18h
0x18000394f  xor     [rbp+arg_0], rax
0x180003953  call    cs:__imp_GetTickCount
0x180003959  mov     eax, eax
0x18000395b  lea     rcx, [rbp+arg_0]
0x18000395f  xor     rax, [rbp+arg_0]
0x180003963  xor     rax, rcx
0x180003966  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000396a  mov     [rbp+arg_0], rax
0x18000396e  call    cs:__imp_QueryPerformanceCounter
0x180003974  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003977  mov     rcx, 0FFFFFFFFFFFFh
0x180003981  shl     rax, 20h
0x180003985  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003989  xor     rax, [rbp+arg_0]
0x18000398d  and     rax, rcx
0x180003990  mov     rcx, rax
0x180003993  cmp     rax, rbx
0x180003996  jnz     short loc_1800039A5
0x180003998  mov     rax, 2B992DDFA233h
0x1800039a2  mov     rcx, rax
0x1800039a5  mov     cs:__security_cookie, rcx
0x1800039ac  mov     rbx, [rsp+20h+arg_18]
0x1800039b1  not     rax
0x1800039b4  mov     cs:__security_cookie_complement, rax
0x1800039bb  add     rsp, 20h
0x1800039bf  pop     rbp
0x1800039c0  retn
```
