# ClfsFinalize

- ea: `0x140035660`
- end: `0x1400358c3`
- name: `ClfsFinalize`
- size: `611`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140035590`

## callees

- `0x140010e08`
- `0x140011d90`
- `0x1400136f0`
- `0x140013738`
- `0x14001376c`
- `0x140017a60`
- `0x140035660`
- `0x14003c8fc`
- `0x140040da4`
- `0x14004fa98`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035731`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035752`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035773`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035794`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400357c8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400357e9`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035807`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035731`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035752`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035773`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035794`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400357c8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400357e9`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140035807`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400356dc`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400356ef`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140035710`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400357a7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140035837`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400356dc`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400356ef`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140035710`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400357a7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140035837`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400356ba`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400356ba`

## pseudocode

```c
void ClfsFinalize(void)
{
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      28,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsFinalize",
      153);
  }
  if ( CClfsHashObject::m_hSha256Algorithm )
  {
    BCryptCloseAlgorithmProvider(CClfsHashObject::m_hSha256Algorithm, 0);
    CClfsHashObject::m_hSha256Algorithm = 0;
  }
  if ( CClfsHashObject::m_fGlobalInitialized )
  {
    ExDeletePagedLookasideList(&CClfsHashObject::m_laSha256ObjectList);
    ExDeletePagedLookasideList(&CClfsHashObject::m_laHashObjectList);
    CClfsHashObject::m_fGlobalInitialized = 0;
  }
  if ( CClfsMerkleTree::m_fGlobalInitialized )
  {
    ExDeletePagedLookasideList(&CClfsMerkleTree::m_laList);
    CClfsMerkleTree::m_fGlobalInitialized = 0;
  }
  if ( CClfsFlushElt::m_fInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsFlushElt::m_laList);
    CClfsFlushElt::m_fInitialize = 0;
  }
  if ( CClfsContainerFlushElt::m_fInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsContainerFlushElt::m_laList);
    CClfsContainerFlushElt::m_fInitialize = 0;
  }
  if ( CClfsLogFcbVirtual::m_fInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsLogFcbVirtual::m_laList);
    CClfsLogFcbVirtual::m_fInitialize = 0;
  }
  if ( CClfsLogFcbPhysical::m_fInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsLogFcbPhysical::m_laList);
    ExDeletePagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
    CClfsLogFcbPhysical::m_fInitialize = 0;
  }
  if ( CClfsLogCcb::m_fInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsLogCcb::m_laList);
    CClfsLogCcb::m_fInitialize = 0;
  }
  if ( CClfsReadCompletionElt::m_fInitialize )
  {
    ExDeleteNPagedLookasideList(&CClfsReadCompletionElt::m_laList);
    CClfsReadCompletionElt::m_fInitialize = 0;
  }
  CClfsRequest::FinalizeGlobals();
  ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceExtension);
  CClfsBaseFilePersisted::m_fInitialized = 0;
  CClfsAuthContainerIoRequest::FinalizeGlobals();
  CClfsHashIoNode::FinalizeGlobals();
  CClfsSectorIoNode::FinalizeGlobals();
  if ( CClfsAuthContainer::m_fGlobalInitialize )
  {
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue.32);
    CClfsAuthContainer::m_fGlobalInitialize = 0;
  }
  CClfsContainer::FinalizeGlobals();
  CClfsDriver::m_fInitialized = 0;
  ClfsTelemetryFinalize();
  if ( (unsigned int)Feature_CLFS_EventLog__private_IsEnabledDeviceUsageNoInline() && ClfsEtwProvider_Context )
  {
    McGenEventUnregister_EtwUnregister(&ClfsEtwProvider_Context);
    ClfsEtwProvider_Context = 0;
  }
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      29,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsFinalize",
      1);
  }
}

```

## disassembly

```asm
0x140035660  mov     [rsp+arg_0], rbx
0x140035665  push    rsi
0x140035666  sub     rsp, 30h
0x14003566a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035671  lea     rsi, WPP_GLOBAL_Control
0x140035678  cmp     rcx, rsi
0x14003567b  jz      short loc_1400356AA
0x14003567d  test    dword ptr [rcx+2Ch], 4000000h
0x140035684  jz      short loc_1400356AA
0x140035686  mov     rcx, [rcx+18h]
0x14003568a  lea     r9, aClfsfinalize; "ClfsFinalize"
0x140035691  mov     edx, 1Ch
0x140035696  mov     [rsp+38h+var_18], 199h
0x14003569e  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400356a5  call    WPP_SF_sd
0x1400356aa  mov     rcx, cs:?m_hSha256Algorithm@CClfsHashObject@@0PEAXEA; hAlgorithm
0x1400356b1  xor     ebx, ebx
0x1400356b3  test    rcx, rcx
0x1400356b6  jz      short loc_1400356CD
0x1400356b8  xor     edx, edx; dwFlags
0x1400356ba  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400356c1  nop     dword ptr [rax+rax+00h]
0x1400356c6  mov     cs:?m_hSha256Algorithm@CClfsHashObject@@0PEAXEA, rbx; void * CClfsHashObject::m_hSha256Algorithm
0x1400356cd  cmp     cs:?m_fGlobalInitialized@CClfsHashObject@@0EA, bl; uchar CClfsHashObject::m_fGlobalInitialized
0x1400356d3  jz      short loc_140035701
0x1400356d5  lea     rcx, ?m_laSha256ObjectList@CClfsHashObject@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400356dc  call    cs:__imp_ExDeletePagedLookasideList
0x1400356e3  nop     dword ptr [rax+rax+00h]
0x1400356e8  lea     rcx, ?m_laHashObjectList@CClfsHashObject@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400356ef  call    cs:__imp_ExDeletePagedLookasideList
0x1400356f6  nop     dword ptr [rax+rax+00h]
0x1400356fb  mov     cs:?m_fGlobalInitialized@CClfsHashObject@@0EA, bl; uchar CClfsHashObject::m_fGlobalInitialized
0x140035701  cmp     cs:?m_fGlobalInitialized@CClfsMerkleTree@@0EA, bl; uchar CClfsMerkleTree::m_fGlobalInitialized
0x140035707  jz      short loc_140035722
0x140035709  lea     rcx, ?m_laList@CClfsMerkleTree@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140035710  call    cs:__imp_ExDeletePagedLookasideList
0x140035717  nop     dword ptr [rax+rax+00h]
0x14003571c  mov     cs:?m_fGlobalInitialized@CClfsMerkleTree@@0EA, bl; uchar CClfsMerkleTree::m_fGlobalInitialized
0x140035722  cmp     cs:?m_fInitialize@CClfsFlushElt@@0_NA, bl; bool CClfsFlushElt::m_fInitialize
0x140035728  jz      short loc_140035743
0x14003572a  lea     rcx, ?m_laList@CClfsFlushElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140035731  call    cs:__imp_ExDeleteNPagedLookasideList
0x140035738  nop     dword ptr [rax+rax+00h]
0x14003573d  mov     cs:?m_fInitialize@CClfsFlushElt@@0_NA, bl; bool CClfsFlushElt::m_fInitialize
0x140035743  cmp     cs:?m_fInitialize@CClfsContainerFlushElt@@0_NA, bl; bool CClfsContainerFlushElt::m_fInitialize
0x140035749  jz      short loc_140035764
0x14003574b  lea     rcx, ?m_laList@CClfsContainerFlushElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140035752  call    cs:__imp_ExDeleteNPagedLookasideList
0x140035759  nop     dword ptr [rax+rax+00h]
0x14003575e  mov     cs:?m_fInitialize@CClfsContainerFlushElt@@0_NA, bl; bool CClfsContainerFlushElt::m_fInitialize
0x140035764  cmp     cs:?m_fInitialize@CClfsLogFcbVirtual@@0_NA, bl; bool CClfsLogFcbVirtual::m_fInitialize
0x14003576a  jz      short loc_140035785
0x14003576c  lea     rcx, ?m_laList@CClfsLogFcbVirtual@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140035773  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003577a  nop     dword ptr [rax+rax+00h]
0x14003577f  mov     cs:?m_fInitialize@CClfsLogFcbVirtual@@0_NA, bl; bool CClfsLogFcbVirtual::m_fInitialize
0x140035785  cmp     cs:?m_fInitialize@CClfsLogFcbPhysical@@0_NA, bl; bool CClfsLogFcbPhysical::m_fInitialize
0x14003578b  jz      short loc_1400357B9
0x14003578d  lea     rcx, ?m_laList@CClfsLogFcbPhysical@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140035794  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003579b  nop     dword ptr [rax+rax+00h]
0x1400357a0  lea     rcx, ?m_laOwnerPage@CClfsLogFcbPhysical@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400357a7  call    cs:__imp_ExDeletePagedLookasideList
0x1400357ae  nop     dword ptr [rax+rax+00h]
0x1400357b3  mov     cs:?m_fInitialize@CClfsLogFcbPhysical@@0_NA, bl; bool CClfsLogFcbPhysical::m_fInitialize
0x1400357b9  cmp     cs:?m_fInitialize@CClfsLogCcb@@0_NA, bl; bool CClfsLogCcb::m_fInitialize
0x1400357bf  jz      short loc_1400357DA
0x1400357c1  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400357c8  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400357cf  nop     dword ptr [rax+rax+00h]
0x1400357d4  mov     cs:?m_fInitialize@CClfsLogCcb@@0_NA, bl; bool CClfsLogCcb::m_fInitialize
0x1400357da  cmp     cs:?m_fInitialize@CClfsReadCompletionElt@@0_NA, bl; bool CClfsReadCompletionElt::m_fInitialize
0x1400357e0  jz      short loc_1400357FB
0x1400357e2  lea     rcx, ?m_laList@CClfsReadCompletionElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400357e9  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400357f0  nop     dword ptr [rax+rax+00h]
0x1400357f5  mov     cs:?m_fInitialize@CClfsReadCompletionElt@@0_NA, bl; bool CClfsReadCompletionElt::m_fInitialize
0x1400357fb  call    ?FinalizeGlobals@CClfsRequest@@SAXXZ; CClfsRequest::FinalizeGlobals(void)
0x140035800  lea     rcx, WPP_MAIN_CB.DeviceExtension; Lookaside
0x140035807  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003580e  nop     dword ptr [rax+rax+00h]
0x140035813  mov     cs:?m_fInitialized@CClfsBaseFilePersisted@@0_NA, bl; bool CClfsBaseFilePersisted::m_fInitialized
0x140035819  call    ?FinalizeGlobals@CClfsAuthContainerIoRequest@@SAXXZ; CClfsAuthContainerIoRequest::FinalizeGlobals(void)
0x14003581e  call    ?FinalizeGlobals@CClfsHashIoNode@@SAXXZ; CClfsHashIoNode::FinalizeGlobals(void)
0x140035823  call    ?FinalizeGlobals@CClfsSectorIoNode@@SAXXZ; CClfsSectorIoNode::FinalizeGlobals(void)
0x140035828  cmp     cs:?m_fGlobalInitialize@CClfsAuthContainer@@0_NA, bl; bool CClfsAuthContainer::m_fGlobalInitialize
0x14003582e  jz      short loc_140035849
0x140035830  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h; Lookaside
0x140035837  call    cs:__imp_ExDeletePagedLookasideList
0x14003583e  nop     dword ptr [rax+rax+00h]
0x140035843  mov     cs:?m_fGlobalInitialize@CClfsAuthContainer@@0_NA, bl; bool CClfsAuthContainer::m_fGlobalInitialize
0x140035849  call    ?FinalizeGlobals@CClfsContainer@@SAXXZ; CClfsContainer::FinalizeGlobals(void)
0x14003584e  mov     cs:?m_fInitialized@CClfsDriver@@0EA, bl; uchar CClfsDriver::m_fInitialized
0x140035854  call    ClfsTelemetryFinalize
0x140035859  call    Feature_CLFS_EventLog__private_IsEnabledDeviceUsageNoInline
0x14003585e  test    eax, eax
0x140035860  jz      short loc_14003587E
0x140035862  cmp     cs:ClfsEtwProvider_Context, rbx
0x140035869  jz      short loc_14003587E
0x14003586b  lea     rcx, ClfsEtwProvider_Context
0x140035872  call    McGenEventUnregister_EtwUnregister
0x140035877  mov     cs:ClfsEtwProvider_Context, rbx
0x14003587e  mov     rcx, cs:WPP_GLOBAL_Control
0x140035885  cmp     rcx, rsi
0x140035888  jz      short loc_1400358B7
0x14003588a  test    dword ptr [rcx+2Ch], 4000000h
0x140035891  jz      short loc_1400358B7
0x140035893  mov     rcx, [rcx+18h]
0x140035897  lea     r9, aClfsfinalize; "ClfsFinalize"
0x14003589e  mov     edx, 1Dh
0x1400358a3  mov     [rsp+38h+var_18], 201h
0x1400358ab  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400358b2  call    WPP_SF_sd
0x1400358b7  mov     rbx, [rsp+38h+arg_0]
0x1400358bc  add     rsp, 30h
0x1400358c0  pop     rsi
0x1400358c1  retn
```
