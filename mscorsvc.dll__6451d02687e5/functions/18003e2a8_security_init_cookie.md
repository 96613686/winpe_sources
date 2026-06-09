# __security_init_cookie

- ea: `0x18003e2a8`
- end: `0x18003e354`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003dbe0`

## callees

- `0x18003e2a8`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18003e2ee`
- `KERNEL32!GetCurrentProcessId` at `0x18003e2ee`
- `KERNEL32!GetCurrentThreadId` at `0x18003e2e2`
- `KERNEL32!GetCurrentThreadId` at `0x18003e2e2`
- `KERNEL32!QueryPerformanceCounter` at `0x18003e2fe`
- `KERNEL32!QueryPerformanceCounter` at `0x18003e2fe`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003e2d4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003e2d4`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x18003e2a8  mov     [rsp-8+arg_18], rbx
0x18003e2ad  push    rbp
0x18003e2ae  mov     rbp, rsp
0x18003e2b1  sub     rsp, 20h
0x18003e2b5  mov     rax, cs:__security_cookie
0x18003e2bc  mov     rbx, 2B992DDFA232h
0x18003e2c6  cmp     rax, rbx
0x18003e2c9  jnz     short loc_18003E33F
0x18003e2cb  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003e2d0  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003e2d4  call    cs:__imp_GetSystemTimeAsFileTime
0x18003e2da  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003e2de  mov     [rbp+arg_0], rax
0x18003e2e2  call    cs:__imp_GetCurrentThreadId
0x18003e2e8  mov     eax, eax
0x18003e2ea  xor     [rbp+arg_0], rax
0x18003e2ee  call    cs:__imp_GetCurrentProcessId
0x18003e2f4  mov     eax, eax
0x18003e2f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003e2fa  xor     [rbp+arg_0], rax
0x18003e2fe  call    cs:__imp_QueryPerformanceCounter
0x18003e304  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003e307  lea     rcx, [rbp+arg_0]
0x18003e30b  shl     rax, 20h
0x18003e30f  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003e313  xor     rax, [rbp+arg_0]
0x18003e317  xor     rax, rcx
0x18003e31a  mov     rcx, 0FFFFFFFFFFFFh
0x18003e324  and     rax, rcx
0x18003e327  mov     rcx, 2B992DDFA233h
0x18003e331  cmp     rax, rbx
0x18003e334  cmovz   rax, rcx
0x18003e338  mov     cs:__security_cookie, rax
0x18003e33f  mov     rbx, [rsp+20h+arg_18]
0x18003e344  not     rax
0x18003e347  mov     cs:__security_cookie_complement, rax
0x18003e34e  add     rsp, 20h
0x18003e352  pop     rbp
0x18003e353  retn
```
