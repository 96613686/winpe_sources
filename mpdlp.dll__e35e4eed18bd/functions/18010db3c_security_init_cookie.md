# __security_init_cookie

- ea: `0x18010db3c`
- end: `0x18010dbeb`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18010caf0`

## callees

- `0x18010db3c`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18010db85`
- `KERNEL32!GetCurrentProcessId` at `0x18010db85`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18010db6b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18010db6b`
- `KERNEL32!GetCurrentThreadId` at `0x18010db79`
- `KERNEL32!GetCurrentThreadId` at `0x18010db79`
- `KERNEL32!QueryPerformanceCounter` at `0x18010db95`
- `KERNEL32!QueryPerformanceCounter` at `0x18010db95`

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
0x18010db3c  mov     [rsp-8+arg_10], rbx
0x18010db41  push    rbp
0x18010db42  mov     rbp, rsp
0x18010db45  sub     rsp, 30h
0x18010db49  mov     rax, cs:__security_cookie
0x18010db50  mov     rbx, 2B992DDFA232h
0x18010db5a  cmp     rax, rbx
0x18010db5d  jnz     short loc_18010DBD6
0x18010db5f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18010db63  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18010db6b  call    cs:__imp_GetSystemTimeAsFileTime
0x18010db71  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18010db75  mov     [rbp+var_10], rax
0x18010db79  call    cs:__imp_GetCurrentThreadId
0x18010db7f  mov     eax, eax
0x18010db81  xor     [rbp+var_10], rax
0x18010db85  call    cs:__imp_GetCurrentProcessId
0x18010db8b  mov     eax, eax
0x18010db8d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18010db91  xor     [rbp+var_10], rax
0x18010db95  call    cs:__imp_QueryPerformanceCounter
0x18010db9b  mov     eax, dword ptr [rbp+PerformanceCount]
0x18010db9e  lea     rcx, [rbp+var_10]
0x18010dba2  shl     rax, 20h
0x18010dba6  xor     rax, qword ptr [rbp+PerformanceCount]
0x18010dbaa  xor     rax, [rbp+var_10]
0x18010dbae  xor     rax, rcx
0x18010dbb1  mov     rcx, 0FFFFFFFFFFFFh
0x18010dbbb  and     rax, rcx
0x18010dbbe  mov     rcx, 2B992DDFA233h
0x18010dbc8  cmp     rax, rbx
0x18010dbcb  cmovz   rax, rcx
0x18010dbcf  mov     cs:__security_cookie, rax
0x18010dbd6  mov     rbx, [rsp+30h+arg_10]
0x18010dbdb  not     rax
0x18010dbde  mov     cs:__security_cookie_complement, rax
0x18010dbe5  add     rsp, 30h
0x18010dbe9  pop     rbp
0x18010dbea  retn
```
