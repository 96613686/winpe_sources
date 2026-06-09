# tlx::_delete<DbTableAccess<SharingToken>>(DbTableAccess<SharingToken> *)

- ea: `0x180016044`
- end: `0x180016064`
- name: `??$_delete@V?$DbTableAccess@VSharingToken@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingToken@@@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015e68`
- `0x180016140`
- `0x18001686c`
- `0x180017140`
- `0x180017318`

## callees

- `0x18000be3c`
- `0x180016044`
- `0x18001622c`

## pseudocode

```c
void __fastcall tlx::_delete<DbTableAccess<SharingToken>>(PVOID P)
{
  if ( P )
  {
    DbTableAccess<SharingToken>::~DbTableAccess<SharingToken>();
    Common::GlobalHeap::Free(P);
  }
}

```

## disassembly

```asm
0x180016044  test    rcx, rcx
0x180016047  jz      short locret_180016063
0x180016049  push    rbx
0x18001604a  sub     rsp, 20h
0x18001604e  mov     rbx, rcx
0x180016051  call    ??1?$DbTableAccess@VSharingToken@@@@QEAA@XZ
0x180016056  mov     rcx, rbx; P
0x180016059  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z
0x18001605e  add     rsp, 20h
0x180016062  pop     rbx
0x180016063  retn
```
