# TableCacheFind(x,x)

- ea: `0x100283fc`
- end: `0x10028423`
- name: `_TableCacheFind@8`
- size: `39`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x10028429`
- `0x10028701`
- `0x1002e5d0`

## callees

- `0x10025775`
- `0x100283fc`

## pseudocode

```c
_DWORD *__fastcall TableCacheFind(_DWORD *a1, int a2)
{
  while ( 1 )
  {
    if ( !a1 )
      return 0;
    if ( !DBlstrcmpi((int)(a1 + 3), a2) )
      break;
    a1 = (_DWORD *)*a1;
  }
  return a1;
}

```

## disassembly

```asm
0x100283fc  mov     edi, edi
0x100283fe  push    esi
0x100283ff  push    edi
0x10028400  mov     edi, edx
0x10028402  mov     esi, ecx
0x10028404  jmp     short loc_10028416
0x10028406  lea     ecx, [esi+0Ch]
0x10028409  mov     edx, edi
0x1002840b  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x10028410  test    eax, eax
0x10028412  jz      short loc_1002841F
0x10028414  mov     esi, [esi]
0x10028416  test    esi, esi
0x10028418  jnz     short loc_10028406
0x1002841a  xor     eax, eax
0x1002841c  pop     edi
0x1002841d  pop     esi
0x1002841e  retn
0x1002841f  mov     eax, esi
0x10028421  jmp     short loc_1002841C
```
