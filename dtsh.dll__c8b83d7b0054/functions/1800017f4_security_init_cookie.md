# __security_init_cookie

- ea: `0x1800017f4`
- end: `0x1800018d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013a0`

## callees

- `0x1800017f4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000187e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000187e`
- `KERNEL32!GetCurrentProcessId` at `0x18000183b`
- `KERNEL32!GetCurrentProcessId` at `0x18000183b`
- `KERNEL32!GetCurrentThreadId` at `0x180001847`
- `KERNEL32!GetCurrentThreadId` at `0x180001847`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000182d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000182d`
- `KERNEL32!GetTickCount` at `0x180001853`
- `KERNEL32!GetTickCount` at `0x180001863`
- `KERNEL32!GetTickCount` at `0x180001853`
- `KERNEL32!GetTickCount` at `0x180001863`

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
0x1800017f4  mov     [rsp-8+arg_18], rbx
0x1800017f9  push    rbp
0x1800017fa  mov     rbp, rsp
0x1800017fd  sub     rsp, 20h
0x180001801  xor     eax, eax
0x180001803  mov     rbx, 2B992DDFA232h
0x18000180d  mov     [rbp+arg_0], rax
0x180001811  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001815  mov     qword ptr [rbp+PerformanceCount], rax
0x180001819  mov     rax, cs:__security_cookie
0x180001820  cmp     rax, rbx
0x180001823  jnz     loc_1800018BC
0x180001829  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000182d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001833  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001837  mov     [rbp+arg_0], rax
0x18000183b  call    cs:__imp_GetCurrentProcessId
0x180001841  mov     eax, eax
0x180001843  xor     [rbp+arg_0], rax
0x180001847  call    cs:__imp_GetCurrentThreadId
0x18000184d  mov     eax, eax
0x18000184f  xor     [rbp+arg_0], rax
0x180001853  call    cs:__imp_GetTickCount
0x180001859  mov     eax, eax
0x18000185b  shl     rax, 18h
0x18000185f  xor     [rbp+arg_0], rax
0x180001863  call    cs:__imp_GetTickCount
0x180001869  mov     eax, eax
0x18000186b  lea     rcx, [rbp+arg_0]
0x18000186f  xor     rax, [rbp+arg_0]
0x180001873  xor     rax, rcx
0x180001876  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000187a  mov     [rbp+arg_0], rax
0x18000187e  call    cs:__imp_QueryPerformanceCounter
0x180001884  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001887  mov     rcx, 0FFFFFFFFFFFFh
0x180001891  shl     rax, 20h
0x180001895  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001899  xor     rax, [rbp+arg_0]
0x18000189d  and     rax, rcx
0x1800018a0  mov     rcx, rax
0x1800018a3  cmp     rax, rbx
0x1800018a6  jnz     short loc_1800018B5
0x1800018a8  mov     rax, 2B992DDFA233h
0x1800018b2  mov     rcx, rax
0x1800018b5  mov     cs:__security_cookie, rcx
0x1800018bc  mov     rbx, [rsp+20h+arg_18]
0x1800018c1  not     rax
0x1800018c4  mov     cs:__security_cookie_complement, rax
0x1800018cb  add     rsp, 20h
0x1800018cf  pop     rbp
0x1800018d0  retn
```
