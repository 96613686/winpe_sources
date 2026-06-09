# MsAllocator::SmrStrategy::GetNextFreeSMRBand(CmsTransactionContext *,MsAllocator::SmrStrategy::State *,SmsContainer * *)

- ea: `0x1c00eb030`
- end: `0x1c00eb494`
- name: `?GetNextFreeSMRBand@SmrStrategy@MsAllocator@@CAJPEAVCmsTransactionContext@@PEAUState@12@PEAPEAUSmsContainer@@@Z`
- size: `1124`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, struct MsAllocator::SmrStrategy::State *, struct SmsContainer **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1c00ec2f0`

## callees

- `0x1c0024964`
- `0x1c0029630`
- `0x1c002b230`
- `0x1c002c7a0`
- `0x1c00663e8`
- `0x1c006a644`
- `0x1c006a684`
- `0x1c006ac80`
- `0x1c00eb030`
- `0x1c00ecf34`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1c00eb35c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00eb437`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00eb35c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00eb437`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x1c00eb231`
- `ntoskrnl!ExTryAcquirePushLockSharedEx` at `0x1c00eb231`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00eb267`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00eb389`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00eb466`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00eb267`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00eb389`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00eb466`

## pseudocode

```c
__int64 __fastcall MsAllocator::SmrStrategy::GetNextFreeSMRBand(
        struct CmsTransactionContext *a1,
        struct MsAllocator::SmrStrategy::State *a2,
        struct SmsContainer **a3)
{
  char v3; // r14
  struct CmsRowWithBuffer *v5; // rax
  struct CmsTransactionContext *v6; // rdx
  unsigned __int64 v7; // r9
  struct CmsContainerCursor **v8; // r10
  struct CmsContainerCursor *v9; // rbp
  struct CmsTableCursor **v10; // r13
  struct SmsContainer *v11; // rbx
  struct CmsRowWithBuffer *v12; // r15
  unsigned __int64 v13; // rsi
  __int64 v14; // rcx
  const struct _CmsRow *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r14
  int v18; // eax
  int ContainerReference; // eax
  struct CmsTransactionContext *v20; // rdx
  char v21; // al
  __int64 v22; // rcx
  int v23; // edx
  char *v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  char v30; // [rsp+88h] [rbp+10h]
  struct SmsContainer *v32; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v30 = 0;
  v5 = CmsTransactionContext::PopRow(a1);
  v9 = *v8;
  v10 = v8 + 4;
  v11 = 0;
  v12 = v5;
  v32 = 0;
  *((_QWORD *)v5 + 3) = 0;
  if ( v8[4] )
  {
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *))(**(_QWORD **)(*(_QWORD *)(*((_QWORD *)v9 + 381)
                                                                                             + 16LL)
                                                                                 + 48LL)
                                                                   + 152LL))(
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v9 + 381) + 16LL) + 48LL),
      a1);
    goto LABEL_6;
  }
  LODWORD(v13) = CmsVolumeContainer::CreateContainerEnumerateCursor(*((CmsVolumeContainer **)v9 + 381), v6, v8 + 4, v7);
  if ( (v13 & 0x80000000) != 0LL )
    goto LABEL_39;
  while ( 1 )
  {
LABEL_6:
    while ( 1 )
    {
      LODWORD(v13) = CmsFailoverBPlusTable::Enumerate(
                       *(CmsFailoverBPlusTable **)(*((_QWORD *)v9 + 381) + 16LL),
                       a1,
                       *v10,
                       *((_QWORD *)v12 + 3) != 0 ? 5 : 1,
                       v12,
                       0);
      if ( (v13 & 0x80000000) == 0LL )
        break;
      if ( (_DWORD)v13 != -1073741197 )
        goto LABEL_39;
      if ( v3 )
      {
        LODWORD(v13) = -1073741197;
        goto LABEL_39;
      }
      v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v9 + 381) + 16LL) + 48LL);
      (*(void (__fastcall **)(__int64, struct CmsTransactionContext *, struct CmsTableCursor *))(*(_QWORD *)v14 + 152LL))(
        v14,
        a1,
        *v10);
      CmsContainerCursor::ReInitializeCursor(*v10, v15);
      *((_QWORD *)v12 + 3) = 0;
      v3 = 1;
      v30 = 1;
    }
    v16 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v9 + 381) + 16LL) + 48LL);
    (*(void (__fastcall **)(__int64, struct CmsTransactionContext *, struct CmsTableCursor *))(*(_QWORD *)v16 + 152LL))(
      v16,
      a1,
      *v10);
    v17 = *((_QWORD *)v12 + 3);
    v13 = *(_QWORD *)v17;
    if ( !*(_DWORD *)(v17 + 60) )
    {
      v18 = *(_DWORD *)(v17 + 20);
      if ( (v18 & 8) == 0
        && (v18 & 0x400) == 0
        && (unsigned int)CmsVolume::GetStorageTierForRange(
                           v9,
                           a1,
                           v17
                         + (unsigned int)(*(_DWORD *)(*((_QWORD *)v9 + 381) + 228LL)
                                        * *(_DWORD *)(*((_QWORD *)v9 + 381) + 232LL))
                         + 80LL) == 7
        && (*(_DWORD *)(v17 + 20) & 0x40) == 0 )
      {
        break;
      }
    }
LABEL_5:
    v3 = v30;
  }
  ContainerReference = CmsVolumeContainer::GetContainerReference(
                         *((CmsVolumeContainer **)v9 + 381),
                         a1,
                         v13,
                         &v32,
                         0,
                         0,
                         0);
  v11 = v32;
  LODWORD(v13) = ContainerReference;
  if ( ContainerReference < 0 )
    goto LABEL_39;
  if ( *((_DWORD *)v32 + 25) || !(unsigned __int8)ExTryAcquirePushLockSharedEx((char *)v32 + 104, 2) )
  {
    v21 = 0;
  }
  else
  {
    ++*((_DWORD *)a1 + 707);
    v21 = 1;
  }
  v22 = *((_QWORD *)v9 + 381);
  if ( !v21 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v11 + 22);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v22 + 328), 0, 0x20u);
    --*((_DWORD *)a1 + 706);
LABEL_35:
    v11 = 0;
    v32 = 0;
    goto LABEL_5;
  }
  LODWORD(v13) = CmsVolumeContainer::QueryContainerWHAndType((CmsVolumeContainer *)v22, v20, v11);
  if ( (v13 & 0x80000000) != 0LL )
    goto LABEL_39;
  if ( (*((_BYTE *)v11 + 25) & 2) != 0 )
    goto LABEL_34;
  if ( *((_DWORD *)v11 + 153) )
    goto LABEL_34;
  v23 = *((_DWORD *)v11 + 143);
  if ( (v23 & 8) != 0 )
    goto LABEL_34;
  if ( (*(_DWORD *)(v17 + 20) & 0x400) != 0 )
    goto LABEL_34;
  v24 = (char *)v11 + 24;
  if ( (*((_BYTE *)v11 + 24) & 0x40) == 0 || (v23 & 0x40) != 0 )
    goto LABEL_34;
  v25 = *((_DWORD *)v11 + 10);
  v11 = v32;
  if ( v25 <= 0 )
    goto LABEL_38;
  if ( *v24 < 0 || byte_1C0136969 )
  {
    v13 = (int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))qword_1C0136AD0)(
                 *((_QWORD *)v9 + 6),
                 *(_QWORD *)((char *)v32
                           + (unsigned int)(*(_DWORD *)(*((_QWORD *)v9 + 381) + 228LL)
                                          * *(_DWORD *)(*((_QWORD *)v9 + 381) + 232LL))
                           + 632) << *((_DWORD *)v9 + 16),
                 (unsigned int)(*((_DWORD *)v9 + 17) * *((_DWORD *)v9 + 20)));
    SmsContainer::LogActivity(v11, 5, *((_QWORD *)v9 + 230), v13);
  }
  if ( (v13 & 0x80000000) != 0LL )
  {
LABEL_34:
    ExReleasePushLockEx((char *)v11 + 104, 2);
    --*((_DWORD *)a1 + 707);
    v26 = *((_QWORD *)v9 + 381);
    _InterlockedDecrement((volatile signed __int32 *)v11 + 22);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v26 + 328), 0, 0x20u);
    --*((_DWORD *)a1 + 706);
    goto LABEL_35;
  }
  *((_DWORD *)v11 + 10) = 0;
LABEL_38:
  *((_BYTE *)v11 + 25) |= 2u;
  *a3 = v11;
  v11 = 0;
  v32 = 0;
LABEL_39:
  v27 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v9 + 381) + 16LL) + 48LL);
  (*(void (__fastcall **)(__int64, struct CmsTransactionContext *, struct CmsTableCursor *))(*(_QWORD *)v27 + 152LL))(
    v27,
    a1,
    *v10);
  *(_DWORD *)v12 = 0;
  *((_DWORD *)a1 + 709) &= ~(1 << (((int)v12 - (int)a1 - 2888) / 0x70u));
  if ( v11 )
  {
    ExReleasePushLockEx((char *)v11 + 104, 2);
    --*((_DWORD *)a1 + 707);
    v28 = *((_QWORD *)v9 + 381);
    _InterlockedDecrement((volatile signed __int32 *)v11 + 22);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v28 + 328), 0, 0x20u);
    --*((_DWORD *)a1 + 706);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1c00eb030  mov     [rsp+arg_0], rbx
0x1c00eb035  mov     [rsp+arg_10], r8
0x1c00eb03a  push    rbp
0x1c00eb03b  push    rsi
0x1c00eb03c  push    rdi
0x1c00eb03d  push    r12
0x1c00eb03f  push    r13
0x1c00eb041  push    r14
0x1c00eb043  push    r15
0x1c00eb045  sub     rsp, 40h
0x1c00eb049  xor     r14b, r14b
0x1c00eb04c  mov     r10, rdx
0x1c00eb04f  mov     [rsp+78h+arg_8], r14b
0x1c00eb057  mov     rdi, rcx
0x1c00eb05a  call    ?PopRow@CmsTransactionContext@@QEAAPEAVCmsRowWithBuffer@@XZ; CmsTransactionContext::PopRow(void)
0x1c00eb05f  mov     rbp, [r10]
0x1c00eb062  lea     r13, [r10+20h]
0x1c00eb066  xor     ebx, ebx
0x1c00eb068  mov     r15, rax
0x1c00eb06b  mov     [rsp+78h+arg_18], rbx
0x1c00eb073  and     [rax+18h], rbx
0x1c00eb077  mov     r8, [r13+0]
0x1c00eb07b  mov     rax, [rbp+0BE8h]
0x1c00eb082  lea     r12d, [rbx+1]
0x1c00eb086  test    r8, r8
0x1c00eb089  jnz     short loc_1C00EB0A2
0x1c00eb08b  mov     r8, r13; struct CmsContainerCursor **
0x1c00eb08e  mov     rcx, rax; this
0x1c00eb091  call    ?CreateContainerEnumerateCursor@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAPEAVCmsContainerCursor@@_K@Z; CmsVolumeContainer::CreateContainerEnumerateCursor(CmsTransactionContext *,CmsContainerCursor * *,unsigned __int64)
0x1c00eb096  mov     esi, eax
0x1c00eb098  test    eax, eax
0x1c00eb09a  js      loc_1C00EB3CE
0x1c00eb0a0  jmp     short loc_1C00EB0C7
0x1c00eb0a2  mov     rax, [rax+10h]
0x1c00eb0a6  mov     rdx, rdi
0x1c00eb0a9  mov     rcx, [rax+30h]
0x1c00eb0ad  mov     rax, [rcx]
0x1c00eb0b0  mov     rax, [rax+98h]
0x1c00eb0b7  call    cs:__guard_dispatch_icall_fptr
0x1c00eb0bd  jmp     short loc_1C00EB0C7
0x1c00eb0bf  mov     r14b, [rsp+78h+arg_8]
0x1c00eb0c7  mov     rax, [rbp+0BE8h]
0x1c00eb0ce  mov     rdx, rdi; struct CmsTransactionContext *
0x1c00eb0d1  mov     r8, [r13+0]; struct CmsTableCursor *
0x1c00eb0d5  mov     [rsp+78h+var_50], 0; char
0x1c00eb0da  mov     [rsp+78h+var_58], r15; struct CmsRowWithBuffer *
0x1c00eb0df  mov     rcx, [rax+10h]; this
0x1c00eb0e3  mov     rax, [r15+18h]
0x1c00eb0e7  neg     rax
0x1c00eb0ea  sbb     r9d, r9d
0x1c00eb0ed  and     r9d, 4
0x1c00eb0f1  add     r9d, r12d; unsigned int
0x1c00eb0f4  call    ?Enumerate@CmsFailoverBPlusTable@@UEAAJPEAVCmsTransactionContext@@PEAVCmsTableCursor@@KPEAVCmsRowWithBuffer@@E@Z; CmsFailoverBPlusTable::Enumerate(CmsTransactionContext *,CmsTableCursor *,ulong,CmsRowWithBuffer *,uchar)
0x1c00eb0f9  mov     esi, eax
0x1c00eb0fb  test    eax, eax
0x1c00eb0fd  jns     short loc_1C00EB159
0x1c00eb0ff  mov     eax, 0C0000273h
0x1c00eb104  cmp     esi, eax
0x1c00eb106  jnz     loc_1C00EB3CE
0x1c00eb10c  test    r14b, r14b
0x1c00eb10f  jnz     loc_1C00EB3AA
0x1c00eb115  mov     rax, [rbp+0BE8h]
0x1c00eb11c  mov     rdx, rdi
0x1c00eb11f  mov     r8, [r13+0]
0x1c00eb123  mov     rcx, [rax+10h]
0x1c00eb127  mov     rcx, [rcx+30h]
0x1c00eb12b  mov     rax, [rcx]
0x1c00eb12e  mov     rax, [rax+98h]
0x1c00eb135  call    cs:__guard_dispatch_icall_fptr
0x1c00eb13b  mov     rcx, [r13+0]; this
0x1c00eb13f  call    ?ReInitializeCursor@CmsContainerCursor@@QEAAXPEBU_CmsRow@@@Z; CmsContainerCursor::ReInitializeCursor(_CmsRow const *)
0x1c00eb144  and     qword ptr [r15+18h], 0
0x1c00eb149  mov     r14b, r12b
0x1c00eb14c  mov     [rsp+78h+arg_8], r12b
0x1c00eb154  jmp     loc_1C00EB0C7
0x1c00eb159  mov     rax, [rbp+0BE8h]
0x1c00eb160  mov     rdx, rdi
0x1c00eb163  mov     r8, [r13+0]
0x1c00eb167  mov     rcx, [rax+10h]
0x1c00eb16b  mov     rcx, [rcx+30h]
0x1c00eb16f  mov     rax, [rcx]
0x1c00eb172  mov     rax, [rax+98h]
0x1c00eb179  call    cs:__guard_dispatch_icall_fptr
0x1c00eb17f  mov     r14, [r15+18h]
0x1c00eb183  cmp     dword ptr [r14+3Ch], 0
0x1c00eb188  mov     rsi, [r14]
0x1c00eb18b  jnz     loc_1C00EB0BF
0x1c00eb191  mov     eax, [r14+14h]
0x1c00eb195  test    al, 8
0x1c00eb197  jnz     loc_1C00EB0BF
0x1c00eb19d  bt      eax, 0Ah
0x1c00eb1a1  jb      loc_1C00EB0BF
0x1c00eb1a7  mov     rax, [rbp+0BE8h]
0x1c00eb1ae  mov     rdx, rdi
0x1c00eb1b1  mov     rcx, rbp
0x1c00eb1b4  mov     r8d, [rax+0E8h]
0x1c00eb1bb  imul    r8d, [rax+0E4h]
0x1c00eb1c3  add     r8, 50h ; 'P'
0x1c00eb1c7  add     r8, r14
0x1c00eb1ca  call    ?GetStorageTierForRange@CmsVolume@@QEAA?AW4_EMS_STORAGE_TIER_MEDIA_TYPE@@PEAVCmsTransactionCore@@PEBU_RANGE@@@Z; CmsVolume::GetStorageTierForRange(CmsTransactionCore *,_RANGE const *)
0x1c00eb1cf  cmp     eax, 7
0x1c00eb1d2  jnz     loc_1C00EB0BF
0x1c00eb1d8  mov     eax, [r14+14h]
0x1c00eb1dc  test    al, 40h
0x1c00eb1de  jnz     loc_1C00EB0BF
0x1c00eb1e4  mov     rcx, [rbp+0BE8h]; this
0x1c00eb1eb  lea     r9, [rsp+78h+arg_18]; struct SmsContainer **
0x1c00eb1f3  xor     ebx, ebx
0x1c00eb1f5  mov     r8, rsi; unsigned __int64
0x1c00eb1f8  mov     [rsp+78h+var_48], bl; unsigned __int8
0x1c00eb1fc  mov     rdx, rdi; struct CmsTransactionContext *
0x1c00eb1ff  mov     [rsp+78h+var_50], bl; unsigned __int8
0x1c00eb203  mov     byte ptr [rsp+78h+var_58], bl; unsigned __int8
0x1c00eb207  call    ?GetContainerReference@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@_KPEAPEAUSmsContainer@@EEE@Z; CmsVolumeContainer::GetContainerReference(CmsTransactionContext *,unsigned __int64,SmsContainer * *,uchar,uchar,uchar)
0x1c00eb20c  mov     rbx, [rsp+78h+arg_18]
0x1c00eb214  mov     esi, eax
0x1c00eb216  test    eax, eax
0x1c00eb218  js      loc_1C00EB3CE
0x1c00eb21e  cmp     dword ptr [rbx+64h], 0
0x1c00eb222  jz      short loc_1C00EB228
0x1c00eb224  xor     al, al
0x1c00eb226  jmp     short loc_1C00EB24B
0x1c00eb228  lea     rcx, [rbx+68h]
0x1c00eb22c  mov     edx, 2
0x1c00eb231  call    cs:__imp_ExTryAcquirePushLockSharedEx
0x1c00eb238  nop     dword ptr [rax+rax+00h]
0x1c00eb23d  test    al, al
0x1c00eb23f  jz      short loc_1C00EB224
0x1c00eb241  add     [rdi+0B0Ch], r12d
0x1c00eb248  mov     al, r12b
0x1c00eb24b  mov     rcx, [rbp+0BE8h]; this
0x1c00eb252  test    al, al
0x1c00eb254  jnz     short loc_1C00EB27E
0x1c00eb256  lock dec dword ptr [rbx+58h]
0x1c00eb25a  xor     edx, edx; Tag
0x1c00eb25c  add     rcx, 148h; RemoveLock
0x1c00eb263  lea     r8d, [rdx+20h]; RemlockSize
0x1c00eb267  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00eb26e  nop     dword ptr [rax+rax+00h]
0x1c00eb273  dec     dword ptr [rdi+0B08h]
0x1c00eb279  jmp     loc_1C00EB39B
0x1c00eb27e  mov     r8, rbx; struct SmsContainer *
0x1c00eb281  call    ?QueryContainerWHAndType@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@@Z; CmsVolumeContainer::QueryContainerWHAndType(CmsTransactionContext *,SmsContainer *)
0x1c00eb286  mov     esi, eax
0x1c00eb288  test    eax, eax
0x1c00eb28a  js      loc_1C00EB3CE
0x1c00eb290  test    byte ptr [rbx+19h], 2
0x1c00eb294  jnz     loc_1C00EB353
0x1c00eb29a  cmp     dword ptr [rbx+264h], 0
0x1c00eb2a1  jnz     loc_1C00EB353
0x1c00eb2a7  mov     edx, [rbx+23Ch]
0x1c00eb2ad  test    dl, 8
0x1c00eb2b0  jnz     loc_1C00EB353
0x1c00eb2b6  test    dword ptr [r14+14h], 400h
0x1c00eb2be  jnz     loc_1C00EB353
0x1c00eb2c4  lea     rcx, [rbx+18h]
0x1c00eb2c8  test    byte ptr [rcx], 40h
0x1c00eb2cb  jz      loc_1C00EB353
0x1c00eb2d1  test    dl, 40h
0x1c00eb2d4  jnz     short loc_1C00EB353
0x1c00eb2d6  mov     eax, [rbx+28h]
0x1c00eb2d9  mov     rbx, [rsp+78h+arg_18]
0x1c00eb2e1  test    eax, eax
0x1c00eb2e3  jle     loc_1C00EB3B5
0x1c00eb2e9  cmp     byte ptr [rcx], 0
0x1c00eb2ec  jl      short loc_1C00EB2F7
0x1c00eb2ee  cmp     cs:byte_1C0136969, 0
0x1c00eb2f5  jz      short loc_1C00EB34F
0x1c00eb2f7  mov     rdx, [rbp+0BE8h]
0x1c00eb2fe  mov     r8d, [rbp+50h]
0x1c00eb302  imul    r8d, [rbp+44h]
0x1c00eb307  mov     rax, cs:qword_1C0136AD0
0x1c00eb30e  mov     ecx, [rdx+0E8h]
0x1c00eb314  imul    ecx, [rdx+0E4h]
0x1c00eb31b  mov     edx, ecx
0x1c00eb31d  mov     ecx, [rbp+40h]
0x1c00eb320  mov     rdx, [rdx+rbx+278h]
0x1c00eb328  shl     rdx, cl
0x1c00eb32b  mov     rcx, [rbp+30h]
0x1c00eb32f  call    cs:__guard_dispatch_icall_fptr
0x1c00eb335  mov     r8, [rbp+730h]
0x1c00eb33c  mov     edx, 5
0x1c00eb341  movsxd  rsi, eax
0x1c00eb344  mov     rcx, rbx
0x1c00eb347  mov     r9, rsi
0x1c00eb34a  call    ?LogActivity@SmsContainer@@QEAAXW4EMS_BAND_ACTIVITY@@_K1@Z; SmsContainer::LogActivity(EMS_BAND_ACTIVITY,unsigned __int64,unsigned __int64)
0x1c00eb34f  test    esi, esi
0x1c00eb351  jns     short loc_1C00EB3AE
0x1c00eb353  lea     rcx, [rbx+68h]
0x1c00eb357  mov     edx, 2
0x1c00eb35c  call    cs:__imp_ExReleasePushLockEx
0x1c00eb363  nop     dword ptr [rax+rax+00h]
0x1c00eb368  xor     edx, edx; Tag
0x1c00eb36a  or      esi, 0FFFFFFFFh
0x1c00eb36d  add     [rdi+0B0Ch], esi
0x1c00eb373  mov     rcx, [rbp+0BE8h]
0x1c00eb37a  lock dec dword ptr [rbx+58h]
0x1c00eb37e  add     rcx, 148h; RemoveLock
0x1c00eb385  lea     r8d, [rdx+20h]; RemlockSize
0x1c00eb389  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00eb390  nop     dword ptr [rax+rax+00h]
0x1c00eb395  add     [rdi+0B08h], esi
0x1c00eb39b  xor     ebx, ebx
0x1c00eb39d  mov     [rsp+78h+arg_18], rbx
0x1c00eb3a5  jmp     loc_1C00EB0BF
0x1c00eb3aa  mov     esi, eax
0x1c00eb3ac  jmp     short loc_1C00EB3CE
0x1c00eb3ae  mov     dword ptr [rbx+28h], 0
0x1c00eb3b5  mov     rax, [rsp+78h+arg_10]
0x1c00eb3bd  or      byte ptr [rbx+19h], 2
0x1c00eb3c1  mov     [rax], rbx
0x1c00eb3c4  xor     ebx, ebx
0x1c00eb3c6  mov     [rsp+78h+arg_18], rbx
0x1c00eb3ce  mov     rax, [rbp+0BE8h]
0x1c00eb3d5  mov     rdx, rdi
0x1c00eb3d8  mov     r8, [r13+0]
0x1c00eb3dc  mov     rcx, [rax+10h]
0x1c00eb3e0  mov     rcx, [rcx+30h]
0x1c00eb3e4  mov     rax, [rcx]
0x1c00eb3e7  mov     rax, [rax+98h]
0x1c00eb3ee  call    cs:__guard_dispatch_icall_fptr
0x1c00eb3f4  and     dword ptr [r15], 0
0x1c00eb3f8  mov     rax, 2492492492492493h
0x1c00eb402  sub     r15d, edi
0x1c00eb405  lea     ecx, [r15-0B48h]
0x1c00eb40c  mul     rcx
0x1c00eb40f  sub     rcx, rdx
0x1c00eb412  shr     rcx, 1
0x1c00eb415  add     rcx, rdx
0x1c00eb418  shr     rcx, 6
0x1c00eb41c  shl     r12d, cl
0x1c00eb41f  not     r12d
0x1c00eb422  and     [rdi+0B14h], r12d
0x1c00eb429  test    rbx, rbx
0x1c00eb42c  jz      short loc_1C00EB479
0x1c00eb42e  lea     rcx, [rbx+68h]
0x1c00eb432  mov     edx, 2
0x1c00eb437  call    cs:__imp_ExReleasePushLockEx
0x1c00eb43e  nop     dword ptr [rax+rax+00h]
0x1c00eb443  xor     edx, edx; Tag
0x1c00eb445  or      r14d, 0FFFFFFFFh
0x1c00eb449  add     [rdi+0B0Ch], r14d
0x1c00eb450  mov     rcx, [rbp+0BE8h]
0x1c00eb457  lock dec dword ptr [rbx+58h]
0x1c00eb45b  add     rcx, 148h; RemoveLock
0x1c00eb462  lea     r8d, [rdx+20h]; RemlockSize
0x1c00eb466  call    cs:__imp_IoReleaseRemoveLockEx
0x1c00eb46d  nop     dword ptr [rax+rax+00h]
0x1c00eb472  add     [rdi+0B08h], r14d
0x1c00eb479  mov     rbx, [rsp+78h+arg_0]
0x1c00eb481  mov     eax, esi
0x1c00eb483  add     rsp, 40h
0x1c00eb487  pop     r15
0x1c00eb489  pop     r14
0x1c00eb48b  pop     r13
0x1c00eb48d  pop     r12
0x1c00eb48f  pop     rdi
0x1c00eb490  pop     rsi
0x1c00eb491  pop     rbp
0x1c00eb492  retn
```
