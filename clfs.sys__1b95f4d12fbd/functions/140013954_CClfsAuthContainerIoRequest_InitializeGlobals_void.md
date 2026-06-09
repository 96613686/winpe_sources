# CClfsAuthContainerIoRequest::InitializeGlobals(void)

- ea: `0x140013954`
- end: `0x1400139d3`
- name: `?InitializeGlobals@CClfsAuthContainerIoRequest@@SAJXZ`
- size: `127`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x14004c5a0`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140013982`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400139b8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140013982`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400139b8`

## pseudocode

```c
__int64 CClfsAuthContainerIoRequest::InitializeGlobals(void)
{
  __int64 result; // rax

  ExInitializeNPagedLookasideList(&CClfsAuthContainerIoRequest::m_laList, 0, 0, 0x200u, 0x1A8u, 0x61664C43u, 0);
  ExInitializeNPagedLookasideList(&CClfsAuthContainerIoRequest::m_laAvlList, 0, 0, 0x200u, 0x78u, 0x64664C43u, 0);
  result = 0;
  CClfsAuthContainerIoRequest::m_fGlobalInitialize = 1;
  return result;
}

```

## disassembly

```asm
0x140013954  sub     rsp, 48h
0x140013958  xor     eax, eax
0x14001395a  lea     rcx, ?m_laList@CClfsAuthContainerIoRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140013961  mov     [rsp+48h+Depth], ax; Depth
0x140013966  mov     r9d, 200h; Flags
0x14001396c  mov     [rsp+48h+Tag], 61664C43h; Tag
0x140013974  xor     r8d, r8d; Free
0x140013977  xor     edx, edx; Allocate
0x140013979  mov     [rsp+48h+Size], 1A8h; Size
0x140013982  call    cs:__imp_ExInitializeNPagedLookasideList
0x140013989  nop     dword ptr [rax+rax+00h]
0x14001398e  xor     eax, eax
0x140013990  lea     rcx, ?m_laAvlList@CClfsAuthContainerIoRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140013997  mov     [rsp+48h+Depth], ax; Depth
0x14001399c  mov     r9d, 200h; Flags
0x1400139a2  mov     [rsp+48h+Tag], 64664C43h; Tag
0x1400139aa  xor     r8d, r8d; Free
0x1400139ad  xor     edx, edx; Allocate
0x1400139af  mov     [rsp+48h+Size], 78h ; 'x'; Size
0x1400139b8  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400139bf  nop     dword ptr [rax+rax+00h]
0x1400139c4  xor     eax, eax
0x1400139c6  mov     cs:?m_fGlobalInitialize@CClfsAuthContainerIoRequest@@0_NA, 1; bool CClfsAuthContainerIoRequest::m_fGlobalInitialize
0x1400139cd  add     rsp, 48h
0x1400139d1  retn
```
