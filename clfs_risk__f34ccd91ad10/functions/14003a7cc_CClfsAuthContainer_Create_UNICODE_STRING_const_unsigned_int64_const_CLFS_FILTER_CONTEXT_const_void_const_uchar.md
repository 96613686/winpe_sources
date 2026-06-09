# CClfsAuthContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,unsigned __int64,uchar &)

- ea: `0x14003a7cc`
- end: `0x14003af39`
- name: `?Create@CClfsAuthContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXE_KAEAE@Z`
- size: `1901`
- prototype: `__int64 __usercall@<rax>(CClfsAuthContainer *__hidden this@<rcx>, const struct _UNICODE_STRING *@<rdx>, const unsigned __int64 *@<r8>, const struct _CLFS_FILTER_CONTEXT *@<r9>, void *const, unsigned __int8, unsigned __int64, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1400374cc`
- `0x14005ed70`
- `0x140062ef8`

## callees

- `0x14000f7bc`
- `0x140017f20`
- `0x140033a78`
- `0x140033c3c`
- `0x140039dc0`
- `0x14003a7cc`
- `0x14003b718`
- `0x14003d364`
- `0x14003d418`
- `0x14003effc`
- `0x14003f3c4`
- `0x14003f4d4`
- `0x14003fb20`
- `0x14004df28`
- `0x14004ec8c`
- `0x14004f140`
- `0x14004f788`
- `0x14005fbe8`
- `0x140069d44`
- `0x14006a3a0`
- `0x14006bc84`
- `0x140070a38`
- `0x140070cd4`
- `0x140073128`
- `0x14007536c`
- `0x140076b4c`
- `0x1400780d0`
- `0x140078618`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003aac4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003aac4`
- `HAL!KeQueryPerformanceCounter` at `0x14003a83e`
- `HAL!KeQueryPerformanceCounter` at `0x14003ae0d`
- `HAL!KeQueryPerformanceCounter` at `0x14007d967`
- `HAL!KeQueryPerformanceCounter` at `0x14003a83e`
- `HAL!KeQueryPerformanceCounter` at `0x14003ae0d`
- `HAL!KeQueryPerformanceCounter` at `0x14007d967`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::Create(
        CClfsAuthContainer *this,
        struct _UNICODE_STRING *a2,
        unsigned __int64 *a3,
        const struct _CLFS_FILTER_CONTEXT *a4,
        void *const a5,
        unsigned __int8 a6,
        unsigned __int64 a7,
        unsigned __int8 *a8)
{
  BOOL v8; // r14d
  LARGE_INTEGER PerformanceCounter; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int ContainerSize; // r15d
  ULONG_PTR v16; // rsi
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  struct _FILE_END_OF_FILE_INFORMATION v25; // rdx
  __int64 v26; // rcx
  CClfsContainer *v27; // rax
  CClfsContainer *v28; // rcx
  int v29; // eax
  char v30; // si
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // edi
  int v34; // esi
  __int64 v35; // r14
  ULONG LowPart; // eax
  CClfsContainer *v37; // rcx
  CClfsMerkleTree *v38; // rcx
  char v40; // [rsp+44h] [rbp-A4h]
  unsigned __int8 v41; // [rsp+45h] [rbp-A3h] BYREF
  char v42; // [rsp+46h] [rbp-A2h]
  bool v43; // [rsp+47h] [rbp-A1h]
  unsigned __int8 v44; // [rsp+48h] [rbp-A0h] BYREF
  unsigned __int8 v45[3]; // [rsp+49h] [rbp-9Fh] BYREF
  BOOL v46; // [rsp+4Ch] [rbp-9Ch]
  int v47; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int64 v48; // [rsp+58h] [rbp-90h]
  __int64 v49; // [rsp+60h] [rbp-88h]
  LARGE_INTEGER EndOfFile; // [rsp+68h] [rbp-80h]
  struct _FILE_END_OF_FILE_INFORMATION v51; // [rsp+70h] [rbp-78h] BYREF
  struct _UNICODE_STRING v52; // [rsp+78h] [rbp-70h] BYREF
  unsigned __int64 v53; // [rsp+88h] [rbp-60h] BYREF
  unsigned __int64 v54; // [rsp+90h] [rbp-58h] BYREF
  unsigned __int64 v55[10]; // [rsp+98h] [rbp-50h] BYREF

  v41 = 0;
  v42 = 0;
  LOBYTE(v8) = 0;
  v46 = v8;
  v43 = 0;
  v40 = 0;
  v54 = 4096;
  v53 = 0;
  v51 = 0;
  v45[0] = 0;
  v44 = 0;
  v47 = -1073741823;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v55[1] = PerformanceCounter.QuadPart;
  v52 = 0;
  if ( !(unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v13)
    && (int)CClfsAuthContainer::SetContainerSizes(this, *a3) < 0 )
  {
    ContainerSize = -1073741672;
    goto LABEL_66;
  }
  v16 = *((_QWORD *)this + 15);
  if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v14) )
  {
    v17 = *a3;
  }
  else
  {
    v48 = 0;
    v48 = *((_QWORD *)this + 1);
    v18 = *((_QWORD *)this + 2);
    v17 = v18 + v48;
    v48 += v18;
    if ( v18 )
    {
      v17 += 4096LL;
      v48 = v17;
    }
  }
  v55[0] = v17;
  ContainerSize = CClfsContainer::Create(v16, a2, v55, a4, a5, 1u, a6, a8);
  if ( ContainerSize >= 0 )
  {
    v42 = 1;
    if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v19) )
    {
      if ( (unsigned int)(*((_DWORD *)this + 34) - 2) > 1 )
      {
        v20 = *((_QWORD *)this + 15);
        if ( v20 )
        {
          if ( *(_QWORD *)(v20 + 48) && ClfsRegistryIsFileAuthExempt(*(PVOID *)(*((_QWORD *)this + 15) + 48LL)) )
          {
            *((_DWORD *)this + 34) = 2;
            *((_DWORD *)this + 43) |= 0x100u;
          }
        }
      }
    }
    *((_DWORD *)this + 12) = CClfsContainer::GetRawSectorSize(*((CClfsContainer **)this + 15));
    *((_DWORD *)this + 13) = CClfsContainer::GetAlignmentRequirement(*((CClfsContainer **)this + 15));
    if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v21)
      && (int)CClfsAuthContainer::SetContainerSizes(this, *a3) < 0 )
    {
      goto LABEL_17;
    }
    ContainerSize = CClfsContainer::GetContainerSize(*((CClfsContainer **)this + 15), &v53);
    if ( ContainerSize >= 0 )
    {
      v49 = 0;
      v49 = *((_QWORD *)this + 1);
      v22 = *((_QWORD *)this + 2);
      v23 = v22 + v49;
      v49 += v22;
      if ( v22 )
      {
        v23 += 4096;
        v49 = v23;
      }
      if ( v23 != v53 )
      {
        if ( !(unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v22) )
          goto LABEL_17;
        EndOfFile.QuadPart = 0;
        EndOfFile = *(LARGE_INTEGER *)((char *)this + 8);
        v24 = *((_QWORD *)this + 2);
        v25 = (struct _FILE_END_OF_FILE_INFORMATION)(v24 + EndOfFile.QuadPart);
        EndOfFile.QuadPart += v24;
        if ( v24 )
        {
          *(_QWORD *)&v25 += 4096LL;
          EndOfFile = v25.EndOfFile;
        }
        v51 = v25;
        ContainerSize = CClfsContainer::Truncate(*((CClfsContainer **)this + 15), &v51);
        if ( ContainerSize < 0 )
        {
LABEL_17:
          ContainerSize = -1073741672;
          goto LABEL_66;
        }
      }
      if ( (unsigned int)(*((_DWORD *)this + 34) - 2) > 1 )
      {
        ContainerSize = CClfsAuthContainer::CreatePatchFilePath(a2, &v52);
        if ( ContainerSize >= 0 )
        {
          if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v26) )
          {
            v27 = (CClfsContainer *)ExAllocateFromPagedLookasideList(&CClfsContainer::m_laList);
            if ( v27 )
              v28 = CClfsContainer::CClfsContainer(v27, *((_DWORD *)this + 11), 1u);
            else
              v28 = 0;
            *((_QWORD *)this + 16) = v28;
            if ( !v28 )
            {
              ContainerSize = -1073741670;
              goto LABEL_66;
            }
            (**(void (__fastcall ***)(CClfsContainer *))v28)(v28);
          }
          v29 = CClfsContainer::Open(*((CClfsContainer **)this + 16), &v52, a4, a6, (bool *)&v41);
          ContainerSize = v29;
          if ( v29 < 0 )
          {
            if ( v29 == -1073741772 )
            {
              ContainerSize = CClfsContainer::Create(*((_QWORD *)this + 16), &v52, &v54, a4, a5, 1u, a6, &v41);
              if ( ContainerSize == -1073741609 )
                ContainerSize = CClfsContainer::Create(*((_QWORD *)this + 16), &v52, &v54, a4, 0, 1u, a6, &v41);
              LOBYTE(v8) = ContainerSize >= 0;
              v46 = ContainerSize >= 0;
              v43 = ContainerSize >= 0;
            }
            v30 = 0;
          }
          else
          {
            v30 = 1;
            v40 = 1;
            if ( v41 )
            {
              ContainerSize = CClfsContainer::CheckSecureAccess(*((CClfsContainer **)this + 16), 1u, &v44, &v47);
              if ( ContainerSize < 0 )
                goto LABEL_66;
              if ( !v44 )
              {
                ContainerSize = -1073741790;
                goto LABEL_66;
              }
            }
          }
          if ( ContainerSize >= 0 )
          {
            if ( *((_DWORD *)this + 12) != CClfsContainer::GetRawSectorSize(*((CClfsContainer **)this + 16))
              || *((_DWORD *)this + 13) != CClfsContainer::GetAlignmentRequirement(*((CClfsContainer **)this + 16))
              || v41 != *a8 )
            {
              ContainerSize = -1073741816;
              goto LABEL_66;
            }
            if ( v8 )
            {
              ContainerSize = CClfsAuthContainer::InitializePatchFile(this);
              if ( ContainerSize < 0 )
                goto LABEL_66;
            }
            else if ( v30 )
            {
              ContainerSize = CClfsAuthContainer::VerifyIsPatchFile(this, v45);
              if ( ContainerSize < 0 )
                goto LABEL_66;
              if ( !v45[0] )
                goto LABEL_56;
            }
            if ( (int)CClfsAuthContainer::InitializeHashTableMetadata(this, a7) >= 0
              && CClfsAuthContainer::CalculateMerkleNodeCount(
                   *((_QWORD *)this + 2),
                   *((_DWORD *)this + 41),
                   (unsigned int *)this + 40) >= 0 )
            {
              CClfsMerkleTree::ResetTree(*((CClfsMerkleTree **)this + 19));
              if ( (int)CClfsMerkleTree::StartTreeInitialization(
                          *((CClfsMerkleTree **)this + 19),
                          *((_DWORD *)this + 40)) >= 0 )
              {
                ContainerSize = CClfsAuthContainer::ProcessHashTable(this, *((struct CClfsContainer **)this + 15), 1u);
                if ( ContainerSize < 0 )
                  goto LABEL_66;
                if ( (int)CClfsAuthContainer::UpdateDomainMerkleNode(this) >= 0
                  && (int)CClfsAuthContainer::UpdateHashTableMetadataNode(this, 1u) >= 0
                  && (int)CClfsMerkleTree::FinishTreeInitialization(
                            *((CClfsMerkleTree **)this + 19),
                            (unsigned __int8 *)(*((_QWORD *)this + 18) + 480LL),
                            *((_DWORD *)this + 14)) >= 0 )
                {
                  ContainerSize = CClfsAuthContainer::WriteHashTableMetadata(
                                    this,
                                    *((struct _KEVENT **)this + 3),
                                    0,
                                    *((struct CClfsContainer **)this + 15),
                                    1);
                  if ( ContainerSize >= 0 )
                    *((_DWORD *)this + 43) |= 1u;
                  goto LABEL_66;
                }
              }
            }
LABEL_56:
            ContainerSize = -1072037875;
          }
        }
      }
    }
  }
LABEL_66:
  CClfsAuthContainer::ReleasePatchFilePath(&v52);
  if ( ContainerSize < 0 )
  {
    *((_DWORD *)this + 43) = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 6) = 0;
    if ( v42 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 24LL))(*((_QWORD *)this + 15));
    if ( (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v31) )
    {
      v37 = (CClfsContainer *)*((_QWORD *)this + 16);
      if ( v37 )
      {
        if ( v8 )
        {
          (*(void (__fastcall **)(CClfsContainer *))(*(_QWORD *)v37 + 24LL))(v37);
        }
        else if ( v40 )
        {
          CClfsContainer::Close(v37);
        }
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 8LL))(*((_QWORD *)this + 16));
        *((_QWORD *)this + 16) = 0;
      }
    }
    else if ( v8 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 24LL))(*((_QWORD *)this + 16));
    }
    else if ( v40 )
    {
      CClfsContainer::Close(*((CClfsContainer **)this + 16));
    }
    v38 = (CClfsMerkleTree *)*((_QWORD *)this + 19);
    if ( v38 )
      CClfsMerkleTree::ResetTree(v38);
  }
  else
  {
    v32 = *((_QWORD *)this + 15);
    if ( v32 && *(_QWORD *)(v32 + 48) )
    {
      v33 = *((_DWORD *)this + 43);
      v34 = *((_DWORD *)this + 34);
      v35 = *((_QWORD *)this + 1);
      LowPart = KeQueryPerformanceCounter(0).LowPart;
      ClfsTelemetryCreatePerf(
        *(_QWORD *)(*((_QWORD *)this + 15) + 48LL) + 88,
        LowPart - PerformanceCounter.LowPart,
        v35,
        a7,
        v34,
        v33,
        1);
    }
  }
  return (unsigned int)ContainerSize;
}

```

## disassembly

```asm
0x14003a7cc  mov     r11, rsp
0x14003a7cf  mov     [r11+20h], r9
0x14003a7d3  mov     [r11+10h], rdx
0x14003a7d7  mov     [r11+8], rcx
0x14003a7db  push    rbx
0x14003a7dc  push    rsi
0x14003a7dd  push    rdi
0x14003a7de  push    r12
0x14003a7e0  push    r13
0x14003a7e2  push    r14
0x14003a7e4  push    r15
0x14003a7e6  sub     rsp, 0B0h
0x14003a7ed  mov     rdi, r8
0x14003a7f0  mov     r15, rdx
0x14003a7f3  mov     r13, rcx
0x14003a7f6  xor     eax, eax
0x14003a7f8  mov     [rsp+0E8h+var_A8], eax
0x14003a7fc  mov     [rsp+0E8h+var_A3], al
0x14003a800  xorps   xmm0, xmm0
0x14003a803  movups  xmmword ptr [rsp+0E8h+var_70.Length], xmm0
0x14003a808  mov     [rsp+0E8h+var_A2], al
0x14003a80c  mov     r14b, al
0x14003a80f  mov     [rsp+0E8h+var_9C], r14d
0x14003a814  mov     [rsp+0E8h+var_A1], al
0x14003a818  mov     [rsp+0E8h+var_A4], al
0x14003a81c  mov     qword ptr [r11-58h], 1000h
0x14003a824  mov     [r11-60h], rax
0x14003a828  mov     [r11-78h], rax
0x14003a82c  mov     [rsp+0E8h+var_9F], al
0x14003a830  mov     [rsp+0E8h+var_A0], al
0x14003a834  mov     [rsp+0E8h+var_98], 0C0000001h
0x14003a83c  xor     ecx, ecx; PerformanceFrequency
0x14003a83e  call    cs:__imp_KeQueryPerformanceCounter
0x14003a845  nop     dword ptr [rax+rax+00h]
0x14003a84a  mov     rbx, rax
0x14003a84d  mov     [rsp+0E8h+var_48], rax
0x14003a855  xorps   xmm0, xmm0
0x14003a858  movups  xmmword ptr [rsp+0E8h+var_70.Length], xmm0
0x14003a85d  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14003a862  test    eax, eax
0x14003a864  jnz     short loc_14003A88F
0x14003a866  mov     rdx, [rdi]; unsigned __int64
0x14003a869  mov     rcx, r13; this
0x14003a86c  call    ?SetContainerSizes@CClfsAuthContainer@@AEAAJ_K@Z; CClfsAuthContainer::SetContainerSizes(unsigned __int64)
0x14003a871  mov     [rsp+0E8h+var_A8], eax
0x14003a875  test    eax, eax
0x14003a877  jns     short loc_14003A88F
0x14003a879  mov     r15d, 0C0000098h
0x14003a87f  mov     [rsp+0E8h+var_A8], r15d
0x14003a884  mov     r12d, 1
0x14003a88a  jmp     loc_14003ADD8
0x14003a88f  mov     rsi, [r13+78h]
0x14003a893  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14003a898  test    eax, eax
0x14003a89a  jz      short loc_14003A8A1
0x14003a89c  mov     rax, [rdi]
0x14003a89f  jmp     short loc_14003A8CF
0x14003a8a1  mov     [rsp+0E8h+var_90], 0
0x14003a8aa  mov     rax, [r13+8]
0x14003a8ae  mov     [rsp+0E8h+var_90], rax
0x14003a8b3  mov     rcx, [r13+10h]
0x14003a8b7  add     rax, rcx
0x14003a8ba  mov     [rsp+0E8h+var_90], rax
0x14003a8bf  test    rcx, rcx
0x14003a8c2  jz      short loc_14003A8CF
0x14003a8c4  add     rax, 1000h
0x14003a8ca  mov     [rsp+0E8h+var_90], rax
0x14003a8cf  mov     [rsp+0E8h+var_50], rax
0x14003a8d7  mov     rax, [rsp+0E8h+arg_38]
0x14003a8df  mov     [rsp+0E8h+var_B0], rax; unsigned __int8 *
0x14003a8e4  mov     al, [rsp+0E8h+arg_28]
0x14003a8eb  mov     [rsp+0E8h+var_B8], al; unsigned __int8
0x14003a8ef  mov     r12d, 1
0x14003a8f5  mov     [rsp+0E8h+var_C0], r12b; unsigned __int8
0x14003a8fa  mov     rax, [rsp+0E8h+arg_20]
0x14003a902  mov     [rsp+0E8h+var_C8], rax; void *
0x14003a907  mov     r9, [rsp+0E8h+arg_18]; struct _CLFS_FILTER_CONTEXT *
0x14003a90f  lea     r8, [rsp+0E8h+var_50]; unsigned __int64 *
0x14003a917  mov     rdx, r15; struct _UNICODE_STRING *
0x14003a91a  mov     rcx, rsi; BugCheckParameter4
0x14003a91d  call    ?Create@CClfsContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXEEAEAE@Z; CClfsContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,uchar,uchar &)
0x14003a922  mov     r15d, eax
0x14003a925  mov     [rsp+0E8h+var_A8], eax
0x14003a929  test    eax, eax
0x14003a92b  js      loc_14003ADD8
0x14003a931  mov     [rsp+0E8h+var_A2], r12b
0x14003a936  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14003a93b  test    eax, eax
0x14003a93d  jz      short loc_14003A985
0x14003a93f  mov     eax, [r13+88h]
0x14003a946  sub     eax, 2
0x14003a949  cmp     eax, r12d
0x14003a94c  jbe     short loc_14003A985
0x14003a94e  mov     rax, [r13+78h]
0x14003a952  test    rax, rax
0x14003a955  jz      short loc_14003A985
0x14003a957  mov     rax, [rax+30h]
0x14003a95b  test    rax, rax
0x14003a95e  jz      short loc_14003A985
0x14003a960  mov     rcx, [r13+78h]
0x14003a964  mov     rcx, [rcx+30h]; Object
0x14003a968  call    ?ClfsRegistryIsFileAuthExempt@@YAEPEAX@Z; ClfsRegistryIsFileAuthExempt(void *)
0x14003a96d  test    al, al
0x14003a96f  jz      short loc_14003A985
0x14003a971  mov     dword ptr [r13+88h], 2
0x14003a97c  bts     dword ptr [r13+0ACh], 8
0x14003a985  mov     rcx, [r13+78h]; this
0x14003a989  call    ?GetRawSectorSize@CClfsContainer@@QEAAKXZ; CClfsContainer::GetRawSectorSize(void)
0x14003a98e  mov     [r13+30h], eax
0x14003a992  mov     rcx, [r13+78h]; this
0x14003a996  call    ?GetAlignmentRequirement@CClfsContainer@@QEAAKXZ; CClfsContainer::GetAlignmentRequirement(void)
0x14003a99b  mov     [r13+34h], eax
0x14003a99f  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14003a9a4  test    eax, eax
0x14003a9a6  jz      short loc_14003A9CB
0x14003a9a8  mov     rdx, [rdi]; unsigned __int64
0x14003a9ab  mov     rcx, r13; this
0x14003a9ae  call    ?SetContainerSizes@CClfsAuthContainer@@AEAAJ_K@Z; CClfsAuthContainer::SetContainerSizes(unsigned __int64)
0x14003a9b3  mov     [rsp+0E8h+var_A8], eax
0x14003a9b7  test    eax, eax
0x14003a9b9  jns     short loc_14003A9CB
0x14003a9bb  mov     r15d, 0C0000098h
0x14003a9c1  mov     [rsp+0E8h+var_A8], r15d
0x14003a9c6  jmp     loc_14003ADD8
0x14003a9cb  lea     rdx, [rsp+0E8h+var_60]; unsigned __int64 *
0x14003a9d3  mov     rcx, [r13+78h]; this
0x14003a9d7  call    ?GetContainerSize@CClfsContainer@@QEAAJAEA_K@Z; CClfsContainer::GetContainerSize(unsigned __int64 &)
0x14003a9dc  mov     r15d, eax
0x14003a9df  mov     [rsp+0E8h+var_A8], eax
0x14003a9e3  test    eax, eax
0x14003a9e5  js      loc_14003ADD8
0x14003a9eb  mov     [rsp+0E8h+var_88], 0
0x14003a9f4  mov     rax, [r13+8]
0x14003a9f8  mov     [rsp+0E8h+var_88], rax
0x14003a9fd  mov     rcx, [r13+10h]
0x14003aa01  lea     rdx, [rcx+rax]
0x14003aa05  mov     [rsp+0E8h+var_88], rdx
0x14003aa0a  test    rcx, rcx
0x14003aa0d  jz      short loc_14003AA1B
0x14003aa0f  add     rdx, 1000h
0x14003aa16  mov     [rsp+0E8h+var_88], rdx
0x14003aa1b  cmp     rdx, [rsp+0E8h+var_60]
0x14003aa23  jz      short loc_14003AA80
0x14003aa25  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14003aa2a  test    eax, eax
0x14003aa2c  jz      short loc_14003A9BB
0x14003aa2e  mov     [rsp+0E8h+var_80], 0
0x14003aa37  mov     rax, [r13+8]
0x14003aa3b  mov     [rsp+0E8h+var_80], rax
0x14003aa40  mov     rcx, [r13+10h]
0x14003aa44  lea     rdx, [rcx+rax]
0x14003aa48  mov     [rsp+0E8h+var_80], rdx
0x14003aa4d  test    rcx, rcx
0x14003aa50  jz      short loc_14003AA5E
0x14003aa52  add     rdx, 1000h
0x14003aa59  mov     [rsp+0E8h+var_80], rdx
0x14003aa5e  mov     qword ptr [rsp+0E8h+var_78.EndOfFile], rdx
0x14003aa63  lea     rdx, [rsp+0E8h+var_78]; struct _FILE_END_OF_FILE_INFORMATION *
0x14003aa68  mov     rcx, [r13+78h]; this
0x14003aa6c  call    ?Truncate@CClfsContainer@@QEAAJAEAU_FILE_END_OF_FILE_INFORMATION@@@Z; CClfsContainer::Truncate(_FILE_END_OF_FILE_INFORMATION &)
0x14003aa71  mov     r15d, eax
0x14003aa74  mov     [rsp+0E8h+var_A8], eax
0x14003aa78  test    eax, eax
0x14003aa7a  js      loc_14003A9BB
0x14003aa80  mov     eax, [r13+88h]
0x14003aa87  sub     eax, 2
0x14003aa8a  cmp     eax, r12d
0x14003aa8d  jbe     loc_14003ADD8
0x14003aa93  lea     rdx, [rsp+0E8h+var_70]; struct _UNICODE_STRING *
0x14003aa98  mov     rcx, [rsp+0E8h+arg_8]; struct _UNICODE_STRING *
0x14003aaa0  call    ?CreatePatchFilePath@CClfsAuthContainer@@CAJAEBU_UNICODE_STRING@@AEAU2@@Z; CClfsAuthContainer::CreatePatchFilePath(_UNICODE_STRING const &,_UNICODE_STRING &)
0x14003aaa5  mov     r15d, eax
0x14003aaa8  mov     [rsp+0E8h+var_A8], eax
0x14003aaac  test    eax, eax
0x14003aaae  js      loc_14003ADD8
0x14003aab4  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14003aab9  test    eax, eax
0x14003aabb  jz      short loc_14003AB0D
0x14003aabd  lea     rcx, ?m_laList@CClfsContainer@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x14003aac4  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003aacb  nop     dword ptr [rax+rax+00h]
0x14003aad0  test    rax, rax
0x14003aad3  jz      short loc_14003AAE9
0x14003aad5  mov     r8b, r12b; unsigned __int8
0x14003aad8  mov     edx, [r13+2Ch]; unsigned int
0x14003aadc  mov     rcx, rax; this
0x14003aadf  call    ??0CClfsContainer@@QEAA@KE@Z; CClfsContainer::CClfsContainer(ulong,uchar)
0x14003aae4  mov     rcx, rax
0x14003aae7  jmp     short loc_14003AAEB
0x14003aae9  xor     ecx, ecx
0x14003aaeb  mov     [r13+80h], rcx
0x14003aaf2  test    rcx, rcx
0x14003aaf5  jnz     short loc_14003AB02
0x14003aaf7  mov     r15d, 0C000009Ah
0x14003aafd  jmp     loc_14003A9C1
0x14003ab02  mov     rax, [rcx]
0x14003ab05  mov     rax, [rax]
0x14003ab08  call    _guard_dispatch_icall
0x14003ab0d  lea     rax, [rsp+0E8h+var_A3]
0x14003ab12  mov     [rsp+0E8h+var_C8], rax; unsigned __int8 *
0x14003ab17  mov     dil, [rsp+0E8h+arg_28]
0x14003ab1f  mov     r9b, dil; unsigned __int8
0x14003ab22  mov     rsi, [rsp+0E8h+arg_18]
0x14003ab2a  mov     r8, rsi; struct _CLFS_FILTER_CONTEXT *
0x14003ab2d  lea     rdx, [rsp+0E8h+var_70]; struct _UNICODE_STRING *
0x14003ab32  mov     rcx, [r13+80h]; this
0x14003ab39  call    ?Open@CClfsContainer@@QEAAJAEAU_UNICODE_STRING@@AEBU_CLFS_FILTER_CONTEXT@@EAEAE@Z; CClfsContainer::Open(_UNICODE_STRING &,_CLFS_FILTER_CONTEXT const &,uchar,uchar &)
0x14003ab3e  mov     r15d, eax
0x14003ab41  mov     [rsp+0E8h+var_A8], eax
0x14003ab45  test    eax, eax
0x14003ab47  js      short loc_14003AB9A
0x14003ab49  mov     sil, r12b
0x14003ab4c  mov     [rsp+0E8h+var_A4], r12b
0x14003ab51  cmp     [rsp+0E8h+var_A3], 0
0x14003ab56  jz      loc_14003AC4A
0x14003ab5c  lea     r9, [rsp+0E8h+var_98]; int *
0x14003ab61  lea     r8, [rsp+0E8h+var_A0]; unsigned __int8 *
0x14003ab66  mov     edx, r12d; unsigned int
0x14003ab69  mov     rcx, [r13+80h]; this
0x14003ab70  call    ?CheckSecureAccess@CClfsContainer@@QEAAJKAEAEAEAJ@Z; CClfsContainer::CheckSecureAccess(ulong,uchar &,long &)
0x14003ab75  mov     r15d, eax
0x14003ab78  mov     [rsp+0E8h+var_A8], eax
0x14003ab7c  test    eax, eax
0x14003ab7e  js      loc_14003ADD8
0x14003ab84  cmp     [rsp+0E8h+var_A0], 0
0x14003ab89  jnz     loc_14003AC4A
0x14003ab8f  mov     r15d, 0C0000022h
0x14003ab95  jmp     loc_14003A9C1
0x14003ab9a  cmp     eax, 0C0000034h
0x14003ab9f  jnz     loc_14003AC45
0x14003aba5  lea     rax, [rsp+0E8h+var_A3]
0x14003abaa  mov     [rsp+0E8h+var_B0], rax; unsigned __int8 *
0x14003abaf  mov     [rsp+0E8h+var_B8], dil; unsigned __int8
0x14003abb4  mov     [rsp+0E8h+var_C0], r12b; unsigned __int8
0x14003abb9  mov     rax, [rsp+0E8h+arg_20]
0x14003abc1  mov     [rsp+0E8h+var_C8], rax; void *
0x14003abc6  mov     r9, rsi; struct _CLFS_FILTER_CONTEXT *
0x14003abc9  lea     r8, [rsp+0E8h+var_58]; unsigned __int64 *
0x14003abd1  lea     rdx, [rsp+0E8h+var_70]; struct _UNICODE_STRING *
0x14003abd6  mov     rcx, [r13+80h]; BugCheckParameter4
0x14003abdd  call    ?Create@CClfsContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXEEAEAE@Z; CClfsContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,uchar,uchar &)
0x14003abe2  mov     r15d, eax
0x14003abe5  mov     [rsp+0E8h+var_A8], eax
0x14003abe9  cmp     eax, 0C00000D7h
0x14003abee  jnz     short loc_14003AC30
0x14003abf0  lea     rax, [rsp+0E8h+var_A3]
0x14003abf5  mov     [rsp+0E8h+var_B0], rax; unsigned __int8 *
0x14003abfa  mov     [rsp+0E8h+var_B8], dil; unsigned __int8
0x14003abff  mov     [rsp+0E8h+var_C0], r12b; unsigned __int8
0x14003ac04  mov     [rsp+0E8h+var_C8], 0; void *
0x14003ac0d  mov     r9, rsi; struct _CLFS_FILTER_CONTEXT *
0x14003ac10  lea     r8, [rsp+0E8h+var_58]; unsigned __int64 *
0x14003ac18  lea     rdx, [rsp+0E8h+var_70]; struct _UNICODE_STRING *
0x14003ac1d  mov     rcx, [r13+80h]; BugCheckParameter4
0x14003ac24  call    ?Create@CClfsContainer@@QEAAJAEBU_UNICODE_STRING@@AEB_KAEBU_CLFS_FILTER_CONTEXT@@QEAXEEAEAE@Z; CClfsContainer::Create(_UNICODE_STRING const &,unsigned __int64 const &,_CLFS_FILTER_CONTEXT const &,void * const,uchar,uchar,uchar &)
0x14003ac29  mov     r15d, eax
0x14003ac2c  mov     [rsp+0E8h+var_A8], eax
0x14003ac30  movzx   r14d, r14b
0x14003ac34  test    r15d, r15d
0x14003ac37  cmovns  r14d, r12d
0x14003ac3b  mov     [rsp+0E8h+var_9C], r14d
0x14003ac40  mov     [rsp+0E8h+var_A1], r14b
0x14003ac45  mov     sil, [rsp+0E8h+var_A4]
0x14003ac4a  test    r15d, r15d
0x14003ac4d  js      loc_14003ADD8
0x14003ac53  mov     rcx, [r13+80h]; this
0x14003ac5a  call    ?GetRawSectorSize@CClfsContainer@@QEAAKXZ; CClfsContainer::GetRawSectorSize(void)
0x14003ac5f  cmp     [r13+30h], eax
0x14003ac63  jz      short loc_14003AC70
0x14003ac65  mov     r15d, 0C0000008h
0x14003ac6b  jmp     loc_14003A9C1
0x14003ac70  mov     rcx, [r13+80h]; this
0x14003ac77  call    ?GetAlignmentRequirement@CClfsContainer@@QEAAKXZ; CClfsContainer::GetAlignmentRequirement(void)
0x14003ac7c  cmp     [r13+34h], eax
0x14003ac80  jnz     short loc_14003AC65
0x14003ac82  mov     rax, [rsp+0E8h+arg_38]
0x14003ac8a  mov     al, [rax]
0x14003ac8c  cmp     [rsp+0E8h+var_A3], al
0x14003ac90  jnz     short loc_14003AC65
0x14003ac92  test    r14b, r14b
0x14003ac95  jz      short loc_14003ACB0
0x14003ac97  mov     rcx, r13; this
0x14003ac9a  call    ?InitializePatchFile@CClfsAuthContainer@@AEAAJXZ; CClfsAuthContainer::InitializePatchFile(void)
0x14003ac9f  mov     r15d, eax
0x14003aca2  mov     [rsp+0E8h+var_A8], eax
0x14003aca6  test    eax, eax
0x14003aca8  js      loc_14003ADD8
0x14003acae  jmp     short loc_14003ACE3
0x14003acb0  test    sil, sil
0x14003acb3  jz      short loc_14003ACE3
0x14003acb5  lea     rdx, [rsp+0E8h+var_9F]; unsigned __int8 *
0x14003acba  mov     rcx, r13; this
0x14003acbd  call    ?VerifyIsPatchFile@CClfsAuthContainer@@AEAAJAEAE@Z; CClfsAuthContainer::VerifyIsPatchFile(uchar &)
0x14003acc2  mov     r15d, eax
0x14003acc5  mov     [rsp+0E8h+var_A8], eax
0x14003acc9  test    eax, eax
0x14003accb  js      loc_14003ADD8
0x14003acd1  cmp     [rsp+0E8h+var_9F], 0
0x14003acd6  jnz     short loc_14003ACE3
0x14003acd8  mov     r15d, 0C01A000Dh
  ... truncated ...
```
