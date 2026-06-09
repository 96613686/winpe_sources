# __security_init_cookie

- ea: `0x18003c16c`
- end: `0x18003c221`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bc30`

## callees

- `0x18003c16c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c1bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c1bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c1af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c1af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003c1cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003c1cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c1a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c1a1`

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
0x18003c16c  mov     [rsp-8+arg_10], rbx
0x18003c171  push    rbp
0x18003c172  mov     rbp, rsp
0x18003c175  sub     rsp, 30h
0x18003c179  mov     rax, cs:__security_cookie
0x18003c180  mov     rbx, 2B992DDFA232h
0x18003c18a  cmp     rax, rbx
0x18003c18d  jnz     short loc_18003C20C
0x18003c18f  xor     eax, eax
0x18003c191  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003c195  mov     [rbp+var_10], rax
0x18003c199  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003c19d  mov     qword ptr [rbp+PerformanceCount], rax
0x18003c1a1  call    cs:__imp_GetSystemTimeAsFileTime
0x18003c1a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003c1ab  mov     [rbp+var_10], rax
0x18003c1af  call    cs:__imp_GetCurrentThreadId
0x18003c1b5  mov     eax, eax
0x18003c1b7  xor     [rbp+var_10], rax
0x18003c1bb  call    cs:__imp_GetCurrentProcessId
0x18003c1c1  mov     eax, eax
0x18003c1c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003c1c7  xor     [rbp+var_10], rax
0x18003c1cb  call    cs:__imp_QueryPerformanceCounter
0x18003c1d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003c1d4  lea     rcx, [rbp+var_10]
0x18003c1d8  shl     rax, 20h
0x18003c1dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003c1e0  xor     rax, [rbp+var_10]
0x18003c1e4  xor     rax, rcx
0x18003c1e7  mov     rcx, 0FFFFFFFFFFFFh
0x18003c1f1  and     rax, rcx
0x18003c1f4  mov     rcx, 2B992DDFA233h
0x18003c1fe  cmp     rax, rbx
0x18003c201  cmovz   rax, rcx
0x18003c205  mov     cs:__security_cookie, rax
0x18003c20c  mov     rbx, [rsp+30h+arg_10]
0x18003c211  not     rax
0x18003c214  mov     cs:__security_cookie_complement, rax
0x18003c21b  add     rsp, 30h
0x18003c21f  pop     rbp
0x18003c220  retn
```
