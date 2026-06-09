# __security_init_cookie

- ea: `0x18002a4e4`
- end: `0x18002a5c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029c90`

## callees

- `0x18002a4e4`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18002a52b`
- `KERNEL32!GetCurrentProcessId` at `0x18002a52b`
- `KERNEL32!GetTickCount` at `0x18002a543`
- `KERNEL32!GetTickCount` at `0x18002a553`
- `KERNEL32!GetTickCount` at `0x18002a543`
- `KERNEL32!GetTickCount` at `0x18002a553`
- `KERNEL32!GetCurrentThreadId` at `0x18002a537`
- `KERNEL32!GetCurrentThreadId` at `0x18002a537`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002a51d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002a51d`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a56e`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a56e`

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
0x18002a4e4  mov     [rsp-8+arg_18], rbx
0x18002a4e9  push    rbp
0x18002a4ea  mov     rbp, rsp
0x18002a4ed  sub     rsp, 20h
0x18002a4f1  xor     eax, eax
0x18002a4f3  mov     rbx, 2B992DDFA232h
0x18002a4fd  mov     [rbp+arg_0], rax
0x18002a501  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002a505  mov     qword ptr [rbp+PerformanceCount], rax
0x18002a509  mov     rax, cs:__security_cookie
0x18002a510  cmp     rax, rbx
0x18002a513  jnz     loc_18002A5AC
0x18002a519  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002a51d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a523  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002a527  mov     [rbp+arg_0], rax
0x18002a52b  call    cs:__imp_GetCurrentProcessId
0x18002a531  mov     eax, eax
0x18002a533  xor     [rbp+arg_0], rax
0x18002a537  call    cs:__imp_GetCurrentThreadId
0x18002a53d  mov     eax, eax
0x18002a53f  xor     [rbp+arg_0], rax
0x18002a543  call    cs:__imp_GetTickCount
0x18002a549  mov     eax, eax
0x18002a54b  shl     rax, 18h
0x18002a54f  xor     [rbp+arg_0], rax
0x18002a553  call    cs:__imp_GetTickCount
0x18002a559  mov     eax, eax
0x18002a55b  lea     rcx, [rbp+arg_0]
0x18002a55f  xor     rax, [rbp+arg_0]
0x18002a563  xor     rax, rcx
0x18002a566  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002a56a  mov     [rbp+arg_0], rax
0x18002a56e  call    cs:__imp_QueryPerformanceCounter
0x18002a574  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002a577  mov     rcx, 0FFFFFFFFFFFFh
0x18002a581  shl     rax, 20h
0x18002a585  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002a589  xor     rax, [rbp+arg_0]
0x18002a58d  and     rax, rcx
0x18002a590  mov     rcx, rax
0x18002a593  cmp     rax, rbx
0x18002a596  jnz     short loc_18002A5A5
0x18002a598  mov     rax, 2B992DDFA233h
0x18002a5a2  mov     rcx, rax
0x18002a5a5  mov     cs:__security_cookie, rcx
0x18002a5ac  mov     rbx, [rsp+20h+arg_18]
0x18002a5b1  not     rax
0x18002a5b4  mov     cs:__security_cookie_complement, rax
0x18002a5bb  add     rsp, 20h
0x18002a5bf  pop     rbp
0x18002a5c0  retn
```
