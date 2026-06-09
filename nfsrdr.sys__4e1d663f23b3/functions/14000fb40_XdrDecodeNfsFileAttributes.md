# XdrDecodeNfsFileAttributes

- ea: `0x14000fb40`
- end: `0x14000fb5b`
- name: `XdrDecodeNfsFileAttributes`
- size: `27`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000d4cc`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011984`
- `0x1400124ec`
- `0x140012c40`
- `0x1400132cc`
- `0x14002a5f0`
- `0x14002a9e0`
- `0x14002b138`

## callees

- `0x14000fb40`
- `0x14002b82c`
- `0x14002b8f8`

## pseudocode

```c
__int64 __fastcall XdrDecodeNfsFileAttributes(__int64 a1, __int64 a2, char a3)
{
  if ( a3 )
    return XdrDecodeNfs3FattrIntoNfsFileAttributes();
  else
    return XdrDecodeNfs2FattrIntoNfsFileAttributes();
}

```

## disassembly

```asm
0x14000fb40  sub     rsp, 28h
0x14000fb44  test    r8b, r8b
0x14000fb47  jz      short loc_14000FB50
0x14000fb49  call    XdrDecodeNfs3FattrIntoNfsFileAttributes
0x14000fb4e  jmp     short loc_14000FB55
0x14000fb50  call    XdrDecodeNfs2FattrIntoNfsFileAttributes
0x14000fb55  add     rsp, 28h
0x14000fb59  retn
```
