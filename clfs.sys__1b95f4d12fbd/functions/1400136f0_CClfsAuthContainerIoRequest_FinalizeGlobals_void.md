# CClfsAuthContainerIoRequest::FinalizeGlobals(void)

- ea: `0x1400136f0`
- end: `0x140013730`
- name: `?FinalizeGlobals@CClfsAuthContainerIoRequest@@SAXXZ`
- size: `64`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140035660`

## callees

- `0x1400136f0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140013704`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140013717`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140013704`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140013717`

## pseudocode

```c
void CClfsAuthContainerIoRequest::FinalizeGlobals(void)
{
  if ( CClfsAuthContainerIoRequest::m_fGlobalInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsAuthContainerIoRequest::m_laList);
    ExDeleteNPagedLookasideList(&CClfsAuthContainerIoRequest::m_laAvlList);
    CClfsAuthContainerIoRequest::m_fGlobalInitialize = 0;
  }
}

```

## disassembly

```asm
0x1400136f0  sub     rsp, 28h
0x1400136f4  cmp     cs:?m_fGlobalInitialize@CClfsAuthContainerIoRequest@@0_NA, 0; bool CClfsAuthContainerIoRequest::m_fGlobalInitialize
0x1400136fb  jz      short loc_14001372A
0x1400136fd  lea     rcx, ?m_laList@CClfsAuthContainerIoRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140013704  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001370b  nop     dword ptr [rax+rax+00h]
0x140013710  lea     rcx, ?m_laAvlList@CClfsAuthContainerIoRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140013717  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001371e  nop     dword ptr [rax+rax+00h]
0x140013723  mov     cs:?m_fGlobalInitialize@CClfsAuthContainerIoRequest@@0_NA, 0; bool CClfsAuthContainerIoRequest::m_fGlobalInitialize
0x14001372a  add     rsp, 28h
0x14001372e  retn
```
