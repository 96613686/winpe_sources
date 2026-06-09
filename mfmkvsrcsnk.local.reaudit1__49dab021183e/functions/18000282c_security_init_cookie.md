# __security_init_cookie

- ea: `0x18000282c`
- end: `0x1800028e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800023b0`

## callees

- `0x18000282c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000286f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000286f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000287b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000287b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000288b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000288b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002861`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002861`

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
0x18000282c  mov     [rsp-8+arg_10], rbx
0x180002831  push    rbp
0x180002832  mov     rbp, rsp
0x180002835  sub     rsp, 30h
0x180002839  mov     rax, cs:__security_cookie
0x180002840  mov     rbx, 2B992DDFA232h
0x18000284a  cmp     rax, rbx
0x18000284d  jnz     short loc_1800028CC
0x18000284f  xor     eax, eax
0x180002851  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002855  mov     [rbp+var_10], rax
0x180002859  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000285d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002861  call    cs:__imp_GetSystemTimeAsFileTime
0x180002867  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000286b  mov     [rbp+var_10], rax
0x18000286f  call    cs:__imp_GetCurrentThreadId
0x180002875  mov     eax, eax
0x180002877  xor     [rbp+var_10], rax
0x18000287b  call    cs:__imp_GetCurrentProcessId
0x180002881  mov     eax, eax
0x180002883  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002887  xor     [rbp+var_10], rax
0x18000288b  call    cs:__imp_QueryPerformanceCounter
0x180002891  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002894  lea     rcx, [rbp+var_10]
0x180002898  shl     rax, 20h
0x18000289c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800028a0  xor     rax, [rbp+var_10]
0x1800028a4  xor     rax, rcx
0x1800028a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800028b1  and     rax, rcx
0x1800028b4  mov     rcx, 2B992DDFA233h
0x1800028be  cmp     rax, rbx
0x1800028c1  cmovz   rax, rcx
0x1800028c5  mov     cs:__security_cookie, rax
0x1800028cc  mov     rbx, [rsp+30h+arg_10]
0x1800028d1  not     rax
0x1800028d4  mov     cs:__security_cookie_complement, rax
0x1800028db  add     rsp, 30h
0x1800028df  pop     rbp
0x1800028e0  retn
```
