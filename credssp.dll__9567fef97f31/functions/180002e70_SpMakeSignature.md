# SpMakeSignature

- ea: `0x180002e70`
- end: `0x180002e86`
- name: `SpMakeSignature`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e70`

## import_xrefs

- `SspiCli!MakeSignature` at `0x180002e7f`

## pseudocode

```c
SECURITY_STATUS __fastcall SpMakeSignature(__int64 a1, unsigned int a2, struct _SecBufferDesc *a3, unsigned int a4)
{
  if ( a1 )
    return MakeSignature(*(PCtxtHandle *)(a1 + 8), a2, a3, a4);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002e70  test    rcx, rcx
0x180002e73  jnz     short loc_180002E7B
0x180002e75  mov     eax, 80090301h
0x180002e7a  retn
0x180002e7b  mov     rcx, [rcx+8]
0x180002e7f  jmp     cs:__imp_MakeSignature
```
