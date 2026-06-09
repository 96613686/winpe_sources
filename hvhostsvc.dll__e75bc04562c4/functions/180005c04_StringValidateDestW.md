# StringValidateDestW

- ea: `0x180005c04`
- end: `0x180005c1a`
- name: `StringValidateDestW`
- size: `22`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH pszDest, size_t cchDest, const size_t cchMax)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004368`
- `0x180005a48`
- `0x180005a80`
- `0x180005acc`

## callees

- `0x180005c04`

## pseudocode

```c
HRESULT __stdcall StringValidateDestW(STRSAFE_PCNZWCH pszDest, size_t cchDest, const size_t cchMax)
{
  HRESULT result; // eax

  if ( !cchDest )
    return -2147024809;
  result = 0;
  if ( cchDest > 0x7FFFFFFF )
    return -2147024809;
  return result;
}

```

## disassembly

```asm
0x180005c04  test    rdx, rdx
0x180005c07  jz      short loc_180005C14
0x180005c09  xor     eax, eax
0x180005c0b  cmp     rdx, 7FFFFFFFh
0x180005c12  jbe     short locret_180005C19
0x180005c14  mov     eax, 80070057h
0x180005c19  retn
```
