# __security_init_cookie

- ea: `0x180001484`
- end: `0x180001539`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001410`
- `0x1800032a4`

## callees

- `0x180001484`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800014c7`
- `KERNEL32!GetCurrentThreadId` at `0x1800014c7`
- `KERNEL32!QueryPerformanceCounter` at `0x1800014e3`
- `KERNEL32!QueryPerformanceCounter` at `0x1800014e3`
- `KERNEL32!GetCurrentProcessId` at `0x1800014d3`
- `KERNEL32!GetCurrentProcessId` at `0x1800014d3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800014b9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800014b9`

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
0x180001484  mov     [rsp-8+arg_10], rbx
0x180001489  push    rbp
0x18000148a  mov     rbp, rsp
0x18000148d  sub     rsp, 30h
0x180001491  mov     rax, cs:__security_cookie
0x180001498  mov     rbx, 2B992DDFA232h
0x1800014a2  cmp     rax, rbx
0x1800014a5  jnz     short loc_180001524
0x1800014a7  xor     eax, eax
0x1800014a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800014ad  mov     [rbp+var_10], rax
0x1800014b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800014b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800014b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800014bf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800014c3  mov     [rbp+var_10], rax
0x1800014c7  call    cs:__imp_GetCurrentThreadId
0x1800014cd  mov     eax, eax
0x1800014cf  xor     [rbp+var_10], rax
0x1800014d3  call    cs:__imp_GetCurrentProcessId
0x1800014d9  mov     eax, eax
0x1800014db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800014df  xor     [rbp+var_10], rax
0x1800014e3  call    cs:__imp_QueryPerformanceCounter
0x1800014e9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800014ec  lea     rcx, [rbp+var_10]
0x1800014f0  shl     rax, 20h
0x1800014f4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800014f8  xor     rax, [rbp+var_10]
0x1800014fc  xor     rax, rcx
0x1800014ff  mov     rcx, 0FFFFFFFFFFFFh
0x180001509  and     rax, rcx
0x18000150c  mov     rcx, 2B992DDFA233h
0x180001516  cmp     rax, rbx
0x180001519  cmovz   rax, rcx
0x18000151d  mov     cs:__security_cookie, rax
0x180001524  mov     rbx, [rsp+30h+arg_10]
0x180001529  not     rax
0x18000152c  mov     cs:__security_cookie_complement, rax
0x180001533  add     rsp, 30h
0x180001537  pop     rbp
0x180001538  retn
```
