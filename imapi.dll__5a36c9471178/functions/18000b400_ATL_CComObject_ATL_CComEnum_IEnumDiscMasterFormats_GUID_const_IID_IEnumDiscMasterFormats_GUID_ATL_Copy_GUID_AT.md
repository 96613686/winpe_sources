# ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::`vector deleting destructor'(uint)

- ea: `0x18000b400`
- end: `0x18000b475`
- name: `??_E?$CComObject@V?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@@ATL@@UEAAPEAXI@Z`
- size: `117`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x18000b358`
- `0x18000b400`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b437`
- `KERNEL32!DeleteCriticalSection` at `0x18000b44b`
- `KERNEL32!DeleteCriticalSection` at `0x18000b437`
- `KERNEL32!DeleteCriticalSection` at `0x18000b44b`

## pseudocode

```c
char *__fastcall ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::`vector deleting destructor'(
        char *Block,
        char a2)
{
  *((_DWORD *)Block + 12) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 104));
  if ( Block[96] )
  {
    Block[96] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 56));
  }
  ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::~CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b400  mov     [rsp+arg_0], rbx
0x18000b405  push    rdi
0x18000b406  sub     rsp, 20h
0x18000b40a  mov     dword ptr [rcx+30h], 0C0000001h
0x18000b411  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::`vftable'
0x18000b418  mov     [rcx], rax
0x18000b41b  mov     rbx, rcx
0x18000b41e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b425  mov     edi, edx
0x18000b427  mov     rax, [rcx]
0x18000b42a  mov     rax, [rax+10h]
0x18000b42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b433  lea     rcx, [rbx+68h]; lpCriticalSection
0x18000b437  call    cs:__imp_DeleteCriticalSection
0x18000b43d  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000b441  cmp     byte ptr [rcx+28h], 0
0x18000b445  jz      short loc_18000B451
0x18000b447  mov     byte ptr [rcx+28h], 0
0x18000b44b  call    cs:__imp_DeleteCriticalSection
0x18000b451  mov     rcx, rbx
0x18000b454  call    ??1?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAA@XZ; ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::~CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>(void)
0x18000b459  test    dil, 1
0x18000b45d  jz      short loc_18000B467
0x18000b45f  mov     rcx, rbx; Block
0x18000b462  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b467  mov     rax, rbx
0x18000b46a  mov     rbx, [rsp+28h+arg_0]
0x18000b46f  add     rsp, 20h
0x18000b473  pop     rdi
0x18000b474  retn
```
