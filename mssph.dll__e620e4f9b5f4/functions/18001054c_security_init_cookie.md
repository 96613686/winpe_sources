# __security_init_cookie

- ea: `0x18001054c`
- end: `0x180010601`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fc70`

## callees

- `0x18001054c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001058f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001058f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001059b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001059b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010581`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010581`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800105ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800105ab`

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
0x18001054c  mov     [rsp-8+arg_10], rbx
0x180010551  push    rbp
0x180010552  mov     rbp, rsp
0x180010555  sub     rsp, 30h
0x180010559  mov     rax, cs:__security_cookie
0x180010560  mov     rbx, 2B992DDFA232h
0x18001056a  cmp     rax, rbx
0x18001056d  jnz     short loc_1800105EC
0x18001056f  xor     eax, eax
0x180010571  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010575  mov     [rbp+var_10], rax
0x180010579  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001057d  mov     qword ptr [rbp+PerformanceCount], rax
0x180010581  call    cs:__imp_GetSystemTimeAsFileTime
0x180010587  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001058b  mov     [rbp+var_10], rax
0x18001058f  call    cs:__imp_GetCurrentThreadId
0x180010595  mov     eax, eax
0x180010597  xor     [rbp+var_10], rax
0x18001059b  call    cs:__imp_GetCurrentProcessId
0x1800105a1  mov     eax, eax
0x1800105a3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800105a7  xor     [rbp+var_10], rax
0x1800105ab  call    cs:__imp_QueryPerformanceCounter
0x1800105b1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800105b4  lea     rcx, [rbp+var_10]
0x1800105b8  shl     rax, 20h
0x1800105bc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800105c0  xor     rax, [rbp+var_10]
0x1800105c4  xor     rax, rcx
0x1800105c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800105d1  and     rax, rcx
0x1800105d4  mov     rcx, 2B992DDFA233h
0x1800105de  cmp     rax, rbx
0x1800105e1  cmovz   rax, rcx
0x1800105e5  mov     cs:__security_cookie, rax
0x1800105ec  mov     rbx, [rsp+30h+arg_10]
0x1800105f1  not     rax
0x1800105f4  mov     cs:__security_cookie_complement, rax
0x1800105fb  add     rsp, 30h
0x1800105ff  pop     rbp
0x180010600  retn
```
