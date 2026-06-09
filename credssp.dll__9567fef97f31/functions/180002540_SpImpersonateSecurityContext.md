# SpImpersonateSecurityContext

- ea: `0x180002540`
- end: `0x18000255a`
- name: `SpImpersonateSecurityContext`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002540`

## import_xrefs

- `SspiCli!ImpersonateSecurityContext` at `0x180002553`

## pseudocode

```c
SECURITY_STATUS __fastcall SpImpersonateSecurityContext(__int64 a1)
{
  if ( a1 )
    return ImpersonateSecurityContext((PCtxtHandle)(*(_QWORD *)(a1 + 8) + 16LL));
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002540  test    rcx, rcx
0x180002543  jnz     short loc_18000254B
0x180002545  mov     eax, 80090301h
0x18000254a  retn
0x18000254b  mov     rcx, [rcx+8]
0x18000254f  add     rcx, 10h
0x180002553  jmp     cs:__imp_ImpersonateSecurityContext
```
