# SpDecryptMessage

- ea: `0x180002360`
- end: `0x180002376`
- name: `SpDecryptMessage`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002360`

## import_xrefs

- `SspiCli!DecryptMessage` at `0x18000236f`

## pseudocode

```c
SECURITY_STATUS __fastcall SpDecryptMessage(__int64 a1, struct _SecBufferDesc *a2, unsigned int a3, unsigned int *a4)
{
  if ( a1 )
    return DecryptMessage(*(PCtxtHandle *)(a1 + 8), a2, a3, a4);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002360  test    rcx, rcx
0x180002363  jnz     short loc_18000236B
0x180002365  mov     eax, 80090301h
0x18000236a  retn
0x18000236b  mov     rcx, [rcx+8]
0x18000236f  jmp     cs:__imp_DecryptMessage
```
