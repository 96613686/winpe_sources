# IntlStrEqWorkerW

- ea: `0x18003a5d4`
- end: `0x18003a6b2`
- name: `IntlStrEqWorkerW`
- size: `222`
- prototype: `BOOL __stdcall(BOOL fCaseSens, LPCWSTR lpString1, LPCWSTR lpString2, int nChar)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005185c`
- `0x180069d54`
- `0x18006a0c4`

## callees

- `0x18003a5d4`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18003a5ec`
- `KERNEL32!GetThreadLocale` at `0x18003a64a`
- `KERNEL32!GetThreadLocale` at `0x18003a5ec`
- `KERNEL32!GetThreadLocale` at `0x18003a64a`
- `KERNEL32!CompareStringW` at `0x18003a608`
- `KERNEL32!CompareStringW` at `0x18003a634`
- `KERNEL32!CompareStringW` at `0x18003a666`
- `KERNEL32!CompareStringW` at `0x18003a68b`
- `KERNEL32!CompareStringW` at `0x18003a608`
- `KERNEL32!CompareStringW` at `0x18003a634`
- `KERNEL32!CompareStringW` at `0x18003a666`
- `KERNEL32!CompareStringW` at `0x18003a68b`
- `KERNEL32!GetSystemDefaultLCID` at `0x18003a618`
- `KERNEL32!GetSystemDefaultLCID` at `0x18003a618`

## pseudocode

```c
BOOL __stdcall IntlStrEqWorkerW(BOOL fCaseSens, LPCWSTR lpString1, LPCWSTR lpString2, int nChar)
{
  LCID ThreadLocale; // eax
  int v8; // ecx
  LCID SystemDefaultLCID; // eax
  LCID v10; // eax

  ThreadLocale = GetThreadLocale();
  v8 = CompareStringW(ThreadLocale, 0x10000001u, lpString1, nChar, lpString2, nChar);
  if ( !v8 )
  {
    SystemDefaultLCID = GetSystemDefaultLCID();
    v8 = CompareStringW(SystemDefaultLCID, 0x10000001u, lpString1, nChar, lpString2, nChar);
    if ( !v8 )
    {
      if ( lpString1 && lpString2 )
      {
        v10 = GetThreadLocale();
        v8 = CompareStringW(v10, 0x10000001u, lpString1, nChar, lpString2, nChar);
        if ( !v8 )
          v8 = CompareStringW(0x800u, 0x10000001u, lpString1, nChar, lpString2, nChar);
      }
      else
      {
        v8 = 2;
      }
    }
  }
  return v8 == 2;
}

```

## disassembly

```asm
0x18003a5d4  mov     [rsp+arg_0], rbx
0x18003a5d9  mov     [rsp+arg_8], rsi
0x18003a5de  push    rdi
0x18003a5df  sub     rsp, 30h
0x18003a5e3  mov     ebx, r9d
0x18003a5e6  mov     rdi, r8
0x18003a5e9  mov     rsi, rdx
0x18003a5ec  call    cs:__imp_GetThreadLocale
0x18003a5f2  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18003a5f6  mov     r9d, ebx; cchCount1
0x18003a5f9  mov     ecx, eax; Locale
0x18003a5fb  mov     [rsp+38h+lpString2], rdi; lpString2
0x18003a600  mov     r8, rsi; lpString1
0x18003a603  mov     edx, 10000001h; dwCmpFlags
0x18003a608  call    cs:__imp_CompareStringW
0x18003a60e  mov     ecx, eax
0x18003a610  test    eax, eax
0x18003a612  jnz     loc_18003A69A
0x18003a618  call    cs:__imp_GetSystemDefaultLCID
0x18003a61e  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18003a622  mov     r9d, ebx; cchCount1
0x18003a625  mov     ecx, eax; Locale
0x18003a627  mov     [rsp+38h+lpString2], rdi; lpString2
0x18003a62c  mov     r8, rsi; lpString1
0x18003a62f  mov     edx, 10000001h; dwCmpFlags
0x18003a634  call    cs:__imp_CompareStringW
0x18003a63a  mov     ecx, eax
0x18003a63c  test    eax, eax
0x18003a63e  jnz     short loc_18003A69A
0x18003a640  test    rsi, rsi
0x18003a643  jz      short loc_18003A695
0x18003a645  test    rdi, rdi
0x18003a648  jz      short loc_18003A695
0x18003a64a  call    cs:__imp_GetThreadLocale
0x18003a650  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18003a654  mov     r9d, ebx; cchCount1
0x18003a657  mov     ecx, eax; Locale
0x18003a659  mov     [rsp+38h+lpString2], rdi; lpString2
0x18003a65e  mov     r8, rsi; lpString1
0x18003a661  mov     edx, 10000001h; dwCmpFlags
0x18003a666  call    cs:__imp_CompareStringW
0x18003a66c  mov     ecx, eax
0x18003a66e  test    eax, eax
0x18003a670  jnz     short loc_18003A69A
0x18003a672  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18003a676  mov     r9d, ebx; cchCount1
0x18003a679  mov     r8, rsi; lpString1
0x18003a67c  mov     [rsp+38h+lpString2], rdi; lpString2
0x18003a681  mov     edx, 10000001h; dwCmpFlags
0x18003a686  mov     ecx, 800h; Locale
0x18003a68b  call    cs:__imp_CompareStringW
0x18003a691  mov     ecx, eax
0x18003a693  jmp     short loc_18003A69A
0x18003a695  mov     ecx, 2
0x18003a69a  mov     rbx, [rsp+38h+arg_0]
0x18003a69f  xor     eax, eax
0x18003a6a1  mov     rsi, [rsp+38h+arg_8]
0x18003a6a6  cmp     ecx, 2
0x18003a6a9  setz    al
0x18003a6ac  add     rsp, 30h
0x18003a6b0  pop     rdi
0x18003a6b1  retn
```
