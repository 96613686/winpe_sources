# __security_init_cookie

- ea: `0x18001df34`
- end: `0x18001e011`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d5b0`

## callees

- `0x18001df34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001df7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001df87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001df87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001df6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001df6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001df93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001dfa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001df93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001dfa3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001dfbe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001dfbe`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18001df34  mov     [rsp-8+arg_18], rbx
0x18001df39  push    rbp
0x18001df3a  mov     rbp, rsp
0x18001df3d  sub     rsp, 20h
0x18001df41  xor     eax, eax
0x18001df43  mov     rbx, 2B992DDFA232h
0x18001df4d  mov     [rbp+arg_0], rax
0x18001df51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001df55  mov     qword ptr [rbp+PerformanceCount], rax
0x18001df59  mov     rax, cs:__security_cookie
0x18001df60  cmp     rax, rbx
0x18001df63  jnz     loc_18001DFFC
0x18001df69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001df6d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001df73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001df77  mov     [rbp+arg_0], rax
0x18001df7b  call    cs:__imp_GetCurrentProcessId
0x18001df81  mov     eax, eax
0x18001df83  xor     [rbp+arg_0], rax
0x18001df87  call    cs:__imp_GetCurrentThreadId
0x18001df8d  mov     eax, eax
0x18001df8f  xor     [rbp+arg_0], rax
0x18001df93  call    cs:__imp_GetTickCount
0x18001df99  mov     eax, eax
0x18001df9b  shl     rax, 18h
0x18001df9f  xor     [rbp+arg_0], rax
0x18001dfa3  call    cs:__imp_GetTickCount
0x18001dfa9  mov     eax, eax
0x18001dfab  lea     rcx, [rbp+arg_0]
0x18001dfaf  xor     rax, [rbp+arg_0]
0x18001dfb3  xor     rax, rcx
0x18001dfb6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001dfba  mov     [rbp+arg_0], rax
0x18001dfbe  call    cs:__imp_QueryPerformanceCounter
0x18001dfc4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001dfc7  mov     rcx, 0FFFFFFFFFFFFh
0x18001dfd1  shl     rax, 20h
0x18001dfd5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001dfd9  xor     rax, [rbp+arg_0]
0x18001dfdd  and     rax, rcx
0x18001dfe0  mov     rcx, rax
0x18001dfe3  cmp     rax, rbx
0x18001dfe6  jnz     short loc_18001DFF5
0x18001dfe8  mov     rax, 2B992DDFA233h
0x18001dff2  mov     rcx, rax
0x18001dff5  mov     cs:__security_cookie, rcx
0x18001dffc  mov     rbx, [rsp+20h+arg_18]
0x18001e001  not     rax
0x18001e004  mov     cs:__security_cookie_complement, rax
0x18001e00b  add     rsp, 20h
0x18001e00f  pop     rbp
0x18001e010  retn
```
