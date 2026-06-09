# __security_init_cookie

- ea: `0x180004ea0`
- end: `0x180004f55`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800045f0`

## callees

- `0x180004ea0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180004eef`
- `KERNEL32!GetCurrentProcessId` at `0x180004eef`
- `KERNEL32!GetCurrentThreadId` at `0x180004ee3`
- `KERNEL32!GetCurrentThreadId` at `0x180004ee3`
- `KERNEL32!QueryPerformanceCounter` at `0x180004eff`
- `KERNEL32!QueryPerformanceCounter` at `0x180004eff`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004ed5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004ed5`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180004ea0  mov     [rsp-8+arg_10], rbx
0x180004ea5  push    rbp
0x180004ea6  mov     rbp, rsp
0x180004ea9  sub     rsp, 30h
0x180004ead  mov     rax, cs:__security_cookie
0x180004eb4  mov     rbx, 2B992DDFA232h
0x180004ebe  cmp     rax, rbx
0x180004ec1  jnz     short loc_180004F40
0x180004ec3  xor     eax, eax
0x180004ec5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004ec9  mov     [rbp+var_10], rax
0x180004ecd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004ed1  mov     qword ptr [rbp+PerformanceCount], rax
0x180004ed5  call    cs:__imp_GetSystemTimeAsFileTime
0x180004edb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004edf  mov     [rbp+var_10], rax
0x180004ee3  call    cs:__imp_GetCurrentThreadId
0x180004ee9  mov     eax, eax
0x180004eeb  xor     [rbp+var_10], rax
0x180004eef  call    cs:__imp_GetCurrentProcessId
0x180004ef5  mov     eax, eax
0x180004ef7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004efb  xor     [rbp+var_10], rax
0x180004eff  call    cs:__imp_QueryPerformanceCounter
0x180004f05  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004f08  lea     rcx, [rbp+var_10]
0x180004f0c  shl     rax, 20h
0x180004f10  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004f14  xor     rax, [rbp+var_10]
0x180004f18  xor     rax, rcx
0x180004f1b  mov     rcx, 0FFFFFFFFFFFFh
0x180004f25  and     rax, rcx
0x180004f28  mov     rcx, 2B992DDFA233h
0x180004f32  cmp     rax, rbx
0x180004f35  cmovz   rax, rcx
0x180004f39  mov     cs:__security_cookie, rax
0x180004f40  mov     rbx, [rsp+30h+arg_10]
0x180004f45  not     rax
0x180004f48  mov     cs:__security_cookie_complement, rax
0x180004f4f  add     rsp, 30h
0x180004f53  pop     rbp
0x180004f54  retn
```
