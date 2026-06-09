# __security_init_cookie

- ea: `0x1800027e4`
- end: `0x1800028c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001dc0`

## callees

- `0x1800027e4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000281d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000281d`
- `KERNEL32!QueryPerformanceCounter` at `0x18000286e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000286e`
- `KERNEL32!GetCurrentThreadId` at `0x180002837`
- `KERNEL32!GetCurrentThreadId` at `0x180002837`
- `KERNEL32!GetCurrentProcessId` at `0x18000282b`
- `KERNEL32!GetCurrentProcessId` at `0x18000282b`
- `KERNEL32!GetTickCount` at `0x180002843`
- `KERNEL32!GetTickCount` at `0x180002853`
- `KERNEL32!GetTickCount` at `0x180002843`
- `KERNEL32!GetTickCount` at `0x180002853`

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
0x1800027e4  mov     [rsp-8+arg_18], rbx
0x1800027e9  push    rbp
0x1800027ea  mov     rbp, rsp
0x1800027ed  sub     rsp, 20h
0x1800027f1  xor     eax, eax
0x1800027f3  mov     rbx, 2B992DDFA232h
0x1800027fd  mov     [rbp+arg_0], rax
0x180002801  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002805  mov     qword ptr [rbp+PerformanceCount], rax
0x180002809  mov     rax, cs:__security_cookie
0x180002810  cmp     rax, rbx
0x180002813  jnz     loc_1800028AC
0x180002819  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000281d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002823  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002827  mov     [rbp+arg_0], rax
0x18000282b  call    cs:__imp_GetCurrentProcessId
0x180002831  mov     eax, eax
0x180002833  xor     [rbp+arg_0], rax
0x180002837  call    cs:__imp_GetCurrentThreadId
0x18000283d  mov     eax, eax
0x18000283f  xor     [rbp+arg_0], rax
0x180002843  call    cs:__imp_GetTickCount
0x180002849  mov     eax, eax
0x18000284b  shl     rax, 18h
0x18000284f  xor     [rbp+arg_0], rax
0x180002853  call    cs:__imp_GetTickCount
0x180002859  mov     eax, eax
0x18000285b  lea     rcx, [rbp+arg_0]
0x18000285f  xor     rax, [rbp+arg_0]
0x180002863  xor     rax, rcx
0x180002866  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000286a  mov     [rbp+arg_0], rax
0x18000286e  call    cs:__imp_QueryPerformanceCounter
0x180002874  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002877  mov     rcx, 0FFFFFFFFFFFFh
0x180002881  shl     rax, 20h
0x180002885  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002889  xor     rax, [rbp+arg_0]
0x18000288d  and     rax, rcx
0x180002890  mov     rcx, rax
0x180002893  cmp     rax, rbx
0x180002896  jnz     short loc_1800028A5
0x180002898  mov     rax, 2B992DDFA233h
0x1800028a2  mov     rcx, rax
0x1800028a5  mov     cs:__security_cookie, rcx
0x1800028ac  mov     rbx, [rsp+20h+arg_18]
0x1800028b1  not     rax
0x1800028b4  mov     cs:__security_cookie_complement, rax
0x1800028bb  add     rsp, 20h
0x1800028bf  pop     rbp
0x1800028c0  retn
```
