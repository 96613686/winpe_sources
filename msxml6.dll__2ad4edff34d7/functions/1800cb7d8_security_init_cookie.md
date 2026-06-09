# __security_init_cookie

- ea: `0x1800cb7d8`
- end: `0x1800cb88d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cb494`

## callees

- `0x1800cb7d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cb827`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cb827`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cb81b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cb81b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cb837`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cb837`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cb80d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cb80d`

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
0x1800cb7d8  mov     [rsp-8+arg_10], rbx
0x1800cb7dd  push    rbp
0x1800cb7de  mov     rbp, rsp
0x1800cb7e1  sub     rsp, 30h
0x1800cb7e5  mov     rax, cs:__security_cookie
0x1800cb7ec  mov     rbx, 2B992DDFA232h
0x1800cb7f6  cmp     rax, rbx
0x1800cb7f9  jnz     short loc_1800CB878
0x1800cb7fb  xor     eax, eax
0x1800cb7fd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800cb801  mov     [rbp+var_10], rax
0x1800cb805  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800cb809  mov     qword ptr [rbp+PerformanceCount], rax
0x1800cb80d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800cb813  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800cb817  mov     [rbp+var_10], rax
0x1800cb81b  call    cs:__imp_GetCurrentThreadId
0x1800cb821  mov     eax, eax
0x1800cb823  xor     [rbp+var_10], rax
0x1800cb827  call    cs:__imp_GetCurrentProcessId
0x1800cb82d  mov     eax, eax
0x1800cb82f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800cb833  xor     [rbp+var_10], rax
0x1800cb837  call    cs:__imp_QueryPerformanceCounter
0x1800cb83d  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800cb840  lea     rcx, [rbp+var_10]
0x1800cb844  shl     rax, 20h
0x1800cb848  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800cb84c  xor     rax, [rbp+var_10]
0x1800cb850  xor     rax, rcx
0x1800cb853  mov     rcx, 0FFFFFFFFFFFFh
0x1800cb85d  and     rax, rcx
0x1800cb860  mov     rcx, 2B992DDFA233h
0x1800cb86a  cmp     rax, rbx
0x1800cb86d  cmovz   rax, rcx
0x1800cb871  mov     cs:__security_cookie, rax
0x1800cb878  mov     rbx, [rsp+30h+arg_10]
0x1800cb87d  not     rax
0x1800cb880  mov     cs:__security_cookie_complement, rax
0x1800cb887  add     rsp, 30h
0x1800cb88b  pop     rbp
0x1800cb88c  retn
```
