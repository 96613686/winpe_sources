# SpEncryptMessage

- ea: `0x180002450`
- end: `0x180002466`
- name: `SpEncryptMessage`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002450`

## import_xrefs

- `SspiCli!EncryptMessage` at `0x18000245f`

## pseudocode

```c
SECURITY_STATUS __fastcall SpEncryptMessage(__int64 a1, unsigned int a2, struct _SecBufferDesc *a3, unsigned int a4)
{
  if ( a1 )
    return EncryptMessage(*(PCtxtHandle *)(a1 + 8), a2, a3, a4);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002450  test    rcx, rcx
0x180002453  jnz     short loc_18000245B
0x180002455  mov     eax, 80090301h
0x18000245a  retn
0x18000245b  mov     rcx, [rcx+8]
0x18000245f  jmp     cs:__imp_EncryptMessage
```
