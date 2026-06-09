# CKsFilter::AddPinFactory(_KSPIN_DESCRIPTOR_EX const * const,ulong *)

- ea: `0x180004348`
- end: `0x1800047d6`
- name: `?AddPinFactory@CKsFilter@@QEAAJQEBU_KSPIN_DESCRIPTOR_EX@@PEAK@Z`
- size: `1166`
- prototype: `__int64 __fastcall(CKsFilter *__hidden this, const struct _KSPIN_DESCRIPTOR_EX *const, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18003d290`

## callees

- `0x180004348`
- `0x1800048a0`
- `0x180005550`
- `0x180005a00`
- `0x18000a2d4`
- `0x18000ffa4`
- `0x1800100a8`
- `0x180019cb0`
- `0x180019d00`
- `0x18004dbc0`
- `0x18004eb9c`
- `0x18004ed60`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800047b5`
- `ntoskrnl!KeReleaseMutex` at `0x1800047b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800043a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800043a6`

## pseudocode

```c
__int64 __fastcall CKsFilter::AddPinFactory(
        CKsFilter *this,
        const struct _KSPIN_DESCRIPTOR_EX *const a2,
        unsigned int *a3)
{
  _KSFILTER *p_Public; // rbx
  CKsFilter *v4; // rdi
  const KSFILTER_DESCRIPTOR *Descriptor; // rax
  size_t PinDescriptorSize; // r12
  ULONG PinDescriptorsCount; // ebp
  NTSTATUS AutomationTableTable; // r15d
  ULONG v10; // esi
  unsigned int v11; // r13d
  unsigned __int64 v12; // rbx
  size_t v13; // rax
  CKsPinFactory *v14; // r14
  size_t v15; // rax
  _KSPPROCESSPIN_INDEXENTRY *v16; // rsi
  size_t v17; // rax
  unsigned int *v18; // rax
  unsigned int *v19; // rbp
  unsigned int v20; // edx
  unsigned int v21; // r12d
  __int64 m_PinFactoriesCount; // rax
  CKsPinFactory *m_PinFactories; // rcx
  _LIST_ENTRY *p_m_ChildPinList; // rax
  CKsPinFactory *v25; // rdx
  _KSPPROCESSPIN_INDEXENTRY *m_ProcessPinsIndex; // rdx
  unsigned int *m_RelatedPinFactoryIds; // rcx
  CKsPinFactory *v28; // rbx
  unsigned int v29; // ecx
  struct _LIST_ENTRY *v30; // r13
  _KSFILTER *v31; // r14
  _LIST_ENTRY *v32; // r12
  struct _LIST_ENTRY *Flink; // rax
  _LIST_ENTRY *v34; // rax
  struct _LIST_ENTRY *v35; // rcx
  const struct _KSPIN_DESCRIPTOR_EX *v36; // r9
  struct _KSGATE *p_m_AndGate; // rdx
  KSOBJECT_BAG ObjectBag; // [rsp+28h] [rbp-70h]
  ULONG v39; // [rsp+30h] [rbp-68h]
  unsigned int v40; // [rsp+34h] [rbp-64h]
  PVOID Item; // [rsp+38h] [rbp-60h] BYREF
  _LIST_ENTRY *v42; // [rsp+40h] [rbp-58h]
  CKsPinFactory *v43; // [rsp+48h] [rbp-50h]
  unsigned int v47; // [rsp+B8h] [rbp+20h]

  p_Public = &this->m_Ext.Public;
  v4 = this;
  Descriptor = this->m_Ext.Public.Descriptor;
  PinDescriptorSize = Descriptor->PinDescriptorSize;
  if ( !(_DWORD)PinDescriptorSize )
    return 3221225485LL;
  PinDescriptorsCount = Descriptor->PinDescriptorsCount;
  v40 = PinDescriptorsCount;
  KeWaitForSingleObject(&this->m_ControlMutex, Executive, 0, 0, 0);
  CKsFilter::HoldProcessing(v4);
  AutomationTableTable = KsEdit(v4->m_Ext.Public.Bag, (PVOID *)p_Public, 0x68u, 0x68u, 0x6466534Bu);
  if ( AutomationTableTable >= 0 )
  {
    v10 = PinDescriptorsCount + 1;
    v11 = PinDescriptorSize * PinDescriptorsCount;
    v39 = PinDescriptorsCount + 1;
    AutomationTableTable = KsEdit(
                             v4->m_Ext.Public.Bag,
                             (PVOID *)&p_Public->Descriptor->PinDescriptors,
                             (PinDescriptorsCount + 1) * PinDescriptorSize,
                             PinDescriptorSize * PinDescriptorsCount,
                             0x6470534Bu);
    if ( AutomationTableTable >= 0 )
    {
      v12 = v10;
      v13 = 88LL * v10;
      if ( !is_mul_ok(v10, 0x58u) )
        v13 = -1;
      v14 = (CKsPinFactory *)operator new(v13, NonPagedPoolNx, 0x6670534Bu);
      v15 = 16LL * v10;
      if ( !is_mul_ok(v10, 0x10u) )
        v15 = -1;
      v16 = (_KSPPROCESSPIN_INDEXENTRY *)operator new(v15, NonPagedPoolNx, 0x6970534Bu);
      v17 = 4 * v12;
      if ( !is_mul_ok(v12, 4u) )
        v17 = -1;
      v18 = (unsigned int *)operator new(v17, PagedPool, 0x7052734Bu);
      v19 = v18;
      if ( v14 && v16 && v18 )
      {
        ObjectBag = v4->m_Ext.Public.Bag;
        v43 = v14;
        Item = 0;
        AutomationTableTable = KspCreateAutomationTableTable(
                                 (int)&Item,
                                 1,
                                 PinDescriptorSize,
                                 (int)a2 + 8,
                                 (PKSAUTOMATION_TABLE)&PinAutomationTable,
                                 ObjectBag);
        if ( AutomationTableTable >= 0 )
        {
          memmove((char *)v4->m_Ext.Public.Descriptor->PinDescriptors + v11, a2, PinDescriptorSize);
          v20 = 0;
          v21 = v39;
          v4->m_Ext.Public.Descriptor->PinDescriptorsCount = v39;
          m_PinFactoriesCount = v4->m_PinFactoriesCount;
          m_PinFactories = v4->m_PinFactories;
          if ( (_DWORD)m_PinFactoriesCount )
          {
            do
            {
              p_m_ChildPinList = &m_PinFactories->m_ChildPinList;
              if ( p_m_ChildPinList->Flink == p_m_ChildPinList )
              {
                m_PinFactories->m_ChildPinList.Blink = 0;
                p_m_ChildPinList->Flink = 0;
              }
              m_PinFactoriesCount = v4->m_PinFactoriesCount;
              ++m_PinFactories;
              ++v20;
            }
            while ( v20 < (unsigned int)m_PinFactoriesCount );
          }
          else
          {
            v43 = v14;
          }
          v25 = v4->m_PinFactories;
          v4->m_PinFactoriesAllocated = v39;
          if ( v25 && (_DWORD)m_PinFactoriesCount )
          {
            memmove(v14, v25, 88 * m_PinFactoriesCount);
            operator delete(v4->m_PinFactories);
            LODWORD(m_PinFactoriesCount) = v4->m_PinFactoriesCount;
          }
          m_ProcessPinsIndex = v4->m_ProcessPinsIndex;
          v4->m_PinFactories = v14;
          if ( m_ProcessPinsIndex && (_DWORD)m_PinFactoriesCount )
          {
            memmove(v16, m_ProcessPinsIndex, 16LL * (unsigned int)m_PinFactoriesCount);
            operator delete(v4->m_ProcessPinsIndex);
          }
          m_RelatedPinFactoryIds = v4->m_RelatedPinFactoryIds;
          v4->m_ProcessPinsIndex = v16;
          if ( m_RelatedPinFactoryIds )
            operator delete(m_RelatedPinFactoryIds);
          v28 = v4->m_PinFactories;
          v29 = 0;
          v4->m_RelatedPinFactoryIds = v19;
          v47 = 0;
          if ( v4->m_PinFactoriesCount )
          {
            v30 = &v28->m_ChildPinList;
            v31 = &v4->m_Ext.Public;
            do
            {
              v32 = &v28->m_ChildPinList;
              Flink = v28->m_ChildPinList.Flink;
              if ( Flink )
              {
                Flink->Blink = v30;
                v28->m_ChildPinList.Blink->Flink = v30;
              }
              else
              {
                v28->m_ChildPinList.Blink = v30;
                v32->Flink = v30;
              }
              v34 = v32->Flink;
              v42 = v34;
              if ( v34 != v32 )
              {
                do
                {
                  v35 = v34[4].Flink;
                  if ( v35 )
                  {
                    AutomationTableTable = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, const KSPIN_DESCRIPTOR_EX *, CKsPinFactory *, _LIST_ENTRY *))v35->Flink[2].Flink)(
                                             v35,
                                             3,
                                             &v31->Descriptor->PinDescriptors[v47],
                                             v28,
                                             &v28->m_ChildPinList);
                    v34 = v42;
                  }
                  v34 = v34->Flink;
                  v42 = v34;
                }
                while ( v34 != v32 );
                v4 = this;
                v29 = v47;
              }
              ++v29;
              ++v28;
              v30 = (struct _LIST_ENTRY *)((char *)v30 + 88);
              v47 = v29;
            }
            while ( v29 < v4->m_PinFactoriesCount );
            v14 = v43;
            v21 = v39;
          }
          v36 = a2;
          v28->m_ChildPinList.Blink = &v28->m_ChildPinList;
          p_m_AndGate = &v4->m_AndGate;
          v28->m_ChildPinList.Flink = &v28->m_ChildPinList;
          v28->m_AutomationTable = *(const KSAUTOMATION_TABLE_ **)Item;
          if ( (a2->Flags & 0x800000) != 0 )
          {
            v28->m_FrameGate.Count = 0;
            v28->m_FrameGate.NextGate = p_m_AndGate;
            if ( v4 != (CKsFilter *)-600LL )
              KsGateTurnInputOff(&v4->m_AndGate);
            KsGateTurnInputOn(&v28->m_FrameGate);
          }
          if ( (v36->Flags & 0x1000000) != 0 )
          {
            v28->m_StateGate.Count = 0;
            v28->m_StateGate.NextGate = p_m_AndGate;
            if ( p_m_AndGate )
              KsGateTurnInputOff(p_m_AndGate);
            KsGateTurnInputOn(&v28->m_StateGate);
          }
          v4->m_PinFactoriesCount = v21;
          *a3 = v40;
        }
        if ( Item )
          KsRemoveItemFromObjectBag(v4->m_Ext.Public.Bag, Item, 1u);
        if ( AutomationTableTable >= 0 )
          goto LABEL_61;
      }
      else
      {
        AutomationTableTable = -1073741670;
      }
      if ( v14 )
        operator delete(v14);
      if ( v16 )
        operator delete(v16);
      if ( v19 )
        operator delete(v19);
    }
  }
LABEL_61:
  CKsFilter::RestoreProcessing(v4);
  KeReleaseMutex(&v4->m_ControlMutex, 0);
  return (unsigned int)AutomationTableTable;
}

```

## disassembly

```asm
0x180004348  mov     [rsp+arg_10], r8
0x18000434d  mov     [rsp+Src], rdx
0x180004352  mov     [rsp+arg_0], rcx
0x180004357  push    rbx
0x180004358  push    rbp
0x180004359  push    rsi
0x18000435a  push    rdi
0x18000435b  push    r12
0x18000435d  push    r13
0x18000435f  push    r14
0x180004361  push    r15
0x180004363  sub     rsp, 58h
0x180004367  lea     rbx, [rcx+0D8h]
0x18000436e  mov     rdi, rcx
0x180004371  mov     rax, [rbx]
0x180004374  mov     r12d, [rax+24h]
0x180004378  test    r12d, r12d
0x18000437b  jnz     short loc_180004387
0x18000437d  mov     eax, 0C000000Dh
0x180004382  jmp     loc_1800047C4
0x180004387  mov     ebp, [rax+20h]
0x18000438a  add     rcx, 190h; Object
0x180004391  xor     r9d, r9d; Alertable
0x180004394  mov     [rsp+98h+var_64], ebp
0x180004398  xor     r8d, r8d; WaitMode
0x18000439b  mov     [rsp+98h+Timeout], 0; Timeout
0x1800043a4  xor     edx, edx; WaitReason
0x1800043a6  call    cs:__imp_KeWaitForSingleObject
0x1800043ad  nop     dword ptr [rax+rax+00h]
0x1800043b2  mov     rcx, rdi; this
0x1800043b5  call    ?HoldProcessing@CKsFilter@@AEAAXXZ; CKsFilter::HoldProcessing(void)
0x1800043ba  mov     rcx, [rdi+0E0h]; ObjectBag
0x1800043c1  mov     r8d, 68h ; 'h'; NewSize
0x1800043c7  mov     r9d, r8d; OldSize
0x1800043ca  mov     dword ptr [rsp+98h+Timeout], 6466534Bh; Tag
0x1800043d2  mov     rdx, rbx; PointerToPointerToItem
0x1800043d5  call    _KsEdit
0x1800043da  mov     r15d, eax
0x1800043dd  test    eax, eax
0x1800043df  js      loc_1800047A4
0x1800043e5  mov     rdx, [rbx]
0x1800043e8  lea     esi, [rbp+1]
0x1800043eb  mov     rcx, [rdi+0E0h]; ObjectBag
0x1800043f2  mov     r8d, r12d
0x1800043f5  mov     r13d, ebp
0x1800043f8  imul    r8d, esi; NewSize
0x1800043fc  imul    r13d, r12d
0x180004400  add     rdx, 28h ; '('; PointerToPointerToItem
0x180004404  mov     [rsp+98h+var_68], esi
0x180004408  mov     dword ptr [rsp+98h+Timeout], 6470534Bh; Tag
0x180004410  mov     r9d, r13d; OldSize
0x180004413  call    _KsEdit
0x180004418  mov     r15d, eax
0x18000441b  test    eax, eax
0x18000441d  js      loc_1800047A4
0x180004423  mov     ebx, esi
0x180004425  mov     eax, 58h ; 'X'
0x18000442a  mul     rbx
0x18000442d  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180004434  mov     esi, 200h
0x180004439  mov     r8d, 6670534Bh; unsigned int
0x18000443f  mov     edx, esi; PoolType
0x180004441  cmovb   rax, rbp
0x180004445  mov     rcx, rax; Size
0x180004448  call    ??2@YAPEAX_KW4_POOL_TYPE@@K@Z; operator new(unsigned __int64,_POOL_TYPE,ulong)
0x18000444d  mov     r14, rax
0x180004450  mov     r8d, 6970534Bh; unsigned int
0x180004456  lea     eax, [rbp+11h]
0x180004459  mul     rbx
0x18000445c  mov     edx, esi; PoolType
0x18000445e  cmovb   rax, rbp
0x180004462  mov     rcx, rax; Size
0x180004465  call    ??2@YAPEAX_KW4_POOL_TYPE@@K@Z; operator new(unsigned __int64,_POOL_TYPE,ulong)
0x18000446a  mov     rsi, rax
0x18000446d  mov     r8d, 7052734Bh; unsigned int
0x180004473  lea     eax, [rbp+5]
0x180004476  mul     rbx
0x180004479  lea     edx, [rbp+2]; PoolType
0x18000447c  cmovb   rax, rbp
0x180004480  mov     rcx, rax; Size
0x180004483  call    ??2@YAPEAX_KW4_POOL_TYPE@@K@Z; operator new(unsigned __int64,_POOL_TYPE,ulong)
0x180004488  mov     rbp, rax
0x18000448b  test    r14, r14
0x18000448e  jz      loc_180004777
0x180004494  test    rsi, rsi
0x180004497  jz      loc_180004777
0x18000449d  test    rax, rax
0x1800044a0  jz      loc_180004777
0x1800044a6  mov     rax, [rdi+0E0h]
0x1800044ad  lea     rcx, [rsp+98h+Item]; int
0x1800044b2  mov     r9, [rsp+98h+Src]
0x1800044ba  mov     r8d, r12d; int
0x1800044bd  mov     [rsp+98h+ObjectBag], rax; ObjectBag
0x1800044c2  add     r9, 8; int
0x1800044c6  lea     rax, ?PinAutomationTable@@3UKSAUTOMATION_TABLE_@@B; KSAUTOMATION_TABLE_ const PinAutomationTable
0x1800044cd  mov     [rsp+98h+var_50], r14
0x1800044d2  mov     edx, 1; int
0x1800044d7  mov     [rsp+98h+Timeout], rax; AutomationTableB
0x1800044dc  mov     [rsp+98h+Item], 0
0x1800044e5  call    KspCreateAutomationTableTable
0x1800044ea  mov     r15d, eax
0x1800044ed  test    eax, eax
0x1800044ef  js      loc_180004754
0x1800044f5  mov     rdx, [rsp+98h+Src]; Src
0x1800044fd  lea     rbx, [rdi+0D8h]
0x180004504  mov     rax, [rbx]
0x180004507  mov     r8, r12; Size
0x18000450a  mov     ecx, r13d
0x18000450d  add     rcx, [rax+28h]; void *
0x180004511  call    memmove
0x180004516  mov     rax, [rbx]
0x180004519  xor     edx, edx
0x18000451b  mov     r12d, [rsp+98h+var_68]
0x180004520  mov     [rax+20h], r12d
0x180004524  mov     eax, [rdi+1C8h]
0x18000452a  mov     rcx, [rdi+1D0h]
0x180004531  test    eax, eax
0x180004533  jz      short loc_18000455F
0x180004535  lea     rax, [rcx+8]
0x180004539  cmp     [rax], rax
0x18000453c  jnz     short loc_18000454D
0x18000453e  mov     qword ptr [rcx+10h], 0
0x180004546  mov     qword ptr [rax], 0
0x18000454d  mov     eax, [rdi+1C8h]
0x180004553  add     rcx, 58h ; 'X'
0x180004557  inc     edx
0x180004559  cmp     edx, eax
0x18000455b  jb      short loc_180004535
0x18000455d  jmp     short loc_180004564
0x18000455f  mov     [rsp+98h+var_50], r14
0x180004564  mov     rdx, [rdi+1D0h]; Src
0x18000456b  mov     [rdi+1CCh], r12d
0x180004572  test    rdx, rdx
0x180004575  jz      short loc_180004599
0x180004577  test    eax, eax
0x180004579  jz      short loc_180004599
0x18000457b  imul    r8, rax, 58h ; 'X'; Size
0x18000457f  mov     rcx, r14; void *
0x180004582  call    memmove
0x180004587  mov     rcx, [rdi+1D0h]; void *
0x18000458e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004593  mov     eax, [rdi+1C8h]
0x180004599  mov     rdx, [rdi+1F8h]; Src
0x1800045a0  mov     [rdi+1D0h], r14
0x1800045a7  test    rdx, rdx
0x1800045aa  jz      short loc_1800045CB
0x1800045ac  test    eax, eax
0x1800045ae  jz      short loc_1800045CB
0x1800045b0  mov     r8d, eax
0x1800045b3  mov     rcx, rsi; void *
0x1800045b6  shl     r8, 4; Size
0x1800045ba  call    memmove
0x1800045bf  mov     rcx, [rdi+1F8h]; void *
0x1800045c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045cb  mov     rcx, [rdi+2F8h]; void *
0x1800045d2  mov     [rdi+1F8h], rsi
0x1800045d9  test    rcx, rcx
0x1800045dc  jz      short loc_1800045E3
0x1800045de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045e3  mov     rbx, [rdi+1D0h]
0x1800045ea  xor     ecx, ecx
0x1800045ec  mov     [rdi+2F8h], rbp
0x1800045f3  mov     [rsp+98h+arg_18], ecx
0x1800045fa  cmp     [rdi+1C8h], ecx
0x180004600  jbe     loc_1800046C3
0x180004606  lea     r13, [rbx+8]
0x18000460a  lea     r14, [rdi+0D8h]
0x180004611  lea     r12, [rbx+8]
0x180004615  mov     rax, [r12]
0x180004619  test    rax, rax
0x18000461c  jnz     short loc_180004628
0x18000461e  mov     [rbx+10h], r13
0x180004622  mov     [r12], r13
0x180004626  jmp     short loc_180004633
0x180004628  mov     [rax+8], r13
0x18000462c  mov     rax, [rbx+10h]
0x180004630  mov     [rax], r13
0x180004633  mov     rax, [r12]
0x180004637  mov     [rsp+98h+var_58], rax
0x18000463c  cmp     rax, r12
0x18000463f  jz      short loc_18000469C
0x180004641  mov     edi, [rsp+98h+arg_18]
0x180004648  mov     rcx, [rax+40h]
0x18000464c  test    rcx, rcx
0x18000464f  jz      short loc_180004680
0x180004651  mov     rax, [r14]
0x180004654  mov     r9, rbx
0x180004657  mov     rdx, [rcx]
0x18000465a  imul    r8, rdi, 88h
0x180004661  mov     [rsp+98h+Timeout], r12
0x180004666  add     r8, [rax+28h]
0x18000466a  mov     rax, [rdx+20h]
0x18000466e  mov     edx, 3
0x180004673  call    _guard_dispatch_icall
0x180004678  mov     r15d, eax
0x18000467b  mov     rax, [rsp+98h+var_58]
0x180004680  mov     rax, [rax]
0x180004683  mov     [rsp+98h+var_58], rax
0x180004688  cmp     rax, r12
0x18000468b  jnz     short loc_180004648
0x18000468d  mov     rdi, [rsp+98h+arg_0]
0x180004695  mov     ecx, [rsp+98h+arg_18]
0x18000469c  inc     ecx
0x18000469e  add     rbx, 58h ; 'X'
0x1800046a2  add     r13, 58h ; 'X'
0x1800046a6  mov     [rsp+98h+arg_18], ecx
0x1800046ad  cmp     ecx, [rdi+1C8h]
0x1800046b3  jb      loc_180004611
0x1800046b9  mov     r14, [rsp+98h+var_50]
0x1800046be  mov     r12d, [rsp+98h+var_68]
0x1800046c3  mov     r9, [rsp+98h+Src]
0x1800046cb  lea     rax, [rbx+8]
0x1800046cf  mov     [rax+8], rax
0x1800046d3  lea     rdx, [rdi+258h]
0x1800046da  mov     [rax], rax
0x1800046dd  mov     rax, [rsp+98h+Item]
0x1800046e2  mov     rax, [rax]
0x1800046e5  mov     [rbx+18h], rax
0x1800046e9  test    dword ptr [r9+68h], 800000h
0x1800046f1  jz      short loc_180004714
0x1800046f3  mov     dword ptr [rbx+38h], 0
0x1800046fa  mov     [rbx+40h], rdx
0x1800046fe  test    rdx, rdx
0x180004701  jz      short loc_18000470B
0x180004703  mov     rcx, rdx; Gate
0x180004706  call    KsGateTurnInputOff
0x18000470b  lea     rcx, [rbx+38h]; Gate
0x18000470f  call    KsGateTurnInputOn
0x180004714  test    dword ptr [r9+68h], 1000000h
0x18000471c  jz      short loc_18000473F
0x18000471e  mov     dword ptr [rbx+48h], 0
0x180004725  mov     [rbx+50h], rdx
0x180004729  test    rdx, rdx
0x18000472c  jz      short loc_180004736
0x18000472e  mov     rcx, rdx; Gate
0x180004731  call    KsGateTurnInputOff
0x180004736  lea     rcx, [rbx+48h]; Gate
0x18000473a  call    KsGateTurnInputOn
0x18000473f  mov     rcx, [rsp+98h+arg_10]
0x180004747  mov     eax, [rsp+98h+var_64]
0x18000474b  mov     [rdi+1C8h], r12d
0x180004752  mov     [rcx], eax
0x180004754  mov     rax, [rsp+98h+Item]
0x180004759  test    rax, rax
0x18000475c  jz      short loc_180004770
0x18000475e  mov     rcx, [rdi+0E0h]; ObjectBag
0x180004765  mov     r8b, 1; Free
0x180004768  mov     rdx, rax; Item
0x18000476b  call    KsRemoveItemFromObjectBag
0x180004770  test    r15d, r15d
0x180004773  js      short loc_18000477D
0x180004775  jmp     short loc_1800047A4
0x180004777  mov     r15d, 0C000009Ah
0x18000477d  test    r14, r14
0x180004780  jz      short loc_18000478A
0x180004782  mov     rcx, r14; void *
0x180004785  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000478a  test    rsi, rsi
0x18000478d  jz      short loc_180004797
0x18000478f  mov     rcx, rsi; void *
0x180004792  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004797  test    rbp, rbp
0x18000479a  jz      short loc_1800047A4
0x18000479c  mov     rcx, rbp; void *
0x18000479f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800047a4  mov     rcx, rdi; this
0x1800047a7  call    ?RestoreProcessing@CKsFilter@@AEAAXXZ; CKsFilter::RestoreProcessing(void)
0x1800047ac  xor     edx, edx; Wait
0x1800047ae  lea     rcx, [rdi+190h]; Mutex
0x1800047b5  call    cs:__imp_KeReleaseMutex
0x1800047bc  nop     dword ptr [rax+rax+00h]
0x1800047c1  mov     eax, r15d
0x1800047c4  add     rsp, 58h
0x1800047c8  pop     r15
0x1800047ca  pop     r14
0x1800047cc  pop     r13
0x1800047ce  pop     r12
0x1800047d0  pop     rdi
0x1800047d1  pop     rsi
0x1800047d2  pop     rbp
0x1800047d3  pop     rbx
0x1800047d4  retn
```
