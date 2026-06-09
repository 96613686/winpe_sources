# __security_init_cookie

- ea: `0x140001594`
- end: `0x140001671`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001350`

## callees

- `0x140001594`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400015e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400015e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400015db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400015db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400015f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001603`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400015f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001603`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400015cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400015cd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000161e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000161e`

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
0x140001594  mov     [rsp-8+arg_18], rbx
0x140001599  push    rbp
0x14000159a  mov     rbp, rsp
0x14000159d  sub     rsp, 20h
0x1400015a1  xor     eax, eax
0x1400015a3  mov     rbx, 2B992DDFA232h
0x1400015ad  mov     [rbp+arg_0], rax
0x1400015b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400015b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400015b9  mov     rax, cs:__security_cookie
0x1400015c0  cmp     rax, rbx
0x1400015c3  jnz     loc_14000165C
0x1400015c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400015cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400015d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400015d7  mov     [rbp+arg_0], rax
0x1400015db  call    cs:__imp_GetCurrentProcessId
0x1400015e1  mov     eax, eax
0x1400015e3  xor     [rbp+arg_0], rax
0x1400015e7  call    cs:__imp_GetCurrentThreadId
0x1400015ed  mov     eax, eax
0x1400015ef  xor     [rbp+arg_0], rax
0x1400015f3  call    cs:__imp_GetTickCount
0x1400015f9  mov     eax, eax
0x1400015fb  shl     rax, 18h
0x1400015ff  xor     [rbp+arg_0], rax
0x140001603  call    cs:__imp_GetTickCount
0x140001609  mov     eax, eax
0x14000160b  lea     rcx, [rbp+arg_0]
0x14000160f  xor     rax, [rbp+arg_0]
0x140001613  xor     rax, rcx
0x140001616  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000161a  mov     [rbp+arg_0], rax
0x14000161e  call    cs:__imp_QueryPerformanceCounter
0x140001624  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001627  mov     rcx, 0FFFFFFFFFFFFh
0x140001631  shl     rax, 20h
0x140001635  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001639  xor     rax, [rbp+arg_0]
0x14000163d  and     rax, rcx
0x140001640  mov     rcx, rax
0x140001643  cmp     rax, rbx
0x140001646  jnz     short loc_140001655
0x140001648  mov     rax, 2B992DDFA233h
0x140001652  mov     rcx, rax
0x140001655  mov     cs:__security_cookie, rcx
0x14000165c  mov     rbx, [rsp+20h+arg_18]
0x140001661  not     rax
0x140001664  mov     cs:__security_cookie_complement, rax
0x14000166b  add     rsp, 20h
0x14000166f  pop     rbp
0x140001670  retn
```
