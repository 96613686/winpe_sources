# __security_init_cookie

- ea: `0x18003f694`
- end: `0x18003f743`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e650`

## callees

- `0x18003f694`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18003f6dd`
- `KERNEL32!GetCurrentProcessId` at `0x18003f6dd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003f6c3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003f6c3`
- `KERNEL32!GetCurrentThreadId` at `0x18003f6d1`
- `KERNEL32!GetCurrentThreadId` at `0x18003f6d1`
- `KERNEL32!QueryPerformanceCounter` at `0x18003f6ed`
- `KERNEL32!QueryPerformanceCounter` at `0x18003f6ed`

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
0x18003f694  mov     [rsp-8+arg_10], rbx
0x18003f699  push    rbp
0x18003f69a  mov     rbp, rsp
0x18003f69d  sub     rsp, 30h
0x18003f6a1  mov     rax, cs:__security_cookie
0x18003f6a8  mov     rbx, 2B992DDFA232h
0x18003f6b2  cmp     rax, rbx
0x18003f6b5  jnz     short loc_18003F72E
0x18003f6b7  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003f6bb  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18003f6c3  call    cs:__imp_GetSystemTimeAsFileTime
0x18003f6c9  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003f6cd  mov     [rbp+var_10], rax
0x18003f6d1  call    cs:__imp_GetCurrentThreadId
0x18003f6d7  mov     eax, eax
0x18003f6d9  xor     [rbp+var_10], rax
0x18003f6dd  call    cs:__imp_GetCurrentProcessId
0x18003f6e3  mov     eax, eax
0x18003f6e5  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003f6e9  xor     [rbp+var_10], rax
0x18003f6ed  call    cs:__imp_QueryPerformanceCounter
0x18003f6f3  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003f6f6  lea     rcx, [rbp+var_10]
0x18003f6fa  shl     rax, 20h
0x18003f6fe  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003f702  xor     rax, [rbp+var_10]
0x18003f706  xor     rax, rcx
0x18003f709  mov     rcx, 0FFFFFFFFFFFFh
0x18003f713  and     rax, rcx
0x18003f716  mov     rcx, 2B992DDFA233h
0x18003f720  cmp     rax, rbx
0x18003f723  cmovz   rax, rcx
0x18003f727  mov     cs:__security_cookie, rax
0x18003f72e  mov     rbx, [rsp+30h+arg_10]
0x18003f733  not     rax
0x18003f736  mov     cs:__security_cookie_complement, rax
0x18003f73d  add     rsp, 30h
0x18003f741  pop     rbp
0x18003f742  retn
```
