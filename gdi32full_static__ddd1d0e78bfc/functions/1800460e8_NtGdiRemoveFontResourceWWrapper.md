# NtGdiRemoveFontResourceWWrapper

- ea: `0x1800460e8`
- end: `0x180046162`
- name: `NtGdiRemoveFontResourceWWrapper`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180044900`

## callees

- `0x1800460e8`
- `0x180046168`

## import_xrefs

- `win32u!NtGdiRemoveFontResourceW` at `0x18004612e`
- `win32u!NtGdiRemoveFontResourceW` at `0x18004612e`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x1800460fe`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x18004613c`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x1800460fe`
- `win32u!NtGdiGetPublicFontTableChangeCookie` at `0x18004613c`

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
0x1800460e8  push    rbx
0x1800460ea  push    rbp
0x1800460eb  push    rsi
0x1800460ec  push    rdi
0x1800460ed  push    r14
0x1800460ef  sub     rsp, 30h
0x1800460f3  mov     ebx, r9d
0x1800460f6  mov     edi, r8d
0x1800460f9  mov     esi, edx
0x1800460fb  mov     rbp, rcx
0x1800460fe  call    cs:__imp_NtGdiGetPublicFontTableChangeCookie
0x180046105  nop     dword ptr [rax+rax+00h]
0x18004610a  mov     r10d, [rsp+58h+arg_20]
0x180046112  mov     r9d, ebx
0x180046115  mov     r8d, edi
0x180046118  mov     [rsp+58h+var_30], 0
0x180046121  mov     edx, esi
0x180046123  mov     [rsp+58h+var_38], r10d
0x180046128  mov     rcx, rbp
0x18004612b  mov     r14d, eax
0x18004612e  call    cs:__imp_NtGdiRemoveFontResourceW
0x180046135  nop     dword ptr [rax+rax+00h]
0x18004613a  mov     ebx, eax
0x18004613c  call    cs:__imp_NtGdiGetPublicFontTableChangeCookie
0x180046143  nop     dword ptr [rax+rax+00h]
0x180046148  cmp     r14d, eax
0x18004614b  jnz     short loc_18004615B
0x18004614d  mov     eax, ebx
0x18004614f  add     rsp, 30h
0x180046153  pop     r14
0x180046155  pop     rdi
0x180046156  pop     rsi
0x180046157  pop     rbp
0x180046158  pop     rbx
0x180046159  retn
0x18004615b  call    OnUpdateSessionFonts
0x180046160  jmp     short loc_18004614D
```
