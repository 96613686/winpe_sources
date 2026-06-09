# __security_init_cookie

- ea: `0x180006aa0`
- end: `0x180006b55`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005de0`

## callees

- `0x180006aa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ae3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ae3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006aef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006aef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006ad5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006ad5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006aff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006aff`

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
0x180006aa0  mov     [rsp-8+arg_10], rbx
0x180006aa5  push    rbp
0x180006aa6  mov     rbp, rsp
0x180006aa9  sub     rsp, 30h
0x180006aad  mov     rax, cs:__security_cookie
0x180006ab4  mov     rbx, 2B992DDFA232h
0x180006abe  cmp     rax, rbx
0x180006ac1  jnz     short loc_180006B40
0x180006ac3  xor     eax, eax
0x180006ac5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006ac9  mov     [rbp+var_10], rax
0x180006acd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006ad1  mov     qword ptr [rbp+PerformanceCount], rax
0x180006ad5  call    cs:__imp_GetSystemTimeAsFileTime
0x180006adb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180006adf  mov     [rbp+var_10], rax
0x180006ae3  call    cs:__imp_GetCurrentThreadId
0x180006ae9  mov     eax, eax
0x180006aeb  xor     [rbp+var_10], rax
0x180006aef  call    cs:__imp_GetCurrentProcessId
0x180006af5  mov     eax, eax
0x180006af7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180006afb  xor     [rbp+var_10], rax
0x180006aff  call    cs:__imp_QueryPerformanceCounter
0x180006b05  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006b08  lea     rcx, [rbp+var_10]
0x180006b0c  shl     rax, 20h
0x180006b10  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006b14  xor     rax, [rbp+var_10]
0x180006b18  xor     rax, rcx
0x180006b1b  mov     rcx, 0FFFFFFFFFFFFh
0x180006b25  and     rax, rcx
0x180006b28  mov     rcx, 2B992DDFA233h
0x180006b32  cmp     rax, rbx
0x180006b35  cmovz   rax, rcx
0x180006b39  mov     cs:__security_cookie, rax
0x180006b40  mov     rbx, [rsp+30h+arg_10]
0x180006b45  not     rax
0x180006b48  mov     cs:__security_cookie_complement, rax
0x180006b4f  add     rsp, 30h
0x180006b53  pop     rbp
0x180006b54  retn
```
