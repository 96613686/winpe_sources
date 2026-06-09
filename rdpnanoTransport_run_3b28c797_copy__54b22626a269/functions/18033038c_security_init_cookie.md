# __security_init_cookie

- ea: `0x18033038c`
- end: `0x18033043b`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18032fa30`

## callees

- `0x18033038c`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1803303d5`
- `KERNEL32!GetCurrentProcessId` at `0x1803303d5`
- `KERNEL32!GetCurrentThreadId` at `0x1803303c9`
- `KERNEL32!GetCurrentThreadId` at `0x1803303c9`
- `KERNEL32!QueryPerformanceCounter` at `0x1803303e5`
- `KERNEL32!QueryPerformanceCounter` at `0x1803303e5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1803303bb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1803303bb`

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
0x18033038c  mov     [rsp-8+arg_10], rbx
0x180330391  push    rbp
0x180330392  mov     rbp, rsp
0x180330395  sub     rsp, 30h
0x180330399  mov     rax, cs:__security_cookie
0x1803303a0  mov     rbx, 2B992DDFA232h
0x1803303aa  cmp     rax, rbx
0x1803303ad  jnz     short loc_180330426
0x1803303af  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1803303b3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1803303bb  call    cs:__imp_GetSystemTimeAsFileTime
0x1803303c1  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1803303c5  mov     [rbp+var_10], rax
0x1803303c9  call    cs:__imp_GetCurrentThreadId
0x1803303cf  mov     eax, eax
0x1803303d1  xor     [rbp+var_10], rax
0x1803303d5  call    cs:__imp_GetCurrentProcessId
0x1803303db  mov     eax, eax
0x1803303dd  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1803303e1  xor     [rbp+var_10], rax
0x1803303e5  call    cs:__imp_QueryPerformanceCounter
0x1803303eb  mov     eax, dword ptr [rbp+PerformanceCount]
0x1803303ee  lea     rcx, [rbp+var_10]
0x1803303f2  shl     rax, 20h
0x1803303f6  xor     rax, qword ptr [rbp+PerformanceCount]
0x1803303fa  xor     rax, [rbp+var_10]
0x1803303fe  xor     rax, rcx
0x180330401  mov     rcx, 0FFFFFFFFFFFFh
0x18033040b  and     rax, rcx
0x18033040e  mov     rcx, 2B992DDFA233h
0x180330418  cmp     rax, rbx
0x18033041b  cmovz   rax, rcx
0x18033041f  mov     cs:__security_cookie, rax
0x180330426  mov     rbx, [rsp+30h+arg_10]
0x18033042b  not     rax
0x18033042e  mov     cs:__security_cookie_complement, rax
0x180330435  add     rsp, 30h
0x180330439  pop     rbp
0x18033043a  retn
```
