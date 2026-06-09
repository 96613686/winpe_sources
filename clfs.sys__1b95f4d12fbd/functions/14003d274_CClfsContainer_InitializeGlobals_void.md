# CClfsContainer::InitializeGlobals(void)

- ea: `0x14003d274`
- end: `0x14003d35e`
- name: `?InitializeGlobals@CClfsContainer@@SAJXZ`
- size: `234`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004c5a0`

## callees

- `0x140018280`
- `0x14003d274`
- `0x14003d56c`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003d33d`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14003d33d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d2e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d2e7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d2a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d2a4`

## pseudocode

```c
__int64 CClfsContainer::InitializeGlobals(void)
{
  PVOID PoolWithTag; // rax
  int v2; // ebx

  memset(&CClfsContainer::m_rgInitPageSegments, 0, 0x2000u);
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x1000u, 0x4F666C43u);
  CClfsContainer::m_pbZeroPage = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, 0x1000u);
  v2 = CClfsContainer::InitializeSecurityDescriptors();
  if ( v2 >= 0 )
  {
    memset64(&CClfsContainer::m_rgInitPageSegments, (unsigned __int64)CClfsContainer::m_pbZeroPage, 0x400u);
    ExInitializePagedLookasideList(&CClfsContainer::m_laList, 0, 0, 0, 0x90u, 0x41666C43u, 0);
    CClfsContainer::m_fInitialize = 1;
  }
  else
  {
    ExFreePoolWithTag(CClfsContainer::m_pbZeroPage, 0);
    CClfsContainer::m_pbZeroPage = 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14003d274  mov     [rsp+arg_0], rbx
0x14003d279  push    rdi
0x14003d27a  sub     rsp, 40h
0x14003d27e  xor     edx, edx; Val
0x14003d280  lea     rcx, ?m_rgInitPageSegments@CClfsContainer@@0PAT_FILE_SEGMENT_ELEMENT@@A; void *
0x14003d287  mov     r8d, 2000h; Size
0x14003d28d  call    memset
0x14003d292  mov     edi, 1000h
0x14003d297  mov     r8d, 4F666C43h; Tag
0x14003d29d  mov     edx, edi; NumberOfBytes
0x14003d29f  mov     ecx, 1; PoolType
0x14003d2a4  call    cs:__imp_ExAllocatePoolWithTag
0x14003d2ab  nop     dword ptr [rax+rax+00h]
0x14003d2b0  mov     cs:?m_pbZeroPage@CClfsContainer@@0PEAEEA, rax; uchar * CClfsContainer::m_pbZeroPage
0x14003d2b7  test    rax, rax
0x14003d2ba  jnz     short loc_14003D2C6
0x14003d2bc  mov     eax, 0C000009Ah
0x14003d2c1  jmp     loc_14003D352
0x14003d2c6  mov     r8, rdi; Size
0x14003d2c9  xor     edx, edx; Val
0x14003d2cb  mov     rcx, rax; void *
0x14003d2ce  call    memset
0x14003d2d3  call    ?InitializeSecurityDescriptors@CClfsContainer@@CAJXZ; CClfsContainer::InitializeSecurityDescriptors(void)
0x14003d2d8  mov     ebx, eax
0x14003d2da  test    eax, eax
0x14003d2dc  jns     short loc_14003D300
0x14003d2de  mov     rcx, cs:?m_pbZeroPage@CClfsContainer@@0PEAEEA; P
0x14003d2e5  xor     edx, edx; Tag
0x14003d2e7  call    cs:__imp_ExFreePoolWithTag
0x14003d2ee  nop     dword ptr [rax+rax+00h]
0x14003d2f3  mov     cs:?m_pbZeroPage@CClfsContainer@@0PEAEEA, 0; uchar * CClfsContainer::m_pbZeroPage
0x14003d2fe  jmp     short loc_14003D350
0x14003d300  mov     rax, cs:?m_pbZeroPage@CClfsContainer@@0PEAEEA; uchar * CClfsContainer::m_pbZeroPage
0x14003d307  lea     rdi, ?m_rgInitPageSegments@CClfsContainer@@0PAT_FILE_SEGMENT_ELEMENT@@A; _FILE_SEGMENT_ELEMENT near * CClfsContainer::m_rgInitPageSegments
0x14003d30e  mov     ecx, 400h
0x14003d313  xor     r9d, r9d; Flags
0x14003d316  rep stosq
0x14003d319  xor     eax, eax
0x14003d31b  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14003d322  mov     [rsp+48h+Depth], ax; Depth
0x14003d327  xor     r8d, r8d; Free
0x14003d32a  mov     [rsp+48h+Tag], 41666C43h; Tag
0x14003d332  xor     edx, edx; Allocate
0x14003d334  mov     [rsp+48h+Size], 90h; Size
0x14003d33d  call    cs:__imp_ExInitializePagedLookasideList
0x14003d344  nop     dword ptr [rax+rax+00h]
0x14003d349  mov     cs:?m_fInitialize@CClfsContainer@@0_NA, 1; bool CClfsContainer::m_fInitialize
0x14003d350  mov     eax, ebx
0x14003d352  mov     rbx, [rsp+48h+arg_0]
0x14003d357  add     rsp, 40h
0x14003d35b  pop     rdi
0x14003d35c  retn
```
