# __security_init_cookie

- ea: `0x18019b498`
- end: `0x18019b547`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18019a7f0`

## callees

- `0x18019b498`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18019b4d5`
- `KERNEL32!GetCurrentThreadId` at `0x18019b4d5`
- `KERNEL32!GetCurrentProcessId` at `0x18019b4e1`
- `KERNEL32!GetCurrentProcessId` at `0x18019b4e1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18019b4c7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18019b4c7`
- `KERNEL32!QueryPerformanceCounter` at `0x18019b4f1`
- `KERNEL32!QueryPerformanceCounter` at `0x18019b4f1`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x18019b498  mov     [rsp-8+arg_10], rbx
0x18019b49d  push    rbp
0x18019b49e  mov     rbp, rsp
0x18019b4a1  sub     rsp, 30h
0x18019b4a5  mov     rax, cs:__security_cookie
0x18019b4ac  mov     rbx, 2B992DDFA232h
0x18019b4b6  cmp     rax, rbx
0x18019b4b9  jnz     short loc_18019B532
0x18019b4bb  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18019b4bf  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18019b4c7  call    cs:__imp_GetSystemTimeAsFileTime
0x18019b4cd  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18019b4d1  mov     [rbp+var_10], rax
0x18019b4d5  call    cs:__imp_GetCurrentThreadId
0x18019b4db  mov     eax, eax
0x18019b4dd  xor     [rbp+var_10], rax
0x18019b4e1  call    cs:__imp_GetCurrentProcessId
0x18019b4e7  mov     eax, eax
0x18019b4e9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18019b4ed  xor     [rbp+var_10], rax
0x18019b4f1  call    cs:__imp_QueryPerformanceCounter
0x18019b4f7  mov     eax, dword ptr [rbp+PerformanceCount]
0x18019b4fa  lea     rcx, [rbp+var_10]
0x18019b4fe  shl     rax, 20h
0x18019b502  xor     rax, qword ptr [rbp+PerformanceCount]
0x18019b506  xor     rax, [rbp+var_10]
0x18019b50a  xor     rax, rcx
0x18019b50d  mov     rcx, 0FFFFFFFFFFFFh
0x18019b517  and     rax, rcx
0x18019b51a  mov     rcx, 2B992DDFA233h
0x18019b524  cmp     rax, rbx
0x18019b527  cmovz   rax, rcx
0x18019b52b  mov     cs:__security_cookie, rax
0x18019b532  mov     rbx, [rsp+30h+arg_10]
0x18019b537  not     rax
0x18019b53a  mov     cs:__security_cookie_complement, rax
0x18019b541  add     rsp, 30h
0x18019b545  pop     rbp
0x18019b546  retn
```
