# W3_RESPONSE::SetVaryByValue(char const *)

- ea: `0x180026200`
- end: `0x180026219`
- name: `?SetVaryByValue@W3_RESPONSE@@UEAAJPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(W3_RESPONSE *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180026200`

## import_xrefs

- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180026212`

## pseudocode

```c
int __fastcall W3_RESPONSE::SetVaryByValue(W3_RESPONSE *this, const char *a2)
{
  if ( a2 )
    return STRA::Copy((W3_RESPONSE *)((char *)this + 1344), a2);
  else
    return -2147024809;
}

```

## disassembly

```asm
0x180026200  test    rdx, rdx
0x180026203  jnz     short loc_18002620B
0x180026205  mov     eax, 80070057h
0x18002620a  retn
0x18002620b  add     rcx, 540h
0x180026212  jmp     cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
```
