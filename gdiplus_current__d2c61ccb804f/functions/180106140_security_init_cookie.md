# __security_init_cookie

- ea: `0x180106140`
- end: `0x1801061f5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180105cf0`

## callees

- `0x180106140`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180106183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180106183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18010618f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18010618f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180106175`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180106175`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010619f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010619f`

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
0x180106140  mov     [rsp-8+arg_10], rbx
0x180106145  push    rbp
0x180106146  mov     rbp, rsp
0x180106149  sub     rsp, 30h
0x18010614d  mov     rax, cs:__security_cookie
0x180106154  mov     rbx, 2B992DDFA232h
0x18010615e  cmp     rax, rbx
0x180106161  jnz     short loc_1801061E0
0x180106163  xor     eax, eax
0x180106165  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180106169  mov     [rbp+var_10], rax
0x18010616d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180106171  mov     qword ptr [rbp+PerformanceCount], rax
0x180106175  call    cs:__imp_GetSystemTimeAsFileTime
0x18010617b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18010617f  mov     [rbp+var_10], rax
0x180106183  call    cs:__imp_GetCurrentThreadId
0x180106189  mov     eax, eax
0x18010618b  xor     [rbp+var_10], rax
0x18010618f  call    cs:__imp_GetCurrentProcessId
0x180106195  mov     eax, eax
0x180106197  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18010619b  xor     [rbp+var_10], rax
0x18010619f  call    cs:__imp_QueryPerformanceCounter
0x1801061a5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801061a8  lea     rcx, [rbp+var_10]
0x1801061ac  shl     rax, 20h
0x1801061b0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801061b4  xor     rax, [rbp+var_10]
0x1801061b8  xor     rax, rcx
0x1801061bb  mov     rcx, 0FFFFFFFFFFFFh
0x1801061c5  and     rax, rcx
0x1801061c8  mov     rcx, 2B992DDFA233h
0x1801061d2  cmp     rax, rbx
0x1801061d5  cmovz   rax, rcx
0x1801061d9  mov     cs:__security_cookie, rax
0x1801061e0  mov     rbx, [rsp+30h+arg_10]
0x1801061e5  not     rax
0x1801061e8  mov     cs:__security_cookie_complement, rax
0x1801061ef  add     rsp, 30h
0x1801061f3  pop     rbp
0x1801061f4  retn
```
