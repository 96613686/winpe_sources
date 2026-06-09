# NtfsCreateInternalAttributeStream

- ea: `0x140163fc8`
- end: `0x14016469c`
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
- `0x1400ff2e4`
- `0x140100f80`
- `0x1401032b0`
- `0x140106888`
- `0x140109ea8`
- `0x14010ae4c`
- `0x14010be8c`
- `0x140110248`
- `0x1401137b0`
- `0x1401233a0`
- `0x140125fc0`
- `0x140134aa8`
- `0x140143730`
- `0x140145ddc`
- `0x14014e804`
- `0x14014ed40`
- `0x140150044`
- `0x1401578f0`
- `0x140158130`
- `0x14015b900`
- `0x14015d2c4`
- `0x14015eaf0`
- `0x1401623c0`
- `0x140163b00`
- `0x140164a44`
- `0x14016581c`
- `0x140175ad0`
- `0x140191a20`
- `0x140194cb8`
- `0x1401ba744`
- `0x1401bf580`
- `0x1401e7e78`
- `0x1401ea0a8`
- `0x1401f6448`
- `0x140211c70`
- `0x1402485d4`
- `0x14024a5e4`
- `0x14025ccec`
- `0x140260188`
- `0x140263878`
- `0x14026fb38`
- `0x140278dd4`

## callees

- `0x14000a600`
- `0x14001e810`
- `0x140023250`
- `0x140025a90`
- `0x1400592c0`
- `0x1401597b8`
- `0x140163fc8`
- `0x1401646b0`
- `0x140164c20`
- `0x140166564`
- `0x1401f2940`
- `0x14023c334`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401640b9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401640b9`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a9267`
- `ntoskrnl!ObfDereferenceObject` at `0x1402a9267`
- `ntoskrnl!IoCreateStreamFileObjectEx` at `0x140164450`
- `ntoskrnl!IoCreateStreamFileObjectEx` at `0x140164450`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x1401640f4`
- `ntoskrnl!IoCreateStreamFileObjectLite` at `0x1401640f4`
- `ntoskrnl!IoUpdateShareAccess` at `0x1401645a9`
- `ntoskrnl!IoUpdateShareAccess` at `0x1401645a9`
- `ntoskrnl!CcSetParallelFlushFile` at `0x140164305`
- `ntoskrnl!CcSetParallelFlushFile` at `0x140164305`
- `ntoskrnl!CcSetLogHandleForFileEx` at `0x140164264`
- `ntoskrnl!CcSetLogHandleForFileEx` at `0x140164264`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402a920f`
- `ntoskrnl!CcUninitializeCacheMap` at `0x1402a920f`
- `ntoskrnl!ZwClose` at `0x1402a9225`
- `ntoskrnl!ZwClose` at `0x1402a9225`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140164205`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140164205`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401641dc`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401641dc`
- `ntoskrnl!ExReleasePushLockEx` at `0x140164682`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a92b0`
- `ntoskrnl!ExReleasePushLockEx` at `0x140164682`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402a92b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14016458b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14016458b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140164096`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140164096`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14016453a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14016453a`

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
  __int64 v21; // r8
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
      FsRtlAcquireHeaderMutex(a2 + 120, a2 + 160, v21);
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
0x140163fc8  mov     r11, rsp
0x140163fcb  mov     [r11+18h], rbx
0x140163fcf  mov     [r11+20h], rsi
0x140163fd3  push    rdi
0x140163fd4  push    r12
0x140163fd6  push    r13
0x140163fd8  push    r14
0x140163fda  push    r15
0x140163fdc  sub     rsp, 0B0h
0x140163fe3  mov     rax, cs:__security_cookie
0x140163fea  xor     rax, rsp
0x140163fed  mov     [rsp+0D8h+var_30], rax
0x140163ff5  mov     sil, r9b
0x140163ff8  mov     [rsp+0D8h+var_95], r8b
0x140163ffd  mov     rbx, rdx
0x140164000  mov     r15, rcx
0x140164003  mov     qword ptr [rsp+0D8h+var_88], rcx
0x140164008  mov     [rsp+0D8h+var_58], rdx
0x140164010  mov     r12, [rsp+0D8h+arg_28]
0x140164018  mov     [rsp+0D8h+var_60], r12
0x14016401d  mov     rax, [rdx+0C0h]
0x140164024  mov     [rsp+0D8h+var_68], rax
0x140164029  xor     ecx, ecx
0x14016402b  mov     [r11-50h], rcx
0x14016402f  xorps   xmm0, xmm0
0x140164032  xor     eax, eax
0x140164034  movups  xmmword ptr [r11-48h], xmm0
0x140164039  mov     [r11-38h], rax
0x14016403d  mov     [r11-80h], rcx
0x140164041  mov     al, r9b
0x140164044  and     al, 4
0x140164046  mov     [rsp+0D8h+var_70], al
0x14016404a  jnz     loc_140164690
0x140164050  lea     r12, [rdx+118h]
0x140164057  mov     [rsp+0D8h+var_60], r12
0x14016405c  mov     rax, [r12]
0x140164060  mov     r14b, sil
0x140164063  and     r14b, 2
0x140164067  test    rax, rax
0x14016406a  jnz     loc_140164668
0x140164070  mov     r13, rcx
0x140164073  mov     [rsp+0D8h+var_90], rcx
0x140164078  mov     [rsp+0D8h+var_96], cl
0x14016407c  mov     dil, cl
0x14016407f  mov     [rsp+0D8h+var_98], cl
0x140164083  mov     [rsp+0D8h+var_97], cl
0x140164087  mov     rax, [rdx+0B8h]
0x14016408e  mov     rcx, [rax+68h]
0x140164092  add     rcx, 40h ; '@'; Resource
0x140164096  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14016409d  nop     dword ptr [rax+rax+00h]
0x1401640a2  xor     r11d, r11d
0x1401640a5  test    al, al
0x1401640a7  jnz     short loc_1401640CD
0x1401640a9  mov     rcx, [rbx+0B8h]
0x1401640b0  add     rcx, 0C8h
0x1401640b7  xor     edx, edx
0x1401640b9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401640c0  nop     dword ptr [rax+rax+00h]
0x1401640c5  mov     [rsp+0D8h+var_97], 1
0x1401640ca  xor     r11d, r11d
0x1401640cd  cmp     [r12], r11
0x1401640d1  jnz     loc_1401643F9
0x1401640d7  test    r14b, r14b
0x1401640da  jnz     loc_140164407
0x1401640e0  mov     rax, [rbx+0C0h]
0x1401640e7  mov     rdx, [rax+0F8h]
0x1401640ee  mov     rdx, [rdx+10h]; DeviceObject
0x1401640f2  xor     ecx, ecx; FileObject
0x1401640f4  call    cs:__imp_IoCreateStreamFileObjectLite
0x1401640fb  nop     dword ptr [rax+rax+00h]
0x140164100  mov     rdi, rax
0x140164103  mov     [rsp+0D8h+var_90], rax
0x140164108  btr     dword ptr [rbx+0C8h], 0Eh
0x140164110  lea     r8, [rdi+58h]
0x140164114  mov     rcx, [rsp+0D8h+arg_20]
0x14016411c  test    rcx, rcx
0x14016411f  jz      loc_1401643D7
0x140164125  movzx   eax, word ptr [rcx+2]
0x140164129  mov     [rdi+5Ah], ax
0x14016412d  movzx   eax, word ptr [rcx]
0x140164130  mov     [r8], ax
0x140164134  mov     rax, [rcx+8]
0x140164138  mov     [rdi+60h], rax
0x14016413c  xor     ecx, ecx
0x14016413e  mov     eax, [rbx+200h]
0x140164144  test    al, 20h
0x140164146  jz      loc_140164318
0x14016414c  test    r13, r13
0x14016414f  jnz     loc_14016450C
0x140164155  lea     r8d, [r13+5]
0x140164159  mov     [rsp+0D8h+var_B8], r13
0x14016415e  mov     r9, rbx
0x140164161  mov     rdx, rdi
0x140164164  mov     rcx, r15
0x140164167  call    NtfsSetFileObject
0x14016416c  mov     byte ptr [rdi+4Ah], 1
0x140164170  xor     r11d, r11d
0x140164173  cmp     [rsp+0D8h+var_70], r11b
0x140164178  jnz     loc_140164526
0x14016417e  mov     byte ptr [rdi+4Bh], 1
0x140164182  mov     word ptr [rdi+4Dh], 101h
0x140164188  mov     byte ptr [rdi+4Fh], 1
0x14016418c  test    r13, r13
0x14016418f  jnz     loc_14016459F
0x140164195  xor     r9d, r9d
0x140164198  mov     r8b, 1
0x14016419b  mov     rdx, rbx
0x14016419e  call    NtfsIncrementCloseCounts
0x1401641a3  test    r14b, r14b
0x1401641a6  jnz     loc_1401643BE
0x1401641ac  lock inc dword ptr [rbx+0D0h]
0x1401641b3  mov     rax, [rbx+0B8h]
0x1401641ba  lock inc dword ptr [rax+14h]
0x1401641be  mov     [rsp+0D8h+var_98], r8b
0x1401641c3  cmp     [rsp+0D8h+var_95], r11b
0x1401641c8  jnz     loc_140164349
0x1401641ce  lea     r14, [rbx+0A0h]
0x1401641d5  mov     rdx, r14
0x1401641d8  lea     rcx, [rbx+78h]
0x1401641dc  call    cs:__imp_FsRtlAcquireHeaderMutex
0x1401641e3  nop     dword ptr [rax+rax+00h]
0x1401641e8  mov     al, [rbx+6]
0x1401641eb  and     al, 0FEh
0x1401641ed  mov     [rbx+6], al
0x1401641f0  mov     eax, [rbx+200h]
0x1401641f6  test    al, 20h
0x1401641f8  jz      loc_1401643A6
0x1401641fe  mov     rdx, r14
0x140164201  lea     rcx, [rbx+78h]
0x140164205  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14016420c  nop     dword ptr [rax+rax+00h]
0x140164211  test    sil, 10h
0x140164215  jnz     short loc_140164270
0x140164217  xor     ecx, ecx
0x140164219  cmp     [rdi+30h], rcx
0x14016421d  jz      short loc_140164281
0x14016421f  mov     r14, [rsp+0D8h+var_68]
0x140164224  mov     eax, [rbx+200h]
0x14016422a  test    al, 20h
0x14016422c  jz      short loc_140164270
0x14016422e  mov     rax, [r14+40h]
0x140164232  cmp     rbx, rax
0x140164235  jz      short loc_140164270
0x140164237  test    rax, rax
0x14016423a  jz      loc_14016439E
0x140164240  mov     rax, [rax+118h]
0x140164247  mov     [rsp+0D8h+var_B8], rax
0x14016424c  lea     r9, NtfsQueryLogFileUsage
0x140164253  lea     r8, LfsFlushToLsn
0x14016425a  mov     rdx, [r14+0E8h]
0x140164261  mov     rcx, rdi
0x140164264  call    cs:__imp_CcSetLogHandleForFileEx
0x14016426b  nop     dword ptr [rax+rax+00h]
0x140164270  mov     [r12], rdi
0x140164274  xor     r11d, r11d
0x140164277  mov     dil, [rsp+0D8h+var_98]
0x14016427c  jmp     loc_140164617
0x140164281  movups  xmm0, xmmword ptr [rbx+18h]
0x140164285  movups  [rsp+0D8h+var_48], xmm0
0x14016428d  mov     edx, [rbx+200h]
0x140164293  test    dl, 20h
0x140164296  mov     rax, [rbx+28h]
0x14016429a  mov     rcx, 7FFFFFFFFFFFFFFFh
0x1401642a4  cmovnz  rax, rcx
0x1401642a8  mov     [rsp+0D8h+var_38], rax
0x1401642b0  cmp     dword ptr [rbx+100h], 80h
0x1401642ba  jz      loc_14016436A
0x1401642c0  mov     sil, 1
0x1401642c3  mov     r14, [rsp+0D8h+var_68]
0x1401642c8  test    dl, 1
0x1401642cb  jnz     loc_1401645E4
0x1401642d1  mov     [rsp+0D8h+var_B8], rbx
0x1401642d6  mov     r9b, sil
0x1401642d9  lea     r8, [rsp+0D8h+var_48]
0x1401642e1  mov     rdx, rdi
0x1401642e4  mov     rcx, qword ptr [rsp+0D8h+var_88]
0x1401642e9  call    NtfsInitializeCacheMap
0x1401642ee  mov     [rsp+0D8h+var_96], 1
0x1401642f3  mov     edx, 2; ChangeBackingType
0x1401642f8  mov     rcx, rdi; NewFileObject
0x1401642fb  call    NtfsUpdateBackingFileObject
0x140164300  mov     dl, 1; EnableParallelFlush
0x140164302  mov     rcx, rdi; FileObject
0x140164305  call    cs:__imp_CcSetParallelFlushFile
0x14016430c  nop     dword ptr [rax+rax+00h]
0x140164311  xor     ecx, ecx
0x140164313  jmp     loc_140164224
0x140164318  mov     rax, [r15+70h]
0x14016431c  test    rax, rax
0x14016431f  jz      loc_14016414C
0x140164325  mov     rax, [rax+0B8h]
0x14016432c  mov     rax, [rax+30h]
0x140164330  test    rax, rax
0x140164333  jz      loc_14016414C
0x140164339  mov     eax, [rax+50h]
0x14016433c  and     eax, 8020h
0x140164341  or      [rdi+50h], eax
0x140164344  jmp     loc_14016414C
0x140164349  mov     eax, [rbx+0C8h]
0x14016434f  test    al, 20h
0x140164351  jnz     loc_1401641CE
0x140164357  xor     r8d, r8d
0x14016435a  mov     rdx, rbx
0x14016435d  mov     rcx, r15
0x140164360  call    NtfsUpdateScbFromAttribute
0x140164365  jmp     loc_1401641CE
0x14016436a  mov     rax, [rbx+0B8h]
0x140164371  test    dword ptr [rax+4], 80104h
0x140164378  jnz     loc_1401642C0
0x14016437e  mov     rax, [rbx+0C0h]
0x140164385  mov     ecx, [rax+4]
0x140164388  test    cl, 10h
0x14016438b  jnz     loc_1401642C0
0x140164391  shr     sil, 3
0x140164395  and     sil, 1
0x140164399  jmp     loc_1401642C3
0x14016439e  mov     rax, rcx
0x1401643a1  jmp     loc_140164247
0x1401643a6  mov     al, [rbx+6]
0x1401643a9  test    al, 1
0x1401643ab  jnz     loc_1401641FE
0x1401643b1  mov     al, [rbx+6]
0x1401643b4  or      al, 1
0x1401643b6  mov     [rbx+6], al
0x1401643b9  jmp     loc_1401641FE
0x1401643be  cmp     [rdi+28h], r11
0x1401643c2  jz      loc_140164277
0x1401643c8  xor     edx, edx; ChangeBackingType
0x1401643ca  mov     rcx, rdi; NewFileObject
0x1401643cd  call    NtfsUpdateBackingFileObject
0x1401643d2  jmp     loc_140164274
0x1401643d7  mov     rdx, rbx
0x1401643da  mov     rcx, r15
0x1401643dd  call    NtfsBuildInternalAttributeStreamName
0x1401643e2  xor     ecx, ecx
0x1401643e4  test    al, al
0x1401643e6  jz      loc_14016413E
0x1401643ec  bts     dword ptr [rbx+0C8h], 0Eh
0x1401643f4  jmp     loc_14016413E
0x1401643f9  test    r14b, r14b
0x1401643fc  jz      loc_140164617
0x140164402  jmp     loc_1401640D7
0x140164407  mov     r12d, 80000008h
0x14016440d  mov     [rsp+0D8h+var_74], r12d
0x140164412  mov     r15d, r11d
0x140164415  mov     [rsp+0D8h+var_78], r11d
0x14016441a  mov     rcx, qword ptr [rsp+0D8h+var_88]
0x14016441f  test    dword ptr [rcx+1B4h], 80008h
0x140164429  mov     eax, 2
0x14016442e  cmovnz  r15d, eax
0x140164432  mov     [rsp+0D8h+var_78], r15d
0x140164437  mov     rax, [rbx+0C0h]
0x14016443e  mov     rdx, [rax+0F8h]
0x140164445  lea     r8, [rsp+0D8h+FileHandle]; FileHandle
0x14016444a  mov     rdx, [rdx+10h]; DeviceObject
0x14016444e  xor     ecx, ecx; FileObject
0x140164450  call    cs:__imp_IoCreateStreamFileObjectEx
0x140164457  nop     dword ptr [rax+rax+00h]
0x14016445c  mov     rdi, rax
0x14016445f  mov     [rsp+0D8h+var_90], rax
0x140164464  mov     eax, [rbx+100h]
0x14016446a  mov     r8d, 0A0h
0x140164470  xor     edx, edx
0x140164472  cmp     eax, r8d
0x140164475  jz      short loc_140164480
0x140164477  cmp     [rbx+108h], dx
0x14016447e  jnz     short loc_14016448B
0x140164480  mov     r12d, 8000000Ah
0x140164486  mov     [rsp+0D8h+var_74], r12d
0x14016448b  mov     rcx, [rbx+0B8h]
0x140164492  cmp     eax, r8d
0x140164495  setz    r8b
0x140164499  lea     rax, [rsp+0D8h+var_50]
0x1401644a1  mov     [rsp+0D8h+var_A0], rax
0x1401644a6  mov     [rsp+0D8h+var_A8], edx
0x1401644aa  mov     [rsp+0D8h+var_B0], rdi
0x1401644af  mov     dword ptr [rsp+0D8h+var_B8], r12d
0x1401644b4  movzx   r9d, word ptr [rcx+22h]
0x1401644b9  mov     rdx, rbx
0x1401644bc  call    NtfsCreateCcb
0x1401644c1  mov     r13, rax
0x1401644c4  or      r15d, 4
0x1401644c8  lea     rcx, [rax+8]
0x1401644cc  mov     edx, r15d
0x1401644cf  call    SetFlagInterlocked
0x1401644d4  mov     r9, [rbx+0B8h]
0x1401644db  mov     ecx, [r9+4]
0x1401644df  mov     r15, qword ptr [rsp+0D8h+var_88]
0x1401644e4  test    cl, 8
0x1401644e7  jnz     short loc_140164502
0x1401644e9  xor     eax, eax
0x1401644eb  mov     [rsp+0D8h+var_B0], rax; __int64
0x1401644f0  mov     [rsp+0D8h+var_B8], rax; __int64
0x1401644f5  xor     r8d, r8d
0x1401644f8  mov     dl, 1
0x1401644fa  mov     rcx, r15; int
0x1401644fd  call    NtfsUpdateFcbInfoFromDisk
0x140164502  mov     r12, [rsp+0D8h+var_60]
0x140164507  jmp     loc_140164108
  ... truncated ...
```
