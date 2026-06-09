# CClfsLogFcbPhysical::AppendLog(_FILE_OBJECT *,uchar,void *,ulong,ulong,uchar,unsigned __int64 const &,__int64 &,__int64 const &,IClfsRequestAsync *,_IO_STATUS_BLOCK *,__int64 &,_CLS_LSN &,_CLS_LSN &)

- ea: `0x140004ca0`
- end: `0x1400055a0`
- name: `?AppendLog@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@EPEAXKKEAEB_KAEA_JAEB_JPEAUIClfsRequestAsync@@PEAU_IO_STATUS_BLOCK@@3AEAT_CLS_LSN@@7@Z`
- size: `2304`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct _FILE_OBJECT *@<rdx>, unsigned __int8@<r8b>, void *@<r9>, unsigned int, unsigned int, char, const unsigned __int64 *, __int64 *, const __int64 *, struct IClfsRequestAsync *, struct _IO_STATUS_BLOCK *, __int64 *, union _CLS_LSN *, union _CLS_LSN *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003b30`
- `0x140004890`

## callees

- `0x140003260`
- `0x140003454`
- `0x140003530`
- `0x140003560`
- `0x140003590`
- `0x140004ca0`
- `0x140005840`
- `0x140005f00`
- `0x140007034`
- `0x14000a4a0`
- `0x14000bc14`
- `0x14000cd9c`
- `0x14000fee8`
- `0x140010548`
- `0x140017f20`
- `0x140066e90`
- `0x1400717d4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004e2d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005019`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140004e2d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005019`
- `ntoskrnl!ObfReferenceObject` at `0x140005256`
- `ntoskrnl!ObfReferenceObject` at `0x140005256`
- `ntoskrnl!KeBugCheckEx` at `0x140004dbd`
- `ntoskrnl!KeBugCheckEx` at `0x1400050a2`
- `ntoskrnl!KeBugCheckEx` at `0x14000510b`
- `ntoskrnl!KeBugCheckEx` at `0x1400051a1`
- `ntoskrnl!KeBugCheckEx` at `0x140004dbd`
- `ntoskrnl!KeBugCheckEx` at `0x1400050a2`
- `ntoskrnl!KeBugCheckEx` at `0x14000510b`
- `ntoskrnl!KeBugCheckEx` at `0x1400051a1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005064`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005064`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400053d6`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1400053d6`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::AppendLog(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        unsigned __int8 a3,
        _QWORD *a4,
        unsigned int a5,
        unsigned int a6,
        char a7,
        const unsigned __int64 *a8,
        __int64 *a9,
        const __int64 *a10,
        struct IClfsRequestAsync *a11,
        struct _IO_STATUS_BLOCK *a12,
        __int64 *a13,
        union _CLS_LSN *a14,
        union _CLS_LSN *a15)
{
  ULONG_PTR v15; // rsi
  union _CLS_LSN v17; // rbx
  unsigned __int8 v18; // r12
  int v20; // eax
  CClfsFlushElt *v21; // rsi
  NTSTATUS v22; // r15d
  _QWORD *v23; // r14
  BOOLEAN v24; // r13
  __int64 v25; // r11
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // r11
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // r9
  __int64 v30; // r10
  __int64 v31; // r11
  __int64 v32; // r8
  __int64 v33; // r8
  void (__fastcall *v34)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, __int64 *, _QWORD); // rax
  unsigned __int64 v35; // rsi
  __int64 v36; // rbx
  int (__fastcall *v37)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, union _CLS_LSN *, _QWORD); // rax
  ULONGLONG v38; // rcx
  unsigned __int64 v39; // rbx
  CLFS_CONTAINER_ID NextContainer; // r12d
  CClfsFlushElt *v41; // rax
  int (__fastcall *v42)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, unsigned __int64 *, _QWORD); // rax
  __int64 v43; // rcx
  void (__fastcall *v44)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, unsigned __int64 *, _QWORD); // r10
  unsigned int v45; // edx
  int v46; // r8d
  void *v47; // rax
  unsigned __int64 v48; // rax
  CLFS_CONTAINER_ID v49; // eax
  struct CClfsAuthContainer *Container; // rax
  char v51; // al
  int v52; // ecx
  unsigned int v53; // edx
  unsigned int v54; // eax
  unsigned int v55; // eax
  __int64 v56; // rcx
  const CLFS_LSN *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  BOOLEAN v60; // [rsp+31h] [rbp-87h]
  char v61; // [rsp+32h] [rbp-86h]
  __int64 v62; // [rsp+38h] [rbp-80h]
  unsigned __int64 v63; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v64[2]; // [rsp+50h] [rbp-68h]
  unsigned __int64 v65; // [rsp+58h] [rbp-60h] BYREF
  __int64 v66; // [rsp+60h] [rbp-58h] BYREF
  union _CLS_LSN v67; // [rsp+68h] [rbp-50h] BYREF
  unsigned int v68; // [rsp+70h] [rbp-48h]
  int v69; // [rsp+78h] [rbp-40h]
  unsigned int v70; // [rsp+7Ch] [rbp-3Ch]

  v15 = a3;
  v64[0] = 0;
  v17.ullOffset = *(unsigned int *)(*((_QWORD *)this + 89) + 144LL);
  if ( v17.offset.idxRecord - 1 > 0xFFF || (v17.offset.idxRecord & 0x1FF) != 0 || 0x1000 % v17.offset.idxRecord )
    return 3221225624LL;
  *a14 = CLFS_LSN_INVALID;
  *a13 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) || (_BYTE)v15 )
  {
    v18 = a7;
  }
  else
  {
    v18 = a7;
    if ( (a7 & 4) == 0 && (a7 & 8) == 0 )
      return 3222929438LL;
  }
  if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
  {
    if ( (v18 & 4) == 0 && (v18 & 8) == 0 )
LABEL_18:
      KeBugCheckEx(0xC1F5u, 0x32u, v18, v15, (ULONG_PTR)this);
    v20 = 1;
  }
  else
  {
    if ( !(_BYTE)v15 && (v18 & 4) == 0 )
      goto LABEL_19;
    v20 = 0;
  }
  if ( !v20 )
    goto LABEL_18;
LABEL_19:
  if ( (*(_DWORD *)a8 & 0x1FFLL) != 0 || (*(_DWORD *)a10 & 0x1FFLL) != 0 || (*(_DWORD *)a9 & 0x1FFLL) != 0 )
    return 3221225485LL;
  v62 = 0;
  v21 = 0;
  v22 = 0;
  v60 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  if ( (*((_DWORD *)this + 91) & 0x1000) != 0 )
  {
    v22 = -1072037845;
    CClfsLogFcbCommon::SetInvalidLogTag(this, 8u, -1072037845);
    v23 = (_QWORD *)((char *)this + 472);
    v24 = 0;
LABEL_78:
    v31 = v62;
    goto LABEL_79;
  }
  v23 = (_QWORD *)((char *)this + 472);
  v25 = *((_QWORD *)this + 59);
  v62 = v25;
  v61 = v18 & 4;
  if ( (v18 & 4) != 0 )
  {
LABEL_35:
    if ( a5 )
    {
      if ( (v18 & 2) == 0 )
      {
        v38 = *((_QWORD *)this + 63);
        a4[3] = v38;
        *((_BYTE *)a4 + 3) = a3;
        *((_WORD *)a4 + 3) = *((_WORD *)a4 + 2);
        if ( (v18 & 1) != 0 )
          a15->ullOffset = v38;
      }
    }
    v24 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 176), 1u);
    v39 = 0;
    *(_QWORD *)v64 = 0;
    while ( 1 )
    {
      v63 = a5;
      if ( v39 >= (unsigned __int64)a5 << 9 )
        break;
      NextContainer = ClfsLsnContainer((const CLFS_LSN *)this + 63);
      v41 = (CClfsFlushElt *)ExAllocateFromNPagedLookasideList(&CClfsFlushElt::m_laList);
      if ( v41 )
        v21 = CClfsFlushElt::CClfsFlushElt(v41);
      else
        v21 = 0;
      if ( !v21 )
      {
        CClfsLogFcbCommon::ReportFlushFailure(1, 3221225473LL);
        v45 = 13;
        goto LABEL_55;
      }
      v65 = (unsigned __int64)v21 + 8;
      (**((void (__fastcall ***)(__int64))v21 + 1))((__int64)v21 + 8);
      v22 = CClfsFlushElt::Initialize(v21, this);
      if ( v22 < 0 )
      {
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v65 + 8LL))(v65);
        v21 = 0;
        CClfsLogFcbCommon::ReportFlushFailure(2, 3221225473LL);
        v46 = v22;
        v45 = 14;
        goto LABEL_56;
      }
      v47 = (void *)(*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a11 + 48LL))(a11);
      *((_QWORD *)v21 + 7) = v47;
      ObfReferenceObject(v47);
      v65 = (*((_QWORD *)this + 87) - (unsigned __int64)ClfsLsnBlockOffset((const CLFS_LSN *)this + 63)) >> 9;
      v48 = CClfsLogFcbPhysical::RawSectorAlign(this, v39);
      v63 -= v48 >> 9;
      *((_QWORD *)v21 + 6) = *((_QWORD *)this + 63);
      *((_QWORD *)v21 + 3) = (char *)a4 + v64[0];
      *((_BYTE *)v21 + 80) = a3;
      *((_DWORD *)v21 + 9) = a6;
      v49 = ClfsLsnContainer((const CLFS_LSN *)v21 + 6);
      *((_DWORD *)v21 + 48) = v49;
      Container = CClfsLogFcbPhysical::GetContainer(this, v49);
      if ( !Container )
      {
        CClfsLogFcbCommon::ReportFlushFailure(10, 3221225473LL);
        v45 = 16;
LABEL_55:
        v46 = -1073741670;
        v22 = -1073741670;
LABEL_56:
        CClfsLogFcbPhysical::SetFlushFailureTag(this, v45, v46);
        goto LABEL_78;
      }
      (*(void (__fastcall **)(struct CClfsAuthContainer *))(*(_QWORD *)Container + 8LL))(Container);
      v51 = *((_BYTE *)v21 + 16);
      v52 = v63;
      v53 = v65;
      if ( v65 >= v63 )
      {
        *((_BYTE *)v21 + 16) = v51 | 0x20;
        v55 = CClfsLogFcbPhysical::RawSectorAlign(this, v52 << 9) >> 9;
        *((_DWORD *)v21 + 8) = v55;
        v39 += CClfsLogFcbPhysical::RawSectorAlign(this, (unsigned __int64)v55 << 9);
        *(_QWORD *)v64 = v39;
        *((_QWORD *)v21 + 9) = (*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a11 + 192LL))(a11);
        if ( v61 )
          *((_QWORD *)v21 + 12) = CClfsLogFcbPhysical::FreeOwnerPage;
        CClfsLogFcbPhysical::RawSectorAlign(this, *((_DWORD *)v21 + 8) << 9);
        v56 = *(_QWORD *)CClfsLogFcbPhysical::AddLsnOffset(this, &v67, (int)this + 504).ullOffset;
        v57 = (const CLFS_LSN *)((char *)this + 504);
        *((_QWORD *)this + 63) = v56;
        while ( ClfsLsnContainer(v57) != NextContainer && NextContainer != -1 )
        {
          NextContainer = CClfsLogFcbPhysical::GetNextContainer(this, NextContainer);
          if ( NextContainer != -1 )
            CClfsLogFcbPhysical::ObservationContainerConsumed(this, a3);
          v57 = (const CLFS_LSN *)((char *)this + 504);
        }
      }
      else
      {
        *((_BYTE *)v21 + 16) = v51 & 0xDF;
        *((_DWORD *)v21 + 8) = v53;
        a6 += v53;
        v68 = a6;
        v39 += (unsigned __int64)v53 << 9;
        *(_QWORD *)v64 = v39;
        v54 = CClfsLogFcbPhysical::GetNextContainer(this, NextContainer);
        if ( v54 == -1 )
        {
          CClfsLogFcbCommon::ReportFlushFailure(10, 3221225473LL);
          v45 = 15;
          goto LABEL_55;
        }
        v70 = v54;
        v69 = 0;
        LODWORD(v66) = 0;
        HIDWORD(v66) = v54;
        *((_QWORD *)this + 63) = v66;
        CClfsLogFcbPhysical::ObservationContainerConsumed(this, a3);
      }
      *((_BYTE *)v21 + 16) |= 1u;
      _InterlockedAdd((volatile signed __int32 *)this + 330, *((_DWORD *)v21 + 8) << 9);
      *((_QWORD *)this + 172) = *((_QWORD *)v21 + 6);
      ExInterlockedInsertTailList(*((PLIST_ENTRY *)this + 119), (PLIST_ENTRY)v21 + 13, *((PKSPIN_LOCK *)this + 120));
    }
    ClfsReleaseResourceLite(*((_QWORD *)this + 176));
    v24 = 0;
    if ( *((_DWORD *)this + 330) > *((_DWORD *)this + 329) && !*((_DWORD *)this + 333) )
      CClfsLogFcbPhysical::QueueFlushWorker(this);
    v21 = 0;
    goto LABEL_78;
  }
  v63 = (unsigned __int64)a5 << 9;
  CClfsLogFcbPhysical::RawSectorAlign(this, v25 + *a8);
  CClfsLogFcbPhysical::RawSectorAlign(this, v26);
  v28 = CClfsLogFcbPhysical::RawSectorAlign(this, v27);
  v33 = v28 + v32;
  v67 = v17;
  if ( v33 % v17.ullOffset )
    KeBugCheckEx(0xC1F5u, 0x33u, HIDWORD(v33), (unsigned int)v33, (ULONG_PTR)this);
  if ( v33 >= 0 )
  {
    v34 = *(void (__fastcall **)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, __int64 *, _QWORD))(*(_QWORD *)this
                                                                                                 + 296LL);
    v66 = v30;
    v34(this, a2, &v66, 0);
    *((_QWORD *)this + 58) -= CClfsLogFcbPhysical::RawSectorAlign(this, v63);
    v35 = *((_QWORD *)this + 58);
    v36 = *a10 - *a9;
    if ( v36 % v67.ullOffset )
      KeBugCheckEx(0xC1F5u, 0x34u, HIDWORD(v36), (unsigned int)v36, (ULONG_PTR)this);
    if ( v36 <= 0 )
    {
      if ( v36 < 0 )
      {
        v42 = *(int (__fastcall **)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, unsigned __int64 *, _QWORD))(*(_QWORD *)this + 296LL);
        v63 = v36 + *v23;
        if ( v42(this, a2, &v63, 0) >= 0 )
          *a9 += v36;
      }
    }
    else
    {
      if ( (__int64)(v36 - v35) <= 0 )
        v35 = *a10 - *a9;
      else
        LODWORD(v36) = *((_QWORD *)this + 58);
      if ( v35 % v67.ullOffset )
        KeBugCheckEx(0xC1F5u, 0x35u, HIDWORD(v35), (unsigned int)v36, (ULONG_PTR)this);
      v37 = *(int (__fastcall **)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, union _CLS_LSN *, _QWORD))(*(_QWORD *)this + 296LL);
      v67.ullOffset = v35 + *v23;
      if ( v37(this, a2, &v67, 0) >= 0 )
        *a9 += v35;
    }
    goto LABEL_35;
  }
  v43 = v33 + *a9;
  if ( v43 >= 0 )
  {
    *a9 = v43;
    v65 = *((_QWORD *)this + 58) + *v23 - CClfsLogFcbPhysical::RawSectorAlign(this, v29);
    v44(this, a2, &v65, 0);
    *((_QWORD *)this + 58) = 0;
    goto LABEL_35;
  }
  v22 = -1072037859;
  v24 = 0;
LABEL_79:
  *a13 = *v23 - v31;
  a12->Status = v22;
  v58 = CClfsLogFcbPhysical::RawSectorAlign(this, v64[0]);
  *(_QWORD *)(v59 + 8) = v58;
  *a14 = *(union _CLS_LSN *)((char *)this + 504);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*((_QWORD *)v21 + 1) + 8LL))((__int64)v21 + 8);
  if ( v60 )
    ClfsReleaseResourceLite((char *)this + 200);
  if ( v24 )
    ClfsReleaseResourceLite(*((_QWORD *)this + 176));
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140004ca0  mov     rax, rsp
0x140004ca3  mov     [rax+20h], r9
0x140004ca7  mov     [rax+18h], r8b
0x140004cab  mov     [rax+10h], rdx
0x140004caf  mov     [rax+8], rcx
0x140004cb3  push    rbx
0x140004cb4  push    rsi
0x140004cb5  push    rdi
0x140004cb6  push    r12
0x140004cb8  push    r13
0x140004cba  push    r14
0x140004cbc  push    r15
0x140004cbe  sub     rsp, 80h
0x140004cc5  movzx   esi, r8b
0x140004cc9  mov     rdi, rcx
0x140004ccc  xor     r14d, r14d
0x140004ccf  mov     [rax-68h], r14d
0x140004cd3  mov     rax, [rcx+2C8h]
0x140004cda  mov     ebx, [rax+90h]
0x140004ce0  lea     eax, [rbx-1]
0x140004ce3  cmp     eax, 0FFFh
0x140004ce8  ja      loc_140005587
0x140004cee  mov     r15d, 1FFh
0x140004cf4  test    r15d, ebx
0x140004cf7  jnz     loc_140005587
0x140004cfd  xor     edx, edx
0x140004cff  mov     eax, 1000h
0x140004d04  div     ebx
0x140004d06  test    edx, edx
0x140004d08  jnz     loc_140005587
0x140004d0e  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140004d15  mov     rcx, [rsp+0B8h+arg_68]
0x140004d1d  mov     [rcx], rax
0x140004d20  mov     rax, [rsp+0B8h+arg_60]
0x140004d28  mov     [rax], r14
0x140004d2b  mov     rax, [rdi]
0x140004d2e  mov     rax, [rax+138h]
0x140004d35  mov     rcx, rdi
0x140004d38  call    _guard_dispatch_icall
0x140004d3d  test    al, al
0x140004d3f  jz      short loc_140004D64
0x140004d41  test    sil, sil
0x140004d44  jnz     short loc_140004D64
0x140004d46  mov     r12b, [rsp+0B8h+arg_30]
0x140004d4e  test    r12b, 4
0x140004d52  jnz     short loc_140004D6C
0x140004d54  test    r12b, 8
0x140004d58  jnz     short loc_140004D6C
0x140004d5a  mov     eax, 0C01A001Eh
0x140004d5f  jmp     loc_14000558C
0x140004d64  mov     r12b, [rsp+0B8h+arg_30]
0x140004d6c  mov     rax, [rdi]
0x140004d6f  mov     rax, [rax+138h]
0x140004d76  mov     rcx, rdi
0x140004d79  call    _guard_dispatch_icall
0x140004d7e  test    al, al
0x140004d80  jz      short loc_140004D95
0x140004d82  test    r12b, 4
0x140004d86  jnz     short loc_140004D8E
0x140004d88  test    r12b, 8
0x140004d8c  jz      short loc_140004DA7
0x140004d8e  mov     eax, 1
0x140004d93  jmp     short loc_140004DA3
0x140004d95  test    sil, sil
0x140004d98  jnz     short loc_140004DA0
0x140004d9a  test    r12b, 4
0x140004d9e  jz      short loc_140004DCA
0x140004da0  mov     eax, r14d
0x140004da3  test    eax, eax
0x140004da5  jnz     short loc_140004DCA
0x140004da7  mov     r9, rsi; BugCheckParameter3
0x140004daa  movzx   r8d, r12b; BugCheckParameter2
0x140004dae  mov     [rsp+0B8h+BugCheckParameter4], rdi; BugCheckParameter4
0x140004db3  mov     edx, 32h ; '2'; BugCheckParameter1
0x140004db8  mov     ecx, 0C1F5h; BugCheckCode
0x140004dbd  call    cs:__imp_KeBugCheckEx
0x140004dca  mov     rax, [rsp+0B8h+arg_38]
0x140004dd2  mov     eax, [rax]
0x140004dd4  test    r15, rax
0x140004dd7  jnz     loc_140005580
0x140004ddd  mov     rax, [rsp+0B8h+arg_48]
0x140004de5  mov     eax, [rax]
0x140004de7  test    r15, rax
0x140004dea  jnz     loc_140005580
0x140004df0  mov     r13, [rsp+0B8h+arg_40]
0x140004df8  mov     eax, [r13+0]
0x140004dfc  test    r15, rax
0x140004dff  jnz     loc_140005580
0x140004e05  mov     [rsp+0B8h+var_80], r14
0x140004e0a  mov     rsi, r14
0x140004e0d  mov     [rsp+0B8h+var_78], r14
0x140004e12  mov     r15d, r14d
0x140004e15  mov     [rsp+0B8h+var_84], r14d
0x140004e1a  mov     [rsp+0B8h+var_87], r14b
0x140004e1f  mov     [rsp+0B8h+var_88], r14b
0x140004e24  lea     rcx, [rdi+0C8h]; Resource
0x140004e2b  mov     dl, 1; Wait
0x140004e2d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140004e34  nop     dword ptr [rax+rax+00h]
0x140004e39  mov     [rsp+0B8h+var_87], al
0x140004e3d  test    dword ptr [rdi+16Ch], 1000h
0x140004e47  jz      short loc_140004E75
0x140004e49  mov     r15d, 0C01A002Bh
0x140004e4f  mov     [rsp+0B8h+var_84], r15d
0x140004e54  mov     r8d, r15d; int
0x140004e57  mov     edx, 8; unsigned int
0x140004e5c  mov     rcx, rdi; this
0x140004e5f  call    ?SetInvalidLogTag@CClfsLogFcbCommon@@QEAAXKJ@Z; CClfsLogFcbCommon::SetInvalidLogTag(ulong,long)
0x140004e64  lea     r14, [rdi+1D8h]
0x140004e6b  mov     r13b, [rsp+0B8h+var_88]
0x140004e70  jmp     loc_1400054FD
0x140004e75  lea     r14, [rdi+1D8h]
0x140004e7c  mov     r11, [r14]
0x140004e7f  mov     [rsp+0B8h+var_80], r11
0x140004e84  mov     al, r12b
0x140004e87  and     al, 4
0x140004e89  mov     [rsp+0B8h+var_86], al
0x140004e8d  jnz     loc_140004FCA
0x140004e93  mov     r9d, [rsp+0B8h+arg_20]
0x140004e9b  shl     r9, 9
0x140004e9f  mov     [rsp+0B8h+var_70], r9
0x140004ea4  mov     rax, [rsp+0B8h+arg_38]
0x140004eac  mov     r10, [rax]
0x140004eaf  add     r10, r11
0x140004eb2  mov     rdx, r10; unsigned __int64
0x140004eb5  mov     rcx, rdi; this
0x140004eb8  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x140004ebd  mov     r8, [rdi+1D0h]
0x140004ec4  sub     r8, rax
0x140004ec7  mov     rdx, r9; unsigned __int64
0x140004eca  mov     rcx, rdi; this
0x140004ecd  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x140004ed2  sub     r8, rax
0x140004ed5  mov     rdx, r11; unsigned __int64
0x140004ed8  mov     rcx, rdi; this
0x140004edb  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x140004ee0  add     r8, rax
0x140004ee3  mov     qword ptr [rsp+0B8h+var_50], rbx
0x140004ee8  xor     edx, edx
0x140004eea  mov     rax, r8
0x140004eed  div     rbx
0x140004ef0  test    rdx, rdx
0x140004ef3  jnz     loc_14000518B
0x140004ef9  test    r8, r8
0x140004efc  js      loc_140005117
0x140004f02  mov     rax, [rdi]
0x140004f05  mov     rax, [rax+128h]
0x140004f0c  mov     [rsp+0B8h+var_58], r10
0x140004f11  xor     r9d, r9d
0x140004f14  lea     r8, [rsp+0B8h+var_58]
0x140004f19  mov     rdx, [rsp+0B8h+arg_8]
0x140004f21  mov     rcx, rdi
0x140004f24  call    _guard_dispatch_icall
0x140004f29  mov     rdx, [rsp+0B8h+var_70]; unsigned __int64
0x140004f2e  mov     rcx, rdi; this
0x140004f31  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x140004f36  sub     [rdi+1D0h], rax
0x140004f3d  mov     rsi, [rdi+1D0h]
0x140004f44  mov     rbx, [rsp+0B8h+arg_48]
0x140004f4c  mov     rbx, [rbx]
0x140004f4f  sub     rbx, [r13+0]
0x140004f53  xor     edx, edx
0x140004f55  mov     rax, rbx
0x140004f58  mov     rcx, qword ptr [rsp+0B8h+var_50]
0x140004f5d  div     rcx
0x140004f60  test    rdx, rdx
0x140004f63  jnz     loc_1400050F2
0x140004f69  test    rbx, rbx
0x140004f6c  jle     loc_1400050AE
0x140004f72  mov     rax, rbx
0x140004f75  sub     rax, rsi
0x140004f78  test    rax, rax
0x140004f7b  jle     short loc_140004F81
0x140004f7d  mov     ebx, esi
0x140004f7f  jmp     short loc_140004F84
0x140004f81  mov     rsi, rbx
0x140004f84  xor     edx, edx
0x140004f86  mov     rax, rsi
0x140004f89  div     rcx
0x140004f8c  test    rdx, rdx
0x140004f8f  jnz     loc_140005089
0x140004f95  mov     rax, [rdi]
0x140004f98  mov     rax, [rax+128h]
0x140004f9f  mov     rdx, [r14]
0x140004fa2  add     rdx, rsi
0x140004fa5  mov     qword ptr [rsp+0B8h+var_50], rdx
0x140004faa  xor     r9d, r9d
0x140004fad  lea     r8, [rsp+0B8h+var_50]
0x140004fb2  mov     rdx, [rsp+0B8h+arg_8]
0x140004fba  mov     rcx, rdi
0x140004fbd  call    _guard_dispatch_icall
0x140004fc2  test    eax, eax
0x140004fc4  js      short loc_140004FCA
0x140004fc6  add     [r13+0], rsi
0x140004fca  cmp     [rsp+0B8h+arg_20], 0
0x140004fd2  jbe     short loc_140005010
0x140004fd4  test    r12b, 2
0x140004fd8  jnz     short loc_140005010
0x140004fda  mov     rcx, [rdi+1F8h]
0x140004fe1  mov     rdx, [rsp+0B8h+arg_18]
0x140004fe9  mov     [rdx+18h], rcx
0x140004fed  mov     al, [rsp+0B8h+arg_10]
0x140004ff4  mov     [rdx+3], al
0x140004ff7  movzx   eax, word ptr [rdx+4]
0x140004ffb  mov     [rdx+6], ax
0x140004fff  test    r12b, 1
0x140005003  jz      short loc_140005010
0x140005005  mov     rax, [rsp+0B8h+arg_70]
0x14000500d  mov     [rax], rcx
0x140005010  mov     dl, 1; Wait
0x140005012  mov     rcx, [rdi+580h]; Resource
0x140005019  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005020  nop     dword ptr [rax+rax+00h]
0x140005025  mov     r13b, al
0x140005028  mov     [rsp+0B8h+var_88], al
0x14000502c  xor     ebx, ebx
0x14000502e  mov     qword ptr [rsp+0B8h+var_68], rbx
0x140005033  mov     eax, [rsp+0B8h+arg_20]
0x14000503a  mov     [rsp+0B8h+var_70], rax
0x14000503f  mov     ecx, eax
0x140005041  shl     rcx, 9
0x140005045  cmp     rbx, rcx
0x140005048  jnb     loc_1400054C3
0x14000504e  lea     rcx, [rdi+1F8h]; plsn
0x140005055  call    ClfsLsnContainer
0x14000505a  mov     r12d, eax
0x14000505d  lea     rcx, ?m_laList@CClfsFlushElt@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140005064  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000506b  nop     dword ptr [rax+rax+00h]
0x140005070  test    rax, rax
0x140005073  jz      loc_1400051AD
0x140005079  mov     rcx, rax; this
0x14000507c  call    ??0CClfsFlushElt@@QEAA@XZ; CClfsFlushElt::CClfsFlushElt(void)
0x140005081  mov     rsi, rax
0x140005084  jmp     loc_1400051AF
0x140005089  mov     r9d, ebx; BugCheckParameter3
0x14000508c  shr     rsi, 20h
0x140005090  mov     [rsp+0B8h+BugCheckParameter4], rdi; BugCheckParameter4
0x140005095  mov     r8, rsi; BugCheckParameter2
0x140005098  mov     edx, 35h ; '5'; BugCheckParameter1
0x14000509d  mov     ecx, 0C1F5h; BugCheckCode
0x1400050a2  call    cs:__imp_KeBugCheckEx
0x1400050ae  jns     loc_140004FCA
0x1400050b4  mov     rax, [rdi]
0x1400050b7  mov     rax, [rax+128h]
0x1400050be  mov     rdx, [r14]
0x1400050c1  add     rdx, rbx
0x1400050c4  mov     [rsp+0B8h+var_70], rdx
0x1400050c9  xor     r9d, r9d
0x1400050cc  lea     r8, [rsp+0B8h+var_70]
0x1400050d1  mov     rdx, [rsp+0B8h+arg_8]
0x1400050d9  mov     rcx, rdi
0x1400050dc  call    _guard_dispatch_icall
0x1400050e1  test    eax, eax
0x1400050e3  js      loc_140004FCA
0x1400050e9  add     [r13+0], rbx
0x1400050ed  jmp     loc_140004FCA
0x1400050f2  mov     r9d, ebx; BugCheckParameter3
0x1400050f5  shr     rbx, 20h
0x1400050f9  mov     [rsp+0B8h+BugCheckParameter4], rdi; BugCheckParameter4
0x1400050fe  mov     r8, rbx; BugCheckParameter2
0x140005101  mov     edx, 34h ; '4'; BugCheckParameter1
0x140005106  mov     ecx, 0C1F5h; BugCheckCode
0x14000510b  call    cs:__imp_KeBugCheckEx
0x140005117  mov     rcx, [r13+0]
0x14000511b  add     rcx, r8
0x14000511e  jns     short loc_140005135
0x140005120  mov     r15d, 0C01A001Dh
0x140005126  mov     [rsp+0B8h+var_84], r15d
0x14000512b  mov     r13b, [rsp+0B8h+var_88]
0x140005130  jmp     loc_140005502
0x140005135  mov     [r13+0], rcx
0x140005139  mov     rax, [rdi]
0x14000513c  mov     r10, [rax+128h]
0x140005143  mov     rdx, r9; unsigned __int64
0x140005146  mov     rcx, rdi; this
0x140005149  call    ?RawSectorAlign@CClfsLogFcbPhysical@@AEBA_K_K@Z; CClfsLogFcbPhysical::RawSectorAlign(unsigned __int64)
0x14000514e  mov     rcx, [r14]
0x140005151  sub     rcx, rax
0x140005154  add     rcx, [rdi+1D0h]
0x14000515b  mov     [rsp+0B8h+var_60], rcx
0x140005160  xor     r9d, r9d
0x140005163  lea     r8, [rsp+0B8h+var_60]
0x140005168  mov     rdx, [rsp+0B8h+arg_8]
0x140005170  mov     rcx, rdi
0x140005173  mov     rax, r10
0x140005176  call    _guard_dispatch_icall
0x14000517b  mov     qword ptr [rdi+1D0h], 0
0x140005186  jmp     loc_140004FCA
0x14000518b  mov     r9d, r8d; BugCheckParameter3
0x14000518e  shr     r8, 20h; BugCheckParameter2
0x140005192  mov     [rsp+0B8h+BugCheckParameter4], rdi; BugCheckParameter4
0x140005197  mov     edx, 33h ; '3'; BugCheckParameter1
0x14000519c  mov     ecx, 0C1F5h; BugCheckCode
0x1400051a1  call    cs:__imp_KeBugCheckEx
0x1400051ad  xor     esi, esi
0x1400051af  mov     [rsp+0B8h+var_78], rsi
0x1400051b4  test    rsi, rsi
0x1400051b7  jnz     short loc_1400051E4
0x1400051b9  mov     edx, 0C0000001h
  ... truncated ...
```
