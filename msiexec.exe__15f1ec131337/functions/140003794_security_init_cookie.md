# __security_init_cookie

- ea: `0x140003794`
- end: `0x140003871`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002f40`

## callees

- `0x140003794`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400037f3`
- `KERNEL32!GetTickCount` at `0x140003803`
- `KERNEL32!GetTickCount` at `0x1400037f3`
- `KERNEL32!GetTickCount` at `0x140003803`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400037cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400037cd`
- `KERNEL32!GetCurrentThreadId` at `0x1400037e7`
- `KERNEL32!GetCurrentThreadId` at `0x1400037e7`
- `KERNEL32!GetCurrentProcessId` at `0x1400037db`
- `KERNEL32!GetCurrentProcessId` at `0x1400037db`
- `KERNEL32!QueryPerformanceCounter` at `0x14000381e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000381e`

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
0x140003794  mov     [rsp-8+arg_18], rbx
0x140003799  push    rbp
0x14000379a  mov     rbp, rsp
0x14000379d  sub     rsp, 20h
0x1400037a1  xor     eax, eax
0x1400037a3  mov     rbx, 2B992DDFA232h
0x1400037ad  mov     [rbp+arg_0], rax
0x1400037b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400037b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400037b9  mov     rax, cs:__security_cookie
0x1400037c0  cmp     rax, rbx
0x1400037c3  jnz     loc_14000385C
0x1400037c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400037cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400037d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400037d7  mov     [rbp+arg_0], rax
0x1400037db  call    cs:__imp_GetCurrentProcessId
0x1400037e1  mov     eax, eax
0x1400037e3  xor     [rbp+arg_0], rax
0x1400037e7  call    cs:__imp_GetCurrentThreadId
0x1400037ed  mov     eax, eax
0x1400037ef  xor     [rbp+arg_0], rax
0x1400037f3  call    cs:__imp_GetTickCount
0x1400037f9  mov     eax, eax
0x1400037fb  shl     rax, 18h
0x1400037ff  xor     [rbp+arg_0], rax
0x140003803  call    cs:__imp_GetTickCount
0x140003809  mov     eax, eax
0x14000380b  lea     rcx, [rbp+arg_0]
0x14000380f  xor     rax, [rbp+arg_0]
0x140003813  xor     rax, rcx
0x140003816  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000381a  mov     [rbp+arg_0], rax
0x14000381e  call    cs:__imp_QueryPerformanceCounter
0x140003824  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003827  mov     rcx, 0FFFFFFFFFFFFh
0x140003831  shl     rax, 20h
0x140003835  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003839  xor     rax, [rbp+arg_0]
0x14000383d  and     rax, rcx
0x140003840  mov     rcx, rax
0x140003843  cmp     rax, rbx
0x140003846  jnz     short loc_140003855
0x140003848  mov     rax, 2B992DDFA233h
0x140003852  mov     rcx, rax
0x140003855  mov     cs:__security_cookie, rcx
0x14000385c  mov     rbx, [rsp+20h+arg_18]
0x140003861  not     rax
0x140003864  mov     cs:__security_cookie_complement, rax
0x14000386b  add     rsp, 20h
0x14000386f  pop     rbp
0x140003870  retn
```
