# __security_init_cookie

- ea: `0x1800580e4`
- end: `0x1800581c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057970`

## callees

- `0x1800580e4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180058137`
- `KERNEL32!GetCurrentThreadId` at `0x180058137`
- `KERNEL32!GetCurrentProcessId` at `0x18005812b`
- `KERNEL32!GetCurrentProcessId` at `0x18005812b`
- `KERNEL32!GetTickCount` at `0x180058143`
- `KERNEL32!GetTickCount` at `0x180058153`
- `KERNEL32!GetTickCount` at `0x180058143`
- `KERNEL32!GetTickCount` at `0x180058153`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005811d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005811d`
- `KERNEL32!QueryPerformanceCounter` at `0x18005816e`
- `KERNEL32!QueryPerformanceCounter` at `0x18005816e`

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
0x1800580e4  mov     [rsp-8+arg_18], rbx
0x1800580e9  push    rbp
0x1800580ea  mov     rbp, rsp
0x1800580ed  sub     rsp, 20h
0x1800580f1  xor     eax, eax
0x1800580f3  mov     rbx, 2B992DDFA232h
0x1800580fd  mov     [rbp+arg_0], rax
0x180058101  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180058105  mov     qword ptr [rbp+PerformanceCount], rax
0x180058109  mov     rax, cs:__security_cookie
0x180058110  cmp     rax, rbx
0x180058113  jnz     loc_1800581AC
0x180058119  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005811d  call    cs:__imp_GetSystemTimeAsFileTime
0x180058123  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180058127  mov     [rbp+arg_0], rax
0x18005812b  call    cs:__imp_GetCurrentProcessId
0x180058131  mov     eax, eax
0x180058133  xor     [rbp+arg_0], rax
0x180058137  call    cs:__imp_GetCurrentThreadId
0x18005813d  mov     eax, eax
0x18005813f  xor     [rbp+arg_0], rax
0x180058143  call    cs:__imp_GetTickCount
0x180058149  mov     eax, eax
0x18005814b  shl     rax, 18h
0x18005814f  xor     [rbp+arg_0], rax
0x180058153  call    cs:__imp_GetTickCount
0x180058159  mov     eax, eax
0x18005815b  lea     rcx, [rbp+arg_0]
0x18005815f  xor     rax, [rbp+arg_0]
0x180058163  xor     rax, rcx
0x180058166  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005816a  mov     [rbp+arg_0], rax
0x18005816e  call    cs:__imp_QueryPerformanceCounter
0x180058174  mov     eax, dword ptr [rbp+PerformanceCount]
0x180058177  mov     rcx, 0FFFFFFFFFFFFh
0x180058181  shl     rax, 20h
0x180058185  xor     rax, qword ptr [rbp+PerformanceCount]
0x180058189  xor     rax, [rbp+arg_0]
0x18005818d  and     rax, rcx
0x180058190  mov     rcx, rax
0x180058193  cmp     rax, rbx
0x180058196  jnz     short loc_1800581A5
0x180058198  mov     rax, 2B992DDFA233h
0x1800581a2  mov     rcx, rax
0x1800581a5  mov     cs:__security_cookie, rcx
0x1800581ac  mov     rbx, [rsp+20h+arg_18]
0x1800581b1  not     rax
0x1800581b4  mov     cs:__security_cookie_complement, rax
0x1800581bb  add     rsp, 20h
0x1800581bf  pop     rbp
0x1800581c0  retn
```
