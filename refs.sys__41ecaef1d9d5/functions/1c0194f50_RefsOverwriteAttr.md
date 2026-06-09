# RefsOverwriteAttr

- ea: `0x1c0194f50`
- end: `0x1c0195c3d`
- name: `RefsOverwriteAttr`
- size: `3309`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, PIRP Irp@<rdx>, POPLOCK_FS_PREPOST_IRP, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1c0153d80`

## callees

- `0x1c0002ef8`
- `0x1c0003658`
- `0x1c0003fb0`
- `0x1c0004300`
- `0x1c000f770`
- `0x1c003a41c`
- `0x1c003b830`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c014fe2c`
- `0x1c01521ec`
- `0x1c0152814`
- `0x1c0154578`
- `0x1c0154d5c`
- `0x1c015ac58`
- `0x1c015d78c`
- `0x1c01632d4`
- `0x1c0190b78`
- `0x1c0194f50`
- `0x1c0195c44`
- `0x1c0195e8c`
- `0x1c01960f8`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x1c0195b90`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c0195b90`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c0195ab9`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c0195ab9`
- `ntoskrnl!FsRtlOplockBreakH` at `0x1c0195606`
- `ntoskrnl!FsRtlOplockBreakH` at `0x1c0195606`

## string_xrefs

- `0x1c0195376`: `Create.c`
- `0x1c01954b0`: `Create.c`
- `0x1c0195668`: `Create.c`
- `0x1c01956f4`: `Create.c`
- `0x1c0195b13`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsOverwriteAttr(
        PVOID Context,
        PIRP Irp,
        __int64 a3,
        char a4,
        POPLOCK_FS_PREPOST_IRP a5,
        __int16 *a6,
        int a7,
        int a8,
        __int64 a9)
{
  __int64 v11; // rcx
  int v12; // r14d
  __int64 v13; // r15
  __int16 v14; // dx
  __int16 v15; // r8
  __int16 v16; // ax
  __int64 result; // rax
  int v18; // edi
  __int64 v19; // rdx
  char IsMinstoreTransactionActive; // bl
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  char v24; // r10
  __int64 v25; // rdx
  int v26; // ebx
  int v27; // ecx
  int v28; // r10d
  int v29; // r8d
  __int64 v30; // rcx
  int v31; // r9d
  int v32; // edx
  __int16 StreamChecksumType; // bx
  int v34; // r11d
  __int64 v35; // rcx
  int *v36; // r9
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // edx
  int v41; // ecx
  int v42; // r14d
  __int64 v43; // rdx
  int v44; // eax
  int v45; // ebx
  __int64 v46; // rdx
  NTSTATUS v47; // eax
  NTSTATUS v48; // r13d
  __int64 v49; // r8
  int v50; // r9d
  int v51; // eax
  int v52; // edx
  __int64 v53; // rax
  __int64 v54; // rdx
  int v55; // r13d
  __int64 NextChildScb; // rbx
  __int64 v57; // rdi
  int v58; // ebx
  int v59; // ecx
  __int64 v60; // rbx
  PIRP v61; // r14
  int v62; // edx
  int v63; // edx
  int v64; // edx
  BOOLEAN CanFileBeTruncated; // al
  void (__stdcall *PostIrpRoutine)(PVOID, PIRP); // [rsp+28h] [rbp-1F0h]
  __int16 v68; // [rsp+84h] [rbp-194h]
  int v69; // [rsp+88h] [rbp-190h]
  __int16 v70; // [rsp+8Ch] [rbp-18Ch]
  int v71; // [rsp+90h] [rbp-188h]
  int v72; // [rsp+90h] [rbp-188h]
  int v73[3]; // [rsp+94h] [rbp-184h] BYREF
  int v74; // [rsp+A0h] [rbp-178h]
  PIRP Irpa; // [rsp+A8h] [rbp-170h]
  int v76; // [rsp+B0h] [rbp-168h]
  int v77; // [rsp+B4h] [rbp-164h]
  int *v78; // [rsp+B8h] [rbp-160h]
  int v79[2]; // [rsp+C0h] [rbp-158h]
  int v80; // [rsp+C8h] [rbp-150h]
  int v81; // [rsp+CCh] [rbp-14Ch]
  int v82; // [rsp+D0h] [rbp-148h]
  int v83[2]; // [rsp+D8h] [rbp-140h]
  __int64 v84; // [rsp+E0h] [rbp-138h]
  PVOID v85; // [rsp+E8h] [rbp-130h]
  __int64 v86; // [rsp+F0h] [rbp-128h]
  __int64 v87; // [rsp+F8h] [rbp-120h]
  _BYTE v88[208]; // [rsp+100h] [rbp-118h] BYREF

  *(_QWORD *)v79 = a3;
  Irpa = Irp;
  *(_QWORD *)v83 = Context;
  v85 = Context;
  v11 = (__int64)a6;
  v84 = (__int64)a6;
  v86 = a9;
  v76 = 0;
  v80 = 0;
  v77 = 0;
  v12 = 0;
  v74 = 0;
  v73[0] = 0;
  v13 = *(_QWORD *)(a9 + 104);
  v87 = v13;
  if ( (*(_DWORD *)(v13 + 160) & 0x400) != 0 )
  {
    v14 = 0;
    v15 = *a6;
    if ( *a6 != 8 || a7 != 160 || **((_QWORD **)a6 + 1) != 0x30003300490024LL )
    {
      v16 = *(_WORD *)(a9 + 82);
      v14 = v15 + v16;
      if ( v16 )
      {
        v14 += 4;
      }
      else if ( v15 )
      {
        v14 += 2;
      }
    }
    result = RefsGetReparsePointValue((__int64)Context, a9, Irp, v13, v14, 1);
    if ( (int)result < 0 || (_DWORD)result == 260 )
      return result;
    v11 = v84;
  }
  v78 = (int *)(*(_QWORD *)(*(_QWORD *)(a9 + 168) + 8LL) + 16LL);
  v81 = *v78 & 0x2000000;
  result = RefsBreakBatchOplock(Context, Irp, v11, a7, a9 + 112);
  v18 = result;
  if ( (int)result >= 0 && (_DWORD)result != 871 && (_DWORD)result != 259 )
  {
    if ( !(_DWORD)result || (_DWORD)result == 264 )
    {
      v69 = result;
    }
    else
    {
      v18 = 0;
      v69 = 0;
    }
    if ( (IsMinstoreTransactionActive = RefsIsMinstoreTransactionActive(Context),
          v21 = *(_QWORD *)(a9 + 112),
          *(_DWORD *)(v21 + 200) != 128)
      || *(_WORD *)v21 == 2053 && *(_QWORD *)(v21 + 360) != v19
      || (RefsBindMinstoreTransaction(Context),
          result = RefsCreateDataStream(Context, *(_QWORD *)(a9 + 112), 0),
          (int)result >= 0) )
    {
      v22 = *(_QWORD *)(a9 + 112);
      if ( (*(_DWORD *)(v22 + 136) & 0x20) == 0 )
        RefsUpdateScbFromAttribute(Context, v22, 0);
      if ( !IsMinstoreTransactionActive && *((_QWORD *)Context + 3) )
        RefsCheckpointCurrentTransaction(Context);
      v23 = *(_QWORD *)(a9 + 112);
      v70 = *(_WORD *)(v23 + 256);
      v68 = *(_WORD *)(v23 + 258);
      v24 = a8;
      v82 = a8 & 2;
      if ( (a8 & 2) != 0 )
      {
        v25 = *(_QWORD *)(a9 + 168);
        v26 = *(unsigned __int16 *)(v25 + 24) | 0x20;
        v27 = v26 & ((unsigned __int8)RefsEffectiveMode(Irpa, v25, 2) != 0 ? 1741095 : 5935399);
        v28 = *(_DWORD *)(v13 + 160);
        v29 = v27 | 0x4000;
        if ( (v28 & 0x4000) == 0 )
          v29 = v27;
        v30 = *(_QWORD *)(a9 + 136);
        v31 = 0x8000;
        if ( v30 )
        {
          v32 = v29 | *(_DWORD *)(*(_QWORD *)(v30 + 120) + 160LL) & 0x28000;
          v70 = *(_WORD *)(v30 + 256);
          StreamChecksumType = *(_WORD *)(v30 + 258);
          v68 = StreamChecksumType;
          if ( !(v29 & 0x8000 | *(_DWORD *)(*(_QWORD *)(v30 + 120) + 160LL) & 0x8000) || StreamChecksumType )
            goto LABEL_39;
        }
        else
        {
          v32 = v29;
          if ( (v29 & 0x8000) == 0 )
          {
            StreamChecksumType = v68;
            goto LABEL_39;
          }
          v30 = *(_QWORD *)(a9 + 112);
        }
        StreamChecksumType = RefsGetStreamChecksumType(*(_QWORD *)(v30 + 128));
        v68 = StreamChecksumType;
LABEL_39:
        v34 = v31 | v32;
        if ( !StreamChecksumType )
          v34 = v32;
        v76 = v34;
        if ( ((v28 & 2) != 0 && (v34 & 2) == 0 || (v28 & 4) != 0 && (v34 & 4) == 0)
          && (*(_BYTE *)(*(_QWORD *)(a9 + 168) + 2LL) & 2) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              128,
              WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
              3221225506LL);
          }
          if ( !RefsStatusDebugEnabled )
            return 3221225506LL;
LABEL_52:
          RefsStatusDebug(-1073741790);
          return 3221225506LL;
        }
        v35 = *(_QWORD *)(a9 + 168);
        if ( (*(_DWORD *)(v35 + 16) & 0x200) != 0 && Irpa->AssociatedIrp.MasterIrp )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              129,
              WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
              3221225506LL);
          }
          if ( !RefsStatusDebugEnabled )
            return 3221225506LL;
          goto LABEL_52;
        }
        v36 = v78;
        if ( (*(_BYTE *)(v35 + 2) & 2) == 0 )
        {
          v37 = *v78;
          v12 = ~(unsigned __int16)*v78 & 0x110;
          v74 = v12;
          *v78 = v12 | v37;
          v38 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a9 + 168) + 8LL) + 8LL);
          if ( (*(_DWORD *)(v38 + 12) & 4) != 0 )
            *(_DWORD *)(v38 + 20) |= v12;
        }
        v80 = v34;
        v24 = a8;
LABEL_74:
        v39 = *(_QWORD *)(a9 + 168);
        if ( (*(_BYTE *)(v39 + 2) & 2) == 0 )
        {
          v40 = a4 != 0 ? 0x10000 : 2;
          if ( (v40 & *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v39 + 8) + 8LL) + 20LL)) == 0 )
          {
            v41 = *v36;
            v42 = v40 & ~*v36 | v12;
            v74 = v42;
            *v36 = v41 | v40;
            v43 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a9 + 168) + 8LL) + 8LL);
            if ( (*(_DWORD *)(v43 + 12) & 4) != 0 )
              *(_DWORD *)(v43 + 20) |= v42;
          }
        }
        LOBYTE(v36) = a7 == 160;
        v44 = RefsCheckExistingFile((_DWORD)Context, a9, v79[0], (_DWORD)v36, v24);
        v45 = v44;
        if ( v44 < 0 || v44 == 871 )
          return (unsigned int)v45;
        v45 = RefsOpenAttributeCheck(Context, Irpa, *(_QWORD *)(a9 + 168), (__int64 *)(a9 + 112), 0, v73);
        v71 = v45;
        if ( v45 == -1073741757
          && (v46 = *(_QWORD *)(a9 + 112), *(_WORD *)v46 == 2053)
          && (*(_DWORD *)(*(_QWORD *)(a9 + 168) + 16LL) & 0x100) == 0 )
        {
          v47 = FsRtlOplockBreakH((POPLOCK)(v46 + 88), Irpa, 0, Context, RefsOplockComplete, RefsOplockPrePostIrp);
          v48 = v47;
          if ( v47 == 259 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 131, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 871);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(871);
            return 871;
          }
          if ( v47 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                132,
                WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                (unsigned int)v47);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(v48);
            v45 = v48;
            v71 = v48;
          }
        }
        else if ( v45 < 0 || !v18 && (!v45 || (v69 = 0, v45 == 264)) )
        {
          v69 = v45;
        }
        if ( v45 >= 0 && v45 != 259 && v45 != 871 )
        {
          memset(v88, 0, sizeof(v88));
          v50 = 0;
          *(_QWORD *)&v73[1] = 0;
          v51 = v73[0];
          if ( v73[0] == 1 )
            v51 = 3;
          v73[0] = v51;
          v52 = ~v74;
          if ( !v81 )
          {
            v53 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a9 + 168) + 8LL) + 8LL);
            *(_DWORD *)(v53 + 20) &= v52;
          }
          *v78 &= v52;
          _InterlockedIncrement((volatile signed __int32 *)(v13 + 28));
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a9 + 112) + 148LL));
          v54 = 0;
          *(_QWORD *)&v73[1] = 0;
          v55 = v82;
          while ( 1 )
          {
            if ( v55 )
            {
              NextChildScb = RefsGetNextChildScb(v13, v54, v49, 0);
              *(_QWORD *)&v73[1] = NextChildScb;
              if ( !NextChildScb )
                goto LABEL_119;
            }
            else
            {
              if ( v54 )
              {
                *(_QWORD *)&v73[1] = 0;
LABEL_119:
                if ( v69 == v50 )
                {
                  if ( !v71 || (v69 = v50, v71 == 264) )
                    v69 = v71;
                }
                v57 = *(_QWORD *)v83;
                if ( v55 )
                {
                  v58 = *(_DWORD *)(v13 + 160);
                  if ( (v58 & 0x400) != 0 )
                  {
                    RefsRemoveReparsePoint(*(_QWORD *)v83, v13);
                    v58 = *(_DWORD *)(v13 + 160);
                    LOBYTE(v50) = 0;
                  }
                  v59 = v76 | 0x10000000;
                  if ( (v58 & 0x10000000) == 0 )
                    v59 = v76;
                  v77 = v58;
                  if ( a4 == (_BYTE)v50 )
                    v59 |= v58;
                  *(_DWORD *)(v13 + 160) = v59;
                  *(_DWORD *)(a9 + 176) = v58 ^ v59;
                  RefsRemoveDataAttributes(
                    v57,
                    v13,
                    v79[0],
                    *(_QWORD *)(*(_QWORD *)(a9 + 168) + 48LL),
                    (_DWORD)a5,
                    *(_DWORD *)(a9 + 152));
                  if ( ((v58 ^ *(_DWORD *)(v13 + 160)) & 0x2000) != 0 )
                    RefsPostUsnChangeWithOverrideOption(v57, *(_QWORD *)(a9 + 112), 0x4000);
                }
                v60 = a9 + 112;
                v61 = Irpa;
                RefsReplaceAttribute(
                  v57,
                  *(_QWORD *)(a9 + 168),
                  v13,
                  *(_QWORD *)(a9 + 112),
                  *(__int64 *)v79,
                  v70,
                  v68,
                  Irpa->Overlay.AllocationSize.QuadPart);
                RefsPostUsnChangeWithOverrideOption(v57, *(_QWORD *)(a9 + 112), 4);
                if ( v55 )
                {
                  v62 = *(_DWORD *)(v13 + 160) | 0x800;
                  *(_DWORD *)(v13 + 160) = v62;
                  if ( !*(_BYTE *)(*(_QWORD *)v60 + 252LL) )
                  {
                    v62 &= ~0x800u;
                    *(_DWORD *)(v13 + 160) = v62;
                  }
                  v63 = v62 | 0x200;
                  *(_DWORD *)(v13 + 160) = v63;
                  if ( *(__int16 *)(*(_QWORD *)v60 + 252LL) >= 0 )
                  {
                    v63 &= ~0x200u;
                    *(_DWORD *)(v13 + 160) = v63;
                  }
                  *(_DWORD *)(a9 + 176) = v77 ^ v63;
                }
                v64 = a8 | 8;
                if ( (*(_DWORD *)(a9 + 152) & 0x40) == 0 )
                  v64 = a8;
                LODWORD(PostIrpRoutine) = (_DWORD)a5;
                v72 = RefsOpenAttribute(
                        v57,
                        *(_QWORD *)(a9 + 168),
                        *(_QWORD *)(v13 + 88),
                        *(__int64 *)v79,
                        v13,
                        PostIrpRoutine,
                        v84,
                        a7,
                        v73[0],
                        2u,
                        0,
                        v64,
                        0,
                        (__int64 *)(a9 + 112),
                        (_QWORD *)(a9 + 120));
                goto LABEL_149;
              }
              NextChildScb = *(_QWORD *)(a9 + 112);
              *(_QWORD *)&v73[1] = NextChildScb;
            }
            _InterlockedIncrement((volatile signed __int32 *)(NextChildScb + 148));
            CanFileBeTruncated = MmCanFileBeTruncated(
                                   (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*(_QWORD *)&v73[1] + 240LL) + 8LL),
                                   &RefsLarge0);
            v50 = 0;
            if ( !CanFileBeTruncated )
              break;
            _InterlockedDecrement((volatile signed __int32 *)(NextChildScb + 148));
            v54 = *(_QWORD *)&v73[1];
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              133,
              WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
              3221226051LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741245);
          v72 = -1073741245;
          v61 = Irpa;
LABEL_149:
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a9 + 112) + 148LL));
          if ( *(_QWORD *)&v73[1] )
            _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v73[1] + 148LL));
          _InterlockedDecrement((volatile signed __int32 *)(v13 + 28));
          v45 = v72;
          if ( v72 >= 0 )
          {
            _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(a9 + 112) + 136LL), 0x4000u);
            CcPurgeCacheSection(
              *(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(*(_QWORD *)(a9 + 168) + 48LL) + 40LL),
              0,
              0,
              0);
            v45 = v69;
            v61->IoStatus.Information = a4 != 0 ? 0 : 3;
          }
        }
        return (unsigned int)v45;
      }
      if ( !Irpa->AssociatedIrp.MasterIrp )
      {
        v36 = v78;
        goto LABEL_74;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 130, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811);
      return 3221225485LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1c0194f50  push    rbx
0x1c0194f52  push    rsi
0x1c0194f53  push    rdi
0x1c0194f54  push    r12
0x1c0194f56  push    r13
0x1c0194f58  push    r14
0x1c0194f5a  push    r15
0x1c0194f5c  sub     rsp, 1E0h
0x1c0194f63  mov     rax, cs:__security_cookie
0x1c0194f6a  xor     rax, rsp
0x1c0194f6d  mov     [rsp+218h+var_48], rax
0x1c0194f75  mov     [rsp+218h+var_198], r9b
0x1c0194f7d  mov     qword ptr [rsp+218h+var_158], r8
0x1c0194f85  mov     rdi, rdx
0x1c0194f88  mov     [rsp+218h+Irp], rdx
0x1c0194f90  mov     r13, rcx
0x1c0194f93  mov     qword ptr [rsp+218h+var_140], rcx
0x1c0194f9b  mov     [rsp+218h+var_130], rcx
0x1c0194fa3  mov     rcx, [rsp+218h+arg_28]
0x1c0194fab  mov     [rsp+218h+var_138], rcx
0x1c0194fb3  mov     rsi, [rsp+218h+arg_40]
0x1c0194fbb  mov     [rsp+218h+var_128], rsi
0x1c0194fc3  xor     r9d, r9d
0x1c0194fc6  mov     eax, r9d
0x1c0194fc9  mov     [rsp+218h+var_168], eax
0x1c0194fd0  mov     [rsp+218h+var_150], eax
0x1c0194fd7  mov     [rsp+218h+var_164], r9d
0x1c0194fdf  mov     r14d, r9d
0x1c0194fe2  mov     [rsp+218h+var_178], r9d
0x1c0194fea  mov     dword ptr [rsp+218h+var_184], r9d
0x1c0194ff2  mov     r15, [rsi+68h]
0x1c0194ff6  mov     [rsp+218h+var_120], r15
0x1c0194ffe  mov     [rsp+218h+var_196], r9b
0x1c0195006  test    dword ptr [r15+0A0h], 400h
0x1c0195011  jz      loc_1C019512F
0x1c0195017  movzx   edx, r9w
0x1c019501b  movzx   r8d, word ptr [rcx]
0x1c019501f  lea     ebx, [r9+8]
0x1c0195023  cmp     r8w, bx
0x1c0195027  jnz     short loc_1C019504C
0x1c0195029  cmp     [rsp+218h+arg_30], 0A0h
0x1c0195034  jnz     short loc_1C019504C
0x1c0195036  mov     rax, [rcx+8]
0x1c019503a  mov     rcx, [rax]
0x1c019503d  mov     rax, 30003300490024h
0x1c0195047  cmp     rcx, rax
0x1c019504a  jz      short loc_1C019506F
0x1c019504c  movzx   eax, word ptr [rsi+52h]
0x1c0195050  lea     edx, [r8+rax]
0x1c0195054  test    ax, ax
0x1c0195057  jz      short loc_1C0195065
0x1c0195059  mov     r12d, 4
0x1c019505f  add     dx, r12w
0x1c0195063  jmp     short loc_1C0195075
0x1c0195065  test    r8w, r8w
0x1c0195069  jz      short loc_1C019506F
0x1c019506b  add     dx, 2
0x1c019506f  mov     r12d, 4
0x1c0195075  mov     byte ptr [rsp+218h+PostIrpRoutine], 1
0x1c019507a  mov     word ptr [rsp+218h+CompletionRoutine], dx
0x1c019507f  mov     r9, r15
0x1c0195082  mov     r8, rdi
0x1c0195085  mov     rdx, rsi
0x1c0195088  mov     rcx, r13
0x1c019508b  call    RefsGetReparsePointValue
0x1c0195090  test    eax, eax
0x1c0195092  js      loc_1C0195680
0x1c0195098  cmp     eax, 104h
0x1c019509d  jz      loc_1C0195680
0x1c01950a3  mov     rcx, [rsp+218h+var_138]
0x1c01950ab  mov     r8, [rsi+0A8h]
0x1c01950b2  mov     rax, [r8+8]
0x1c01950b6  add     rax, 10h
0x1c01950ba  mov     [rsp+218h+var_160], rax
0x1c01950c2  mov     eax, [rax]
0x1c01950c4  and     eax, 2000000h
0x1c01950c9  mov     [rsp+218h+var_14C], eax
0x1c01950d0  lea     rax, [rsi+70h]
0x1c01950d4  mov     [rsp+218h+var_1E8], rax; __int64
0x1c01950d9  mov     eax, [rsp+218h+arg_30]
0x1c01950e0  mov     dword ptr [rsp+218h+PostIrpRoutine], eax; int
0x1c01950e4  mov     [rsp+218h+CompletionRoutine], rcx; __int64
0x1c01950e9  mov     r9, r15
0x1c01950ec  mov     rdx, rdi; Irp
0x1c01950ef  mov     rcx, r13; Context
0x1c01950f2  call    RefsBreakBatchOplock
0x1c01950f7  mov     edi, eax
0x1c01950f9  xor     edx, edx
0x1c01950fb  test    eax, eax
0x1c01950fd  js      loc_1C0195680
0x1c0195103  cmp     eax, 367h
0x1c0195108  jz      loc_1C0195680
0x1c019510e  cmp     eax, 103h
0x1c0195113  jz      loc_1C0195680
0x1c0195119  test    eax, eax
0x1c019511b  jz      short loc_1C019513A
0x1c019511d  cmp     eax, 108h
0x1c0195122  jz      short loc_1C019513A
0x1c0195124  mov     edi, edx
0x1c0195126  mov     [rsp+218h+var_190], edx
0x1c019512d  jmp     short loc_1C0195141
0x1c019512f  mov     r12d, 4
0x1c0195135  jmp     loc_1C01950AB
0x1c019513a  mov     [rsp+218h+var_190], eax
0x1c0195141  mov     rcx, r13
0x1c0195144  call    RefsIsMinstoreTransactionActive
0x1c0195149  mov     bl, al
0x1c019514b  mov     rcx, [rsi+70h]
0x1c019514f  cmp     dword ptr [rcx+0C8h], 80h
0x1c0195159  jnz     short loc_1C019518F
0x1c019515b  mov     r8d, 805h
0x1c0195161  cmp     [rcx], r8w
0x1c0195165  jnz     short loc_1C0195170
0x1c0195167  cmp     [rcx+168h], rdx
0x1c019516e  jnz     short loc_1C019518F
0x1c0195170  mov     rcx, r13
0x1c0195173  call    RefsBindMinstoreTransaction
0x1c0195178  xor     r8d, r8d
0x1c019517b  mov     rdx, [rsi+70h]
0x1c019517f  mov     rcx, r13
0x1c0195182  call    RefsCreateDataStream
0x1c0195187  test    eax, eax
0x1c0195189  js      loc_1C0195680
0x1c019518f  mov     rdx, [rsi+70h]
0x1c0195193  mov     eax, [rdx+88h]
0x1c0195199  test    al, 20h
0x1c019519b  jnz     short loc_1C01951A8
0x1c019519d  xor     r8d, r8d
0x1c01951a0  mov     rcx, r13
0x1c01951a3  call    RefsUpdateScbFromAttribute
0x1c01951a8  xor     eax, eax
0x1c01951aa  test    bl, bl
0x1c01951ac  jnz     short loc_1C01951BC
0x1c01951ae  cmp     [r13+18h], rax
0x1c01951b2  jz      short loc_1C01951BC
0x1c01951b4  mov     rcx, r13
0x1c01951b7  call    RefsCheckpointCurrentTransaction
0x1c01951bc  mov     rax, [rsi+70h]
0x1c01951c0  movzx   ecx, word ptr [rax+100h]
0x1c01951c7  mov     [rsp+218h+var_18C], cx
0x1c01951cf  movzx   ebx, word ptr [rax+102h]
0x1c01951d6  mov     [rsp+218h+var_194], bx
0x1c01951de  mov     r10d, [rsp+218h+arg_38]
0x1c01951e6  mov     eax, r10d
0x1c01951e9  mov     r8d, 2
0x1c01951ef  and     eax, r8d
0x1c01951f2  mov     [rsp+218h+var_148], eax
0x1c01951f9  jz      loc_1C0195451
0x1c01951ff  mov     rdx, [rsi+0A8h]
0x1c0195206  movzx   ebx, word ptr [rdx+18h]
0x1c019520a  or      ebx, 20h
0x1c019520d  mov     rcx, [rsp+218h+Irp]
0x1c0195215  call    RefsEffectiveMode
0x1c019521a  neg     al
0x1c019521c  sbb     ecx, ecx
0x1c019521e  and     ecx, 0FFC00000h
0x1c0195224  add     ecx, 5A9127h
0x1c019522a  and     ecx, ebx
0x1c019522c  mov     r10d, [r15+0A0h]
0x1c0195233  mov     eax, r10d
0x1c0195236  mov     edx, 4000h
0x1c019523b  mov     r8d, ecx
0x1c019523e  or      r8d, edx
0x1c0195241  and     eax, edx
0x1c0195243  cmovz   r8d, ecx
0x1c0195247  mov     rcx, [rsi+88h]
0x1c019524e  mov     r9d, 8000h
0x1c0195254  test    rcx, rcx
0x1c0195257  jz      short loc_1C01952AD
0x1c0195259  mov     rax, [rcx+78h]
0x1c019525d  mov     edx, [rax+0A0h]
0x1c0195263  and     edx, 28000h
0x1c0195269  or      edx, r8d
0x1c019526c  movzx   eax, word ptr [rcx+100h]
0x1c0195273  mov     [rsp+218h+var_18C], ax
0x1c019527b  movzx   ebx, word ptr [rcx+102h]
0x1c0195282  mov     [rsp+218h+var_194], bx
0x1c019528a  test    r9d, edx
0x1c019528d  jz      short loc_1C01952C3
0x1c019528f  test    bx, bx
0x1c0195292  jnz     short loc_1C01952C3
0x1c0195294  mov     rcx, [rcx+80h]
0x1c019529b  call    RefsGetStreamChecksumType
0x1c01952a0  movzx   ebx, ax
0x1c01952a3  mov     [rsp+218h+var_194], ax
0x1c01952ab  jmp     short loc_1C01952C3
0x1c01952ad  mov     edx, r8d
0x1c01952b0  test    r9d, r8d
0x1c01952b3  jz      short loc_1C01952BB
0x1c01952b5  mov     rcx, [rsi+70h]
0x1c01952b9  jmp     short loc_1C0195294
0x1c01952bb  movzx   ebx, [rsp+218h+var_194]
0x1c01952c3  mov     r11d, edx
0x1c01952c6  or      r11d, r9d
0x1c01952c9  test    bx, bx
0x1c01952cc  cmovz   r11d, edx
0x1c01952d0  mov     [rsp+218h+var_168], r11d
0x1c01952d8  mov     eax, r10d
0x1c01952db  and     eax, r12d
0x1c01952de  mov     r8d, 2
0x1c01952e4  test    r8b, r10b
0x1c01952e7  jz      short loc_1C01952F2
0x1c01952e9  test    r8b, r11b
0x1c01952ec  jz      loc_1C0195391
0x1c01952f2  xor     ebx, ebx
0x1c01952f4  test    eax, eax
0x1c01952f6  jz      short loc_1C0195301
0x1c01952f8  test    r12b, r11b
0x1c01952fb  jz      loc_1C0195393
0x1c0195301  mov     rcx, [rsi+0A8h]
0x1c0195308  test    dword ptr [rcx+10h], 200h
0x1c019530f  jz      loc_1C01953F5
0x1c0195315  mov     rax, [rsp+218h+Irp]
0x1c019531d  cmp     [rax+18h], rbx
0x1c0195321  jz      loc_1C01953F5
0x1c0195327  lea     rdi, WPP_GLOBAL_Control
0x1c019532e  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0195335  cmp     rcx, rdi
0x1c0195338  jz      short loc_1C0195366
0x1c019533a  mov     r14d, 100h
0x1c0195340  test    [rcx+2Ch], r14d
0x1c0195344  jz      short loc_1C0195366
0x1c0195346  cmp     [rcx+29h], r12b
0x1c019534a  jb      short loc_1C0195366
0x1c019534c  lea     edx, [r14-7Fh]
0x1c0195350  mov     r9d, 0C0000022h
0x1c0195356  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c019535d  mov     rcx, [rcx+18h]
0x1c0195361  call    WPP_SF_D
0x1c0195366  mov     cl, cs:RefsStatusDebugEnabled
0x1c019536c  test    cl, cl
0x1c019536e  jz      short loc_1C0195387
0x1c0195370  mov     r8d, 2CBEh
0x1c0195376  lea     rdx, aCreateC; "Create.c"
0x1c019537d  mov     ecx, 0C0000022h; Status
0x1c0195382  call    RefsStatusDebug
0x1c0195387  mov     eax, 0C0000022h
0x1c019538c  jmp     loc_1C0195680
0x1c0195391  xor     ebx, ebx
0x1c0195393  mov     rax, [rsi+0A8h]
0x1c019539a  test    [rax+2], r8b
0x1c019539e  jnz     loc_1C0195301
0x1c01953a4  lea     rdi, WPP_GLOBAL_Control
0x1c01953ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01953b2  cmp     rcx, rdi
0x1c01953b5  jz      short loc_1C01953E3
0x1c01953b7  mov     r14d, 100h
0x1c01953bd  test    [rcx+2Ch], r14d
0x1c01953c1  jz      short loc_1C01953E3
0x1c01953c3  cmp     [rcx+29h], r12b
0x1c01953c7  jb      short loc_1C01953E3
0x1c01953c9  lea     edx, [r14-80h]
0x1c01953cd  mov     r9d, 0C0000022h
0x1c01953d3  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01953da  mov     rcx, [rcx+18h]
0x1c01953de  call    WPP_SF_D
0x1c01953e3  mov     al, cs:RefsStatusDebugEnabled
0x1c01953e9  test    al, al
0x1c01953eb  jz      short loc_1C0195387
0x1c01953ed  mov     r8d, 2CB2h
0x1c01953f3  jmp     short loc_1C0195376
0x1c01953f5  mov     r9, [rsp+218h+var_160]
0x1c01953fd  test    [rcx+2], r8b
0x1c0195401  jnz     short loc_1C019543C
0x1c0195403  mov     eax, [r9]
0x1c0195406  mov     r14d, eax
0x1c0195409  not     r14d
0x1c019540c  and     r14d, 110h
0x1c0195413  mov     [rsp+218h+var_178], r14d
0x1c019541b  or      eax, r14d
0x1c019541e  mov     [r9], eax
0x1c0195421  mov     rax, [rsi+0A8h]
0x1c0195428  mov     rcx, [rax+8]
0x1c019542c  mov     rdx, [rcx+8]
0x1c0195430  mov     eax, [rdx+0Ch]
0x1c0195433  test    r12b, al
0x1c0195436  jz      short loc_1C019543C
0x1c0195438  or      [rdx+14h], r14d
0x1c019543c  mov     [rsp+218h+var_150], r11d
0x1c0195444  mov     r10d, [rsp+218h+arg_38]
0x1c019544c  jmp     loc_1C01954D3
0x1c0195451  mov     rax, [rsp+218h+Irp]
0x1c0195459  xor     ebx, ebx
0x1c019545b  cmp     [rax+18h], rbx
0x1c019545f  jz      short loc_1C01954CB
0x1c0195461  lea     rdi, WPP_GLOBAL_Control
0x1c0195468  mov     rcx, cs:WPP_GLOBAL_Control
0x1c019546f  cmp     rcx, rdi
0x1c0195472  jz      short loc_1C01954A0
0x1c0195474  mov     r14d, 100h
0x1c019547a  test    [rcx+2Ch], r14d
0x1c019547e  jz      short loc_1C01954A0
0x1c0195480  cmp     [rcx+29h], r12b
0x1c0195484  jb      short loc_1C01954A0
0x1c0195486  lea     edx, [r14-7Eh]
0x1c019548a  mov     r9d, 0C000000Dh
0x1c0195490  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0195497  mov     rcx, [rcx+18h]
0x1c019549b  call    WPP_SF_D
0x1c01954a0  mov     cl, cs:RefsStatusDebugEnabled
  ... truncated ...
```
