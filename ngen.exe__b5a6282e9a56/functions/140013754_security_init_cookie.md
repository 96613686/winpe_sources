# __security_init_cookie

- ea: `0x140013754`
- end: `0x140013800`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400131d0`

## callees

- `0x140013754`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1400137aa`
- `KERNEL32!QueryPerformanceCounter` at `0x1400137aa`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140013780`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140013780`
- `KERNEL32!GetCurrentThreadId` at `0x14001378e`
- `KERNEL32!GetCurrentThreadId` at `0x14001378e`
- `KERNEL32!GetCurrentProcessId` at `0x14001379a`
- `KERNEL32!GetCurrentProcessId` at `0x14001379a`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x140013754  mov     [rsp-8+arg_18], rbx
0x140013759  push    rbp
0x14001375a  mov     rbp, rsp
0x14001375d  sub     rsp, 20h
0x140013761  mov     rax, cs:__security_cookie
0x140013768  mov     rbx, 2B992DDFA232h
0x140013772  cmp     rax, rbx
0x140013775  jnz     short loc_1400137EB
0x140013777  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14001377c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140013780  call    cs:__imp_GetSystemTimeAsFileTime
0x140013786  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14001378a  mov     [rbp+arg_0], rax
0x14001378e  call    cs:__imp_GetCurrentThreadId
0x140013794  mov     eax, eax
0x140013796  xor     [rbp+arg_0], rax
0x14001379a  call    cs:__imp_GetCurrentProcessId
0x1400137a0  mov     eax, eax
0x1400137a2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400137a6  xor     [rbp+arg_0], rax
0x1400137aa  call    cs:__imp_QueryPerformanceCounter
0x1400137b0  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400137b3  lea     rcx, [rbp+arg_0]
0x1400137b7  shl     rax, 20h
0x1400137bb  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400137bf  xor     rax, [rbp+arg_0]
0x1400137c3  xor     rax, rcx
0x1400137c6  mov     rcx, 0FFFFFFFFFFFFh
0x1400137d0  and     rax, rcx
0x1400137d3  mov     rcx, 2B992DDFA233h
0x1400137dd  cmp     rax, rbx
0x1400137e0  cmovz   rax, rcx
0x1400137e4  mov     cs:__security_cookie, rax
0x1400137eb  mov     rbx, [rsp+20h+arg_18]
0x1400137f0  not     rax
0x1400137f3  mov     cs:__security_cookie_complement, rax
0x1400137fa  add     rsp, 20h
0x1400137fe  pop     rbp
0x1400137ff  retn
```
