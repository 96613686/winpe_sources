# ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::~CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>(void)

- ea: `0x18000b358`
- end: `0x18000b38b`
- name: `??1?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAA@XZ`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b400`

## callees

- `0x180001150`
- `0x18000b358`
- `0x180019010`

## pseudocode

```c
void __fastcall ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::~CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>(
        __int64 a1)
{
  __int64 v2; // rcx

  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
    operator delete[](*(void **)(a1 + 16));
  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x18000b358  push    rbx
0x18000b35a  sub     rsp, 20h
0x18000b35e  test    byte ptr [rcx+28h], 2
0x18000b362  mov     rbx, rcx
0x18000b365  jz      short loc_18000B370
0x18000b367  mov     rcx, [rcx+10h]; Block
0x18000b36b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000b370  mov     rcx, [rbx+8]
0x18000b374  test    rcx, rcx
0x18000b377  jz      short loc_18000B385
0x18000b379  mov     rax, [rcx]
0x18000b37c  mov     rax, [rax+10h]
0x18000b380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b385  add     rsp, 20h
0x18000b389  pop     rbx
0x18000b38a  retn
```
