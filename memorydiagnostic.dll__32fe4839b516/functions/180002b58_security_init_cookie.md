# __security_init_cookie

- ea: `0x180002b58`
- end: `0x180002c09`
- name: `__security_init_cookie`
- size: `177`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002660`

## callees

- `0x180002b58`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180002ba3`
- `KERNEL32!GetCurrentProcessId` at `0x180002ba3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002b89`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002b89`
- `KERNEL32!GetCurrentThreadId` at `0x180002b97`
- `KERNEL32!GetCurrentThreadId` at `0x180002b97`
- `KERNEL32!QueryPerformanceCounter` at `0x180002bb3`
- `KERNEL32!QueryPerformanceCounter` at `0x180002bb3`

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
0x180002b58  mov     [rsp-8+arg_10], rbx
0x180002b5d  push    rbp
0x180002b5e  mov     rbp, rsp
0x180002b61  sub     rsp, 30h
0x180002b65  mov     rax, cs:__security_cookie
0x180002b6c  mov     rbx, 2B992DDFA232h
0x180002b76  cmp     rax, rbx
0x180002b79  jnz     short loc_180002BF4
0x180002b7b  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002b80  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002b84  and     qword ptr [rbp+PerformanceCount], 0
0x180002b89  call    cs:__imp_GetSystemTimeAsFileTime
0x180002b8f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002b93  mov     [rbp+var_10], rax
0x180002b97  call    cs:__imp_GetCurrentThreadId
0x180002b9d  mov     eax, eax
0x180002b9f  xor     [rbp+var_10], rax
0x180002ba3  call    cs:__imp_GetCurrentProcessId
0x180002ba9  mov     eax, eax
0x180002bab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002baf  xor     [rbp+var_10], rax
0x180002bb3  call    cs:__imp_QueryPerformanceCounter
0x180002bb9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002bbc  lea     rcx, [rbp+var_10]
0x180002bc0  shl     rax, 20h
0x180002bc4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002bc8  xor     rax, [rbp+var_10]
0x180002bcc  xor     rax, rcx
0x180002bcf  mov     rcx, 0FFFFFFFFFFFFh
0x180002bd9  and     rax, rcx
0x180002bdc  mov     rcx, 2B992DDFA233h
0x180002be6  cmp     rax, rbx
0x180002be9  cmovz   rax, rcx
0x180002bed  mov     cs:__security_cookie, rax
0x180002bf4  mov     rbx, [rsp+30h+arg_10]
0x180002bf9  not     rax
0x180002bfc  mov     cs:__security_cookie_complement, rax
0x180002c03  add     rsp, 30h
0x180002c07  pop     rbp
0x180002c08  retn
```
