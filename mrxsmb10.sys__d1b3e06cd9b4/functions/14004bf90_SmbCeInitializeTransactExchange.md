# SmbCeInitializeTransactExchange

- ea: `0x14004bf90`
- end: `0x14004ccdd`
- name: `SmbCeInitializeTransactExchange`
- size: `3405`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _WORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x14004bce0`

## callees

- `0x14000dc44`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000ebd8`
- `0x140010358`
- `0x140014738`
- `0x140014820`
- `0x1400166c0`
- `0x1400169c0`
- `0x14003ee9c`
- `0x14003ef9c`
- `0x14004bf90`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c708`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004c708`
- `ntoskrnl!RtlxUnicodeStringToAnsiSize` at `0x14004c7fd`
- `ntoskrnl!RtlxUnicodeStringToAnsiSize` at `0x14004c7fd`
- `ntoskrnl!IoFreeMdl` at `0x14004c9e3`
- `ntoskrnl!IoFreeMdl` at `0x14004c9e3`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004c8cc`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004c8cc`
- `ntoskrnl!ExAllocatePool2` at `0x14004c234`
- `ntoskrnl!ExAllocatePool2` at `0x14004c234`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004cc88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004cc88`
- `rdbss!RxAllocateMdl2` at `0x14004c35c`
- `rdbss!RxAllocateMdl2` at `0x14004c35c`

## pseudocode

```c
__int64 __fastcall SmbCeInitializeTransactExchange(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4,
        _QWORD *a5,
        __int64 a6)
{
  _DWORD *v10; // rsi
  void *v11; // r11
  unsigned int v12; // r8d
  unsigned __int16 v13; // r9
  unsigned int v14; // r10d
  __int64 v15; // r13
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // r10
  unsigned int v19; // r11d
  unsigned int v20; // eax
  unsigned int v21; // r14d
  int v22; // edx
  char v23; // dl
  unsigned int v24; // esi
  unsigned __int16 *v25; // r9
  int *v26; // rax
  int v27; // edx
  ULONG v28; // r9d
  unsigned int v29; // esi
  unsigned int v30; // esi
  unsigned int v31; // r14d
  __int64 Pool2; // rax
  char *v33; // r10
  unsigned __int16 v34; // cx
  __int64 Mdl2; // rax
  struct _MDL *v37; // r10
  PDEVICE_OBJECT v38; // rcx
  unsigned __int16 v39; // dx
  __int64 v40; // r8
  __int16 v41; // dx
  int v42; // edx
  int v43; // edx
  PDEVICE_OBJECT v44; // rcx
  PVOID MappedSystemVa; // rax
  PMDL v46; // r10
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // r9
  int v50; // r9d
  char *v51; // r14
  __int64 v52; // rdx
  unsigned int v53; // eax
  unsigned __int16 v54; // [rsp+40h] [rbp-118h]
  unsigned __int8 v55; // [rsp+42h] [rbp-116h]
  char v56; // [rsp+43h] [rbp-115h]
  unsigned int Size; // [rsp+44h] [rbp-114h]
  unsigned int Size_4; // [rsp+48h] [rbp-110h]
  unsigned int v59; // [rsp+4Ch] [rbp-10Ch]
  unsigned int v60; // [rsp+50h] [rbp-108h]
  unsigned int v61; // [rsp+54h] [rbp-104h]
  _BYTE *v62; // [rsp+58h] [rbp-100h]
  PMDL MemoryDescriptorList; // [rsp+70h] [rbp-E8h]
  void *v64; // [rsp+78h] [rbp-E0h]
  PVOID P; // [rsp+80h] [rbp-D8h]
  unsigned __int64 v66; // [rsp+88h] [rbp-D0h] BYREF
  unsigned int v67; // [rsp+90h] [rbp-C8h]
  __int64 v68; // [rsp+98h] [rbp-C0h]
  __int64 v69; // [rsp+A0h] [rbp-B8h]
  __int64 v70; // [rsp+A8h] [rbp-B0h]
  __int64 v71; // [rsp+B0h] [rbp-A8h]
  __int64 v72; // [rsp+B8h] [rbp-A0h]
  __int64 v73; // [rsp+C0h] [rbp-98h]
  void *Src; // [rsp+C8h] [rbp-90h]
  __int64 v75; // [rsp+D0h] [rbp-88h]
  __int64 v76; // [rsp+D8h] [rbp-80h]
  __int64 v77; // [rsp+E0h] [rbp-78h]
  __int64 v78; // [rsp+E8h] [rbp-70h]
  __int64 v79; // [rsp+F0h] [rbp-68h]
  void *v80; // [rsp+F8h] [rbp-60h]
  void *v81; // [rsp+100h] [rbp-58h]
  __int64 v82; // [rsp+108h] [rbp-50h]
  PMDL *v83; // [rsp+110h] [rbp-48h]
  _QWORD *v84; // [rsp+118h] [rbp-40h]
  __int64 v85; // [rsp+160h] [rbp+8h]
  void *v86; // [rsp+178h] [rbp+20h] BYREF

  v86 = a4;
  v76 = *(_QWORD *)(a2 + 64);
  v78 = v76;
  *(_QWORD *)(a1 + 24) = a2;
  v10 = *(_DWORD **)(a1 + 80);
  v84 = (_QWORD *)(a2 + 224);
  *(_QWORD *)(a2 + 224) = a1;
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, 3221225485LL);
    return 3221225485LL;
  }
  v75 = *((_QWORD *)a4 + 5);
  v79 = v75;
  v11 = (void *)*((_QWORD *)a4 + 3);
  v64 = v11;
  v80 = v11;
  v12 = *((_DWORD *)a4 + 4);
  Size = v12;
  v67 = v12;
  v83 = (PMDL *)(a4 + 16);
  MemoryDescriptorList = (PMDL)*((_QWORD *)a4 + 4);
  Src = (void *)*((_QWORD *)a4 + 1);
  v81 = Src;
  v13 = a4[1];
  v54 = v13;
  v14 = *((_DWORD *)a4 + 12);
  v59 = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v11, v12, v14);
    v12 = Size;
    v13 = v54;
    v14 = v59;
  }
  v15 = (__int64)a5;
  if ( !a5 )
  {
    v70 = 0;
    v73 = 0;
    v69 = 0;
    v72 = 0;
    v68 = 0;
    v71 = 0;
    Size_4 = 0;
    v19 = 0;
    v60 = 0;
    goto LABEL_12;
  }
  v16 = a5[5];
  v68 = v16;
  v71 = v16;
  v17 = a5[4];
  v69 = v17;
  v72 = v17;
  v18 = a5[1];
  v70 = v18;
  v73 = v18;
  if ( v16 )
  {
    v19 = *(_DWORD *)(v16 + 40);
    v60 = v19;
  }
  else
  {
    v19 = 0;
    v60 = 0;
  }
  if ( v17 )
    Size_4 = *(_DWORD *)(v17 + 40);
  else
    Size_4 = 0;
  v13 = v54;
  if ( !v18 )
  {
    v14 = v59;
LABEL_12:
    v20 = 0;
    goto LABEL_13;
  }
  v20 = *(_DWORD *)(v18 + 40);
  v14 = v59;
LABEL_13:
  v61 = v20;
  v21 = v10[117];
  if ( v21 >= *(_DWORD *)(a3 + 20) )
    v21 = *(_DWORD *)(a3 + 20);
  *(_DWORD *)(a1 + 520) = v21;
  v22 = v10[104];
  if ( v22 == 5 )
  {
    v23 = 0;
    v56 = 0;
    if ( _bittest16((const signed __int16 *)(a3 + 2), 0xBu) || (v10[105] & 0x8000) == 0 )
    {
LABEL_20:
      if ( *(_WORD *)a3 )
      {
        v55 = -96;
        v29 = v13 + 72;
        v27 = 0;
        v26 = (int *)(a1 + 516);
      }
      else
      {
        if ( v12 > 0xFFFF || Size_4 > 0xFFFF || v14 > 0xFFFF || v19 > 0xFFFF )
        {
          v38 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
          {
            return 3221225485LL;
          }
          v48 = 67;
LABEL_96:
          WPP_SF_(v38->AttachedDevice, v48, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
          return 3221225485LL;
        }
        v24 = v13 + 62;
        v25 = *(unsigned __int16 **)(a3 + 8);
        v26 = (int *)(a1 + 516);
        if ( v25 )
        {
          if ( v23 )
          {
            v28 = *v25 + 2;
            v24 = (v24 + 1) & 0xFFFFFFFE;
            v27 = v28;
          }
          else
          {
            v28 = RtlxUnicodeStringToAnsiSize(*(PCUNICODE_STRING *)(a3 + 8));
            v27 = v28;
            v12 = Size;
          }
          v55 = 37;
          v26 = (int *)(a1 + 516);
        }
        else
        {
          v55 = 50;
          v27 = 1;
          v28 = 1;
        }
        v29 = v28 + v24;
      }
      *v26 = v27;
      if ( v29 <= v21 )
      {
        v30 = (v29 + 5) & 0xFFFFFFFC;
        LODWORD(v66) = v30;
        if ( v12 && v30 + v12 > v21 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
          }
          v62 = (_BYTE *)(a1 + 508);
          v82 = a1 + 508;
          *(_BYTE *)(a1 + 508) = 0;
          Mdl2 = RxAllocateMdl2(v64, Size, 0, 0, 0);
          v37 = (struct _MDL *)Mdl2;
          MemoryDescriptorList = (PMDL)Mdl2;
          v77 = Mdl2;
          if ( Mdl2 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, Mdl2);
              v37 = MemoryDescriptorList;
            }
            v31 = 0;
            MmProbeAndLockPages(v37, 0, IoModifyAccess);
            v46 = MemoryDescriptorList;
            if ( (MemoryDescriptorList->MdlFlags & 5) != 0 )
            {
              MappedSystemVa = MemoryDescriptorList->MappedSystemVa;
            }
            else
            {
              MappedSystemVa = MmMapLockedPagesSpecifyCache(MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000000u);
              v46 = MemoryDescriptorList;
            }
            if ( !MappedSystemVa )
              v31 = -1073741670;
            *v83 = v46;
          }
          else
          {
            v31 = -1073741670;
          }
        }
        else
        {
          v31 = 0;
          v30 = (v12 + v30 + 3) & 0xFFFFFFFC;
          v62 = (_BYTE *)(a1 + 508);
          *(_BYTE *)(a1 + 508) = 1;
        }
        Pool2 = ExAllocatePool2(258, v30 + 36, 1918135635);
        P = (PVOID)Pool2;
        if ( !Pool2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
            Pool2 = 0;
          }
          v31 = -1073741670;
          goto LABEL_36;
        }
        v33 = 0;
        v86 = 0;
        v85 = Pool2 + 32;
        if ( !v31 )
        {
          memset((void *)(Pool2 + 32), 0, v30 + 4);
          if ( v55 == 50 || v55 == 37 )
          {
            v39 = v54;
            *(_BYTE *)(v85 + 32) = (v54 >> 1) + 14;
            *(_WORD *)(v85 + 33) = Size;
            *(_WORD *)(v85 + 35) = v59;
            *(_WORD *)(v85 + 37) = Size_4;
            *(_WORD *)(v85 + 39) = v60;
            *(_WORD *)(v85 + 41) = (unsigned __int8)(v61 >> 1);
            *(_BYTE *)(v85 + 60) = 0;
            *(_WORD *)(v85 + 49) = 0;
            *(_WORD *)(v85 + 43) = (unsigned __int8)*(_WORD *)(a3 + 2);
            *(_BYTE *)(v85 + 59) = v54 >> 1;
            *(_DWORD *)(v85 + 45) = *(_DWORD *)(a3 + 16);
            v33 = (char *)(v85 + 61);
            v40 = *(_QWORD *)(a3 + 8);
            if ( v40 )
            {
              v50 = *(_DWORD *)(a1 + 516);
              LODWORD(v86) = v50;
              v51 = &v33[v54 + 2];
              v66 = (unsigned __int64)v51;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                WPP_SF_lZ(WPP_GLOBAL_Control->AttachedDevice, (unsigned int)&WPP_GLOBAL_Control, v40, v50, v40);
              }
              v52 = *(_QWORD *)(a3 + 8);
              if ( v56 )
              {
                v66 = (unsigned __int64)(v51 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
                v53 = SmbPutUnicodeString(&v66, v52, &v86);
              }
              else
              {
                v53 = SmbPutUnicodeStringAsOemString(&v66, v52, &v86);
              }
              v39 = v54;
              v33 = (char *)(v85 + 61);
              v31 = v53;
            }
            v86 = (void *)((unsigned __int64)&v33[*(unsigned int *)(a1 + 516) + 5 + v39] & 0xFFFFFFFFFFFFFFFCuLL);
          }
          else
          {
            if ( v55 == 160 )
            {
              LOWORD(v86) = v54 >> 1;
              v49 = v85;
              *(_BYTE *)(v85 + 32) = (v54 >> 1) + 19;
              *(_DWORD *)(v85 + 36) = Size;
              *(_DWORD *)(v85 + 40) = v59;
              *(_DWORD *)(v85 + 44) = Size_4;
              *(_DWORD *)(v85 + 48) = v60;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                WPP_SF_dddd(WPP_GLOBAL_Control->AttachedDevice, 73, v59, Size, v59, Size_4, v60);
                v49 = v85;
              }
              *(_BYTE *)(v49 + 33) = v61 >> 1;
              *(_WORD *)(v49 + 34) = (unsigned __int8)*(_WORD *)(a3 + 2);
              *(_WORD *)(v49 + 69) = *(_WORD *)a3;
              *(_BYTE *)(v49 + 68) = (_BYTE)v86;
              v33 = (char *)(v49 + 71);
              v34 = v54;
              v86 = (void *)((v49 + 71 + v54 + 5LL) & 0xFFFFFFFFFFFFFFFCuLL);
              v62 = (_BYTE *)(a1 + 508);
              goto LABEL_34;
            }
            v31 = -1073741811;
            v33 = 0;
          }
        }
        v34 = v54;
LABEL_34:
        if ( !v31 )
        {
          memmove(v33, Src, v34);
          if ( *v62 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                74,
                WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
                v64,
                Size);
            }
            memmove(v86, v64, Size);
          }
          *(_DWORD *)(a1 + 48) = -1073741802;
          *(_WORD *)(a1 + 64) = 0;
          *(_BYTE *)(a1 + 509) = v55;
          *(_QWORD *)(a1 + 480) = P;
          *(_QWORD *)(a1 + 488) = v85;
          *(_DWORD *)(a1 + 472) = v30;
          *(_QWORD *)(a1 + 368) = v75;
          *(_DWORD *)(a1 + 376) = v59;
          *(_QWORD *)(a1 + 384) = v68;
          *(_DWORD *)(a1 + 392) = v60;
          *(_DWORD *)(a1 + 380) = 0;
          *(_DWORD *)(a1 + 396) = 0;
          *(_QWORD *)(a1 + 408) = v64;
          *(_DWORD *)(a1 + 416) = Size;
          *(_QWORD *)(a1 + 400) = MemoryDescriptorList;
          *(_QWORD *)(a1 + 424) = v69;
          *(_DWORD *)(a1 + 432) = Size_4;
          *(_DWORD *)(a1 + 420) = 0;
          *(_DWORD *)(a1 + 436) = 0;
          *(_QWORD *)(a1 + 456) = v70;
          *(_DWORD *)(a1 + 464) = v61;
          *(_DWORD *)(a1 + 468) = 0;
          *(_WORD *)(a1 + 512) = *(_WORD *)a3;
          v41 = *(_WORD *)(a3 + 2);
          *(_WORD *)(a1 + 510) = v41;
          if ( v76 && (*(_DWORD *)(v76 + 72) & 1) != 0
            || !*(_BYTE *)(a2 + 32)
            && (*(_DWORD *)(*(_QWORD *)(a2 + 648) + 56LL) & 2) != 0
            && *(_QWORD *)(a2 + 560) == 4282664531LL )
          {
            v41 |= 0x200u;
            *(_WORD *)(a1 + 510) = v41;
          }
          *(_QWORD *)(a1 + 528) = a6;
          if ( (*a4 & 0x2000) != 0 )
            *(_WORD *)(a1 + 510) = v41 | 0x2000;
          *(_OWORD *)a4 = 0;
          *((_OWORD *)a4 + 1) = 0;
          *((_OWORD *)a4 + 2) = 0;
          *((_QWORD *)a4 + 6) = 0;
          *(_OWORD *)v15 = 0;
          *(_OWORD *)(v15 + 16) = 0;
          *(_OWORD *)(v15 + 32) = 0;
          *(_QWORD *)(v15 + 48) = 0;
          *v84 = a1;
          if ( !_bittest16((const signed __int16 *)(a1 + 510), 0xBu) )
            *(_DWORD *)(a1 + 72) &= ~0x10u;
          if ( _bittest16((const signed __int16 *)(a3 + 2), 0xAu) )
            *(_DWORD *)(a1 + 72) |= 0x20u;
          return v31;
        }
        Pool2 = (__int64)P;
LABEL_36:
        if ( Pool2 )
          ExFreePoolWithTag((PVOID)Pool2, 0);
        return v31;
      }
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      {
        return 3221225485LL;
      }
      v48 = 68;
      goto LABEL_96;
    }
    v23 = 1;
LABEL_19:
    v56 = v23;
    goto LABEL_20;
  }
  v42 = v22 - 1;
  if ( v42 && (v43 = v42 - 1) != 0 )
  {
    if ( (unsigned int)(v43 - 1) >= 2 )
    {
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      {
        return 3221225659LL;
      }
      v47 = 66;
      goto LABEL_85;
    }
  }
  else if ( !*(_QWORD *)(a3 + 8) )
  {
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      return 3221225659LL;
    v47 = 64;
    goto LABEL_85;
  }
  if ( !*(_WORD *)a3 )
  {
    v23 = 0;
    goto LABEL_19;
  }
  v44 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    v47 = 65;
LABEL_85:
    WPP_SF_(v44->AttachedDevice, v47, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x14004bf90  mov     [rsp+arg_18], r9
0x14004bf95  mov     [rsp+arg_10], r8
0x14004bf9a  mov     [rsp+arg_8], rdx
0x14004bf9f  mov     [rsp+arg_0], rcx
0x14004bfa4  push    rbx
0x14004bfa5  push    rsi
0x14004bfa6  push    rdi
0x14004bfa7  push    r12
0x14004bfa9  push    r13
0x14004bfab  push    r14
0x14004bfad  push    r15
0x14004bfaf  sub     rsp, 120h
0x14004bfb6  mov     rbx, r9
0x14004bfb9  mov     r12, r8
0x14004bfbc  mov     r15, rdx
0x14004bfbf  mov     rdi, rcx
0x14004bfc2  mov     rax, [rdx+40h]
0x14004bfc6  mov     [rsp+158h+var_80], rax
0x14004bfce  mov     [rsp+158h+var_70], rax
0x14004bfd6  mov     [rcx+18h], rdx
0x14004bfda  mov     rsi, [rcx+50h]
0x14004bfde  lea     rax, [rdx+0E0h]
0x14004bfe5  mov     [rsp+158h+var_40], rax
0x14004bfed  mov     [rax], rcx
0x14004bff0  test    r9, r9
0x14004bff3  jz      loc_14004CC99
0x14004bff9  mov     rax, [r9+28h]
0x14004bffd  mov     [rsp+158h+var_88], rax
0x14004c005  mov     [rsp+158h+var_68], rax
0x14004c00d  mov     r11, [r9+18h]
0x14004c011  mov     [rsp+158h+var_E0], r11
0x14004c016  mov     [rsp+158h+var_60], r11
0x14004c01e  mov     r8d, [r9+10h]
0x14004c022  mov     dword ptr [rsp+158h+Size], r8d
0x14004c027  mov     [rsp+158h+var_C8], r8d
0x14004c02f  lea     rax, [r9+20h]
0x14004c033  mov     [rsp+158h+var_48], rax
0x14004c03b  mov     rax, [rax]
0x14004c03e  mov     [rsp+158h+MemoryDescriptorList], rax
0x14004c043  mov     rax, [r9+8]
0x14004c047  mov     [rsp+158h+Src], rax
0x14004c04f  mov     [rsp+158h+var_58], rax
0x14004c057  movzx   r9d, word ptr [r9+2]
0x14004c05c  mov     [rsp+158h+var_118], r9w
0x14004c062  mov     [rsp+158h+var_F8], r9w
0x14004c068  mov     r10d, [rbx+30h]
0x14004c06c  mov     [rsp+158h+var_10C], r10d
0x14004c071  mov     dword ptr [rsp+158h+P], r10d
0x14004c079  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14004c080  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c087  cmp     rcx, rax
0x14004c08a  jz      short loc_14004C099
0x14004c08c  test    dword ptr [rcx+2Ch], 400h
0x14004c093  jnz     loc_14004C71B
0x14004c099  mov     r13, [rsp+158h+arg_20]
0x14004c0a1  xor     ecx, ecx
0x14004c0a3  test    r13, r13
0x14004c0a6  jz      loc_14004C38C
0x14004c0ac  mov     rdx, [r13+28h]
0x14004c0b0  mov     [rsp+158h+var_C0], rdx
0x14004c0b8  mov     [rsp+158h+var_A8], rdx
0x14004c0c0  mov     r9, [r13+20h]
0x14004c0c4  mov     [rsp+158h+var_B8], r9
0x14004c0cc  mov     [rsp+158h+var_A0], r9
0x14004c0d4  mov     r10, [r13+8]
0x14004c0d8  mov     [rsp+158h+var_B0], r10
0x14004c0e0  mov     [rsp+158h+var_98], r10
0x14004c0e8  test    rdx, rdx
0x14004c0eb  jz      loc_14004C752
0x14004c0f1  mov     r11d, [rdx+28h]
0x14004c0f5  mov     [rsp+158h+var_108], r11d
0x14004c0fa  mov     [rsp+158h+var_F0], r11d
0x14004c0ff  test    r9, r9
0x14004c102  jz      loc_14004C2E3
0x14004c108  mov     eax, [r9+28h]
0x14004c10c  mov     dword ptr [rsp+158h+Size+4], eax
0x14004c110  mov     [rsp+158h+var_EC], eax
0x14004c114  movzx   r9d, [rsp+158h+var_118]
0x14004c11a  test    r10, r10
0x14004c11d  jnz     loc_14004C2D5
0x14004c123  mov     r10d, [rsp+158h+var_10C]
0x14004c128  mov     eax, ecx
0x14004c12a  mov     [rsp+158h+var_104], eax
0x14004c12e  mov     [rsp+158h+var_F4], eax
0x14004c132  mov     eax, [r12+14h]
0x14004c137  mov     r14d, [rsi+1D4h]
0x14004c13e  cmp     r14d, eax
0x14004c141  cmovnb  r14d, eax
0x14004c145  mov     [rdi+208h], r14d
0x14004c14c  mov     edx, [rsi+1A0h]
0x14004c152  cmp     edx, 5
0x14004c155  jnz     loc_14004C682
0x14004c15b  xor     dl, dl
0x14004c15d  mov     [rsp+158h+var_115], dl
0x14004c161  bt      word ptr [r12+2], 0Bh
0x14004c169  jb      short loc_14004C17D
0x14004c16b  test    dword ptr [rsi+1A4h], 8000h
0x14004c175  jz      short loc_14004C17D
0x14004c177  mov     dl, 1
0x14004c179  mov     [rsp+158h+var_115], dl
0x14004c17d  cmp     word ptr [r12], 0
0x14004c183  jnz     loc_14004C2BB
0x14004c189  cmp     r8d, 0FFFFh
0x14004c190  ja      loc_14004C838
0x14004c196  cmp     dword ptr [rsp+158h+Size+4], 0FFFFh
0x14004c19e  ja      loc_14004C838
0x14004c1a4  cmp     r10d, 0FFFFh
0x14004c1ab  ja      loc_14004C838
0x14004c1b1  cmp     r11d, 0FFFFh
0x14004c1b8  ja      loc_14004C838
0x14004c1be  movzx   esi, r9w
0x14004c1c2  add     esi, 3Eh ; '>'
0x14004c1c5  mov     r9, [r12+8]
0x14004c1ca  lea     rax, [rdi+204h]
0x14004c1d1  test    r9, r9
0x14004c1d4  jnz     loc_14004C7F6
0x14004c1da  mov     [rsp+158h+var_116], 32h ; '2'
0x14004c1df  mov     edx, 1
0x14004c1e4  mov     r9d, edx
0x14004c1e7  add     esi, r9d
0x14004c1ea  mov     [rax], edx
0x14004c1ec  cmp     esi, r14d
0x14004c1ef  ja      loc_14004C3D4
0x14004c1f5  add     esi, 5
0x14004c1f8  and     esi, 0FFFFFFFCh
0x14004c1fb  mov     dword ptr [rsp+158h+var_D0], esi
0x14004c202  test    r8d, r8d
0x14004c205  jnz     loc_14004C2F0
0x14004c20b  mov     r14d, ecx
0x14004c20e  add     esi, 3
0x14004c211  add     esi, r8d
0x14004c214  and     esi, 0FFFFFFFCh
0x14004c217  lea     rax, [rdi+1FCh]
0x14004c21e  mov     [rsp+158h+var_100], rax
0x14004c223  mov     byte ptr [rax], 1
0x14004c226  lea     edx, [rsi+24h]
0x14004c229  mov     ecx, 102h
0x14004c22e  mov     r8d, 72546D53h
0x14004c234  call    cs:__imp_ExAllocatePool2
0x14004c23b  nop     dword ptr [rax+rax+00h]
0x14004c240  mov     [rsp+158h+P], rax
0x14004c248  test    rax, rax
0x14004c24b  jz      loc_14004C9F4
0x14004c251  xor     ecx, ecx
0x14004c253  mov     r10d, ecx
0x14004c256  mov     [rsp+158h+arg_8], rcx
0x14004c25e  mov     [rsp+158h+arg_18], rcx
0x14004c266  lea     r9, [rax+20h]
0x14004c26a  mov     [rsp+158h+arg_0], r9
0x14004c272  test    r14d, r14d
0x14004c275  jz      loc_14004C3F5
0x14004c27b  mov     rax, [rsp+158h+var_100]
0x14004c280  mov     [rsp+158h+var_100], rax
0x14004c285  movzx   ecx, [rsp+158h+var_118]
0x14004c28a  test    r14d, r14d
0x14004c28d  jz      loc_14004C4CB
0x14004c293  mov     rax, [rsp+158h+P]
0x14004c29b  test    rax, rax
0x14004c29e  jnz     loc_14004CC83
0x14004c2a4  mov     eax, r14d
0x14004c2a7  add     rsp, 120h
0x14004c2ae  pop     r15
0x14004c2b0  pop     r14
0x14004c2b2  pop     r13
0x14004c2b4  pop     r12
0x14004c2b6  pop     rdi
0x14004c2b7  pop     rsi
0x14004c2b8  pop     rbx
0x14004c2b9  retn
0x14004c2bb  mov     [rsp+158h+var_116], 0A0h
0x14004c2c0  movzx   esi, r9w
0x14004c2c4  add     esi, 48h ; 'H'
0x14004c2c7  mov     edx, ecx
0x14004c2c9  lea     rax, [rdi+204h]
0x14004c2d0  jmp     loc_14004C1EA
0x14004c2d5  mov     eax, [r10+28h]
0x14004c2d9  mov     r10d, [rsp+158h+var_10C]
0x14004c2de  jmp     loc_14004C12A
0x14004c2e3  mov     dword ptr [rsp+158h+Size+4], ecx
0x14004c2e7  mov     [rsp+158h+var_EC], ecx
0x14004c2eb  jmp     loc_14004C114
0x14004c2f0  lea     eax, [rsi+r8]
0x14004c2f4  cmp     eax, r14d
0x14004c2f7  jbe     loc_14004C20B
0x14004c2fd  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004c304  lea     r14, WPP_GLOBAL_Control
0x14004c30b  cmp     r9, r14
0x14004c30e  jz      short loc_14004C331
0x14004c310  test    dword ptr [r9+2Ch], 400h
0x14004c318  jz      short loc_14004C331
0x14004c31a  mov     edx, 45h ; 'E'
0x14004c31f  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14004c326  mov     rcx, [r9+18h]
0x14004c32a  call    WPP_SF_
0x14004c32f  xor     ecx, ecx
0x14004c331  lea     rax, [rdi+1FCh]
0x14004c338  mov     [rsp+158h+var_100], rax
0x14004c33d  mov     [rsp+158h+var_50], rax
0x14004c345  mov     byte ptr [rax], 0
0x14004c348  mov     qword ptr [rsp+158h+BugCheckOnFailure], rcx
0x14004c34d  xor     r9d, r9d
0x14004c350  xor     r8d, r8d
0x14004c353  mov     edx, dword ptr [rsp+158h+Size]
0x14004c357  mov     rcx, [rsp+158h+var_E0]
0x14004c35c  call    cs:__imp_RxAllocateMdl2
0x14004c363  nop     dword ptr [rax+rax+00h]
0x14004c368  mov     r10, rax
0x14004c36b  mov     [rsp+158h+MemoryDescriptorList], rax
0x14004c370  mov     [rsp+158h+var_78], rax
0x14004c378  test    rax, rax
0x14004c37b  jnz     loc_14004C88A
0x14004c381  mov     r14d, 0C000009Ah
0x14004c387  jmp     loc_14004C226
0x14004c38c  mov     [rsp+158h+var_B0], rcx
0x14004c394  mov     [rsp+158h+var_98], rcx
0x14004c39c  mov     [rsp+158h+var_B8], rcx
0x14004c3a4  mov     [rsp+158h+var_A0], rcx
0x14004c3ac  mov     [rsp+158h+var_C0], rcx
0x14004c3b4  mov     [rsp+158h+var_A8], rcx
0x14004c3bc  mov     dword ptr [rsp+158h+Size+4], ecx
0x14004c3c0  mov     [rsp+158h+var_EC], ecx
0x14004c3c4  mov     r11d, ecx
0x14004c3c7  mov     [rsp+158h+var_108], ecx
0x14004c3cb  mov     [rsp+158h+var_F0], ecx
0x14004c3cf  jmp     loc_14004C128
0x14004c3d4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004c3db  lea     rdx, WPP_GLOBAL_Control
0x14004c3e2  cmp     rcx, rdx
0x14004c3e5  jnz     loc_14004C863
0x14004c3eb  mov     eax, 0C000000Dh
0x14004c3f0  jmp     loc_14004C2A7
0x14004c3f5  lea     r8d, [rsi+4]; Size
0x14004c3f9  xor     edx, edx; Val
0x14004c3fb  mov     rcx, r9; void *
0x14004c3fe  call    memset
0x14004c403  movzx   ecx, [rsp+158h+var_116]
0x14004c408  cmp     ecx, 32h ; '2'
0x14004c40b  jnz     loc_14004CA38
0x14004c411  movzx   edx, [rsp+158h+var_118]
0x14004c416  movzx   ecx, dx
0x14004c419  shr     cx, 1
0x14004c41c  lea     eax, [rcx+0Eh]
0x14004c41f  mov     r9, [rsp+158h+arg_0]
0x14004c427  mov     [r9+20h], al
0x14004c42b  mov     eax, dword ptr [rsp+158h+Size]
0x14004c42f  mov     [r9+21h], ax
0x14004c434  mov     r8d, [rsp+158h+var_10C]
0x14004c439  mov     [r9+23h], r8w
0x14004c43e  mov     eax, dword ptr [rsp+158h+Size+4]
0x14004c442  mov     [r9+25h], ax
0x14004c447  mov     eax, [rsp+158h+var_108]
0x14004c44b  mov     [r9+27h], ax
0x14004c450  mov     eax, [rsp+158h+var_104]
0x14004c454  shr     eax, 1
0x14004c456  mov     [r9+29h], al
0x14004c45a  mov     byte ptr [r9+2Ah], 0
0x14004c45f  mov     byte ptr [r9+3Ch], 0
0x14004c464  xor     eax, eax
0x14004c466  mov     [r9+31h], ax
0x14004c46b  movzx   eax, word ptr [r12+2]
0x14004c471  mov     r8d, 0FFh
0x14004c477  and     ax, r8w
0x14004c47b  mov     [r9+2Bh], ax
0x14004c480  mov     [r9+3Bh], cl
0x14004c484  mov     eax, [r12+10h]
0x14004c489  mov     [r9+2Dh], eax
0x14004c48d  lea     r10, [r9+3Dh]
0x14004c491  mov     [rsp+158h+arg_8], r10
0x14004c499  mov     r8, [r12+8]
0x14004c49e  test    r8, r8
0x14004c4a1  jnz     loc_14004CB3F
0x14004c4a7  mov     eax, [rdi+204h]
0x14004c4ad  movzx   ecx, dx
0x14004c4b0  add     rax, 5
0x14004c4b4  add     rax, r10
0x14004c4b7  add     rcx, rax
0x14004c4ba  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14004c4be  mov     [rsp+158h+arg_18], rcx
0x14004c4c6  jmp     loc_14004C27B
0x14004c4cb  movzx   r8d, cx; Size
0x14004c4cf  mov     rdx, [rsp+158h+Src]; Src
0x14004c4d7  mov     rcx, r10; void *
0x14004c4da  call    memmove
0x14004c4df  mov     rax, [rsp+158h+var_100]
0x14004c4e4  cmp     byte ptr [rax], 0
0x14004c4e7  jnz     loc_14004CBD8
0x14004c4ed  mov     dword ptr [rdi+30h], 0C0000016h
0x14004c4f4  xor     ecx, ecx
0x14004c4f6  mov     [rdi+40h], cx
0x14004c4fa  movzx   eax, [rsp+158h+var_116]
0x14004c4ff  mov     [rdi+1FDh], al
0x14004c505  mov     rax, [rsp+158h+P]
0x14004c50d  mov     [rdi+1E0h], rax
0x14004c514  mov     rax, [rsp+158h+arg_0]
0x14004c51c  mov     [rdi+1E8h], rax
0x14004c523  mov     [rdi+1D8h], esi
0x14004c529  mov     rax, [rsp+158h+var_88]
0x14004c531  mov     [rdi+170h], rax
0x14004c538  mov     eax, [rsp+158h+var_10C]
0x14004c53c  mov     [rdi+178h], eax
  ... truncated ...
```
