# PmpUuidCreate(_GUID *)

- ea: `0x18000ec00`
- end: `0x18000ec1c`
- name: `?PmpUuidCreate@@YAKPEAU_GUID@@@Z`
- size: `28`
- prototype: `RPC_STATUS __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c4d4`
- `0x18000e6a8`
- `0x18000e948`

## callees

- `0x18000ec00`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000ec04`
- `RPCRT4!UuidCreate` at `0x18000ec04`

## pseudocode

```c
RPC_STATUS __fastcall PmpUuidCreate(struct _GUID *a1)
{
  RPC_STATUS result; // eax

  result = UuidCreate(a1);
  if ( !result || result == 1824 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000ec00  sub     rsp, 28h
0x18000ec04  call    cs:__imp_UuidCreate
0x18000ec0a  test    eax, eax
0x18000ec0c  jz      short loc_18000EC15
0x18000ec0e  cmp     eax, 720h
0x18000ec13  jnz     short loc_18000EC17
0x18000ec15  xor     eax, eax
0x18000ec17  add     rsp, 28h
0x18000ec1b  retn
```
