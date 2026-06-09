# CmsVolumeContainer::PinContainer(CmsTransactionContext *,unsigned __int64,SmsContainer * *,_SmsContainerOverflowPinList *,uchar,uchar)

- ea: `0x1c0014760`
- end: `0x1c0014a48`
- name: `?PinContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@PEAU_SmsContainerOverflowPinList@@EE@Z`
- size: `744`
- prototype: `int(CmsVolumeContainer *__hidden this, struct CmsTransactionContext *, unsigned __int64, struct SmsContainer **, struct _SmsContainerOverflowPinList *, unsigned __int8, unsigned __int8)`
- caller_count: `17`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c0014510`
- `0x1c002baa0`
- `0x1c002c4cc`
- `0x1c002d228`
- `0x1c002d3a4`
- `0x1c0060740`
- `0x1c00bfec0`
- `0x1c00c16dc`
- `0x1c00d2790`
- `0x1c00d34d0`
- `0x1c00d75fc`
- `0x1c00d7a6c`
- `0x1c00d8810`
- `0x1c00d8ae0`
- `0x1c00d8f10`
- `0x1c00e22c0`
- `0x1c00e253c`

## callees

- `0x1c0014760`
- `0x1c002c800`
- `0x1c00538e8`
- `0x1c00625fc`
- `0x1c0062754`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007543d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007543d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0075465`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0075465`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00753de`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00753de`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00148e3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00148e3`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c0014822`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c0014822`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0014861`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0014861`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c001498f`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c001498f`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00149e4`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00149e4`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c0014806`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c0014806`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1c001483b`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1c001483b`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c00149c2`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c00149c2`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00753b7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0075484`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00753b7`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0075484`

## pseudocode

```c
__int64 __fastcall CmsVolumeContainer::PinContainer(
        PRTL_DYNAMIC_HASH_TABLE *this,
        struct CmsTransactionContext *a2,
        ULONG_PTR a3,
        struct SmsContainer **a4,
        struct _SmsContainerOverflowPinList *a5,
        unsigned __int8 a6,
        unsigned __int8 a7)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rbx
  __int64 *v9; // rdx
  struct SmsContainer **v10; // r14
  _QWORD *v13; // r12
  __int64 v14; // rax
  struct SmsContainer **v15; // r10
  struct SmsContainer *v16; // r8
  __int64 *v17; // rax
  char v18; // r15
  NTSTATUS ContainerForCache; // edi
  __int64 v20; // r14
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v21; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v22; // rdi
  struct _IO_REMOVE_LOCK *v23; // r15
  unsigned int v24; // ebp
  __int64 v25; // rcx
  __int64 v27; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v28; // rdi
  int v29; // ebx
  unsigned int v30; // edx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  struct SmsContainer *v34; // rcx
  __int64 *v35; // rax
  _QWORD *PoolWithTag; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v37; // [rsp+30h] [rbp-58h] BYREF
  PIO_REMOVE_LOCK RemoveLock; // [rsp+38h] [rbp-50h]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+40h] [rbp-48h] BYREF
  CmsVolumeContainer *v40; // [rsp+48h] [rbp-40h] BYREF
  __int64 *v41; // [rsp+50h] [rbp-38h]

  v8 = 0;
  v9 = 0;
  v37 = 0;
  v10 = a4;
  v41 = 0;
  v13 = (_QWORD *)((char *)a2 + 2776);
  v14 = 0;
  v15 = (struct SmsContainer **)((char *)a2 + 2776);
  do
  {
    v16 = *v15;
    if ( *v15 && *((_QWORD *)v16 + 69) == a3 )
    {
      *a4 = v16;
      ++*((_DWORD *)a2 + v14 + 702);
      return 0;
    }
    v14 = (unsigned int)(v14 + 1);
    ++v15;
  }
  while ( (unsigned int)v14 < 4 );
  v17 = (__int64 *)*((_QWORD *)a2 + 328);
  if ( !v17 )
  {
LABEL_5:
    v40 = (CmsVolumeContainer *)this;
    Entry = 0;
    RemoveLock = (PIO_REMOVE_LOCK)(this + 41);
    v18 = 0;
    ContainerForCache = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(this + 41), 0, File, 1u, 0x20u);
    if ( ContainerForCache < 0 )
    {
      v23 = RemoveLock;
LABEL_16:
      v24 = ContainerForCache;
      if ( ContainerForCache >= 0 )
      {
        if ( HIDWORD(v8[4].Linkage.Flink) )
          KeWaitForSingleObject(&v8[4].Signature, Executive, 0, 0, 0);
        ExAcquirePushLockSharedEx(&v8[4].Linkage.Blink, 2);
        ++*((_DWORD *)a2 + 707);
        v25 = 0;
        while ( *v13 )
        {
          v25 = (unsigned int)(v25 + 1);
          ++v13;
          if ( (unsigned int)v25 >= 4 )
            goto LABEL_22;
        }
        *((_QWORD *)a2 + v25 + 347) = v8;
        *((_DWORD *)a2 + v25 + 702) = 1;
LABEL_22:
        if ( (_DWORD)v25 != 4 )
          goto LABEL_23;
        if ( a5 )
        {
          *((_QWORD *)a5 + 1) = v8;
          *((_DWORD *)a5 + 4) = 1;
          *(_QWORD *)a5 = 0;
LABEL_23:
          *v10 = (struct SmsContainer *)v8;
          return v24;
        }
        v35 = v41;
        if ( v41 )
        {
          while ( v35[1] )
          {
            v35 = (__int64 *)*v35;
            if ( !v35 )
              goto LABEL_60;
          }
          v35[1] = (__int64)v8;
          *((_DWORD *)v35 + 4) = 1;
          goto LABEL_23;
        }
LABEL_60:
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x6950534Du);
        if ( PoolWithTag )
        {
          PoolWithTag[1] = v8;
          *((_DWORD *)PoolWithTag + 4) = 1;
          *PoolWithTag = *((_QWORD *)a2 + 328);
          *((_QWORD *)a2 + 328) = PoolWithTag;
          goto LABEL_23;
        }
        v24 = -1073741670;
      }
      if ( v8 )
      {
        ExReleasePushLockEx(&v8[4].Linkage.Blink, 2);
        --*((_DWORD *)a2 + 707);
        _InterlockedDecrement((volatile signed __int32 *)&v8[3].Signature);
        IoReleaseRemoveLockEx(v23, 0, 0x20u);
        --*((_DWORD *)a2 + 706);
      }
      return v24;
    }
    v20 = ExAcquireAutoExpandPushLockShared(this[7], 0);
    v21 = RtlLookupEntryHashTable(this[6], a3, 0);
    v22 = v21;
    if ( v21 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v21[3].Signature);
      v8 = v37;
    }
    else
    {
      v22 = 0;
    }
    ExReleaseAutoExpandPushLockShared(v20, 0);
    if ( v22 )
    {
      if ( ((v22[23].Signature & 0x80000000000LL) != 0 || ((__int64)v22[1].Linkage.Flink & 2) != 0) && !a6 )
      {
        _InterlockedDecrement((volatile signed __int32 *)&v22[3].Signature);
        ContainerForCache = -1073741772;
        goto LABEL_40;
      }
      if ( !a7 )
        HIDWORD(v22[3].Signature) = 0;
      v8 = v22;
      ContainerForCache = 0;
      v37 = v8;
    }
    else
    {
      ContainerForCache = CmsVolumeContainer::CreateContainerForCache(
                            (CmsVolumeContainer *)this,
                            a2,
                            a3,
                            (struct SmsContainer **)&Entry);
      if ( ContainerForCache < 0 )
      {
LABEL_54:
        v23 = RemoveLock;
        IoReleaseRemoveLockEx(RemoveLock, 0, 0x20u);
        goto LABEL_15;
      }
      ExAcquireAutoExpandPushLockExclusive(this[7], 0);
      v27 = lambda_92acd8de50c64e0f63723dd5ec38c6f6_::operator()(&v40, a3);
      v28 = Entry;
      v29 = v27;
      if ( v27 )
      {
        v18 = 1;
      }
      else
      {
        RtlInsertEntryHashTable(this[6], Entry, a3, 0);
        v29 = lambda_92acd8de50c64e0f63723dd5ec38c6f6_::operator()(&v40, a3);
      }
      ExReleaseAutoExpandPushLockExclusive(this[7], 0);
      if ( v18 && v28 )
        SmsContainer::`scalar deleting destructor'(v28, v30);
      if ( a7 )
        v33 = 0;
      else
        LOBYTE(v33) = 1;
      LOBYTE(v32) = a6 != 0;
      ContainerForCache = lambda_0c9c8de26fc204c063c6035cbd5d6fb0_::operator()(v31, v29, v32, v33, (__int64)&v37);
      if ( ContainerForCache < 0 )
      {
LABEL_40:
        v8 = v37;
        goto LABEL_54;
      }
      v8 = v37;
    }
    ++*((_DWORD *)a2 + 706);
    v23 = RemoveLock;
LABEL_15:
    v10 = a4;
    goto LABEL_16;
  }
  while ( 1 )
  {
    v34 = (struct SmsContainer *)v17[1];
    if ( !v34 )
    {
      if ( !v9 )
        v9 = v17;
      v41 = v9;
      goto LABEL_47;
    }
    if ( *((_QWORD *)v34 + 69) == a3 )
      break;
LABEL_47:
    v17 = (__int64 *)*v17;
    if ( !v17 )
      goto LABEL_5;
  }
  *a4 = v34;
  ++*((_DWORD *)v17 + 4);
  return 0;
}

```

## disassembly

```asm
0x1c0014760  mov     [rsp+arg_10], rbx
0x1c0014765  mov     [rsp+arg_18], r9
0x1c001476a  push    rbp
0x1c001476b  push    rsi
0x1c001476c  push    r12
0x1c001476e  push    r13
0x1c0014770  push    r14
0x1c0014772  sub     rsp, 60h
0x1c0014776  mov     rsi, rdx
0x1c0014779  xor     ebx, ebx
0x1c001477b  xor     edx, edx
0x1c001477d  mov     [rsp+88h+var_58], rbx
0x1c0014782  mov     r14, r9
0x1c0014785  mov     [rsp+88h+var_38], rdx
0x1c001478a  mov     r13, r8
0x1c001478d  mov     rbp, rcx
0x1c0014790  lea     r12, [rsi+0AD8h]
0x1c0014797  xor     eax, eax
0x1c0014799  mov     r10, r12
0x1c001479c  mov     r8, [r10]
0x1c001479f  test    r8, r8
0x1c00147a2  jnz     loc_1C001493D
0x1c00147a8  inc     eax
0x1c00147aa  add     r10, 8
0x1c00147ae  cmp     eax, 4
0x1c00147b1  jb      short loc_1C001479C
0x1c00147b3  mov     rax, [rsi+0A40h]
0x1c00147ba  test    rax, rax
0x1c00147bd  jnz     loc_1C0075334
0x1c00147c3  lea     rax, [rbp+148h]
0x1c00147ca  mov     [rsp+88h+arg_0], rdi
0x1c00147d2  mov     rcx, rax; RemoveLock
0x1c00147d5  mov     [rsp+88h+arg_8], r15
0x1c00147dd  mov     r9d, 1; Line
0x1c00147e3  mov     [rsp+88h+var_40], rbp
0x1c00147e8  lea     r8, File; File
0x1c00147ef  mov     [rsp+88h+Entry], rbx
0x1c00147f4  xor     edx, edx; Tag
0x1c00147f6  mov     [rsp+88h+RemoveLock], rax
0x1c00147fb  xor     r15b, r15b
0x1c00147fe  mov     [rsp+88h+RemlockSize], 20h ; ' '; RemlockSize
0x1c0014806  call    cs:__imp_IoAcquireRemoveLockEx
0x1c001480d  nop     dword ptr [rax+rax+00h]
0x1c0014812  mov     edi, eax
0x1c0014814  test    eax, eax
0x1c0014816  js      loc_1C007536C
0x1c001481c  mov     rcx, [rbp+38h]
0x1c0014820  xor     edx, edx
0x1c0014822  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x1c0014829  nop     dword ptr [rax+rax+00h]
0x1c001482e  mov     rcx, [rbp+30h]; HashTable
0x1c0014832  xor     r8d, r8d; Context
0x1c0014835  mov     rdx, r13; Signature
0x1c0014838  mov     r14, rax
0x1c001483b  call    cs:__imp_RtlLookupEntryHashTable
0x1c0014842  nop     dword ptr [rax+rax+00h]
0x1c0014847  mov     rdi, rax
0x1c001484a  test    rax, rax
0x1c001484d  jz      loc_1C0014965
0x1c0014853  lock inc dword ptr [rax+58h]
0x1c0014857  mov     rbx, [rsp+88h+var_58]
0x1c001485c  xor     edx, edx
0x1c001485e  mov     rcx, r14
0x1c0014861  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1c0014868  nop     dword ptr [rax+rax+00h]
0x1c001486d  test    rdi, rdi
0x1c0014870  jz      loc_1C001496C
0x1c0014876  test    dword ptr [rdi+23Ch], 800h
0x1c0014880  jnz     loc_1C0075376
0x1c0014886  test    byte ptr [rdi+18h], 2
0x1c001488a  jnz     loc_1C0075376
0x1c0014890  cmp     [rsp+88h+arg_30], r15b
0x1c0014898  jnz     short loc_1C00148A1
0x1c001489a  mov     dword ptr [rdi+5Ch], 0
0x1c00148a1  mov     rbx, rdi
0x1c00148a4  xor     edi, edi
0x1c00148a6  mov     [rsp+88h+var_58], rbx
0x1c00148ab  inc     dword ptr [rsi+0B08h]
0x1c00148b1  mov     r15, [rsp+88h+RemoveLock]
0x1c00148b6  mov     r14, [rsp+88h+arg_18]
0x1c00148be  mov     ebp, edi
0x1c00148c0  test    edi, edi
0x1c00148c2  mov     rdi, [rsp+88h+arg_0]
0x1c00148ca  js      loc_1C0075453
0x1c00148d0  cmp     dword ptr [rbx+64h], 0
0x1c00148d4  jnz     loc_1C00753C9
0x1c00148da  lea     rcx, [rbx+68h]
0x1c00148de  mov     edx, 2
0x1c00148e3  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c00148ea  nop     dword ptr [rax+rax+00h]
0x1c00148ef  inc     dword ptr [rsi+0B0Ch]
0x1c00148f5  xor     ecx, ecx
0x1c00148f7  cmp     qword ptr [r12], 0
0x1c00148fc  jnz     short loc_1C0014958
0x1c00148fe  mov     [rsi+rcx*8+0AD8h], rbx
0x1c0014906  mov     dword ptr [rsi+rcx*4+0AF8h], 1
0x1c0014911  cmp     ecx, 4
0x1c0014914  jz      loc_1C00753F0
0x1c001491a  mov     [r14], rbx
0x1c001491d  mov     r15, [rsp+88h+arg_8]
0x1c0014925  mov     eax, ebp
0x1c0014927  mov     rbx, [rsp+88h+arg_10]
0x1c001492f  add     rsp, 60h
0x1c0014933  pop     r14
0x1c0014935  pop     r13
0x1c0014937  pop     r12
0x1c0014939  pop     rsi
0x1c001493a  pop     rbp
0x1c001493b  retn
0x1c001493d  cmp     [r8+228h], r13
0x1c0014944  jnz     loc_1C00147A8
0x1c001494a  mov     [r9], r8
0x1c001494d  inc     dword ptr [rsi+rax*4+0AF8h]
0x1c0014954  xor     eax, eax
0x1c0014956  jmp     short loc_1C0014927
0x1c0014958  inc     ecx
0x1c001495a  add     r12, 8
0x1c001495e  cmp     ecx, 4
0x1c0014961  jb      short loc_1C00148F7
0x1c0014963  jmp     short loc_1C0014911
0x1c0014965  xor     edi, edi
0x1c0014967  jmp     loc_1C001485C
0x1c001496c  lea     r9, [rsp+88h+Entry]; struct SmsContainer **
0x1c0014971  mov     r8, r13; unsigned __int64
0x1c0014974  mov     rdx, rsi; struct CmsTransactionContext *
0x1c0014977  mov     rcx, rbp; this
0x1c001497a  call    ?CreateContainerForCache@CmsVolumeContainer@@AEAAJPEAVCmsTransactionContext@@_KAEAPEAUSmsContainer@@@Z; CmsVolumeContainer::CreateContainerForCache(CmsTransactionContext *,unsigned __int64,SmsContainer * &)
0x1c001497f  mov     edi, eax
0x1c0014981  test    eax, eax
0x1c0014983  js      loc_1C00753A9
0x1c0014989  mov     rcx, [rbp+38h]
0x1c001498d  xor     edx, edx
0x1c001498f  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x1c0014996  nop     dword ptr [rax+rax+00h]
0x1c001499b  mov     rdx, r13
0x1c001499e  lea     rcx, [rsp+88h+var_40]
0x1c00149a3  call    _lambda_92acd8de50c64e0f63723dd5ec38c6f6___operator__
0x1c00149a8  mov     rdi, [rsp+88h+Entry]
0x1c00149ad  mov     rbx, rax
0x1c00149b0  test    rax, rax
0x1c00149b3  jnz     short loc_1C0014A34
0x1c00149b5  mov     rcx, [rbp+30h]; HashTable
0x1c00149b9  xor     r9d, r9d; Context
0x1c00149bc  mov     r8, r13; Signature
0x1c00149bf  mov     rdx, rdi; Entry
0x1c00149c2  call    cs:__imp_RtlInsertEntryHashTable
0x1c00149c9  nop     dword ptr [rax+rax+00h]
0x1c00149ce  mov     rdx, r13
0x1c00149d1  lea     rcx, [rsp+88h+var_40]
0x1c00149d6  call    _lambda_92acd8de50c64e0f63723dd5ec38c6f6___operator__
0x1c00149db  mov     rbx, rax
0x1c00149de  mov     rcx, [rbp+38h]
0x1c00149e2  xor     edx, edx
0x1c00149e4  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x1c00149eb  nop     dword ptr [rax+rax+00h]
0x1c00149f0  test    r15b, r15b
0x1c00149f3  jnz     loc_1C0075392
0x1c00149f9  cmp     [rsp+88h+arg_30], 0
0x1c0014a01  jnz     short loc_1C0014A39
0x1c0014a03  mov     r9b, 1
0x1c0014a06  cmp     [rsp+88h+arg_28], 0
0x1c0014a0e  lea     rax, [rsp+88h+var_58]
0x1c0014a13  mov     rdx, rbx
0x1c0014a16  mov     qword ptr [rsp+88h+RemlockSize], rax
0x1c0014a1b  setnz   r8b
0x1c0014a1f  call    _lambda_0c9c8de26fc204c063c6035cbd5d6fb0___operator__
0x1c0014a24  mov     edi, eax
0x1c0014a26  test    eax, eax
0x1c0014a28  js      short loc_1C0014A3E
0x1c0014a2a  mov     rbx, [rsp+88h+var_58]
0x1c0014a2f  jmp     loc_1C00148AB
0x1c0014a34  mov     r15b, 1
0x1c0014a37  jmp     short loc_1C00149DE
0x1c0014a39  xor     r9d, r9d
0x1c0014a3c  jmp     short loc_1C0014A06
0x1c0014a3e  mov     rbx, [rsp+88h+var_58]
0x1c0014a43  jmp     loc_1C00753A9
0x1c0075334  mov     rcx, [rax+8]
0x1c0075338  test    rcx, rcx
0x1c007533b  jz      short loc_1C0075353
0x1c007533d  cmp     [rcx+228h], r13
0x1c0075344  jnz     short loc_1C007535F
0x1c0075346  mov     [r9], rcx
0x1c0075349  inc     dword ptr [rax+10h]
0x1c007534c  xor     eax, eax
0x1c007534e  jmp     loc_1C0014927
0x1c0075353  test    rdx, rdx
0x1c0075356  cmovz   rdx, rax
0x1c007535a  mov     [rsp+88h+var_38], rdx
0x1c007535f  mov     rax, [rax]
0x1c0075362  test    rax, rax
0x1c0075365  jnz     short loc_1C0075334
0x1c0075367  jmp     loc_1C00147C3
0x1c007536c  mov     r15, [rsp+88h+RemoveLock]
0x1c0075371  jmp     loc_1C00148BE
0x1c0075376  cmp     [rsp+88h+arg_28], r15b
0x1c007537e  jnz     loc_1C0014890
0x1c0075384  lock dec dword ptr [rdi+58h]
0x1c0075388  mov     edi, 0C0000034h
0x1c007538d  jmp     loc_1C0014A3E
0x1c0075392  test    rdi, rdi
0x1c0075395  jz      loc_1C00149F9
0x1c007539b  mov     rcx, rdi; P
0x1c007539e  call    ??_GSmsContainer@@QEAAPEAXI@Z; SmsContainer::`scalar deleting destructor'(uint)
0x1c00753a3  nop
0x1c00753a4  jmp     loc_1C00149F9
0x1c00753a9  mov     r15, [rsp+88h+RemoveLock]
0x1c00753ae  xor     edx, edx; Tag
0x1c00753b0  mov     rcx, r15; RemoveLock
0x1c00753b3  lea     r8d, [rdx+20h]; RemlockSize
0x1c00753b7  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00753be  nop     dword ptr [rax+rax+00h]
0x1c00753c3  nop
0x1c00753c4  jmp     loc_1C00148B6
0x1c00753c9  lea     rcx, [rbx+70h]; Object
0x1c00753cd  mov     qword ptr [rsp+88h+RemlockSize], 0; Timeout
0x1c00753d6  xor     r9d, r9d; Alertable
0x1c00753d9  xor     r8d, r8d; WaitMode
0x1c00753dc  xor     edx, edx; WaitReason
0x1c00753de  call    cs:__imp_KeWaitForSingleObject
0x1c00753e5  nop     dword ptr [rax+rax+00h]
0x1c00753ea  nop
0x1c00753eb  jmp     loc_1C00148DA
0x1c00753f0  mov     rax, [rsp+88h+arg_20]
0x1c00753f8  test    rax, rax
0x1c00753fb  jz      short loc_1C0075414
0x1c00753fd  mov     [rax+8], rbx
0x1c0075401  mov     dword ptr [rax+10h], 1
0x1c0075408  mov     qword ptr [rax], 0
0x1c007540f  jmp     loc_1C001491A
0x1c0075414  mov     rax, [rsp+88h+var_38]
0x1c0075419  test    rax, rax
0x1c007541c  jz      short loc_1C007542D
0x1c007541e  cmp     qword ptr [rax+8], 0
0x1c0075423  jz      short loc_1C007549B
0x1c0075425  mov     rax, [rax]
0x1c0075428  test    rax, rax
0x1c007542b  jnz     short loc_1C007541E
0x1c007542d  mov     edx, 18h; NumberOfBytes
0x1c0075432  mov     ecx, 200h; PoolType
0x1c0075437  mov     r8d, 6950534Dh; Tag
0x1c007543d  call    cs:__imp_ExAllocatePoolWithTag
0x1c0075444  nop     dword ptr [rax+rax+00h]
0x1c0075449  test    rax, rax
0x1c007544c  jnz     short loc_1C00754AB
0x1c007544e  mov     ebp, 0C000009Ah
0x1c0075453  test    rbx, rbx
0x1c0075456  jz      loc_1C001491D
0x1c007545c  lea     rcx, [rbx+68h]
0x1c0075460  mov     edx, 2
0x1c0075465  call    cs:__imp_ExReleasePushLockEx
0x1c007546c  nop     dword ptr [rax+rax+00h]
0x1c0075471  dec     dword ptr [rsi+0B0Ch]
0x1c0075477  xor     edx, edx; Tag
0x1c0075479  lock dec dword ptr [rbx+58h]
0x1c007547d  mov     rcx, r15; RemoveLock
0x1c0075480  lea     r8d, [rdx+20h]; RemlockSize
0x1c0075484  call    cs:__imp_IoReleaseRemoveLockEx
0x1c007548b  nop     dword ptr [rax+rax+00h]
0x1c0075490  dec     dword ptr [rsi+0B08h]
0x1c0075496  jmp     loc_1C001491D
0x1c007549b  mov     [rax+8], rbx
0x1c007549f  mov     dword ptr [rax+10h], 1
0x1c00754a6  jmp     loc_1C001491A
0x1c00754ab  mov     [rax+8], rbx
0x1c00754af  mov     dword ptr [rax+10h], 1
0x1c00754b6  mov     rcx, [rsi+0A40h]
0x1c00754bd  mov     [rax], rcx
0x1c00754c0  mov     [rsi+0A40h], rax
0x1c00754c7  jmp     loc_1C001491A
```
