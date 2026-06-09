# NtGdiRemoveFontResourceWWrapper

- ea: `0x18003a5a0`
- end: `0x18003a607`
- name: `NtGdiRemoveFontResourceWWrapper`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180038ef0`

## callees

- `0x18003a5a0`
- `0x18003a610`

## import_xrefs

- `win32u!NtGdiRemoveFontResourceW` at `0x18003a5e0`
- `win32u!NtGdiRemoveFontResourceW` at `0x18003a5e0`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x18003a5b6`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x18003a5e8`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x18003a5b6`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x18003a5e8`

## pseudocode

```c
__int64 __fastcall NtGdiRemoveFontResourceWWrapper(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  int v9; // r14d
  unsigned int v10; // ebx

  v9 = NtGdiGetPublicFontTableChangeCookie();
  v10 = NtGdiRemoveFontResourceW(a1, a2, a3, a4, a5, 0);
  if ( v9 != (unsigned int)NtGdiGetPublicFontTableChangeCookie() )
    OnUpdateSessionFonts();
  return v10;
}

```

## disassembly

```asm
0x18003a5a0  push    rbx
0x18003a5a2  push    rbp
0x18003a5a3  push    rsi
0x18003a5a4  push    rdi
0x18003a5a5  push    r14
0x18003a5a7  sub     rsp, 30h
0x18003a5ab  mov     ebx, r9d
0x18003a5ae  mov     edi, r8d
0x18003a5b1  mov     esi, edx
0x18003a5b3  mov     rbp, rcx
0x18003a5b6  call    cs:__imp_NtGdiGetPublicFontTableChangeCookie
0x18003a5bc  mov     r10d, [rsp+58h+arg_20]
0x18003a5c4  mov     r9d, ebx
0x18003a5c7  mov     r8d, edi
0x18003a5ca  mov     [rsp+58h+var_30], 0
0x18003a5d3  mov     edx, esi
0x18003a5d5  mov     [rsp+58h+var_38], r10d
0x18003a5da  mov     rcx, rbp
0x18003a5dd  mov     r14d, eax
0x18003a5e0  call    cs:__imp_NtGdiRemoveFontResourceW
0x18003a5e6  mov     ebx, eax
0x18003a5e8  call    cs:__imp_NtGdiGetPublicFontTableChangeCookie
0x18003a5ee  cmp     r14d, eax
0x18003a5f1  jnz     short loc_18003A600
0x18003a5f3  mov     eax, ebx
0x18003a5f5  add     rsp, 30h
0x18003a5f9  pop     r14
0x18003a5fb  pop     rdi
0x18003a5fc  pop     rsi
0x18003a5fd  pop     rbp
0x18003a5fe  pop     rbx
0x18003a5ff  retn
0x18003a600  call    OnUpdateSessionFonts
0x18003a605  jmp     short loc_18003A5F3
```
