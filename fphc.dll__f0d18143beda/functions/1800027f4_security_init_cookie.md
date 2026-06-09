# __security_init_cookie

- ea: `0x1800027f4`
- end: `0x1800028d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e20`

## callees

- `0x1800027f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000283b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000283b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002847`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000287e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000287e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000282d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000282d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002853`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002863`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002853`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002863`

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
0x1800027f4  mov     [rsp-8+arg_18], rbx
0x1800027f9  push    rbp
0x1800027fa  mov     rbp, rsp
0x1800027fd  sub     rsp, 20h
0x180002801  xor     eax, eax
0x180002803  mov     rbx, 2B992DDFA232h
0x18000280d  mov     [rbp+arg_0], rax
0x180002811  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002815  mov     qword ptr [rbp+PerformanceCount], rax
0x180002819  mov     rax, cs:__security_cookie
0x180002820  cmp     rax, rbx
0x180002823  jnz     loc_1800028BC
0x180002829  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000282d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002833  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002837  mov     [rbp+arg_0], rax
0x18000283b  call    cs:__imp_GetCurrentProcessId
0x180002841  mov     eax, eax
0x180002843  xor     [rbp+arg_0], rax
0x180002847  call    cs:__imp_GetCurrentThreadId
0x18000284d  mov     eax, eax
0x18000284f  xor     [rbp+arg_0], rax
0x180002853  call    cs:__imp_GetTickCount
0x180002859  mov     eax, eax
0x18000285b  shl     rax, 18h
0x18000285f  xor     [rbp+arg_0], rax
0x180002863  call    cs:__imp_GetTickCount
0x180002869  mov     eax, eax
0x18000286b  lea     rcx, [rbp+arg_0]
0x18000286f  xor     rax, [rbp+arg_0]
0x180002873  xor     rax, rcx
0x180002876  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000287a  mov     [rbp+arg_0], rax
0x18000287e  call    cs:__imp_QueryPerformanceCounter
0x180002884  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002887  mov     rcx, 0FFFFFFFFFFFFh
0x180002891  shl     rax, 20h
0x180002895  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002899  xor     rax, [rbp+arg_0]
0x18000289d  and     rax, rcx
0x1800028a0  mov     rcx, rax
0x1800028a3  cmp     rax, rbx
0x1800028a6  jnz     short loc_1800028B5
0x1800028a8  mov     rax, 2B992DDFA233h
0x1800028b2  mov     rcx, rax
0x1800028b5  mov     cs:__security_cookie, rcx
0x1800028bc  mov     rbx, [rsp+20h+arg_18]
0x1800028c1  not     rax
0x1800028c4  mov     cs:__security_cookie_complement, rax
0x1800028cb  add     rsp, 20h
0x1800028cf  pop     rbp
0x1800028d0  retn
```
