# CClfsLogFcbPhysical::CompleteFlush(void)

- ea: `0x140009420`
- end: `0x14000a222`
- name: `?CompleteFlush@CClfsLogFcbPhysical@@AEAAXXZ`
- size: `3586`
- prototype: `void __fastcall(CClfsLogFcbPhysical *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400093d0`

## callees

- `0x140003590`
- `0x140005f00`
- `0x1400075b0`
- `0x140009420`
- `0x14000a228`
- `0x14000a29c`
- `0x14000cd9c`
- `0x14000d6b8`
- `0x14000ed64`
- `0x1400121e4`
- `0x140016a08`
- `0x140016bec`
- `0x140017f20`
- `0x140017f80`
- `0x140018280`
- `0x140066cc0`
- `0x140066e90`
- `0x140067060`
- `0x140067458`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140009490`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400094ad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140009490`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400094ad`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000a1e1`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000a202`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14001908a`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400190b0`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000a1e1`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000a202`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14001908a`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400190b0`
- `ntoskrnl!ObfReferenceObject` at `0x140009b32`
- `ntoskrnl!ObfReferenceObject` at `0x140009b32`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1c0`
- `ntoskrnl!ObfDereferenceObject` at `0x140019056`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a1c0`
- `ntoskrnl!ObfDereferenceObject` at `0x140019056`
- `ntoskrnl!KeSetEvent` at `0x14000965a`
- `ntoskrnl!KeSetEvent` at `0x14000965a`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140009735`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140009735`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400096c7`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140009b09`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400096c7`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140009b09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400094ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000961d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400094ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000961d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000950f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000967a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000950f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000967a`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x140009c83`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x140009d35`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x140009c83`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x140009d35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e76`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140009d6e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140009d6e`

## string_xrefs

- `0x140009fce`: `CClfsLogFcbPhysical::CompleteFlush`
- `0x14000a122`: `CClfsLogFcbPhysical::CompleteFlush`
- `0x14000a181`: `CClfsLogFcbPhysical::CompleteFlush`

## pseudocode

```c
void __fastcall CClfsLogFcbPhysical::CompleteFlush(CClfsLogFcbPhysical *this)
{
  unsigned __int64 ullOffset; // rbx
  unsigned __int64 v3; // rdi
  CLFS_LSN v4; // rsi
  struct _FILE_OBJECT *v5; // r12
  BOOLEAN v6; // r13
  BOOLEAN v7; // r15
  KIRQL v8; // al
  int v9; // r15d
  union _CLS_LSN v10; // r13
  unsigned int v11; // r12d
  struct _LIST_ENTRY *v12; // rcx
  unsigned __int64 *v13; // r15
  unsigned int v14; // r9d
  CLFS_LSN v15; // rax
  unsigned int v16; // r8d
  unsigned int v17; // edx
  _DWORD *v18; // rbx
  KIRQL v19; // si
  _OWORD *v20; // rcx
  PIRP v21; // rax
  int v22; // esi
  PIRP v23; // rbx
  PLIST_ENTRY v24; // rax
  struct _LIST_ENTRY *Flink; // r15
  struct _LIST_ENTRY *v26; // rax
  struct _LIST_ENTRY *v27; // rbx
  CLFS_LSN v28; // rax
  __int64 v29; // rax
  __int64 Flink_high; // rcx
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rcx
  struct _LIST_ENTRY *v34; // rcx
  struct _LIST_ENTRY *v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned __int64 v38; // r8
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v42; // r9
  struct _LIST_ENTRY *v43; // rbx
  struct _FILE_OBJECT *Blink; // rax
  struct _LIST_ENTRY *v45; // rax
  unsigned __int64 v46; // rcx
  SIZE_T v47; // rax
  PVOID PoolWithTag; // rax
  CClfsLogFcbPhysical *v49; // rcx
  const CLFS_LSN *v50; // r15
  char v51; // r13
  char v52; // r12
  CLFS_CONTAINER_ID v53; // eax
  int v54; // r9d
  const CLFS_LSN *v55; // r15
  int v56; // eax
  struct _LIST_ENTRY *v57; // rax
  int v58; // eax
  int v59; // ebx
  int v60; // [rsp+20h] [rbp-138h]
  BOOLEAN v61; // [rsp+70h] [rbp-E8h]
  BOOLEAN v62; // [rsp+71h] [rbp-E7h]
  unsigned int P; // [rsp+78h] [rbp-E0h]
  unsigned int Pa; // [rsp+78h] [rbp-E0h]
  PVOID Pb; // [rsp+78h] [rbp-E0h]
  struct _LIST_ENTRY *v66; // [rsp+80h] [rbp-D8h]
  void *v67[2]; // [rsp+90h] [rbp-C8h]
  struct _FILE_OBJECT *Object; // [rsp+A8h] [rbp-B0h]
  CClfsBaseFile *v69; // [rsp+B0h] [rbp-A8h]
  CClfsBaseFile *v70; // [rsp+B0h] [rbp-A8h]
  unsigned __int64 PeekContext; // [rsp+B8h] [rbp-A0h] BYREF
  __int64 v72; // [rsp+C0h] [rbp-98h]
  CLFS_LSN v73; // [rsp+C8h] [rbp-90h]
  unsigned __int64 v74; // [rsp+D0h] [rbp-88h]
  CLFS_LSN plsn; // [rsp+D8h] [rbp-80h] BYREF
  union _CLS_LSN v76; // [rsp+E0h] [rbp-78h] BYREF
  int v77; // [rsp+E8h] [rbp-70h]
  CLFS_LSN v78; // [rsp+F8h] [rbp-60h]
  int v79; // [rsp+110h] [rbp-48h]
  int v80; // [rsp+114h] [rbp-44h]
  __int64 v81; // [rsp+168h] [rbp+10h] BYREF
  int v82; // [rsp+170h] [rbp+18h]
  int v83; // [rsp+178h] [rbp+20h]

  PeekContext = 0;
  v72 = 0;
  ullOffset = CLFS_LSN_INVALID.ullOffset;
  v3 = CLFS_LSN_INVALID.ullOffset;
  v4 = CLFS_LSN_INVALID;
  plsn = CLFS_LSN_INVALID;
  v5 = 0;
  Object = 0;
  HIDWORD(v67[0]) = 0;
  v67[1] = 0;
  v83 = 0;
  LOBYTE(v81) = 0;
  v6 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  v61 = v6;
  v7 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 176), 1u);
  v62 = v7;
  if ( *((_DWORD *)this + 327) || !*((_DWORD *)this + 333) )
  {
    _InterlockedIncrement((volatile signed __int32 *)&CClfsLogFcbCommon::m_cSpuriousCompleteFlush);
    goto LABEL_145;
  }
  CClfsLogFcbPhysical::ClearContainerQueue(this);
  v8 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)this + 120));
  v82 = *((_DWORD *)this + 350);
  v9 = v82;
  KeReleaseSpinLock(*((PKSPIN_LOCK *)this + 120), v8);
  LODWORD(v67[0]) = v9;
  if ( v9 < 0 && (*((_DWORD *)this + 334) & 2) != 0 && v9 != -1073741801 && v9 != -1073741670 && v9 != -1073741663 )
    *((_DWORD *)this + 91) |= 0x1000u;
  v10.ullOffset = -1;
  v11 = -1;
  while ( 1 )
  {
    v12 = (struct _LIST_ENTRY *)*((_QWORD *)this + 119);
    if ( v12->Flink == v12 )
      break;
    v24 = ExInterlockedRemoveHeadList(v12, *((PKSPIN_LOCK *)this + 120));
    Flink = v24[1].Flink;
    v66 = Flink;
    if ( (*((_DWORD *)this + 91) & 0x1000) != 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
      {
        v45 = Flink[6].Flink;
        if ( v45 )
        {
          ((void (__fastcall *)(CClfsLogFcbPhysical *, struct _LIST_ENTRY *))v45)(this, Flink[1].Blink);
          Flink[1].Blink = 0;
        }
      }
      v82 = -1072037845;
      LODWORD(v67[0]) = -1072037845;
    }
    else
    {
      v24->Blink = v24;
      v24->Flink = v24;
      if ( !HIDWORD(Flink[2].Blink) )
      {
        ullOffset = (unsigned __int64)Flink[3].Flink;
        v78.ullOffset = ullOffset;
        ExInterlockedInsertHeadList(*((PLIST_ENTRY *)this + 119), Flink + 13, *((PKSPIN_LOCK *)this + 120));
        break;
      }
      if ( CLFS_LSN_INVALID.ullOffset == v4.ullOffset )
      {
        v4 = (CLFS_LSN)Flink[3].Flink;
        plsn = v4;
      }
      _InterlockedAdd((volatile signed __int32 *)this + 330, -512 * LODWORD(Flink[2].Flink));
      if ( !Object )
      {
        Blink = (struct _FILE_OBJECT *)Flink[3].Blink;
        Object = Blink;
        if ( Blink )
          ObfReferenceObject(Blink);
      }
      if ( SLODWORD(Flink[9].Flink) >= 0 )
      {
        if ( (*((_DWORD *)this + 91) & 0x1000) != 0 )
        {
          v34 = Flink + 1;
        }
        else
        {
          if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this)
            && Flink[6].Flink )
          {
            *((_QWORD *)this + 173) = Flink[3].Flink;
            LOBYTE(v81) = 1;
          }
          v26 = Flink[9].Blink;
          v67[1] = (char *)v67[1] + (unsigned __int64)v26;
          *((_QWORD *)this + 694) += v26;
          if ( ((__int64)Flink[1].Flink & 0x20) != 0 )
          {
            P = LODWORD(Flink[2].Flink) << 9;
            v27 = Flink + 3;
            if ( Flink != (struct _LIST_ENTRY *)-48LL
              && (v28 = CLFS_LSN_INVALID, (struct _LIST_ENTRY *)CLFS_LSN_INVALID.ullOffset == v27->Flink) )
            {
              v73 = CLFS_LSN_INVALID;
              ullOffset = CLFS_LSN_INVALID.ullOffset;
              v78 = CLFS_LSN_INVALID;
              v34 = Flink + 1;
            }
            else
            {
              if ( !CClfsLogFcbPhysical::ValidateContainerSize(this) )
              {
                v28 = CLFS_LSN_INVALID;
                v73 = CLFS_LSN_INVALID;
                ullOffset = CLFS_LSN_INVALID.ullOffset;
                goto LABEL_53;
              }
              v29 = 0xFFFFFFFFLL;
              if ( Flink != (struct _LIST_ENTRY *)-48LL )
                v29 = (__int64)v27->Flink & 0xFFFFFE00;
              Flink_high = 0xFFFFFFFFLL;
              if ( Flink != (struct _LIST_ENTRY *)-48LL )
                Flink_high = HIDWORD(Flink[3].Flink);
              v31 = *((_QWORD *)this + 87);
              v32 = (v29 + v31 * Flink_high + P) % v31;
              v33 = (v29 + v31 * Flink_high + P) / v31;
              if ( HIDWORD(v33) )
              {
                v28 = CLFS_LSN_INVALID;
                v73 = CLFS_LSN_INVALID;
                ullOffset = CLFS_LSN_INVALID.ullOffset;
                v78 = CLFS_LSN_INVALID;
                v34 = Flink + 1;
              }
              else if ( HIDWORD(v32) )
              {
                v28 = CLFS_LSN_INVALID;
                v73 = CLFS_LSN_INVALID;
                ullOffset = CLFS_LSN_INVALID.ullOffset;
                v78 = CLFS_LSN_INVALID;
                v34 = Flink + 1;
              }
              else
              {
                if ( (_DWORD)v33 == -1 || (v32 & 0x1FF) != 0 )
                {
                  v28 = CLFS_LSN_INVALID;
                  ullOffset = CLFS_LSN_INVALID.ullOffset;
                }
                else
                {
                  ullOffset = (unsigned int)v32 | ((unsigned __int64)(unsigned int)v33 << 32);
                  v28 = CLFS_LSN_INVALID;
                }
                v73.ullOffset = ullOffset;
LABEL_53:
                v78.ullOffset = ullOffset;
                v34 = Flink + 1;
              }
            }
LABEL_67:
            if ( ((__int64)v34->Flink & 0x40) == 0 )
            {
              Pa = LODWORD(Flink[2].Flink) << 9;
              v35 = Flink + 3;
              if ( Flink != (struct _LIST_ENTRY *)-48LL && (struct _LIST_ENTRY *)v28.ullOffset == v35->Flink )
              {
                v74 = v28.ullOffset;
                v3 = v28.ullOffset;
              }
              else
              {
                if ( !CClfsLogFcbPhysical::ValidateContainerSize(this) )
                  goto LABEL_90;
                v36 = 0xFFFFFFFFLL;
                if ( Flink != (struct _LIST_ENTRY *)-48LL )
                  v36 = (__int64)v35->Flink & 0xFFFFFE00;
                v37 = 0xFFFFFFFFLL;
                if ( Flink != (struct _LIST_ENTRY *)-48LL )
                  v37 = HIDWORD(Flink[3].Flink);
                v38 = *((_QWORD *)this + 87);
                v39 = (v36 + v38 * v37 + Pa) % v38;
                v40 = (v36 + v38 * v37 + Pa) / v38;
                if ( HIDWORD(v40) || HIDWORD(v39) || (_DWORD)v40 == -1 || (v39 & 0x1FF) != 0 )
                {
LABEL_90:
                  v3 = CLFS_LSN_INVALID.ullOffset;
                }
                else
                {
                  v80 = v40;
                  v79 = v39;
                  v3 = (unsigned int)v39 | ((unsigned __int64)(unsigned int)v40 << 32);
                }
                v74 = v3;
              }
            }
            goto LABEL_81;
          }
          v34 = Flink + 1;
        }
        v28 = CLFS_LSN_INVALID;
        goto LABEL_67;
      }
      v46 = ((unsigned __int64)*((unsigned __int16 *)this + 160) >> 1) + 1;
      v47 = 2 * v46;
      if ( !is_mul_ok(v46, 2u) )
        v47 = -1;
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, v47, 0x73666C43u);
      Pb = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, *((unsigned __int16 *)this + 160) + 2LL);
        memmove(Pb, *((const void **)this + 41), *((unsigned __int16 *)this + 160));
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
        {
          v50 = (const CLFS_LSN *)&Flink[3];
          v51 = ClfsLsnRecordSequence(v50);
          v52 = ClfsLsnBlockOffset(v50);
          v53 = ClfsLsnContainer(v50);
          Flink = v66;
          WPP_SF_slSiDDDiDD(
            *((_QWORD *)v69 + 3),
            LODWORD(v66[9].Blink) >> 9,
            v53,
            v54,
            v60,
            (__int64)Pb,
            (char)v66,
            v53,
            v52,
            v51,
            (unsigned __int64)LODWORD(v66[9].Blink) >> 9,
            (char)v66[2].Flink,
            (char)v66[9].Flink);
          v11 = -1;
          v10.ullOffset = -1;
        }
        ExFreePoolWithTag(Pb, 0);
      }
      else
      {
        v70 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
        {
          v55 = (const CLFS_LSN *)&Flink[3];
          ClfsLsnRecordSequence(v55);
          ClfsLsnBlockOffset(v55);
          ClfsLsnContainer(v55);
          Flink = v66;
          WPP_SF_sliiDDDDDD(*((_QWORD *)v70 + 3));
          v11 = -1;
          v10.ullOffset = -1;
        }
      }
      if ( v82 >= 0 )
      {
        v82 = (int)Flink[9].Flink;
        LODWORD(v67[0]) = v82;
      }
      v67[1] = (char *)v67[1] + LODWORD(Flink[9].Blink);
      if ( (*((_DWORD *)this + 334) & 2) == 0
        && (*((_DWORD *)this + 91) & 0x1000) == 0
        && CClfsLogFcbPhysical::IsRetryableFlushError(v49, (int)Flink[9].Flink) )
      {
        ++LODWORD(Flink[2].Blink);
        HIDWORD(Flink[2].Blink) = 0;
        LOBYTE(Flink[1].Flink) |= 0x11u;
        ExInterlockedInsertHeadList(*((PLIST_ENTRY *)this + 119), Flink + 13, *((PKSPIN_LOCK *)this + 120));
        _InterlockedAdd((volatile signed __int32 *)this + 330, LODWORD(Flink[2].Flink) << 9);
        break;
      }
      *((_DWORD *)this + 91) |= 0x21000u;
      if ( !*((_DWORD *)this + 149) )
      {
        v56 = (int)Flink[9].Flink;
        *((_DWORD *)this + 149) = 7;
        *((_DWORD *)this + 150) = v56;
      }
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slid(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          56,
          (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
          (unsigned int)"CClfsLogFcbPhysical::CompleteFlush",
          222,
          (char)this,
          (char)Flink[9].Flink);
      }
      if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
      {
        v57 = Flink[6].Flink;
        if ( v57 )
        {
          ((void (__fastcall *)(CClfsLogFcbPhysical *, struct _LIST_ENTRY *))v57)(this, Flink[1].Blink);
          Flink[1].Blink = 0;
        }
      }
      v3 = *(_QWORD *)CClfsLogFcbPhysical::AddLsnOffset(this, &v76, (int)Flink + 48).ullOffset;
    }
LABEL_81:
    ((void (__fastcall *)(struct _LIST_ENTRY **))Flink->Blink->Blink)(&Flink->Blink);
  }
  v13 = (unsigned __int64 *)((char *)this + 480);
  if ( CLFS_LSN_INVALID.ullOffset != ullOffset )
    *v13 = ullOffset;
  if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
  {
    if ( (_BYTE)v81 )
    {
      if ( v82 >= 0 )
      {
        v58 = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 112LL))(this);
        v59 = v58;
        v83 = v58;
        v77 = v58;
        if ( v58 < 0 )
        {
          *((_DWORD *)this + 91) |= 0x21000u;
          if ( !*((_DWORD *)this + 149) )
          {
            *((_DWORD *)this + 149) = 8;
            *((_DWORD *)this + 150) = v58;
          }
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
          {
            WPP_SF_slid(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              57,
              (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
              (unsigned int)"CClfsLogFcbPhysical::CompleteFlush",
              128,
              (char)this,
              v58);
          }
          v82 = v59;
          LODWORD(v67[0]) = v59;
        }
      }
    }
  }
  ++*((_QWORD *)this + 693);
  v15 = CLFS_LSN_INVALID;
  if ( this == (CClfsLogFcbPhysical *)-480LL || CLFS_LSN_INVALID.ullOffset != *v13 )
  {
    v16 = -1;
    if ( this != (CClfsLogFcbPhysical *)-1368LL )
      v16 = *((_DWORD *)this + 342) & 0xFFFFFE00;
    v14 = -1;
    if ( this != (CClfsLogFcbPhysical *)-1368LL )
      v14 = *((_DWORD *)this + 343);
    v17 = -1;
    if ( this != (CClfsLogFcbPhysical *)-480LL )
    {
      v17 = *(_DWORD *)v13 & 0xFFFFFE00;
      v11 = *((_DWORD *)this + 121);
    }
    v10.ullOffset = v17 + *((_QWORD *)this + 87) * (v11 - (unsigned __int64)v14) - v16;
  }
  v76 = v10;
  v5 = Object;
  if ( Object && (__int64)v10.ullOffset > *((_QWORD *)this + 11) )
  {
    v81 = *((_QWORD *)this + 57);
    CClfsLogFcbPhysical::SetCacheFileSizes(this, Object, (const __int64 *)&v76, &v81);
    v15 = CLFS_LSN_INVALID;
  }
  v18 = (_DWORD *)((char *)this + 364);
  if ( v15.ullOffset != v4.ullOffset && (*v18 & 0x1000) == 0 )
    CClfsLogFcbPhysical::PurgeCacheSection(this, &plsn, (CLFS_LSN *)this + 60, v14);
  v19 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)this + 120));
  v20 = (_OWORD *)*((_QWORD *)this + 169);
  if ( v20 )
  {
    *v20 = *(_OWORD *)v67;
    *((_QWORD *)this + 169) = 0;
  }
  KeSetEvent(*((PRKEVENT *)this + 170), 0, 0);
  _InterlockedExchange((volatile __int32 *)this + 333, 0);
  KeReleaseSpinLock(*((PKSPIN_LOCK *)this + 120), v19);
  if ( CLFS_LSN_INVALID.ullOffset == v3 )
  {
    if ( (*v18 & 0x1000) != 0 )
    {
      v82 = -1072037845;
      if ( !*((_DWORD *)this + 147) )
      {
        *((_DWORD *)this + 147) = 11;
        *((_DWORD *)this + 148) = v83;
      }
    }
    else
    {
      v3 = *v13;
    }
  }
  LODWORD(v72) = -2147014612;
  PeekContext = v3;
  BYTE4(v72) = 0;
  v21 = IoCsqRemoveNextIrp((PIO_CSQ)((char *)this + 1000), &PeekContext);
  v22 = v82;
  while ( 1 )
  {
    v23 = v21;
    if ( !v21 )
      break;
    CurrentStackLocation = v21->Tail.Overlay.CurrentStackLocation;
    v42 = (unsigned int)v22;
    if ( CurrentStackLocation->MajorFunction == 14
      && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == -2146981849
      && v22 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          58,
          (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
          (unsigned int)"CClfsLogFcbPhysical::CompleteFlush",
          24,
          v22);
      }
      v42 = 3222929455LL;
    }
    v43 = v23->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
    ((void (__fastcall *)(struct _LIST_ENTRY *, char *, __int64, __int64))v43->Flink[5].Flink)(
      v43,
      (char *)this + 480,
      8,
      v42);
    ((void (__fastcall *)(struct _LIST_ENTRY *))v43->Flink->Blink)(v43);
    v21 = IoCsqRemoveNextIrp((PIO_CSQ)((char *)this + 1000), &PeekContext);
  }
  if ( BYTE4(v72) )
    CClfsLogFcbPhysical::QueueFlushWorker(this);
  if ( v82 >= 0 && v67[1] )
    CClfsLogFcbCommon::NotifyObservers(this, 0xCF05u, v67[1], 0);
  v7 = v62;
  v6 = v61;
LABEL_145:
  if ( v5 )
    ObfDereferenceObject(v5);
  if ( v6 )
    ExReleaseResourceForThreadLite((PERESOURCE)((char *)this + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
  if ( v7 )
    ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 176), (ERESOURCE_THREAD)KeGetCurrentThread());
}

```

## disassembly

```asm
0x140009420  mov     r11, rsp
0x140009423  mov     [r11+8], rcx
0x140009427  push    rbx
0x140009428  push    rsi
0x140009429  push    rdi
0x14000942a  push    r12
0x14000942c  push    r13
0x14000942e  push    r14
0x140009430  push    r15
0x140009432  sub     rsp, 120h
0x140009439  mov     r14, rcx
0x14000943c  xor     ecx, ecx
0x14000943e  mov     [r11-0A0h], rcx
0x140009445  mov     [r11-98h], rcx
0x14000944c  mov     rbx, qword ptr cs:CLFS_LSN_INVALID
0x140009453  mov     rdi, rbx
0x140009456  mov     rsi, rbx
0x140009459  mov     [r11-80h], rbx
0x14000945d  mov     r12d, ecx
0x140009460  mov     [r11-0B0h], rcx
0x140009467  xor     eax, eax
0x140009469  mov     dword ptr [rsp+158h+var_C8+4], eax
0x140009470  mov     [r11-0C0h], rcx
0x140009477  mov     [r11+20h], ecx
0x14000947b  mov     [rsp+158h+var_E7], al
0x14000947f  mov     [rsp+158h+var_E8], al
0x140009483  mov     [r11+10h], al
0x140009487  lea     rcx, [r14+0C8h]; Resource
0x14000948e  mov     dl, 1; Wait
0x140009490  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140009497  nop     dword ptr [rax+rax+00h]
0x14000949c  movzx   r13d, al
0x1400094a0  mov     [rsp+158h+var_E8], al
0x1400094a4  mov     dl, 1; Wait
0x1400094a6  mov     rcx, [r14+580h]; Resource
0x1400094ad  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400094b4  nop     dword ptr [rax+rax+00h]
0x1400094b9  movzx   r15d, al
0x1400094bd  mov     [rsp+158h+var_E7], al
0x1400094c1  cmp     [r14+51Ch], r12d
0x1400094c8  jnz     loc_140009C0E
0x1400094ce  cmp     [r14+534h], r12d
0x1400094d5  jz      loc_140009CE2
0x1400094db  mov     rcx, r14; this
0x1400094de  call    ?ClearContainerQueue@CClfsLogFcbPhysical@@AEAAXXZ; CClfsLogFcbPhysical::ClearContainerQueue(void)
0x1400094e3  mov     rcx, [r14+3C0h]; SpinLock
0x1400094ea  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400094f1  nop     dword ptr [rax+rax+00h]
0x1400094f6  mov     r15d, [r14+578h]
0x1400094fd  mov     [rsp+158h+arg_10], r15d
0x140009505  movzx   edx, al; NewIrql
0x140009508  mov     rcx, [r14+3C0h]; SpinLock
0x14000950f  call    cs:__imp_KeReleaseSpinLock
0x140009516  nop     dword ptr [rax+rax+00h]
0x14000951b  mov     dword ptr [rsp+158h+var_C8], r15d
0x140009523  test    r15d, r15d
0x140009526  js      loc_140009911
0x14000952c  mov     r13, 0FFFFFFFFFFFFFFFFh
0x140009533  mov     r12d, 0FFFFFFFFh
0x140009539  mov     rcx, [r14+3B8h]; ListHead
0x140009540  cmp     [rcx], rcx
0x140009543  jnz     loc_14000972E
0x140009549  lea     r15, [r14+1E0h]
0x140009550  cmp     qword ptr cs:CLFS_LSN_INVALID, rbx
0x140009557  jnz     loc_1400098E5
0x14000955d  mov     rax, [r14]
0x140009560  mov     rax, [rax+138h]
0x140009567  mov     rcx, r14
0x14000956a  call    _guard_dispatch_icall
0x14000956f  test    al, al
0x140009571  jnz     loc_14000A086
0x140009577  inc     qword ptr [r14+15A8h]
0x14000957e  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140009585  test    r15, r15
0x140009588  jz      short loc_14000958F
0x14000958a  cmp     rax, [r15]
0x14000958d  jz      short loc_1400095ED
0x14000958f  lea     rcx, [r14+558h]
0x140009596  mov     r8d, r12d
0x140009599  test    rcx, rcx
0x14000959c  jz      short loc_1400095A8
0x14000959e  mov     r8d, [rcx]
0x1400095a1  and     r8d, 0FFFFFE00h
0x1400095a8  mov     r9d, r12d
0x1400095ab  test    rcx, rcx
0x1400095ae  jz      short loc_1400095B4
0x1400095b0  mov     r9d, [rcx+4]; unsigned __int8
0x1400095b4  mov     r10, [r14+2B8h]
0x1400095bb  mov     edx, r12d
0x1400095be  test    r15, r15
0x1400095c1  jz      short loc_1400095D5
0x1400095c3  mov     edx, [r15]
0x1400095c6  and     edx, 0FFFFFE00h
0x1400095cc  test    r15, r15
0x1400095cf  jz      short loc_1400095D5
0x1400095d1  mov     r12d, [r15+4]
0x1400095d5  mov     r13d, r12d
0x1400095d8  mov     ecx, r9d
0x1400095db  sub     r13, rcx
0x1400095de  imul    r13, r10
0x1400095e2  mov     ecx, r8d
0x1400095e5  sub     r13, rcx
0x1400095e8  mov     ecx, edx
0x1400095ea  add     r13, rcx
0x1400095ed  mov     qword ptr [rsp+158h+var_78], r13
0x1400095f5  mov     r12, [rsp+158h+Object]
0x1400095fd  test    r12, r12
0x140009600  jnz     loc_140009973
0x140009606  lea     rbx, [r14+16Ch]
0x14000960d  cmp     rax, rsi
0x140009610  jnz     loc_1400098ED
0x140009616  mov     rcx, [r14+3C0h]; SpinLock
0x14000961d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009624  nop     dword ptr [rax+rax+00h]
0x140009629  movzx   esi, al
0x14000962c  mov     rcx, [r14+548h]
0x140009633  test    rcx, rcx
0x140009636  jz      short loc_14000964E
0x140009638  movups  xmm0, xmmword ptr [rsp+158h+var_C8]
0x140009640  movups  xmmword ptr [rcx], xmm0
0x140009643  mov     qword ptr [r14+548h], 0
0x14000964e  xor     r8d, r8d; Wait
0x140009651  xor     edx, edx; Increment
0x140009653  mov     rcx, [r14+550h]; Event
0x14000965a  call    cs:__imp_KeSetEvent
0x140009661  nop     dword ptr [rax+rax+00h]
0x140009666  xor     eax, eax
0x140009668  xchg    eax, [r14+534h]
0x14000966f  movzx   edx, sil; NewIrql
0x140009673  mov     rcx, [r14+3C0h]; SpinLock
0x14000967a  call    cs:__imp_KeReleaseSpinLock
0x140009681  nop     dword ptr [rax+rax+00h]
0x140009686  cmp     qword ptr cs:CLFS_LSN_INVALID, rdi
0x14000968d  jz      loc_140009957
0x140009693  mov     [rsp+158h+var_98], 8007282Ch
0x14000969e  mov     [rsp+158h+PeekContext], edi
0x1400096a5  shr     rdi, 20h
0x1400096a9  mov     [rsp+158h+var_9C], edi
0x1400096b0  mov     [rsp+158h+var_94], 0
0x1400096b8  lea     rdx, [rsp+158h+PeekContext]; PeekContext
0x1400096c0  lea     rcx, [r14+3E8h]; Csq
0x1400096c7  call    cs:__imp_IoCsqRemoveNextIrp
0x1400096ce  nop     dword ptr [rax+rax+00h]
0x1400096d3  mov     esi, [rsp+158h+arg_10]
0x1400096da  mov     rbx, rax
0x1400096dd  test    rax, rax
0x1400096e0  jnz     loc_140009AA1
0x1400096e6  cmp     [rsp+158h+var_94], al
0x1400096ed  jnz     loc_14000A1AB
0x1400096f3  cmp     [rsp+158h+arg_10], 0
0x1400096fb  jl      short loc_14000971D
0x1400096fd  mov     rax, [rsp+158h+var_C8+8]
0x140009705  test    rax, rax
0x140009708  jz      short loc_14000971D
0x14000970a  xor     r9d, r9d; void *
0x14000970d  mov     r8, rax; void *
0x140009710  mov     edx, 0CF05h; unsigned int
0x140009715  mov     rcx, r14; this
0x140009718  call    ?NotifyObservers@CClfsLogFcbCommon@@QEAAJKPEAX0@Z; CClfsLogFcbCommon::NotifyObservers(ulong,void *,void *)
0x14000971d  movzx   r15d, [rsp+158h+var_E7]
0x140009723  movzx   r13d, [rsp+158h+var_E8]
0x140009729  jmp     loc_14000A1B8
0x14000972e  mov     rdx, [r14+3C0h]; Lock
0x140009735  call    cs:__imp_ExInterlockedRemoveHeadList
0x14000973c  nop     dword ptr [rax+rax+00h]
0x140009741  mov     r15, [rax+10h]
0x140009745  mov     [rsp+158h+var_D8], r15
0x14000974d  test    dword ptr [r14+16Ch], 1000h
0x140009758  jnz     loc_140009BB5
0x14000975e  mov     [rax+8], rax
0x140009762  mov     [rax], rax
0x140009765  cmp     dword ptr [r15+2Ch], 0
0x14000976a  jz      loc_140009D14
0x140009770  cmp     qword ptr cs:CLFS_LSN_INVALID, rsi
0x140009777  jnz     short loc_140009785
0x140009779  mov     rsi, [r15+30h]
0x14000977d  mov     qword ptr [rsp+158h+plsn], rsi
0x140009785  mov     eax, [r15+20h]
0x140009789  shl     eax, 9
0x14000978c  neg     eax
0x14000978e  lock add [r14+528h], eax
0x140009796  cmp     [rsp+158h+Object], 0
0x14000979f  jz      loc_140009B1A
0x1400097a5  cmp     dword ptr [r15+90h], 0
0x1400097ad  jl      loc_140009D46
0x1400097b3  test    dword ptr [r14+16Ch], 1000h
0x1400097be  jnz     loc_1400099B3
0x1400097c4  mov     rax, [r14]
0x1400097c7  mov     rax, [rax+138h]
0x1400097ce  mov     rcx, r14
0x1400097d1  call    _guard_dispatch_icall
0x1400097d6  test    al, al
0x1400097d8  jnz     loc_14000A044
0x1400097de  mov     rax, [r15+98h]
0x1400097e5  add     [rsp+158h+var_C8+8], rax
0x1400097ed  add     [r14+15B0h], rax
0x1400097f4  lea     rax, [r15+10h]
0x1400097f8  mov     [rsp+158h+var_D8], rax
0x140009800  test    byte ptr [rax], 20h
0x140009803  jz      loc_140009A99
0x140009809  mov     eax, [r15+20h]
0x14000980d  shl     eax, 9
0x140009810  mov     dword ptr [rsp+158h+P], eax
0x140009814  lea     rbx, [r15+30h]
0x140009818  xor     eax, eax
0x14000981a  mov     [rsp+158h+var_A8], rax
0x140009822  test    rbx, rbx
0x140009825  jz      short loc_140009837
0x140009827  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14000982e  cmp     rax, [rbx]
0x140009831  jz      loc_140009B43
0x140009837  mov     rcx, r14; this
0x14000983a  call    ?ValidateContainerSize@CClfsLogFcbPhysical@@AEAAEXZ; CClfsLogFcbPhysical::ValidateContainerSize(void)
0x14000983f  test    al, al
0x140009841  jz      loc_14000A06F
0x140009847  mov     eax, r12d
0x14000984a  test    rbx, rbx
0x14000984d  jz      short loc_140009856
0x14000984f  mov     eax, [rbx]
0x140009851  and     eax, 0FFFFFE00h
0x140009856  mov     ecx, r12d
0x140009859  test    rbx, rbx
0x14000985c  jz      short loc_140009861
0x14000985e  mov     ecx, [rbx+4]
0x140009861  mov     r8, [r14+2B8h]
0x140009868  imul    rcx, r8
0x14000986c  add     rcx, rax
0x14000986f  mov     eax, dword ptr [rsp+158h+P]
0x140009873  add     rax, rcx
0x140009876  xor     edx, edx
0x140009878  div     r8
0x14000987b  mov     rcx, rax
0x14000987e  shr     rax, 20h
0x140009882  test    eax, eax
0x140009884  jnz     loc_140009BE7
0x14000988a  mov     rax, rdx
0x14000988d  shr     rax, 20h
0x140009891  test    eax, eax
0x140009893  jnz     loc_140009B7F
0x140009899  cmp     ecx, r12d
0x14000989c  jz      loc_140009BA6
0x1400098a2  test    edx, 1FFh
0x1400098a8  jnz     loc_140009BA6
0x1400098ae  mov     dword ptr [rsp+158h+P+4], ecx
0x1400098b2  mov     dword ptr [rsp+158h+P], edx
0x1400098b6  mov     ebx, ecx
0x1400098b8  shl     rbx, 20h
0x1400098bc  mov     eax, edx
0x1400098be  or      rbx, rax
0x1400098c1  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400098c8  mov     [rsp+158h+var_90], rbx
0x1400098d0  mov     [rsp+158h+var_60], rbx
0x1400098d8  mov     rcx, [rsp+158h+var_D8]
0x1400098e0  jmp     loc_1400099BE
0x1400098e5  mov     [r15], rbx
0x1400098e8  jmp     loc_14000955D
0x1400098ed  test    dword ptr [rbx], 1000h
0x1400098f3  jnz     loc_140009616
0x1400098f9  mov     r8, r15; CLFS_LSN *
0x1400098fc  lea     rdx, [rsp+158h+plsn]; plsn
0x140009904  mov     rcx, r14; this
0x140009907  call    ?PurgeCacheSection@CClfsLogFcbPhysical@@AEAAEAEBT_CLS_LSN@@0E@Z; CClfsLogFcbPhysical::PurgeCacheSection(_CLS_LSN const &,_CLS_LSN const &,uchar)
0x14000990c  jmp     loc_140009616
0x140009911  mov     eax, [r14+538h]
0x140009918  test    al, 2
0x14000991a  jz      loc_14000952C
0x140009920  cmp     r15d, 0C0000017h
0x140009927  jz      loc_14000952C
0x14000992d  cmp     r15d, 0C000009Ah
0x140009934  jz      loc_14000952C
0x14000993a  cmp     r15d, 0C00000A1h
0x140009941  jz      loc_14000952C
0x140009947  or      dword ptr [r14+16Ch], 1000h
0x140009952  jmp     loc_14000952C
0x140009957  test    dword ptr [rbx], 1000h
0x14000995d  jnz     loc_140009CA3
0x140009963  mov     rdi, [r15]
0x140009966  mov     [rsp+158h+var_D8], rdi
0x14000996e  jmp     loc_140009693
0x140009973  cmp     r13, [r14+58h]
0x140009977  jle     loc_140009606
0x14000997d  mov     rax, [r14+1C8h]
0x140009984  mov     [rsp+158h+arg_8], rax
0x14000998c  lea     r9, [rsp+158h+arg_8]; __int64 *
0x140009994  lea     r8, [rsp+158h+var_78]; __int64 *
0x14000999c  mov     rdx, r12; struct _FILE_OBJECT *
0x14000999f  mov     rcx, r14; this
0x1400099a2  call    ?SetCacheFileSizes@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@AEB_J1@Z; CClfsLogFcbPhysical::SetCacheFileSizes(_FILE_OBJECT *,__int64 const &,__int64 const &)
0x1400099a7  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400099ae  jmp     loc_140009606
0x1400099b3  lea     rcx, [r15+10h]
0x1400099b7  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400099be  test    byte ptr [rcx], 40h
0x1400099c1  jnz     loc_140009A84
0x1400099c7  mov     ecx, [r15+20h]
0x1400099cb  shl     ecx, 9
0x1400099ce  mov     dword ptr [rsp+158h+P], ecx
0x1400099d2  lea     rdi, [r15+30h]
0x1400099d6  test    rdi, rdi
0x1400099d9  jz      short loc_1400099E4
  ... truncated ...
```
