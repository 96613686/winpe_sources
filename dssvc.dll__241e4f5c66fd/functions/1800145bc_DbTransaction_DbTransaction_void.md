# DbTransaction::~DbTransaction(void)

- ea: `0x1800145bc`
- end: `0x1800145d6`
- name: `??1DbTransaction@@QEAA@XZ`
- size: `26`
- prototype: `void __fastcall(JET_SESID *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800144ac`

## callees

- `0x1800145bc`

## import_xrefs

- `ESENT!JetRollback` at `0x1800145cb`
- `ESENT!JetRollback` at `0x1800145cb`

## pseudocode

```c
void __fastcall DbTransaction::~DbTransaction(JET_SESID *this)
{
  if ( *this != -1 )
    JetRollback(*this, 0);
}

```

## disassembly

```asm
0x1800145bc  sub     rsp, 28h
0x1800145c0  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x1800145c4  jz      short loc_1800145D1
0x1800145c6  mov     rcx, [rcx]; sesid
0x1800145c9  xor     edx, edx; grbit
0x1800145cb  call    cs:__imp_JetRollback
0x1800145d1  add     rsp, 28h
0x1800145d5  retn
```
