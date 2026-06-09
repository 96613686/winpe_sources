# CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar)

- ea: `0x1400105d0`
- end: `0x1400108e1`
- name: `?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EE@Z`
- size: `785`
- prototype: `int(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int64, struct SmsContainer **, unsigned __int8, unsigned __int8)`
- caller_count: `34`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f740`
- `0x1400103b0`
- `0x140079550`
- `0x1400b0e8c`
- `0x1400c0c34`
- `0x1400c0ec0`
- `0x1400c2a04`
- `0x1400ca6a0`
- `0x1400ce0f4`
- `0x14012f71c`
- `0x140139a54`
- `0x14013a514`
- `0x14013a718`
- `0x14013ada8`
- `0x14013b2ac`
- `0x14013b528`
- `0x14013c6d0`
- `0x14013e8cc`
- `0x14013e9a4`
- `0x14013eb4c`
- `0x14013ebcc`
- `0x14013ecc8`
- `0x140151d24`
- `0x14015369c`
- `0x1401651e0`
- `0x140166208`
- `0x140166c80`
- `0x140167904`
- `0x14016d7e8`
- `0x14016d980`
- `0x14016e3c0`
- `0x14016e5cc`
- `0x14016f1cc`
- `0x14016fca8`

## callees

- `0x1400105d0`
- `0x140024c60`
- `0x1400c13c8`

## import_xrefs

- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140010652`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x140010652`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14001068d`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140010701`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14001068d`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140010701`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14001074d`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x14001074d`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140010789`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140010867`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140010789`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140010867`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001062b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14001062b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001066b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140010763`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140010843`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001066b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140010763`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140010843`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001082d`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14001082d`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400108ac`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400108ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400107c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400108d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400107c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400108d0`

## pseudocode

```c
NTSTATUS __fastcall CmsVolumeContainer::GetContainerReference(
        CmsVolumeContainer *this,
        struct CmsTransactionContext *a2,
        ULONG_PTR a3,
        PRTL_DYNAMIC_HASH_TABLE_ENTRY *a4,
        unsigned __int8 a5,
        unsigned __int8 a6)
{
  bool v10; // r15
  struct _IO_REMOVE_LOCK *v11; // r13
  NTSTATUS result; // eax
  __int64 v13; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v14; // rax
  __int64 v15; // r8
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v16; // rsi
  int ContainerForCache; // ebx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v18; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // rcx
  void *v21; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v22; // rax
  PVOID P; // [rsp+60h] [rbp+8h] BYREF

  P = 0;
  v10 = !a2 || !_bittest64((const signed __int64 *)a2, 0x22u);
  v11 = (struct _IO_REMOVE_LOCK *)((char *)this + 480);
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)this + 15, 0, &File, 1u, 0x20u);
  if ( result >= 0 )
  {
    v13 = ExAcquireAutoExpandPushLockShared((char *)this + 56, 2);
    v14 = RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), a3, 0);
    v16 = v14;
    if ( v14 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v14[3].Signature + 1);
      ExReleaseAutoExpandPushLockShared(v13, 2, v15);
      *a4 = 0;
      if ( ((HIDWORD(v16[25].Linkage.Blink) & 0x800) != 0 || ((__int64)v16[1].Linkage.Flink & 4) != 0) && !a6 )
      {
LABEL_31:
        ContainerForCache = -1073741772;
        _InterlockedDecrement((volatile signed __int32 *)&v16[3].Signature + 1);
LABEL_10:
        if ( ContainerForCache >= 0 )
        {
          if ( a2 )
            ++*((_DWORD *)a2 + 88);
          return ContainerForCache;
        }
        goto LABEL_39;
      }
      if ( !v10 )
      {
LABEL_9:
        ContainerForCache = 0;
        *a4 = v16;
        goto LABEL_10;
      }
    }
    else
    {
      ExReleaseAutoExpandPushLockShared(v13, 2, v15);
      if ( a5 )
      {
        ContainerForCache = -1073741772;
        goto LABEL_39;
      }
      if ( !a2 )
      {
        ContainerForCache = -1073741802;
        goto LABEL_39;
      }
      ContainerForCache = CmsVolumeContainer::CreateContainerForCache(this, a2, a3, (struct SmsContainer **)&P);
      if ( ContainerForCache < 0 )
      {
LABEL_39:
        IoReleaseRemoveLockEx(v11, 0, 0x20u);
        return ContainerForCache;
      }
      ExAcquireAutoExpandPushLockExclusive((char *)this + 56, 2);
      v18 = RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), a3, 0);
      v16 = v18;
      if ( v18 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&v18[3].Signature + 1);
        ExReleaseAutoExpandPushLockExclusive((char *)this + 56, 2);
        v19 = P;
        if ( P )
        {
          v20 = (_QWORD *)*((_QWORD *)P + 21);
          if ( v20 )
            CmsLookasides::Free(v20);
          v21 = (void *)v19[71];
          if ( v21 )
            ExFreePoolWithTag(v21, 0);
          ExFreePoolWithTag(v19, 0);
        }
      }
      else
      {
        RtlInsertEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)P, a3, 0);
        v22 = RtlLookupEntryHashTable(*((PRTL_DYNAMIC_HASH_TABLE *)this + 6), a3, 0);
        v16 = v22;
        if ( v22 )
          _InterlockedIncrement((volatile signed __int32 *)&v22[3].Signature + 1);
        else
          v16 = 0;
        ExReleaseAutoExpandPushLockExclusive((char *)this + 56, 2);
      }
      *a4 = 0;
      if ( ((HIDWORD(v16[25].Linkage.Blink) & 0x800) != 0 || ((__int64)v16[1].Linkage.Flink & 4) != 0) && !a6 )
        goto LABEL_31;
      if ( !v10 )
        goto LABEL_9;
    }
    LODWORD(v16[4].Linkage.Flink) = 0;
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x1400105d0  mov     [rsp+arg_18], rbp
0x1400105d5  push    rdi
0x1400105d6  push    r12
0x1400105d8  push    r13
0x1400105da  push    r14
0x1400105dc  push    r15
0x1400105de  sub     rsp, 30h
0x1400105e2  mov     [rsp+58h+P], 0
0x1400105eb  mov     r14, r9
0x1400105ee  mov     r12, r8
0x1400105f1  mov     rdi, rdx
0x1400105f4  mov     rbp, rcx
0x1400105f7  test    rdx, rdx
0x1400105fa  jz      short loc_140010607
0x1400105fc  bt      qword ptr [rdx], 22h ; '"'
0x140010601  jb      loc_1400106F9
0x140010607  mov     r15b, 1
0x14001060a  lea     r13, [rcx+1E0h]
0x140010611  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140010619  mov     rcx, r13; RemoveLock
0x14001061c  lea     r8, File; File
0x140010623  mov     r9d, 1; Line
0x140010629  xor     edx, edx; Tag
0x14001062b  call    cs:__imp_IoAcquireRemoveLockEx
0x140010632  nop     dword ptr [rax+rax+00h]
0x140010637  test    eax, eax
0x140010639  js      loc_1400106E5
0x14001063f  mov     [rsp+58h+arg_8], rbx
0x140010644  lea     rcx, [rbp+38h]
0x140010648  mov     edx, 2
0x14001064d  mov     [rsp+58h+arg_10], rsi
0x140010652  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x140010659  nop     dword ptr [rax+rax+00h]
0x14001065e  mov     rcx, [rbp+30h]; HashTable
0x140010662  xor     r8d, r8d; Context
0x140010665  mov     rdx, r12; Signature
0x140010668  mov     rbx, rax
0x14001066b  call    cs:__imp_RtlLookupEntryHashTable
0x140010672  nop     dword ptr [rax+rax+00h]
0x140010677  mov     edx, 2
0x14001067c  mov     rcx, rbx
0x14001067f  mov     rsi, rax
0x140010682  test    rax, rax
0x140010685  jz      short loc_140010701
0x140010687  nop
0x140010688  lock inc dword ptr [rax+5Ch]
0x14001068c  nop
0x14001068d  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140010694  nop     dword ptr [rax+rax+00h]
0x140010699  xor     ebp, ebp
0x14001069b  mov     [r14], rbp
0x14001069e  test    dword ptr [rsi+264h], 800h
0x1400106a8  jnz     loc_140010800
0x1400106ae  test    byte ptr [rsi+18h], 4
0x1400106b2  jnz     loc_140010800
0x1400106b8  test    r15b, r15b
0x1400106bb  jnz     loc_1400107F8
0x1400106c1  mov     ebx, ebp
0x1400106c3  mov     [r14], rsi
0x1400106c6  test    ebx, ebx
0x1400106c8  js      loc_1400108A1
0x1400106ce  test    rdi, rdi
0x1400106d1  jz      short loc_1400106D9
0x1400106d3  inc     dword ptr [rdi+160h]
0x1400106d9  mov     rsi, [rsp+58h+arg_10]
0x1400106de  mov     eax, ebx
0x1400106e0  mov     rbx, [rsp+58h+arg_8]
0x1400106e5  mov     rbp, [rsp+58h+arg_18]
0x1400106ea  add     rsp, 30h
0x1400106ee  pop     r15
0x1400106f0  pop     r14
0x1400106f2  pop     r13
0x1400106f4  pop     r12
0x1400106f6  pop     rdi
0x1400106f7  retn
0x1400106f9  xor     r15b, r15b
0x1400106fc  jmp     loc_14001060A
0x140010701  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140010708  nop     dword ptr [rax+rax+00h]
0x14001070d  cmp     [rsp+58h+arg_20], 0
0x140010715  jnz     loc_14001089C
0x14001071b  test    rdi, rdi
0x14001071e  jz      loc_1400108BD
0x140010724  lea     r9, [rsp+58h+P]; struct SmsContainer **
0x140010729  mov     r8, r12; unsigned __int64
0x14001072c  mov     rdx, rdi; struct CmsTransactionContext *
0x14001072f  mov     rcx, rbp; this
0x140010732  call    ?CreateContainerForCache@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@_KAEAPEAUSmsContainer@@@Z; CmsVolumeContainer::CreateContainerForCache(CmsTransactionContext *,unsigned __int64,SmsContainer * &)
0x140010737  mov     ebx, eax
0x140010739  test    eax, eax
0x14001073b  js      loc_1400108A1
0x140010741  lea     rbx, [rbp+38h]
0x140010745  mov     edx, 2
0x14001074a  mov     rcx, rbx
0x14001074d  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x140010754  nop     dword ptr [rax+rax+00h]
0x140010759  mov     rcx, [rbp+30h]; HashTable
0x14001075d  xor     r8d, r8d; Context
0x140010760  mov     rdx, r12; Signature
0x140010763  call    cs:__imp_RtlLookupEntryHashTable
0x14001076a  nop     dword ptr [rax+rax+00h]
0x14001076f  mov     rsi, rax
0x140010772  test    rax, rax
0x140010775  jz      loc_14001081E
0x14001077b  nop
0x14001077c  lock inc dword ptr [rax+5Ch]
0x140010780  mov     edx, 2
0x140010785  mov     rcx, rbx
0x140010788  nop
0x140010789  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x140010790  nop     dword ptr [rax+rax+00h]
0x140010795  mov     rbx, [rsp+58h+P]
0x14001079a  test    rbx, rbx
0x14001079d  jz      short loc_1400107D0
0x14001079f  mov     rcx, [rbx+0A8h]; void *
0x1400107a6  test    rcx, rcx
0x1400107a9  jnz     loc_1400108C4
0x1400107af  mov     rcx, [rbx+238h]; P
0x1400107b6  test    rcx, rcx
0x1400107b9  jnz     loc_1400108CE
0x1400107bf  xor     edx, edx; Tag
0x1400107c1  mov     rcx, rbx; P
0x1400107c4  call    cs:__imp_ExFreePoolWithTag
0x1400107cb  nop     dword ptr [rax+rax+00h]
0x1400107d0  xor     ebp, ebp
0x1400107d2  mov     [r14], rbp
0x1400107d5  test    dword ptr [rsi+264h], 800h
0x1400107df  jnz     loc_14001087E
0x1400107e5  test    byte ptr [rsi+18h], 4
0x1400107e9  jnz     loc_14001087E
0x1400107ef  test    r15b, r15b
0x1400107f2  jz      loc_1400106C1
0x1400107f8  mov     [rsi+60h], ebp
0x1400107fb  jmp     loc_1400106C1
0x140010800  cmp     [rsp+58h+arg_28], bpl
0x140010808  jnz     loc_1400106B8
0x14001080e  nop
0x14001080f  mov     ebx, 0C0000034h
0x140010814  lock dec dword ptr [rsi+5Ch]
0x140010818  nop
0x140010819  jmp     loc_1400106C6
0x14001081e  mov     rdx, [rsp+58h+P]; Entry
0x140010823  xor     r9d, r9d; Context
0x140010826  mov     rcx, [rbp+30h]; HashTable
0x14001082a  mov     r8, r12; Signature
0x14001082d  call    cs:__imp_RtlInsertEntryHashTable
0x140010834  nop     dword ptr [rax+rax+00h]
0x140010839  mov     rcx, [rbp+30h]; HashTable
0x14001083d  xor     r8d, r8d; Context
0x140010840  mov     rdx, r12; Signature
0x140010843  call    cs:__imp_RtlLookupEntryHashTable
0x14001084a  nop     dword ptr [rax+rax+00h]
0x14001084f  mov     rsi, rax
0x140010852  test    rax, rax
0x140010855  jz      short loc_140010878
0x140010857  nop
0x140010858  lock inc dword ptr [rax+5Ch]
0x14001085c  nop
0x14001085d  xor     ebp, ebp
0x14001085f  mov     edx, 2
0x140010864  mov     rcx, rbx
0x140010867  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x14001086e  nop     dword ptr [rax+rax+00h]
0x140010873  jmp     loc_1400107D2
0x140010878  xor     ebp, ebp
0x14001087a  mov     esi, ebp
0x14001087c  jmp     short loc_14001085F
0x14001087e  cmp     [rsp+58h+arg_28], 0
0x140010886  jnz     loc_1400107EF
0x14001088c  nop
0x14001088d  mov     ebx, 0C0000034h
0x140010892  lock dec dword ptr [rsi+5Ch]
0x140010896  nop
0x140010897  jmp     loc_1400106C6
0x14001089c  mov     ebx, 0C0000034h
0x1400108a1  xor     edx, edx; Tag
0x1400108a3  mov     r8d, 20h ; ' '; RemlockSize
0x1400108a9  mov     rcx, r13; RemoveLock
0x1400108ac  call    cs:__imp_IoReleaseRemoveLockEx
0x1400108b3  nop     dword ptr [rax+rax+00h]
0x1400108b8  jmp     loc_1400106D9
0x1400108bd  mov     ebx, 0C0000016h
0x1400108c2  jmp     short loc_1400108A1
0x1400108c4  call    ?Free@CmsLookasides@@SAXPEAX@Z; CmsLookasides::Free(void *)
0x1400108c9  jmp     loc_1400107AF
0x1400108ce  xor     edx, edx; Tag
0x1400108d0  call    cs:__imp_ExFreePoolWithTag
0x1400108d7  nop     dword ptr [rax+rax+00h]
0x1400108dc  jmp     loc_1400107BF
```
