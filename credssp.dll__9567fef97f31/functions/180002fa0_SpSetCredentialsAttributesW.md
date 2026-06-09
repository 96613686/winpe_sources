# SpSetCredentialsAttributesW

- ea: `0x180002fa0`
- end: `0x180002fba`
- name: `SpSetCredentialsAttributesW`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002fa0`

## import_xrefs

- `SspiCli!SetCredentialsAttributesW` at `0x180002fb3`

## pseudocode

```c
SECURITY_STATUS __fastcall SpSetCredentialsAttributesW(__int64 a1, unsigned int a2, void *a3, unsigned int a4)
{
  if ( a1 )
    return SetCredentialsAttributesW((PCredHandle)(*(_QWORD *)(a1 + 8) + 16LL), a2, a3, a4);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002fa0  test    rcx, rcx
0x180002fa3  jnz     short loc_180002FAB
0x180002fa5  mov     eax, 80090301h
0x180002faa  retn
0x180002fab  mov     rcx, [rcx+8]
0x180002faf  add     rcx, 10h
0x180002fb3  jmp     cs:__imp_SetCredentialsAttributesW
```
