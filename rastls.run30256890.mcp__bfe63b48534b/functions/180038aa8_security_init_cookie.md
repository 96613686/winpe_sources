# __security_init_cookie

- ea: `0x180038aa8`
- end: `0x180038b5d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180038210`

## callees

- `0x180038aa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038af7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180038af7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038aeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038aeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038add`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180038add`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038b07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038b07`

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
0x180038aa8  mov     [rsp-8+arg_10], rbx
0x180038aad  push    rbp
0x180038aae  mov     rbp, rsp
0x180038ab1  sub     rsp, 30h
0x180038ab5  mov     rax, cs:__security_cookie
0x180038abc  mov     rbx, 2B992DDFA232h
0x180038ac6  cmp     rax, rbx
0x180038ac9  jnz     short loc_180038B48
0x180038acb  xor     eax, eax
0x180038acd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180038ad1  mov     [rbp+var_10], rax
0x180038ad5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180038ad9  mov     qword ptr [rbp+PerformanceCount], rax
0x180038add  call    cs:__imp_GetSystemTimeAsFileTime
0x180038ae3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180038ae7  mov     [rbp+var_10], rax
0x180038aeb  call    cs:__imp_GetCurrentThreadId
0x180038af1  mov     eax, eax
0x180038af3  xor     [rbp+var_10], rax
0x180038af7  call    cs:__imp_GetCurrentProcessId
0x180038afd  mov     eax, eax
0x180038aff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180038b03  xor     [rbp+var_10], rax
0x180038b07  call    cs:__imp_QueryPerformanceCounter
0x180038b0d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180038b10  lea     rcx, [rbp+var_10]
0x180038b14  shl     rax, 20h
0x180038b18  xor     rax, qword ptr [rbp+PerformanceCount]
0x180038b1c  xor     rax, [rbp+var_10]
0x180038b20  xor     rax, rcx
0x180038b23  mov     rcx, 0FFFFFFFFFFFFh
0x180038b2d  and     rax, rcx
0x180038b30  mov     rcx, 2B992DDFA233h
0x180038b3a  cmp     rax, rbx
0x180038b3d  cmovz   rax, rcx
0x180038b41  mov     cs:__security_cookie, rax
0x180038b48  mov     rbx, [rsp+30h+arg_10]
0x180038b4d  not     rax
0x180038b50  mov     cs:__security_cookie_complement, rax
0x180038b57  add     rsp, 30h
0x180038b5b  pop     rbp
0x180038b5c  retn
```
