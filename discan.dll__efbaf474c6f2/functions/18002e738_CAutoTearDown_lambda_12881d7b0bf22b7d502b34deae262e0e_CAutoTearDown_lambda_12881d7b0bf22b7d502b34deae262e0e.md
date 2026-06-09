# CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___::_CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___

- ea: `0x18002e738`
- end: `0x18002e758`
- name: `CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___::_CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18003061c`

## callees

- `0x18002e738`

## import_xrefs

- `ESENT!JetRollback` at `0x18002e74d`
- `ESENT!JetRollback` at `0x18002e74d`

## pseudocode

```c
JET_ERR __fastcall CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___::_CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___(
        __int64 *a1)
{
  __int64 v1; // rcx
  JET_ERR result; // eax

  v1 = *a1;
  if ( v1 )
    return JetRollback(*(_QWORD *)(*(_QWORD *)v1 + 8LL), 0);
  return result;
}

```

## disassembly

```asm
0x18002e738  sub     rsp, 28h
0x18002e73c  mov     rcx, [rcx]
0x18002e73f  test    rcx, rcx
0x18002e742  jz      short loc_18002E753
0x18002e744  mov     rcx, [rcx]
0x18002e747  xor     edx, edx; grbit
0x18002e749  mov     rcx, [rcx+8]; sesid
0x18002e74d  call    cs:__imp_JetRollback
0x18002e753  add     rsp, 28h
0x18002e757  retn
```
