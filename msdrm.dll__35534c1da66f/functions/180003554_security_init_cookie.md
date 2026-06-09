# __security_init_cookie

- ea: `0x180003554`
- end: `0x180003631`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a10`

## callees

- `0x180003554`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000359b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000359b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800035c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000358d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000358d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800035de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800035de`

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
0x180003554  mov     [rsp-8+arg_18], rbx
0x180003559  push    rbp
0x18000355a  mov     rbp, rsp
0x18000355d  sub     rsp, 20h
0x180003561  xor     eax, eax
0x180003563  mov     rbx, 2B992DDFA232h
0x18000356d  mov     [rbp+arg_0], rax
0x180003571  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003575  mov     qword ptr [rbp+PerformanceCount], rax
0x180003579  mov     rax, cs:__security_cookie
0x180003580  cmp     rax, rbx
0x180003583  jnz     loc_18000361C
0x180003589  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000358d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003593  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003597  mov     [rbp+arg_0], rax
0x18000359b  call    cs:__imp_GetCurrentProcessId
0x1800035a1  mov     eax, eax
0x1800035a3  xor     [rbp+arg_0], rax
0x1800035a7  call    cs:__imp_GetCurrentThreadId
0x1800035ad  mov     eax, eax
0x1800035af  xor     [rbp+arg_0], rax
0x1800035b3  call    cs:__imp_GetTickCount
0x1800035b9  mov     eax, eax
0x1800035bb  shl     rax, 18h
0x1800035bf  xor     [rbp+arg_0], rax
0x1800035c3  call    cs:__imp_GetTickCount
0x1800035c9  mov     eax, eax
0x1800035cb  lea     rcx, [rbp+arg_0]
0x1800035cf  xor     rax, [rbp+arg_0]
0x1800035d3  xor     rax, rcx
0x1800035d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800035da  mov     [rbp+arg_0], rax
0x1800035de  call    cs:__imp_QueryPerformanceCounter
0x1800035e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800035e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800035f1  shl     rax, 20h
0x1800035f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800035f9  xor     rax, [rbp+arg_0]
0x1800035fd  and     rax, rcx
0x180003600  mov     rcx, rax
0x180003603  cmp     rax, rbx
0x180003606  jnz     short loc_180003615
0x180003608  mov     rax, 2B992DDFA233h
0x180003612  mov     rcx, rax
0x180003615  mov     cs:__security_cookie, rcx
0x18000361c  mov     rbx, [rsp+20h+arg_18]
0x180003621  not     rax
0x180003624  mov     cs:__security_cookie_complement, rax
0x18000362b  add     rsp, 20h
0x18000362f  pop     rbp
0x180003630  retn
```
