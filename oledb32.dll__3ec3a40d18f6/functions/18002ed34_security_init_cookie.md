# __security_init_cookie

- ea: `0x18002ed34`
- end: `0x18002ee11`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e2e0`

## callees

- `0x18002ed34`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18002ed93`
- `KERNEL32!GetTickCount` at `0x18002eda3`
- `KERNEL32!GetTickCount` at `0x18002ed93`
- `KERNEL32!GetTickCount` at `0x18002eda3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002ed6d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002ed6d`
- `KERNEL32!QueryPerformanceCounter` at `0x18002edbe`
- `KERNEL32!QueryPerformanceCounter` at `0x18002edbe`
- `KERNEL32!GetCurrentProcessId` at `0x18002ed7b`
- `KERNEL32!GetCurrentProcessId` at `0x18002ed7b`
- `KERNEL32!GetCurrentThreadId` at `0x18002ed87`
- `KERNEL32!GetCurrentThreadId` at `0x18002ed87`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18002ed34  mov     [rsp-8+arg_18], rbx
0x18002ed39  push    rbp
0x18002ed3a  mov     rbp, rsp
0x18002ed3d  sub     rsp, 20h
0x18002ed41  xor     eax, eax
0x18002ed43  mov     rbx, 2B992DDFA232h
0x18002ed4d  mov     [rbp+arg_0], rax
0x18002ed51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002ed55  mov     qword ptr [rbp+PerformanceCount], rax
0x18002ed59  mov     rax, cs:__security_cookie
0x18002ed60  cmp     rax, rbx
0x18002ed63  jnz     loc_18002EDFC
0x18002ed69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002ed6d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002ed73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002ed77  mov     [rbp+arg_0], rax
0x18002ed7b  call    cs:__imp_GetCurrentProcessId
0x18002ed81  mov     eax, eax
0x18002ed83  xor     [rbp+arg_0], rax
0x18002ed87  call    cs:__imp_GetCurrentThreadId
0x18002ed8d  mov     eax, eax
0x18002ed8f  xor     [rbp+arg_0], rax
0x18002ed93  call    cs:__imp_GetTickCount
0x18002ed99  mov     eax, eax
0x18002ed9b  shl     rax, 18h
0x18002ed9f  xor     [rbp+arg_0], rax
0x18002eda3  call    cs:__imp_GetTickCount
0x18002eda9  mov     eax, eax
0x18002edab  lea     rcx, [rbp+arg_0]
0x18002edaf  xor     rax, [rbp+arg_0]
0x18002edb3  xor     rax, rcx
0x18002edb6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002edba  mov     [rbp+arg_0], rax
0x18002edbe  call    cs:__imp_QueryPerformanceCounter
0x18002edc4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002edc7  mov     rcx, 0FFFFFFFFFFFFh
0x18002edd1  shl     rax, 20h
0x18002edd5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002edd9  xor     rax, [rbp+arg_0]
0x18002eddd  and     rax, rcx
0x18002ede0  mov     rcx, rax
0x18002ede3  cmp     rax, rbx
0x18002ede6  jnz     short loc_18002EDF5
0x18002ede8  mov     rax, 2B992DDFA233h
0x18002edf2  mov     rcx, rax
0x18002edf5  mov     cs:__security_cookie, rcx
0x18002edfc  mov     rbx, [rsp+20h+arg_18]
0x18002ee01  not     rax
0x18002ee04  mov     cs:__security_cookie_complement, rax
0x18002ee0b  add     rsp, 20h
0x18002ee0f  pop     rbp
0x18002ee10  retn
```
