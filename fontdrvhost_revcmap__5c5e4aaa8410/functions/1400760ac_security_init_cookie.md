# __security_init_cookie

- ea: `0x1400760ac`
- end: `0x140076161`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140075db0`

## callees

- `0x1400760ac`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400760e1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400760e1`
- `KERNEL32!QueryPerformanceCounter` at `0x14007610b`
- `KERNEL32!QueryPerformanceCounter` at `0x14007610b`
- `KERNEL32!GetCurrentProcessId` at `0x1400760fb`
- `KERNEL32!GetCurrentProcessId` at `0x1400760fb`
- `KERNEL32!GetCurrentThreadId` at `0x1400760ef`
- `KERNEL32!GetCurrentThreadId` at `0x1400760ef`

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
0x1400760ac  mov     [rsp-8+arg_10], rbx
0x1400760b1  push    rbp
0x1400760b2  mov     rbp, rsp
0x1400760b5  sub     rsp, 30h
0x1400760b9  mov     rax, cs:__security_cookie
0x1400760c0  mov     rbx, 2B992DDFA232h
0x1400760ca  cmp     rax, rbx
0x1400760cd  jnz     short loc_14007614C
0x1400760cf  xor     eax, eax
0x1400760d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400760d5  mov     [rbp+var_10], rax
0x1400760d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400760dd  mov     qword ptr [rbp+PerformanceCount], rax
0x1400760e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400760e7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400760eb  mov     [rbp+var_10], rax
0x1400760ef  call    cs:__imp_GetCurrentThreadId
0x1400760f5  mov     eax, eax
0x1400760f7  xor     [rbp+var_10], rax
0x1400760fb  call    cs:__imp_GetCurrentProcessId
0x140076101  mov     eax, eax
0x140076103  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140076107  xor     [rbp+var_10], rax
0x14007610b  call    cs:__imp_QueryPerformanceCounter
0x140076111  mov     eax, dword ptr [rbp+PerformanceCount]
0x140076114  lea     rcx, [rbp+var_10]
0x140076118  shl     rax, 20h
0x14007611c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140076120  xor     rax, [rbp+var_10]
0x140076124  xor     rax, rcx
0x140076127  mov     rcx, 0FFFFFFFFFFFFh
0x140076131  and     rax, rcx
0x140076134  mov     rcx, 2B992DDFA233h
0x14007613e  cmp     rax, rbx
0x140076141  cmovz   rax, rcx
0x140076145  mov     cs:__security_cookie, rax
0x14007614c  mov     rbx, [rsp+30h+arg_10]
0x140076151  not     rax
0x140076154  mov     cs:__security_cookie_complement, rax
0x14007615b  add     rsp, 30h
0x14007615f  pop     rbp
0x140076160  retn
```
