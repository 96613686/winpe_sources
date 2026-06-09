# CASFReader::QueryFilterInfo(_FilterInfo *)

- ea: `0x18000c750`
- end: `0x18000c770`
- name: `?QueryFilterInfo@CASFReader@@UEAAJPEAU_FilterInfo@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, struct _FilterInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800057f0`
- `0x18000c750`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::QueryFilterInfo(CASFReader *this, struct _FilterInfo *a2)
{
  __int64 v2; // r8

  v2 = *((_QWORD *)this + 55);
  if ( v2 )
    return (*(__int64 (__fastcall **)(_QWORD, struct _FilterInfo *))(*(_QWORD *)v2 + 96LL))(*((_QWORD *)this + 55), a2);
  else
    return CBaseFilter::QueryFilterInfo(this, a2);
}

```

## disassembly

```asm
0x18000c750  mov     r8, [rcx+1B8h]
0x18000c757  test    r8, r8
0x18000c75a  jz      short loc_18000C76B
0x18000c75c  mov     rax, [r8]
0x18000c75f  mov     rcx, r8; this
0x18000c762  mov     rax, [rax+60h]
0x18000c766  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000c76b  jmp     ?QueryFilterInfo@CBaseFilter@@UEAAJPEAU_FilterInfo@@@Z; CBaseFilter::QueryFilterInfo(_FilterInfo *)
```
