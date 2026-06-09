# SpApplyControlToken

- ea: `0x180002340`
- end: `0x180002356`
- name: `SpApplyControlToken`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002340`

## import_xrefs

- `SspiCli!ApplyControlToken` at `0x18000234f`

## pseudocode

```c
SECURITY_STATUS __fastcall SpApplyControlToken(__int64 a1, struct _SecBufferDesc *a2)
{
  if ( a1 )
    return ApplyControlToken(*(PCtxtHandle *)(a1 + 8), a2);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180002340  test    rcx, rcx
0x180002343  jnz     short loc_18000234B
0x180002345  mov     eax, 80090301h
0x18000234a  retn
0x18000234b  mov     rcx, [rcx+8]
0x18000234f  jmp     cs:__imp_ApplyControlToken
```
