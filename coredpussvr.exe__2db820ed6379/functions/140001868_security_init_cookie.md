# __security_init_cookie

- ea: `0x140001868`
- end: `0x14000191d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400014d0`

## callees

- `0x140001868`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400018ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400018ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400018b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400018b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400018c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400018c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000189d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000189d`

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
0x140001868  mov     [rsp-8+arg_10], rbx
0x14000186d  push    rbp
0x14000186e  mov     rbp, rsp
0x140001871  sub     rsp, 30h
0x140001875  mov     rax, cs:__security_cookie
0x14000187c  mov     rbx, 2B992DDFA232h
0x140001886  cmp     rax, rbx
0x140001889  jnz     short loc_140001908
0x14000188b  xor     eax, eax
0x14000188d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001891  mov     [rbp+var_10], rax
0x140001895  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001899  mov     qword ptr [rbp+PerformanceCount], rax
0x14000189d  call    cs:__imp_GetSystemTimeAsFileTime
0x1400018a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400018a7  mov     [rbp+var_10], rax
0x1400018ab  call    cs:__imp_GetCurrentThreadId
0x1400018b1  mov     eax, eax
0x1400018b3  xor     [rbp+var_10], rax
0x1400018b7  call    cs:__imp_GetCurrentProcessId
0x1400018bd  mov     eax, eax
0x1400018bf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400018c3  xor     [rbp+var_10], rax
0x1400018c7  call    cs:__imp_QueryPerformanceCounter
0x1400018cd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400018d0  lea     rcx, [rbp+var_10]
0x1400018d4  shl     rax, 20h
0x1400018d8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400018dc  xor     rax, [rbp+var_10]
0x1400018e0  xor     rax, rcx
0x1400018e3  mov     rcx, 0FFFFFFFFFFFFh
0x1400018ed  and     rax, rcx
0x1400018f0  mov     rcx, 2B992DDFA233h
0x1400018fa  cmp     rax, rbx
0x1400018fd  cmovz   rax, rcx
0x140001901  mov     cs:__security_cookie, rax
0x140001908  mov     rbx, [rsp+30h+arg_10]
0x14000190d  not     rax
0x140001910  mov     cs:__security_cookie_complement, rax
0x140001917  add     rsp, 30h
0x14000191b  pop     rbp
0x14000191c  retn
```
