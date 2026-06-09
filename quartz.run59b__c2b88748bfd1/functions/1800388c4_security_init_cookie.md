# __security_init_cookie

- ea: `0x1800388c4`
- end: `0x180038979`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038850`

## callees

- `0x1800388c4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800388f9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800388f9`
- `KERNEL32!GetCurrentThreadId` at `0x180038907`
- `KERNEL32!GetCurrentThreadId` at `0x180038907`
- `KERNEL32!GetCurrentProcessId` at `0x180038913`
- `KERNEL32!GetCurrentProcessId` at `0x180038913`
- `KERNEL32!QueryPerformanceCounter` at `0x180038923`
- `KERNEL32!QueryPerformanceCounter` at `0x180038923`

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
0x1800388c4  mov     [rsp-8+arg_10], rbx
0x1800388c9  push    rbp
0x1800388ca  mov     rbp, rsp
0x1800388cd  sub     rsp, 30h
0x1800388d1  mov     rax, cs:__security_cookie
0x1800388d8  mov     rbx, 2B992DDFA232h
0x1800388e2  cmp     rax, rbx
0x1800388e5  jnz     short loc_180038964
0x1800388e7  xor     eax, eax
0x1800388e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800388ed  mov     [rbp+var_10], rax
0x1800388f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800388f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800388f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800388ff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180038903  mov     [rbp+var_10], rax
0x180038907  call    cs:__imp_GetCurrentThreadId
0x18003890d  mov     eax, eax
0x18003890f  xor     [rbp+var_10], rax
0x180038913  call    cs:__imp_GetCurrentProcessId
0x180038919  mov     eax, eax
0x18003891b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003891f  xor     [rbp+var_10], rax
0x180038923  call    cs:__imp_QueryPerformanceCounter
0x180038929  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003892c  lea     rcx, [rbp+var_10]
0x180038930  shl     rax, 20h
0x180038934  xor     rax, qword ptr [rbp+PerformanceCount]
0x180038938  xor     rax, [rbp+var_10]
0x18003893c  xor     rax, rcx
0x18003893f  mov     rcx, 0FFFFFFFFFFFFh
0x180038949  and     rax, rcx
0x18003894c  mov     rcx, 2B992DDFA233h
0x180038956  cmp     rax, rbx
0x180038959  cmovz   rax, rcx
0x18003895d  mov     cs:__security_cookie, rax
0x180038964  mov     rbx, [rsp+30h+arg_10]
0x180038969  not     rax
0x18003896c  mov     cs:__security_cookie_complement, rax
0x180038973  add     rsp, 30h
0x180038977  pop     rbp
0x180038978  retn
```
