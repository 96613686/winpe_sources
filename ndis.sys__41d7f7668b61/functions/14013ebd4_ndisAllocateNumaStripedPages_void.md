# ndisAllocateNumaStripedPages(void)

- ea: `0x14013ebd4`
- end: `0x14013ee77`
- name: `?ndisAllocateNumaStripedPages@@YAPEAXXZ`
- size: `675`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1400c937c`

## callees

- `0x140041060`
- `0x14008b1b0`
- `0x1400c9304`
- `0x1400c9424`
- `0x1400eb7c0`
- `0x14013ebd4`
- `0x14013fde0`
- `0x14014cbe4`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14013ec2f`
- `ntoskrnl!MmSizeOfMdl` at `0x14013ec2f`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14013ebeb`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14013ebeb`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14013ec0e`
- `ntoskrnl!MmAllocateMappingAddress` at `0x14013ec0e`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14013ed6c`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14013ed6c`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14013ed9d`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14013ed9d`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14013edd2`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14013edd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ede4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ee05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ee33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ee50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ede4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ee05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ee33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013ee50`
- `ntoskrnl!ExAllocatePool2` at `0x14013ec4c`
- `ntoskrnl!ExAllocatePool2` at `0x14013ecf5`
- `ntoskrnl!ExAllocatePool2` at `0x14013ec4c`
- `ntoskrnl!ExAllocatePool2` at `0x14013ecf5`

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
0x14013ebd4  push    rbp
0x14013ebd6  push    rbx
0x14013ebd7  push    rsi
0x14013ebd8  push    rdi
0x14013ebd9  push    r12
0x14013ebdb  push    r14
0x14013ebdd  push    r15
0x14013ebdf  mov     rbp, rsp
0x14013ebe2  sub     rsp, 40h
0x14013ebe6  mov     ecx, 0FFFFh; GroupNumber
0x14013ebeb  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14013ebf2  nop     dword ptr [rax+rax+00h]
0x14013ebf7  mov     r12d, 1
0x14013ebfd  mov     edx, 6C53444Eh; PoolTag
0x14013ec02  lea     edi, [r12+rax]
0x14013ec06  mov     ecx, edi
0x14013ec08  shl     ecx, 0Ch; NumberOfBytes
0x14013ec0b  mov     r14d, ecx
0x14013ec0e  call    cs:__imp_MmAllocateMappingAddress
0x14013ec15  nop     dword ptr [rax+rax+00h]
0x14013ec1a  mov     [rbp+arg_0], rax
0x14013ec1e  mov     rsi, rax
0x14013ec21  test    rax, rax
0x14013ec24  jz      loc_14013EE5C
0x14013ec2a  mov     edx, r14d; Length
0x14013ec2d  xor     ecx, ecx; Base
0x14013ec2f  call    cs:__imp_MmSizeOfMdl
0x14013ec36  nop     dword ptr [rax+rax+00h]
0x14013ec3b  mov     r15d, 6D4D444Eh
0x14013ec41  lea     ecx, [r12+3Fh]
0x14013ec46  mov     r8d, r15d
0x14013ec49  mov     rdx, rax
0x14013ec4c  call    cs:__imp_ExAllocatePool2
0x14013ec53  nop     dword ptr [rax+rax+00h]
0x14013ec58  lea     rcx, [rbp+MemoryDescriptorList]
0x14013ec5c  test    rax, rax
0x14013ec5f  jnz     short loc_14013EC68
0x14013ec61  call    ??$?0$00X@?$unique_ptr@_WU?$KFreePool@_W@@@wistd@@QEAA@$$T@Z; wistd::unique_ptr<wchar_t,KFreePool<wchar_t>>::unique_ptr<wchar_t,KFreePool<wchar_t>>(std::nullptr_t)
0x14013ec66  jmp     short loc_14013EC7E
0x14013ec68  xorps   xmm0, xmm0
0x14013ec6b  mov     rdx, rax
0x14013ec6e  movups  xmmword ptr [rax], xmm0
0x14013ec71  movups  xmmword ptr [rax+10h], xmm0
0x14013ec75  movups  xmmword ptr [rax+20h], xmm0
0x14013ec79  call    ??$?0$00X@?$unique_ptr@VInterfaceProfileKnobCollection@@U?$KFreePool@VInterfaceProfileKnobCollection@@@@@wistd@@QEAA@PEAVInterfaceProfileKnobCollection@@@Z; wistd::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>::unique_ptr<InterfaceProfileKnobCollection,KFreePool<InterfaceProfileKnobCollection>>(InterfaceProfileKnobCollection *)
0x14013ec7e  mov     rbx, [rbp+MemoryDescriptorList]
0x14013ec82  test    rbx, rbx
0x14013ec85  jz      loc_14013EE5C
0x14013ec8b  mov     r9d, 0FFFh
0x14013ec91  mov     [rbx+28h], r14d
0x14013ec95  mov     edx, esi
0x14013ec97  mov     qword ptr [rbx], 0
0x14013ec9e  mov     ecx, edx
0x14013eca0  mov     rax, rsi
0x14013eca3  and     rcx, r9
0x14013eca6  and     rax, 0FFFFFFFFFFFFF000h
0x14013ecac  add     rcx, r9
0x14013ecaf  mov     [rbx+20h], rax
0x14013ecb3  add     rcx, r14
0x14013ecb6  and     edx, r9d
0x14013ecb9  shr     rcx, 0Ch
0x14013ecbd  mov     eax, 8
0x14013ecc2  add     cx, 6
0x14013ecc6  mov     [rbx+2Ch], edx
0x14013ecc9  shl     cx, 3
0x14013eccd  mov     r8d, r15d
0x14013ecd0  mov     [rbx+8], cx
0x14013ecd4  mov     ecx, edi
0x14013ecd6  mul     rcx
0x14013ecd9  mov     ecx, 100h
0x14013ecde  mov     word ptr [rbx+0Ah], 2
0x14013ece4  mov     r14, rax
0x14013ece7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14013ecee  cmovb   r14, rax
0x14013ecf2  mov     rdx, r14
0x14013ecf5  call    cs:__imp_ExAllocatePool2
0x14013ecfc  nop     dword ptr [rax+rax+00h]
0x14013ed01  xor     edx, edx; Tag
0x14013ed03  mov     r15, rax
0x14013ed06  test    rax, rax
0x14013ed09  jz      loc_14013EE4D
0x14013ed0f  mov     r8, r14; Size
0x14013ed12  mov     rcx, rax; void *
0x14013ed15  call    memset
0x14013ed1a  xor     r14d, r14d
0x14013ed1d  cmp     r14d, edi
0x14013ed20  jnb     short loc_14013ED8F
0x14013ed22  mov     eax, r14d
0x14013ed25  lea     edx, [r14-1]
0x14013ed29  neg     eax
0x14013ed2b  sbb     ecx, ecx
0x14013ed2d  and     ecx, edx; ProcIndex
0x14013ed2f  call    ndisGetNodeIdForProcessor
0x14013ed34  mov     edx, 1000h
0x14013ed39  mov     [rsp+40h+var_10], 5
0x14013ed41  mov     [rbp+arg_0], rdx
0x14013ed45  mov     r9d, edx
0x14013ed48  mov     r8d, edx
0x14013ed4b  mov     [rsp+40h+var_18], eax
0x14013ed4f  mov     [rbp+MemoryDescriptorList], 0FFFFFFFFFFFFFFFFh
0x14013ed57  mov     rdx, [rbp+MemoryDescriptorList]
0x14013ed5b  mov     [rbp+arg_10], 0
0x14013ed63  mov     rcx, [rbp+arg_10]
0x14013ed67  mov     [rsp+40h+var_20], r12d
0x14013ed6c  call    cs:__imp_MmAllocateNodePagesForMdlEx
0x14013ed73  nop     dword ptr [rax+rax+00h]
0x14013ed78  mov     [r15+r14*8], rax
0x14013ed7c  test    rax, rax
0x14013ed7f  jz      short loc_14013EDB3
0x14013ed81  mov     rax, [rax+30h]
0x14013ed85  mov     [rbx+r14*8+30h], rax
0x14013ed8a  add     r14d, r12d
0x14013ed8d  jmp     short loc_14013ED1D
0x14013ed8f  mov     r9d, r12d; CacheType
0x14013ed92  mov     r8, rbx; MemoryDescriptorList
0x14013ed95  mov     edx, 6C53444Eh; PoolTag
0x14013ed9a  mov     rcx, rsi; MappingAddress
0x14013ed9d  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x14013eda4  nop     dword ptr [rax+rax+00h]
0x14013eda9  test    rax, rax
0x14013edac  jz      short loc_14013EDB3
0x14013edae  xor     r12b, r12b
0x14013edb1  jmp     short loc_14013EDBD
0x14013edb3  mov     rcx, rsi; void *
0x14013edb6  call    ?ndisFreeMappingAddress@@YAXPEAX@Z; ndisFreeMappingAddress(void *)
0x14013edbb  xor     esi, esi
0x14013edbd  test    edi, edi
0x14013edbf  jz      short loc_14013EE19
0x14013edc1  xor     r14d, r14d
0x14013edc4  test    r12b, r12b
0x14013edc7  jz      short loc_14013EDFA
0x14013edc9  mov     rcx, [r15+r14*8]; MemoryDescriptorList
0x14013edcd  test    rcx, rcx
0x14013edd0  jz      short loc_14013EDF0
0x14013edd2  call    cs:__imp_MmFreePagesFromMdl
0x14013edd9  nop     dword ptr [rax+rax+00h]
0x14013edde  mov     rcx, [r15+r14*8]; P
0x14013ede2  xor     edx, edx; Tag
0x14013ede4  call    cs:__imp_ExFreePoolWithTag
0x14013edeb  nop     dword ptr [rax+rax+00h]
0x14013edf0  inc     r14d
0x14013edf3  cmp     r14d, edi
0x14013edf6  jb      short loc_14013EDC9
0x14013edf8  jmp     short loc_14013EE19
0x14013edfa  mov     rcx, [r15+r14*8]; P
0x14013edfe  test    rcx, rcx
0x14013ee01  jz      short loc_14013EE11
0x14013ee03  xor     edx, edx; Tag
0x14013ee05  call    cs:__imp_ExFreePoolWithTag
0x14013ee0c  nop     dword ptr [rax+rax+00h]
0x14013ee11  inc     r14d
0x14013ee14  cmp     r14d, edi
0x14013ee17  jb      short loc_14013EDFA
0x14013ee19  mov     rcx, r15; void *
0x14013ee1c  mov     [rbp+arg_0], 0
0x14013ee24  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x14013ee29  test    rbx, rbx
0x14013ee2c  jz      short loc_14013EE3F
0x14013ee2e  xor     edx, edx; Tag
0x14013ee30  mov     rcx, rbx; P
0x14013ee33  call    cs:__imp_ExFreePoolWithTag
0x14013ee3a  nop     dword ptr [rax+rax+00h]
0x14013ee3f  lea     rcx, [rbp+arg_0]
0x14013ee43  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ndisFreeMappingAddress@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>(void)
0x14013ee48  mov     rax, rsi
0x14013ee4b  jmp     short loc_14013EE67
0x14013ee4d  mov     rcx, rbx; P
0x14013ee50  call    cs:__imp_ExFreePoolWithTag
0x14013ee57  nop     dword ptr [rax+rax+00h]
0x14013ee5c  lea     rcx, [rbp+arg_0]
0x14013ee60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ndisFreeMappingAddress@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ndisFreeMappingAddress(void *),wistd::integral_constant<unsigned __int64,1>,void *,void *,0,std::nullptr_t>>(void)
0x14013ee65  xor     eax, eax
0x14013ee67  add     rsp, 40h
0x14013ee6b  pop     r15
0x14013ee6d  pop     r14
0x14013ee6f  pop     r12
0x14013ee71  pop     rdi
0x14013ee72  pop     rsi
0x14013ee73  pop     rbx
0x14013ee74  pop     rbp
0x14013ee75  retn
```
