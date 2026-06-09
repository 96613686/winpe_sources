# ___security_init_cookie

- ea: `0x10034b0e`
- end: `0x10034baa`
- name: `___security_init_cookie`
- size: `156`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1002e361`

## callees

- `0x10034b0e`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x10034b5a`
- `KERNEL32!GetCurrentProcessId` at `0x10034b5a`
- `KERNEL32!GetCurrentThreadId` at `0x10034b51`
- `KERNEL32!GetCurrentThreadId` at `0x10034b51`
- `KERNEL32!QueryPerformanceCounter` at `0x10034b67`
- `KERNEL32!QueryPerformanceCounter` at `0x10034b67`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10034b42`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10034b42`

## pseudocode

```c
void __cdecl __security_init_cookie()
{
  uintptr_t v0; // ecx
  LARGE_INTEGER PerformanceCount; // [esp+8h] [ebp-14h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [esp+10h] [ebp-Ch] BYREF
  DWORD v3; // [esp+18h] [ebp-4h] BYREF

  SystemTimeAsFileTime.dwLowDateTime = 0;
  SystemTimeAsFileTime.dwHighDateTime = 0;
  if ( __security_cookie == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v3 = SystemTimeAsFileTime.dwLowDateTime ^ SystemTimeAsFileTime.dwHighDateTime;
    v3 ^= GetCurrentThreadId();
    v3 ^= GetCurrentProcessId();
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (unsigned int)&v3 ^ v3 ^ PerformanceCount.LowPart ^ PerformanceCount.HighPart;
    if ( v0 == -1153374642 )
    {
      v0 = -1153374641;
    }
    else if ( (v0 & 0xFFFF0000) == 0 )
    {
      v0 |= (v0 | 0x4711) << 16;
    }
    __security_cookie = v0;
    __security_cookie_complement = ~v0;
  }
  else
  {
    __security_cookie_complement = ~__security_cookie;
  }
}

```

## disassembly

```asm
0x10034b0e  push    ebp
0x10034b0f  mov     ebp, esp
0x10034b11  sub     esp, 14h
0x10034b14  and     [ebp+SystemTimeAsFileTime.dwLowDateTime], 0
0x10034b18  and     [ebp+SystemTimeAsFileTime.dwHighDateTime], 0
0x10034b1c  mov     eax, ___security_cookie
0x10034b21  push    esi
0x10034b22  push    edi
0x10034b23  mov     edi, 0BB40E64Eh
0x10034b28  mov     esi, 0FFFF0000h
0x10034b2d  cmp     eax, edi
0x10034b2f  jz      short loc_10034B3E
0x10034b31  test    esi, eax
0x10034b33  jz      short loc_10034B3E
0x10034b35  not     eax
0x10034b37  mov     ___security_cookie_complement, eax
0x10034b3c  jmp     short loc_10034BA4
0x10034b3e  lea     eax, [ebp+SystemTimeAsFileTime]
0x10034b41  push    eax; lpSystemTimeAsFileTime
0x10034b42  call    ds:__imp__GetSystemTimeAsFileTime@4
0x10034b48  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x10034b4b  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x10034b4e  mov     [ebp+var_4], eax
0x10034b51  call    ds:__imp__GetCurrentThreadId@0
0x10034b57  xor     [ebp+var_4], eax
0x10034b5a  call    ds:__imp__GetCurrentProcessId@0
0x10034b60  xor     [ebp+var_4], eax
0x10034b63  lea     eax, [ebp+PerformanceCount]
0x10034b66  push    eax; lpPerformanceCount
0x10034b67  call    ds:__imp__QueryPerformanceCounter@4
0x10034b6d  mov     ecx, dword ptr [ebp+PerformanceCount+4]
0x10034b70  lea     eax, [ebp+var_4]
0x10034b73  xor     ecx, dword ptr [ebp+PerformanceCount]
0x10034b76  xor     ecx, [ebp+var_4]
0x10034b79  xor     ecx, eax
0x10034b7b  cmp     ecx, edi
0x10034b7d  jnz     short loc_10034B86
0x10034b7f  mov     ecx, 0BB40E64Fh
0x10034b84  jmp     short loc_10034B96
0x10034b86  test    esi, ecx
0x10034b88  jnz     short loc_10034B96
0x10034b8a  mov     eax, ecx
0x10034b8c  or      eax, 4711h
0x10034b91  shl     eax, 10h
0x10034b94  or      ecx, eax
0x10034b96  mov     ___security_cookie, ecx
0x10034b9c  not     ecx
0x10034b9e  mov     ___security_cookie_complement, ecx
0x10034ba4  pop     edi
0x10034ba5  pop     esi
0x10034ba6  mov     esp, ebp
0x10034ba8  pop     ebp
0x10034ba9  retn
```
