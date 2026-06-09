# __security_init_cookie

- ea: `0x14002cac4`
- end: `0x14002cb70`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002cab0`

## callees

- `0x14002cac4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002caf0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002caf0`
- `KERNEL32!GetCurrentProcessId` at `0x14002cb0a`
- `KERNEL32!GetCurrentProcessId` at `0x14002cb0a`
- `KERNEL32!QueryPerformanceCounter` at `0x14002cb1a`
- `KERNEL32!QueryPerformanceCounter` at `0x14002cb1a`
- `KERNEL32!GetCurrentThreadId` at `0x14002cafe`
- `KERNEL32!GetCurrentThreadId` at `0x14002cafe`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

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
0x14002cac4  mov     [rsp-8+arg_10], rbx
0x14002cac9  push    rbp
0x14002caca  mov     rbp, rsp
0x14002cacd  sub     rsp, 30h
0x14002cad1  mov     rax, cs:__security_cookie
0x14002cad8  mov     rbx, 2B992DDFA232h
0x14002cae2  cmp     rax, rbx
0x14002cae5  jnz     short loc_14002CB5B
0x14002cae7  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14002caec  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002caf0  call    cs:__imp_GetSystemTimeAsFileTime
0x14002caf6  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14002cafa  mov     [rbp+var_10], rax
0x14002cafe  call    cs:__imp_GetCurrentThreadId
0x14002cb04  mov     eax, eax
0x14002cb06  xor     [rbp+var_10], rax
0x14002cb0a  call    cs:__imp_GetCurrentProcessId
0x14002cb10  mov     eax, eax
0x14002cb12  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14002cb16  xor     [rbp+var_10], rax
0x14002cb1a  call    cs:__imp_QueryPerformanceCounter
0x14002cb20  mov     eax, dword ptr [rbp+PerformanceCount]
0x14002cb23  lea     rcx, [rbp+var_10]
0x14002cb27  shl     rax, 20h
0x14002cb2b  xor     rax, qword ptr [rbp+PerformanceCount]
0x14002cb2f  xor     rax, [rbp+var_10]
0x14002cb33  xor     rax, rcx
0x14002cb36  mov     rcx, 0FFFFFFFFFFFFh
0x14002cb40  and     rax, rcx
0x14002cb43  mov     rcx, 2B992DDFA233h
0x14002cb4d  cmp     rax, rbx
0x14002cb50  cmovz   rax, rcx
0x14002cb54  mov     cs:__security_cookie, rax
0x14002cb5b  mov     rbx, [rsp+30h+arg_10]
0x14002cb60  not     rax
0x14002cb63  mov     cs:__security_cookie_complement, rax
0x14002cb6a  add     rsp, 30h
0x14002cb6e  pop     rbp
0x14002cb6f  retn
```
