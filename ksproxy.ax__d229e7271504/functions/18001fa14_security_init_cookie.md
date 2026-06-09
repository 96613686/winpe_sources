# __security_init_cookie

- ea: `0x18001fa14`
- end: `0x18001fac9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f5d0`

## callees

- `0x18001fa14`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001fa57`
- `KERNEL32!GetCurrentThreadId` at `0x18001fa57`
- `KERNEL32!GetCurrentProcessId` at `0x18001fa63`
- `KERNEL32!GetCurrentProcessId` at `0x18001fa63`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001fa49`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001fa49`
- `KERNEL32!QueryPerformanceCounter` at `0x18001fa73`
- `KERNEL32!QueryPerformanceCounter` at `0x18001fa73`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
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
0x18001fa14  mov     [rsp-8+arg_10], rbx
0x18001fa19  push    rbp
0x18001fa1a  mov     rbp, rsp
0x18001fa1d  sub     rsp, 30h
0x18001fa21  mov     rax, cs:__security_cookie
0x18001fa28  mov     rbx, 2B992DDFA232h
0x18001fa32  cmp     rax, rbx
0x18001fa35  jnz     short loc_18001FAB4
0x18001fa37  xor     eax, eax
0x18001fa39  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001fa3d  mov     [rbp+var_10], rax
0x18001fa41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001fa45  mov     qword ptr [rbp+PerformanceCount], rax
0x18001fa49  call    cs:__imp_GetSystemTimeAsFileTime
0x18001fa4f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001fa53  mov     [rbp+var_10], rax
0x18001fa57  call    cs:__imp_GetCurrentThreadId
0x18001fa5d  mov     eax, eax
0x18001fa5f  xor     [rbp+var_10], rax
0x18001fa63  call    cs:__imp_GetCurrentProcessId
0x18001fa69  mov     eax, eax
0x18001fa6b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001fa6f  xor     [rbp+var_10], rax
0x18001fa73  call    cs:__imp_QueryPerformanceCounter
0x18001fa79  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001fa7c  lea     rcx, [rbp+var_10]
0x18001fa80  shl     rax, 20h
0x18001fa84  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001fa88  xor     rax, [rbp+var_10]
0x18001fa8c  xor     rax, rcx
0x18001fa8f  mov     rcx, 0FFFFFFFFFFFFh
0x18001fa99  and     rax, rcx
0x18001fa9c  mov     rcx, 2B992DDFA233h
0x18001faa6  cmp     rax, rbx
0x18001faa9  cmovz   rax, rcx
0x18001faad  mov     cs:__security_cookie, rax
0x18001fab4  mov     rbx, [rsp+30h+arg_10]
0x18001fab9  not     rax
0x18001fabc  mov     cs:__security_cookie_complement, rax
0x18001fac3  add     rsp, 30h
0x18001fac7  pop     rbp
0x18001fac8  retn
```
