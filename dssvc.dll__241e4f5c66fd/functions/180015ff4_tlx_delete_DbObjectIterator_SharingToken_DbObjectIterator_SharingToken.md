# tlx::_delete<DbObjectIterator<SharingToken>>(DbObjectIterator<SharingToken> *)

- ea: `0x180015ff4`
- end: `0x180016014`
- name: `??$_delete@V?$DbObjectIterator@VSharingToken@@@@@tlx@@YAXPEAV?$DbObjectIterator@VSharingToken@@@@@Z`
- size: `32`
- prototype: `void __fastcall(DbTableIterator *P)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800160e8`
- `0x18001686c`
- `0x180016a94`
- `0x180016b40`
- `0x180016dec`
- `0x180017140`
- `0x180017318`
- `0x180017518`

## callees

- `0x18000be3c`
- `0x180015ff4`
- `0x1800162e4`

## pseudocode

```c
void __fastcall tlx::_delete<DbObjectIterator<SharingToken>>(DbTableIterator *P)
{
  if ( P )
  {
    DbTableIterator::~DbTableIterator(P);
    Common::GlobalHeap::Free(P);
  }
}

```

## disassembly

```asm
0x180015ff4  test    rcx, rcx
0x180015ff7  jz      short locret_180016013
0x180015ff9  push    rbx
0x180015ffa  sub     rsp, 20h
0x180015ffe  mov     rbx, rcx
0x180016001  call    ??1DbTableIterator@@QEAA@XZ
0x180016006  mov     rcx, rbx; P
0x180016009  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z
0x18001600e  add     rsp, 20h
0x180016012  pop     rbx
0x180016013  retn
```
