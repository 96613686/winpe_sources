# RxPerformSingleLogicalViewMigration

- ea: `0x14004f55c`
- end: `0x14004fede`
- name: `RxPerformSingleLogicalViewMigration`
- size: `2434`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update`

## callers

- `0x14004f4d0`

## callees

- `0x140015230`
- `0x140017280`
- `0x140017310`
- `0x140017c28`
- `0x1400210b8`
- `0x140021f80`
- `0x140022820`
- `0x140022aac`
- `0x140025558`
- `0x1400255b4`
- `0x140025d00`
- `0x140025d80`
- `0x140026080`
- `0x14004d498`
- `0x14004dd60`
- `0x14004eb28`
- `0x14004f55c`
- `0x140058f00`
- `0x14005c450`
- `0x14005f110`
- `0x14006b820`
- `0x1400780a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004fcc2`
- `ntoskrnl!ExAllocatePool2` at `0x14004fcc2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004f725`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004f725`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004fa14`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004fb77`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004fb97`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004fa14`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004fb77`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004fb97`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004fa55`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004fdd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004fdfc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004fa55`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004fdd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004fdfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fcf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fcf1`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14004f5c5`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14004f5c5`

## pseudocode

```c
__int64 __fastcall RxPerformSingleLogicalViewMigration(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _WORD *a5,
        const void **a6)
{
  __int64 v6; // rbx
  __int64 v7; // r15
  int v8; // r13d
  __int64 v10; // r9
  char v11; // r8
  char v12; // al
  const void **v13; // r14
  char v14; // r8
  char v15; // al
  char v16; // r8
  _QWORD *v17; // rax
  __int64 v18; // rdx
  _WORD *v19; // r10
  unsigned __int16 v20; // di
  BOOLEAN v21; // al
  int v22; // r12d
  bool v23; // si
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  void (__fastcall *v28)(__int64); // rax
  int v29; // r9d
  _QWORD *v30; // rsi
  char v31; // r14
  _QWORD *v32; // rdi
  int v33; // r8d
  int v34; // r9d
  int DestinationVNetRoot; // r15d
  int v36; // r9d
  int v37; // r8d
  int v38; // r9d
  int v39; // r9d
  int v40; // esi
  int v41; // r9d
  char v42; // al
  __int64 Pool2; // rdi
  __int16 v44; // ax
  void *v45; // rcx
  void *v46; // rcx
  _QWORD *v47; // rax
  __int64 v48; // rcx
  _QWORD *v49; // rdi
  void *v50; // rcx
  char v51; // al
  __int64 v52; // [rsp+20h] [rbp-E0h]
  __int64 v53; // [rsp+28h] [rbp-D8h]
  int v54; // [rsp+38h] [rbp-C8h]
  int v55; // [rsp+40h] [rbp-C0h]
  int v56; // [rsp+48h] [rbp-B8h]
  int v57; // [rsp+58h] [rbp-A8h]
  _QWORD v58[12]; // [rsp+60h] [rbp-A0h] BYREF
  int v59; // [rsp+C0h] [rbp-40h]
  int v60; // [rsp+C4h] [rbp-3Ch]
  _QWORD v61[2]; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v64[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v65; // [rsp+118h] [rbp+18h]
  _OWORD v66[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v67; // [rsp+140h] [rbp+40h]
  _OWORD v68[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v69; // [rsp+168h] [rbp+68h]

  v6 = a2;
  v7 = a3;
  v8 = a1;
  memset(v58, 0, sizeof(v58));
  v61[0] = 0x20000;
  v61[1] = &unk_14002991C;
  ExIsResourceAcquiredSharedLite((PERESOURCE)&Fcb[1].spacer.ValidDataLength);
  v10 = *(_QWORD *)(v6 + 32);
  v58[6] = &v58[5];
  v58[5] = &v58[5];
  v58[11] = &v58[10];
  v58[10] = &v58[10];
  v58[2] = a4;
  v58[3] = v10;
  v11 = v58[7] & 0xFD | (a4 != v10 ? 2 : 0);
  LOBYTE(v58[7]) = v11;
  if ( (v11 & 2) == 0 || *(_QWORD *)(*(_QWORD *)(v10 + 32) + 48LL) == *(_QWORD *)(*(_QWORD *)(a4 + 32) + 48LL) )
    v12 = 0;
  else
    v12 = 8;
  v13 = a6;
  v58[0] = v6;
  v58[1] = v7;
  v58[4] = a6;
  v14 = (v6 != v7) | v12 & 0xFE | v11 & 0xF6;
  LOBYTE(v58[7]) = v14;
  if ( (v14 & 2) != 0 && ((*(_DWORD *)(a4 + 56) & 2) != 0 || (*(_DWORD *)(v10 + 56) & 2) != 0) )
    v15 = 16;
  else
    v15 = 0;
  v16 = v15 | v14 & 0xEF;
  v17 = v61;
  LOBYTE(v58[7]) = v16;
  if ( *(_QWORD *)(a4 + 200) )
    v17 = *(_QWORD **)(a4 + 200);
  v58[8] = v17;
  v18 = *(unsigned __int16 *)(v6 + 64);
  LOWORD(v18) = v18 - **(_WORD **)(v58[3] + 88LL);
  LOWORD(v58[9]) = v18;
  v19 = *(_WORD **)(a4 + 88);
  v20 = *(_WORD *)a6 - *v19;
  WORD1(v58[9]) = v20;
  LOBYTE(v58[7]) = v16 & 0xFB | (v20 != (unsigned __int16)v18 ? 4 : 0);
  if ( (_WORD)v18 == v20 && (_WORD)v18 )
  {
    String1 = 0;
    String2 = 0;
    String1.Buffer = (wchar_t *)(*(_QWORD *)(v6 + 72) + **(unsigned __int16 **)(v10 + 88));
    String1.Length = v18;
    String2.Buffer = (wchar_t *)((char *)a6[1] + (unsigned __int16)*v19);
    String2.Length = v20;
    v21 = RtlEqualUnicodeString(&String1, &String2, 1u);
    v20 = WORD1(v58[9]);
    v18 = LOWORD(v58[9]);
    LOBYTE(v58[7]) = (v21 != 0 ? 0 : 4) | v58[7] & 0xFB;
  }
  v22 = (int)a5;
  v23 = (v58[7] & 1) != 0 && *a5 > *(_WORD *)(v6 + 112);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      LOBYTE(v57) = (v58[7] & 0x10) != 0 ? 89 : 78;
      v56 = (unsigned __int16)v18;
      LOBYTE(v18) = (v58[7] & 4) != 0 ? 89 : 78;
      LOBYTE(v55) = v18;
      LOBYTE(v54) = v23 ? 89 : 78;
      WPP_SF_qqqqccddc(AttachedDevice, v18, v20, v6, v7, *(_QWORD *)(v6 + 32), v58[2], v54, v55, v56, v20, v57, v58[0]);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          133,
          (unsigned int)&WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
          v6 + 112,
          (__int64)a5);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_ZZ(
            WPP_GLOBAL_Control->AttachedDevice,
            134,
            (unsigned int)&WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
            v6 + 64,
            (__int64)a6);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            135,
            &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
            *(_QWORD *)(*(_QWORD *)(v58[3] + 32LL) + 48LL),
            *(_QWORD *)(*(_QWORD *)(v58[2] + 32LL) + 48LL));
        }
      }
    }
  }
  if ( (v58[7] & 1) != 0 && v58[2] != *(_QWORD *)(v7 + 32) )
    return 3221225701LL;
  *(_DWORD *)(v6 + 192) = 1;
  *(_DWORD *)(v7 + 192) = 1;
  v26 = *(_QWORD *)(v6 + 232);
  v60 = 0;
  v59 = 0;
  memset(v64, 0, sizeof(v64));
  v65 = 0;
  v69 = 0;
  memset(v68, 0, sizeof(v68));
  v67 = 0;
  memset(v66, 0, sizeof(v66));
  RfsStartRundownProtectionReleaseCacheAware(v26, v66);
  RfsStartRundownProtectionReleaseCacheAware(*(_QWORD *)(v6 + 216), v64);
  RfsStartRundownProtectionReleaseCacheAware(*(_QWORD *)(v6 + 224), v68);
  RxWaitForLViewRequestsToDrain(v6, 0, v64);
  RfsWaitForRundownProtectionReleaseCacheAware(v66);
  RxCancelNotifyChangeDirectoryRequestsForLogicalView(v6);
  v28 = *(void (__fastcall **)(__int64))(*(_QWORD *)&Fcb->ShareAccess.Writers + 512LL);
  if ( v28 )
    v28(v6);
  LOBYTE(v27) = 1;
  RxWaitForLViewRequestsToDrain(v6, v27, v68);
  if ( (v58[7] & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 136, &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids);
    }
    ExAcquireResourceExclusiveLite((PERESOURCE)(v58[3] + 344LL), 1u);
    LOBYTE(v29) = 1;
    RxIterateOnFcbs(v8, (_DWORD)a5, v58[3], v29, (__int64)RxMigrationBuildVNetRootListFcbCallback, (__int64)v58);
    ExReleaseResourceLite((PERESOURCE)(v58[3] + 344LL));
    v30 = (_QWORD *)v58[5];
    if ( (_QWORD *)v58[5] != &v58[5] )
    {
      v31 = 1;
      do
      {
        v32 = v30 - 50;
        while ( 1 )
        {
          *((_DWORD *)v32 + 106) = -1073741576;
          DestinationVNetRoot = RxFindCreateDestinationVNetRoot(a1, v30 - 50, v58[2], v30 + 2, v58[1]);
          if ( DestinationVNetRoot != -1073741419 || !v31 )
            break;
          LOBYTE(v34) = 1;
          LOBYTE(v33) = 1;
          RxScavengeRelatedVNetRoots(*(_QWORD *)(*(_QWORD *)(v58[2] + 32LL) + 48LL), 0, v33, v34, 0);
          v31 = 0;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            137,
            &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
            v30 - 50,
            v30[2]);
        }
        *((_DWORD *)v32 + 106) = DestinationVNetRoot;
        v30 = (_QWORD *)*v30;
      }
      while ( v30 != &v58[5] );
      v6 = a2;
      v13 = a6;
      v22 = (int)a5;
      v7 = a3;
      v8 = a1;
    }
  }
  ExAcquireResourceExclusiveLite((PERESOURCE)(v58[3] + 344LL), 1u);
  if ( (v58[7] & 2) != 0 )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)(v58[2] + 344LL), 1u);
    v59 = 2;
  }
  LOBYTE(v36) = 1;
  v37 = v58[3];
  *(_QWORD *)(v6 + 240) = KeGetCurrentThread();
  RxIterateOnFcbs(v8, v22, v37, v36, (__int64)&RxMigrationPerFcbCleanupFobxsCallback, (__int64)v58);
  LOBYTE(v38) = 1;
  RxIterateOnFcbs(v8, v22, v58[3], v38, (__int64)&RxMigrationPerFcbFinishMigrationCallback, (__int64)v58);
  LOBYTE(v39) = 1;
  v40 = RxIterateOnFcbs(v8, (int)v6 + 112, v58[3], v39, (__int64)RxMigrationPerFcbFixParentCallback, (__int64)v58);
  v42 = v58[7];
  if ( (v58[7] & 1) != 0 )
  {
    LOBYTE(v41) = 1;
    v40 = RxIterateOnFcbs(v8, v22, v58[3], v41, (__int64)RxMigrationPerFcbFixParentCallback, (__int64)v58);
    v42 = v58[7];
  }
  if ( (v42 & 2) != 0 )
  {
    LOBYTE(v41) = 1;
    v40 = RxIterateOnFcbs(v8, v22, v58[2], v41, (__int64)RxMigrationPerFcbFixParentCallback, (__int64)v58);
  }
  RxMigrationDeferredFcbFinalization(v58);
  if ( (v58[7] & 1) == 0 && (v58[7] & 2) != 0 )
  {
    if ( *(_WORD *)v13 > *(_WORD *)(v6 + 66) )
    {
      Pool2 = ExAllocatePool2(258, *(unsigned __int16 *)v13, 1061124178);
      if ( !Pool2 )
      {
        v40 = -1073741670;
        v60 = 7956;
        goto LABEL_72;
      }
      if ( (*(_DWORD *)(v6 + 92) & 2) != 0 )
      {
        ExFreePoolWithTag(*(PVOID *)(v6 + 72), 0);
        *(_QWORD *)(v6 + 72) = 0;
      }
      *(_QWORD *)(v6 + 72) = Pool2;
      *(_WORD *)(v6 + 64) = 0;
      v44 = *(_WORD *)v13;
      *(_DWORD *)(v6 + 92) |= 2u;
      *(_WORD *)(v6 + 66) = v44;
    }
    memmove(*(void **)(v6 + 72), v13[1], *(unsigned __int16 *)v13);
    v45 = *(void **)(v6 + 32);
    *(_WORD *)(v6 + 64) = *(_WORD *)v13;
    RxDereference(v45, LHS_SharedLockHeld);
    v46 = (void *)v58[2];
    *(_QWORD *)(v6 + 32) = v58[2];
    RxReference(v46);
  }
LABEL_72:
  *(_QWORD *)(v6 + 240) = 0;
  while ( 1 )
  {
    v47 = (_QWORD *)v58[5];
    if ( (_QWORD *)v58[5] == &v58[5] )
      break;
    if ( *(_QWORD **)(v58[5] + 8LL) != &v58[5]
      || (v48 = *(_QWORD *)v58[5], *(_QWORD *)(*(_QWORD *)v58[5] + 8LL) != v58[5]) )
    {
      __fastfail(3u);
    }
    v58[5] = *(_QWORD *)v58[5];
    v49 = v47 - 50;
    *(_QWORD *)(v48 + 8) = &v58[5];
    v50 = (void *)v47[2];
    v47[1] = 0;
    *v47 = 0;
    *((_DWORD *)v47 + 6) = 0;
    if ( v50 )
    {
      RxDereference(v50, LHS_LockNotHeld);
      v49[52] = 0;
    }
    RxDereference(v49, LHS_LockNotHeld);
  }
  ExReleaseResourceLite((PERESOURCE)(v58[3] + 344LL));
  v51 = v58[7];
  if ( (v58[7] & 2) != 0 && v59 )
  {
    ExReleaseResourceLite((PERESOURCE)(v58[2] + 344LL));
    v51 = v58[7];
  }
  if ( v40 >= 0 && (v51 & 1) != 0 && *(_WORD *)(v7 + 112) < *(_WORD *)(v6 + 112) )
    RxUpperFinalizeLogicalView(v6);
  ++*(_DWORD *)(v6 + 96);
  RxAcceptNewRequestsOnLView(v6);
  LOWORD(v53) = -5357;
  v52 = v6 + 200;
  RxUpdateCondition(Condition_Good, 0, (PLIST_ENTRY)(v6 + 192));
  if ( (v58[7] & 1) != 0 )
  {
    LOWORD(v53) = -5357;
    v52 = v7 + 200;
    RxUpdateCondition(Condition_Good, 0, (PLIST_ENTRY)(v7 + 192));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      138,
      &WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids,
      (unsigned int)v40,
      v60);
  }
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x14004f55c  mov     [rsp-8+arg_10], r8
0x14004f561  mov     [rsp-8+arg_8], rdx
0x14004f566  mov     [rsp-8+arg_0], rcx
0x14004f56b  push    rbp
0x14004f56c  push    rbx
0x14004f56d  push    rsi
0x14004f56e  push    rdi
0x14004f56f  push    r12
0x14004f571  push    r13
0x14004f573  push    r14
0x14004f575  push    r15
0x14004f577  lea     rbp, [rsp-78h]
0x14004f57c  sub     rsp, 178h
0x14004f583  mov     rbx, rdx
0x14004f586  mov     r15, r8
0x14004f589  xor     edx, edx; Val
0x14004f58b  mov     r13, rcx
0x14004f58e  lea     rcx, [rsp+1B0h+var_150]; void *
0x14004f593  mov     rdi, r9
0x14004f596  lea     r8d, [rdx+60h]; Size
0x14004f59a  call    memset
0x14004f59f  mov     rcx, cs:Fcb
0x14004f5a6  lea     rax, unk_14002991C
0x14004f5ad  add     rcx, 2B8h; Resource
0x14004f5b4  mov     [rbp+0B0h+var_E8], 20000h
0x14004f5bc  mov     esi, 2
0x14004f5c1  mov     [rbp+0B0h+var_E0], rax
0x14004f5c5  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14004f5cc  nop     dword ptr [rax+rax+00h]
0x14004f5d1  mov     r9, [rbx+20h]
0x14004f5d5  lea     rax, [rbp+0B0h+var_128]
0x14004f5d9  mov     [rbp+0B0h+var_120], rax
0x14004f5dd  lea     rax, [rbp+0B0h+var_128]
0x14004f5e1  mov     [rbp+0B0h+var_128], rax
0x14004f5e5  lea     rax, [rbp+0B0h+var_100]
0x14004f5e9  mov     [rbp+0B0h+var_F8], rax
0x14004f5ed  lea     rax, [rbp+0B0h+var_100]
0x14004f5f1  mov     [rbp+0B0h+var_100], rax
0x14004f5f5  mov     rax, r9
0x14004f5f8  sub     rax, rdi
0x14004f5fb  mov     [rsp+1B0h+Instance], rdi
0x14004f600  neg     rax
0x14004f603  mov     [rsp+1B0h+var_138], r9
0x14004f608  mov     al, [rbp+0B0h+var_118]
0x14004f60b  sbb     r8b, r8b
0x14004f60e  and     al, 0FDh
0x14004f610  and     r8b, sil
0x14004f613  or      r8b, al
0x14004f616  mov     [rbp+0B0h+var_118], r8b
0x14004f61a  test    sil, r8b
0x14004f61d  jz      short loc_14004F635
0x14004f61f  mov     rax, [rdi+20h]
0x14004f623  mov     rdx, [r9+20h]
0x14004f627  mov     rcx, [rax+30h]
0x14004f62b  cmp     [rdx+30h], rcx
0x14004f62f  jz      short loc_14004F635
0x14004f631  mov     al, 8
0x14004f633  jmp     short loc_14004F637
0x14004f635  xor     al, al
0x14004f637  mov     r14, [rbp+0B0h+arg_28]
0x14004f63e  and     r8b, 0F7h
0x14004f642  or      r8b, al
0x14004f645  mov     [rsp+1B0h+var_150], rbx
0x14004f64a  and     r8b, 0FEh
0x14004f64e  mov     [rsp+1B0h+var_148], r15
0x14004f653  cmp     rbx, r15
0x14004f656  mov     [rbp+0B0h+var_130], r14
0x14004f65a  setnz   al
0x14004f65d  or      r8b, al
0x14004f660  mov     [rbp+0B0h+var_118], r8b
0x14004f664  test    sil, r8b
0x14004f667  jz      short loc_14004F67E
0x14004f669  mov     eax, [rdi+38h]
0x14004f66c  test    sil, al
0x14004f66f  jnz     short loc_14004F67A
0x14004f671  mov     eax, [r9+38h]
0x14004f675  test    sil, al
0x14004f678  jz      short loc_14004F67E
0x14004f67a  mov     al, 10h
0x14004f67c  jmp     short loc_14004F680
0x14004f67e  xor     al, al
0x14004f680  and     r8b, 0EFh
0x14004f684  or      r8b, al
0x14004f687  lea     rax, [rbp+0B0h+var_E8]
0x14004f68b  mov     [rbp+0B0h+var_118], r8b
0x14004f68f  mov     rcx, [rdi+0C8h]
0x14004f696  test    rcx, rcx
0x14004f699  cmovnz  rax, rcx
0x14004f69d  mov     [rbp+0B0h+var_110], rax
0x14004f6a1  movzx   edx, word ptr [rbx+40h]
0x14004f6a5  mov     rax, [rsp+1B0h+var_138]
0x14004f6aa  mov     rcx, [rax+58h]
0x14004f6ae  sub     dx, [rcx]
0x14004f6b1  mov     [rbp+0B0h+var_108], dx
0x14004f6b5  movzx   eax, dx
0x14004f6b8  mov     r10, [rdi+58h]
0x14004f6bc  movzx   edi, word ptr [r14]
0x14004f6c0  sub     di, [r10]
0x14004f6c4  sub     ax, di
0x14004f6c7  mov     [rbp+0B0h+var_106], di
0x14004f6cb  neg     ax
0x14004f6ce  sbb     cl, cl
0x14004f6d0  and     r8b, 0FBh
0x14004f6d4  and     cl, 4
0x14004f6d7  or      cl, r8b
0x14004f6da  mov     [rbp+0B0h+var_118], cl
0x14004f6dd  cmp     dx, di
0x14004f6e0  jnz     short loc_14004F74C
0x14004f6e2  xor     eax, eax
0x14004f6e4  cmp     ax, dx
0x14004f6e7  jz      short loc_14004F74C
0x14004f6e9  xorps   xmm0, xmm0
0x14004f6ec  xorps   xmm1, xmm1
0x14004f6ef  movups  xmmword ptr [rbp+0B0h+String1.Length], xmm0
0x14004f6f3  mov     r8b, 1; CaseInSensitive
0x14004f6f6  movups  xmmword ptr [rbp+0B0h+String2.Length], xmm1
0x14004f6fa  mov     rax, [r9+58h]
0x14004f6fe  movzx   ecx, word ptr [rax]
0x14004f701  add     rcx, [rbx+48h]
0x14004f705  mov     [rbp+0B0h+String1.Buffer], rcx
0x14004f709  lea     rcx, [rbp+0B0h+String1]; String1
0x14004f70d  mov     [rbp+0B0h+String1.Length], dx
0x14004f711  lea     rdx, [rbp+0B0h+String2]; String2
0x14004f715  movzx   eax, word ptr [r10]
0x14004f719  add     rax, [r14+8]
0x14004f71d  mov     [rbp+0B0h+String2.Buffer], rax
0x14004f721  mov     [rbp+0B0h+String2.Length], di
0x14004f725  call    cs:__imp_RtlEqualUnicodeString
0x14004f72c  nop     dword ptr [rax+rax+00h]
0x14004f731  movzx   edi, [rbp+0B0h+var_106]
0x14004f735  neg     al
0x14004f737  mov     al, [rbp+0B0h+var_118]
0x14004f73a  movzx   edx, [rbp+0B0h+var_108]
0x14004f73e  sbb     cl, cl
0x14004f740  not     cl
0x14004f742  and     al, 0FBh
0x14004f744  and     cl, 4
0x14004f747  or      al, cl
0x14004f749  mov     [rbp+0B0h+var_118], al
0x14004f74c  mov     r11b, [rbp+0B0h+var_118]
0x14004f750  mov     r12, [rbp+0B0h+arg_20]
0x14004f757  test    r11b, 1
0x14004f75b  jz      short loc_14004F76D
0x14004f75d  movzx   eax, word ptr [rbx+70h]
0x14004f761  cmp     [r12], ax
0x14004f766  jbe     short loc_14004F76D
0x14004f768  mov     sil, 1
0x14004f76b  jmp     short loc_14004F770
0x14004f76d  xor     sil, sil
0x14004f770  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f777  lea     rax, WPP_GLOBAL_Control
0x14004f77e  cmp     rcx, rax
0x14004f781  jz      loc_14004F8D5
0x14004f787  test    dword ptr [rcx+2Ch], 400h
0x14004f78e  jz      short loc_14004F803
0x14004f790  cmp     byte ptr [rcx+29h], 2
0x14004f794  jb      short loc_14004F803
0x14004f796  mov     rcx, [rcx+18h]
0x14004f79a  mov     al, r11b
0x14004f79d  and     al, 10h
0x14004f79f  movzx   r9d, dx
0x14004f7a3  neg     al
0x14004f7a5  movzx   r8d, di
0x14004f7a9  sbb     r10b, r10b
0x14004f7ac  and     r11b, 4
0x14004f7b0  and     r10b, 0Bh
0x14004f7b4  add     r10b, 4Eh ; 'N'
0x14004f7b8  mov     byte ptr [rsp+1B0h+var_158], r10b
0x14004f7bd  neg     r11b
0x14004f7c0  mov     [rsp+1B0h+var_160], r8d
0x14004f7c5  sbb     dl, dl
0x14004f7c7  mov     [rsp+1B0h+var_168], r9d
0x14004f7cc  and     dl, 0Bh
0x14004f7cf  mov     r9, rbx
0x14004f7d2  add     dl, 4Eh ; 'N'
0x14004f7d5  mov     byte ptr [rsp+1B0h+var_170], dl
0x14004f7d9  neg     sil
0x14004f7dc  sbb     al, al
0x14004f7de  and     al, 0Bh
0x14004f7e0  add     al, 4Eh ; 'N'
0x14004f7e2  mov     byte ptr [rsp+1B0h+var_178], al
0x14004f7e6  mov     rax, [rsp+1B0h+Instance]
0x14004f7eb  mov     [rsp+1B0h+var_180], rax
0x14004f7f0  mov     rax, [rbx+20h]
0x14004f7f4  mov     [rsp+1B0h+var_188], rax
0x14004f7f9  mov     [rsp+1B0h+var_190], r15
0x14004f7fe  call    WPP_SF_qqqqccddc
0x14004f803  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f80a  lea     rdi, WPP_GLOBAL_Control
0x14004f811  cmp     rcx, rdi
0x14004f814  jz      loc_14004F8DC
0x14004f81a  test    dword ptr [rcx+2Ch], 400h
0x14004f821  jz      short loc_14004F847
0x14004f823  cmp     byte ptr [rcx+29h], 2
0x14004f827  jb      short loc_14004F847
0x14004f829  mov     rcx, [rcx+18h]
0x14004f82d  lea     r9, [rbx+70h]
0x14004f831  mov     edx, 85h
0x14004f836  mov     [rsp+1B0h+var_190], r12
0x14004f83b  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004f842  call    WPP_SF_ZZ
0x14004f847  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f84e  cmp     rcx, rdi
0x14004f851  jz      loc_14004F8DC
0x14004f857  test    dword ptr [rcx+2Ch], 400h
0x14004f85e  jz      short loc_14004F884
0x14004f860  cmp     byte ptr [rcx+29h], 2
0x14004f864  jb      short loc_14004F884
0x14004f866  mov     rcx, [rcx+18h]
0x14004f86a  lea     r9, [rbx+40h]
0x14004f86e  mov     edx, 86h
0x14004f873  mov     [rsp+1B0h+var_190], r14
0x14004f878  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004f87f  call    WPP_SF_ZZ
0x14004f884  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f88b  cmp     rcx, rdi
0x14004f88e  jz      short loc_14004F8DC
0x14004f890  test    dword ptr [rcx+2Ch], 400h
0x14004f897  jz      short loc_14004F8DC
0x14004f899  cmp     byte ptr [rcx+29h], 2
0x14004f89d  jb      short loc_14004F8DC
0x14004f89f  mov     rax, [rsp+1B0h+Instance]
0x14004f8a4  mov     edx, 87h
0x14004f8a9  mov     rcx, [rcx+18h]
0x14004f8ad  mov     r8, [rax+20h]
0x14004f8b1  mov     rax, [rsp+1B0h+var_138]
0x14004f8b6  mov     r9, [rax+20h]
0x14004f8ba  mov     rax, [r8+30h]
0x14004f8be  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004f8c5  mov     [rsp+1B0h+var_190], rax
0x14004f8ca  mov     r9, [r9+30h]
0x14004f8ce  call    WPP_SF_qq
0x14004f8d3  jmp     short loc_14004F8DC
0x14004f8d5  lea     rdi, WPP_GLOBAL_Control
0x14004f8dc  test    [rbp+0B0h+var_118], 1
0x14004f8e0  jz      short loc_14004F8F7
0x14004f8e2  mov     rax, [r15+20h]
0x14004f8e6  cmp     [rsp+1B0h+Instance], rax
0x14004f8eb  jz      short loc_14004F8F7
0x14004f8ed  mov     eax, 0C00000E5h
0x14004f8f2  jmp     loc_14004FEC9
0x14004f8f7  xorps   xmm0, xmm0
0x14004f8fa  mov     dword ptr [rbx+0C0h], 1
0x14004f904  xor     eax, eax
0x14004f906  mov     dword ptr [r15+0C0h], 1
0x14004f911  mov     rcx, [rbx+0E8h]
0x14004f918  lea     rdx, [rbp+0B0h+var_90]
0x14004f91c  xorps   xmm1, xmm1
0x14004f91f  mov     [rbp+0B0h+var_EC], 0
0x14004f926  mov     [rbp+0B0h+var_F0], 0
0x14004f92d  movups  [rbp+0B0h+var_B8], xmm0
0x14004f931  mov     [rbp+0B0h+var_98], rax
0x14004f935  movups  [rbp+0B0h+var_A8], xmm0
0x14004f939  mov     [rbp+0B0h+var_48], rax
0x14004f93d  movups  [rbp+0B0h+var_68], xmm1
0x14004f941  mov     [rbp+0B0h+var_70], rax
0x14004f945  movups  [rbp+0B0h+var_58], xmm1
0x14004f949  movups  [rbp+0B0h+var_90], xmm0
0x14004f94d  movups  [rbp+0B0h+var_80], xmm0
0x14004f951  call    RfsStartRundownProtectionReleaseCacheAware
0x14004f956  mov     rcx, [rbx+0D8h]
0x14004f95d  lea     rdx, [rbp+0B0h+var_B8]
0x14004f961  call    RfsStartRundownProtectionReleaseCacheAware
0x14004f966  mov     rcx, [rbx+0E0h]
0x14004f96d  lea     rdx, [rbp+0B0h+var_68]
0x14004f971  call    RfsStartRundownProtectionReleaseCacheAware
0x14004f976  lea     r8, [rbp+0B0h+var_B8]
0x14004f97a  xor     edx, edx
0x14004f97c  mov     rcx, rbx
0x14004f97f  call    RxWaitForLViewRequestsToDrain
0x14004f984  lea     rcx, [rbp+0B0h+var_90]
0x14004f988  call    RfsWaitForRundownProtectionReleaseCacheAware
0x14004f98d  mov     rcx, rbx
0x14004f990  call    RxCancelNotifyChangeDirectoryRequestsForLogicalView
0x14004f995  mov     rax, cs:Fcb
0x14004f99c  mov     rcx, [rax+160h]
0x14004f9a3  mov     rax, [rcx+200h]
0x14004f9aa  test    rax, rax
0x14004f9ad  jz      short loc_14004F9B7
0x14004f9af  mov     rcx, rbx
0x14004f9b2  call    _guard_dispatch_icall
0x14004f9b7  lea     r8, [rbp+0B0h+var_68]
0x14004f9bb  mov     dl, 1
0x14004f9bd  mov     rcx, rbx
0x14004f9c0  call    RxWaitForLViewRequestsToDrain
0x14004f9c5  test    [rbp+0B0h+var_118], 2
0x14004f9c9  jz      loc_14004FB69
0x14004f9cf  mov     [rbp+0B0h+arg_18], 1
0x14004f9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f9dd  cmp     rcx, rdi
0x14004f9e0  jz      short loc_14004FA06
0x14004f9e2  test    dword ptr [rcx+2Ch], 400h
0x14004f9e9  jz      short loc_14004FA06
0x14004f9eb  cmp     byte ptr [rcx+29h], 2
0x14004f9ef  jb      short loc_14004FA06
0x14004f9f1  mov     rcx, [rcx+18h]
0x14004f9f5  lea     r8, WPP_8f40199b670e3a186f0ad2764a4463aa_Traceguids
0x14004f9fc  mov     edx, 88h
0x14004fa01  call    WPP_SF_
0x14004fa06  mov     rcx, [rsp+1B0h+var_138]
  ... truncated ...
```
