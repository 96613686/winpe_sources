# SpVerifySignature

- ea: `0x180002fc0`
- end: `0x180002fd6`
- name: `SpVerifySignature`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002fc0`

## import_xrefs

- `SspiCli!VerifySignature` at `0x180002fcf`

## pseudocode

```c
SECURITY_STATUS __fastcall SpVerifySignature(__int64 a1, struct _SecBufferDesc *a2, unsigned int a3, unsigned int *a4)
{
  if ( a1 )
    return VerifySignature(*(PCtxtHandle *)(a1 + 8), a2, a3, a4);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002fc0  test    rcx, rcx
0x180002fc3  jnz     short loc_180002FCB
0x180002fc5  mov     eax, 80090301h
0x180002fca  retn
0x180002fcb  mov     rcx, [rcx+8]
0x180002fcf  jmp     cs:__imp_VerifySignature
```
