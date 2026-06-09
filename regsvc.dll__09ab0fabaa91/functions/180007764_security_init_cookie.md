# __security_init_cookie

- ea: `0x180007764`
- end: `0x180007819`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800076f0`

## callees

- `0x180007764`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800077c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800077c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800077b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800077b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007799`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007799`

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
0x180007764  mov     [rsp-8+arg_10], rbx
0x180007769  push    rbp
0x18000776a  mov     rbp, rsp
0x18000776d  sub     rsp, 30h
0x180007771  mov     rax, cs:__security_cookie
0x180007778  mov     rbx, 2B992DDFA232h
0x180007782  cmp     rax, rbx
0x180007785  jnz     short loc_180007804
0x180007787  xor     eax, eax
0x180007789  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000778d  mov     [rbp+var_10], rax
0x180007791  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007795  mov     qword ptr [rbp+PerformanceCount], rax
0x180007799  call    cs:__imp_GetSystemTimeAsFileTime
0x18000779f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800077a3  mov     [rbp+var_10], rax
0x1800077a7  call    cs:__imp_GetCurrentThreadId
0x1800077ad  mov     eax, eax
0x1800077af  xor     [rbp+var_10], rax
0x1800077b3  call    cs:__imp_GetCurrentProcessId
0x1800077b9  mov     eax, eax
0x1800077bb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800077bf  xor     [rbp+var_10], rax
0x1800077c3  call    cs:__imp_QueryPerformanceCounter
0x1800077c9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800077cc  lea     rcx, [rbp+var_10]
0x1800077d0  shl     rax, 20h
0x1800077d4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800077d8  xor     rax, [rbp+var_10]
0x1800077dc  xor     rax, rcx
0x1800077df  mov     rcx, 0FFFFFFFFFFFFh
0x1800077e9  and     rax, rcx
0x1800077ec  mov     rcx, 2B992DDFA233h
0x1800077f6  cmp     rax, rbx
0x1800077f9  cmovz   rax, rcx
0x1800077fd  mov     cs:__security_cookie, rax
0x180007804  mov     rbx, [rsp+30h+arg_10]
0x180007809  not     rax
0x18000780c  mov     cs:__security_cookie_complement, rax
0x180007813  add     rsp, 30h
0x180007817  pop     rbp
0x180007818  retn
```
