# CClfsAuthContainer::Open(_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,uchar,unsigned __int64,uchar &)

- ea: `0x140078d5c`
- end: `0x1400794f0`
- name: `?Open@CClfsAuthContainer@@QEAAJAEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@E_KAEAE@Z`
- size: `1940`
- prototype: `__int64 __fastcall(CClfsAuthContainer *__hidden this, struct _UNICODE_STRING *, const struct _CLFS_FILTER_CONTEXT *, unsigned __int8, unsigned __int64, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005ed70`
- `0x1400632d4`

## callees

- `0x14000f7bc`
- `0x140010e08`
- `0x1400130d0`
- `0x140017f20`
- `0x140033a78`
- `0x140034b1c`
- `0x140039b74`
- `0x14003b718`
- `0x14003be24`
- `0x14003be98`
- `0x14003cc4c`
- `0x14003d418`
- `0x14003eb2c`
- `0x14003ecf8`
- `0x14003f568`
- `0x14004df28`
- `0x14004f54c`
- `0x14004f788`
- `0x14004f8a0`
- `0x14004fe24`
- `0x14005fbe8`
- `0x14006a3a0`
- `0x14006bc84`
- `0x140070a38`
- `0x140070cd4`
- `0x140073128`
- `0x14007536c`
- `0x140076b4c`
- `0x1400780d0`
- `0x140078618`
- `0x140078d5c`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140078f65`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140078f65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400793e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e271`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400793e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e271`
- `HAL!KeQueryPerformanceCounter` at `0x140078de1`
- `HAL!KeQueryPerformanceCounter` at `0x14007939b`
- `HAL!KeQueryPerformanceCounter` at `0x14007e221`
- `HAL!KeQueryPerformanceCounter` at `0x140078de1`
- `HAL!KeQueryPerformanceCounter` at `0x14007939b`
- `HAL!KeQueryPerformanceCounter` at `0x14007e221`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::Open(
        CClfsAuthContainer *this,
        struct _UNICODE_STRING *a2,
        const struct _CLFS_FILTER_CONTEXT *a3,
        char a4,
        unsigned __int64 a5,
        bool *a6)
{
  LARGE_INTEGER PerformanceCounter; // rbx
  __int64 v11; // rcx
  int ContainerSize; // r12d
  _DWORD *v13; // rdi
  __int64 v14; // rax
  CClfsContainer *v15; // rcx
  struct _UNICODE_STRING *v16; // r8
  char v17; // r14
  __int64 v18; // rcx
  CClfsContainer *v19; // rax
  CClfsContainer *v20; // rcx
  int v21; // eax
  unsigned int *v22; // r8
  unsigned __int8 v23; // di
  char v24; // r12
  bool *v25; // r15
  int v26; // eax
  int v27; // edi
  int v28; // edi
  char v29; // di
  int v30; // eax
  char v31; // cl
  struct _CLFS_CPF_HEADER *v32; // rdi
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rax
  int v39; // r14d
  int v40; // r15d
  int ContainerGroup; // edi
  __int64 v42; // rsi
  ULONG LowPart; // eax
  PVOID v44; // rcx
  CClfsContainer *v45; // rcx
  CClfsMerkleTree *v46; // rcx
  char v48; // [rsp+40h] [rbp-98h]
  char v49; // [rsp+41h] [rbp-97h]
  unsigned __int8 v50; // [rsp+48h] [rbp-90h] BYREF
  char v51; // [rsp+49h] [rbp-8Fh] BYREF
  unsigned __int8 v52; // [rsp+4Ah] [rbp-8Eh] BYREF
  char v53; // [rsp+4Bh] [rbp-8Dh]
  char v54; // [rsp+4Ch] [rbp-8Ch]
  unsigned __int8 v55; // [rsp+4Dh] [rbp-8Bh] BYREF
  unsigned __int8 v56; // [rsp+4Eh] [rbp-8Ah] BYREF
  unsigned __int8 v57; // [rsp+4Fh] [rbp-89h] BYREF
  int v58; // [rsp+50h] [rbp-88h] BYREF
  int v59; // [rsp+54h] [rbp-84h]
  struct _CLFS_CPF_HEADER *v60; // [rsp+58h] [rbp-80h] BYREF
  PVOID P; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int64 v62; // [rsp+68h] [rbp-70h] BYREF
  struct _UNICODE_STRING v63; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int64 v64; // [rsp+80h] [rbp-58h] BYREF
  unsigned int v65; // [rsp+88h] [rbp-50h] BYREF
  LARGE_INTEGER v66; // [rsp+90h] [rbp-48h]

  v62 = 0;
  v50 = 0;
  v54 = 0;
  v48 = 0;
  v49 = 0;
  v64 = 4096;
  P = 0;
  v60 = 0;
  v55 = 0;
  v51 = 0;
  v56 = 0;
  v57 = 0;
  v58 = -1073741823;
  v52 = 0;
  LOBYTE(v59) = 0;
  v53 = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v66 = PerformanceCounter;
  v63 = 0;
  ContainerSize = CClfsContainer::Open(*((CClfsContainer **)this + 15), a2, a3, a4, a6);
  if ( ContainerSize >= 0 )
  {
    v54 = 1;
    v13 = (_DWORD *)((char *)this + 136);
    if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v11) )
    {
      if ( (unsigned int)(*v13 - 2) > 1 )
      {
        v14 = *((_QWORD *)this + 15);
        if ( v14 )
        {
          if ( *(_QWORD *)(v14 + 48) && ClfsRegistryIsFileAuthExempt(*(PVOID *)(*((_QWORD *)this + 15) + 48LL)) )
          {
            *v13 = 2;
            *((_DWORD *)this + 43) |= 0x100u;
          }
        }
      }
    }
    *((_DWORD *)this + 12) = CClfsContainer::GetRawSectorSize(*((CClfsContainer **)this + 15));
    *((_DWORD *)this + 13) = CClfsContainer::GetAlignmentRequirement(*((CClfsContainer **)this + 15));
    ContainerSize = CClfsContainer::GetContainerSize(*((CClfsContainer **)this + 15), &v62);
    if ( ContainerSize >= 0 )
    {
      if ( *a6 )
      {
        ContainerSize = CClfsContainer::CheckSecureAccess(v15, 1u, &v55, &v58);
        if ( ContainerSize < 0 )
          goto LABEL_65;
        if ( !v55 && *v13 <= 1u )
        {
LABEL_13:
          ContainerSize = -1073741790;
          goto LABEL_65;
        }
        ContainerSize = CClfsContainer::CheckSecureAccess(
                          *((CClfsContainer **)this + 15),
                          3u,
                          (unsigned __int8 *)&v51,
                          &v58);
        if ( ContainerSize < 0 )
          goto LABEL_65;
        v17 = v51;
      }
      else
      {
        v17 = 1;
        v51 = 1;
      }
      if ( *v13 > 1u )
        goto LABEL_55;
      ContainerSize = CClfsAuthContainer::CreatePatchFilePath(a2, &v63);
      if ( ContainerSize < 0 )
        goto LABEL_65;
      if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v18) )
      {
        v19 = (CClfsContainer *)ExAllocateFromPagedLookasideList(&CClfsContainer::m_laList);
        if ( v19 )
          v20 = CClfsContainer::CClfsContainer(v19, *((_DWORD *)this + 11), 1u);
        else
          v20 = 0;
        *((_QWORD *)this + 16) = v20;
        if ( !v20 )
        {
          ContainerSize = -1073741670;
          goto LABEL_65;
        }
        (**(void (__fastcall ***)(CClfsContainer *))v20)(v20);
      }
      v21 = CClfsContainer::Open(*((CClfsContainer **)this + 16), &v63, a3, a4, (bool *)&v50);
      ContainerSize = v21;
      if ( v21 >= 0 )
      {
        v48 = 1;
        v23 = v50;
        if ( v50 )
        {
          ContainerSize = CClfsContainer::CheckSecureAccess(*((CClfsContainer **)this + 16), 1u, &v56, &v58);
          if ( ContainerSize < 0 )
            goto LABEL_65;
          if ( !v56 )
            goto LABEL_13;
        }
        v24 = 0;
        v25 = a6;
        goto LABEL_31;
      }
      if ( v21 == -1073741772 )
      {
        v25 = a6;
        v26 = *a6
            ? CClfsContainer::DuplicateSecurityDescriptor(*((CClfsContainer **)this + 15), &P, v22, 1)
            : CClfsContainer::DuplicateNullSecurityDescriptor(&P, &v65);
        ContainerSize = v26;
        if ( v26 >= 0 )
        {
          ContainerSize = CClfsContainer::Create(*((_QWORD *)this + 16), &v63, &v64, a3, P, 1u, a4, &v50);
          if ( ContainerSize == -1073741609 )
            ContainerSize = CClfsContainer::Create(*((_QWORD *)this + 16), &v63, &v64, a3, 0, 1u, a4, &v50);
          if ( ContainerSize >= 0 )
          {
            v24 = 1;
            v49 = 1;
            v23 = v50;
LABEL_31:
            if ( v23 != *v25
              || (v27 = *((_DWORD *)this + 12), v27 != CClfsContainer::GetRawSectorSize(*((CClfsContainer **)this + 16)))
              || (v28 = *((_DWORD *)this + 13),
                  v28 != CClfsContainer::GetAlignmentRequirement(*((CClfsContainer **)this + 16))) )
            {
              ContainerSize = -1073741816;
              goto LABEL_65;
            }
            if ( v24 )
            {
              ContainerSize = CClfsAuthContainer::InitializePatchFile(this);
              if ( ContainerSize < 0 )
                goto LABEL_65;
              v29 = v48;
            }
            else
            {
              v29 = v48;
              if ( !v48 )
                goto LABEL_55;
              ContainerSize = CClfsAuthContainer::VerifyIsPatchFile(this, &v57);
              if ( ContainerSize < 0 )
                goto LABEL_65;
              if ( !v57 )
                goto LABEL_54;
            }
            if ( v29 )
            {
              v30 = CClfsAuthContainer::VerifyPatchContents(this, &v60);
              v31 = v59;
              if ( v30 >= 0 )
                v31 = 1;
              goto LABEL_56;
            }
LABEL_55:
            v31 = v59;
LABEL_56:
            if ( !v31 )
              goto LABEL_64;
            v32 = v60;
            v33 = CClfsAuthContainer::RecoverContainer(this, v60, v16, a3, v62, a5, &v52);
            ContainerSize = v33;
            if ( v33 >= 0 )
            {
              *((_DWORD *)this + 43) |= 1u;
              goto LABEL_65;
            }
            if ( v33 != -1072037875 && v17 )
            {
              v53 = 1;
              v52 = 1;
              if ( CClfsAuthContainer::ApplyPatchFile(this, *((struct CClfsContainer **)this + 15), v32) < 0 )
                goto LABEL_54;
LABEL_64:
              ContainerSize = CClfsAuthContainer::ParseContainerMetadata(
                                this,
                                *((struct CClfsContainer **)this + 15),
                                v62,
                                a5,
                                v17);
              goto LABEL_65;
            }
            if ( !v52 )
              goto LABEL_64;
LABEL_54:
            ContainerSize = -1072037875;
          }
        }
      }
    }
  }
LABEL_65:
  if ( ContainerSize == -1072037875 )
  {
    v34 = *((_QWORD *)this + 15);
    if ( v34 )
    {
      if ( *(_QWORD *)(v34 + 48) )
        ClfsTelemetryFileCorruption(
          *(_QWORD *)(*((_QWORD *)this + 15) + 48LL) + 88LL,
          *((unsigned int *)this + 43),
          *((unsigned int *)this + 34));
    }
  }
  if ( (unsigned int)Feature_CLFS_EventLog__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( ContainerSize == -1072037875 )
    {
      v35 = *((_QWORD *)this + 15);
      if ( v35 )
      {
        if ( *(_QWORD *)(v35 + 48) )
        {
          v36 = ClfsConvertStateToFailureReason(
                  *((unsigned int *)this + 43),
                  *((unsigned int *)this + 43),
                  *(_QWORD *)(*((_QWORD *)this + 15) + 48LL) + 88LL);
          ClfsEtwWriteLogCorruptionEvent(v36);
        }
      }
    }
  }
  if ( v53 )
  {
    v37 = *((_QWORD *)this + 15);
    if ( v37 )
    {
      if ( *(_QWORD *)(v37 + 48) )
        ClfsTelemetryLogFileRecoverySummary(
          *(_QWORD *)(*((_QWORD *)this + 15) + 48LL) + 88LL,
          1,
          (unsigned int)ContainerSize);
    }
  }
  if ( ContainerSize >= 0 )
  {
    v38 = *((_QWORD *)this + 15);
    if ( v38 )
    {
      if ( *(_QWORD *)(v38 + 48) )
      {
        v39 = *((_DWORD *)this + 43);
        v40 = *((_DWORD *)this + 34);
        ContainerGroup = CClfsAuthContainer::GetContainerGroup(this);
        v42 = *((_QWORD *)this + 1);
        LowPart = KeQueryPerformanceCounter(0).LowPart;
        ClfsTelemetryCreatePerf(
          *(_QWORD *)(*((_QWORD *)this + 15) + 48LL) + 88,
          LowPart - PerformanceCounter.LowPart,
          v42,
          ContainerGroup,
          v40,
          v39,
          0);
      }
    }
  }
  CClfsAuthContainer::ReleasePatchFilePath(&v63);
  v44 = P;
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( ContainerSize < 0 )
  {
    *((_DWORD *)this + 43) = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 6) = 0;
    if ( v54 )
      CClfsContainer::Close(*((CClfsContainer **)this + 15));
    if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v44) )
    {
      v45 = (CClfsContainer *)*((_QWORD *)this + 16);
      if ( v45 )
      {
        if ( v48 )
        {
          CClfsContainer::Close(v45);
        }
        else if ( v49 )
        {
          (*(void (__fastcall **)(CClfsContainer *))(*(_QWORD *)v45 + 24LL))(v45);
        }
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 8LL))(*((_QWORD *)this + 16));
        *((_QWORD *)this + 16) = 0;
      }
    }
    else if ( v48 )
    {
      CClfsContainer::Close(*((CClfsContainer **)this + 16));
    }
    else if ( v49 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 24LL))(*((_QWORD *)this + 16));
    }
    if ( v60 )
      CClfsAuthContainer::ReleasePatchHeader(&v60);
    v46 = (CClfsMerkleTree *)*((_QWORD *)this + 19);
    if ( v46 )
      CClfsMerkleTree::ResetTree(v46);
  }
  return (unsigned int)ContainerSize;
}

```

## disassembly

```asm
0x140078d5c  mov     r11, rsp
0x140078d5f  mov     [r11+20h], r9b
0x140078d63  mov     [r11+18h], r8
0x140078d67  mov     [r11+8], rcx
0x140078d6b  push    rbx
0x140078d6c  push    rsi
0x140078d6d  push    rdi
0x140078d6e  push    r12
0x140078d70  push    r13
0x140078d72  push    r14
0x140078d74  push    r15
0x140078d76  sub     rsp, 0A0h
0x140078d7d  mov     dil, r9b
0x140078d80  mov     rsi, r8
0x140078d83  mov     r15, rdx
0x140078d86  mov     r13, rcx
0x140078d89  xor     eax, eax
0x140078d8b  mov     [rsp+0D8h+var_94], eax
0x140078d8f  mov     [r11-70h], rax
0x140078d93  xorps   xmm0, xmm0
0x140078d96  movups  xmmword ptr [rsp+0D8h+var_68.Length], xmm0
0x140078d9b  mov     [rsp+0D8h+var_90], al
0x140078d9f  mov     [rsp+0D8h+var_8C], al
0x140078da3  mov     [rsp+0D8h+var_98], al
0x140078da7  mov     [rsp+0D8h+var_97], al
0x140078dab  mov     qword ptr [r11-58h], 1000h
0x140078db3  mov     [r11-78h], rax
0x140078db7  mov     [r11-80h], rax
0x140078dbb  mov     [rsp+0D8h+var_8B], al
0x140078dbf  mov     [rsp+0D8h+var_8F], al
0x140078dc3  mov     [rsp+0D8h+var_8A], al
0x140078dc7  mov     [rsp+0D8h+var_89], al
0x140078dcb  mov     [rsp+0D8h+var_88], 0C0000001h
0x140078dd3  mov     [rsp+0D8h+var_8E], al
0x140078dd7  mov     byte ptr [rsp+0D8h+var_84], al
0x140078ddb  mov     [rsp+0D8h+var_8D], al
0x140078ddf  xor     ecx, ecx; PerformanceFrequency
0x140078de1  call    cs:__imp_KeQueryPerformanceCounter
0x140078de8  nop     dword ptr [rax+rax+00h]
0x140078ded  mov     rbx, rax
0x140078df0  mov     [rsp+0D8h+var_48], rax
0x140078df8  xorps   xmm0, xmm0
0x140078dfb  movups  xmmword ptr [rsp+0D8h+var_68.Length], xmm0
0x140078e00  mov     r14, [rsp+0D8h+arg_28]
0x140078e08  mov     [rsp+0D8h+var_B8], r14; unsigned __int8 *
0x140078e0d  mov     r9b, dil; unsigned __int8
0x140078e10  mov     r8, rsi; struct _CLFS_FILTER_CONTEXT *
0x140078e13  mov     rdx, r15; struct _UNICODE_STRING *
0x140078e16  mov     rcx, [r13+78h]; this
0x140078e1a  call    ?Open@CClfsContainer@@QEAAJAEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@EAEAE@Z; CClfsContainer::Open(_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,uchar,uchar &)
0x140078e1f  mov     r12d, eax
0x140078e22  mov     [rsp+0D8h+var_94], eax
0x140078e26  mov     esi, 1
0x140078e2b  test    eax, eax
0x140078e2d  js      loc_1400792B7
0x140078e33  mov     [rsp+0D8h+var_8C], sil
0x140078e38  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x140078e3d  lea     rdi, [r13+88h]
0x140078e44  test    eax, eax
0x140078e46  jz      short loc_140078E83
0x140078e48  mov     eax, [rdi]
0x140078e4a  sub     eax, 2
0x140078e4d  cmp     eax, esi
0x140078e4f  jbe     short loc_140078E83
0x140078e51  mov     rax, [r13+78h]
0x140078e55  test    rax, rax
0x140078e58  jz      short loc_140078E83
0x140078e5a  mov     rax, [rax+30h]
0x140078e5e  test    rax, rax
0x140078e61  jz      short loc_140078E83
0x140078e63  mov     rcx, [r13+78h]
0x140078e67  mov     rcx, [rcx+30h]; Object
0x140078e6b  call    ?ClfsRegistryIsFileAuthExempt@@YAEPEAX@Z; ClfsRegistryIsFileAuthExempt(void *)
0x140078e70  test    al, al
0x140078e72  jz      short loc_140078E83
0x140078e74  mov     dword ptr [rdi], 2
0x140078e7a  bts     dword ptr [r13+0ACh], 8
0x140078e83  mov     rcx, [r13+78h]; this
0x140078e87  call    ?GetRawSectorSize@CClfsContainer@@QEAAKXZ; CClfsContainer::GetRawSectorSize(void)
0x140078e8c  mov     [r13+30h], eax
0x140078e90  mov     rcx, [r13+78h]; this
0x140078e94  call    ?GetAlignmentRequirement@CClfsContainer@@QEAAKXZ; CClfsContainer::GetAlignmentRequirement(void)
0x140078e99  mov     [r13+34h], eax
0x140078e9d  mov     rcx, [r13+78h]; this
0x140078ea1  lea     rdx, [rsp+0D8h+var_70]; unsigned __int64 *
0x140078ea6  call    ?GetContainerSize@CClfsContainer@@QEAAJAEA_K@Z; CClfsContainer::GetContainerSize(unsigned __int64 &)
0x140078eab  mov     r12d, eax
0x140078eae  mov     [rsp+0D8h+var_94], eax
0x140078eb2  test    eax, eax
0x140078eb4  js      loc_1400792B7
0x140078eba  cmp     byte ptr [r14], 0
0x140078ebe  jz      short loc_140078F29
0x140078ec0  lea     r9, [rsp+0D8h+var_88]; int *
0x140078ec5  lea     r8, [rsp+0D8h+var_8B]; unsigned __int8 *
0x140078eca  mov     edx, esi; unsigned int
0x140078ecc  call    ?CheckSecureAccess@CClfsContainer@@QEAAJKAEAEAEAJ@Z; CClfsContainer::CheckSecureAccess(ulong,uchar &,long &)
0x140078ed1  mov     r12d, eax
0x140078ed4  mov     [rsp+0D8h+var_94], eax
0x140078ed8  test    eax, eax
0x140078eda  js      loc_1400792B7
0x140078ee0  cmp     [rsp+0D8h+var_8B], 0
0x140078ee5  jnz     short loc_140078EFB
0x140078ee7  cmp     [rdi], esi
0x140078ee9  ja      short loc_140078EFB
0x140078eeb  mov     r12d, 0C0000022h
0x140078ef1  mov     [rsp+0D8h+var_94], r12d
0x140078ef6  jmp     loc_1400792B7
0x140078efb  lea     r9, [rsp+0D8h+var_88]; int *
0x140078f00  lea     r8, [rsp+0D8h+var_8F]; unsigned __int8 *
0x140078f05  mov     edx, 3; unsigned int
0x140078f0a  mov     rcx, [r13+78h]; this
0x140078f0e  call    ?CheckSecureAccess@CClfsContainer@@QEAAJKAEAEAEAJ@Z; CClfsContainer::CheckSecureAccess(ulong,uchar &,long &)
0x140078f13  mov     r12d, eax
0x140078f16  mov     [rsp+0D8h+var_94], eax
0x140078f1a  test    eax, eax
0x140078f1c  js      loc_1400792B7
0x140078f22  mov     r14b, [rsp+0D8h+var_8F]
0x140078f27  jmp     short loc_140078F31
0x140078f29  mov     r14b, sil
0x140078f2c  mov     [rsp+0D8h+var_8F], sil
0x140078f31  cmp     [rdi], esi
0x140078f33  ja      loc_1400791F4
0x140078f39  lea     rdx, [rsp+0D8h+var_68]; struct _UNICODE_STRING *
0x140078f3e  mov     rcx, r15; struct _UNICODE_STRING *
0x140078f41  call    ?CreatePatchFilePath@CClfsAuthContainer@@CAJAEBU_UNICODE_STRING@@AEAU2@@Z; CClfsAuthContainer::CreatePatchFilePath(_UNICODE_STRING const &,_UNICODE_STRING &)
0x140078f46  mov     r12d, eax
0x140078f49  mov     [rsp+0D8h+var_94], eax
0x140078f4d  test    eax, eax
0x140078f4f  js      loc_1400792B7
0x140078f55  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x140078f5a  test    eax, eax
0x140078f5c  jz      short loc_140078FAE
0x140078f5e  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140078f65  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140078f6c  nop     dword ptr [rax+rax+00h]
0x140078f71  test    rax, rax
0x140078f74  jz      short loc_140078F8A
0x140078f76  mov     r8b, sil; unsigned __int8
0x140078f79  mov     edx, [r13+2Ch]; unsigned int
0x140078f7d  mov     rcx, rax; this
0x140078f80  call    ??0CClfsContainer@@QEAA@KE@Z; CClfsContainer::CClfsContainer(ulong,uchar)
0x140078f85  mov     rcx, rax
0x140078f88  jmp     short loc_140078F8C
0x140078f8a  xor     ecx, ecx
0x140078f8c  mov     [r13+80h], rcx
0x140078f93  test    rcx, rcx
0x140078f96  jnz     short loc_140078FA3
0x140078f98  mov     r12d, 0C000009Ah
0x140078f9e  jmp     loc_140078EF1
0x140078fa3  mov     rax, [rcx]
0x140078fa6  mov     rax, [rax]
0x140078fa9  call    _guard_dispatch_icall
0x140078fae  lea     rax, [rsp+0D8h+var_90]
0x140078fb3  mov     [rsp+0D8h+var_B8], rax; unsigned __int8 *
0x140078fb8  mov     dil, [rsp+0D8h+arg_18]
0x140078fc0  mov     r9b, dil; unsigned __int8
0x140078fc3  mov     r8, [rsp+0D8h+arg_10]; struct _CLFS_FILTER_CONTEXT *
0x140078fcb  lea     rdx, [rsp+0D8h+var_68]; struct _UNICODE_STRING *
0x140078fd0  mov     rcx, [r13+80h]; this
0x140078fd7  call    ?Open@CClfsContainer@@QEAAJAEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@EAEAE@Z; CClfsContainer::Open(_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,uchar,uchar &)
0x140078fdc  mov     r12d, eax
0x140078fdf  mov     [rsp+0D8h+var_94], eax
0x140078fe3  test    eax, eax
0x140078fe5  js      short loc_140079049
0x140078fe7  mov     [rsp+0D8h+var_98], sil
0x140078fec  mov     dil, [rsp+0D8h+var_90]
0x140078ff1  test    dil, dil
0x140078ff4  jz      short loc_140079028
0x140078ff6  lea     r9, [rsp+0D8h+var_88]; int *
0x140078ffb  lea     r8, [rsp+0D8h+var_8A]; unsigned __int8 *
0x140079000  mov     edx, esi; unsigned int
0x140079002  mov     rcx, [r13+80h]; this
0x140079009  call    ?CheckSecureAccess@CClfsContainer@@QEAAJKAEAEAEAJ@Z; CClfsContainer::CheckSecureAccess(ulong,uchar &,long &)
0x14007900e  mov     r12d, eax
0x140079011  mov     [rsp+0D8h+var_94], eax
0x140079015  test    eax, eax
0x140079017  js      loc_1400792B7
0x14007901d  cmp     [rsp+0D8h+var_8A], 0
0x140079022  jz      loc_140078EEB
0x140079028  mov     r12b, [rsp+0D8h+var_97]
0x14007902d  mov     r15, [rsp+0D8h+arg_28]
0x140079035  cmp     dil, [r15]
0x140079038  jz      loc_14007914B
0x14007903e  mov     r12d, 0C0000008h
0x140079044  jmp     loc_140078EF1
0x140079049  cmp     eax, 0C0000034h
0x14007904e  jnz     loc_1400792B7
0x140079054  mov     [rsp+0D8h+var_94], 0
0x14007905c  mov     r15, [rsp+0D8h+arg_28]
0x140079064  cmp     byte ptr [r15], 0
0x140079068  jz      short loc_14007907D
0x14007906a  mov     r9b, sil; unsigned __int8
0x14007906d  lea     rdx, [rsp+0D8h+P]; void **
0x140079072  mov     rcx, [r13+78h]; this
0x140079076  call    ?DuplicateSecurityDescriptor@CClfsContainer@@QEAAJAEAPEAXAEAKE@Z; CClfsContainer::DuplicateSecurityDescriptor(void * &,ulong &,uchar)
0x14007907b  jmp     short loc_14007908F
0x14007907d  lea     rdx, [rsp+0D8h+var_50]; unsigned int *
0x140079085  lea     rcx, [rsp+0D8h+P]; void **
0x14007908a  call    ?DuplicateNullSecurityDescriptor@CClfsContainer@@SAJAEAPEAXPEAK@Z; CClfsContainer::DuplicateNullSecurityDescriptor(void * &,ulong *)
0x14007908f  test    eax, eax
0x140079091  mov     [rsp+0D8h+var_94], eax
0x140079095  mov     r12d, eax
0x140079098  js      loc_1400792B7
0x14007909e  lea     rax, [rsp+0D8h+var_90]
0x1400790a3  mov     [rsp+0D8h+var_A0], rax; unsigned __int8 *
0x1400790a8  mov     byte ptr [rsp+0D8h+var_A8], dil; unsigned __int8
0x1400790ad  mov     [rsp+0D8h+var_B0], sil; unsigned __int8
0x1400790b2  mov     rax, [rsp+0D8h+P]
0x1400790b7  mov     [rsp+0D8h+var_B8], rax; void *
0x1400790bc  mov     r9, [rsp+0D8h+arg_10]; struct _CLFS_FILTER_CONTEXT *
0x1400790c4  lea     r8, [rsp+0D8h+var_58]; unsigned __int64 *
0x1400790cc  lea     rdx, [rsp+0D8h+var_68]; struct _UNICODE_STRING *
0x1400790d1  mov     rcx, [r13+80h]; BugCheckParameter4
0x1400790d8  call    ?Create@CClfsContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXEEAEAE@Z; CClfsContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,uchar,uchar &)
0x1400790dd  mov     r12d, eax
0x1400790e0  mov     [rsp+0D8h+var_94], eax
0x1400790e4  cmp     eax, 0C00000D7h
0x1400790e9  jnz     short loc_140079130
0x1400790eb  lea     rax, [rsp+0D8h+var_90]
0x1400790f0  mov     [rsp+0D8h+var_A0], rax; unsigned __int8 *
0x1400790f5  mov     byte ptr [rsp+0D8h+var_A8], dil; unsigned __int8
0x1400790fa  mov     [rsp+0D8h+var_B0], sil; unsigned __int8
0x1400790ff  mov     [rsp+0D8h+var_B8], 0; void *
0x140079108  mov     r9, [rsp+0D8h+arg_10]; struct _CLFS_FILTER_CONTEXT *
0x140079110  lea     r8, [rsp+0D8h+var_58]; unsigned __int64 *
0x140079118  lea     rdx, [rsp+0D8h+var_68]; struct _UNICODE_STRING *
0x14007911d  mov     rcx, [r13+80h]; BugCheckParameter4
0x140079124  call    ?Create@CClfsContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXEEAEAE@Z; CClfsContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,uchar,uchar &)
0x140079129  mov     r12d, eax
0x14007912c  mov     [rsp+0D8h+var_94], eax
0x140079130  test    r12d, r12d
0x140079133  js      loc_1400792B7
0x140079139  mov     r12b, sil
0x14007913c  mov     [rsp+0D8h+var_97], sil
0x140079141  mov     dil, [rsp+0D8h+var_90]
0x140079146  jmp     loc_140079035
0x14007914b  mov     edi, [r13+30h]
0x14007914f  mov     rcx, [r13+80h]; this
0x140079156  call    ?GetRawSectorSize@CClfsContainer@@QEAAKXZ; CClfsContainer::GetRawSectorSize(void)
0x14007915b  cmp     edi, eax
0x14007915d  jnz     loc_14007903E
0x140079163  mov     edi, [r13+34h]
0x140079167  mov     rcx, [r13+80h]; this
0x14007916e  call    ?GetAlignmentRequirement@CClfsContainer@@QEAAKXZ; CClfsContainer::GetAlignmentRequirement(void)
0x140079173  cmp     edi, eax
0x140079175  jnz     loc_14007903E
0x14007917b  test    r12b, r12b
0x14007917e  jz      short loc_1400791BC
0x140079180  mov     rcx, r13; this
0x140079183  call    ?InitializePatchFile@CClfsAuthContainer@@AEAAJXZ; CClfsAuthContainer::InitializePatchFile(void)
0x140079188  mov     r12d, eax
0x14007918b  mov     [rsp+0D8h+var_94], eax
0x14007918f  test    eax, eax
0x140079191  js      loc_1400792B7
0x140079197  mov     dil, [rsp+0D8h+var_98]
0x14007919c  test    dil, dil
0x14007919f  jz      short loc_1400791F4
0x1400791a1  lea     rdx, [rsp+0D8h+var_80]; struct _CLFS_CPF_HEADER **
0x1400791a6  mov     rcx, r13; this
0x1400791a9  call    ?VerifyPatchContents@CClfsAuthContainer@@AEAAJAEAPEAU_CLFS_CPF_HEADER@@@Z; CClfsAuthContainer::VerifyPatchContents(_CLFS_CPF_HEADER * &)
0x1400791ae  mov     ecx, [rsp+0D8h+var_84]
0x1400791b2  movzx   ecx, cl
0x1400791b5  test    eax, eax
0x1400791b7  cmovns  ecx, esi
0x1400791ba  jmp     short loc_1400791F8
0x1400791bc  mov     dil, [rsp+0D8h+var_98]
0x1400791c1  test    dil, dil
0x1400791c4  jz      short loc_1400791F4
0x1400791c6  lea     rdx, [rsp+0D8h+var_89]; unsigned __int8 *
0x1400791cb  mov     rcx, r13; this
0x1400791ce  call    ?VerifyIsPatchFile@CClfsAuthContainer@@AEAAJAEAE@Z; CClfsAuthContainer::VerifyIsPatchFile(uchar &)
0x1400791d3  mov     r12d, eax
0x1400791d6  mov     [rsp+0D8h+var_94], eax
0x1400791da  test    eax, eax
0x1400791dc  js      loc_1400792B7
0x1400791e2  cmp     [rsp+0D8h+var_89], 0
0x1400791e7  jnz     short loc_14007919C
0x1400791e9  mov     r12d, 0C01A000Dh
0x1400791ef  jmp     loc_140078EF1
0x1400791f4  mov     ecx, [rsp+0D8h+var_84]
0x1400791f8  test    cl, cl
0x1400791fa  jz      loc_140079292
0x140079200  lea     rax, [rsp+0D8h+var_8E]
0x140079205  mov     [rsp+0D8h+var_A8], rax; unsigned __int8 *
0x14007920a  mov     rax, [rsp+0D8h+arg_20]
0x140079212  mov     qword ptr [rsp+0D8h+var_B0], rax; unsigned __int64
0x140079217  mov     rax, [rsp+0D8h+var_70]
0x14007921c  mov     [rsp+0D8h+var_B8], rax; unsigned __int64
0x140079221  mov     r9, [rsp+0D8h+arg_10]; struct _CLFS_FILTER_CONTEXT *
0x140079229  mov     rdi, [rsp+0D8h+var_80]
0x14007922e  mov     rdx, rdi; struct _CLFS_CPF_HEADER *
0x140079231  mov     rcx, r13; this
0x140079234  call    ?RecoverContainer@CClfsAuthContainer@@AEAAJPEAU_CLFS_CPF_HEADER@@AEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@_K3AEAE@Z; CClfsAuthContainer::RecoverContainer(_CLFS_CPF_HEADER *,_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,unsigned __int64,unsigned __int64,uchar &)
0x140079239  mov     r12d, eax
0x14007923c  mov     [rsp+0D8h+var_94], eax
0x140079240  test    eax, eax
0x140079242  js      short loc_14007924D
0x140079244  or      [r13+0ACh], esi
0x14007924b  jmp     short loc_1400792B7
0x14007924d  cmp     eax, 0C01A000Dh
  ... truncated ...
```
