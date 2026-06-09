# NtfsCreateInternalAttributeStream

- ea: `0x140163f78`
- end: `0x14016464c`
- name: `NtfsCreateInternalAttributeStream`
- size: `1748`
- prototype: ``
- caller_count: `55`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x14000a230`
- `0x1400177d0`
- `0x14002c840`
- `0x1400bb020`
- `0x1400cc78c`
- `0x1400cf580`
- `0x1400d2740`
- `0x1400ddcb8`
- `0x1400ff294`
- `0x140100f30`
- `0x140103260`
- `0x140106838`
- `0x140109e58`
- `0x14010adfc`
- `0x14010be3c`
- `0x1401101f8`
- `0x140113760`
- `0x140123350`
- `0x140125f70`
- `0x140134a58`
- `0x1401436e0`
- `0x140145d8c`
- `0x14014e7b4`
- `0x14014ecf0`
- `0x14014fff4`
- `0x1401578a0`
- `0x1401580e0`
- `0x14015b8b0`
- `0x14015d274`
- `0x14015eaa0`
- `0x140162370`
- `0x140163ab0`
- `0x1401649f4`
- `0x1401657cc`
- `0x140175a80`
- `0x1401919d0`
- `0x140194c68`
- `0x1401ba6f4`
- `0x1401bf530`
- `0x1401e7e28`
- `0x1401ea058`
- `0x1401f63f8`
- `0x140211c20`
- `0x140248584`
- `0x14024a594`
- `0x14025cc9c`
- `0x140260138`
- `0x140263828`
- `0x14026fae8`
- `0x140278d84`

## callees

- `0x14000a600`
- `0x14001e810`
- `0x140023250`
- `0x140025a90`
- `0x140059250`
- `0x140159768`
- `0x140163f78`
- `0x140164660`
- `0x140164bd0`
- `0x140166514`
- `0x1401f28f0`
- `0x14023c2e4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140164069`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140164069`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a9217`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a9217`
- `ntoskrnl!IoCreateStreamFileObjectEx` at `0x140164400`
- `ntoskrnl!IoCreateStreamFileObjectEx` at `0x140164400`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x1401640a4`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x1401640a4`
- `ntoskrnl!IoUpdateShareAccess` at `0x140164559`
- `ntoskrnl!IoUpdateShareAccess` at `0x140164559`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1401642b5`
- `ntoskrnl!CcSetParallelFlushFile` at `0x1401642b5`
- `ntoskrnl!CcSetLogHandleForFileEx` at `0x140164214`
- `ntoskrnl!CcSetLogHandleForFileEx` at `0x140164214`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402a91bf`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402a91bf`
- `ntoskrnl!ZwClose` at `0x1402a91d5`
- `ntoskrnl!ZwClose` at `0x1402a91d5`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401641b5`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x1401641b5`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14016418c`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14016418c`
- `ntoskrnl!ExReleasePushLockEx` at `0x140164632`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a9260`
- `ntoskrnl!ExReleasePushLockEx` at `0x140164632`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a9260`
- `ntoskrnl!ExReleaseResourceLite` at `0x14016453b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14016453b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140164046`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140164046`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401644ea`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401644ea`

## pseudocode

```c
void *__fastcall NtfsCreateInternalAttributeStream(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        __int64 a5,
        PFILE_OBJECT *a6)
{
  __int64 v8; // r15
  PFILE_OBJECT *v9; // r12
  __int64 v10; // rax
  char v11; // r14
  __int64 Ccb; // r13
  char v13; // di
  BOOLEAN IsResourceAcquiredExclusiveLite; // al
  SECTION_OBJECT_POINTERS *v15; // r11
  PFILE_OBJECT StreamFileObjectLite; // rdi
  UNICODE_STRING *p_FileName; // r8
  int v18; // r8d
  __int64 v19; // rcx
  __int64 v20; // r8
  char v21; // r8
  int v22; // r9d
  __int64 v23; // r14
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // edx
  __int64 v27; // rax
  bool v28; // si
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // r12d
  int v32; // r15d
  int v33; // eax
  int v34; // r8d
  int v35; // ecx
  int v36; // eax
  char v38; // [rsp+40h] [rbp-98h]
  char v39; // [rsp+41h] [rbp-97h]
  void *FileHandle; // [rsp+58h] [rbp-80h] BYREF
  int v43; // [rsp+60h] [rbp-78h]
  int v44; // [rsp+64h] [rbp-74h]
  char v45; // [rsp+68h] [rbp-70h]
  __int64 v46; // [rsp+70h] [rbp-68h]
  PFILE_OBJECT *v47; // [rsp+78h] [rbp-60h]
  __int64 v48; // [rsp+80h] [rbp-58h]
  __int64 v49; // [rsp+88h] [rbp-50h] BYREF
  __int128 v50; // [rsp+90h] [rbp-48h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-38h]

  v8 = a1;
  v48 = a2;
  v9 = a6;
  v47 = a6;
  v46 = *(_QWORD *)(a2 + 192);
  v49 = 0;
  v50 = 0;
  v51 = 0;
  FileHandle = 0;
  v45 = a4 & 4;
  if ( (a4 & 4) != 0 )
  {
    *a6 = 0;
    v10 = 0;
  }
  else
  {
    v9 = (PFILE_OBJECT *)(a2 + 280);
    v47 = (PFILE_OBJECT *)(a2 + 280);
    v10 = *(_QWORD *)(a2 + 280);
  }
  v11 = a4 & 2;
  if ( v10 && !v11 )
    return FileHandle;
  Ccb = 0;
  v13 = 0;
  v38 = 0;
  v39 = 0;
  IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a2 + 184)
                                                                                             + 104LL)
                                                                                 + 64LL));
  LOBYTE(v15) = 0;
  if ( !IsResourceAcquiredExclusiveLite )
  {
    ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 184) + 200LL, 0);
    v39 = 1;
    LOBYTE(v15) = 0;
  }
  if ( !*v9 || v11 )
  {
    if ( v11 )
    {
      v31 = -2147483640;
      v44 = -2147483640;
      v32 = 0;
      v43 = 0;
      if ( (*(_DWORD *)(a1 + 436) & 0x80008) != 0 )
        v32 = 2;
      v43 = v32;
      StreamFileObjectLite = IoCreateStreamFileObjectEx(
                               0,
                               *(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(a2 + 192) + 248LL) + 16LL),
                               &FileHandle);
      v33 = *(_DWORD *)(a2 + 256);
      v34 = 160;
      if ( v33 == 160 || !*(_WORD *)(a2 + 264) )
      {
        v31 = -2147483638;
        v44 = -2147483638;
      }
      LOBYTE(v34) = v33 == 160;
      Ccb = NtfsCreateCcb(
              *(_QWORD *)(a2 + 184),
              a2,
              v34,
              *(unsigned __int16 *)(*(_QWORD *)(a2 + 184) + 34LL),
              v31,
              (__int64)StreamFileObjectLite,
              0,
              (__int64)&v49);
      SetFlagInterlocked(Ccb + 8, v32 | 4u);
      v8 = a1;
      if ( (*(_DWORD *)(*(_QWORD *)(a2 + 184) + 4LL) & 8) == 0 )
        NtfsUpdateFcbInfoFromDisk(a1, 0, 0);
      v9 = v47;
    }
    else
    {
      StreamFileObjectLite = IoCreateStreamFileObjectLite(
                               0,
                               *(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(a2 + 192) + 248LL) + 16LL));
    }
    *(_DWORD *)(a2 + 200) &= ~0x4000u;
    p_FileName = &StreamFileObjectLite->FileName;
    if ( a5 )
    {
      StreamFileObjectLite->FileName.MaximumLength = *(_WORD *)(a5 + 2);
      p_FileName->Length = *(_WORD *)a5;
      StreamFileObjectLite->FileName.Buffer = *(PWSTR *)(a5 + 8);
    }
    else if ( (unsigned __int8)NtfsBuildInternalAttributeStreamName(v8, a2, p_FileName) )
    {
      *(_DWORD *)(a2 + 200) |= 0x4000u;
    }
    if ( (*(_DWORD *)(a2 + 512) & 0x20) == 0 )
    {
      v29 = *(_QWORD *)(v8 + 112);
      if ( v29 )
      {
        v30 = *(_QWORD *)(*(_QWORD *)(v29 + 184) + 48LL);
        if ( v30 )
          StreamFileObjectLite->Flags |= *(_DWORD *)(v30 + 80) & 0x8020;
      }
    }
    if ( Ccb )
      v18 = (*(_DWORD *)(a2 + 256) != 128) + 2;
    else
      v18 = 5;
    NtfsSetFileObject(v8, (_DWORD)StreamFileObjectLite, v18, a2, Ccb);
    StreamFileObjectLite->ReadAccess = 1;
    if ( v45 )
    {
      ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 528) + 64LL) + 136LL), 1u);
      StreamFileObjectLite->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)(**(_QWORD **)(*(_QWORD *)(a2 + 528) + 112LL)
                                                                            + 16LL);
      _InterlockedIncrement((volatile signed __int32 *)(**(_QWORD **)(*(_QWORD *)(a2 + 528) + 112LL) + 64LL));
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 288) + 64LL));
      ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 528) + 64LL) + 136LL));
    }
    StreamFileObjectLite->WriteAccess = 1;
    *(_WORD *)&StreamFileObjectLite->SharedRead = 257;
    StreamFileObjectLite->SharedDelete = 1;
    if ( Ccb )
    {
      IoUpdateShareAccess(StreamFileObjectLite, (PSHARE_ACCESS)(a2 + 228));
      if ( *(int *)(Ccb + 4) >= 0 || (v36 = 1, (*(_DWORD *)(Ccb + 8) & 2) != 0) )
        v36 = 0;
      NtfsIncrementCleanupCounts(v35, a2, 0, 0, v36);
    }
    LOBYTE(v20) = 1;
    NtfsIncrementCloseCounts(v19, a2, v20, 0);
    if ( v11 )
    {
      if ( StreamFileObjectLite->SectionObjectPointer == v15 )
        goto LABEL_30;
      NtfsUpdateBackingFileObject(StreamFileObjectLite, ChangeDataControlArea);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 208));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 184) + 20LL));
      v38 = v21;
      if ( a3 != (_BYTE)v15 && (*(_DWORD *)(a2 + 200) & 0x20) == 0 )
        NtfsUpdateScbFromAttribute(v8, a2, 0);
      FsRtlAcquireHeaderMutex(a2 + 120, a2 + 160);
      *(_BYTE *)(a2 + 6) &= ~1u;
      if ( (*(_DWORD *)(a2 + 512) & 0x20) == 0 && (*(_BYTE *)(a2 + 6) & 1) == 0 )
        *(_BYTE *)(a2 + 6) |= 1u;
      FsRtlReleaseHeaderMutex(a2 + 120, a2 + 160);
      if ( (a4 & 0x10) == 0 )
      {
        if ( StreamFileObjectLite->PrivateCacheMap )
        {
          v23 = v46;
        }
        else
        {
          v50 = *(_OWORD *)(a2 + 24);
          v26 = *(_DWORD *)(a2 + 512);
          v27 = *(_QWORD *)(a2 + 40);
          if ( (v26 & 0x20) != 0 )
            v27 = 0x7FFFFFFFFFFFFFFFLL;
          v51 = v27;
          v28 = *(_DWORD *)(a2 + 256) != 128
             || (*(_DWORD *)(*(_QWORD *)(a2 + 184) + 4LL) & 0x80104) != 0
             || (*(_DWORD *)(*(_QWORD *)(a2 + 192) + 4LL) & 0x10) != 0
             || (a4 & 8) != 0;
          v23 = v46;
          if ( (v26 & 1) != 0 )
          {
            *(_QWORD *)&v50 = v50 - *(_QWORD *)(v46 + 1952);
            *((_QWORD *)&v50 + 1) -= *(_QWORD *)(v46 + 1952);
          }
          LOBYTE(v22) = v28;
          NtfsInitializeCacheMap(a1, (_DWORD)StreamFileObjectLite, (unsigned int)&v50, v22, a2);
          NtfsUpdateBackingFileObject(StreamFileObjectLite, ChangeSharedCacheMap);
          CcSetParallelFlushFile(StreamFileObjectLite, 1u);
        }
        if ( (*(_DWORD *)(a2 + 512) & 0x20) != 0 )
        {
          v24 = *(_QWORD *)(v23 + 64);
          if ( a2 != v24 )
          {
            if ( v24 )
              v25 = *(_QWORD *)(v24 + 280);
            else
              v25 = 0;
            CcSetLogHandleForFileEx(
              StreamFileObjectLite,
              *(_QWORD *)(v23 + 232),
              LfsFlushToLsn,
              NtfsQueryLogFileUsage,
              v25);
          }
        }
      }
      *v9 = StreamFileObjectLite;
    }
    LOBYTE(v15) = 0;
LABEL_30:
    v13 = v38;
  }
  if ( v13 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(a2 + 208));
    _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a2 + 184) + 20LL));
  }
  if ( v39 != (_BYTE)v15 )
    ExReleasePushLockEx(*(_QWORD *)(a2 + 184) + 200LL, 0);
  return FileHandle;
}

```

## disassembly

```asm
0x140163f78  mov     r11, rsp
0x140163f7b  mov     [r11+18h], rbx
0x140163f7f  mov     [r11+20h], rsi
0x140163f83  push    rdi
0x140163f84  push    r12
0x140163f86  push    r13
0x140163f88  push    r14
0x140163f8a  push    r15
0x140163f8c  sub     rsp, 0B0h
0x140163f93  mov     rax, cs:__security_cookie
0x140163f9a  xor     rax, rsp
0x140163f9d  mov     [rsp+0D8h+var_30], rax
0x140163fa5  mov     sil, r9b
0x140163fa8  mov     [rsp+0D8h+var_95], r8b
0x140163fad  mov     rbx, rdx
0x140163fb0  mov     r15, rcx
0x140163fb3  mov     qword ptr [rsp+0D8h+var_88], rcx
0x140163fb8  mov     [rsp+0D8h+var_58], rdx
0x140163fc0  mov     r12, [rsp+0D8h+arg_28]
0x140163fc8  mov     [rsp+0D8h+var_60], r12
0x140163fcd  mov     rax, [rdx+0C0h]
0x140163fd4  mov     [rsp+0D8h+var_68], rax
0x140163fd9  xor     ecx, ecx
0x140163fdb  mov     [r11-50h], rcx
0x140163fdf  xorps   xmm0, xmm0
0x140163fe2  xor     eax, eax
0x140163fe4  movups  xmmword ptr [r11-48h], xmm0
0x140163fe9  mov     [r11-38h], rax
0x140163fed  mov     [r11-80h], rcx
0x140163ff1  mov     al, r9b
0x140163ff4  and     al, 4
0x140163ff6  mov     [rsp+0D8h+var_70], al
0x140163ffa  jnz     loc_140164640
0x140164000  lea     r12, [rdx+118h]
0x140164007  mov     [rsp+0D8h+var_60], r12
0x14016400c  mov     rax, [r12]
0x140164010  mov     r14b, sil
0x140164013  and     r14b, 2
0x140164017  test    rax, rax
0x14016401a  jnz     loc_140164618
0x140164020  mov     r13, rcx
0x140164023  mov     [rsp+0D8h+var_90], rcx
0x140164028  mov     [rsp+0D8h+var_96], cl
0x14016402c  mov     dil, cl
0x14016402f  mov     [rsp+0D8h+var_98], cl
0x140164033  mov     [rsp+0D8h+var_97], cl
0x140164037  mov     rax, [rdx+0B8h]
0x14016403e  mov     rcx, [rax+68h]
0x140164042  add     rcx, 40h ; '@'; Resource
0x140164046  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14016404d  nop     dword ptr [rax+rax+00h]
0x140164052  xor     r11d, r11d
0x140164055  test    al, al
0x140164057  jnz     short loc_14016407D
0x140164059  mov     rcx, [rbx+0B8h]
0x140164060  add     rcx, 0C8h
0x140164067  xor     edx, edx
0x140164069  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140164070  nop     dword ptr [rax+rax+00h]
0x140164075  mov     [rsp+0D8h+var_97], 1
0x14016407a  xor     r11d, r11d
0x14016407d  cmp     [r12], r11
0x140164081  jnz     loc_1401643A9
0x140164087  test    r14b, r14b
0x14016408a  jnz     loc_1401643B7
0x140164090  mov     rax, [rbx+0C0h]
0x140164097  mov     rdx, [rax+0F8h]
0x14016409e  mov     rdx, [rdx+10h]; DeviceObject
0x1401640a2  xor     ecx, ecx; FileObject
0x1401640a4  call    cs:__imp_IoCreateStreamFileObjectLite
0x1401640ab  nop     dword ptr [rax+rax+00h]
0x1401640b0  mov     rdi, rax
0x1401640b3  mov     [rsp+0D8h+var_90], rax
0x1401640b8  btr     dword ptr [rbx+0C8h], 0Eh
0x1401640c0  lea     r8, [rdi+58h]
0x1401640c4  mov     rcx, [rsp+0D8h+arg_20]
0x1401640cc  test    rcx, rcx
0x1401640cf  jz      loc_140164387
0x1401640d5  movzx   eax, word ptr [rcx+2]
0x1401640d9  mov     [rdi+5Ah], ax
0x1401640dd  movzx   eax, word ptr [rcx]
0x1401640e0  mov     [r8], ax
0x1401640e4  mov     rax, [rcx+8]
0x1401640e8  mov     [rdi+60h], rax
0x1401640ec  xor     ecx, ecx
0x1401640ee  mov     eax, [rbx+200h]
0x1401640f4  test    al, 20h
0x1401640f6  jz      loc_1401642C8
0x1401640fc  test    r13, r13
0x1401640ff  jnz     loc_1401644BC
0x140164105  lea     r8d, [r13+5]
0x140164109  mov     [rsp+0D8h+var_B8], r13
0x14016410e  mov     r9, rbx
0x140164111  mov     rdx, rdi
0x140164114  mov     rcx, r15
0x140164117  call    NtfsSetFileObject
0x14016411c  mov     byte ptr [rdi+4Ah], 1
0x140164120  xor     r11d, r11d
0x140164123  cmp     [rsp+0D8h+var_70], r11b
0x140164128  jnz     loc_1401644D6
0x14016412e  mov     byte ptr [rdi+4Bh], 1
0x140164132  mov     word ptr [rdi+4Dh], 101h
0x140164138  mov     byte ptr [rdi+4Fh], 1
0x14016413c  test    r13, r13
0x14016413f  jnz     loc_14016454F
0x140164145  xor     r9d, r9d
0x140164148  mov     r8b, 1
0x14016414b  mov     rdx, rbx
0x14016414e  call    NtfsIncrementCloseCounts
0x140164153  test    r14b, r14b
0x140164156  jnz     loc_14016436E
0x14016415c  lock inc dword ptr [rbx+0D0h]
0x140164163  mov     rax, [rbx+0B8h]
0x14016416a  lock inc dword ptr [rax+14h]
0x14016416e  mov     [rsp+0D8h+var_98], r8b
0x140164173  cmp     [rsp+0D8h+var_95], r11b
0x140164178  jnz     loc_1401642F9
0x14016417e  lea     r14, [rbx+0A0h]
0x140164185  mov     rdx, r14
0x140164188  lea     rcx, [rbx+78h]
0x14016418c  call    cs:__imp_FsRtlAcquireHeaderMutex
0x140164193  nop     dword ptr [rax+rax+00h]
0x140164198  mov     al, [rbx+6]
0x14016419b  and     al, 0FEh
0x14016419d  mov     [rbx+6], al
0x1401641a0  mov     eax, [rbx+200h]
0x1401641a6  test    al, 20h
0x1401641a8  jz      loc_140164356
0x1401641ae  mov     rdx, r14
0x1401641b1  lea     rcx, [rbx+78h]
0x1401641b5  call    cs:__imp_FsRtlReleaseHeaderMutex
0x1401641bc  nop     dword ptr [rax+rax+00h]
0x1401641c1  test    sil, 10h
0x1401641c5  jnz     short loc_140164220
0x1401641c7  xor     ecx, ecx
0x1401641c9  cmp     [rdi+30h], rcx
0x1401641cd  jz      short loc_140164231
0x1401641cf  mov     r14, [rsp+0D8h+var_68]
0x1401641d4  mov     eax, [rbx+200h]
0x1401641da  test    al, 20h
0x1401641dc  jz      short loc_140164220
0x1401641de  mov     rax, [r14+40h]
0x1401641e2  cmp     rbx, rax
0x1401641e5  jz      short loc_140164220
0x1401641e7  test    rax, rax
0x1401641ea  jz      loc_14016434E
0x1401641f0  mov     rax, [rax+118h]
0x1401641f7  mov     [rsp+0D8h+var_B8], rax
0x1401641fc  lea     r9, NtfsQueryLogFileUsage
0x140164203  lea     r8, LfsFlushToLsn
0x14016420a  mov     rdx, [r14+0E8h]
0x140164211  mov     rcx, rdi
0x140164214  call    cs:__imp_CcSetLogHandleForFileEx
0x14016421b  nop     dword ptr [rax+rax+00h]
0x140164220  mov     [r12], rdi
0x140164224  xor     r11d, r11d
0x140164227  mov     dil, [rsp+0D8h+var_98]
0x14016422c  jmp     loc_1401645C7
0x140164231  movups  xmm0, xmmword ptr [rbx+18h]
0x140164235  movups  [rsp+0D8h+var_48], xmm0
0x14016423d  mov     edx, [rbx+200h]
0x140164243  test    dl, 20h
0x140164246  mov     rax, [rbx+28h]
0x14016424a  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140164254  cmovnz  rax, rcx
0x140164258  mov     [rsp+0D8h+var_38], rax
0x140164260  cmp     dword ptr [rbx+100h], 80h
0x14016426a  jz      loc_14016431A
0x140164270  mov     sil, 1
0x140164273  mov     r14, [rsp+0D8h+var_68]
0x140164278  test    dl, 1
0x14016427b  jnz     loc_140164594
0x140164281  mov     [rsp+0D8h+var_B8], rbx
0x140164286  mov     r9b, sil
0x140164289  lea     r8, [rsp+0D8h+var_48]
0x140164291  mov     rdx, rdi
0x140164294  mov     rcx, qword ptr [rsp+0D8h+var_88]
0x140164299  call    NtfsInitializeCacheMap
0x14016429e  mov     [rsp+0D8h+var_96], 1
0x1401642a3  mov     edx, 2; ChangeBackingType
0x1401642a8  mov     rcx, rdi; NewFileObject
0x1401642ab  call    NtfsUpdateBackingFileObject
0x1401642b0  mov     dl, 1; EnableParallelFlush
0x1401642b2  mov     rcx, rdi; FileObject
0x1401642b5  call    cs:__imp_CcSetParallelFlushFile
0x1401642bc  nop     dword ptr [rax+rax+00h]
0x1401642c1  xor     ecx, ecx
0x1401642c3  jmp     loc_1401641D4
0x1401642c8  mov     rax, [r15+70h]
0x1401642cc  test    rax, rax
0x1401642cf  jz      loc_1401640FC
0x1401642d5  mov     rax, [rax+0B8h]
0x1401642dc  mov     rax, [rax+30h]
0x1401642e0  test    rax, rax
0x1401642e3  jz      loc_1401640FC
0x1401642e9  mov     eax, [rax+50h]
0x1401642ec  and     eax, 8020h
0x1401642f1  or      [rdi+50h], eax
0x1401642f4  jmp     loc_1401640FC
0x1401642f9  mov     eax, [rbx+0C8h]
0x1401642ff  test    al, 20h
0x140164301  jnz     loc_14016417E
0x140164307  xor     r8d, r8d
0x14016430a  mov     rdx, rbx
0x14016430d  mov     rcx, r15
0x140164310  call    NtfsUpdateScbFromAttribute
0x140164315  jmp     loc_14016417E
0x14016431a  mov     rax, [rbx+0B8h]
0x140164321  test    dword ptr [rax+4], 80104h
0x140164328  jnz     loc_140164270
0x14016432e  mov     rax, [rbx+0C0h]
0x140164335  mov     ecx, [rax+4]
0x140164338  test    cl, 10h
0x14016433b  jnz     loc_140164270
0x140164341  shr     sil, 3
0x140164345  and     sil, 1
0x140164349  jmp     loc_140164273
0x14016434e  mov     rax, rcx
0x140164351  jmp     loc_1401641F7
0x140164356  mov     al, [rbx+6]
0x140164359  test    al, 1
0x14016435b  jnz     loc_1401641AE
0x140164361  mov     al, [rbx+6]
0x140164364  or      al, 1
0x140164366  mov     [rbx+6], al
0x140164369  jmp     loc_1401641AE
0x14016436e  cmp     [rdi+28h], r11
0x140164372  jz      loc_140164227
0x140164378  xor     edx, edx; ChangeBackingType
0x14016437a  mov     rcx, rdi; NewFileObject
0x14016437d  call    NtfsUpdateBackingFileObject
0x140164382  jmp     loc_140164224
0x140164387  mov     rdx, rbx
0x14016438a  mov     rcx, r15
0x14016438d  call    NtfsBuildInternalAttributeStreamName
0x140164392  xor     ecx, ecx
0x140164394  test    al, al
0x140164396  jz      loc_1401640EE
0x14016439c  bts     dword ptr [rbx+0C8h], 0Eh
0x1401643a4  jmp     loc_1401640EE
0x1401643a9  test    r14b, r14b
0x1401643ac  jz      loc_1401645C7
0x1401643b2  jmp     loc_140164087
0x1401643b7  mov     r12d, 80000008h
0x1401643bd  mov     [rsp+0D8h+var_74], r12d
0x1401643c2  mov     r15d, r11d
0x1401643c5  mov     [rsp+0D8h+var_78], r11d
0x1401643ca  mov     rcx, qword ptr [rsp+0D8h+var_88]
0x1401643cf  test    dword ptr [rcx+1B4h], 80008h
0x1401643d9  mov     eax, 2
0x1401643de  cmovnz  r15d, eax
0x1401643e2  mov     [rsp+0D8h+var_78], r15d
0x1401643e7  mov     rax, [rbx+0C0h]
0x1401643ee  mov     rdx, [rax+0F8h]
0x1401643f5  lea     r8, [rsp+0D8h+FileHandle]; FileHandle
0x1401643fa  mov     rdx, [rdx+10h]; DeviceObject
0x1401643fe  xor     ecx, ecx; FileObject
0x140164400  call    cs:__imp_IoCreateStreamFileObjectEx
0x140164407  nop     dword ptr [rax+rax+00h]
0x14016440c  mov     rdi, rax
0x14016440f  mov     [rsp+0D8h+var_90], rax
0x140164414  mov     eax, [rbx+100h]
0x14016441a  mov     r8d, 0A0h
0x140164420  xor     edx, edx
0x140164422  cmp     eax, r8d
0x140164425  jz      short loc_140164430
0x140164427  cmp     [rbx+108h], dx
0x14016442e  jnz     short loc_14016443B
0x140164430  mov     r12d, 8000000Ah
0x140164436  mov     [rsp+0D8h+var_74], r12d
0x14016443b  mov     rcx, [rbx+0B8h]
0x140164442  cmp     eax, r8d
0x140164445  setz    r8b
0x140164449  lea     rax, [rsp+0D8h+var_50]
0x140164451  mov     [rsp+0D8h+var_A0], rax
0x140164456  mov     [rsp+0D8h+var_A8], edx
0x14016445a  mov     [rsp+0D8h+var_B0], rdi
0x14016445f  mov     dword ptr [rsp+0D8h+var_B8], r12d
0x140164464  movzx   r9d, word ptr [rcx+22h]
0x140164469  mov     rdx, rbx
0x14016446c  call    NtfsCreateCcb
0x140164471  mov     r13, rax
0x140164474  or      r15d, 4
0x140164478  lea     rcx, [rax+8]
0x14016447c  mov     edx, r15d
0x14016447f  call    SetFlagInterlocked
0x140164484  mov     r9, [rbx+0B8h]
0x14016448b  mov     ecx, [r9+4]
0x14016448f  mov     r15, qword ptr [rsp+0D8h+var_88]
0x140164494  test    cl, 8
0x140164497  jnz     short loc_1401644B2
0x140164499  xor     eax, eax
0x14016449b  mov     [rsp+0D8h+var_B0], rax; __int64
0x1401644a0  mov     [rsp+0D8h+var_B8], rax; __int64
0x1401644a5  xor     r8d, r8d
0x1401644a8  mov     dl, 1
0x1401644aa  mov     rcx, r15; int
0x1401644ad  call    NtfsUpdateFcbInfoFromDisk
0x1401644b2  mov     r12, [rsp+0D8h+var_60]
0x1401644b7  jmp     loc_1401640B8
  ... truncated ...
```
