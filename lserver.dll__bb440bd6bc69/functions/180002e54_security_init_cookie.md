# __security_init_cookie

- ea: `0x180002e54`
- end: `0x180002f2d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002510`

## callees

- `0x180002e54`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180002eda`
- `KERNEL32!QueryPerformanceCounter` at `0x180002eda`
- `KERNEL32!GetTickCount` at `0x180002eaf`
- `KERNEL32!GetTickCount` at `0x180002ebf`
- `KERNEL32!GetTickCount` at `0x180002eaf`
- `KERNEL32!GetTickCount` at `0x180002ebf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002e89`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002e89`
- `KERNEL32!GetCurrentProcessId` at `0x180002e97`
- `KERNEL32!GetCurrentProcessId` at `0x180002e97`
- `KERNEL32!GetCurrentThreadId` at `0x180002ea3`
- `KERNEL32!GetCurrentThreadId` at `0x180002ea3`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180002e54  mov     [rsp-8+arg_18], rbx
0x180002e59  push    rbp
0x180002e5a  mov     rbp, rsp
0x180002e5d  sub     rsp, 20h
0x180002e61  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002e66  mov     rbx, 2B992DDFA232h
0x180002e70  and     qword ptr [rbp+PerformanceCount], 0
0x180002e75  mov     rax, cs:__security_cookie
0x180002e7c  cmp     rax, rbx
0x180002e7f  jnz     loc_180002F18
0x180002e85  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002e89  call    cs:__imp_GetSystemTimeAsFileTime
0x180002e8f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002e93  mov     [rbp+arg_0], rax
0x180002e97  call    cs:__imp_GetCurrentProcessId
0x180002e9d  mov     eax, eax
0x180002e9f  xor     [rbp+arg_0], rax
0x180002ea3  call    cs:__imp_GetCurrentThreadId
0x180002ea9  mov     eax, eax
0x180002eab  xor     [rbp+arg_0], rax
0x180002eaf  call    cs:__imp_GetTickCount
0x180002eb5  mov     eax, eax
0x180002eb7  shl     rax, 18h
0x180002ebb  xor     [rbp+arg_0], rax
0x180002ebf  call    cs:__imp_GetTickCount
0x180002ec5  mov     eax, eax
0x180002ec7  lea     rcx, [rbp+arg_0]
0x180002ecb  xor     rax, [rbp+arg_0]
0x180002ecf  xor     rax, rcx
0x180002ed2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002ed6  mov     [rbp+arg_0], rax
0x180002eda  call    cs:__imp_QueryPerformanceCounter
0x180002ee0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ee3  mov     rcx, 0FFFFFFFFFFFFh
0x180002eed  shl     rax, 20h
0x180002ef1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002ef5  xor     rax, [rbp+arg_0]
0x180002ef9  and     rax, rcx
0x180002efc  mov     rcx, rax
0x180002eff  cmp     rax, rbx
0x180002f02  jnz     short loc_180002F11
0x180002f04  mov     rax, 2B992DDFA233h
0x180002f0e  mov     rcx, rax
0x180002f11  mov     cs:__security_cookie, rcx
0x180002f18  mov     rbx, [rsp+20h+arg_18]
0x180002f1d  not     rax
0x180002f20  mov     cs:__security_cookie_complement, rax
0x180002f27  add     rsp, 20h
0x180002f2b  pop     rbp
0x180002f2c  retn
```
