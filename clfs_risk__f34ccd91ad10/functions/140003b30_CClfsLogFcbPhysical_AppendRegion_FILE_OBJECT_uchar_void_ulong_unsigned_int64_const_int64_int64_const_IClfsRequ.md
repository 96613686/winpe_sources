# CClfsLogFcbPhysical::AppendRegion(_FILE_OBJECT *,uchar,void *,ulong,unsigned __int64 const &,__int64 &,__int64 const &,IClfsRequestAsync *,_IO_STATUS_BLOCK *,__int64 &,_CLS_LSN &,_CLS_LSN &,_CLS_LSN &)

- ea: `0x140003b30`
- end: `0x140004888`
- name: `?AppendRegion@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@EPEAXKAEB_KAEA_JAEB_JPEAUIClfsRequestAsync@@PEAU_IO_STATUS_BLOCK@@3AEAT_CLS_LSN@@77@Z`
- size: `3416`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *, unsigned __int8, void *, unsigned int, const unsigned __int64 *, __int64 *, const __int64 *, struct IClfsRequestAsync *, struct _IO_STATUS_BLOCK *, __int64 *, union _CLS_LSN *, union _CLS_LSN *, union _CLS_LSN *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140003040`
- `0x1400032d0`
- `0x140003530`
- `0x140003560`
- `0x140003b30`
- `0x140004ca0`
- `0x140005840`
- `0x14000c8b8`
- `0x14000cc2c`
- `0x14000e46c`
- `0x14000ef5c`
- `0x1400103d8`
- `0x140011d90`
- `0x1400121e4`
- `0x140017f20`
- `0x140066e90`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003c21`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140003c21`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400044c0`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400044c0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140004519`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000459f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140004519`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000459f`
- `ntoskrnl!KeBugCheckEx` at `0x1400046eb`
- `ntoskrnl!KeBugCheckEx` at `0x14000470d`
- `ntoskrnl!KeBugCheckEx` at `0x1400046eb`
- `ntoskrnl!KeBugCheckEx` at `0x14000470d`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::AppendRegion(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        unsigned __int8 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        signed __int64 a6,
        __int64 *a7,
        __int64 *a8,
        struct IClfsRequestAsync *a9,
        struct _IO_STATUS_BLOCK *a10,
        __int64 *a11,
        union _CLS_LSN *a12,
        union _CLS_LSN *a13,
        union _CLS_LSN *a14)
{
  const unsigned __int64 *v16; // rbx
  CLFS_LSN v17; // rdi
  char *BugCheckParameter4; // r13
  unsigned int v19; // ecx
  unsigned __int8 *v20; // r12
  unsigned int v21; // r14d
  struct _IO_STATUS_BLOCK *v22; // rax
  int appended; // r14d
  unsigned int v24; // ebx
  unsigned int i; // ecx
  int v26; // edx
  __int64 v27; // rax
  char v28; // bl
  CLFS_CONTAINER_ID cidContainer; // r9d
  union _CLS_LSN *v30; // r8
  CLFS_LSN *v31; // rcx
  char v32; // al
  char v33; // al
  bool v34; // sf
  unsigned int v35; // r12d
  unsigned int v36; // eax
  signed int v37; // edx
  __int64 Information_low; // rax
  unsigned int v39; // eax
  __int64 v40; // r8
  unsigned __int64 v41; // r9
  unsigned __int64 v42; // rax
  __int64 v43; // r8
  union _CLS_LSN *FirstRecord; // rax
  union _CLS_LSN v45; // rsi
  CLFS_LSN v46; // rcx
  unsigned __int64 v47; // r9
  unsigned int v48; // eax
  int v49; // ebx
  unsigned __int8 *v50; // rax
  unsigned __int8 *v51; // r12
  __int64 v52; // rbx
  char v54; // [rsp+F8h] [rbp-C8h]
  char v55; // [rsp+FAh] [rbp-C6h]
  BOOLEAN v56; // [rsp+100h] [rbp-C0h]
  unsigned __int8 *v57; // [rsp+108h] [rbp-B8h]
  int v58; // [rsp+110h] [rbp-B0h]
  __int64 v59; // [rsp+118h] [rbp-A8h] BYREF
  union _CLS_LSN v60; // [rsp+120h] [rbp-A0h] BYREF
  unsigned int v61; // [rsp+128h] [rbp-98h]
  unsigned int v62; // [rsp+12Ch] [rbp-94h]
  unsigned int v63; // [rsp+130h] [rbp-90h]
  unsigned __int64 v64; // [rsp+138h] [rbp-88h]
  unsigned __int64 v65; // [rsp+140h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK v66; // [rsp+148h] [rbp-78h] BYREF
  int v67; // [rsp+158h] [rbp-68h]
  unsigned int v68; // [rsp+15Ch] [rbp-64h]
  unsigned int v69; // [rsp+160h] [rbp-60h]
  unsigned __int8 *v70; // [rsp+168h] [rbp-58h]
  union _CLS_LSN v71; // [rsp+170h] [rbp-50h] BYREF
  int v72; // [rsp+178h] [rbp-48h]
  int v73; // [rsp+17Ch] [rbp-44h]
  CLFS_LSN v74; // [rsp+180h] [rbp-40h]
  struct _CLFS_LOG_BLOCK_HEADER *v77; // [rsp+1E0h] [rbp+20h]

  v77 = (struct _CLFS_LOG_BLOCK_HEADER *)a4;
  v16 = (const unsigned __int64 *)a6;
  v65 = *(_QWORD *)a6;
  v59 = 0;
  v17 = CLFS_LSN_INVALID;
  v60 = CLFS_LSN_INVALID;
  v66.Pointer = 0;
  v66.Information = 0;
  BugCheckParameter4 = (char *)this - 608;
  v19 = *(_DWORD *)(*((_QWORD *)this + 13) + 144LL);
  v63 = v19;
  if ( v19 - 1 > 0xFFF || (v19 & 0x1FF) != 0 || 0x1000 % v19 )
    return 3221225624LL;
  v20 = 0;
  v55 = 0;
  v54 = 0;
  v58 = 0;
  v21 = v19 >> 9;
  v22 = a10;
  a10->Status = 0;
  v22->Information = 0;
  *a11 = 0;
  v56 = ExAcquireResourceExclusiveLite((PERESOURCE)(BugCheckParameter4 + 200), 1u);
  if ( a5 )
  {
    CClfsLogFcbPhysical::RawSectorAlign((CClfsLogFcbPhysical *)BugCheckParameter4, *((_QWORD *)this - 17) + *v16);
    CClfsLogFcbPhysical::RawSectorAlign((CClfsLogFcbPhysical *)BugCheckParameter4, (unsigned __int64)a5 << 9);
    v42 = CClfsLogFcbPhysical::RawSectorAlign((CClfsLogFcbPhysical *)BugCheckParameter4, v41);
    if ( (__int64)(v43 + v42) < 0 && (__int64)(v43 + v42 + *a7) < 0 )
    {
      appended = -1072037859;
      goto LABEL_89;
    }
    v70 = a4;
    v20 = a4;
    v57 = a4;
    FirstRecord = (union _CLS_LSN *)ClfsGetFirstRecord(a4, a5 << 9);
    if ( !FirstRecord )
    {
      appended = -1072037878;
      goto LABEL_89;
    }
    v45 = *FirstRecord;
    v71 = *FirstRecord;
    v62 = v21 * (CClfsLogFcbPhysical::RawSectorAlign((CClfsLogFcbPhysical *)BugCheckParameter4, a5 << 9) / v63);
    v17 = **(CLFS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(
                            (CClfsLogFcbPhysical *)BugCheckParameter4,
                            (const union _CLS_LSN *)&a6,
                            (int)this - 104);
    v60 = v17;
    a6 = 0;
    v64 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*(_QWORD *)BugCheckParameter4 + 312LL))(BugCheckParameter4)
      || (v46 = CLFS_LSN_INVALID, CLFS_LSN_INVALID.ullOffset == v17.ullOffset) )
    {
      v74 = CLFS_LSN_INVALID;
      v46 = CLFS_LSN_INVALID;
    }
    else
    {
      LODWORD(a6) = v17.offset.idxRecord & 0xFFFFFE00;
      v47 = *((_QWORD *)BugCheckParameter4 + 87);
      v64 = ((((__int64)(v47 * v60.offset.cidContainer + a6) / 0x80000) << 19) + 520192) / v47;
      a6 = ((((__int64)(v47 * v60.offset.cidContainer + a6) / 0x80000) << 19) + 520192) % v47;
      if ( (_DWORD)v64 != -1 )
      {
        v48 = a6;
        if ( (a6 & 0x1FF) == 0 )
        {
          v73 = v64;
          v72 = a6;
          a6 = __PAIR64__(v64, a6);
          v46.ullOffset = __PAIR64__(v64, v48);
        }
      }
      v74 = v46;
    }
    if ( v46.ullOffset == v17.ullOffset )
    {
      v17 = **(CLFS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(
                              (CClfsLogFcbPhysical *)BugCheckParameter4,
                              (const union _CLS_LSN *)&a6,
                              (unsigned int)&v60);
      v60 = v17;
    }
    appended = ClfsEncodeBlock(v77, a5 << 9, *((_BYTE *)this + 81), 4u, 0);
    if ( appended < 0 )
    {
LABEL_64:
      v20 = v57;
      goto LABEL_89;
    }
    v55 = 1;
    v28 = 9;
    LOBYTE(a6) = 9;
    v36 = v62;
    v35 = v62;
    v61 = v62;
    while ( 1 )
    {
      if ( (int)v35 <= 0 )
        goto LABEL_64;
      v37 = *((_DWORD *)this + 176);
      if ( v37 > (int)v35 )
        break;
      if ( v37 )
      {
        appended = CClfsLogFcbPhysical::AppendLog(
                     (CClfsLogFcbPhysical *)BugCheckParameter4,
                     a2,
                     a3,
                     v77,
                     v37,
                     *((unsigned __int16 *)v57 + 2) - v35,
                     v28,
                     &v65,
                     a7,
                     a8,
                     a9,
                     &v66,
                     &v59,
                     a12,
                     a13);
        if ( appended < 0 )
          goto LABEL_64;
        v54 = 1;
        v49 = LODWORD(v66.Information) >> 9;
        v58 += LODWORD(v66.Information);
        v67 = v58;
        a10->Information += LODWORD(v66.Information);
        v77 = (struct _CLFS_LOG_BLOCK_HEADER *)((char *)v77 + v66.Information);
        v70 = (unsigned __int8 *)v77;
        *a11 += v59;
        v59 = 0;
        v65 = 0;
        CClfsLogFcbPhysical::UpdateOwnerSectors((ULONG_PTR)BugCheckParameter4, a3, v62 - v35, *((_DWORD *)this + 176));
        appended = CClfsLogFcbPhysical::UpdateOwnerReferrals((CClfsLogFcbPhysical *)BugCheckParameter4, a3, &v71, &v60);
        if ( appended < 0 )
          goto LABEL_64;
        v61 = v35 - v49;
        LOBYTE(a6) = a6 | 2;
      }
      v50 = (unsigned __int8 *)ExAllocateFromPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage);
      v51 = v50;
      if ( !v50 )
      {
        appended = -1073741670;
        goto LABEL_64;
      }
      ClfsInitializeOwnerPage(v50, v63);
      appended = CClfsLogFcbPhysical::OverflowReferral((CClfsLogFcbPhysical *)BugCheckParameter4, v51);
      if ( appended < 0 )
      {
        ExFreeToPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage, v51);
        goto LABEL_64;
      }
      v52 = *((_QWORD *)this + 12);
      appended = ClfsEncodeBlock((struct _CLFS_LOG_BLOCK_HEADER *)v52, 0x1000u, *((_BYTE *)this + 81), 8u, 0);
      if ( appended < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            31,
            (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
            (unsigned int)"CClfsLogFcbPhysical::AppendRegion",
            4);
        }
        ExFreeToPagedLookasideList(&CClfsLogFcbPhysical::m_laOwnerPage, v51);
        v20 = v57;
        goto LABEL_89;
      }
      appended = CClfsLogFcbPhysical::AppendLog(
                   (CClfsLogFcbPhysical *)BugCheckParameter4,
                   a2,
                   0,
                   *((void **)this + 12),
                   8u,
                   0,
                   4,
                   &v65,
                   a7,
                   a8,
                   a9,
                   &v66,
                   &v59,
                   a12,
                   a13);
      if ( appended < 0 )
      {
        if ( v52 )
          ClfsDecodeBlock((struct _CLFS_LOG_BLOCK_HEADER *)v52, 8u, *(_BYTE *)(v52 + 2), 8u, (unsigned int *)&a6);
        goto LABEL_64;
      }
      v54 = 1;
      *((_QWORD *)this + 12) = v51;
      *((_DWORD *)this + 176) = 1016;
      *a11 += v59;
      v59 = 0;
      v35 = v61;
      v28 = a6;
LABEL_34:
      v36 = v62;
    }
    v24 = v36 - v35;
    appended = CClfsLogFcbPhysical::AppendLog(
                 (CClfsLogFcbPhysical *)BugCheckParameter4,
                 a2,
                 a3,
                 v77,
                 v35,
                 v36 - v35,
                 a6,
                 &v65,
                 a7,
                 a8,
                 a9,
                 &v66,
                 &v59,
                 a12,
                 a13);
    if ( appended < 0 )
      goto LABEL_64;
    v54 = 1;
    Information_low = LODWORD(v66.Information);
    LODWORD(v64) = LODWORD(v66.Information) >> 9;
    v58 += LODWORD(v66.Information);
    v67 = v58;
    a10->Information = LODWORD(v66.Information);
    v77 = (struct _CLFS_LOG_BLOCK_HEADER *)((char *)v77 + Information_low);
    v70 = (unsigned __int8 *)v77;
    *a11 += v59;
    v59 = 0;
    v65 = 0;
    v39 = *((_DWORD *)BugCheckParameter4 + 328);
    if ( v39 > 0x3F8 )
      KeBugCheckEx(0xC1F5u, 0x25u, *((unsigned int *)BugCheckParameter4 + 328), 0x3F8u, (ULONG_PTR)BugCheckParameter4);
    if ( v35 > v39 )
      KeBugCheckEx(0xC1F5u, 0x26u, v35, *((unsigned int *)BugCheckParameter4 + 328), (ULONG_PTR)BugCheckParameter4);
    v40 = *((_QWORD *)BugCheckParameter4 + 88) + *(unsigned int *)(*((_QWORD *)BugCheckParameter4 + 88) + 44LL);
    if ( v24 > 0xFF )
      LOBYTE(v24) = -1;
    else
      v68 = v24;
    for ( i = 0; ; ++i )
    {
      v69 = i;
      v26 = *((_DWORD *)BugCheckParameter4 + 328);
      if ( i >= v35 )
        break;
      v27 = i - v26 + 1016;
      *(_BYTE *)(v40 + 2 * v27) = a3;
      *(_BYTE *)(v40 + 2 * v27 + 1) = v24;
      if ( (_BYTE)v24 != 0xFF )
        LOBYTE(v24) = v24 + 1;
    }
    *((_DWORD *)BugCheckParameter4 + 328) = v26 - v35;
    v28 = a6;
    if ( (a6 & 2) != 0 )
    {
      appended = CClfsLogFcbPhysical::UpdateOwnerReferrals((CClfsLogFcbPhysical *)BugCheckParameter4, a3, &v60, &v60);
      v34 = appended < 0;
LABEL_32:
      if ( v34 )
        goto LABEL_64;
      goto LABEL_33;
    }
    if ( (a6 & 1) == 0 )
    {
LABEL_33:
      v35 -= v64;
      v61 = v35;
      goto LABEL_34;
    }
    if ( a3 > 0x60u
      || v45.ullOffset == CLFS_LSN_INVALID.ullOffset
      || v17.ullOffset == CLFS_LSN_INVALID.ullOffset
      || (cidContainer = v60.offset.cidContainer, v71.offset.cidContainer >= v60.offset.cidContainer)
      && (v71.offset.cidContainer != v60.offset.cidContainer || v45.offset.idxRecord > v17.offset.idxRecord) )
    {
      appended = -1072037878;
      goto LABEL_31;
    }
    v30 = (union _CLS_LSN *)(16LL * a3 + *(unsigned int *)(*((_QWORD *)this + 12) + 48LL) + *((_QWORD *)this + 12));
    if ( v30 && CLFS_LSN_INVALID.ullOffset == v30->ullOffset )
    {
      v31 = v30 + 1;
      if ( v30 == (union _CLS_LSN *)-8LL
        || CLFS_LSN_INVALID.ullOffset != v31->ullOffset && CLFS_LSN_NULL.ullOffset != v31->ullOffset )
      {
        *v30 = *v31;
        goto LABEL_29;
      }
    }
    else
    {
      v31 = v30 + 1;
    }
    if ( v30 )
    {
      if ( v30->ullOffset <= __PAIR64__(v71.offset.cidContainer, v45.offset.idxRecord) )
        goto LABEL_25;
      v32 = 1;
    }
    else
    {
      v32 = 0;
    }
    if ( v32 )
      *v30 = v45;
LABEL_25:
    if ( v31 )
    {
      if ( v31->ullOffset >= __PAIR64__(cidContainer, v17.offset.idxRecord) )
        goto LABEL_30;
      v33 = 1;
    }
    else
    {
      v33 = 0;
    }
    if ( v33 )
LABEL_29:
      *v31 = v17;
LABEL_30:
    appended = 0;
LABEL_31:
    v34 = appended < 0;
    goto LABEL_32;
  }
  appended = CClfsLogFcbPhysical::AppendLog(
               (CClfsLogFcbPhysical *)BugCheckParameter4,
               a2,
               a3,
               a4,
               0,
               0,
               9,
               v16,
               a7,
               a8,
               a9,
               a10,
               a11,
               a12,
               a13);
LABEL_89:
  if ( appended < 0 )
  {
    if ( v55 )
    {
      if ( v54 )
      {
        *((_DWORD *)this - 61) |= 0x11000u;
        if ( !*((_DWORD *)this - 3) )
        {
          *((_DWORD *)this - 3) = 6;
          *((_DWORD *)this - 2) = appended;
        }
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
        {
          WPP_SF_slid(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            32,
            (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
            (unsigned int)"CClfsLogFcbPhysical::AppendRegion",
            198,
            (char)BugCheckParameter4,
            appended);
        }
        appended = -1072037845;
        if ( !*((_DWORD *)this - 5) )
        {
          *((_DWORD *)this - 5) = 7;
          *((_DWORD *)this - 4) = -1072037845;
        }
      }
      else if ( v20 )
      {
        ClfsDecodeBlock((struct _CLFS_LOG_BLOCK_HEADER *)v20, a5, v20[2], 4u, (unsigned int *)&a6);
      }
    }
  }
  else
  {
    *a14 = *(union _CLS_LSN *)((char *)this - 128);
  }
  if ( v56 )
    ClfsReleaseResourceLite(BugCheckParameter4 + 200);
  if ( appended >= 0 )
  {
    if ( a5 )
      *a12 = v17;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140003b30  mov     r11, rsp
0x140003b33  mov     [r11+20h], r9
0x140003b37  mov     [r11+18h], r8b
0x140003b3b  mov     [r11+10h], rdx
0x140003b3f  mov     [r11+8], rcx
0x140003b43  push    rbx
0x140003b44  push    rsi
0x140003b45  push    rdi
0x140003b46  push    r12
0x140003b48  push    r13
0x140003b4a  push    r14
0x140003b4c  push    r15
0x140003b4e  sub     rsp, 110h
0x140003b55  mov     rsi, r9
0x140003b58  mov     r15, rcx
0x140003b5b  mov     rbx, qword ptr [rsp+148h+arg_28]
0x140003b63  mov     rax, [rbx]
0x140003b66  mov     [r11-80h], rax
0x140003b6a  xor     r8d, r8d
0x140003b6d  mov     [r11-0A8h], r8
0x140003b74  mov     rdi, qword ptr cs:CLFS_LSN_INVALID
0x140003b7b  mov     qword ptr [rsp+148h+var_A0], rdi
0x140003b83  mov     [r11-78h], r8
0x140003b87  mov     [r11-70h], r8
0x140003b8b  lea     r13, [rcx-260h]
0x140003b92  mov     rax, [r13+2C8h]
0x140003b99  mov     ecx, [rax+90h]
0x140003b9f  mov     [rsp+148h+var_90], ecx
0x140003ba6  lea     eax, [rcx-1]
0x140003ba9  cmp     eax, 0FFFh
0x140003bae  ja      loc_14000487E
0x140003bb4  test    ecx, 1FFh
0x140003bba  jnz     loc_14000487E
0x140003bc0  xor     edx, edx
0x140003bc2  mov     eax, 1000h
0x140003bc7  div     ecx
0x140003bc9  test    edx, edx
0x140003bcb  jnz     loc_14000487E
0x140003bd1  mov     r12d, r8d
0x140003bd4  mov     [r11-0B8h], r8
0x140003bdb  mov     [r11-0C4h], r8d
0x140003be2  mov     [r11-0C6h], r8b
0x140003be9  mov     [r11-0C8h], r8b
0x140003bf0  mov     [r11-0B0h], r8d
0x140003bf7  mov     r14d, ecx
0x140003bfa  shr     r14d, 9
0x140003bfe  mov     rax, [rsp+148h+arg_48]
0x140003c06  mov     [rax], r8d
0x140003c09  mov     [rax+8], r8
0x140003c0d  mov     rax, [rsp+148h+arg_50]
0x140003c15  mov     [rax], r8
0x140003c18  lea     rcx, [r13+0C8h]; Resource
0x140003c1f  mov     dl, 1; Wait
0x140003c21  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140003c28  nop     dword ptr [rax+rax+00h]
0x140003c2d  mov     [rsp+148h+var_C0], al
0x140003c34  cmp     [rsp+148h+arg_20], r12d
0x140003c3c  jnz     loc_14000404B
0x140003c42  mov     rcx, [rsp+148h+arg_60]
0x140003c4a  mov     [rsp+148h+var_D8], rcx; union _CLS_LSN *
0x140003c4f  mov     rcx, [rsp+148h+arg_58]
0x140003c57  mov     [rsp+148h+var_E0], rcx; union _CLS_LSN *
0x140003c5c  mov     rax, [rsp+148h+arg_50]
0x140003c64  mov     [rsp+148h+var_E8], rax; __int64 *
0x140003c69  mov     rax, [rsp+148h+arg_48]
0x140003c71  mov     [rsp+148h+var_F0], rax; struct _IO_STATUS_BLOCK *
0x140003c76  mov     rax, [rsp+148h+arg_40]
0x140003c7e  mov     [rsp+148h+var_F8], rax; struct IClfsRequestAsync *
0x140003c83  mov     rax, [rsp+148h+arg_38]
0x140003c8b  mov     [rsp+148h+var_100], rax; __int64 *
0x140003c90  mov     rax, [rsp+148h+arg_30]
0x140003c98  mov     [rsp+148h+var_108], rax; __int64 *
0x140003c9d  mov     [rsp+148h+var_110], rbx; unsigned __int64 *
0x140003ca2  mov     al, 9
0x140003ca4  mov     [rsp+148h+var_118], al; char
0x140003ca8  mov     [rsp+148h+var_120], r12d; unsigned int
0x140003cad  mov     dword ptr [rsp+148h+BugCheckParameter4], r12d; unsigned int
0x140003cb2  mov     r9, rsi; void *
0x140003cb5  mov     r8b, [rsp+148h+arg_10]; unsigned __int8
0x140003cbd  mov     rdx, [rsp+148h+arg_8]; struct _FILE_OBJECT *
0x140003cc5  mov     rcx, r13; this
0x140003cc8  call    ?AppendLog@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@EPEAXKKEAEB_KAEA_JAEB_JPEAUIClfsRequestAsync@@PEAU_IO_STATUS_BLOCK@@3AEAT_CLS_LSN@@7@Z; CClfsLogFcbPhysical::AppendLog(_FILE_OBJECT *,uchar,void *,ulong,ulong,uchar,unsigned __int64 const &,__int64 &,__int64 const &,IClfsRequestAsync *,_IO_STATUS_BLOCK *,__int64 &,_CLS_LSN &,_CLS_LSN &)
0x140003ccd  mov     r14d, eax
0x140003cd0  mov     [rsp+148h+var_C4], eax
0x140003cd7  lea     rbx, WPP_GLOBAL_Control
0x140003cde  jmp     loc_14000474E
0x140003ce3  mov     bl, 0FFh
0x140003ce5  mov     [rsp+148h+var_C7], bl
0x140003cec  xor     ecx, ecx
0x140003cee  movzx   r11d, [rsp+148h+arg_10]
0x140003cf7  mov     [rsp+148h+var_60], ecx
0x140003cfe  mov     edx, [r13+520h]
0x140003d05  cmp     ecx, r12d
0x140003d08  jnb     short loc_140003D2E
0x140003d0a  mov     eax, ecx
0x140003d0c  sub     eax, edx
0x140003d0e  add     eax, 3F8h
0x140003d13  mov     [r8+rax*2], r11b
0x140003d17  mov     [r8+rax*2+1], bl
0x140003d1c  cmp     bl, 0FFh
0x140003d1f  jnb     short loc_140003D2A
0x140003d21  inc     bl
0x140003d23  mov     [rsp+148h+var_C7], bl
0x140003d2a  inc     ecx
0x140003d2c  jmp     short loc_140003CF7
0x140003d2e  sub     edx, r12d
0x140003d31  mov     [r13+520h], edx
0x140003d38  mov     bl, byte ptr [rsp+148h+arg_28]
0x140003d3f  test    bl, 2
0x140003d42  jnz     loc_14000471A
0x140003d48  test    bl, 1
0x140003d4b  jz      loc_140003DF8
0x140003d51  cmp     r11b, 60h ; '`'
0x140003d55  ja      loc_140004007
0x140003d5b  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140003d62  cmp     rsi, rax
0x140003d65  jz      loc_140004007
0x140003d6b  cmp     rdi, rax
0x140003d6e  jz      loc_140004007
0x140003d74  mov     r9d, dword ptr [rsp+148h+var_A0+4]
0x140003d7c  mov     r10d, dword ptr [rsp+148h+var_50+4]
0x140003d84  cmp     r10d, r9d
0x140003d87  jnb     loc_140003FFD
0x140003d8d  mov     r8, [r15+60h]
0x140003d91  mov     ecx, [r8+30h]
0x140003d95  mov     rdx, r11
0x140003d98  shl     rdx, 4
0x140003d9c  add     r8, rcx
0x140003d9f  add     r8, rdx
0x140003da2  jz      short loc_140003DAD
0x140003da4  cmp     rax, [r8]
0x140003da7  jz      loc_140004019
0x140003dad  lea     rcx, [r8+8]
0x140003db1  test    r8, r8
0x140003db4  jnz     loc_140003FDE
0x140003dba  xor     al, al
0x140003dbc  test    al, al
0x140003dbe  jnz     loc_140004746
0x140003dc4  test    rcx, rcx
0x140003dc7  jz      loc_140004012
0x140003dcd  mov     eax, [rcx+4]
0x140003dd0  cmp     eax, r9d
0x140003dd3  ja      short loc_140003DE4
0x140003dd5  jnz     short loc_140003DDB
0x140003dd7  cmp     [rcx], edi
0x140003dd9  jnb     short loc_140003DE4
0x140003ddb  mov     al, 1
0x140003ddd  test    al, al
0x140003ddf  jz      short loc_140003DE4
0x140003de1  mov     [rcx], rdi
0x140003de4  xor     r14d, r14d
0x140003de7  mov     [rsp+148h+var_C4], r14d
0x140003def  test    r14d, r14d
0x140003df2  js      loc_14000426B
0x140003df8  sub     r12d, dword ptr [rsp+148h+var_88]
0x140003e00  mov     [rsp+148h+var_98], r12d
0x140003e08  mov     eax, [rsp+148h+var_94]
0x140003e0f  jmp     short loc_140003E3A
0x140003e11  mov     [rsp+148h+var_C6], 1
0x140003e19  mov     bl, 9
0x140003e1b  mov     byte ptr [rsp+148h+arg_28], bl
0x140003e22  mov     [rsp+148h+var_BF], bl
0x140003e29  mov     eax, [rsp+148h+var_94]
0x140003e30  mov     r12d, eax
0x140003e33  mov     [rsp+148h+var_98], eax
0x140003e3a  test    r12d, r12d
0x140003e3d  jle     loc_14000426B
0x140003e43  mov     edx, [r15+2C0h]
0x140003e4a  cmp     edx, r12d
0x140003e4d  jle     loc_140004305
0x140003e53  mov     ebx, eax
0x140003e55  sub     ebx, r12d
0x140003e58  mov     rax, [rsp+148h+arg_60]
0x140003e60  mov     [rsp+148h+var_D8], rax; union _CLS_LSN *
0x140003e65  mov     rax, [rsp+148h+arg_58]
0x140003e6d  mov     [rsp+148h+var_E0], rax; union _CLS_LSN *
0x140003e72  lea     rax, [rsp+148h+var_A8]
0x140003e7a  mov     [rsp+148h+var_E8], rax; __int64 *
0x140003e7f  lea     rax, [rsp+148h+var_78]
0x140003e87  mov     [rsp+148h+var_F0], rax; struct _IO_STATUS_BLOCK *
0x140003e8c  mov     rax, [rsp+148h+arg_40]
0x140003e94  mov     [rsp+148h+var_F8], rax; struct IClfsRequestAsync *
0x140003e99  mov     rax, [rsp+148h+arg_38]
0x140003ea1  mov     [rsp+148h+var_100], rax; __int64 *
0x140003ea6  mov     rax, [rsp+148h+arg_30]
0x140003eae  mov     [rsp+148h+var_108], rax; __int64 *
0x140003eb3  lea     rax, [rsp+148h+var_80]
0x140003ebb  mov     [rsp+148h+var_110], rax; unsigned __int64 *
0x140003ec0  mov     al, byte ptr [rsp+148h+arg_28]
0x140003ec7  mov     [rsp+148h+var_118], al; char
0x140003ecb  mov     [rsp+148h+var_120], ebx; unsigned int
0x140003ecf  mov     dword ptr [rsp+148h+BugCheckParameter4], r12d; unsigned int
0x140003ed4  mov     r9, [rsp+148h+arg_18]; void *
0x140003edc  mov     r8b, [rsp+148h+arg_10]; unsigned __int8
0x140003ee4  mov     rdx, [rsp+148h+arg_8]; struct _FILE_OBJECT *
0x140003eec  mov     rcx, r13; this
0x140003eef  call    ?AppendLog@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@EPEAXKKEAEB_KAEA_JAEB_JPEAUIClfsRequestAsync@@PEAU_IO_STATUS_BLOCK@@3AEAT_CLS_LSN@@7@Z; CClfsLogFcbPhysical::AppendLog(_FILE_OBJECT *,uchar,void *,ulong,ulong,uchar,unsigned __int64 const &,__int64 &,__int64 const &,IClfsRequestAsync *,_IO_STATUS_BLOCK *,__int64 &,_CLS_LSN &,_CLS_LSN &)
0x140003ef4  mov     r14d, eax
0x140003ef7  mov     [rsp+148h+var_C4], eax
0x140003efe  test    eax, eax
0x140003f00  js      loc_14000426B
0x140003f06  mov     [rsp+148h+var_C8], 1
0x140003f0e  mov     eax, dword ptr [rsp+148h+var_78.Information]
0x140003f15  mov     ecx, eax
0x140003f17  shr     ecx, 9
0x140003f1a  mov     dword ptr [rsp+148h+var_88], ecx
0x140003f21  mov     ecx, [rsp+148h+var_B0]
0x140003f28  add     ecx, eax
0x140003f2a  mov     [rsp+148h+var_B0], ecx
0x140003f31  mov     [rsp+148h+var_68], ecx
0x140003f38  mov     rcx, [rsp+148h+arg_48]
0x140003f40  mov     [rcx+8], rax
0x140003f44  mov     rcx, [rsp+148h+arg_18]
0x140003f4c  add     rcx, rax
0x140003f4f  mov     [rsp+148h+arg_18], rcx
0x140003f57  mov     [rsp+148h+var_58], rcx
0x140003f5f  mov     rax, [rsp+148h+var_A8]
0x140003f67  mov     rcx, [rsp+148h+arg_50]
0x140003f6f  add     [rcx], rax
0x140003f72  mov     [rsp+148h+var_A8], 0
0x140003f7e  mov     [rsp+148h+var_80], 0
0x140003f8a  mov     [rsp+148h+var_C7], 0
0x140003f92  mov     eax, [r13+520h]
0x140003f99  cmp     eax, 3F8h
0x140003f9e  ja      loc_1400046D3
0x140003fa4  cmp     r12d, eax
0x140003fa7  ja      loc_1400046F8
0x140003fad  mov     rax, [r13+2C0h]
0x140003fb4  mov     r8d, [rax+2Ch]
0x140003fb8  add     r8, rax
0x140003fbb  cmp     ebx, 0FFh
0x140003fc1  ja      loc_140003CE3
0x140003fc7  mov     [rsp+148h+var_64], 0
0x140003fd2  mov     [rsp+148h+var_64], ebx
0x140003fd9  jmp     loc_140003CE5
0x140003fde  mov     eax, [r8+4]
0x140003fe2  cmp     eax, r10d
0x140003fe5  jb      loc_140003DC4
0x140003feb  jnz     short loc_140003FF6
0x140003fed  cmp     [r8], esi
0x140003ff0  jbe     loc_140003DC4
0x140003ff6  mov     al, 1
0x140003ff8  jmp     loc_140003DBC
0x140003ffd  jnz     short loc_140004007
0x140003fff  cmp     esi, edi
0x140004001  jbe     loc_140003D8D
0x140004007  mov     r14d, 0C01A000Ah
0x14000400d  jmp     loc_140003DE7
0x140004012  xor     al, al
0x140004014  jmp     loc_140003DDD
0x140004019  lea     rcx, [r8+8]
0x14000401d  test    rcx, rcx
0x140004020  jz      short loc_140004040
0x140004022  cmp     rax, [rcx]
0x140004025  jz      loc_140003DB1
0x14000402b  test    rcx, rcx
0x14000402e  jz      short loc_140004040
0x140004030  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140004037  cmp     rax, [rcx]
0x14000403a  jz      loc_140003DB1
0x140004040  mov     rax, [rcx]
0x140004043  mov     [r8], rax
0x140004046  jmp     loc_140003DE1
0x14000404b  mov     r9, [r15-88h]
0x140004052  mov     rdx, [rbx]
0x140004055  add     rdx, r9; unsigned __int64
0x140004058  mov     rcx, r13; this
0x14000405b  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x140004060  mov     r8, [r15-90h]
0x140004067  sub     r8, rax
0x14000406a  mov     edx, [rsp+148h+arg_20]
0x140004071  shl     rdx, 9; unsigned __int64
0x140004075  mov     rcx, r13; this
0x140004078  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x14000407d  sub     r8, rax
0x140004080  mov     rdx, r9; unsigned __int64
0x140004083  mov     rcx, r13; this
0x140004086  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x14000408b  lea     rdx, [r8+rax]
0x14000408f  test    rdx, rdx
0x140004092  js      loc_140004285
0x140004098  mov     [rsp+148h+var_58], rsi
0x1400040a0  mov     r12, rsi
0x1400040a3  mov     [rsp+148h+var_B8], rsi
0x1400040ab  mov     edx, [rsp+148h+arg_20]
0x1400040b2  shl     edx, 9; unsigned int
0x1400040b5  mov     rcx, rsi; unsigned __int8 *
0x1400040b8  call    ?ClfsGetFirstRecord@@YAPEAU_CLFS_RECORD_HEADER@@PEAEK@Z; ClfsGetFirstRecord(uchar *,ulong)
0x1400040bd  test    rax, rax
0x1400040c0  jz      loc_1400042A1
0x1400040c6  mov     rsi, [rax]
0x1400040c9  mov     qword ptr [rsp+148h+var_50], rsi
0x1400040d1  xor     r8d, r8d
0x1400040d4  mov     r12d, [rsp+148h+arg_20]
0x1400040dc  shl     r12d, 9
0x1400040e0  mov     edx, r12d; unsigned int
0x1400040e3  mov     rcx, r13; this
0x1400040e6  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBAKK@Z; CClfsLogFcbPhysical::RawSectorAlign(ulong)
0x1400040eb  xor     edx, edx
0x1400040ed  mov     ecx, [rsp+148h+var_90]
  ... truncated ...
```
