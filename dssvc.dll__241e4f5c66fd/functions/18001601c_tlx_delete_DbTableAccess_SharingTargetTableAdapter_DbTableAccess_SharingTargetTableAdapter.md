# tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(DbTableAccess<SharingTargetTableAdapter> *)

- ea: `0x18001601c`
- end: `0x18001603c`
- name: `??$_delete@V?$DbTableAccess@VSharingTargetTableAdapter@@@@@tlx@@YAXPEAV?$DbTableAccess@VSharingTargetTableAdapter@@@@@Z`
- size: `32`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015cfc`
- `0x180015da4`
- `0x180016114`
- `0x1800163ec`
- `0x18001669c`
- `0x180016dec`
- `0x180017518`
- `0x180017c90`

## callees

- `0x18000be3c`
- `0x18001601c`
- `0x1800161f0`

## pseudocode

```c
void __fastcall tlx::_delete<DbTableAccess<SharingTargetTableAdapter>>(PVOID P)
{
  if ( P )
  {
    DbTableAccess<SharingTargetTableAdapter>::~DbTableAccess<SharingTargetTableAdapter>();
    Common::GlobalHeap::Free(P);
  }
}

```

## disassembly

```asm
0x18001601c  test    rcx, rcx
0x18001601f  jz      short locret_18001603B
0x180016021  push    rbx
0x180016022  sub     rsp, 20h
0x180016026  mov     rbx, rcx
0x180016029  call    ??1?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAA@XZ
0x18001602e  mov     rcx, rbx; P
0x180016031  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z
0x180016036  add     rsp, 20h
0x18001603a  pop     rbx
0x18001603b  retn
```
