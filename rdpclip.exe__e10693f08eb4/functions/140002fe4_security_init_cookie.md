# __security_init_cookie

- ea: `0x140002fe4`
- end: `0x1400030c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002a30`

## callees

- `0x140002fe4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000302b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000302b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000301d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000301d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140003043`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140003053`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140003043`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140003053`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000306e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000306e`

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
0x140002fe4  mov     [rsp-8+arg_18], rbx
0x140002fe9  push    rbp
0x140002fea  mov     rbp, rsp
0x140002fed  sub     rsp, 20h
0x140002ff1  xor     eax, eax
0x140002ff3  mov     rbx, 2B992DDFA232h
0x140002ffd  mov     [rbp+arg_0], rax
0x140003001  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140003005  mov     qword ptr [rbp+PerformanceCount], rax
0x140003009  mov     rax, cs:__security_cookie
0x140003010  cmp     rax, rbx
0x140003013  jnz     loc_1400030AC
0x140003019  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000301d  call    cs:__imp_GetSystemTimeAsFileTime
0x140003023  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140003027  mov     [rbp+arg_0], rax
0x14000302b  call    cs:__imp_GetCurrentProcessId
0x140003031  mov     eax, eax
0x140003033  xor     [rbp+arg_0], rax
0x140003037  call    cs:__imp_GetCurrentThreadId
0x14000303d  mov     eax, eax
0x14000303f  xor     [rbp+arg_0], rax
0x140003043  call    cs:__imp_GetTickCount
0x140003049  mov     eax, eax
0x14000304b  shl     rax, 18h
0x14000304f  xor     [rbp+arg_0], rax
0x140003053  call    cs:__imp_GetTickCount
0x140003059  mov     eax, eax
0x14000305b  lea     rcx, [rbp+arg_0]
0x14000305f  xor     rax, [rbp+arg_0]
0x140003063  xor     rax, rcx
0x140003066  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000306a  mov     [rbp+arg_0], rax
0x14000306e  call    cs:__imp_QueryPerformanceCounter
0x140003074  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003077  mov     rcx, 0FFFFFFFFFFFFh
0x140003081  shl     rax, 20h
0x140003085  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003089  xor     rax, [rbp+arg_0]
0x14000308d  and     rax, rcx
0x140003090  mov     rcx, rax
0x140003093  cmp     rax, rbx
0x140003096  jnz     short loc_1400030A5
0x140003098  mov     rax, 2B992DDFA233h
0x1400030a2  mov     rcx, rax
0x1400030a5  mov     cs:__security_cookie, rcx
0x1400030ac  mov     rbx, [rsp+20h+arg_18]
0x1400030b1  not     rax
0x1400030b4  mov     cs:__security_cookie_complement, rax
0x1400030bb  add     rsp, 20h
0x1400030bf  pop     rbp
0x1400030c0  retn
```
