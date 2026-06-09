# __security_init_cookie

- ea: `0x140003594`
- end: `0x140003649`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002f10`

## callees

- `0x140003594`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400035e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400035e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400035d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400035d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400035c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400035c9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400035f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400035f3`

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
0x140003594  mov     [rsp-8+arg_10], rbx
0x140003599  push    rbp
0x14000359a  mov     rbp, rsp
0x14000359d  sub     rsp, 30h
0x1400035a1  mov     rax, cs:__security_cookie
0x1400035a8  mov     rbx, 2B992DDFA232h
0x1400035b2  cmp     rax, rbx
0x1400035b5  jnz     short loc_140003634
0x1400035b7  xor     eax, eax
0x1400035b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400035bd  mov     [rbp+var_10], rax
0x1400035c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400035c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400035c9  call    cs:__imp_GetSystemTimeAsFileTime
0x1400035cf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400035d3  mov     [rbp+var_10], rax
0x1400035d7  call    cs:__imp_GetCurrentThreadId
0x1400035dd  mov     eax, eax
0x1400035df  xor     [rbp+var_10], rax
0x1400035e3  call    cs:__imp_GetCurrentProcessId
0x1400035e9  mov     eax, eax
0x1400035eb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400035ef  xor     [rbp+var_10], rax
0x1400035f3  call    cs:__imp_QueryPerformanceCounter
0x1400035f9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400035fc  lea     rcx, [rbp+var_10]
0x140003600  shl     rax, 20h
0x140003604  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003608  xor     rax, [rbp+var_10]
0x14000360c  xor     rax, rcx
0x14000360f  mov     rcx, 0FFFFFFFFFFFFh
0x140003619  and     rax, rcx
0x14000361c  mov     rcx, 2B992DDFA233h
0x140003626  cmp     rax, rbx
0x140003629  cmovz   rax, rcx
0x14000362d  mov     cs:__security_cookie, rax
0x140003634  mov     rbx, [rsp+30h+arg_10]
0x140003639  not     rax
0x14000363c  mov     cs:__security_cookie_complement, rax
0x140003643  add     rsp, 30h
0x140003647  pop     rbp
0x140003648  retn
```
