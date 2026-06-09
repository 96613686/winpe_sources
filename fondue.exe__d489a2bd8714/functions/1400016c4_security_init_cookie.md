# __security_init_cookie

- ea: `0x1400016c4`
- end: `0x1400017a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001490`

## callees

- `0x1400016c4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001717`
- `KERNEL32!GetCurrentThreadId` at `0x140001717`
- `KERNEL32!GetCurrentProcessId` at `0x14000170b`
- `KERNEL32!GetCurrentProcessId` at `0x14000170b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000174e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000174e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001723`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001733`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001723`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001733`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400016fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400016fd`

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
0x1400016c4  mov     [rsp-8+arg_18], rbx
0x1400016c9  push    rbp
0x1400016ca  mov     rbp, rsp
0x1400016cd  sub     rsp, 20h
0x1400016d1  xor     eax, eax
0x1400016d3  mov     rbx, 2B992DDFA232h
0x1400016dd  mov     [rbp+arg_0], rax
0x1400016e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400016e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400016e9  mov     rax, cs:__security_cookie
0x1400016f0  cmp     rax, rbx
0x1400016f3  jnz     loc_14000178C
0x1400016f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400016fd  call    cs:__imp_GetSystemTimeAsFileTime
0x140001703  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001707  mov     [rbp+arg_0], rax
0x14000170b  call    cs:__imp_GetCurrentProcessId
0x140001711  mov     eax, eax
0x140001713  xor     [rbp+arg_0], rax
0x140001717  call    cs:__imp_GetCurrentThreadId
0x14000171d  mov     eax, eax
0x14000171f  xor     [rbp+arg_0], rax
0x140001723  call    cs:__imp_GetTickCount
0x140001729  mov     eax, eax
0x14000172b  shl     rax, 18h
0x14000172f  xor     [rbp+arg_0], rax
0x140001733  call    cs:__imp_GetTickCount
0x140001739  mov     eax, eax
0x14000173b  lea     rcx, [rbp+arg_0]
0x14000173f  xor     rax, [rbp+arg_0]
0x140001743  xor     rax, rcx
0x140001746  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000174a  mov     [rbp+arg_0], rax
0x14000174e  call    cs:__imp_QueryPerformanceCounter
0x140001754  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001757  mov     rcx, 0FFFFFFFFFFFFh
0x140001761  shl     rax, 20h
0x140001765  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001769  xor     rax, [rbp+arg_0]
0x14000176d  and     rax, rcx
0x140001770  mov     rcx, rax
0x140001773  cmp     rax, rbx
0x140001776  jnz     short loc_140001785
0x140001778  mov     rax, 2B992DDFA233h
0x140001782  mov     rcx, rax
0x140001785  mov     cs:__security_cookie, rcx
0x14000178c  mov     rbx, [rsp+20h+arg_18]
0x140001791  not     rax
0x140001794  mov     cs:__security_cookie_complement, rax
0x14000179b  add     rsp, 20h
0x14000179f  pop     rbp
0x1400017a0  retn
```
