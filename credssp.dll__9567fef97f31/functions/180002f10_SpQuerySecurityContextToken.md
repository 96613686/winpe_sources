# SpQuerySecurityContextToken

- ea: `0x180002f10`
- end: `0x180002f2a`
- name: `SpQuerySecurityContextToken`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f10`

## import_xrefs

- `SspiCli!QuerySecurityContextToken` at `0x180002f23`

## pseudocode

```c
SECURITY_STATUS __fastcall SpQuerySecurityContextToken(__int64 a1, void **a2)
{
  if ( a1 )
    return QuerySecurityContextToken((PCtxtHandle)(*(_QWORD *)(a1 + 8) + 16LL), a2);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002f10  test    rcx, rcx
0x180002f13  jnz     short loc_180002F1B
0x180002f15  mov     eax, 80090301h
0x180002f1a  retn
0x180002f1b  mov     rcx, [rcx+8]
0x180002f1f  add     rcx, 10h
0x180002f23  jmp     cs:__imp_QuerySecurityContextToken
```
