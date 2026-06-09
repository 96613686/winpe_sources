# __security_init_cookie

- ea: `0x1800037b4`
- end: `0x180003891`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002e40`

## callees

- `0x1800037b4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003807`
- `KERNEL32!GetCurrentThreadId` at `0x180003807`
- `KERNEL32!QueryPerformanceCounter` at `0x18000383e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000383e`
- `KERNEL32!GetCurrentProcessId` at `0x1800037fb`
- `KERNEL32!GetCurrentProcessId` at `0x1800037fb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800037ed`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800037ed`
- `KERNEL32!GetTickCount` at `0x180003813`
- `KERNEL32!GetTickCount` at `0x180003823`
- `KERNEL32!GetTickCount` at `0x180003813`
- `KERNEL32!GetTickCount` at `0x180003823`

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
0x1800037b4  mov     [rsp-8+arg_18], rbx
0x1800037b9  push    rbp
0x1800037ba  mov     rbp, rsp
0x1800037bd  sub     rsp, 20h
0x1800037c1  xor     eax, eax
0x1800037c3  mov     rbx, 2B992DDFA232h
0x1800037cd  mov     [rbp+arg_0], rax
0x1800037d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800037d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800037d9  mov     rax, cs:__security_cookie
0x1800037e0  cmp     rax, rbx
0x1800037e3  jnz     loc_18000387C
0x1800037e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800037ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800037f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800037f7  mov     [rbp+arg_0], rax
0x1800037fb  call    cs:__imp_GetCurrentProcessId
0x180003801  mov     eax, eax
0x180003803  xor     [rbp+arg_0], rax
0x180003807  call    cs:__imp_GetCurrentThreadId
0x18000380d  mov     eax, eax
0x18000380f  xor     [rbp+arg_0], rax
0x180003813  call    cs:__imp_GetTickCount
0x180003819  mov     eax, eax
0x18000381b  shl     rax, 18h
0x18000381f  xor     [rbp+arg_0], rax
0x180003823  call    cs:__imp_GetTickCount
0x180003829  mov     eax, eax
0x18000382b  lea     rcx, [rbp+arg_0]
0x18000382f  xor     rax, [rbp+arg_0]
0x180003833  xor     rax, rcx
0x180003836  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000383a  mov     [rbp+arg_0], rax
0x18000383e  call    cs:__imp_QueryPerformanceCounter
0x180003844  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003847  mov     rcx, 0FFFFFFFFFFFFh
0x180003851  shl     rax, 20h
0x180003855  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003859  xor     rax, [rbp+arg_0]
0x18000385d  and     rax, rcx
0x180003860  mov     rcx, rax
0x180003863  cmp     rax, rbx
0x180003866  jnz     short loc_180003875
0x180003868  mov     rax, 2B992DDFA233h
0x180003872  mov     rcx, rax
0x180003875  mov     cs:__security_cookie, rcx
0x18000387c  mov     rbx, [rsp+20h+arg_18]
0x180003881  not     rax
0x180003884  mov     cs:__security_cookie_complement, rax
0x18000388b  add     rsp, 20h
0x18000388f  pop     rbp
0x180003890  retn
```
