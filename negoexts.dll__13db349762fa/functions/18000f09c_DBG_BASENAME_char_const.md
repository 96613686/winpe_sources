# _DBG_BASENAME(char const *)

- ea: `0x18000f09c`
- end: `0x18000f0c2`
- name: `?_DBG_BASENAME@@YAPEBDPEBD@Z`
- size: `38`
- prototype: `const char *__fastcall(const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ec9c`
- `0x18001e2b4`
- `0x18001e5f0`

## callees

- `0x18000f09c`

## string_xrefs

- `0x18000f0ae`: `onecore\ds\security\protocols\basessp\scardbuffer.cxx`

## pseudocode

```c
char *__fastcall _DBG_BASENAME(const char *a1)
{
  char *result; // rax
  const char *v2; // rcx
  bool v3; // zf

  result = "";
  while ( 1 )
  {
    v2 = result--;
    v3 = *result == 92;
    if ( *result == 92 )
      break;
    if ( result <= "onecore\\ds\\security\\protocols\\basessp\\scardbuffer.cxx" )
    {
      v3 = *result == 92;
      break;
    }
  }
  if ( v3 )
    return (char *)v2;
  return result;
}

```

## disassembly

```asm
0x18000f09c  lea     rax, aOnecoreDsSecur_2+35h; ""
0x18000f0a3  mov     rcx, rax
0x18000f0a6  dec     rax
0x18000f0a9  cmp     byte ptr [rax], 5Ch ; '\'
0x18000f0ac  jz      short loc_18000F0BD
0x18000f0ae  lea     rdx, aOnecoreDsSecur_2; "onecore\\ds\\security\\protocols\\bases"...
0x18000f0b5  cmp     rax, rdx
0x18000f0b8  ja      short loc_18000F0A3
0x18000f0ba  cmp     byte ptr [rax], 5Ch ; '\'
0x18000f0bd  cmovz   rax, rcx
0x18000f0c1  retn
```
