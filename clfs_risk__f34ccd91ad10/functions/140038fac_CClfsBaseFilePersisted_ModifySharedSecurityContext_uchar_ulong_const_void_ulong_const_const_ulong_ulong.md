# CClfsBaseFilePersisted::ModifySharedSecurityContext(uchar,ulong const &,void *,ulong const * const,ulong,ulong)

- ea: `0x140038fac`
- end: `0x1400392a1`
- name: `?ModifySharedSecurityContext@CClfsBaseFilePersisted@@QEAAJEAEBKPEAXQEBKKK@Z`
- size: `757`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFilePersisted *__hidden this@<rcx>, unsigned __int8@<dl>, const unsigned int *@<r8>, void *@<r9>, const unsigned int *const, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140046f30`

## callees

- `0x14000b6b0`
- `0x140011cec`
- `0x140036a14`
- `0x1400389ac`
- `0x140038fac`
- `0x1400396fc`
- `0x14003f1b0`
- `0x140061c00`
- `0x140061d00`
- `0x140062980`
- `0x140062a30`
- `0x140062c60`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039000`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140039000`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140039168`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140039168`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140039142`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140039142`
- `ntoskrnl!SeDeassignSecurity` at `0x1400391b0`
- `ntoskrnl!SeDeassignSecurity` at `0x1400391ec`
- `ntoskrnl!SeDeassignSecurity` at `0x14003921d`
- `ntoskrnl!SeDeassignSecurity` at `0x1400391b0`
- `ntoskrnl!SeDeassignSecurity` at `0x1400391ec`
- `ntoskrnl!SeDeassignSecurity` at `0x14003921d`

## pseudocode

```c
__int64 __fastcall CClfsBaseFilePersisted::ModifySharedSecurityContext(
        CClfsBaseFilePersisted *this,
        unsigned __int8 a2,
        DWORD *a3,
        void *a4,
        const unsigned int *a5,
        unsigned int a6,
        unsigned int a7)
{
  struct _CLFS_CLIENT_CONTEXT *v11; // r14
  struct _CLFS_CONTAINER_CONTEXT *v12; // r15
  BOOLEAN v13; // si
  NTSTATUS SecurityDescriptor; // ebx
  CClfsAuthContainer *v16; // rcx
  CClfsBaseFile *v17; // rcx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v20; // [rsp+30h] [rbp-78h]
  unsigned __int8 v21[8]; // [rsp+38h] [rbp-70h] BYREF
  struct _CLFS_CLIENT_CONTEXT *v22; // [rsp+40h] [rbp-68h] BYREF
  struct _CLFS_CONTAINER_CONTEXT *v23; // [rsp+48h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+50h] [rbp-58h] BYREF
  void *v25; // [rsp+58h] [rbp-50h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-48h]
  struct _IO_STATUS_BLOCK v27; // [rsp+68h] [rbp-40h] BYREF
  unsigned int v28; // [rsp+78h] [rbp-30h] BYREF

  v25 = (void *)-1LL;
  v11 = 0;
  v22 = 0;
  v12 = 0;
  v23 = 0;
  v27.Pointer = 0;
  ObjectsSecurityDescriptor = 0;
  v21[0] = 0;
  v13 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 4), 1u);
  v20 = v13;
  if ( a2 )
  {
    CClfsBaseFile::AcquireClientContext(this, a2, &v22);
    v11 = v22;
    if ( v22 )
    {
      SecurityDescriptor = CClfsBaseFile::AcquireSharedSecurityContext(
                             this,
                             *((void *const *)v22 + 16),
                             (struct _CLFS_SHARED_SECURITY_CONTEXT **)&v27);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = CClfsBaseFile::GetSecurityDescriptor(
                               v17,
                               (const struct _CLFS_SHARED_SECURITY_CONTEXT *)v27.Pointer,
                               &ObjectsSecurityDescriptor,
                               &v28);
        if ( SecurityDescriptor >= 0 )
        {
          GenericMapping = IoGetFileObjectGenericMapping();
          SecurityDescriptor = SeSetSecurityDescriptorInfo(
                                 0,
                                 a3,
                                 a4,
                                 &ObjectsSecurityDescriptor,
                                 PagedPool,
                                 GenericMapping);
          if ( SecurityDescriptor >= 0 )
          {
            SecurityDescriptor = CClfsBaseFile::FindSharedSecurityDescriptor(
                                   this,
                                   ObjectsSecurityDescriptor,
                                   1u,
                                   v21,
                                   &v25);
            if ( SecurityDescriptor >= 0 )
            {
              SecurityDescriptor = CClfsBaseFile::ReleaseSharedSecurityDescriptor(this, *((void *const *)v11 + 16));
              if ( SecurityDescriptor >= 0 )
              {
                *((_QWORD *)v11 + 16) = v25;
                v25 = (void *)-1LL;
                SeDeassignSecurity(&ObjectsSecurityDescriptor);
                CClfsBaseFile::ReleaseClientContext(this, &v22);
                SecurityDescriptor = CClfsBaseFilePersisted::FlushImage(this);
                v11 = v22;
              }
              else
              {
                CClfsBaseFile::ReleaseSharedSecurityDescriptor(this, v25);
                SeDeassignSecurity(&ObjectsSecurityDescriptor);
                v25 = (void *)-1LL;
              }
            }
            else
            {
              SeDeassignSecurity(&ObjectsSecurityDescriptor);
            }
          }
        }
      }
    }
    else
    {
      SecurityDescriptor = -1073741811;
    }
  }
  else
  {
    while ( 1 )
    {
      v26 = a6;
      if ( a6 >= a7 )
        break;
      SecurityDescriptor = CClfsBaseFile::AcquireContainerContext(this, a5[a6 & 0x3FF], &v23);
      v12 = v23;
      if ( !v23 )
        goto LABEL_19;
      v16 = (CClfsAuthContainer *)*((_QWORD *)v23 + 3);
      if ( !v16 )
      {
        SecurityDescriptor = -1072037874;
        goto LABEL_19;
      }
      SecurityDescriptor = CClfsAuthContainer::SetSecurityInformation(v16, &v27, a3, a4);
      if ( SecurityDescriptor < 0 )
        goto LABEL_19;
      CClfsBaseFile::ReleaseContainerContext(this, &v23);
      ++a6;
      v12 = v23;
    }
    SecurityDescriptor = CClfsAuthContainer::SetSecurityInformation(*((CClfsAuthContainer **)this + 19), &v27, a3, a4);
LABEL_19:
    v13 = v20;
  }
  if ( v11 )
    CClfsBaseFile::ReleaseClientContext(this, &v22);
  if ( v12 )
    CClfsBaseFile::ReleaseContainerContext(this, &v23);
  if ( v13 )
    CClfsBaseFile::UnlockImage(this);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140038fac  mov     r11, rsp
0x140038faf  mov     [r11+10h], rbx
0x140038fb3  mov     [r11+18h], rsi
0x140038fb7  mov     [r11+8], rcx
0x140038fbb  push    rdi
0x140038fbc  push    r12
0x140038fbe  push    r13
0x140038fc0  push    r14
0x140038fc2  push    r15
0x140038fc4  sub     rsp, 80h
0x140038fcb  mov     r12, r9
0x140038fce  mov     r13, r8
0x140038fd1  mov     bl, dl
0x140038fd3  mov     rdi, rcx
0x140038fd6  mov     qword ptr [r11-50h], 0FFFFFFFFFFFFFFFFh
0x140038fde  xor     eax, eax
0x140038fe0  mov     r14d, eax
0x140038fe3  mov     [r11-68h], rax
0x140038fe7  mov     r15d, eax
0x140038fea  mov     [r11-60h], rax
0x140038fee  mov     [r11-40h], rax
0x140038ff2  mov     [r11-58h], rax
0x140038ff6  mov     [rsp+0A8h+var_70], al
0x140038ffa  mov     dl, 1; Wait
0x140038ffc  mov     rcx, [rcx+20h]; Resource
0x140039000  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140039007  nop     dword ptr [rax+rax+00h]
0x14003900c  mov     sil, al
0x14003900f  mov     [rsp+0A8h+var_78], al
0x140039013  test    bl, bl
0x140039015  jnz     loc_1400390D7
0x14003901b  mov     esi, [rsp+0A8h+arg_28]
0x140039022  mov     [rsp+0A8h+var_48], esi
0x140039026  cmp     esi, [rsp+0A8h+arg_30]
0x14003902d  jnb     loc_1400390B5
0x140039033  mov     edx, esi
0x140039035  and     edx, 3FFh
0x14003903b  lea     r8, [rsp+0A8h+var_60]; struct _CLFS_CONTAINER_CONTEXT **
0x140039040  mov     rax, [rsp+0A8h+arg_20]
0x140039048  mov     edx, [rax+rdx*4]; unsigned int
0x14003904b  mov     rcx, rdi; this
0x14003904e  call    ?AcquireContainerContext@CClfsBaseFile@@QEAAJKPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::AcquireContainerContext(ulong,_CLFS_CONTAINER_CONTEXT * *)
0x140039053  mov     ebx, eax
0x140039055  mov     [rsp+0A8h+var_74], eax
0x140039059  mov     r15, [rsp+0A8h+var_60]
0x14003905e  test    r15, r15
0x140039061  jz      loc_14003924B
0x140039067  mov     rcx, [r15+18h]; this
0x14003906b  test    rcx, rcx
0x14003906e  jnz     short loc_14003907E
0x140039070  mov     ebx, 0C01A000Eh
0x140039075  mov     [rsp+0A8h+var_74], ebx
0x140039079  jmp     loc_14003924B
0x14003907e  mov     r9, r12; void *
0x140039081  mov     r8, r13; unsigned int *
0x140039084  lea     rdx, [rsp+0A8h+var_40]; struct _IO_STATUS_BLOCK *
0x140039089  call    ?SetSecurityInformation@CClfsAuthContainer@@QEAAJPEAU_IO_STATUS_BLOCK@@AEBKPEAX@Z; CClfsAuthContainer::SetSecurityInformation(_IO_STATUS_BLOCK *,ulong const &,void *)
0x14003908e  mov     ebx, eax
0x140039090  mov     [rsp+0A8h+var_74], eax
0x140039094  test    eax, eax
0x140039096  js      loc_14003924B
0x14003909c  lea     rdx, [rsp+0A8h+var_60]; struct _CLFS_CONTAINER_CONTEXT **
0x1400390a1  mov     rcx, rdi; this
0x1400390a4  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x1400390a9  inc     esi
0x1400390ab  mov     r15, [rsp+0A8h+var_60]
0x1400390b0  jmp     loc_140039022
0x1400390b5  mov     r9, r12; void *
0x1400390b8  mov     r8, r13; unsigned int *
0x1400390bb  lea     rdx, [rsp+0A8h+var_40]; struct _IO_STATUS_BLOCK *
0x1400390c0  mov     rcx, [rdi+98h]; this
0x1400390c7  call    ?SetSecurityInformation@CClfsAuthContainer@@QEAAJPEAU_IO_STATUS_BLOCK@@AEBKPEAX@Z; CClfsAuthContainer::SetSecurityInformation(_IO_STATUS_BLOCK *,ulong const &,void *)
0x1400390cc  mov     ebx, eax
0x1400390ce  mov     [rsp+0A8h+var_74], eax
0x1400390d2  jmp     loc_14003924B
0x1400390d7  lea     r8, [rsp+0A8h+var_68]; struct _CLFS_CLIENT_CONTEXT **
0x1400390dc  mov     dl, bl; unsigned __int8
0x1400390de  mov     rcx, rdi; this
0x1400390e1  call    ?AcquireClientContext@CClfsBaseFile@@QEAAJEPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::AcquireClientContext(uchar,_CLFS_CLIENT_CONTEXT * *)
0x1400390e6  mov     r14, [rsp+0A8h+var_68]
0x1400390eb  test    r14, r14
0x1400390ee  jnz     short loc_1400390FE
0x1400390f0  mov     ebx, 0C000000Dh
0x1400390f5  mov     [rsp+0A8h+var_74], ebx
0x1400390f9  jmp     loc_140039250
0x1400390fe  lea     r8, [rsp+0A8h+var_40]; struct _CLFS_SHARED_SECURITY_CONTEXT **
0x140039103  mov     rdx, [r14+80h]; void *
0x14003910a  mov     rcx, rdi; this
0x14003910d  call    ?AcquireSharedSecurityContext@CClfsBaseFile@@QEAAJQEAXAEAPEAU_CLFS_SHARED_SECURITY_CONTEXT@@@Z; CClfsBaseFile::AcquireSharedSecurityContext(void * const,_CLFS_SHARED_SECURITY_CONTEXT * &)
0x140039112  mov     ebx, eax
0x140039114  mov     [rsp+0A8h+var_74], eax
0x140039118  test    eax, eax
0x14003911a  js      loc_140039250
0x140039120  lea     r9, [rsp+0A8h+var_30]; unsigned int *
0x140039125  lea     r8, [rsp+0A8h+ObjectsSecurityDescriptor]; void **
0x14003912a  mov     rdx, qword ptr [rsp+0A8h+var_40]; struct _CLFS_SHARED_SECURITY_CONTEXT *
0x14003912f  call    ?GetSecurityDescriptor@CClfsBaseFile@@IEAAJAEBU_CLFS_SHARED_SECURITY_CONTEXT@@AEAPEAXAEAK@Z; CClfsBaseFile::GetSecurityDescriptor(_CLFS_SHARED_SECURITY_CONTEXT const &,void * &,ulong &)
0x140039134  mov     ebx, eax
0x140039136  mov     [rsp+0A8h+var_74], eax
0x14003913a  test    eax, eax
0x14003913c  js      loc_140039250
0x140039142  call    cs:__imp_IoGetFileObjectGenericMapping
0x140039149  nop     dword ptr [rax+rax+00h]
0x14003914e  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x140039153  mov     [rsp+0A8h+PoolType], 1; PoolType
0x14003915b  lea     r9, [rsp+0A8h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x140039160  mov     r8, r12; ModificationDescriptor
0x140039163  mov     rdx, r13; SecurityInformation
0x140039166  xor     ecx, ecx; Object
0x140039168  call    cs:__imp_SeSetSecurityDescriptorInfo
0x14003916f  nop     dword ptr [rax+rax+00h]
0x140039174  mov     ebx, eax
0x140039176  mov     [rsp+0A8h+var_74], eax
0x14003917a  test    eax, eax
0x14003917c  js      loc_140039250
0x140039182  lea     rax, [rsp+0A8h+var_50]
0x140039187  mov     qword ptr [rsp+0A8h+PoolType], rax; void **
0x14003918c  lea     r9, [rsp+0A8h+var_70]; unsigned __int8 *
0x140039191  mov     r8b, 1; unsigned __int8
0x140039194  mov     rdx, [rsp+0A8h+ObjectsSecurityDescriptor]; Src
0x140039199  mov     rcx, rdi; this
0x14003919c  call    ?FindSharedSecurityDescriptor@CClfsBaseFile@@QEAAJQEAXEAEAEAEAPEAX@Z; CClfsBaseFile::FindSharedSecurityDescriptor(void * const,uchar,uchar &,void * &)
0x1400391a1  mov     ebx, eax
0x1400391a3  mov     [rsp+0A8h+var_74], eax
0x1400391a7  test    eax, eax
0x1400391a9  jns     short loc_1400391C1
0x1400391ab  lea     rcx, [rsp+0A8h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1400391b0  call    cs:__imp_SeDeassignSecurity
0x1400391b7  nop     dword ptr [rax+rax+00h]
0x1400391bc  jmp     loc_140039250
0x1400391c1  mov     rdx, [r14+80h]; void *
0x1400391c8  mov     rcx, rdi; this
0x1400391cb  call    ?ReleaseSharedSecurityDescriptor@CClfsBaseFile@@QEAAJQEAX@Z; CClfsBaseFile::ReleaseSharedSecurityDescriptor(void * const)
0x1400391d0  mov     ebx, eax
0x1400391d2  mov     [rsp+0A8h+var_74], eax
0x1400391d6  test    eax, eax
0x1400391d8  jns     short loc_140039203
0x1400391da  mov     rdx, [rsp+0A8h+var_50]; void *
0x1400391df  mov     rcx, rdi; this
0x1400391e2  call    ?ReleaseSharedSecurityDescriptor@CClfsBaseFile@@QEAAJQEAX@Z; CClfsBaseFile::ReleaseSharedSecurityDescriptor(void * const)
0x1400391e7  lea     rcx, [rsp+0A8h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1400391ec  call    cs:__imp_SeDeassignSecurity
0x1400391f3  nop     dword ptr [rax+rax+00h]
0x1400391f8  mov     [rsp+0A8h+var_50], 0FFFFFFFFFFFFFFFFh
0x140039201  jmp     short loc_140039250
0x140039203  mov     rax, [rsp+0A8h+var_50]
0x140039208  mov     [r14+80h], rax
0x14003920f  mov     [rsp+0A8h+var_50], 0FFFFFFFFFFFFFFFFh
0x140039218  lea     rcx, [rsp+0A8h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x14003921d  call    cs:__imp_SeDeassignSecurity
0x140039224  nop     dword ptr [rax+rax+00h]
0x140039229  lea     rdx, [rsp+0A8h+var_68]; struct _CLFS_CLIENT_CONTEXT **
0x14003922e  mov     rcx, rdi; this
0x140039231  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x140039236  mov     rcx, rdi; this
0x140039239  call    ?FlushImage@CClfsBaseFilePersisted@@QEAAJXZ; CClfsBaseFilePersisted::FlushImage(void)
0x14003923e  mov     ebx, eax
0x140039240  mov     [rsp+0A8h+var_74], eax
0x140039244  mov     r14, [rsp+0A8h+var_68]
0x140039249  jmp     short loc_140039250
0x14003924b  mov     sil, [rsp+0A8h+var_78]
0x140039250  test    r14, r14
0x140039253  jz      short loc_140039262
0x140039255  lea     rdx, [rsp+0A8h+var_68]; struct _CLFS_CLIENT_CONTEXT **
0x14003925a  mov     rcx, rdi; this
0x14003925d  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x140039262  test    r15, r15
0x140039265  jz      short loc_140039274
0x140039267  lea     rdx, [rsp+0A8h+var_60]; struct _CLFS_CONTAINER_CONTEXT **
0x14003926c  mov     rcx, rdi; this
0x14003926f  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x140039274  test    sil, sil
0x140039277  jz      short loc_140039281
0x140039279  mov     rcx, rdi; this
0x14003927c  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x140039281  mov     eax, ebx
0x140039283  lea     r11, [rsp+0A8h+var_28]
0x14003928b  mov     rbx, [r11+38h]
0x14003928f  mov     rsi, [r11+40h]
0x140039293  mov     rsp, r11
0x140039296  pop     r15
0x140039298  pop     r14
0x14003929a  pop     r13
0x14003929c  pop     r12
0x14003929e  pop     rdi
0x14003929f  retn
0x14007d621  push    rbp
0x14007d623  sub     rsp, 30h
0x14007d627  mov     rbp, rdx
0x14007d62a  cmp     qword ptr [rbp+40h], 0
0x14007d62f  jz      short loc_14007D642
0x14007d631  lea     rdx, [rbp+40h]; struct _CLFS_CLIENT_CONTEXT **
0x14007d635  mov     rcx, [rbp+0B0h]; this
0x14007d63c  call    ?ReleaseClientContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CLIENT_CONTEXT@@@Z; CClfsBaseFile::ReleaseClientContext(_CLFS_CLIENT_CONTEXT * *)
0x14007d641  nop
0x14007d642  cmp     qword ptr [rbp+48h], 0
0x14007d647  jz      short loc_14007D65A
0x14007d649  lea     rdx, [rbp+48h]; struct _CLFS_CONTAINER_CONTEXT **
0x14007d64d  mov     rcx, [rbp+0B0h]; this
0x14007d654  call    ?ReleaseContainerContext@CClfsBaseFile@@QEAAJPEAPEAU_CLFS_CONTAINER_CONTEXT@@@Z; CClfsBaseFile::ReleaseContainerContext(_CLFS_CONTAINER_CONTEXT * *)
0x14007d659  nop
0x14007d65a  cmp     byte ptr [rbp+30h], 0
0x14007d65e  jz      short loc_14007D66D
0x14007d660  mov     rcx, [rbp+0B0h]; this
0x14007d667  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14007d66c  nop
0x14007d66d  add     rsp, 30h
0x14007d671  pop     rbp
0x14007d672  retn
```
