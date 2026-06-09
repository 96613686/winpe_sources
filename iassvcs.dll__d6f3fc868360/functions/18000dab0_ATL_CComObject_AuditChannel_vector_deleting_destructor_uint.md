# ATL::CComObject<AuditChannel>::`vector deleting destructor'(uint)

- ea: `0x18000dab0`
- end: `0x18000db28`
- name: `??_E?$CComObject@VAuditChannel@@@ATL@@UEAAPEAXI@Z`
- size: `120`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d7ac`
- `0x18000dab0`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x18000db14`
- `msvcrt!free` at `0x18000db14`
- `KERNEL32!DeleteCriticalSection` at `0x18000db05`
- `KERNEL32!DeleteCriticalSection` at `0x18000db05`

## pseudocode

```c
char *__fastcall ATL::CComObject<AuditChannel>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 4) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSink'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSource'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>((__int64)(Block + 72));
  if ( Block[64] )
  {
    Block[64] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 24));
  }
  if ( (a2 & 1) != 0 )
    free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000dab0  mov     [rsp+arg_0], rbx
0x18000dab5  push    rdi
0x18000dab6  sub     rsp, 20h
0x18000daba  mov     dword ptr [rcx+10h], 0C0000001h
0x18000dac1  lea     rax, ??_7?$CComObject@VAuditChannel@@@ATL@@6BIAuditSink@@@; const ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSink'}
0x18000dac8  mov     [rcx], rax
0x18000dacb  mov     rbx, rcx
0x18000dace  lea     rax, ??_7?$CComObject@VAuditChannel@@@ATL@@6BIAuditSource@@@; const ATL::CComObject<AuditChannel>::`vftable'{for `IAuditSource'}
0x18000dad5  mov     edi, edx
0x18000dad7  mov     [rcx+8], rax
0x18000dadb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dae2  mov     rax, [rcx]
0x18000dae5  mov     rax, [rax+10h]
0x18000dae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daee  lea     rcx, [rbx+48h]
0x18000daf2  call    ??1?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAA@XZ; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(void)
0x18000daf7  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000dafb  cmp     byte ptr [rcx+28h], 0
0x18000daff  jz      short loc_18000DB0B
0x18000db01  mov     byte ptr [rcx+28h], 0
0x18000db05  call    cs:__imp_DeleteCriticalSection
0x18000db0b  test    dil, 1
0x18000db0f  jz      short loc_18000DB1A
0x18000db11  mov     rcx, rbx; Block
0x18000db14  call    cs:__imp_free
0x18000db1a  mov     rax, rbx
0x18000db1d  mov     rbx, [rsp+28h+arg_0]
0x18000db22  add     rsp, 20h
0x18000db26  pop     rdi
0x18000db27  retn
```
