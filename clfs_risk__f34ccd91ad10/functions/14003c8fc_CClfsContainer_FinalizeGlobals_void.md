# CClfsContainer::FinalizeGlobals(void)

- ea: `0x14003c8fc`
- end: `0x14003c9a2`
- name: `?FinalizeGlobals@CClfsContainer@@SAXXZ`
- size: `166`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140035660`

## callees

- `0x14003c8fc`

## import_xrefs

- `ntoskrnl!SeDeassignSecurity` at `0x14003c911`
- `ntoskrnl!SeDeassignSecurity` at `0x14003c943`
- `ntoskrnl!SeDeassignSecurity` at `0x14003c911`
- `ntoskrnl!SeDeassignSecurity` at `0x14003c943`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003c974`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14003c974`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c989`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c989`

## pseudocode

```c
void CClfsContainer::FinalizeGlobals(void)
{
  if ( CClfsContainer::m_psdNoSecurity )
  {
    SeDeassignSecurity(&CClfsContainer::m_psdNoSecurity);
    CClfsContainer::m_psdNoSecurity = 0;
    LODWORD(CClfsContainer::m_cbNoSecurity) = 0;
  }
  if ( CClfsContainer::m_psdDefaultSecurity )
  {
    SeDeassignSecurity(&CClfsContainer::m_psdDefaultSecurity);
    CClfsContainer::m_psdDefaultSecurity = 0;
    LODWORD(CClfsContainer::m_cbDefaultSecurity) = 0;
  }
  if ( CClfsContainer::m_fInitialize )
  {
    ExDeletePagedLookasideList(&CClfsContainer::m_laList);
    ExFreePoolWithTag(CClfsContainer::m_pbZeroPage, 0);
    CClfsContainer::m_fInitialize = 0;
  }
}

```

## disassembly

```asm
0x14003c8fc  sub     rsp, 28h
0x14003c900  cmp     cs:?m_psdNoSecurity@CClfsContainer@@0PEAXEA, 0; void * CClfsContainer::m_psdNoSecurity
0x14003c908  jz      short loc_14003C932
0x14003c90a  lea     rcx, ?m_psdNoSecurity@CClfsContainer@@0PEAXEA; SecurityDescriptor
0x14003c911  call    cs:__imp_SeDeassignSecurity
0x14003c918  nop     dword ptr [rax+rax+00h]
0x14003c91d  mov     cs:?m_psdNoSecurity@CClfsContainer@@0PEAXEA, 0; void * CClfsContainer::m_psdNoSecurity
0x14003c928  mov     cs:?m_cbNoSecurity@CClfsContainer@@0KA, 0; ulong CClfsContainer::m_cbNoSecurity
0x14003c932  cmp     cs:?m_psdDefaultSecurity@CClfsContainer@@0PEAXEA, 0; void * CClfsContainer::m_psdDefaultSecurity
0x14003c93a  jz      short loc_14003C964
0x14003c93c  lea     rcx, ?m_psdDefaultSecurity@CClfsContainer@@0PEAXEA; SecurityDescriptor
0x14003c943  call    cs:__imp_SeDeassignSecurity
0x14003c94a  nop     dword ptr [rax+rax+00h]
0x14003c94f  mov     cs:?m_psdDefaultSecurity@CClfsContainer@@0PEAXEA, 0; void * CClfsContainer::m_psdDefaultSecurity
0x14003c95a  mov     cs:?m_cbDefaultSecurity@CClfsContainer@@0KA, 0; ulong CClfsContainer::m_cbDefaultSecurity
0x14003c964  cmp     cs:?m_fInitialize@CClfsContainer@@0_NA, 0; bool CClfsContainer::m_fInitialize
0x14003c96b  jz      short loc_14003C99C
0x14003c96d  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14003c974  call    cs:__imp_ExDeletePagedLookasideList
0x14003c97b  nop     dword ptr [rax+rax+00h]
0x14003c980  mov     rcx, cs:?m_pbZeroPage@CClfsContainer@@0PEAEEA; P
0x14003c987  xor     edx, edx; Tag
0x14003c989  call    cs:__imp_ExFreePoolWithTag
0x14003c990  nop     dword ptr [rax+rax+00h]
0x14003c995  mov     cs:?m_fInitialize@CClfsContainer@@0_NA, 0; bool CClfsContainer::m_fInitialize
0x14003c99c  add     rsp, 28h
0x14003c9a0  retn
```
