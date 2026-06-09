# ATL::CComObjectCached<AuditChannel>::~CComObjectCached<AuditChannel>(void)

- ea: `0x18000d718`
- end: `0x18000d760`
- name: `??1?$CComObjectCached@VAuditChannel@@@ATL@@QEAA@XZ`
- size: `72`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f3b0`

## callees

- `0x18000d718`
- `0x18000d7ac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000d754`
- `KERNEL32!DeleteCriticalSection` at `0x18000d754`

## pseudocode

```c
void __fastcall ATL::CComObjectCached<AuditChannel>::~CComObjectCached<AuditChannel>(__int64 a1)
{
  *(_DWORD *)(a1 + 16) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'};
  std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(a1 + 72);
  if ( *(_BYTE *)(a1 + 64) )
  {
    *(_BYTE *)(a1 + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  }
}

```

## disassembly

```asm
0x18000d718  push    rbx
0x18000d71a  sub     rsp, 20h
0x18000d71e  lea     rax, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSink@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSink'}
0x18000d725  mov     dword ptr [rcx+10h], 0C0000001h
0x18000d72c  mov     [rcx], rax
0x18000d72f  mov     rbx, rcx
0x18000d732  lea     rax, ??_7?$CComObjectCached@VAuditChannel@@@ATL@@6BIAuditSource@@@; const ATL::CComObjectCached<AuditChannel>::`vftable'{for `IAuditSource'}
0x18000d739  mov     [rcx+8], rax
0x18000d73d  add     rcx, 48h ; 'H'
0x18000d741  call    ??1?$vector@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@V?$allocator@V?$_com_ptr_t@V?$_com_IIID@UIAuditSink@@$1?_GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B@@@@@std@@@std@@QEAA@XZ; std::vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>::~vector<_com_ptr_t<_com_IIID<IAuditSink,&__s_GUID const _GUID_6bc0969a_0ce6_11d1_baae_00c04fc2e20d>>>(void)
0x18000d746  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000d74a  cmp     byte ptr [rcx+28h], 0
0x18000d74e  jz      short loc_18000D75A
0x18000d750  mov     byte ptr [rcx+28h], 0
0x18000d754  call    cs:__imp_DeleteCriticalSection
0x18000d75a  add     rsp, 20h
0x18000d75e  pop     rbx
0x18000d75f  retn
```
