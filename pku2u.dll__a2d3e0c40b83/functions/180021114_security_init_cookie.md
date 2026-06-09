# __security_init_cookie

- ea: `0x180021114`
- end: `0x1800211c9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800210a0`

## callees

- `0x180021114`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021173`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180021173`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021163`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021163`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021157`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021149`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180021149`

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
0x180021114  mov     [rsp-8+arg_10], rbx
0x180021119  push    rbp
0x18002111a  mov     rbp, rsp
0x18002111d  sub     rsp, 30h
0x180021121  mov     rax, cs:__security_cookie
0x180021128  mov     rbx, 2B992DDFA232h
0x180021132  cmp     rax, rbx
0x180021135  jnz     short loc_1800211B4
0x180021137  xor     eax, eax
0x180021139  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002113d  mov     [rbp+var_10], rax
0x180021141  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180021145  mov     qword ptr [rbp+PerformanceCount], rax
0x180021149  call    cs:__imp_GetSystemTimeAsFileTime
0x18002114f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180021153  mov     [rbp+var_10], rax
0x180021157  call    cs:__imp_GetCurrentThreadId
0x18002115d  mov     eax, eax
0x18002115f  xor     [rbp+var_10], rax
0x180021163  call    cs:__imp_GetCurrentProcessId
0x180021169  mov     eax, eax
0x18002116b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002116f  xor     [rbp+var_10], rax
0x180021173  call    cs:__imp_QueryPerformanceCounter
0x180021179  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002117c  lea     rcx, [rbp+var_10]
0x180021180  shl     rax, 20h
0x180021184  xor     rax, qword ptr [rbp+PerformanceCount]
0x180021188  xor     rax, [rbp+var_10]
0x18002118c  xor     rax, rcx
0x18002118f  mov     rcx, 0FFFFFFFFFFFFh
0x180021199  and     rax, rcx
0x18002119c  mov     rcx, 2B992DDFA233h
0x1800211a6  cmp     rax, rbx
0x1800211a9  cmovz   rax, rcx
0x1800211ad  mov     cs:__security_cookie, rax
0x1800211b4  mov     rbx, [rsp+30h+arg_10]
0x1800211b9  not     rax
0x1800211bc  mov     cs:__security_cookie_complement, rax
0x1800211c3  add     rsp, 30h
0x1800211c7  pop     rbp
0x1800211c8  retn
```
