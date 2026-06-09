# CClfsBaseFilePersisted::OpenImage(_UNICODE_STRING *,_CLFS_FILTER_CONTEXT const &,ulong,uchar &)

- ea: `0x1400632d4`
- end: `0x1400637e4`
- name: `?OpenImage@CClfsBaseFilePersisted@@QEAAJPEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@KAEAE@Z`
- size: `1296`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFilePersisted *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, const struct _CLFS_FILTER_CONTEXT *@<r8>, unsigned int@<r9d>, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005f1c`
- `0x140040444`

## callees

- `0x140012418`
- `0x140017f20`
- `0x140017f80`
- `0x140033898`
- `0x140034a20`
- `0x140037f48`
- `0x14003cc4c`
- `0x14005ff58`
- `0x140062c20`
- `0x1400632d4`
- `0x1400637ec`
- `0x140063844`
- `0x140063b84`
- `0x14006a6fc`
- `0x14006c4c0`
- `0x140071438`
- `0x14007493c`
- `0x14007634c`
- `0x140078d5c`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140063391`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140063391`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063456`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063775`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a95e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063456`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063775`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a95e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140063493`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140063505`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140063493`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140063505`

## string_xrefs

- `0x14006333d`: `CClfsBaseFilePersisted::OpenImage`
- `0x1400637b3`: `CClfsBaseFilePersisted::OpenImage`
- `0x14007a9a4`: `CClfsBaseFilePersisted::OpenImage`

## pseudocode

```c
__int64 __fastcall CClfsBaseFilePersisted::OpenImage(
        CClfsBaseFilePersisted *this,
        struct _UNICODE_STRING *a2,
        const struct _CLFS_FILTER_CONTEXT *a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  unsigned __int8 *v9; // r12
  unsigned __int8 v10; // r14
  __int64 result; // rax
  PVOID v12; // rax
  __int64 v13; // rdx
  void (__fastcall ***v14)(_QWORD); // rcx
  int ContainerSize; // ebx
  void *v16; // rcx
  SIZE_T v17; // rax
  PVOID PoolWithTag; // rcx
  unsigned int Length; // eax
  unsigned int v20; // eax
  PVOID v21; // rcx
  int v22; // eax
  CClfsAuthContainer *v23; // rcx
  unsigned int RawSectorSize; // eax
  struct _CLFS_BASE_RECORD_HEADER *BaseLogRecord; // rax
  struct _CLFS_CONTROL_RECORD *v26; // rsi
  unsigned __int16 v27; // cx
  unsigned __int16 v28; // dx
  unsigned __int16 v29; // ax
  int v30; // eax
  PVOID P; // [rsp+50h] [rbp-50h] BYREF
  struct _CLFS_CONTROL_RECORD *v32; // [rsp+58h] [rbp-48h] BYREF
  unsigned __int8 v33; // [rsp+C0h] [rbp+20h] BYREF

  v32 = 0;
  v33 = 0;
  P = (PVOID)1;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slS(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      32,
      (unsigned int)WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids,
      (unsigned int)"CClfsBaseFilePersisted::OpenImage",
      113,
      (__int64)a2->Buffer);
  }
  v9 = a5;
  *a5 = 0;
  v10 = (a4 & 0x200) != 0;
  result = CClfsBaseFilePersisted::Initialize(this, a4);
  if ( (int)result >= 0 )
  {
    if ( !*((_QWORD *)this + 19) )
    {
      v12 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue.32);
      if ( v12 )
        v14 = (void (__fastcall ***)(_QWORD))CClfsAuthContainer::CClfsAuthContainer(
                                               v12,
                                               v13,
                                               *((unsigned int *)this + 58),
                                               *((_QWORD *)this + 30));
      else
        v14 = 0;
      *((_QWORD *)this + 19) = v14;
      if ( !v14 )
        return 3221225626LL;
      (**v14)(v14);
      ContainerSize = CClfsAuthContainer::Initialize(*((CClfsAuthContainer **)this + 19), (unsigned __int64 *)&P, 1u);
      if ( ContainerSize < 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 8LL))(*((_QWORD *)this + 19));
        *((_QWORD *)this + 19) = 0;
        return (unsigned int)ContainerSize;
      }
    }
    if ( !*((_QWORD *)this + 4) )
    {
      ContainerSize = CClfsBaseFile::InitializeImageResource(this);
      if ( ContainerSize < 0 )
      {
LABEL_47:
        P = 0;
        if ( ContainerSize >= 0 )
        {
          if ( v33 )
          {
            LODWORD(a5) = 0;
            v30 = CClfsBaseFilePersisted::QueryContainerSecurity(
                    *((struct CClfsAuthContainer **)this + 19),
                    &P,
                    0,
                    (unsigned int *)&a5);
            ContainerSize = 0;
            if ( v30 < 0 )
              ContainerSize = v30;
            if ( ContainerSize >= 0 )
            {
              if ( !CClfsContainer::IsNullSecurityDescriptor(P) )
                *v9 = 1;
              ExFreePoolWithTag(P, 0);
            }
          }
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
          {
            WPP_SF_slS(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              33,
              (unsigned int)WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids,
              (unsigned int)"CClfsBaseFilePersisted::OpenImage",
              197,
              (__int64)a2->Buffer);
          }
        }
        if ( v32 )
          CClfsBaseFile::ReleaseMetadataBlock(this, 0);
        return (unsigned int)ContainerSize;
      }
    }
    v16 = (void *)*((_QWORD *)this + 28);
    if ( v16 )
    {
      ExFreePoolWithTag(v16, 0);
      *((_QWORD *)this + 28) = 0;
    }
    v17 = 2 * (a2->Length + 1LL);
    if ( !is_mul_ok(a2->Length + 1LL, 2u) )
      v17 = -1;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, v17, 0x73666C43u);
    *((_QWORD *)this + 28) = PoolWithTag;
    if ( !PoolWithTag )
    {
LABEL_22:
      ContainerSize = -1073741670;
      goto LABEL_47;
    }
    *((_WORD *)this + 109) = a2->Length + 2;
    Length = a2->Length;
    *((_WORD *)this + 108) = Length;
    memmove(PoolWithTag, a2->Buffer, Length);
    *(_WORD *)(*((_QWORD *)this + 28) + 2 * ((unsigned __int64)*((unsigned __int16 *)this + 108) >> 1)) = 0;
    v20 = *((_DWORD *)a3 + 4);
    if ( v20 )
    {
      v21 = ExAllocatePoolWithTag(PagedPool, v20, 0x73666C43u);
      *((_QWORD *)this + 23) = v21;
      if ( !*((_QWORD *)a3 + 1) )
        goto LABEL_22;
      *((_DWORD *)this + 48) = *((_DWORD *)a3 + 4);
      memmove(v21, *((const void **)a3 + 1), *((unsigned int *)a3 + 4));
    }
    *((_QWORD *)this + 22) = *(_QWORD *)a3;
    v22 = CClfsAuthContainer::Open(*((CClfsAuthContainer **)this + 19), a2, a3, v10, 0, &v33);
    ContainerSize = v22;
    if ( v22 < 0 )
      goto LABEL_27;
    *((_QWORD *)this + 31) = CClfsAuthContainer::GetContainerGroup(*((CClfsAuthContainer **)this + 19));
    RawSectorSize = CClfsAuthContainer::GetRawSectorSize(v23);
    *((_DWORD *)this + 36) = RawSectorSize;
    if ( RawSectorSize - 1 > 0xFFF || (RawSectorSize & 0x1FF) != 0 || 0x1000 % RawSectorSize )
    {
      ContainerSize = -1073741672;
      goto LABEL_47;
    }
    v22 = CClfsBaseFilePersisted::ReadImage(this, &v32);
    ContainerSize = v22;
    if ( v22 < 0 )
    {
LABEL_27:
      if ( v22 != -1073741807 )
        goto LABEL_47;
    }
    else
    {
      ContainerSize = CClfsAuthContainer::GetContainerSize(
                        *((CClfsAuthContainer **)this + 19),
                        (unsigned __int64 *)this + 17);
      if ( ContainerSize < 0 )
        goto LABEL_47;
      BaseLogRecord = CClfsBaseFile::GetBaseLogRecord(this);
      if ( BaseLogRecord )
      {
        *((_QWORD *)this + 8) = (char *)BaseLogRecord + 24;
        *((_DWORD *)this + 18) = 11;
        *((_QWORD *)this + 10) = this;
        *((_QWORD *)this + 11) = (char *)BaseLogRecord + 112;
        *((_DWORD *)this + 24) = 11;
        *((_QWORD *)this + 13) = this;
        *((_QWORD *)this + 14) = (char *)BaseLogRecord + 200;
        *((_DWORD *)this + 30) = 11;
        *((_QWORD *)this + 16) = this;
        v26 = v32;
        if ( !*((_DWORD *)v32 + 5) )
          goto LABEL_47;
        v27 = *((_WORD *)v32 + 12);
        if ( v27 )
        {
          v28 = *((_WORD *)this + 20);
          if ( v27 < v28 && ((v27 - 2) & 0xFFFD) == 0 )
          {
            v29 = *((_WORD *)v32 + 13);
            if ( v29 )
            {
              if ( v29 < v28
                && v29 < 6u
                && v29 >= v27
                && *((_DWORD *)v26 + 8) <= (unsigned int)CClfsBaseFile::GetSize(this) >> 9
                && *((_DWORD *)v26 + 7) <= (unsigned int)((*((_DWORD *)v26 + 9) >> 1)
                                                        + (*(_DWORD *)(*((_QWORD *)this + 6)
                                                                     + 24LL * *((unsigned __int16 *)v26 + 12)
                                                                     + 8) >> 9)) )
              {
                ContainerSize = CClfsBaseFilePersisted::ExtendMetadataBlock(this, *((unsigned __int16 *)v26 + 12));
                goto LABEL_47;
              }
            }
          }
        }
      }
    }
    ContainerSize = -1072037875;
    goto LABEL_47;
  }
  return result;
}

```

## disassembly

```asm
0x1400632d4  mov     r11, rsp
0x1400632d7  mov     [r11+10h], rdx
0x1400632db  mov     [r11+8], rcx
0x1400632df  push    rbx
0x1400632e0  push    rsi
0x1400632e1  push    rdi
0x1400632e2  push    r12
0x1400632e4  push    r13
0x1400632e6  push    r14
0x1400632e8  push    r15
0x1400632ea  sub     rsp, 50h
0x1400632ee  mov     ebx, r9d
0x1400632f1  mov     rsi, r8
0x1400632f4  mov     r15, rdx
0x1400632f7  mov     rdi, rcx
0x1400632fa  xor     r13d, r13d
0x1400632fd  mov     [r11-48h], r13
0x140063301  mov     [r11+20h], r13b
0x140063305  mov     qword ptr [r11-50h], 1
0x14006330d  lea     rax, WPP_GLOBAL_Control
0x140063314  mov     rcx, cs:WPP_GLOBAL_Control
0x14006331b  cmp     rcx, rax
0x14006331e  jz      short loc_140063354
0x140063320  test    dword ptr [rcx+2Ch], 4000000h
0x140063327  jz      short loc_140063354
0x140063329  lea     edx, [r13+20h]
0x14006332d  mov     rax, [r15+8]
0x140063331  mov     [r11-60h], rax
0x140063335  mov     dword ptr [rsp+88h+var_68], 1D71h
0x14006333d  lea     r9, aCclfsbasefilep_4; "CClfsBaseFilePersisted::OpenImage"
0x140063344  lea     r8, WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids
0x14006334b  mov     rcx, [rcx+18h]
0x14006334f  call    WPP_SF_slS
0x140063354  mov     r12, [rsp+88h+arg_20]
0x14006335c  mov     [r12], r13b
0x140063360  mov     r14d, ebx
0x140063363  shr     r14d, 9
0x140063367  and     r14b, 1
0x14006336b  mov     edx, ebx; unsigned int
0x14006336d  mov     rcx, rdi; this
0x140063370  call    ?Initialize@CClfsBaseFilePersisted@@AEAAJK@Z; CClfsBaseFilePersisted::Initialize(ulong)
0x140063375  mov     [rsp+88h+var_58], eax
0x140063379  test    eax, eax
0x14006337b  js      short loc_1400633D1
0x14006337d  cmp     [rdi+98h], r13
0x140063384  jnz     loc_14006342C
0x14006338a  lea     rcx, WPP_MAIN_CB.DeviceQueue.20h; Lookaside
0x140063391  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140063398  nop     dword ptr [rax+rax+00h]
0x14006339d  test    rax, rax
0x1400633a0  jz      short loc_1400633BD
0x1400633a2  mov     r9, [rdi+0F0h]
0x1400633a9  mov     r8d, [rdi+0E8h]
0x1400633b0  mov     rcx, rax
0x1400633b3  call    ??0CClfsAuthContainer@@QEAA@KW4_CLFS_AUTHENTICATION_MODE@@PEAU_DEVICE_OBJECT@@@Z; CClfsAuthContainer::CClfsAuthContainer(ulong,_CLFS_AUTHENTICATION_MODE,_DEVICE_OBJECT *)
0x1400633b8  mov     rcx, rax
0x1400633bb  jmp     short loc_1400633C0
0x1400633bd  mov     rcx, r13
0x1400633c0  mov     [rdi+98h], rcx
0x1400633c7  test    rcx, rcx
0x1400633ca  jnz     short loc_1400633E2
0x1400633cc  mov     eax, 0C000009Ah
0x1400633d1  add     rsp, 50h
0x1400633d5  pop     r15
0x1400633d7  pop     r14
0x1400633d9  pop     r13
0x1400633db  pop     r12
0x1400633dd  pop     rdi
0x1400633de  pop     rsi
0x1400633df  pop     rbx
0x1400633e0  retn
0x1400633e2  mov     rax, [rcx]
0x1400633e5  mov     rax, [rax]
0x1400633e8  call    _guard_dispatch_icall
0x1400633ed  mov     r8d, 1; unsigned int
0x1400633f3  lea     rdx, [rsp+88h+P]; unsigned __int64 *
0x1400633f8  mov     rcx, [rdi+98h]; this
0x1400633ff  call    ?Initialize@CClfsAuthContainer@@QEAAJPEA_KK@Z; CClfsAuthContainer::Initialize(unsigned __int64 *,ulong)
0x140063404  mov     ebx, eax
0x140063406  mov     [rsp+88h+var_58], eax
0x14006340a  test    eax, eax
0x14006340c  jns     short loc_14006342C
0x14006340e  mov     rcx, [rdi+98h]
0x140063415  mov     rdx, [rcx]
0x140063418  mov     rax, [rdx+8]
0x14006341c  call    _guard_dispatch_icall
0x140063421  mov     [rdi+98h], r13
0x140063428  mov     eax, ebx
0x14006342a  jmp     short loc_1400633D1
0x14006342c  cmp     [rdi+20h], r13
0x140063430  jnz     short loc_140063448
0x140063432  mov     rcx, rdi; this
0x140063435  call    ?InitializeImageResource@CClfsBaseFile@@IEAAJXZ; CClfsBaseFile::InitializeImageResource(void)
0x14006343a  mov     ebx, eax
0x14006343c  mov     [rsp+88h+var_58], eax
0x140063440  test    eax, eax
0x140063442  js      loc_140063714
0x140063448  mov     rcx, [rdi+0E0h]; P
0x14006344f  test    rcx, rcx
0x140063452  jz      short loc_140063469
0x140063454  xor     edx, edx; Tag
0x140063456  call    cs:__imp_ExFreePoolWithTag
0x14006345d  nop     dword ptr [rax+rax+00h]
0x140063462  mov     [rdi+0E0h], r13
0x140063469  movzx   ecx, word ptr [r15]
0x14006346d  inc     rcx
0x140063470  mov     eax, 2
0x140063475  mul     rcx
0x140063478  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14006347f  cmovb   rax, rcx
0x140063483  mov     ebx, 73666C43h
0x140063488  mov     r8d, ebx; Tag
0x14006348b  mov     rdx, rax; NumberOfBytes
0x14006348e  mov     ecx, 1; PoolType
0x140063493  call    cs:__imp_ExAllocatePoolWithTag
0x14006349a  nop     dword ptr [rax+rax+00h]
0x14006349f  mov     rcx, rax; void *
0x1400634a2  mov     [rdi+0E0h], rax
0x1400634a9  test    rax, rax
0x1400634ac  jnz     short loc_1400634B8
0x1400634ae  mov     ebx, 0C000009Ah
0x1400634b3  jmp     loc_140063710
0x1400634b8  movzx   eax, word ptr [r15]
0x1400634bc  add     ax, 2
0x1400634c0  mov     [rdi+0DAh], ax
0x1400634c7  movzx   eax, word ptr [r15]
0x1400634cb  mov     [rdi+0D8h], ax
0x1400634d2  mov     r8d, eax; Size
0x1400634d5  mov     rdx, [r15+8]; Src
0x1400634d9  call    memmove
0x1400634de  movzx   edx, word ptr [rdi+0D8h]
0x1400634e5  shr     rdx, 1
0x1400634e8  mov     rcx, [rdi+0E0h]
0x1400634ef  mov     [rcx+rdx*2], r13w
0x1400634f4  mov     eax, [rsi+10h]
0x1400634f7  test    eax, eax
0x1400634f9  jz      short loc_140063537
0x1400634fb  mov     edx, eax; NumberOfBytes
0x1400634fd  mov     r8d, ebx; Tag
0x140063500  mov     ecx, 1; PoolType
0x140063505  call    cs:__imp_ExAllocatePoolWithTag
0x14006350c  nop     dword ptr [rax+rax+00h]
0x140063511  mov     rcx, rax; void *
0x140063514  mov     [rdi+0B8h], rax
0x14006351b  cmp     [rsi+8], r13
0x14006351f  jz      short loc_1400634AE
0x140063521  mov     eax, [rsi+10h]
0x140063524  mov     [rdi+0C0h], eax
0x14006352a  mov     r8d, [rsi+10h]; Size
0x14006352e  mov     rdx, [rsi+8]; Src
0x140063532  call    memmove
0x140063537  mov     rax, [rsi]
0x14006353a  mov     [rdi+0B0h], rax
0x140063541  lea     rax, [rsp+88h+arg_18]
0x140063549  mov     [rsp+88h+var_60], rax; unsigned __int8 *
0x14006354e  mov     [rsp+88h+var_68], r13; unsigned __int64
0x140063553  mov     r9b, r14b; unsigned __int8
0x140063556  mov     r8, rsi; struct _CLFS_FILTER_CONTEXT *
0x140063559  mov     rdx, r15; struct _UNICODE_STRING *
0x14006355c  mov     rcx, [rdi+98h]; this
0x140063563  call    ?Open@CClfsAuthContainer@@QEAAJAEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@E_KAEAE@Z; CClfsAuthContainer::Open(_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,uchar,unsigned __int64,uchar &)
0x140063568  mov     ebx, eax
0x14006356a  mov     [rsp+88h+var_58], eax
0x14006356e  test    eax, eax
0x140063570  jns     short loc_140063587
0x140063572  cmp     eax, 0C0000011h
0x140063577  jnz     loc_140063714
0x14006357d  mov     ebx, 0C01A000Dh
0x140063582  jmp     loc_140063710
0x140063587  mov     rcx, [rdi+98h]; this
0x14006358e  call    ?GetContainerGroup@CClfsAuthContainer@@QEAA_KXZ; CClfsAuthContainer::GetContainerGroup(void)
0x140063593  mov     [rdi+0F8h], rax
0x14006359a  call    ?GetRawSectorSize@CClfsAuthContainer@@QEAAKXZ; CClfsAuthContainer::GetRawSectorSize(void)
0x14006359f  mov     r8d, eax
0x1400635a2  mov     [rdi+90h], eax
0x1400635a8  lea     ecx, [rax-1]
0x1400635ab  cmp     ecx, 0FFFh
0x1400635b1  ja      loc_14006370B
0x1400635b7  test    eax, 1FFh
0x1400635bc  jnz     loc_14006370B
0x1400635c2  xor     edx, edx
0x1400635c4  mov     eax, 1000h
0x1400635c9  div     r8d
0x1400635cc  test    edx, edx
0x1400635ce  jnz     loc_14006370B
0x1400635d4  lea     rdx, [rsp+88h+var_48]; struct _CLFS_CONTROL_RECORD **
0x1400635d9  mov     rcx, rdi; this
0x1400635dc  call    ?ReadImage@CClfsBaseFilePersisted@@QEAAJAEAPEAU_CLFS_CONTROL_RECORD@@@Z; CClfsBaseFilePersisted::ReadImage(_CLFS_CONTROL_RECORD * &)
0x1400635e1  mov     ebx, eax
0x1400635e3  mov     [rsp+88h+var_58], eax
0x1400635e7  test    eax, eax
0x1400635e9  js      short loc_140063572
0x1400635eb  lea     rdx, [rdi+88h]; unsigned __int64 *
0x1400635f2  mov     rcx, [rdi+98h]; this
0x1400635f9  call    ?GetContainerSize@CClfsAuthContainer@@QEAAJAEA_K@Z; CClfsAuthContainer::GetContainerSize(unsigned __int64 &)
0x1400635fe  mov     ebx, eax
0x140063600  mov     [rsp+88h+var_58], eax
0x140063604  test    eax, eax
0x140063606  js      loc_140063714
0x14006360c  mov     rcx, rdi; this
0x14006360f  call    ?GetBaseLogRecord@CClfsBaseFile@@IEAAPEAU_CLFS_BASE_RECORD_HEADER@@XZ; CClfsBaseFile::GetBaseLogRecord(void)
0x140063614  mov     r8, rax
0x140063617  test    rax, rax
0x14006361a  jz      loc_14006357D
0x140063620  add     rax, 18h
0x140063624  mov     [rdi+40h], rax
0x140063628  mov     ecx, 0Bh
0x14006362d  mov     [rdi+48h], ecx
0x140063630  mov     [rdi+50h], rdi
0x140063634  lea     rax, [r8+70h]
0x140063638  mov     [rdi+58h], rax
0x14006363c  mov     [rdi+60h], ecx
0x14006363f  mov     [rdi+68h], rdi
0x140063643  lea     rax, [r8+0C8h]
0x14006364a  mov     [rdi+70h], rax
0x14006364e  mov     [rdi+78h], ecx
0x140063651  mov     [rdi+80h], rdi
0x140063658  mov     rsi, [rsp+88h+var_48]
0x14006365d  cmp     [rsi+14h], r13d
0x140063661  jz      loc_140063714
0x140063667  movzx   ecx, word ptr [rsi+18h]
0x14006366b  test    cx, cx
0x14006366e  jz      loc_14006357D
0x140063674  movzx   edx, word ptr [rdi+28h]
0x140063678  cmp     cx, dx
0x14006367b  jnb     loc_14006357D
0x140063681  lea     eax, [rcx-2]
0x140063684  mov     r8d, 0FFFDh
0x14006368a  test    r8w, ax
0x14006368e  jnz     loc_14006357D
0x140063694  movzx   eax, word ptr [rsi+1Ah]
0x140063698  test    ax, ax
0x14006369b  jz      loc_14006357D
0x1400636a1  cmp     ax, dx
0x1400636a4  jnb     loc_14006357D
0x1400636aa  cmp     ax, 6
0x1400636ae  jnb     loc_14006357D
0x1400636b4  cmp     ax, cx
0x1400636b7  jb      loc_14006357D
0x1400636bd  mov     rcx, rdi; this
0x1400636c0  call    ?GetSize@CClfsBaseFile@@QEAA_KXZ; CClfsBaseFile::GetSize(void)
0x1400636c5  shr     eax, 9
0x1400636c8  cmp     [rsi+20h], eax
0x1400636cb  ja      loc_14006357D
0x1400636d1  mov     r8d, [rsi+24h]
0x1400636d5  shr     r8d, 1
0x1400636d8  movzx   r9d, word ptr [rsi+18h]
0x1400636dd  lea     rcx, [r9+r9*2]
0x1400636e1  mov     rax, [rdi+30h]
0x1400636e5  mov     edx, [rax+rcx*8+8]
0x1400636e9  shr     edx, 9
0x1400636ec  add     edx, r8d
0x1400636ef  cmp     [rsi+1Ch], edx
0x1400636f2  ja      loc_14006357D
0x1400636f8  mov     edx, r9d
0x1400636fb  mov     rcx, rdi
0x1400636fe  call    ?ExtendMetadataBlock@CClfsBaseFilePersisted@@QEAAJW4_CLFS_METADATA_BLOCK_TYPE@@K@Z; CClfsBaseFilePersisted::ExtendMetadataBlock(_CLFS_METADATA_BLOCK_TYPE,ulong)
0x140063703  mov     ebx, eax
0x140063705  mov     [rsp+88h+var_58], eax
0x140063709  jmp     short loc_140063714
0x14006370b  mov     ebx, 0C0000098h
0x140063710  mov     [rsp+88h+var_58], ebx
0x140063714  mov     [rsp+88h+P], r13
0x140063719  test    ebx, ebx
0x14006371b  js      loc_1400637CA
0x140063721  cmp     [rsp+88h+arg_18], r13b
0x140063729  jz      short loc_140063781
0x14006372b  mov     dword ptr [rsp+88h+arg_20], r13d
0x140063733  lea     r9, [rsp+88h+arg_20]; unsigned int *
0x14006373b  xor     r8d, r8d; unsigned int
0x14006373e  lea     rdx, [rsp+88h+P]; void **
0x140063743  mov     rcx, [rdi+98h]; this
0x14006374a  call    ?QueryContainerSecurity@CClfsBaseFilePersisted@@SAJPEAVCClfsAuthContainer@@AEAPEAXKAEAK@Z; CClfsBaseFilePersisted::QueryContainerSecurity(CClfsAuthContainer *,void * &,ulong,ulong &)
0x14006374f  mov     ebx, r13d
0x140063752  test    eax, eax
0x140063754  cmovs   ebx, eax
0x140063757  test    ebx, ebx
0x140063759  js      short loc_140063781
0x14006375b  mov     rcx, [rsp+88h+P]; void *
0x140063760  call    ?IsNullSecurityDescriptor@CClfsContainer@@SAEPEAX@Z; CClfsContainer::IsNullSecurityDescriptor(void *)
0x140063765  test    al, al
0x140063767  jnz     short loc_14006376E
0x140063769  mov     byte ptr [r12], 1
0x14006376e  xor     edx, edx; Tag
0x140063770  mov     rcx, [rsp+88h+P]; P
0x140063775  call    cs:__imp_ExFreePoolWithTag
0x14006377c  nop     dword ptr [rax+rax+00h]
0x140063781  mov     rcx, cs:WPP_GLOBAL_Control
0x140063788  lea     rax, WPP_GLOBAL_Control
0x14006378f  cmp     rcx, rax
0x140063792  jz      short loc_1400637CA
0x140063794  test    dword ptr [rcx+2Ch], 4000000h
0x14006379b  jz      short loc_1400637CA
0x14006379d  mov     edx, 21h ; '!'
0x1400637a2  mov     rax, [r15+8]
0x1400637a6  mov     [rsp+88h+var_60], rax
0x1400637ab  mov     dword ptr [rsp+88h+var_68], 1EC5h
0x1400637b3  lea     r9, aCclfsbasefilep_4; "CClfsBaseFilePersisted::OpenImage"
0x1400637ba  lea     r8, WPP_1169606c7f2f3d218636bb1790f0fe72_Traceguids
0x1400637c1  mov     rcx, [rcx+18h]
  ... truncated ...
```
