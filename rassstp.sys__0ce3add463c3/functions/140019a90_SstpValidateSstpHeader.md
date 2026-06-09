# SstpValidateSstpHeader

- ea: `0x140019a90`
- end: `0x140019ad4`
- name: `SstpValidateSstpHeader`
- size: `68`
- prototype: `_BOOL8 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400015b0`
- `0x140018698`

## callees

- `0x140019a90`

## pseudocode

```c
_BOOL8 __fastcall SstpValidateSstpHeader(__int64 a1, char a2)
{
  __int16 v2; // r8

  v2 = __ROR2__(*(_WORD *)(a1 + 2), 8);
  if ( *(_BYTE *)a1 == 16 )
  {
    if ( (*(_BYTE *)(a1 + 1) & 1) != 0 )
    {
      if ( a2 )
        return (v2 & 0xFFFu) > 4;
    }
    else if ( !a2 )
    {
      return (v2 & 0xFFFu) > 4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140019a90  movzx   r8d, word ptr [rcx+2]
0x140019a95  xor     r9b, r9b
0x140019a98  ror     r8w, 8
0x140019a9d  cmp     byte ptr [rcx], 10h
0x140019aa0  jnz     short loc_140019AC8
0x140019aa2  test    byte ptr [rcx+1], 1
0x140019aa6  jnz     short loc_140019ACE
0x140019aa8  test    dl, dl
0x140019aaa  jnz     short loc_140019AC8
0x140019aac  mov     eax, 0FFFh
0x140019ab1  mov     ecx, 1
0x140019ab6  and     r8w, ax
0x140019aba  movzx   eax, r9b
0x140019abe  cmp     r8w, 4
0x140019ac3  cmova   eax, ecx
0x140019ac6  retn
0x140019ac8  movzx   eax, r9b
0x140019acc  retn
0x140019ace  test    dl, dl
0x140019ad0  jnz     short loc_140019AAC
0x140019ad2  jmp     short loc_140019AC8
```
