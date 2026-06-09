# ClfsInitialize

- ea: `0x14004c5a0`
- end: `0x14004c9f8`
- name: `ClfsInitialize`
- size: `1112`
- prototype: `NTSTATUS(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003599c`

## callees

- `0x14000ed64`
- `0x14000f13c`
- `0x140011d90`
- `0x140013954`
- `0x1400139dc`
- `0x140013a2c`
- `0x14003d11c`
- `0x14003d274`
- `0x1400415d4`
- `0x140046b00`
- `0x14004c5a0`
- `0x14004d968`
- `0x14004ee7c`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c808`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c842`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c8b8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c92e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c969`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c99f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c808`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c842`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c8b8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c92e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c969`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14004c99f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004c693`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14004c693`

## pseudocode

```c
NTSTATUS ClfsInitialize(void)
{
  unsigned int v0; // ecx
  int v1; // eax
  NTSTATUS v2; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax

  v0 = (unsigned int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      10,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsInitialize",
      133);
  }
  CCrc32::Initialize(v0);
  v1 = ClfsRegistryInitialize();
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          11,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsInitialize",
          153,
          v1);
    }
    return v2;
  }
  v4 = CClfsHashObject::InitializeGlobals();
  v2 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        12,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        169,
        v4);
    }
    return v2;
  }
  ExInitializePagedLookasideList(&CClfsMerkleTree::m_laList, 0, 0, 0, 0x50u, 0x4D666C43u, 0);
  CClfsMerkleTree::m_fGlobalInitialized = 1;
  v5 = CClfsContainer::InitializeGlobals();
  v2 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        14,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        197,
        v5);
    }
    return v2;
  }
  v6 = CClfsAuthContainer::InitializeGlobals();
  v2 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        15,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        213,
        v6);
    }
    return v2;
  }
  v7 = CClfsAuthContainerIoRequest::InitializeGlobals();
  v2 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        16,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        229,
        v7);
    }
    return v2;
  }
  v8 = CClfsSectorIoNode::InitializeGlobals();
  v2 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        17,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        245,
        v8);
    }
    return v2;
  }
  v9 = CClfsHashIoNode::InitializeGlobals();
  v2 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        18,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        5,
        v9);
    }
    return v2;
  }
  if ( !CClfsBaseFilePersisted::m_fInitialized )
  {
    ExInitializeNPagedLookasideList(
      (PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceExtension,
      0,
      0,
      0x200u,
      0x21D8u,
      0x42666C43u,
      0);
    CClfsBaseFilePersisted::m_fInitialized = 1;
  }
  ExInitializeNPagedLookasideList(&CClfsReadCompletionElt::m_laList, 0, 0, 0x200u, 0x70u, 0x4B666C43u, 0);
  CClfsReadCompletionElt::m_fInitialize = 1;
  v10 = CClfsRequest::InitializeGlobals();
  v2 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        21,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        41,
        v10);
    }
    return v2;
  }
  ExInitializeNPagedLookasideList(&CClfsLogCcb::m_laList, 0, 0, 0x200u, 0x110u, 0x45666C43u, 0);
  CClfsLogCcb::m_fInitialize = 1;
  v11 = CClfsLogFcbPhysical::InitializeGlobals();
  v2 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        23,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsInitialize",
        67,
        v11);
    }
    return v2;
  }
  ExInitializeNPagedLookasideList(&CClfsLogFcbVirtual::m_laList, 0, 0, 0x200u, 0x298u, 0x44666C43u, 0);
  CClfsLogFcbVirtual::m_fInitialize = 1;
  ExInitializeNPagedLookasideList(&CClfsContainerFlushElt::m_laList, 0, 0, 0x200u, 0xB0u, 0x46666C43u, 0);
  CClfsContainerFlushElt::m_fInitialize = 1;
  ExInitializeNPagedLookasideList(&CClfsFlushElt::m_laList, 0, 0, 0x200u, 0xF0u, 0x46666C43u, 0);
  CClfsFlushElt::m_fInitialize = 1;
  CClfsDriver::m_fInitialized = 1;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0x1Au) )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      27,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsInitialize",
      115);
  }
  return 0;
}

```

## disassembly

```asm
0x14004c5a0  push    rbx
0x14004c5a2  push    rbp
0x14004c5a3  push    rsi
0x14004c5a4  push    rdi
0x14004c5a5  push    r14
0x14004c5a7  push    r15
0x14004c5a9  sub     rsp, 48h
0x14004c5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c5b4  lea     rsi, WPP_GLOBAL_Control
0x14004c5bb  lea     rbp, aClfsinitialize; "ClfsInitialize"
0x14004c5c2  lea     r14, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004c5c9  cmp     rcx, rsi
0x14004c5cc  jz      short loc_14004C5F1
0x14004c5ce  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c5d3  jnb     short loc_14004C5F1
0x14004c5d5  mov     rcx, [rcx+18h]
0x14004c5d9  mov     edx, 0Ah
0x14004c5de  mov     r9, rbp
0x14004c5e1  mov     dword ptr [rsp+78h+Size], 85h
0x14004c5e9  mov     r8, r14
0x14004c5ec  call    WPP_SF_sd
0x14004c5f1  call    ?Initialize@CCrc32@@SAXK@Z; CCrc32::Initialize(ulong)
0x14004c5f6  call    ?ClfsRegistryInitialize@@YAJXZ; ClfsRegistryInitialize(void)
0x14004c5fb  mov     ebx, eax
0x14004c5fd  test    eax, eax
0x14004c5ff  jns     short loc_14004C63B
0x14004c601  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c608  cmp     rcx, rsi
0x14004c60b  jz      short loc_14004C634
0x14004c60d  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c612  jnb     short loc_14004C634
0x14004c614  mov     [rsp+78h+Tag], eax
0x14004c618  mov     edx, 0Bh
0x14004c61d  mov     dword ptr [rsp+78h+Size], 99h
0x14004c625  mov     rcx, [rcx+18h]
0x14004c629  mov     r9, rbp
0x14004c62c  mov     r8, r14
0x14004c62f  call    WPP_SF_slD
0x14004c634  mov     eax, ebx
0x14004c636  jmp     loc_14004C9EA
0x14004c63b  call    ?InitializeGlobals@CClfsHashObject@@SAJXZ; CClfsHashObject::InitializeGlobals(void)
0x14004c640  mov     ebx, eax
0x14004c642  test    eax, eax
0x14004c644  jns     short loc_14004C66C
0x14004c646  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c64d  cmp     rcx, rsi
0x14004c650  jz      short loc_14004C634
0x14004c652  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c657  jnb     short loc_14004C634
0x14004c659  mov     [rsp+78h+Tag], eax
0x14004c65d  mov     edx, 0Ch
0x14004c662  mov     dword ptr [rsp+78h+Size], 0A9h
0x14004c66a  jmp     short loc_14004C625
0x14004c66c  xor     eax, eax
0x14004c66e  lea     rcx, ?m_laList@CClfsMerkleTree@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004c675  mov     [rsp+78h+Depth], ax; Depth
0x14004c67a  xor     r9d, r9d; Flags
0x14004c67d  mov     [rsp+78h+Tag], 4D666C43h; Tag
0x14004c685  xor     r8d, r8d; Free
0x14004c688  xor     edx, edx; Allocate
0x14004c68a  mov     [rsp+78h+Size], 50h ; 'P'; Size
0x14004c693  call    cs:__imp_ExInitializePagedLookasideList
0x14004c69a  nop     dword ptr [rax+rax+00h]
0x14004c69f  mov     cs:?m_fGlobalInitialized@CClfsMerkleTree@@0EA, 1; uchar CClfsMerkleTree::m_fGlobalInitialized
0x14004c6a6  call    ?InitializeGlobals@CClfsContainer@@SAJXZ; CClfsContainer::InitializeGlobals(void)
0x14004c6ab  mov     ebx, eax
0x14004c6ad  test    eax, eax
0x14004c6af  jns     short loc_14004C6E2
0x14004c6b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c6b8  cmp     rcx, rsi
0x14004c6bb  jz      loc_14004C634
0x14004c6c1  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c6c6  jnb     loc_14004C634
0x14004c6cc  mov     [rsp+78h+Tag], eax
0x14004c6d0  mov     edx, 0Eh
0x14004c6d5  mov     dword ptr [rsp+78h+Size], 0C5h
0x14004c6dd  jmp     loc_14004C625
0x14004c6e2  call    ?InitializeGlobals@CClfsAuthContainer@@SAJXZ; CClfsAuthContainer::InitializeGlobals(void)
0x14004c6e7  mov     ebx, eax
0x14004c6e9  test    eax, eax
0x14004c6eb  jns     short loc_14004C71E
0x14004c6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c6f4  cmp     rcx, rsi
0x14004c6f7  jz      loc_14004C634
0x14004c6fd  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c702  jnb     loc_14004C634
0x14004c708  mov     [rsp+78h+Tag], eax
0x14004c70c  mov     edx, 0Fh
0x14004c711  mov     dword ptr [rsp+78h+Size], 0D5h
0x14004c719  jmp     loc_14004C625
0x14004c71e  call    ?InitializeGlobals@CClfsAuthContainerIoRequest@@SAJXZ; CClfsAuthContainerIoRequest::InitializeGlobals(void)
0x14004c723  mov     ebx, eax
0x14004c725  test    eax, eax
0x14004c727  jns     short loc_14004C75A
0x14004c729  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c730  cmp     rcx, rsi
0x14004c733  jz      loc_14004C634
0x14004c739  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c73e  jnb     loc_14004C634
0x14004c744  mov     [rsp+78h+Tag], eax
0x14004c748  mov     edx, 10h
0x14004c74d  mov     dword ptr [rsp+78h+Size], 0E5h
0x14004c755  jmp     loc_14004C625
0x14004c75a  call    ?InitializeGlobals@CClfsSectorIoNode@@SAJXZ; CClfsSectorIoNode::InitializeGlobals(void)
0x14004c75f  mov     ebx, eax
0x14004c761  test    eax, eax
0x14004c763  jns     short loc_14004C796
0x14004c765  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c76c  cmp     rcx, rsi
0x14004c76f  jz      loc_14004C634
0x14004c775  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c77a  jnb     loc_14004C634
0x14004c780  mov     [rsp+78h+Tag], eax
0x14004c784  mov     edx, 11h
0x14004c789  mov     dword ptr [rsp+78h+Size], 0F5h
0x14004c791  jmp     loc_14004C625
0x14004c796  call    ?InitializeGlobals@CClfsHashIoNode@@SAJXZ; CClfsHashIoNode::InitializeGlobals(void)
0x14004c79b  mov     ebx, eax
0x14004c79d  test    eax, eax
0x14004c79f  jns     short loc_14004C7D2
0x14004c7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c7a8  cmp     rcx, rsi
0x14004c7ab  jz      loc_14004C634
0x14004c7b1  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c7b6  jnb     loc_14004C634
0x14004c7bc  mov     [rsp+78h+Tag], eax
0x14004c7c0  mov     edx, 12h
0x14004c7c5  mov     dword ptr [rsp+78h+Size], 105h
0x14004c7cd  jmp     loc_14004C625
0x14004c7d2  cmp     cs:?m_fInitialized@CClfsBaseFilePersisted@@0_NA, 0; bool CClfsBaseFilePersisted::m_fInitialized
0x14004c7d9  mov     r15d, 200h
0x14004c7df  jnz     short loc_14004C81B
0x14004c7e1  xor     eax, eax
0x14004c7e3  lea     rcx, WPP_MAIN_CB.DeviceExtension; Lookaside
0x14004c7ea  mov     [rsp+78h+Depth], ax; Depth
0x14004c7ef  mov     r9d, r15d; Flags
0x14004c7f2  mov     [rsp+78h+Tag], 42666C43h; Tag
0x14004c7fa  xor     r8d, r8d; Free
0x14004c7fd  xor     edx, edx; Allocate
0x14004c7ff  mov     [rsp+78h+Size], 21D8h; Size
0x14004c808  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004c80f  nop     dword ptr [rax+rax+00h]
0x14004c814  mov     cs:?m_fInitialized@CClfsBaseFilePersisted@@0_NA, 1; bool CClfsBaseFilePersisted::m_fInitialized
0x14004c81b  xor     eax, eax
0x14004c81d  lea     rcx, ?m_laList@CClfsReadCompletionElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004c824  mov     [rsp+78h+Depth], ax; Depth
0x14004c829  mov     r9d, r15d; Flags
0x14004c82c  mov     [rsp+78h+Tag], 4B666C43h; Tag
0x14004c834  xor     r8d, r8d; Free
0x14004c837  xor     edx, edx; Allocate
0x14004c839  mov     [rsp+78h+Size], 70h ; 'p'; Size
0x14004c842  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004c849  nop     dword ptr [rax+rax+00h]
0x14004c84e  mov     cs:?m_fInitialize@CClfsReadCompletionElt@@0_NA, 1; bool CClfsReadCompletionElt::m_fInitialize
0x14004c855  call    ?InitializeGlobals@CClfsRequest@@SAJXZ; CClfsRequest::InitializeGlobals(void)
0x14004c85a  mov     ebx, eax
0x14004c85c  test    eax, eax
0x14004c85e  jns     short loc_14004C891
0x14004c860  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c867  cmp     rcx, rsi
0x14004c86a  jz      loc_14004C634
0x14004c870  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c875  jnb     loc_14004C634
0x14004c87b  mov     [rsp+78h+Tag], eax
0x14004c87f  mov     edx, 15h
0x14004c884  mov     dword ptr [rsp+78h+Size], 129h
0x14004c88c  jmp     loc_14004C625
0x14004c891  xor     eax, eax
0x14004c893  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004c89a  mov     [rsp+78h+Depth], ax; Depth
0x14004c89f  mov     r9d, r15d; Flags
0x14004c8a2  mov     [rsp+78h+Tag], 45666C43h; Tag
0x14004c8aa  xor     r8d, r8d; Free
0x14004c8ad  xor     edx, edx; Allocate
0x14004c8af  mov     [rsp+78h+Size], 110h; Size
0x14004c8b8  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004c8bf  nop     dword ptr [rax+rax+00h]
0x14004c8c4  mov     cs:?m_fInitialize@CClfsLogCcb@@0_NA, 1; bool CClfsLogCcb::m_fInitialize
0x14004c8cb  call    ?InitializeGlobals@CClfsLogFcbPhysical@@SAJXZ; CClfsLogFcbPhysical::InitializeGlobals(void)
0x14004c8d0  mov     ebx, eax
0x14004c8d2  test    eax, eax
0x14004c8d4  jns     short loc_14004C907
0x14004c8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c8dd  cmp     rcx, rsi
0x14004c8e0  jz      loc_14004C634
0x14004c8e6  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c8eb  jnb     loc_14004C634
0x14004c8f1  mov     [rsp+78h+Tag], eax
0x14004c8f5  mov     edx, 17h
0x14004c8fa  mov     dword ptr [rsp+78h+Size], 143h
0x14004c902  jmp     loc_14004C625
0x14004c907  xor     eax, eax
0x14004c909  lea     rcx, ?m_laList@CClfsLogFcbVirtual@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004c910  mov     [rsp+78h+Depth], ax; Depth
0x14004c915  mov     r9d, r15d; Flags
0x14004c918  mov     [rsp+78h+Tag], 44666C43h; Tag
0x14004c920  xor     r8d, r8d; Free
0x14004c923  xor     edx, edx; Allocate
0x14004c925  mov     [rsp+78h+Size], 298h; Size
0x14004c92e  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004c935  nop     dword ptr [rax+rax+00h]
0x14004c93a  xor     eax, eax
0x14004c93c  mov     cs:?m_fInitialize@CClfsLogFcbVirtual@@0_NA, 1; bool CClfsLogFcbVirtual::m_fInitialize
0x14004c943  mov     [rsp+78h+Depth], ax; Depth
0x14004c948  lea     rcx, ?m_laList@CClfsContainerFlushElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004c94f  mov     ebx, 46666C43h
0x14004c954  mov     r9d, r15d; Flags
0x14004c957  mov     [rsp+78h+Tag], ebx; Tag
0x14004c95b  xor     r8d, r8d; Free
0x14004c95e  xor     edx, edx; Allocate
0x14004c960  mov     [rsp+78h+Size], 0B0h; Size
0x14004c969  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004c970  nop     dword ptr [rax+rax+00h]
0x14004c975  xor     eax, eax
0x14004c977  mov     cs:?m_fInitialize@CClfsContainerFlushElt@@0_NA, 1; bool CClfsContainerFlushElt::m_fInitialize
0x14004c97e  mov     [rsp+78h+Depth], ax; Depth
0x14004c983  lea     rcx, ?m_laList@CClfsFlushElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14004c98a  mov     [rsp+78h+Tag], ebx; Tag
0x14004c98e  mov     r9d, r15d; Flags
0x14004c991  xor     r8d, r8d; Free
0x14004c994  mov     [rsp+78h+Size], 0F0h; Size
0x14004c99d  xor     edx, edx; Allocate
0x14004c99f  call    cs:__imp_ExInitializeNPagedLookasideList
0x14004c9a6  nop     dword ptr [rax+rax+00h]
0x14004c9ab  mov     cs:?m_fInitialize@CClfsFlushElt@@0_NA, 1; bool CClfsFlushElt::m_fInitialize
0x14004c9b2  mov     cs:?m_fInitialized@CClfsDriver@@0EA, 1; uchar CClfsDriver::m_fInitialized
0x14004c9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c9c0  cmp     rcx, rsi
0x14004c9c3  jz      short loc_14004C9E8
0x14004c9c5  bt      dword ptr [rcx+2Ch], 1Ah
0x14004c9ca  jnb     short loc_14004C9E8
0x14004c9cc  mov     rcx, [rcx+18h]
0x14004c9d0  mov     edx, 1Bh
0x14004c9d5  mov     r9, rbp
0x14004c9d8  mov     dword ptr [rsp+78h+Size], 173h
0x14004c9e0  mov     r8, r14
0x14004c9e3  call    WPP_SF_sd
0x14004c9e8  xor     eax, eax
0x14004c9ea  add     rsp, 48h
0x14004c9ee  pop     r15
0x14004c9f0  pop     r14
0x14004c9f2  pop     rdi
0x14004c9f3  pop     rsi
0x14004c9f4  pop     rbp
0x14004c9f5  pop     rbx
0x14004c9f6  retn
```
