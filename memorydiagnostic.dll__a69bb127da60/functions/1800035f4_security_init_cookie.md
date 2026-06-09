# __security_init_cookie

- ea: `0x1800035f4`
- end: `0x1800036a9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002e00`

## callees

- `0x1800035f4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180003653`
- `KERNEL32!QueryPerformanceCounter` at `0x180003653`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003629`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003629`
- `KERNEL32!GetCurrentProcessId` at `0x180003643`
- `KERNEL32!GetCurrentProcessId` at `0x180003643`
- `KERNEL32!GetCurrentThreadId` at `0x180003637`
- `KERNEL32!GetCurrentThreadId` at `0x180003637`

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
0x1800035f4  mov     [rsp-8+arg_10], rbx
0x1800035f9  push    rbp
0x1800035fa  mov     rbp, rsp
0x1800035fd  sub     rsp, 30h
0x180003601  mov     rax, cs:__security_cookie
0x180003608  mov     rbx, 2B992DDFA232h
0x180003612  cmp     rax, rbx
0x180003615  jnz     short loc_180003694
0x180003617  xor     eax, eax
0x180003619  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000361d  mov     [rbp+var_10], rax
0x180003621  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003625  mov     qword ptr [rbp+PerformanceCount], rax
0x180003629  call    cs:__imp_GetSystemTimeAsFileTime
0x18000362f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003633  mov     [rbp+var_10], rax
0x180003637  call    cs:__imp_GetCurrentThreadId
0x18000363d  mov     eax, eax
0x18000363f  xor     [rbp+var_10], rax
0x180003643  call    cs:__imp_GetCurrentProcessId
0x180003649  mov     eax, eax
0x18000364b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000364f  xor     [rbp+var_10], rax
0x180003653  call    cs:__imp_QueryPerformanceCounter
0x180003659  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000365c  lea     rcx, [rbp+var_10]
0x180003660  shl     rax, 20h
0x180003664  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003668  xor     rax, [rbp+var_10]
0x18000366c  xor     rax, rcx
0x18000366f  mov     rcx, 0FFFFFFFFFFFFh
0x180003679  and     rax, rcx
0x18000367c  mov     rcx, 2B992DDFA233h
0x180003686  cmp     rax, rbx
0x180003689  cmovz   rax, rcx
0x18000368d  mov     cs:__security_cookie, rax
0x180003694  mov     rbx, [rsp+30h+arg_10]
0x180003699  not     rax
0x18000369c  mov     cs:__security_cookie_complement, rax
0x1800036a3  add     rsp, 30h
0x1800036a7  pop     rbp
0x1800036a8  retn
```
