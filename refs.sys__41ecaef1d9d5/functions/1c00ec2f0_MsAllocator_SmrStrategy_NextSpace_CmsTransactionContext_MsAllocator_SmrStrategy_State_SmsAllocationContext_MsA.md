# MsAllocator::SmrStrategy::NextSpace(CmsTransactionContext *,MsAllocator::SmrStrategy::State *,SmsAllocationContext *,MsAllocator::SmrStrategy::Context &)

- ea: `0x1c00ec2f0`
- end: `0x1c00ec589`
- name: `?NextSpace@SmrStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAUSmsAllocationContext@@AEAUContext@12@@Z`
- size: `665`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, struct MsAllocator::SmrStrategy::State *, struct SmsAllocationContext *, struct MsAllocator::SmrStrategy::Context *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1c00ea170`

## callees

- `0x1c0024964`
- `0x1c006a644`
- `0x1c00eb030`
- `0x1c00ec2f0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ec337`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00ec337`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ec46e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ec518`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ec561`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ec46e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ec518`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00ec561`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ec42f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ec498`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ec545`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ec42f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ec498`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00ec545`

## pseudocode

```c
__int64 __fastcall MsAllocator::SmrStrategy::NextSpace(
        struct CmsTransactionContext *a1,
        struct MsAllocator::SmrStrategy::State *a2,
        struct SmsAllocationContext *a3,
        struct MsAllocator::SmrStrategy::Context *a4)
{
  __int64 v4; // rdi
  struct SmsContainer *v7; // rbx
  unsigned int v8; // r12d
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  int NextFreeSMRBand; // eax
  __int64 v15; // rdx
  char *v16; // rsi
  struct _IO_REMOVE_LOCK *v17; // rcx
  struct SmsContainer *v18; // rbx
  __int64 v19; // rcx
  struct SmsContainer *v20; // rax
  __int64 v21; // rcx
  struct SmsContainer *v23; // [rsp+88h] [rbp+10h] BYREF
  char *v24; // [rsp+90h] [rbp+18h]

  v4 = *(_QWORD *)a2;
  *((_DWORD *)a3 + 18) = 7;
  v24 = (char *)a2 + 8;
  v7 = 0;
  v8 = 0;
  v23 = 0;
  ExAcquirePushLockExclusiveEx((char *)a2 + 8, 0);
  LODWORD(v11) = *(_DWORD *)(v4 + 80);
  do
  {
    v12 = *((_DWORD *)a3 + 19);
    if ( v12 == (_DWORD)v11 || (v13 = *((_QWORD *)a2 + 2)) == 0 || *(_DWORD *)(v13 + 612) == (_DWORD)v11 )
    {
      NextFreeSMRBand = MsAllocator::SmrStrategy::GetNextFreeSMRBand(a1, a2, &v23);
      v7 = v23;
      v8 = NextFreeSMRBand;
      if ( NextFreeSMRBand < 0 )
        break;
      SmsContainer::LogActivity(v23, 9, *(_QWORD *)(v4 + 1840), *((unsigned int *)a3 + 19));
      v12 = *((_DWORD *)a3 + 19);
      LODWORD(v11) = *(_DWORD *)(v4 + 80);
    }
    if ( v12 == (_DWORD)v11 )
    {
      v15 = 0;
      *(_OWORD *)a4 = *(_OWORD *)((char *)v7
                                + (unsigned int)(*(_DWORD *)(*(_QWORD *)(v4 + 3048) + 228LL)
                                               * *(_DWORD *)(*(_QWORD *)(v4 + 3048) + 232LL))
                                + 632);
    }
    else
    {
      v16 = (char *)a2 + 16;
      if ( v7 )
      {
        if ( *(_QWORD *)v16 )
        {
          if ( CmsVolumeContainer::GetContainerReference(
                 *(CmsVolumeContainer **)(v4 + 3048),
                 a1,
                 *((_QWORD *)a2 + 3),
                 (struct SmsContainer **)a2 + 2,
                 1u,
                 0,
                 0) >= 0 )
          {
            _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v16 + 84LL));
            v17 = (struct _IO_REMOVE_LOCK *)(*(_QWORD *)(v4 + 3048) + 328LL);
            _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v16 + 88LL));
            IoReleaseRemoveLockEx(v17, 0, 0x20u);
            --*((_DWORD *)a1 + 706);
            v7 = v23;
          }
          *(_QWORD *)v16 = 0;
        }
        _InterlockedIncrement((volatile signed __int32 *)v7 + 21);
        _InterlockedIncrement((volatile signed __int32 *)v23 + 18);
        v18 = v23;
        ExReleasePushLockEx((char *)v23 + 104, 2);
        --*((_DWORD *)a1 + 707);
        v19 = *(_QWORD *)(v4 + 3048);
        _InterlockedDecrement((volatile signed __int32 *)v18 + 22);
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v19 + 328), 0, 0x20u);
        --*((_DWORD *)a1 + 706);
        v20 = v23;
        v7 = 0;
        *(_QWORD *)v16 = v23;
        v23 = 0;
        *((_QWORD *)a2 + 3) = *((_QWORD *)v20 + 69);
      }
      *(_OWORD *)a4 = *(_OWORD *)((unsigned int)(*(_DWORD *)(*(_QWORD *)(v4 + 3048) + 228LL)
                                               * *(_DWORD *)(*(_QWORD *)(v4 + 3048) + 232LL))
                                + *(_QWORD *)v16
                                + 632LL);
      v15 = *(int *)(*(_QWORD *)v16 + 612LL);
    }
    *((_QWORD *)a4 + 2) = v15;
    v11 = *(int *)(v4 + 80);
  }
  while ( v15 == v11 );
  if ( v7 )
  {
    ExReleasePushLockEx((char *)v7 + 104, 2);
    --*((_DWORD *)a1 + 707);
    v21 = *(_QWORD *)(v4 + 3048);
    _InterlockedDecrement((volatile signed __int32 *)v7 + 22);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v21 + 328), 0, 0x20u);
    --*((_DWORD *)a1 + 706);
  }
  ExReleasePushLockEx(v24, 0);
  return v8;
}

```

## disassembly

```asm
0x1c00ec2f0  mov     rax, rsp
0x1c00ec2f3  mov     [rax+8], rbx
0x1c00ec2f7  push    rbp
0x1c00ec2f8  push    rsi
0x1c00ec2f9  push    rdi
0x1c00ec2fa  push    r12
0x1c00ec2fc  push    r13
0x1c00ec2fe  push    r14
0x1c00ec300  push    r15
0x1c00ec302  sub     rsp, 40h
0x1c00ec306  mov     rdi, [rdx]
0x1c00ec309  lea     rsi, [rdx+8]
0x1c00ec30d  mov     r14, rdx
0x1c00ec310  mov     dword ptr [r8+48h], 7
0x1c00ec318  mov     rbp, rcx
0x1c00ec31b  mov     [rsp+78h+arg_10], rsi
0x1c00ec323  xor     ebx, ebx
0x1c00ec325  mov     rcx, rsi
0x1c00ec328  xor     r12d, r12d
0x1c00ec32b  mov     [rax+10h], rbx
0x1c00ec32f  xor     edx, edx
0x1c00ec331  mov     r13, r9
0x1c00ec334  mov     r15, r8
0x1c00ec337  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00ec33e  nop     dword ptr [rax+rax+00h]
0x1c00ec343  mov     ecx, [rdi+50h]
0x1c00ec346  mov     eax, [r15+4Ch]
0x1c00ec34a  cmp     eax, ecx
0x1c00ec34c  jz      short loc_1C00EC35F
0x1c00ec34e  mov     rdx, [r14+10h]
0x1c00ec352  test    rdx, rdx
0x1c00ec355  jz      short loc_1C00EC35F
0x1c00ec357  cmp     [rdx+264h], ecx
0x1c00ec35d  jnz     short loc_1C00EC3A4
0x1c00ec35f  lea     r8, [rsp+78h+arg_8]; struct SmsContainer **
0x1c00ec367  mov     rdx, r14; struct MsAllocator::SmrStrategy::State *
0x1c00ec36a  mov     rcx, rbp; struct CmsTransactionContext *
0x1c00ec36d  call    ?GetNextFreeSMRBand@SmrStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAPEAUSmsContainer@@@Z; MsAllocator::SmrStrategy::GetNextFreeSMRBand(CmsTransactionContext *,MsAllocator::SmrStrategy::State *,SmsContainer * *)
0x1c00ec372  mov     rbx, [rsp+78h+arg_8]
0x1c00ec37a  mov     r12d, eax
0x1c00ec37d  test    eax, eax
0x1c00ec37f  js      loc_1C00EC50A
0x1c00ec385  mov     r9d, [r15+4Ch]
0x1c00ec389  mov     edx, 9
0x1c00ec38e  mov     r8, [rdi+730h]
0x1c00ec395  mov     rcx, rbx
0x1c00ec398  call    ?LogActivity@SmsContainer@@QEAAXW4EMS_BAND_ACTIVITY@@_K1@Z; SmsContainer::LogActivity(EMS_BAND_ACTIVITY,unsigned __int64,unsigned __int64)
0x1c00ec39d  mov     eax, [r15+4Ch]
0x1c00ec3a1  mov     ecx, [rdi+50h]
0x1c00ec3a4  cmp     eax, ecx
0x1c00ec3a6  jnz     short loc_1C00EC3D1
0x1c00ec3a8  mov     rax, [rdi+0BE8h]
0x1c00ec3af  mov     ecx, [rax+0E8h]
0x1c00ec3b5  imul    ecx, [rax+0E4h]
0x1c00ec3bc  xor     edx, edx
0x1c00ec3be  movups  xmm0, xmmword ptr [rcx+rbx+278h]
0x1c00ec3c6  movdqu  xmmword ptr [r13+0], xmm0
0x1c00ec3cc  jmp     loc_1C00EC4F9
0x1c00ec3d1  lea     rsi, [r14+10h]
0x1c00ec3d5  test    rbx, rbx
0x1c00ec3d8  jz      loc_1C00EC4CA
0x1c00ec3de  cmp     qword ptr [rsi], 0
0x1c00ec3e2  jz      short loc_1C00EC44D
0x1c00ec3e4  mov     rcx, [rdi+0BE8h]; this
0x1c00ec3eb  mov     r9, rsi; struct SmsContainer **
0x1c00ec3ee  mov     r8, [r14+18h]; unsigned __int64
0x1c00ec3f2  mov     rdx, rbp; struct CmsTransactionContext *
0x1c00ec3f5  mov     [rsp+78h+var_48], 0; unsigned __int8
0x1c00ec3fa  mov     [rsp+78h+var_50], 0; unsigned __int8
0x1c00ec3ff  mov     [rsp+78h+var_58], 1; unsigned __int8
0x1c00ec404  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c00ec409  test    eax, eax
0x1c00ec40b  js      short loc_1C00EC449
0x1c00ec40d  mov     rax, [rsi]
0x1c00ec410  xor     edx, edx; Tag
0x1c00ec412  lock dec dword ptr [rax+54h]
0x1c00ec416  lea     r8d, [rdx+20h]; RemlockSize
0x1c00ec41a  mov     rcx, [rdi+0BE8h]
0x1c00ec421  mov     rax, [rsi]
0x1c00ec424  add     rcx, 148h; RemoveLock
0x1c00ec42b  lock dec dword ptr [rax+58h]
0x1c00ec42f  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00ec436  nop     dword ptr [rax+rax+00h]
0x1c00ec43b  dec     dword ptr [rbp+0B08h]
0x1c00ec441  mov     rbx, [rsp+78h+arg_8]
0x1c00ec449  and     qword ptr [rsi], 0
0x1c00ec44d  lock inc dword ptr [rbx+54h]
0x1c00ec451  mov     rax, [rsp+78h+arg_8]
0x1c00ec459  lock inc dword ptr [rax+48h]
0x1c00ec45d  mov     rbx, [rsp+78h+arg_8]
0x1c00ec465  mov     edx, 2
0x1c00ec46a  lea     rcx, [rbx+68h]
0x1c00ec46e  call    cs:__imp_ExReleasePushLockEx
0x1c00ec475  nop     dword ptr [rax+rax+00h]
0x1c00ec47a  dec     dword ptr [rbp+0B0Ch]
0x1c00ec480  xor     edx, edx; Tag
0x1c00ec482  mov     rcx, [rdi+0BE8h]
0x1c00ec489  lock dec dword ptr [rbx+58h]
0x1c00ec48d  add     rcx, 148h; RemoveLock
0x1c00ec494  lea     r8d, [rdx+20h]; RemlockSize
0x1c00ec498  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00ec49f  nop     dword ptr [rax+rax+00h]
0x1c00ec4a4  dec     dword ptr [rbp+0B08h]
0x1c00ec4aa  mov     rax, [rsp+78h+arg_8]
0x1c00ec4b2  xor     ebx, ebx
0x1c00ec4b4  mov     [rsi], rax
0x1c00ec4b7  mov     [rsp+78h+arg_8], rbx
0x1c00ec4bf  mov     rax, [rax+228h]
0x1c00ec4c6  mov     [r14+18h], rax
0x1c00ec4ca  mov     rax, [rdi+0BE8h]
0x1c00ec4d1  mov     ecx, [rax+0E8h]
0x1c00ec4d7  imul    ecx, [rax+0E4h]
0x1c00ec4de  mov     rax, [rsi]
0x1c00ec4e1  movups  xmm0, xmmword ptr [rcx+rax+278h]
0x1c00ec4e9  movdqu  xmmword ptr [r13+0], xmm0
0x1c00ec4ef  mov     rax, [rsi]
0x1c00ec4f2  movsxd  rdx, dword ptr [rax+264h]
0x1c00ec4f9  mov     [r13+10h], rdx
0x1c00ec4fd  movsxd  rcx, dword ptr [rdi+50h]
0x1c00ec501  cmp     rdx, rcx
0x1c00ec504  jz      loc_1C00EC346
0x1c00ec50a  test    rbx, rbx
0x1c00ec50d  jz      short loc_1C00EC557
0x1c00ec50f  lea     rcx, [rbx+68h]
0x1c00ec513  mov     edx, 2
0x1c00ec518  call    cs:__imp_ExReleasePushLockEx
0x1c00ec51f  nop     dword ptr [rax+rax+00h]
0x1c00ec524  xor     edx, edx; Tag
0x1c00ec526  or      esi, 0FFFFFFFFh
0x1c00ec529  add     [rbp+0B0Ch], esi
0x1c00ec52f  mov     rcx, [rdi+0BE8h]
0x1c00ec536  lock dec dword ptr [rbx+58h]
0x1c00ec53a  add     rcx, 148h; RemoveLock
0x1c00ec541  lea     r8d, [rdx+20h]; RemlockSize
0x1c00ec545  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00ec54c  nop     dword ptr [rax+rax+00h]
0x1c00ec551  add     [rbp+0B08h], esi
0x1c00ec557  mov     rcx, [rsp+78h+arg_10]
0x1c00ec55f  xor     edx, edx
0x1c00ec561  call    cs:__imp_ExReleasePushLockEx
0x1c00ec568  nop     dword ptr [rax+rax+00h]
0x1c00ec56d  mov     rbx, [rsp+78h+arg_0]
0x1c00ec575  mov     eax, r12d
0x1c00ec578  add     rsp, 40h
0x1c00ec57c  pop     r15
0x1c00ec57e  pop     r14
0x1c00ec580  pop     r13
0x1c00ec582  pop     r12
0x1c00ec584  pop     rdi
0x1c00ec585  pop     rsi
0x1c00ec586  pop     rbp
0x1c00ec587  retn
```
