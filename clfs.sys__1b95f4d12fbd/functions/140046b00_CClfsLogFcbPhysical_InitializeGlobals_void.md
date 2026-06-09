# CClfsLogFcbPhysical::InitializeGlobals(void)

- ea: `0x140046b00`
- end: `0x140046b7c`
- name: `?InitializeGlobals@CClfsLogFcbPhysical@@SAJXZ`
- size: `124`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14004c5a0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140046b2e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140046b2e`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140046b61`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140046b61`

## pseudocode

```c
__int64 CClfsLogFcbPhysical::InitializeGlobals(void)
{
  __int64 result; // rax

  ExInitializeNPagedLookasideList(&CClfsLogFcbPhysical::m_laList, 0, 0, 0x200u, 0x1620u, 0x43666C43u, 0);
  ExInitializePagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage, 0, 0, 0, 0x1000u, 0x73666C43u, 0);
  result = 0;
  CClfsLogFcbPhysical::m_fInitialize = 1;
  return result;
}

```

## disassembly

```asm
0x140046b00  sub     rsp, 48h
0x140046b04  xor     eax, eax
0x140046b06  lea     rcx, ?m_laList@CClfsLogFcbPhysical@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140046b0d  mov     [rsp+48h+Depth], ax; Depth
0x140046b12  mov     r9d, 200h; Flags
0x140046b18  mov     [rsp+48h+Tag], 43666C43h; Tag
0x140046b20  xor     r8d, r8d; Free
0x140046b23  xor     edx, edx; Allocate
0x140046b25  mov     [rsp+48h+Size], 1620h; Size
0x140046b2e  call    cs:__imp_ExInitializeNPagedLookasideList
0x140046b35  nop     dword ptr [rax+rax+00h]
0x140046b3a  xor     eax, eax
0x140046b3c  lea     rcx, ?m_laOwnerPage@CClfsLogFcbPhysical@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140046b43  mov     [rsp+48h+Depth], ax; Depth
0x140046b48  xor     r9d, r9d; Flags
0x140046b4b  mov     [rsp+48h+Tag], 73666C43h; Tag
0x140046b53  xor     r8d, r8d; Free
0x140046b56  xor     edx, edx; Allocate
0x140046b58  mov     [rsp+48h+Size], 1000h; Size
0x140046b61  call    cs:__imp_ExInitializePagedLookasideList
0x140046b68  nop     dword ptr [rax+rax+00h]
0x140046b6d  xor     eax, eax
0x140046b6f  mov     cs:?m_fInitialize@CClfsLogFcbPhysical@@0_NA, 1; bool CClfsLogFcbPhysical::m_fInitialize
0x140046b76  add     rsp, 48h
0x140046b7a  retn
```
