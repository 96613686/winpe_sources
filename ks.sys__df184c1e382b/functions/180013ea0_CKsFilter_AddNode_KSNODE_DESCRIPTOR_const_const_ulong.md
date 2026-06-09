# CKsFilter::AddNode(_KSNODE_DESCRIPTOR const * const,ulong *)

- ea: `0x180013ea0`
- end: `0x1800140a2`
- name: `?AddNode@CKsFilter@@QEAAJQEBU_KSNODE_DESCRIPTOR@@PEAK@Z`
- size: `514`
- prototype: `__int64 __fastcall(CKsFilter *this, struct _KSNODE_DESCRIPTOR *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003d270`

## callees

- `0x18000ffa4`
- `0x1800100a8`
- `0x180013ea0`
- `0x180019d00`
- `0x18001a000`
- `0x18004dbc0`
- `0x18004eb9c`
- `0x18004ed60`
- `0x18005b4e8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18001407b`
- `ntoskrnl!KeReleaseMutex` at `0x18001407b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180013ef8`
- `ntoskrnl!KeWaitForSingleObject` at `0x180013ef8`

## pseudocode

```c
__int64 __fastcall CKsFilter::AddNode(CKsFilter *this, struct _KSNODE_DESCRIPTOR *a2, unsigned int *a3)
{
  _KSFILTER *p_Public; // rsi
  const KSFILTER_DESCRIPTOR *Descriptor; // rax
  size_t NodeDescriptorSize; // rbp
  ULONG NodeDescriptorsCount; // r13d
  NTSTATUS AutomationTableTable; // edi
  unsigned int v10; // r15d
  __int64 v11; // r12
  NTSTATUS v12; // eax
  const KSFILTER_DESCRIPTOR *v13; // rax
  KSAUTOMATION_TABLE_ **m_NodeAutomationTables; // rdx
  PVOID Item; // [rsp+70h] [rbp+8h] BYREF
  void *Src; // [rsp+78h] [rbp+10h]
  unsigned int *v17; // [rsp+80h] [rbp+18h]

  v17 = a3;
  Src = a2;
  p_Public = &this->m_Ext.Public;
  Descriptor = this->m_Ext.Public.Descriptor;
  NodeDescriptorSize = Descriptor->NodeDescriptorSize;
  if ( !(_DWORD)NodeDescriptorSize )
    return 3221225485LL;
  NodeDescriptorsCount = Descriptor->NodeDescriptorsCount;
  KeWaitForSingleObject(&this->m_ControlMutex, Executive, 0, 0, 0);
  CKsFilter::HoldProcessing(this);
  AutomationTableTable = KsEdit(this->m_Ext.Public.Bag, (PVOID *)p_Public, 0x68u, 0x68u, 0x6466534Bu);
  if ( AutomationTableTable >= 0 )
  {
    v10 = NodeDescriptorsCount + 1;
    v11 = (unsigned int)NodeDescriptorSize * NodeDescriptorsCount;
    v12 = KsEdit(
            this->m_Ext.Public.Bag,
            (PVOID *)&p_Public->Descriptor->NodeDescriptors,
            (NodeDescriptorsCount + 1) * NodeDescriptorSize,
            NodeDescriptorSize * NodeDescriptorsCount,
            0x646E534Bu);
    Item = 0;
    AutomationTableTable = v12;
    if ( v12 >= 0 )
    {
      memmove((char *)p_Public->Descriptor->NodeDescriptors + v11, Src, NodeDescriptorSize);
      AutomationTableTable = KspCreateAutomationTableTable(
                               (int)&Item,
                               this->m_NodesCount + 1,
                               NodeDescriptorSize,
                               (int)p_Public->Descriptor->NodeDescriptors,
                               0,
                               this->m_Ext.Public.Bag);
      v13 = p_Public->Descriptor;
      if ( AutomationTableTable >= 0 )
      {
        v13->NodeDescriptorsCount = v10;
        this->m_NodesCount = v10;
        if ( (unsigned int)CKsFilter::ConstructDefaultTopology(this) )
        {
          m_NodeAutomationTables = (KSAUTOMATION_TABLE_ **)this->m_NodeAutomationTables;
          if ( m_NodeAutomationTables )
            KsRemoveItemFromObjectBag(this->m_Ext.Public.Bag, m_NodeAutomationTables, 1u);
          this->m_NodeAutomationTables = (KSAUTOMATION_TABLE_ *const *)Item;
          *v17 = NodeDescriptorsCount;
        }
        else
        {
          --p_Public->Descriptor->NodeDescriptorsCount;
          --this->m_NodesCount;
          memset(
            (char *)p_Public->Descriptor->NodeDescriptors
          + (NodeDescriptorsCount + 1) * (unsigned int)NodeDescriptorSize,
            0,
            NodeDescriptorSize);
          KsRemoveItemFromObjectBag(this->m_Ext.Public.Bag, Item, 1u);
          AutomationTableTable = -1073741670;
        }
      }
      else
      {
        memset((char *)v13->NodeDescriptors + v11, 0, NodeDescriptorSize);
      }
    }
  }
  CKsFilter::RestoreProcessing(this);
  KeReleaseMutex(&this->m_ControlMutex, 0);
  return (unsigned int)AutomationTableTable;
}

```

## disassembly

```asm
0x180013ea0  mov     [rsp+arg_18], rbx
0x180013ea5  mov     [rsp+arg_10], r8
0x180013eaa  mov     [rsp+Src], rdx
0x180013eaf  push    rbp
0x180013eb0  push    rsi
0x180013eb1  push    rdi
0x180013eb2  push    r12
0x180013eb4  push    r13
0x180013eb6  push    r14
0x180013eb8  push    r15
0x180013eba  sub     rsp, 30h
0x180013ebe  lea     rsi, [rcx+0D8h]
0x180013ec5  mov     rbx, rcx
0x180013ec8  mov     rax, [rsi]
0x180013ecb  mov     ebp, [rax+44h]
0x180013ece  test    ebp, ebp
0x180013ed0  jnz     short loc_180013EDC
0x180013ed2  mov     eax, 0C000000Dh
0x180013ed7  jmp     loc_180014089
0x180013edc  mov     r13d, [rax+40h]
0x180013ee0  add     rcx, 190h; Object
0x180013ee7  xor     r9d, r9d; Alertable
0x180013eea  mov     [rsp+68h+Timeout], 0; Timeout
0x180013ef3  xor     r8d, r8d; WaitMode
0x180013ef6  xor     edx, edx; WaitReason
0x180013ef8  call    cs:__imp_KeWaitForSingleObject
0x180013eff  nop     dword ptr [rax+rax+00h]
0x180013f04  mov     rcx, rbx; this
0x180013f07  call    ?HoldProcessing@CKsFilter@@AEAAXXZ; CKsFilter::HoldProcessing(void)
0x180013f0c  mov     rcx, [rbx+0E0h]; ObjectBag
0x180013f13  mov     r8d, 68h ; 'h'; NewSize
0x180013f19  mov     r9d, r8d; OldSize
0x180013f1c  mov     dword ptr [rsp+68h+Timeout], 6466534Bh; Tag
0x180013f24  mov     rdx, rsi; PointerToPointerToItem
0x180013f27  call    _KsEdit
0x180013f2c  mov     edi, eax
0x180013f2e  test    eax, eax
0x180013f30  js      loc_18001406A
0x180013f36  mov     rdx, [rsi]
0x180013f39  lea     r15d, [r13+1]
0x180013f3d  mov     rcx, [rbx+0E0h]; ObjectBag
0x180013f44  mov     r12d, r13d
0x180013f47  mov     r14d, ebp
0x180013f4a  imul    r12d, ebp
0x180013f4e  imul    r14d, r15d
0x180013f52  add     rdx, 48h ; 'H'; PointerToPointerToItem
0x180013f56  mov     dword ptr [rsp+68h+Timeout], 646E534Bh; Tag
0x180013f5e  mov     r9d, r12d; OldSize
0x180013f61  mov     r8d, r14d; NewSize
0x180013f64  call    _KsEdit
0x180013f69  mov     [rsp+68h+Item], 0
0x180013f72  mov     edi, eax
0x180013f74  test    eax, eax
0x180013f76  js      loc_18001406A
0x180013f7c  mov     rax, [rsi]
0x180013f7f  mov     r8, rbp; Size
0x180013f82  mov     rdx, [rsp+68h+Src]; Src
0x180013f87  mov     rcx, [rax+48h]
0x180013f8b  add     rcx, r12; void *
0x180013f8e  call    memmove
0x180013f93  mov     r9, [rsi]
0x180013f96  lea     rcx, [rsp+68h+Item]; int
0x180013f9b  mov     edx, [rbx+178h]
0x180013fa1  mov     r8d, ebp; int
0x180013fa4  mov     rax, [rbx+0E0h]
0x180013fab  inc     edx; int
0x180013fad  mov     [rsp+68h+ObjectBag], rax; ObjectBag
0x180013fb2  mov     r9, [r9+48h]; int
0x180013fb6  mov     [rsp+68h+Timeout], 0; AutomationTableB
0x180013fbf  call    KspCreateAutomationTableTable
0x180013fc4  mov     edi, eax
0x180013fc6  mov     rax, [rsi]
0x180013fc9  test    edi, edi
0x180013fcb  jns     short loc_180013FE3
0x180013fcd  mov     rcx, [rax+48h]
0x180013fd1  mov     r8, rbp; Size
0x180013fd4  add     rcx, r12; void *
0x180013fd7  xor     edx, edx; Val
0x180013fd9  call    memset
0x180013fde  jmp     loc_18001406A
0x180013fe3  mov     [rax+40h], r15d
0x180013fe7  mov     rcx, rbx; this
0x180013fea  mov     [rbx+178h], r15d
0x180013ff1  call    ?ConstructDefaultTopology@CKsFilter@@QEAAHXZ; CKsFilter::ConstructDefaultTopology(void)
0x180013ff6  test    eax, eax
0x180013ff8  jnz     short loc_180014038
0x180013ffa  mov     rax, [rsi]
0x180013ffd  or      ecx, 0FFFFFFFFh
0x180014000  mov     r8, rbp; Size
0x180014003  xor     edx, edx; Val
0x180014005  add     [rax+40h], ecx
0x180014008  add     [rbx+178h], ecx
0x18001400e  mov     rax, [rsi]
0x180014011  mov     ecx, r14d
0x180014014  add     rcx, [rax+48h]; void *
0x180014018  call    memset
0x18001401d  mov     rdx, [rsp+68h+Item]; Item
0x180014022  mov     r8b, 1; Free
0x180014025  mov     rcx, [rbx+0E0h]; ObjectBag
0x18001402c  call    KsRemoveItemFromObjectBag
0x180014031  mov     edi, 0C000009Ah
0x180014036  jmp     short loc_18001406A
0x180014038  mov     rdx, [rbx+170h]; Item
0x18001403f  test    rdx, rdx
0x180014042  jz      short loc_180014053
0x180014044  mov     rcx, [rbx+0E0h]; ObjectBag
0x18001404b  mov     r8b, 1; Free
0x18001404e  call    KsRemoveItemFromObjectBag
0x180014053  mov     rax, [rsp+68h+Item]
0x180014058  mov     [rbx+170h], rax
0x18001405f  mov     rax, [rsp+68h+arg_10]
0x180014067  mov     [rax], r13d
0x18001406a  mov     rcx, rbx; this
0x18001406d  call    ?RestoreProcessing@CKsFilter@@AEAAXXZ; CKsFilter::RestoreProcessing(void)
0x180014072  xor     edx, edx; Wait
0x180014074  lea     rcx, [rbx+190h]; Mutex
0x18001407b  call    cs:__imp_KeReleaseMutex
0x180014082  nop     dword ptr [rax+rax+00h]
0x180014087  mov     eax, edi
0x180014089  mov     rbx, [rsp+68h+arg_18]
0x180014091  add     rsp, 30h
0x180014095  pop     r15
0x180014097  pop     r14
0x180014099  pop     r13
0x18001409b  pop     r12
0x18001409d  pop     rdi
0x18001409e  pop     rsi
0x18001409f  pop     rbp
0x1800140a0  retn
```
