# __security_init_cookie

- ea: `0x18000c51c`
- end: `0x18000c5d1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bdf0`

## callees

- `0x18000c51c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c56b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c56b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c55f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c55f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c551`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000c551`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c57b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000c57b`

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
0x18000c51c  mov     [rsp-8+arg_10], rbx
0x18000c521  push    rbp
0x18000c522  mov     rbp, rsp
0x18000c525  sub     rsp, 30h
0x18000c529  mov     rax, cs:__security_cookie
0x18000c530  mov     rbx, 2B992DDFA232h
0x18000c53a  cmp     rax, rbx
0x18000c53d  jnz     short loc_18000C5BC
0x18000c53f  xor     eax, eax
0x18000c541  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000c545  mov     [rbp+var_10], rax
0x18000c549  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000c54d  mov     qword ptr [rbp+PerformanceCount], rax
0x18000c551  call    cs:__imp_GetSystemTimeAsFileTime
0x18000c557  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000c55b  mov     [rbp+var_10], rax
0x18000c55f  call    cs:__imp_GetCurrentThreadId
0x18000c565  mov     eax, eax
0x18000c567  xor     [rbp+var_10], rax
0x18000c56b  call    cs:__imp_GetCurrentProcessId
0x18000c571  mov     eax, eax
0x18000c573  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000c577  xor     [rbp+var_10], rax
0x18000c57b  call    cs:__imp_QueryPerformanceCounter
0x18000c581  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000c584  lea     rcx, [rbp+var_10]
0x18000c588  shl     rax, 20h
0x18000c58c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000c590  xor     rax, [rbp+var_10]
0x18000c594  xor     rax, rcx
0x18000c597  mov     rcx, 0FFFFFFFFFFFFh
0x18000c5a1  and     rax, rcx
0x18000c5a4  mov     rcx, 2B992DDFA233h
0x18000c5ae  cmp     rax, rbx
0x18000c5b1  cmovz   rax, rcx
0x18000c5b5  mov     cs:__security_cookie, rax
0x18000c5bc  mov     rbx, [rsp+30h+arg_10]
0x18000c5c1  not     rax
0x18000c5c4  mov     cs:__security_cookie_complement, rax
0x18000c5cb  add     rsp, 30h
0x18000c5cf  pop     rbp
0x18000c5d0  retn
```
