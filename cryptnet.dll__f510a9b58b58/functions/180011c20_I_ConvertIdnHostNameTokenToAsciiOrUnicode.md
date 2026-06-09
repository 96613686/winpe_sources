# I_ConvertIdnHostNameTokenToAsciiOrUnicode

- ea: `0x180011c20`
- end: `0x180011cbe`
- name: `I_ConvertIdnHostNameTokenToAsciiOrUnicode`
- size: `158`
- prototype: `__int64 __fastcall(int, const WCHAR *, WCHAR **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800119b8`
- `0x180011cc4`

## callees

- `0x180005980`
- `0x18000a990`
- `0x180011c20`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180011c67`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180011c96`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180011c67`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180011c96`
- `api-ms-win-core-localization-l1-2-0!IdnToUnicode` at `0x180011c46`
- `api-ms-win-core-localization-l1-2-0!IdnToUnicode` at `0x180011caa`
- `api-ms-win-core-localization-l1-2-0!IdnToUnicode` at `0x180011c46`
- `api-ms-win-core-localization-l1-2-0!IdnToUnicode` at `0x180011caa`

## pseudocode

```c
__int64 __fastcall I_ConvertIdnHostNameTokenToAsciiOrUnicode(int a1, const WCHAR *a2, WCHAR **a3)
{
  WCHAR *v3; // rbx
  unsigned int v7; // eax
  int cchUnicodeChar; // edi
  __int64 result; // rax
  WCHAR *v10; // rax
  int v11; // eax

  v3 = 0;
  if ( a1 )
    v7 = IdnToAscii(0, a2, -1, 0, 0);
  else
    v7 = IdnToUnicode(0, a2, -1, 0, 0);
  cchUnicodeChar = v7;
  if ( v7
    && (v10 = (WCHAR *)PkiZeroAlloc(2LL * v7), (v3 = v10) != 0)
    && (!a1 ? (v11 = IdnToUnicode(0, a2, -1, v10, cchUnicodeChar)) : (v11 = IdnToAscii(0, a2, -1, v10, cchUnicodeChar)),
        v11) )
  {
    *a3 = v3;
    return 1;
  }
  else
  {
    result = 0;
    if ( v3 )
    {
      operator delete(v3);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011c20  push    rbx
0x180011c22  push    rsi
0x180011c23  push    rdi
0x180011c24  push    r14
0x180011c26  push    r15
0x180011c28  sub     rsp, 30h
0x180011c2c  xor     ebx, ebx
0x180011c2e  mov     r15, r8
0x180011c31  or      r8d, 0FFFFFFFFh; cchUnicodeChar
0x180011c35  mov     [rsp+58h+cchUnicodeChar], ebx; cchASCIIChar
0x180011c39  xor     r9d, r9d; lpASCIICharStr
0x180011c3c  mov     rsi, rdx
0x180011c3f  mov     r14d, ecx
0x180011c42  test    ecx, ecx
0x180011c44  jnz     short loc_180011C65
0x180011c46  call    cs:__imp_IdnToUnicode
0x180011c4c  mov     edi, eax
0x180011c4e  test    eax, eax
0x180011c50  jnz     short loc_180011C6F
0x180011c52  xor     eax, eax
0x180011c54  test    rbx, rbx
0x180011c57  jnz     short loc_180011CB2
0x180011c59  add     rsp, 30h
0x180011c5d  pop     r15
0x180011c5f  pop     r14
0x180011c61  pop     rdi
0x180011c62  pop     rsi
0x180011c63  pop     rbx
0x180011c64  retn
0x180011c65  xor     ecx, ecx; dwFlags
0x180011c67  call    cs:__imp_IdnToAscii
0x180011c6d  jmp     short loc_180011C4C
0x180011c6f  mov     ecx, edi
0x180011c71  add     rcx, rcx; uBytes
0x180011c74  call    PkiZeroAlloc
0x180011c79  mov     rbx, rax
0x180011c7c  test    rax, rax
0x180011c7f  jz      short loc_180011C52
0x180011c81  or      r8d, 0FFFFFFFFh; cchASCIIChar
0x180011c85  mov     [rsp+58h+cchUnicodeChar], edi; cchUnicodeChar
0x180011c89  xor     ecx, ecx; dwFlags
0x180011c8b  mov     r9, rax; lpUnicodeCharStr
0x180011c8e  mov     rdx, rsi; lpASCIICharStr
0x180011c91  test    r14d, r14d
0x180011c94  jz      short loc_180011CAA
0x180011c96  call    cs:__imp_IdnToAscii
0x180011c9c  test    eax, eax
0x180011c9e  jz      short loc_180011C52
0x180011ca0  mov     [r15], rbx
0x180011ca3  mov     eax, 1
0x180011ca8  jmp     short loc_180011C59
0x180011caa  call    cs:__imp_IdnToUnicode
0x180011cb0  jmp     short loc_180011C9C
0x180011cb2  mov     rcx, rbx; hMem
0x180011cb5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011cba  xor     eax, eax
0x180011cbc  jmp     short loc_180011C59
```
