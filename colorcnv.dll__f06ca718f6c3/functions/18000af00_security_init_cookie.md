# __security_init_cookie

- ea: `0x18000af00`
- end: `0x18000afb5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000aae0`

## callees

- `0x18000af00`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000af5f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000af5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000af35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000af35`

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
0x18000af00  mov     [rsp-8+arg_10], rbx
0x18000af05  push    rbp
0x18000af06  mov     rbp, rsp
0x18000af09  sub     rsp, 30h
0x18000af0d  mov     rax, cs:__security_cookie
0x18000af14  mov     rbx, 2B992DDFA232h
0x18000af1e  cmp     rax, rbx
0x18000af21  jnz     short loc_18000AFA0
0x18000af23  xor     eax, eax
0x18000af25  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000af29  mov     [rbp+var_10], rax
0x18000af2d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000af31  mov     qword ptr [rbp+PerformanceCount], rax
0x18000af35  call    cs:__imp_GetSystemTimeAsFileTime
0x18000af3b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000af3f  mov     [rbp+var_10], rax
0x18000af43  call    cs:__imp_GetCurrentThreadId
0x18000af49  mov     eax, eax
0x18000af4b  xor     [rbp+var_10], rax
0x18000af4f  call    cs:__imp_GetCurrentProcessId
0x18000af55  mov     eax, eax
0x18000af57  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000af5b  xor     [rbp+var_10], rax
0x18000af5f  call    cs:__imp_QueryPerformanceCounter
0x18000af65  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000af68  lea     rcx, [rbp+var_10]
0x18000af6c  shl     rax, 20h
0x18000af70  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000af74  xor     rax, [rbp+var_10]
0x18000af78  xor     rax, rcx
0x18000af7b  mov     rcx, 0FFFFFFFFFFFFh
0x18000af85  and     rax, rcx
0x18000af88  mov     rcx, 2B992DDFA233h
0x18000af92  cmp     rax, rbx
0x18000af95  cmovz   rax, rcx
0x18000af99  mov     cs:__security_cookie, rax
0x18000afa0  mov     rbx, [rsp+30h+arg_10]
0x18000afa5  not     rax
0x18000afa8  mov     cs:__security_cookie_complement, rax
0x18000afaf  add     rsp, 30h
0x18000afb3  pop     rbp
0x18000afb4  retn
```
