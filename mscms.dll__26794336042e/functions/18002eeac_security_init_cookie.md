# __security_init_cookie

- ea: `0x18002eeac`
- end: `0x18002ef61`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e5a0`

## callees

- `0x18002eeac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002eeef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002eeef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002eefb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002eefb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002eee1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002eee1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ef0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ef0b`

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
0x18002eeac  mov     [rsp-8+arg_10], rbx
0x18002eeb1  push    rbp
0x18002eeb2  mov     rbp, rsp
0x18002eeb5  sub     rsp, 30h
0x18002eeb9  mov     rax, cs:__security_cookie
0x18002eec0  mov     rbx, 2B992DDFA232h
0x18002eeca  cmp     rax, rbx
0x18002eecd  jnz     short loc_18002EF4C
0x18002eecf  xor     eax, eax
0x18002eed1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002eed5  mov     [rbp+var_10], rax
0x18002eed9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002eedd  mov     qword ptr [rbp+PerformanceCount], rax
0x18002eee1  call    cs:__imp_GetSystemTimeAsFileTime
0x18002eee7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002eeeb  mov     [rbp+var_10], rax
0x18002eeef  call    cs:__imp_GetCurrentThreadId
0x18002eef5  mov     eax, eax
0x18002eef7  xor     [rbp+var_10], rax
0x18002eefb  call    cs:__imp_GetCurrentProcessId
0x18002ef01  mov     eax, eax
0x18002ef03  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002ef07  xor     [rbp+var_10], rax
0x18002ef0b  call    cs:__imp_QueryPerformanceCounter
0x18002ef11  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002ef14  lea     rcx, [rbp+var_10]
0x18002ef18  shl     rax, 20h
0x18002ef1c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002ef20  xor     rax, [rbp+var_10]
0x18002ef24  xor     rax, rcx
0x18002ef27  mov     rcx, 0FFFFFFFFFFFFh
0x18002ef31  and     rax, rcx
0x18002ef34  mov     rcx, 2B992DDFA233h
0x18002ef3e  cmp     rax, rbx
0x18002ef41  cmovz   rax, rcx
0x18002ef45  mov     cs:__security_cookie, rax
0x18002ef4c  mov     rbx, [rsp+30h+arg_10]
0x18002ef51  not     rax
0x18002ef54  mov     cs:__security_cookie_complement, rax
0x18002ef5b  add     rsp, 30h
0x18002ef5f  pop     rbp
0x18002ef60  retn
```
