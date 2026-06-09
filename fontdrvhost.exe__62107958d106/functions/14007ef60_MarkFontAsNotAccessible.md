# MarkFontAsNotAccessible

- ea: `0x14007ef60`
- end: `0x14007ef7f`
- name: `MarkFontAsNotAccessible`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14003af80`
- `0x14003f300`
- `0x1400527d0`
- `0x140052930`
- `0x140060a50`
- `0x140066130`

## callees

- `0x14007ef60`

## pseudocode

```c
void __fastcall MarkFontAsNotAccessible(__int64 a1)
{
  __int64 v1; // rax

  if ( (_BYTE)word_1400B6270 && a1 )
  {
    v1 = *(_QWORD *)(a1 + 24);
    if ( v1 )
      *(_BYTE *)(v1 + 355) |= 1u;
  }
}

```

## disassembly

```asm
0x14007ef60  cmp     byte ptr cs:word_1400B6270, 0
0x14007ef67  jz      short locret_14007EF7E
0x14007ef69  test    rcx, rcx
0x14007ef6c  jz      short locret_14007EF7E
0x14007ef6e  mov     rax, [rcx+18h]
0x14007ef72  test    rax, rax
0x14007ef75  jz      short locret_14007EF7E
0x14007ef77  or      byte ptr [rax+163h], 1
0x14007ef7e  retn
0x140097679  push    rbp
0x14009767b  mov     rbp, rdx
0x14009767e  pop     rbp
0x14009767f  retn
```
