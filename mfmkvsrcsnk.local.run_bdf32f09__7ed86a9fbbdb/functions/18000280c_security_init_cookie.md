# __security_init_cookie

- ea: `0x18000280c`
- end: `0x1800028c1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002390`

## callees

- `0x18000280c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000284f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000284f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000285b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000285b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000286b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000286b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002841`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002841`

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
0x18000280c  mov     [rsp-8+arg_10], rbx
0x180002811  push    rbp
0x180002812  mov     rbp, rsp
0x180002815  sub     rsp, 30h
0x180002819  mov     rax, cs:__security_cookie
0x180002820  mov     rbx, 2B992DDFA232h
0x18000282a  cmp     rax, rbx
0x18000282d  jnz     short loc_1800028AC
0x18000282f  xor     eax, eax
0x180002831  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002835  mov     [rbp+var_10], rax
0x180002839  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000283d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002841  call    cs:__imp_GetSystemTimeAsFileTime
0x180002847  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000284b  mov     [rbp+var_10], rax
0x18000284f  call    cs:__imp_GetCurrentThreadId
0x180002855  mov     eax, eax
0x180002857  xor     [rbp+var_10], rax
0x18000285b  call    cs:__imp_GetCurrentProcessId
0x180002861  mov     eax, eax
0x180002863  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002867  xor     [rbp+var_10], rax
0x18000286b  call    cs:__imp_QueryPerformanceCounter
0x180002871  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002874  lea     rcx, [rbp+var_10]
0x180002878  shl     rax, 20h
0x18000287c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002880  xor     rax, [rbp+var_10]
0x180002884  xor     rax, rcx
0x180002887  mov     rcx, 0FFFFFFFFFFFFh
0x180002891  and     rax, rcx
0x180002894  mov     rcx, 2B992DDFA233h
0x18000289e  cmp     rax, rbx
0x1800028a1  cmovz   rax, rcx
0x1800028a5  mov     cs:__security_cookie, rax
0x1800028ac  mov     rbx, [rsp+30h+arg_10]
0x1800028b1  not     rax
0x1800028b4  mov     cs:__security_cookie_complement, rax
0x1800028bb  add     rsp, 30h
0x1800028bf  pop     rbp
0x1800028c0  retn
```
