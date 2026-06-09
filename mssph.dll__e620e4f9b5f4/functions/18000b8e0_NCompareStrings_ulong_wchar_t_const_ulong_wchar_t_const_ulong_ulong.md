# NCompareStrings(ulong,wchar_t const *,ulong,wchar_t const *,ulong,ulong)

- ea: `0x18000b8e0`
- end: `0x18000b968`
- name: `?NCompareStrings@@YAHKPEB_WK0KK@Z`
- size: `136`
- prototype: `int(unsigned int, const wchar_t *, unsigned int, const wchar_t *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b860`

## callees

- `0x18000b8e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000b949`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000b949`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b924`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b924`

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
0x18000b8e0  push    rbx
0x18000b8e2  push    rbp
0x18000b8e3  push    rsi
0x18000b8e4  push    rdi
0x18000b8e5  sub     rsp, 38h
0x18000b8e9  mov     eax, [rsp+58h+cchCount1]
0x18000b8f0  mov     edi, r8d
0x18000b8f3  mov     ebx, [rsp+58h+arg_20]
0x18000b8fa  cmp     r8d, eax
0x18000b8fd  mov     rsi, r9
0x18000b900  mov     rbp, rdx
0x18000b903  cmovnb  edi, eax
0x18000b906  mov     r8, rdx; lpString1
0x18000b909  cmp     ebx, eax
0x18000b90b  mov     edx, 1; dwCmpFlags
0x18000b910  mov     ecx, 800h; Locale
0x18000b915  cmovnb  ebx, eax
0x18000b918  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x18000b91c  mov     [rsp+58h+lpString2], r9; lpString2
0x18000b921  mov     r9d, edi; cchCount1
0x18000b924  call    cs:__imp_CompareStringW
0x18000b92a  mov     ecx, eax
0x18000b92c  sub     ecx, 1
0x18000b92f  jz      short loc_18000B95C
0x18000b931  sub     ecx, 1
0x18000b934  jz      short loc_18000B958
0x18000b936  cmp     ecx, 1
0x18000b939  jz      short loc_18000B951
0x18000b93b  cmp     edi, ebx
0x18000b93d  mov     rdx, rsi
0x18000b940  mov     rcx, rbp
0x18000b943  cmovl   ebx, edi
0x18000b946  movsxd  r8, ebx
0x18000b949  call    cs:__imp__o__wcsnicmp
0x18000b94f  jmp     short loc_18000B95F
0x18000b951  mov     eax, 1
0x18000b956  jmp     short loc_18000B95F
0x18000b958  xor     eax, eax
0x18000b95a  jmp     short loc_18000B95F
0x18000b95c  or      eax, 0FFFFFFFFh
0x18000b95f  add     rsp, 38h
0x18000b963  pop     rdi
0x18000b964  pop     rsi
0x18000b965  pop     rbp
0x18000b966  pop     rbx
0x18000b967  retn
```
