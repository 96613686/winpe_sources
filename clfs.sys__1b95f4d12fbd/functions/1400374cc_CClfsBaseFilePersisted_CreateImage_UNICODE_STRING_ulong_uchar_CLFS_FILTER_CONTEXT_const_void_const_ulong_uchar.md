# CClfsBaseFilePersisted::CreateImage(_UNICODE_STRING *,ulong,uchar,_CLFS_FILTER_CONTEXT const &,void * const,ulong,uchar &)

- ea: `0x1400374cc`
- end: `0x140037c6e`
- name: `?CreateImage@CClfsBaseFilePersisted@@QEAAJPEAU_UNICODE_STRING@@KEAEBU_CLFS_FILTER_CONTEXT@@QEAXKAEAE@Z`
- size: `1954`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFilePersisted *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, const struct _CLFS_FILTER_CONTEXT *, void *const, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140076e00`

## callees

- `0x1400124ec`
- `0x140017f20`
- `0x140017f80`
- `0x140018280`
- `0x140032878`
- `0x140033898`
- `0x140034a20`
- `0x1400374cc`
- `0x14003a7cc`
- `0x14005ff58`
- `0x140060efc`
- `0x1400623e4`
- `0x140062c20`
- `0x1400637ec`
- `0x140063844`
- `0x140063b84`
- `0x14006a6fc`
- `0x140072eb8`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400375a5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400375a5`
- `ntoskrnl!ExUuidCreate` at `0x140037a5d`
- `ntoskrnl!ExUuidCreate` at `0x140037a5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037647`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037647`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037687`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037707`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037900`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003791e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037687`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037707`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037900`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003791e`
- `cng!BCryptGenRandom` at `0x140037791`
- `cng!BCryptGenRandom` at `0x140037791`

## pseudocode

```c
__int64 __fastcall CClfsBaseFilePersisted::CreateImage(
        CClfsAuthContainer **this,
        struct _UNICODE_STRING *a2,
        int a3,
        char a4,
        const struct _CLFS_FILTER_CONTEXT *a5,
        void *const a6,
        unsigned int a7,
        unsigned __int8 *a8)
{
  struct _UNICODE_STRING *v8; // r12
  struct _CLFS_CONTROL_RECORD *v10; // r13
  unsigned __int8 *v11; // rdi
  unsigned __int8 v12; // r15
  NTSTATUS v13; // ebx
  int v14; // r8d
  char v15; // r9
  PVOID v16; // rax
  __int64 v17; // rdx
  CClfsAuthContainer *v18; // rcx
  CClfsAuthContainer *v19; // rcx
  SIZE_T v20; // rax
  CClfsAuthContainer *PoolWithTag; // rcx
  unsigned int Length; // eax
  const struct _CLFS_FILTER_CONTEXT *v23; // rdi
  unsigned int v24; // eax
  CClfsAuthContainer *v25; // rcx
  unsigned __int64 *v26; // r14
  CClfsAuthContainer *v27; // rcx
  unsigned __int64 v28; // rax
  CClfsAuthContainer *v29; // rcx
  unsigned __int64 v30; // rax
  unsigned int RawSectorSize; // r15d
  unsigned int v32; // edi
  CClfsAuthContainer *v33; // rax
  CClfsAuthContainer *v34; // rcx
  CClfsAuthContainer *v35; // rax
  struct _CLFS_BASE_RECORD_HEADER *BaseLogRecord; // r14
  unsigned __int16 i; // di
  int v39; // [rsp+48h] [rbp-60h] BYREF
  struct _CLFS_CONTROL_RECORD *v40; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v41; // [rsp+58h] [rbp-50h] BYREF
  unsigned __int64 v42[4]; // [rsp+60h] [rbp-48h] BYREF
  int v44; // [rsp+C0h] [rbp+18h] BYREF
  char v45; // [rsp+C8h] [rbp+20h]

  v45 = a4;
  v44 = a3;
  v8 = a2;
  v10 = 0;
  v40 = 0;
  v39 = 0;
  LOBYTE(v44) = 0;
  v41 = 1;
  v11 = a8;
  *a8 = 0;
  v12 = (a7 & 0x200) != 0;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slSD(*((_QWORD *)WPP_GLOBAL_Control + 3), 30, a3, a4, 232, (__int64)a2->Buffer);
  }
  v13 = CClfsBaseFilePersisted::Initialize((CClfsBaseFilePersisted *)this, a7);
  if ( v13 >= 0 )
  {
    if ( this[4] || (v13 = CClfsBaseFile::InitializeImageResource((CClfsBaseFile *)this), v13 >= 0) )
    {
      v16 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue.32);
      if ( v16 )
        v18 = (CClfsAuthContainer *)CClfsAuthContainer::CClfsAuthContainer(
                                      v16,
                                      v17,
                                      *((unsigned int *)this + 58),
                                      this[30]);
      else
        v18 = 0;
      this[19] = v18;
      if ( !v18 )
      {
        v13 = -1073741670;
        goto LABEL_61;
      }
      (**(void (__fastcall ***)(CClfsAuthContainer *))v18)(v18);
      v13 = CClfsAuthContainer::Initialize(this[19], &v41, 1u);
      if ( v13 < 0 )
      {
LABEL_13:
        (*(void (__fastcall **)(CClfsAuthContainer *))(*(_QWORD *)this[19] + 8LL))(this[19]);
        this[19] = 0;
        goto LABEL_61;
      }
      v19 = this[28];
      if ( v19 )
      {
        ExFreePoolWithTag(v19, 0);
        this[28] = 0;
      }
      v20 = 2 * (v8->Length + 1LL);
      if ( !is_mul_ok(v8->Length + 1LL, 2u) )
        v20 = -1;
      PoolWithTag = (CClfsAuthContainer *)ExAllocatePoolWithTag(PagedPool, v20, 0x73666C43u);
      this[28] = PoolWithTag;
      if ( !PoolWithTag )
      {
        v13 = -1073741670;
        goto LABEL_13;
      }
      *((_WORD *)this + 109) = v8->Length + 2;
      Length = v8->Length;
      *((_WORD *)this + 108) = Length;
      memmove(PoolWithTag, v8->Buffer, Length);
      *((_WORD *)this[28] + ((unsigned __int64)*((unsigned __int16 *)this + 108) >> 1)) = 0;
      v23 = a5;
      v24 = *((_DWORD *)a5 + 4);
      if ( v24 )
      {
        v25 = (CClfsAuthContainer *)ExAllocatePoolWithTag(PagedPool, v24, 0x73666C43u);
        this[23] = v25;
        if ( !*((_QWORD *)v23 + 1) )
        {
          v13 = -1073741670;
          (*(void (__fastcall **)(CClfsAuthContainer *))(*(_QWORD *)this[19] + 8LL))(this[19]);
          this[19] = 0;
LABEL_60:
          v11 = a8;
          goto LABEL_61;
        }
        *((_DWORD *)this + 48) = *((_DWORD *)v23 + 4);
        memmove(v25, *((const void **)v23 + 1), *((unsigned int *)v23 + 4));
      }
      this[22] = *(CClfsAuthContainer **)v23;
      v26 = (unsigned __int64 *)(this + 31);
      v13 = 0;
      this[31] = 0;
      do
      {
        if ( *v26 )
          break;
        v13 = BCryptGenRandom(0, (PUCHAR)this + 248, 8u, 2u);
      }
      while ( v13 >= 0 );
      v27 = this[19];
      if ( v13 < 0 )
        goto LABEL_28;
      v28 = *v26;
      v41 = 0x10000;
      v13 = CClfsAuthContainer::Create(v27, v8, &v41, v23, a6, v12, v28, (unsigned __int8 *)&v44);
      if ( v13 == -1073741609 )
      {
        v29 = this[19];
        v30 = *v26;
        v42[0] = 0x10000;
        v13 = CClfsAuthContainer::Create(v29, v8, v42, v23, 0, v12, v30, (unsigned __int8 *)&v44);
      }
      v27 = this[19];
      if ( v13 < 0 )
      {
LABEL_28:
        (*(void (__fastcall **)(CClfsAuthContainer *))(*(_QWORD *)v27 + 8LL))(v27);
        this[19] = 0;
        goto LABEL_60;
      }
      RawSectorSize = CClfsAuthContainer::GetRawSectorSize(v27);
      *((_DWORD *)this + 36) = RawSectorSize;
      if ( RawSectorSize - 1 > 0xFFF || (RawSectorSize & 0x1FF) != 0 || 0x1000 % RawSectorSize )
      {
        v13 = -1073741672;
        goto LABEL_60;
      }
      if ( 6 * RawSectorSize > 0x10000 || (v32 = (0x10000 - 6 * RawSectorSize) >> 1, v32 < 0x13A8) )
      {
        v13 = -1073741789;
        goto LABEL_60;
      }
      this[17] = (CClfsAuthContainer *)0x10000;
      this[6] = (CClfsAuthContainer *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x90u, 0x73666C43u);
      v33 = (CClfsAuthContainer *)ExAllocatePoolWithTag((POOL_TYPE)512, 0xCu, 0x73666C43u);
      this[7] = v33;
      v34 = this[6];
      if ( !v34 || !v33 )
      {
        v13 = -1073741670;
        goto LABEL_60;
      }
      memset(v34, 0, 0x90u);
      v35 = this[7];
      *(_QWORD *)v35 = 0;
      *((_DWORD *)v35 + 2) = 0;
      v13 = CClfsBaseFilePersisted::CreateMetadataBlock(this, 0, &v39, 2 * RawSectorSize);
      if ( v13 < 0 )
        goto LABEL_60;
      CClfsBaseFile::GetControlRecord((CClfsBaseFile *)this, &v40, 1u);
      CClfsBaseFile::ReleaseMetadataBlock(this, 0);
      v10 = v40;
      *((_DWORD *)v40 + 5) = 0;
      *((_QWORD *)v10 + 1) = 0xC1F5C1F500005F1CuLL;
      *((_BYTE *)v10 + 16) = 1;
      v13 = CClfsBaseFilePersisted::CreateMetadataBlock(this, 2, &v39, v32);
      if ( v13 < 0 )
        goto LABEL_60;
      *((_BYTE *)this + 148) = 1;
      BaseLogRecord = CClfsBaseFile::GetBaseLogRecord((CClfsBaseFile *)this);
      if ( !BaseLogRecord )
      {
        v13 = -1072037875;
        goto LABEL_60;
      }
      *((_DWORD *)BaseLogRecord + 72) = 0;
      *((_QWORD *)BaseLogRecord + 37) = 0;
      *(_WORD *)((char *)BaseLogRecord + 4915) = 1;
      *((_BYTE *)BaseLogRecord + 292) = 1;
      *((_QWORD *)BaseLogRecord + 38) = 0;
      *((_DWORD *)BaseLogRecord + 1226) = 0;
      *((_BYTE *)BaseLogRecord + 4914) = 1;
      *(_QWORD *)BaseLogRecord = 0;
      *(_OWORD *)((char *)BaseLogRecord + 8) = CLFS_GUID_NULL;
      for ( i = 0; i < 0x14u; ++i )
      {
        v13 = ExUuidCreate((UUID *)((char *)BaseLogRecord + 8));
        if ( v13 != -1073741267 )
          goto LABEL_49;
      }
      v13 = -1073741693;
LABEL_49:
      if ( v13 < 0 )
      {
        v8 = a2;
        goto LABEL_60;
      }
      if ( v45 )
        *((_BYTE *)BaseLogRecord + 4914) |= 0x40u;
      *(_OWORD *)((char *)BaseLogRecord + 24) = 0;
      *(_OWORD *)((char *)BaseLogRecord + 40) = 0;
      *(_OWORD *)((char *)BaseLogRecord + 52) = 0;
      *((_OWORD *)BaseLogRecord + 7) = 0;
      *((_OWORD *)BaseLogRecord + 8) = 0;
      *(_OWORD *)((char *)BaseLogRecord + 140) = 0;
      memset((char *)BaseLogRecord + 312, 0, 0x1F0u);
      memset((char *)BaseLogRecord + 808, 0, 0x1000u);
      *(_OWORD *)((char *)BaseLogRecord + 200) = 0;
      *(_OWORD *)((char *)BaseLogRecord + 216) = 0;
      *(_OWORD *)((char *)BaseLogRecord + 228) = 0;
      this[8] = (struct _CLFS_BASE_RECORD_HEADER *)((char *)BaseLogRecord + 24);
      *((_DWORD *)this + 18) = 11;
      this[10] = (CClfsAuthContainer *)this;
      this[11] = (struct _CLFS_BASE_RECORD_HEADER *)((char *)BaseLogRecord + 112);
      *((_DWORD *)this + 24) = 11;
      this[13] = (CClfsAuthContainer *)this;
      this[14] = (struct _CLFS_BASE_RECORD_HEADER *)((char *)BaseLogRecord + 200);
      *((_DWORD *)this + 30) = 11;
      this[16] = (CClfsAuthContainer *)this;
      v8 = a2;
      v13 = CClfsBaseFilePersisted::AddMetaClient((CClfsBaseFilePersisted *)this, a2);
      if ( v13 < 0 )
        goto LABEL_60;
      v13 = CClfsBaseFilePersisted::CreateMetadataBlock(this, 4, &v39, RawSectorSize);
      if ( v13 < 0 )
        goto LABEL_60;
      v13 = CClfsBaseFilePersisted::WriteMetadataBlock((CClfsBaseFilePersisted *)this, 4u, 1u);
      CClfsBaseFile::ReleaseMetadataBlock(this, 4);
      v11 = a8;
      if ( v13 >= 0 )
      {
        *((_BYTE *)BaseLogRecord + 4914) |= 2u;
        *((_WORD *)v10 + 36) = *((_WORD *)this + 20);
        this[58] = v10;
      }
    }
  }
LABEL_61:
  if ( v10 && !this[58] )
    CClfsBaseFile::ReleaseMetadataBlock(this, 0);
  if ( v13 >= 0 )
  {
    if ( (_BYTE)v44 && (!a6 || !CClfsContainer::IsNullSecurityDescriptor(a6)) )
      *v11 = 1;
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slSD(*((_QWORD *)WPP_GLOBAL_Control + 3), 31, v14, v15, 219, (__int64)v8->Buffer);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400374cc  mov     r11, rsp
0x1400374cf  mov     [r11+20h], r9b
0x1400374d3  mov     [r11+18h], r8d
0x1400374d7  mov     [r11+10h], rdx
0x1400374db  mov     [r11+8], rcx
0x1400374df  push    rbx
0x1400374e0  push    rsi
0x1400374e1  push    rdi
0x1400374e2  push    r12
0x1400374e4  push    r13
0x1400374e6  push    r14
0x1400374e8  push    r15
0x1400374ea  sub     rsp, 70h
0x1400374ee  mov     r12, rdx
0x1400374f1  mov     rsi, rcx
0x1400374f4  xor     r13d, r13d
0x1400374f7  mov     [r11-58h], r13
0x1400374fb  mov     [r11-60h], r13d
0x1400374ff  mov     [r11-64h], r13d
0x140037503  mov     [r11+18h], r13b
0x140037507  lea     r14d, [r13+1]
0x14003750b  mov     [r11-50h], r14
0x14003750f  mov     rdi, [rsp+0A8h+arg_38]
0x140037517  mov     [rdi], r13b
0x14003751a  mov     r15d, [rsp+0A8h+arg_30]
0x140037522  shr     r15d, 9
0x140037526  and     r15b, r14b
0x140037529  lea     rax, WPP_GLOBAL_Control
0x140037530  mov     rcx, cs:WPP_GLOBAL_Control
0x140037537  cmp     rcx, rax
0x14003753a  jz      short loc_140037564
0x14003753c  mov     eax, [rcx+2Ch]
0x14003753f  bt      eax, 1Ah
0x140037543  jnb     short loc_140037564
0x140037545  lea     edx, [r13+1Eh]
0x140037549  mov     rax, [r12+8]
0x14003754e  mov     [r11-80h], rax
0x140037552  mov     dword ptr [rsp+0A8h+var_88], 1AE8h
0x14003755a  mov     rcx, [rcx+18h]
0x14003755e  call    WPP_SF_slSD
0x140037563  nop
0x140037564  mov     edx, [rsp+0A8h+arg_30]; unsigned int
0x14003756b  mov     rcx, rsi; this
0x14003756e  call    ?Initialize@CClfsBaseFilePersisted@@AEAAJK@Z; CClfsBaseFilePersisted::Initialize(ulong)
0x140037573  mov     ebx, eax
0x140037575  mov     [rsp+0A8h+var_64], eax
0x140037579  test    eax, eax
0x14003757b  js      loc_140037BDF
0x140037581  cmp     qword ptr [rsi+20h], 0
0x140037586  jnz     short loc_14003759E
0x140037588  mov     rcx, rsi; this
0x14003758b  call    ?InitializeImageResource@CClfsBaseFile@@IEAAJXZ; CClfsBaseFile::InitializeImageResource(void)
0x140037590  mov     ebx, eax
0x140037592  mov     [rsp+0A8h+var_64], eax
0x140037596  test    eax, eax
0x140037598  js      loc_140037BDF
0x14003759e  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h; Lookaside
0x1400375a5  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400375ac  nop     dword ptr [rax+rax+00h]
0x1400375b1  test    rax, rax
0x1400375b4  jz      short loc_1400375D1
0x1400375b6  mov     r9, [rsi+0F0h]
0x1400375bd  mov     r8d, [rsi+0E8h]
0x1400375c4  mov     rcx, rax
0x1400375c7  call    ??0CClfsAuthContainer@@QEAA@KW4_CLFS_AUTHENTICATION_MODE@@PEAU_DEVICE_OBJECT@@@Z; CClfsAuthContainer::CClfsAuthContainer(ulong,_CLFS_AUTHENTICATION_MODE,_DEVICE_OBJECT *)
0x1400375cc  mov     rcx, rax
0x1400375cf  jmp     short loc_1400375D3
0x1400375d1  xor     ecx, ecx
0x1400375d3  mov     [rsi+98h], rcx
0x1400375da  test    rcx, rcx
0x1400375dd  jnz     short loc_1400375ED
0x1400375df  mov     ebx, 0C000009Ah
0x1400375e4  mov     [rsp+0A8h+var_64], ebx
0x1400375e8  jmp     loc_140037BDF
0x1400375ed  mov     rax, [rcx]
0x1400375f0  mov     rax, [rax]
0x1400375f3  call    _guard_dispatch_icall
0x1400375f8  mov     r8d, r14d; unsigned int
0x1400375fb  lea     rdx, [rsp+0A8h+var_50]; unsigned __int64 *
0x140037600  mov     rcx, [rsi+98h]; this
0x140037607  call    ?Initialize@CClfsAuthContainer@@QEAAJPEA_KK@Z; CClfsAuthContainer::Initialize(unsigned __int64 *,ulong)
0x14003760c  mov     ebx, eax
0x14003760e  mov     [rsp+0A8h+var_64], eax
0x140037612  test    eax, eax
0x140037614  jns     short loc_140037639
0x140037616  mov     rcx, [rsi+98h]
0x14003761d  mov     rax, [rcx]
0x140037620  mov     rax, [rax+8]
0x140037624  call    _guard_dispatch_icall
0x140037629  mov     qword ptr [rsi+98h], 0
0x140037634  jmp     loc_140037BDF
0x140037639  mov     rcx, [rsi+0E0h]; P
0x140037640  test    rcx, rcx
0x140037643  jz      short loc_14003765E
0x140037645  xor     edx, edx; Tag
0x140037647  call    cs:__imp_ExFreePoolWithTag
0x14003764e  nop     dword ptr [rax+rax+00h]
0x140037653  mov     qword ptr [rsi+0E0h], 0
0x14003765e  movzx   ecx, word ptr [r12]
0x140037663  add     rcx, r14
0x140037666  mov     eax, 2
0x14003766b  mul     rcx
0x14003766e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140037675  cmovb   rax, rcx
0x140037679  mov     ebx, 73666C43h
0x14003767e  mov     r8d, ebx; Tag
0x140037681  mov     rdx, rax; NumberOfBytes
0x140037684  mov     ecx, r14d; PoolType
0x140037687  call    cs:__imp_ExAllocatePoolWithTag
0x14003768e  nop     dword ptr [rax+rax+00h]
0x140037693  mov     rcx, rax; void *
0x140037696  mov     [rsi+0E0h], rax
0x14003769d  test    rax, rax
0x1400376a0  jnz     short loc_1400376B0
0x1400376a2  mov     ebx, 0C000009Ah
0x1400376a7  mov     [rsp+0A8h+var_64], ebx
0x1400376ab  jmp     loc_140037616
0x1400376b0  movzx   eax, word ptr [r12]
0x1400376b5  add     ax, 2
0x1400376b9  mov     [rsi+0DAh], ax
0x1400376c0  movzx   eax, word ptr [r12]
0x1400376c5  mov     [rsi+0D8h], ax
0x1400376cc  mov     r8d, eax; Size
0x1400376cf  mov     rdx, [r12+8]; Src
0x1400376d4  call    memmove
0x1400376d9  movzx   edx, word ptr [rsi+0D8h]
0x1400376e0  shr     rdx, 1
0x1400376e3  mov     rcx, [rsi+0E0h]
0x1400376ea  xor     eax, eax
0x1400376ec  mov     [rcx+rdx*2], ax
0x1400376f0  mov     rdi, [rsp+0A8h+arg_20]
0x1400376f8  mov     eax, [rdi+10h]
0x1400376fb  test    eax, eax
0x1400376fd  jz      short loc_140037766
0x1400376ff  mov     edx, eax; NumberOfBytes
0x140037701  mov     r8d, ebx; Tag
0x140037704  mov     ecx, r14d; PoolType
0x140037707  call    cs:__imp_ExAllocatePoolWithTag
0x14003770e  nop     dword ptr [rax+rax+00h]
0x140037713  mov     rcx, rax; void *
0x140037716  mov     [rsi+0B8h], rax
0x14003771d  cmp     qword ptr [rdi+8], 0
0x140037722  jnz     short loc_140037750
0x140037724  mov     ebx, 0C000009Ah
0x140037729  mov     [rsp+0A8h+var_64], ebx
0x14003772d  mov     rcx, [rsi+98h]
0x140037734  mov     rax, [rcx]
0x140037737  mov     rax, [rax+8]
0x14003773b  call    _guard_dispatch_icall
0x140037740  mov     qword ptr [rsi+98h], 0
0x14003774b  jmp     loc_140037BD7
0x140037750  mov     eax, [rdi+10h]
0x140037753  mov     [rsi+0C0h], eax
0x140037759  mov     r8d, [rdi+10h]; Size
0x14003775d  mov     rdx, [rdi+8]; Src
0x140037761  call    memmove
0x140037766  mov     rax, [rdi]
0x140037769  mov     [rsi+0B0h], rax
0x140037770  lea     r14, [rsi+0F8h]
0x140037777  xor     ebx, ebx
0x140037779  mov     [r14], rbx
0x14003777c  cmp     qword ptr [r14], 0
0x140037780  jnz     short loc_1400377A5
0x140037782  mov     r9d, 2; dwFlags
0x140037788  lea     r8d, [r9+6]; cbBuffer
0x14003778c  mov     rdx, r14; pbBuffer
0x14003778f  xor     ecx, ecx; hAlgorithm
0x140037791  call    cs:__imp_BCryptGenRandom
0x140037798  nop     dword ptr [rax+rax+00h]
0x14003779d  mov     ebx, eax
0x14003779f  test    eax, eax
0x1400377a1  js      short loc_1400377A5
0x1400377a3  jmp     short loc_14003777C
0x1400377a5  mov     [rsp+0A8h+var_64], ebx
0x1400377a9  mov     rcx, [rsi+98h]; this
0x1400377b0  test    ebx, ebx
0x1400377b2  jns     short loc_1400377D0
0x1400377b4  mov     rax, [rcx]
0x1400377b7  mov     rax, [rax+8]
0x1400377bb  call    _guard_dispatch_icall
0x1400377c0  mov     qword ptr [rsi+98h], 0
0x1400377cb  jmp     loc_140037BD1
0x1400377d0  mov     rax, [r14]
0x1400377d3  mov     [rsp+0A8h+var_50], 10000h
0x1400377dc  lea     rdx, [rsp+0A8h+arg_10]
0x1400377e4  mov     [rsp+0A8h+var_70], rdx; unsigned __int8 *
0x1400377e9  mov     [rsp+0A8h+var_78], rax; unsigned __int64
0x1400377ee  mov     [rsp+0A8h+var_80], r15b; unsigned __int8
0x1400377f3  mov     rax, [rsp+0A8h+arg_28]
0x1400377fb  mov     [rsp+0A8h+var_88], rax; void *
0x140037800  mov     r9, rdi; struct _CLFS_FILTER_CONTEXT *
0x140037803  lea     r8, [rsp+0A8h+var_50]; unsigned __int64 *
0x140037808  mov     rdx, r12; struct _UNICODE_STRING *
0x14003780b  call    ?Create@CClfsAuthContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXE_KAEAE@Z; CClfsAuthContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,unsigned __int64,uchar &)
0x140037810  mov     ebx, eax
0x140037812  mov     [rsp+0A8h+var_64], eax
0x140037816  cmp     eax, 0C00000D7h
0x14003781b  jnz     short loc_14003786A
0x14003781d  mov     rcx, [rsi+98h]; this
0x140037824  mov     rax, [r14]
0x140037827  mov     r14d, 10000h
0x14003782d  mov     [rsp+0A8h+var_48], r14
0x140037832  lea     rdx, [rsp+0A8h+arg_10]
0x14003783a  mov     [rsp+0A8h+var_70], rdx; unsigned __int8 *
0x14003783f  mov     [rsp+0A8h+var_78], rax; unsigned __int64
0x140037844  mov     [rsp+0A8h+var_80], r15b; unsigned __int8
0x140037849  mov     [rsp+0A8h+var_88], 0; void *
0x140037852  mov     r9, rdi; struct _CLFS_FILTER_CONTEXT *
0x140037855  lea     r8, [rsp+0A8h+var_48]; unsigned __int64 *
0x14003785a  mov     rdx, r12; struct _UNICODE_STRING *
0x14003785d  call    ?Create@CClfsAuthContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXE_KAEAE@Z; CClfsAuthContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,unsigned __int64,uchar &)
0x140037862  mov     ebx, eax
0x140037864  mov     [rsp+0A8h+var_64], eax
0x140037868  jmp     short loc_140037870
0x14003786a  mov     r14d, 10000h
0x140037870  mov     rcx, [rsi+98h]; this
0x140037877  test    ebx, ebx
0x140037879  js      loc_1400377B4
0x14003787f  call    ?GetRawSectorSize@CClfsAuthContainer@@QEAAKXZ; CClfsAuthContainer::GetRawSectorSize(void)
0x140037884  mov     r15d, eax
0x140037887  mov     [rsi+90h], eax
0x14003788d  dec     eax
0x14003788f  cmp     eax, 0FFFh
0x140037894  ja      loc_140037BBF
0x14003789a  test    r15d, 1FFh
0x1400378a1  jnz     loc_140037BBF
0x1400378a7  xor     edx, edx
0x1400378a9  mov     eax, 1000h
0x1400378ae  div     r15d
0x1400378b1  test    edx, edx
0x1400378b3  jnz     loc_140037BBF
0x1400378b9  lea     ebx, [r15+r15]
0x1400378bd  lea     eax, [rbx+r15]
0x1400378c1  add     eax, eax
0x1400378c3  cmp     eax, r14d
0x1400378c6  jbe     short loc_1400378D6
0x1400378c8  mov     ebx, 0C0000023h
0x1400378cd  mov     [rsp+0A8h+var_64], ebx
0x1400378d1  jmp     loc_140037BD1
0x1400378d6  mov     edi, r14d
0x1400378d9  sub     edi, eax
0x1400378db  shr     edi, 1
0x1400378dd  cmp     edi, 13A8h
0x1400378e3  jb      short loc_1400378C8
0x1400378e5  mov     [rsi+88h], r14
0x1400378ec  mov     edx, 90h; NumberOfBytes
0x1400378f1  mov     r8d, 73666C43h; Tag
0x1400378f7  mov     r14d, 200h
0x1400378fd  mov     ecx, r14d; PoolType
0x140037900  call    cs:__imp_ExAllocatePoolWithTag
0x140037907  nop     dword ptr [rax+rax+00h]
0x14003790c  mov     [rsi+30h], rax
0x140037910  mov     edx, 0Ch; NumberOfBytes
0x140037915  mov     r8d, 73666C43h; Tag
0x14003791b  mov     ecx, r14d; PoolType
0x14003791e  call    cs:__imp_ExAllocatePoolWithTag
0x140037925  nop     dword ptr [rax+rax+00h]
0x14003792a  mov     [rsi+38h], rax
0x14003792e  mov     rcx, [rsi+30h]; void *
0x140037932  test    rcx, rcx
0x140037935  jz      loc_140037BB5
0x14003793b  test    rax, rax
0x14003793e  jz      loc_140037BB5
0x140037944  xor     edx, edx; Val
0x140037946  mov     r8d, 90h; Size
0x14003794c  call    memset
0x140037951  xor     ecx, ecx
0x140037953  mov     rax, [rsi+38h]
0x140037957  mov     [rax], rcx
0x14003795a  mov     [rax+8], ecx
0x14003795d  mov     r9d, ebx
0x140037960  lea     r8, [rsp+0A8h+var_60]
0x140037965  xor     edx, edx
0x140037967  mov     rcx, rsi
0x14003796a  call    ?CreateMetadataBlock@CClfsBaseFilePersisted@@AEAAJW4_CLFS_METADATA_BLOCK_TYPE@@AEAKK@Z; CClfsBaseFilePersisted::CreateMetadataBlock(_CLFS_METADATA_BLOCK_TYPE,ulong &,ulong)
0x14003796f  mov     ebx, eax
0x140037971  mov     [rsp+0A8h+var_64], eax
0x140037975  test    eax, eax
0x140037977  js      loc_140037BD1
0x14003797d  mov     r14d, 1
0x140037983  mov     r8b, r14b; unsigned __int8
0x140037986  lea     rdx, [rsp+0A8h+var_58]; struct _CLFS_CONTROL_RECORD **
0x14003798b  mov     rcx, rsi; this
0x14003798e  call    ?GetControlRecord@CClfsBaseFile@@IEAAJAEAPEAU_CLFS_CONTROL_RECORD@@E@Z; CClfsBaseFile::GetControlRecord(_CLFS_CONTROL_RECORD * &,uchar)
0x140037993  mov     [rsp+0A8h+var_64], eax
0x140037997  xor     edx, edx
0x140037999  mov     rcx, rsi
0x14003799c  call    ?ReleaseMetadataBlock@CClfsBaseFile@@IEAAXW4_CLFS_METADATA_BLOCK_TYPE@@@Z; CClfsBaseFile::ReleaseMetadataBlock(_CLFS_METADATA_BLOCK_TYPE)
0x1400379a1  mov     r13, [rsp+0A8h+var_58]
0x1400379a6  mov     dword ptr [r13+14h], 0
0x1400379ae  mov     rax, 0C1F5C1F500005F1Ch
0x1400379b8  mov     [r13+8], rax
0x1400379bc  mov     [r13+10h], r14b
0x1400379c0  mov     r9d, edi
0x1400379c3  lea     r8, [rsp+0A8h+var_60]
0x1400379c8  lea     edx, [r14+1]
0x1400379cc  mov     rcx, rsi
0x1400379cf  call    ?CreateMetadataBlock@CClfsBaseFilePersisted@@AEAAJW4_CLFS_METADATA_BLOCK_TYPE@@AEAKK@Z; CClfsBaseFilePersisted::CreateMetadataBlock(_CLFS_METADATA_BLOCK_TYPE,ulong &,ulong)
0x1400379d4  mov     ebx, eax
0x1400379d6  mov     [rsp+0A8h+var_64], eax
  ... truncated ...
```
