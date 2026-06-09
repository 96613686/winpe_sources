# CDataTransferObj::~CDataTransferObj(void)

- ea: `0x18005bb34`
- end: `0x18005bbd3`
- name: `??1CDataTransferObj@@AEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CDataTransferObj *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18005cab0`

## callees

- `0x18002720c`
- `0x180040b40`
- `0x18004bac8`
- `0x18005bb34`
- `0x180095010`

## import_xrefs

- `GDI32!DeleteMetaFile` at `0x18005bbb9`
- `GDI32!DeleteMetaFile` at `0x18005bbb9`

## pseudocode

```c
void __fastcall CDataTransferObj::~CDataTransferObj(CDataTransferObj *this)
{
  struct ITxNotify *v2; // rdx
  __int64 v3; // rcx
  CNotifyMgr *v4; // rcx
  struct tagFORMATETC near **v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  HMETAFILE v8; // rcx

  *(_QWORD *)this = &CDataTransferObj::`vftable'{for `IDataObject'};
  v2 = (CDataTransferObj *)((char *)this + 8);
  v3 = *((_QWORD *)this + 7);
  *(_QWORD *)v2 = &CDataTransferObj::`vftable'{for `ITxNotify'};
  if ( v3 )
  {
    v4 = (CNotifyMgr *)(v3 + 128);
    if ( v4 )
      CNotifyMgr::Remove(v4, v2);
  }
  v5 = (struct tagFORMATETC near **)*((_QWORD *)this + 4);
  if ( v5 && v5 != &g_rgFETC )
    CW32System::FreePv(v5);
  v6 = *((_QWORD *)this + 12);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 13);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (HMETAFILE)*((_QWORD *)this + 15);
  if ( v8 )
    DeleteMetaFile(v8);
  CW32System::GlobalFree(*((void **)this + 14));
}

```

## disassembly

```asm
0x18005bb34  push    rbx
0x18005bb36  sub     rsp, 20h
0x18005bb3a  lea     rax, ??_7CDataTransferObj@@6BIDataObject@@@; const CDataTransferObj::`vftable'{for `IDataObject'}
0x18005bb41  mov     rbx, rcx
0x18005bb44  mov     [rcx], rax
0x18005bb47  lea     rdx, [rcx+8]; struct ITxNotify *
0x18005bb4b  mov     rcx, [rcx+38h]
0x18005bb4f  lea     rax, ??_7CDataTransferObj@@6BITxNotify@@@; const CDataTransferObj::`vftable'{for `ITxNotify'}
0x18005bb56  mov     [rdx], rax
0x18005bb59  test    rcx, rcx
0x18005bb5c  jz      short loc_18005BB6C
0x18005bb5e  add     rcx, 80h; this
0x18005bb65  jz      short loc_18005BB6C
0x18005bb67  call    ?Remove@CNotifyMgr@@QEAAXPEAVITxNotify@@@Z; CNotifyMgr::Remove(ITxNotify *)
0x18005bb6c  mov     rcx, [rbx+20h]; lpMem
0x18005bb70  test    rcx, rcx
0x18005bb73  jz      short loc_18005BB86
0x18005bb75  lea     rax, ?g_rgFETC@@3PAUtagFORMATETC@@A; tagFORMATETC near * g_rgFETC
0x18005bb7c  cmp     rcx, rax
0x18005bb7f  jz      short loc_18005BB86
0x18005bb81  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18005bb86  mov     rcx, [rbx+60h]
0x18005bb8a  test    rcx, rcx
0x18005bb8d  jz      short loc_18005BB9B
0x18005bb8f  mov     rax, [rcx]
0x18005bb92  mov     rax, [rax+10h]
0x18005bb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb9b  mov     rcx, [rbx+68h]
0x18005bb9f  test    rcx, rcx
0x18005bba2  jz      short loc_18005BBB0
0x18005bba4  mov     rax, [rcx]
0x18005bba7  mov     rax, [rax+10h]
0x18005bbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbb0  mov     rcx, [rbx+78h]; hmf
0x18005bbb4  test    rcx, rcx
0x18005bbb7  jz      short loc_18005BBC5
0x18005bbb9  call    cs:__imp_DeleteMetaFile
0x18005bbc0  nop     dword ptr [rax+rax+00h]
0x18005bbc5  mov     rcx, [rbx+70h]; void *
0x18005bbc9  add     rsp, 20h
0x18005bbcd  pop     rbx
0x18005bbce  jmp     ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
```
