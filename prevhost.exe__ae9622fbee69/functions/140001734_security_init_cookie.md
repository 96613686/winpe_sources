# __security_init_cookie

- ea: `0x140001734`
- end: `0x1400017e9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001440`

## callees

- `0x140001734`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001777`
- `KERNEL32!GetCurrentThreadId` at `0x140001777`
- `KERNEL32!GetCurrentProcessId` at `0x140001783`
- `KERNEL32!GetCurrentProcessId` at `0x140001783`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001793`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001793`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001769`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001769`

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
0x140001734  mov     [rsp-8+arg_10], rbx
0x140001739  push    rbp
0x14000173a  mov     rbp, rsp
0x14000173d  sub     rsp, 30h
0x140001741  mov     rax, cs:__security_cookie
0x140001748  mov     rbx, 2B992DDFA232h
0x140001752  cmp     rax, rbx
0x140001755  jnz     short loc_1400017D4
0x140001757  xor     eax, eax
0x140001759  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000175d  mov     [rbp+var_10], rax
0x140001761  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001765  mov     qword ptr [rbp+PerformanceCount], rax
0x140001769  call    cs:__imp_GetSystemTimeAsFileTime
0x14000176f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001773  mov     [rbp+var_10], rax
0x140001777  call    cs:__imp_GetCurrentThreadId
0x14000177d  mov     eax, eax
0x14000177f  xor     [rbp+var_10], rax
0x140001783  call    cs:__imp_GetCurrentProcessId
0x140001789  mov     eax, eax
0x14000178b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000178f  xor     [rbp+var_10], rax
0x140001793  call    cs:__imp_QueryPerformanceCounter
0x140001799  mov     eax, dword ptr [rbp+PerformanceCount]
0x14000179c  lea     rcx, [rbp+var_10]
0x1400017a0  shl     rax, 20h
0x1400017a4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400017a8  xor     rax, [rbp+var_10]
0x1400017ac  xor     rax, rcx
0x1400017af  mov     rcx, 0FFFFFFFFFFFFh
0x1400017b9  and     rax, rcx
0x1400017bc  mov     rcx, 2B992DDFA233h
0x1400017c6  cmp     rax, rbx
0x1400017c9  cmovz   rax, rcx
0x1400017cd  mov     cs:__security_cookie, rax
0x1400017d4  mov     rbx, [rsp+30h+arg_10]
0x1400017d9  not     rax
0x1400017dc  mov     cs:__security_cookie_complement, rax
0x1400017e3  add     rsp, 30h
0x1400017e7  pop     rbp
0x1400017e8  retn
```
