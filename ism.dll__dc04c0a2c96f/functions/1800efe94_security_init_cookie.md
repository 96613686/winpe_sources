# __security_init_cookie

- ea: `0x1800efe94`
- end: `0x1800eff49`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800efe50`

## callees

- `0x1800efe94`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800efef3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800efef3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800efee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800efee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800efed7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800efec9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800efec9`

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
0x1800efe94  mov     [rsp-8+arg_10], rbx
0x1800efe99  push    rbp
0x1800efe9a  mov     rbp, rsp
0x1800efe9d  sub     rsp, 30h
0x1800efea1  mov     rax, cs:__security_cookie
0x1800efea8  mov     rbx, 2B992DDFA232h
0x1800efeb2  cmp     rax, rbx
0x1800efeb5  jnz     short loc_1800EFF34
0x1800efeb7  xor     eax, eax
0x1800efeb9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800efebd  mov     [rbp+var_10], rax
0x1800efec1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800efec5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800efec9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800efecf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800efed3  mov     [rbp+var_10], rax
0x1800efed7  call    cs:__imp_GetCurrentThreadId
0x1800efedd  mov     eax, eax
0x1800efedf  xor     [rbp+var_10], rax
0x1800efee3  call    cs:__imp_GetCurrentProcessId
0x1800efee9  mov     eax, eax
0x1800efeeb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800efeef  xor     [rbp+var_10], rax
0x1800efef3  call    cs:__imp_QueryPerformanceCounter
0x1800efef9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800efefc  lea     rcx, [rbp+var_10]
0x1800eff00  shl     rax, 20h
0x1800eff04  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800eff08  xor     rax, [rbp+var_10]
0x1800eff0c  xor     rax, rcx
0x1800eff0f  mov     rcx, 0FFFFFFFFFFFFh
0x1800eff19  and     rax, rcx
0x1800eff1c  mov     rcx, 2B992DDFA233h
0x1800eff26  cmp     rax, rbx
0x1800eff29  cmovz   rax, rcx
0x1800eff2d  mov     cs:__security_cookie, rax
0x1800eff34  mov     rbx, [rsp+30h+arg_10]
0x1800eff39  not     rax
0x1800eff3c  mov     cs:__security_cookie_complement, rax
0x1800eff43  add     rsp, 30h
0x1800eff47  pop     rbp
0x1800eff48  retn
```
