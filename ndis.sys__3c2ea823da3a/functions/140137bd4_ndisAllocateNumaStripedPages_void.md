# ndisAllocateNumaStripedPages(void)

- ea: `0x140137bd4`
- end: `0x140137e77`
- name: `?ndisAllocateNumaStripedPages@@YAPEAXXZ`
- size: `675`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1400c41cc`

## callees

- `0x14003e8b0`
- `0x140085f30`
- `0x1400c4154`
- `0x1400c4274`
- `0x1400e65c0`
- `0x140137bd4`
- `0x140138de0`
- `0x140145c44`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140137c2f`
- `ntoskrnl!MmSizeOfMdl` at `0x140137c2f`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140137beb`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140137beb`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140137c0e`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140137c0e`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x140137d6c`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x140137d6c`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140137d9d`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140137d9d`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140137dd2`
- `ntoskrnl!MmFreePagesFromMdl` at `0x140137dd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137e05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137e33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137de4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137e05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137e33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140137e50`
- `ntoskrnl!ExAllocatePool2` at `0x140137c4c`
- `ntoskrnl!ExAllocatePool2` at `0x140137cf5`
- `ntoskrnl!ExAllocatePool2` at `0x140137c4c`
- `ntoskrnl!ExAllocatePool2` at `0x140137cf5`

## pseudocode

```c
__int64 ndisAllocateNumaStripedPages(void)
{
  char v0; // r12
  ULONG v1; // edi
  SIZE_T v2; // r14
  __int64 v3; // rsi
  SIZE_T v4; // rax
  _OWORD *Pool2; // rax
  PMDL v6; // rbx
  size_t v7; // r14
  _QWORD *v8; // rax
  _QWORD *v9; // r15
  __int64 i; // r14
  int NodeIdForProcessor; // eax
  __int64 NodePagesForMdl; // rax
  __int64 v13; // r14
  struct _MDL *v14; // rcx
  void *v15; // rcx
  __int64 MappingAddress; // [rsp+80h] [rbp+40h] BYREF
  PMDL MemoryDescriptorList; // [rsp+88h] [rbp+48h] BYREF
  __int64 v19; // [rsp+90h] [rbp+50h]

  v0 = 1;
  v1 = KeQueryMaximumProcessorCountEx(0xFFFFu) + 1;
  v2 = v1 << 12;
  MappingAddress = (__int64)MmAllocateMappingAddress(v2, 0x6C53444Eu);
  v3 = MappingAddress;
  if ( !MappingAddress )
    goto LABEL_29;
  v4 = MmSizeOfMdl(0, (unsigned int)v2);
  Pool2 = (_OWORD *)ExAllocatePool2(64, v4, 1833780302);
  if ( Pool2 )
  {
    *Pool2 = 0;
    Pool2[1] = 0;
    Pool2[2] = 0;
    wistd::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>(
      &MemoryDescriptorList,
      Pool2);
  }
  else
  {
    wistd::unique_ptr<wchar_t,KFreePool<wchar_t>>::unique_ptr<wchar_t,KFreePool<wchar_t>>(&MemoryDescriptorList);
  }
  v6 = MemoryDescriptorList;
  if ( !MemoryDescriptorList )
    goto LABEL_29;
  MemoryDescriptorList->ByteCount = v2;
  v6->Next = 0;
  v6->StartVa = (PVOID)(v3 & 0xFFFFFFFFFFFFF000uLL);
  v6->ByteOffset = v3 & 0xFFF;
  v6->Size = 8 * (((v2 + (v3 & 0xFFF) + 4095) >> 12) + 6);
  v6->MdlFlags = 2;
  v7 = 8LL * v1;
  if ( !is_mul_ok(v1, 8u) )
    v7 = -1;
  v8 = (_QWORD *)ExAllocatePool2(256, v7, 1833780302);
  v9 = v8;
  if ( !v8 )
  {
    ExFreePoolWithTag(v6, 0);
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>(&MappingAddress);
    return 0;
  }
  memset(v8, 0, v7);
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
  {
    NodeIdForProcessor = ndisGetNodeIdForProcessor((_DWORD)i != 0 ? i - 1 : 0);
    MappingAddress = 4096;
    MemoryDescriptorList = (PMDL)-1LL;
    v19 = 0;
    NodePagesForMdl = MmAllocateNodePagesForMdlEx(0, -1, 4096, 4096, 1, NodeIdForProcessor, 5);
    v9[i] = NodePagesForMdl;
    if ( !NodePagesForMdl )
      goto LABEL_15;
    *((_QWORD *)&v6[1].Next + i) = *(_QWORD *)(NodePagesForMdl + 48);
  }
  if ( MmMapLockedPagesWithReservedMapping((PVOID)v3, 0x6C53444Eu, v6, MmCached) )
  {
    v0 = 0;
    goto LABEL_16;
  }
LABEL_15:
  ndisFreeMappingAddress((void *)v3);
  v3 = 0;
LABEL_16:
  if ( v1 )
  {
    v13 = 0;
    if ( v0 )
    {
      do
      {
        v14 = (struct _MDL *)v9[v13];
        if ( v14 )
        {
          MmFreePagesFromMdl(v14);
          ExFreePoolWithTag((PVOID)v9[v13], 0);
        }
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < v1 );
    }
    else
    {
      do
      {
        v15 = (void *)v9[v13];
        if ( v15 )
          ExFreePoolWithTag(v15, 0);
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < v1 );
    }
  }
  MappingAddress = 0;
  operator delete[](v9);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>(&MappingAddress);
  return v3;
}

```

## disassembly

```asm
0x140137bd4  push    rbp
0x140137bd6  push    rbx
0x140137bd7  push    rsi
0x140137bd8  push    rdi
0x140137bd9  push    r12
0x140137bdb  push    r14
0x140137bdd  push    r15
0x140137bdf  mov     rbp, rsp
0x140137be2  sub     rsp, 40h
0x140137be6  mov     ecx, 0FFFFh; GroupNumber
0x140137beb  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140137bf2  nop     dword ptr [rax+rax+00h]
0x140137bf7  mov     r12d, 1
0x140137bfd  mov     edx, 6C53444Eh; PoolTag
0x140137c02  lea     edi, [r12+rax]
0x140137c06  mov     ecx, edi
0x140137c08  shl     ecx, 0Ch; NumberOfBytes
0x140137c0b  mov     r14d, ecx
0x140137c0e  call    cs:__imp_MmAllocateMappingAddress
0x140137c15  nop     dword ptr [rax+rax+00h]
0x140137c1a  mov     [rbp+arg_0], rax
0x140137c1e  mov     rsi, rax
0x140137c21  test    rax, rax
0x140137c24  jz      loc_140137E5C
0x140137c2a  mov     edx, r14d; Length
0x140137c2d  xor     ecx, ecx; Base
0x140137c2f  call    cs:__imp_MmSizeOfMdl
0x140137c36  nop     dword ptr [rax+rax+00h]
0x140137c3b  mov     r15d, 6D4D444Eh
0x140137c41  lea     ecx, [r12+3Fh]
0x140137c46  mov     r8d, r15d
0x140137c49  mov     rdx, rax
0x140137c4c  call    cs:__imp_ExAllocatePool2
0x140137c53  nop     dword ptr [rax+rax+00h]
0x140137c58  lea     rcx, [rbp+MemoryDescriptorList]
0x140137c5c  test    rax, rax
0x140137c5f  jnz     short loc_140137C68
0x140137c61  call    ??$?0$00X@?$unique_ptr@_WU?$KFreePool@_W@@@wistd@@QEAA@$$T@Z; wistd::unique_ptr<wchar_t,KFreePool<wchar_t>>::unique_ptr<wchar_t,KFreePool<wchar_t>>(std::nullptr_t)
0x140137c66  jmp     short loc_140137C7E
0x140137c68  xorps   xmm0, xmm0
0x140137c6b  mov     rdx, rax
0x140137c6e  movups  xmmword ptr [rax], xmm0
0x140137c71  movups  xmmword ptr [rax+10h], xmm0
0x140137c75  movups  xmmword ptr [rax+20h], xmm0
0x140137c79  call    ??$?0$00X@?$unique_ptr@VInterfaceProfileKnobCollection@@U?$KFreePool@VInterfaceProfileKnobCollection@@@@@wistd@@QEAA@PEAVInterfaceProfileKnobCollection@@@Z; wistd::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>(InterfaceProfileKnobCollection *)
0x140137c7e  mov     rbx, [rbp+MemoryDescriptorList]
0x140137c82  test    rbx, rbx
0x140137c85  jz      loc_140137E5C
0x140137c8b  mov     r9d, 0FFFh
0x140137c91  mov     [rbx+28h], r14d
0x140137c95  mov     edx, esi
0x140137c97  mov     qword ptr [rbx], 0
0x140137c9e  mov     ecx, edx
0x140137ca0  mov     rax, rsi
0x140137ca3  and     rcx, r9
0x140137ca6  and     rax, 0FFFFFFFFFFFFF000h
0x140137cac  add     rcx, r9
0x140137caf  mov     [rbx+20h], rax
0x140137cb3  add     rcx, r14
0x140137cb6  and     edx, r9d
0x140137cb9  shr     rcx, 0Ch
0x140137cbd  mov     eax, 8
0x140137cc2  add     cx, 6
0x140137cc6  mov     [rbx+2Ch], edx
0x140137cc9  shl     cx, 3
0x140137ccd  mov     r8d, r15d
0x140137cd0  mov     [rbx+8], cx
0x140137cd4  mov     ecx, edi
0x140137cd6  mul     rcx
0x140137cd9  mov     ecx, 100h
0x140137cde  mov     word ptr [rbx+0Ah], 2
0x140137ce4  mov     r14, rax
0x140137ce7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140137cee  cmovb   r14, rax
0x140137cf2  mov     rdx, r14
0x140137cf5  call    cs:__imp_ExAllocatePool2
0x140137cfc  nop     dword ptr [rax+rax+00h]
0x140137d01  xor     edx, edx; Tag
0x140137d03  mov     r15, rax
0x140137d06  test    rax, rax
0x140137d09  jz      loc_140137E4D
0x140137d0f  mov     r8, r14; Size
0x140137d12  mov     rcx, rax; void *
0x140137d15  call    memset
0x140137d1a  xor     r14d, r14d
0x140137d1d  cmp     r14d, edi
0x140137d20  jnb     short loc_140137D8F
0x140137d22  mov     eax, r14d
0x140137d25  lea     edx, [r14-1]
0x140137d29  neg     eax
0x140137d2b  sbb     ecx, ecx
0x140137d2d  and     ecx, edx; ProcIndex
0x140137d2f  call    ndisGetNodeIdForProcessor
0x140137d34  mov     edx, 1000h
0x140137d39  mov     [rsp+40h+var_10], 5
0x140137d41  mov     [rbp+arg_0], rdx
0x140137d45  mov     r9d, edx
0x140137d48  mov     r8d, edx
0x140137d4b  mov     [rsp+40h+var_18], eax
0x140137d4f  mov     [rbp+MemoryDescriptorList], 0FFFFFFFFFFFFFFFFh
0x140137d57  mov     rdx, [rbp+MemoryDescriptorList]
0x140137d5b  mov     [rbp+arg_10], 0
0x140137d63  mov     rcx, [rbp+arg_10]
0x140137d67  mov     [rsp+40h+var_20], r12d
0x140137d6c  call    cs:__imp_MmAllocateNodePagesForMdlEx
0x140137d73  nop     dword ptr [rax+rax+00h]
0x140137d78  mov     [r15+r14*8], rax
0x140137d7c  test    rax, rax
0x140137d7f  jz      short loc_140137DB3
0x140137d81  mov     rax, [rax+30h]
0x140137d85  mov     [rbx+r14*8+30h], rax
0x140137d8a  add     r14d, r12d
0x140137d8d  jmp     short loc_140137D1D
0x140137d8f  mov     r9d, r12d; CacheType
0x140137d92  mov     r8, rbx; MemoryDescriptorList
0x140137d95  mov     edx, 6C53444Eh; PoolTag
0x140137d9a  mov     rcx, rsi; MappingAddress
0x140137d9d  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140137da4  nop     dword ptr [rax+rax+00h]
0x140137da9  test    rax, rax
0x140137dac  jz      short loc_140137DB3
0x140137dae  xor     r12b, r12b
0x140137db1  jmp     short loc_140137DBD
0x140137db3  mov     rcx, rsi; void *
0x140137db6  call    ?ndisFreeMappingAddress@@YAXPEAX@Z; ndisFreeMappingAddress(void *)
0x140137dbb  xor     esi, esi
0x140137dbd  test    edi, edi
0x140137dbf  jz      short loc_140137E19
0x140137dc1  xor     r14d, r14d
0x140137dc4  test    r12b, r12b
0x140137dc7  jz      short loc_140137DFA
0x140137dc9  mov     rcx, [r15+r14*8]; MemoryDescriptorList
0x140137dcd  test    rcx, rcx
0x140137dd0  jz      short loc_140137DF0
0x140137dd2  call    cs:__imp_MmFreePagesFromMdl
0x140137dd9  nop     dword ptr [rax+rax+00h]
0x140137dde  mov     rcx, [r15+r14*8]; P
0x140137de2  xor     edx, edx; Tag
0x140137de4  call    cs:__imp_ExFreePoolWithTag
0x140137deb  nop     dword ptr [rax+rax+00h]
0x140137df0  inc     r14d
0x140137df3  cmp     r14d, edi
0x140137df6  jb      short loc_140137DC9
0x140137df8  jmp     short loc_140137E19
0x140137dfa  mov     rcx, [r15+r14*8]; P
0x140137dfe  test    rcx, rcx
0x140137e01  jz      short loc_140137E11
0x140137e03  xor     edx, edx; Tag
0x140137e05  call    cs:__imp_ExFreePoolWithTag
0x140137e0c  nop     dword ptr [rax+rax+00h]
0x140137e11  inc     r14d
0x140137e14  cmp     r14d, edi
0x140137e17  jb      short loc_140137DFA
0x140137e19  mov     rcx, r15; void *
0x140137e1c  mov     [rbp+arg_0], 0
0x140137e24  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140137e29  test    rbx, rbx
0x140137e2c  jz      short loc_140137E3F
0x140137e2e  xor     edx, edx; Tag
0x140137e30  mov     rcx, rbx; P
0x140137e33  call    cs:__imp_ExFreePoolWithTag
0x140137e3a  nop     dword ptr [rax+rax+00h]
0x140137e3f  lea     rcx, [rbp+arg_0]
0x140137e43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ndisFreeMappingAddress@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>(void)
0x140137e48  mov     rax, rsi
0x140137e4b  jmp     short loc_140137E67
0x140137e4d  mov     rcx, rbx; P
0x140137e50  call    cs:__imp_ExFreePoolWithTag
0x140137e57  nop     dword ptr [rax+rax+00h]
0x140137e5c  lea     rcx, [rbp+arg_0]
0x140137e60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ndisFreeMappingAddress@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>(void)
0x140137e65  xor     eax, eax
0x140137e67  add     rsp, 40h
0x140137e6b  pop     r15
0x140137e6d  pop     r14
0x140137e6f  pop     r12
0x140137e71  pop     rdi
0x140137e72  pop     rsi
0x140137e73  pop     rbx
0x140137e74  pop     rbp
0x140137e75  retn
```
