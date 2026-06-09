# W3_RESPONSE::SetVaryByValue(char const *)

- ea: `0x180028220`
- end: `0x18002823a`
- name: `?SetVaryByValue@W3_RESPONSE@@UEAAJPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(W3_RESPONSE *__hidden this, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180028220`

## import_xrefs

- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180028233`

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
0x180028220  test    rdx, rdx
0x180028223  jnz     short loc_18002822C
0x180028225  mov     eax, 80070057h
0x18002822a  retn
0x18002822c  add     rcx, 540h
0x180028233  jmp     cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
```
