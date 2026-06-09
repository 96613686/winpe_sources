# __security_init_cookie

- ea: `0x18001dd70`
- end: `0x18001de25`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d890`

## callees

- `0x18001dd70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ddb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ddb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ddbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ddbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001dda5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001dda5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ddcf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ddcf`

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
0x18001dd70  mov     [rsp-8+arg_10], rbx
0x18001dd75  push    rbp
0x18001dd76  mov     rbp, rsp
0x18001dd79  sub     rsp, 30h
0x18001dd7d  mov     rax, cs:__security_cookie
0x18001dd84  mov     rbx, 2B992DDFA232h
0x18001dd8e  cmp     rax, rbx
0x18001dd91  jnz     short loc_18001DE10
0x18001dd93  xor     eax, eax
0x18001dd95  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001dd99  mov     [rbp+var_10], rax
0x18001dd9d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001dda1  mov     qword ptr [rbp+PerformanceCount], rax
0x18001dda5  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ddab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001ddaf  mov     [rbp+var_10], rax
0x18001ddb3  call    cs:__imp_GetCurrentThreadId
0x18001ddb9  mov     eax, eax
0x18001ddbb  xor     [rbp+var_10], rax
0x18001ddbf  call    cs:__imp_GetCurrentProcessId
0x18001ddc5  mov     eax, eax
0x18001ddc7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001ddcb  xor     [rbp+var_10], rax
0x18001ddcf  call    cs:__imp_QueryPerformanceCounter
0x18001ddd5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001ddd8  lea     rcx, [rbp+var_10]
0x18001dddc  shl     rax, 20h
0x18001dde0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001dde4  xor     rax, [rbp+var_10]
0x18001dde8  xor     rax, rcx
0x18001ddeb  mov     rcx, 0FFFFFFFFFFFFh
0x18001ddf5  and     rax, rcx
0x18001ddf8  mov     rcx, 2B992DDFA233h
0x18001de02  cmp     rax, rbx
0x18001de05  cmovz   rax, rcx
0x18001de09  mov     cs:__security_cookie, rax
0x18001de10  mov     rbx, [rsp+30h+arg_10]
0x18001de15  not     rax
0x18001de18  mov     cs:__security_cookie_complement, rax
0x18001de1f  add     rsp, 30h
0x18001de23  pop     rbp
0x18001de24  retn
```
