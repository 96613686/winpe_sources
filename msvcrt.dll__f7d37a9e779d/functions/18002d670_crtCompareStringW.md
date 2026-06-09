# __crtCompareStringW

- ea: `0x18002d670`
- end: `0x18002d72f`
- name: `__crtCompareStringW`
- size: `191`
- prototype: `__int64 __fastcall(struct localeinfo_struct *, LCID Locale, DWORD dwCmpFlags, PCNZWCH lpString1, int, wchar_t *Source, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005f570`
- `0x18005f9e0`
- `0x18005fec0`
- `0x180060270`

## callees

- `0x180001038`
- `0x18002d670`
- `0x180061f40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002d6ec`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002d6ec`

## pseudocode

```c
__int64 __fastcall _crtCompareStringW(
        struct localeinfo_struct *a1,
        LCID Locale,
        DWORD dwCmpFlags,
        PCNZWCH lpString1,
        int a5,
        wchar_t *Source,
        int a7)
{
  int v10; // ebx
  int cchCount2; // edi
  unsigned int v12; // ebx
  int v13; // eax
  _BYTE v15[16]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h]
  char v17; // [rsp+48h] [rbp-40h]

  _LocaleUpdate::_LocaleUpdate((_LocaleUpdate *)v15, a1);
  v10 = a5;
  cchCount2 = a7;
  if ( a5 > 0 )
    v10 = wcsnlen(lpString1, a5);
  if ( a7 > 0 )
    cchCount2 = wcsnlen(Source, a7);
  if ( v10 && cchCount2 )
  {
    v12 = CompareStringW(Locale, dwCmpFlags, lpString1, v10, Source, cchCount2);
  }
  else
  {
    v13 = v10 - cchCount2;
    v12 = (((v10 - cchCount2) >> 31) & 0xFFFFFFFE) + 3;
    if ( !v13 )
      v12 = 2;
  }
  if ( v17 )
    *(_DWORD *)(v16 + 200) &= ~2u;
  return v12;
}

```

## disassembly

```asm
0x18002d670  push    rbx
0x18002d672  push    rbp
0x18002d673  push    rsi
0x18002d674  push    rdi
0x18002d675  push    r14
0x18002d677  push    r15
0x18002d679  sub     rsp, 58h
0x18002d67d  mov     r15d, edx
0x18002d680  mov     rbp, r9
0x18002d683  mov     rdx, rcx; struct localeinfo_struct *
0x18002d686  mov     r14d, r8d
0x18002d689  lea     rcx, [rsp+88h+var_58]; this
0x18002d68e  call    ??0_LocaleUpdate@@QEAA@PEAUlocaleinfo_struct@@@Z; _LocaleUpdate::_LocaleUpdate(localeinfo_struct *)
0x18002d693  movsxd  rbx, [rsp+88h+arg_20]
0x18002d69b  movsxd  rdi, [rsp+88h+arg_30]
0x18002d6a3  test    ebx, ebx
0x18002d6a5  jle     short loc_18002D6B5
0x18002d6a7  mov     rdx, rbx; MaxCount
0x18002d6aa  mov     rcx, rbp; Source
0x18002d6ad  call    wcsnlen
0x18002d6b2  mov     rbx, rax
0x18002d6b5  mov     rsi, [rsp+88h+Source]
0x18002d6bd  test    edi, edi
0x18002d6bf  jle     short loc_18002D6CF
0x18002d6c1  mov     rdx, rdi; MaxCount
0x18002d6c4  mov     rcx, rsi; Source
0x18002d6c7  call    wcsnlen
0x18002d6cc  mov     rdi, rax
0x18002d6cf  test    ebx, ebx
0x18002d6d1  jz      short loc_18002D6F6
0x18002d6d3  test    edi, edi
0x18002d6d5  jz      short loc_18002D6F6
0x18002d6d7  mov     [rsp+88h+cchCount2], edi; cchCount2
0x18002d6db  mov     r9d, ebx; cchCount1
0x18002d6de  mov     r8, rbp; lpString1
0x18002d6e1  mov     [rsp+88h+lpString2], rsi; lpString2
0x18002d6e6  mov     edx, r14d; dwCmpFlags
0x18002d6e9  mov     ecx, r15d; Locale
0x18002d6ec  call    cs:__imp_CompareStringW
0x18002d6f2  mov     ebx, eax
0x18002d6f4  jmp     short loc_18002D70D
0x18002d6f6  sub     ebx, edi
0x18002d6f8  mov     ecx, 2
0x18002d6fd  mov     eax, ebx
0x18002d6ff  sar     ebx, 1Fh
0x18002d702  and     ebx, 0FFFFFFFEh
0x18002d705  add     ebx, 3
0x18002d708  test    eax, eax
0x18002d70a  cmovz   ebx, ecx
0x18002d70d  cmp     [rsp+88h+var_40], 0
0x18002d712  jz      short loc_18002D720
0x18002d714  mov     rax, [rsp+88h+var_48]
0x18002d719  and     dword ptr [rax+0C8h], 0FFFFFFFDh
0x18002d720  mov     eax, ebx
0x18002d722  add     rsp, 58h
0x18002d726  pop     r15
0x18002d728  pop     r14
0x18002d72a  pop     rdi
0x18002d72b  pop     rsi
0x18002d72c  pop     rbp
0x18002d72d  pop     rbx
0x18002d72e  retn
```
