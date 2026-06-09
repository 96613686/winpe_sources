# __security_init_cookie

- ea: `0x1800093e4`
- end: `0x1800094c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008c90`

## callees

- `0x1800093e4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180009443`
- `KERNEL32!GetTickCount` at `0x180009453`
- `KERNEL32!GetTickCount` at `0x180009443`
- `KERNEL32!GetTickCount` at `0x180009453`
- `KERNEL32!GetCurrentProcessId` at `0x18000942b`
- `KERNEL32!GetCurrentProcessId` at `0x18000942b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000946e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000946e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000941d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000941d`
- `KERNEL32!GetCurrentThreadId` at `0x180009437`
- `KERNEL32!GetCurrentThreadId` at `0x180009437`

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
0x1800093e4  mov     [rsp-8+arg_18], rbx
0x1800093e9  push    rbp
0x1800093ea  mov     rbp, rsp
0x1800093ed  sub     rsp, 20h
0x1800093f1  xor     eax, eax
0x1800093f3  mov     rbx, 2B992DDFA232h
0x1800093fd  mov     [rbp+arg_0], rax
0x180009401  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180009405  mov     qword ptr [rbp+PerformanceCount], rax
0x180009409  mov     rax, cs:__security_cookie
0x180009410  cmp     rax, rbx
0x180009413  jnz     loc_1800094AC
0x180009419  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000941d  call    cs:__imp_GetSystemTimeAsFileTime
0x180009423  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009427  mov     [rbp+arg_0], rax
0x18000942b  call    cs:__imp_GetCurrentProcessId
0x180009431  mov     eax, eax
0x180009433  xor     [rbp+arg_0], rax
0x180009437  call    cs:__imp_GetCurrentThreadId
0x18000943d  mov     eax, eax
0x18000943f  xor     [rbp+arg_0], rax
0x180009443  call    cs:__imp_GetTickCount
0x180009449  mov     eax, eax
0x18000944b  shl     rax, 18h
0x18000944f  xor     [rbp+arg_0], rax
0x180009453  call    cs:__imp_GetTickCount
0x180009459  mov     eax, eax
0x18000945b  lea     rcx, [rbp+arg_0]
0x18000945f  xor     rax, [rbp+arg_0]
0x180009463  xor     rax, rcx
0x180009466  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000946a  mov     [rbp+arg_0], rax
0x18000946e  call    cs:__imp_QueryPerformanceCounter
0x180009474  mov     eax, dword ptr [rbp+PerformanceCount]
0x180009477  mov     rcx, 0FFFFFFFFFFFFh
0x180009481  shl     rax, 20h
0x180009485  xor     rax, qword ptr [rbp+PerformanceCount]
0x180009489  xor     rax, [rbp+arg_0]
0x18000948d  and     rax, rcx
0x180009490  mov     rcx, rax
0x180009493  cmp     rax, rbx
0x180009496  jnz     short loc_1800094A5
0x180009498  mov     rax, 2B992DDFA233h
0x1800094a2  mov     rcx, rax
0x1800094a5  mov     cs:__security_cookie, rcx
0x1800094ac  mov     rbx, [rsp+20h+arg_18]
0x1800094b1  not     rax
0x1800094b4  mov     cs:__security_cookie_complement, rax
0x1800094bb  add     rsp, 20h
0x1800094bf  pop     rbp
0x1800094c0  retn
```
