# __security_init_cookie

- ea: `0x180001984`
- end: `0x180001a39`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014b0`

## callees

- `0x180001984`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019b9`

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
0x180001984  mov     [rsp-8+arg_10], rbx
0x180001989  push    rbp
0x18000198a  mov     rbp, rsp
0x18000198d  sub     rsp, 30h
0x180001991  mov     rax, cs:__security_cookie
0x180001998  mov     rbx, 2B992DDFA232h
0x1800019a2  cmp     rax, rbx
0x1800019a5  jnz     short loc_180001A24
0x1800019a7  xor     eax, eax
0x1800019a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019ad  mov     [rbp+var_10], rax
0x1800019b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019bf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019c3  mov     [rbp+var_10], rax
0x1800019c7  call    cs:__imp_GetCurrentThreadId
0x1800019cd  mov     eax, eax
0x1800019cf  xor     [rbp+var_10], rax
0x1800019d3  call    cs:__imp_GetCurrentProcessId
0x1800019d9  mov     eax, eax
0x1800019db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800019df  xor     [rbp+var_10], rax
0x1800019e3  call    cs:__imp_QueryPerformanceCounter
0x1800019e9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019ec  lea     rcx, [rbp+var_10]
0x1800019f0  shl     rax, 20h
0x1800019f4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800019f8  xor     rax, [rbp+var_10]
0x1800019fc  xor     rax, rcx
0x1800019ff  mov     rcx, 0FFFFFFFFFFFFh
0x180001a09  and     rax, rcx
0x180001a0c  mov     rcx, 2B992DDFA233h
0x180001a16  cmp     rax, rbx
0x180001a19  cmovz   rax, rcx
0x180001a1d  mov     cs:__security_cookie, rax
0x180001a24  mov     rbx, [rsp+30h+arg_10]
0x180001a29  not     rax
0x180001a2c  mov     cs:__security_cookie_complement, rax
0x180001a33  add     rsp, 30h
0x180001a37  pop     rbp
0x180001a38  retn
```
