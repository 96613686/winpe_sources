# NCompareStrings(ulong,wchar_t const *,ulong,wchar_t const *,ulong,ulong)

- ea: `0x180037b78`
- end: `0x180037c00`
- name: `?NCompareStrings@@YAHKPEB_WK0KK@Z`
- size: `136`
- prototype: `int(unsigned int, const wchar_t *, unsigned int, const wchar_t *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180037878`

## callees

- `0x180037b78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180037be1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180037be1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037bbc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037bbc`

## pseudocode

```c
__int64 __fastcall NCompareStrings(
        __int64 a1,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *lpString2,
        unsigned int a5,
        unsigned int cchCount1)
{
  int v6; // edi
  int cchCount2; // ebx
  int v10; // eax

  v6 = a3;
  cchCount2 = a5;
  if ( a3 >= cchCount1 )
    v6 = cchCount1;
  if ( a5 >= cchCount1 )
    cchCount2 = cchCount1;
  v10 = CompareStringW(0x800u, 1u, a2, v6, lpString2, cchCount2);
  switch ( v10 )
  {
    case 1:
      return 0xFFFFFFFFLL;
    case 2:
      return 0;
    case 3:
      return 1;
  }
  if ( v6 < cchCount2 )
    cchCount2 = v6;
  return _o__wcsnicmp(a2, lpString2, cchCount2);
}

```

## disassembly

```asm
0x180037b78  push    rbx
0x180037b7a  push    rbp
0x180037b7b  push    rsi
0x180037b7c  push    rdi
0x180037b7d  sub     rsp, 38h
0x180037b81  mov     eax, [rsp+58h+cchCount1]
0x180037b88  mov     edi, r8d
0x180037b8b  mov     ebx, [rsp+58h+arg_20]
0x180037b92  cmp     r8d, eax
0x180037b95  mov     rsi, r9
0x180037b98  mov     rbp, rdx
0x180037b9b  cmovnb  edi, eax
0x180037b9e  mov     r8, rdx; lpString1
0x180037ba1  cmp     ebx, eax
0x180037ba3  mov     edx, 1; dwCmpFlags
0x180037ba8  mov     ecx, 800h; Locale
0x180037bad  cmovnb  ebx, eax
0x180037bb0  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x180037bb4  mov     [rsp+58h+lpString2], r9; lpString2
0x180037bb9  mov     r9d, edi; cchCount1
0x180037bbc  call    cs:__imp_CompareStringW
0x180037bc2  mov     ecx, eax
0x180037bc4  sub     ecx, 1
0x180037bc7  jz      short loc_180037BF4
0x180037bc9  sub     ecx, 1
0x180037bcc  jz      short loc_180037BF0
0x180037bce  cmp     ecx, 1
0x180037bd1  jz      short loc_180037BE9
0x180037bd3  cmp     edi, ebx
0x180037bd5  mov     rdx, rsi
0x180037bd8  mov     rcx, rbp
0x180037bdb  cmovl   ebx, edi
0x180037bde  movsxd  r8, ebx
0x180037be1  call    cs:__imp__o__wcsnicmp
0x180037be7  jmp     short loc_180037BF7
0x180037be9  mov     eax, 1
0x180037bee  jmp     short loc_180037BF7
0x180037bf0  xor     eax, eax
0x180037bf2  jmp     short loc_180037BF7
0x180037bf4  or      eax, 0FFFFFFFFh
0x180037bf7  add     rsp, 38h
0x180037bfb  pop     rdi
0x180037bfc  pop     rsi
0x180037bfd  pop     rbp
0x180037bfe  pop     rbx
0x180037bff  retn
```
