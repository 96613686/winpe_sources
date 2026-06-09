# ndisFilterIndicateReceiveNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong)

- ea: `0x140023960`
- end: `0x1400248ed`
- name: `?ndisFilterIndicateReceiveNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z`
- size: `3981`
- prototype: `void(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140023960`
- `0x1400260b0`
- `0x1400334f0`
- `0x140037bd0`
- `0x140038090`
- `0x14003a0e0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140023c0c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023cc5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023d0a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023d35`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002438e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400243d5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023c0c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023cc5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023d0a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140023d35`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002438e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400243d5`
- `ntoskrnl!IoGetStackLimits` at `0x140023da2`
- `ntoskrnl!IoGetStackLimits` at `0x140023da2`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140023e15`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140023e15`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400244f7`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400245c2`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400244f7`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400245c2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140024558`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140024628`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140024558`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140024628`

## pseudocode

```c
void __fastcall ndisFilterIndicateReceiveNetBufferLists(
        _QWORD *a1,
        struct _NET_BUFFER_LIST *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int Number; // r15d
  __int64 v6; // rax
  struct _NET_BUFFER_LIST *v7; // r12
  __int64 v8; // rdx
  unsigned int v9; // edi
  int v10; // r14d
  _QWORD *v11; // rsi
  struct NDIS_NBL_TRACKER_HANDLE__ *v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r14
  unsigned __int64 v15; // rdi
  __int64 v16; // rbx
  unsigned int v17; // r15d
  unsigned __int64 v18; // r13
  unsigned __int64 v19; // rbx
  _SLIST_HEADER *Alignment; // rsi
  unsigned __int64 v21; // r12
  unsigned __int64 Region; // rdi
  char *v23; // rcx
  unsigned __int64 v24; // r9
  __int64 v25; // rcx
  unsigned __int64 v26; // r14
  unsigned __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int v30; // ebx
  __int64 v31; // rdi
  void (__fastcall *v32)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int); // r14
  __int64 v33; // r15
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rdi
  __int64 v36; // rdx
  __int64 v37; // rcx
  unsigned int v38; // r13d
  __int64 v39; // rax
  unsigned __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  int v43; // ecx
  int v44; // r8d
  unsigned int v45; // ecx
  _SLIST_HEADER *v46; // rax
  unsigned __int64 v47; // rax
  __int64 v48; // rcx
  __int64 *v49; // rsi
  unsigned __int64 v50; // rcx
  struct _NET_BUFFER_LIST *v51; // rbx
  __int64 v52; // r13
  __int64 v53; // r12
  struct _NET_BUFFER_LIST *v54; // rbx
  unsigned int ChildRefCount; // ecx
  unsigned int NdisReserved2; // edx
  struct _NET_BUFFER_LIST *Scratch; // rsi
  struct _NET_BUFFER_LIST *v58; // rbx
  unsigned int v59; // ecx
  struct _NET_BUFFER_LIST *v60; // rsi
  unsigned int v61; // r13d
  unsigned int v62; // r12d
  __int64 v63; // rdx
  struct _NET_BUFFER_LIST *v64; // rax
  struct _NET_BUFFER_LIST **p_Next; // rcx
  unsigned int v66; // r8d
  unsigned int v67; // r13d
  __int64 v68; // rdi
  __int64 v69; // rsi
  __int64 v70; // r8
  unsigned __int64 v71; // rbx
  struct NDIS_NBL_TRACKER_HANDLE__ *v72; // rdx
  unsigned __int64 v73; // r14
  unsigned __int64 v74; // rbx
  unsigned __int64 v75; // rdi
  unsigned __int64 v76; // r13
  char *SourceHandle; // rcx
  __int64 v78; // rax
  unsigned __int64 v79; // r15
  __int64 v80; // rcx
  unsigned __int64 v81; // rsi
  unsigned __int64 v82; // rdx
  __int64 v83; // rcx
  KIRQL CurrentIrql; // al
  unsigned __int64 v85; // rdx
  unsigned __int64 v86; // rdi
  __int64 v87; // rdx
  KIRQL v88; // al
  unsigned int v89; // ecx
  unsigned int v90; // edx
  struct _NET_BUFFER_LIST *v91; // r12
  unsigned int v92; // r13d
  __int64 v93; // rax
  bool v94; // zf
  __int64 v95; // rdx
  __int64 v96; // rax
  unsigned int v97; // esi
  __int64 v98; // rdx
  __int64 v99; // rax
  unsigned __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // r8
  __int64 v103; // rdx
  __int64 v104; // r8
  char v105; // [rsp+40h] [rbp-71h]
  unsigned int v106; // [rsp+44h] [rbp-6Dh]
  unsigned int v107; // [rsp+44h] [rbp-6Dh]
  __int64 v108; // [rsp+48h] [rbp-69h]
  __int64 v109; // [rsp+48h] [rbp-69h]
  unsigned int v110; // [rsp+48h] [rbp-69h]
  unsigned int v111; // [rsp+50h] [rbp-61h]
  unsigned int v112; // [rsp+50h] [rbp-61h]
  __int64 v113; // [rsp+58h] [rbp-59h]
  __int64 v114; // [rsp+58h] [rbp-59h]
  unsigned __int64 LowLimit; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int64 HighLimit; // [rsp+68h] [rbp-49h] BYREF
  unsigned __int64 v117; // [rsp+70h] [rbp-41h]
  __int128 Parameter; // [rsp+78h] [rbp-39h] BYREF
  __int128 v119; // [rsp+88h] [rbp-29h]
  unsigned __int64 v120; // [rsp+98h] [rbp-19h]
  unsigned int v121; // [rsp+A0h] [rbp-11h]
  int v122; // [rsp+A4h] [rbp-Dh]
  _QWORD v123[11]; // [rsp+A8h] [rbp-9h] BYREF
  _UNKNOWN *retaddr; // [rsp+108h] [rbp+57h] BYREF
  unsigned int v126; // [rsp+110h] [rbp+5Fh]
  char v127; // [rsp+110h] [rbp+5Fh]
  unsigned int v128; // [rsp+110h] [rbp+5Fh]
  unsigned int v130; // [rsp+120h] [rbp+6Fh]
  unsigned int v132; // [rsp+130h] [rbp+7Fh]
  unsigned int v133; // [rsp+130h] [rbp+7Fh]
  unsigned int v134; // [rsp+130h] [rbp+7Fh]
  unsigned int v135; // [rsp+130h] [rbp+7Fh]
  unsigned int v136; // [rsp+130h] [rbp+7Fh]

  v130 = a3;
  Number = KeGetPcr()->Prcb.Number;
  v6 = *(unsigned int *)ndisNblTrackerMode;
  v7 = a2;
  v8 = a1[53];
  v9 = a4;
  v113 = v8;
  v10 = a3;
  v106 = Number;
  v11 = a1;
  if ( *(_DWORD *)ndisNblTrackerMode )
  {
    v12 = (struct NDIS_NBL_TRACKER_HANDLE__ *)a1[81];
    v13 = 0;
    a3 = a5;
    v14 = 0;
    v15 = a1[64];
    v16 = ndisNblTrackerEpoch;
    LOBYTE(v17) = a5 & 1;
    LowLimit = (unsigned __int64)v12;
    v111 = a5 & 1;
    v117 = 0;
    v108 = 0;
    v105 = 0;
    if ( *(int *)ndisNblTrackerMode >= 3 )
    {
      ndisNblTrackerRecordEventInternal(v7, v12, (a5 & 2 | 0x104) >> 1, (void *)v15, a5 & 1);
      v13 = 0;
    }
    v18 = v15 & 0xFFFFFFFFFFFFFFFDuLL;
    if ( (v15 & 1) != 0 )
    {
      v6 = 2 * v16;
      v19 = (2 * v16) ^ (v15 ^ (2 * v16)) & 0xFFFFFFFFFFFFFFFDuLL;
      v18 = *(_QWORD *)((v15 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
    }
    else
    {
      v19 = v15 & 0xFFFFFFFFFFFFFFFDuLL;
    }
    Alignment = (_SLIST_HEADER *)v7;
    if ( v7 )
    {
      v21 = LowLimit;
      while ( 1 )
      {
        Region = Alignment[22].Region;
        while ( Alignment[22].Region == Region )
        {
          if ( Region )
          {
            if ( (Region & 4) != 0 )
              goto LABEL_73;
          }
          else if ( !Alignment[7].Region )
          {
            v47 = v21 & 0xFFFFFFFFFFFFFFFDuLL;
            if ( (v21 & 1) != 0 )
              v47 = *(_QWORD *)((v21 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
            Alignment[7].Region = v47;
          }
          v23 = (char *)Alignment[7].Region;
          if ( v23 )
          {
            LODWORD(v12) = (unsigned __int8)*v23;
            if ( (unsigned __int8)((_BYTE)v12 - 17) <= 1u || (_BYTE)v12 == 5 )
            {
              if ( v23 != (char *)v18 || Alignment[1].Region )
              {
                ++v14;
                v6 = v19;
              }
              else
              {
                ++v13;
                v6 = 24;
                v108 = v13;
                ++v14;
              }
              goto LABEL_16;
            }
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = 3;
              WPP_RECORDER_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                (int)v12,
                27,
                12,
                (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                (char)Alignment,
                *v23);
LABEL_208:
              v13 = v108;
            }
          }
          else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 3;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              (int)v12,
              27,
              11,
              (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
              (char)Alignment);
            goto LABEL_208;
          }
LABEL_73:
          v6 = v19 | 4;
LABEL_16:
          Alignment[22].Region = v6;
          Alignment = (_SLIST_HEADER *)Alignment->Alignment;
          if ( !Alignment )
            break;
        }
        v17 = v111;
        if ( (Region & 1) == 0 )
          goto LABEL_22;
        v24 = v117 - v14;
        v117 -= v14;
        if ( !v117 )
          goto LABEL_22;
        if ( (_BYTE)v111 || v105 )
        {
          v12 = (struct NDIS_NBL_TRACKER_HANDLE__ *)((Region & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((Region >> 1) & 1) + 3));
          if ( !(_BYTE)v111 )
            goto LABEL_38;
          goto LABEL_21;
        }
        v105 = 1;
        LOBYTE(v6) = KeGetCurrentIrql();
        v24 = v117;
        v34 = Region >> 1;
        v35 = Region & 0xFFFFFFFFFFFFFFF8uLL;
        v36 = 16 * ((v34 & 1) + 3);
        if ( (_BYTE)v6 == 2 )
        {
          LOBYTE(v17) = 1;
          v12 = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v35 + v36);
          v111 = v17;
LABEL_21:
          v25 = KeGetPcr()->Prcb.Number << 12;
          v6 = *(_QWORD *)v12;
          *(_QWORD *)(v25 + *(_QWORD *)v12) += v24;
          goto LABEL_22;
        }
        LOBYTE(v17) = 0;
        v111 = v17;
        v12 = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v35 + v36);
LABEL_38:
        _InterlockedAdd64((volatile signed __int64 *)v12 + 1, v24);
LABEL_22:
        v13 = v108;
        v117 = v14;
        if ( !Alignment )
        {
          v7 = a2;
          break;
        }
      }
    }
    if ( (v19 & 1) == 0 )
      goto LABEL_29;
    v26 = v14 - v108;
    if ( !v26 )
      goto LABEL_29;
    if ( (_BYTE)v17 || v105 )
    {
      v27 = (v19 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v19 >> 1) & 1) + 3);
      if ( !(_BYTE)v17 )
      {
LABEL_47:
        _InterlockedAdd64((volatile signed __int64 *)(v27 + 8), v26);
        goto LABEL_29;
      }
    }
    else
    {
      LOBYTE(v6) = KeGetCurrentIrql();
      v27 = (v19 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v19 >> 1) & 1) + 3);
      if ( (_BYTE)v6 != 2 )
        goto LABEL_47;
    }
    v28 = KeGetPcr()->Prcb.Number << 12;
    v6 = *(_QWORD *)v27;
    *(_QWORD *)(v28 + *(_QWORD *)v27) += v26;
LABEL_29:
    v8 = v113;
    Number = v106;
    v10 = v130;
    v9 = a4;
    v11 = a1;
  }
  v30 = a5 & 2;
  if ( (a5 & 2) != 0 )
    goto LABEL_31;
  if ( (a5 & 1) == 0 )
  {
    if ( KeGetCurrentIrql() != 2 )
      goto LABEL_31;
    v8 = v113;
  }
  v6 = Number;
  v37 = 96LL * Number;
  if ( *(_BYTE *)(v37 + v8 + 64) )
  {
    v38 = a5 | 1;
    v39 = v37 + v8;
    if ( *(_QWORD *)(v37 + v8 + 48) )
    {
      v63 = *(_QWORD *)(v39 + 56);
      if ( v10 == *(_DWORD *)(v63 + 140) && v38 == *(_DWORD *)(v63 + 132) && (a5 & 0xCB00) == 0 )
      {
        v64 = *(struct _NET_BUFFER_LIST **)v63;
        if ( *(_QWORD *)v63 )
        {
          v66 = v9 + LODWORD(v64->Scratch);
          do
          {
            p_Next = &v64->Next;
            v64 = (struct _NET_BUFFER_LIST *)v64->Link.Alignment;
          }
          while ( v64 );
        }
        else
        {
          p_Next = (struct _NET_BUFFER_LIST **)v63;
          v66 = v9 + 1;
        }
        *p_Next = v7;
        if ( *(_QWORD *)v63 )
          *(_QWORD *)(*(_QWORD *)v63 + 112LL) = v66;
        return;
      }
      *(_QWORD *)(v63 + 112) = v7;
    }
    else
    {
      *(_QWORD *)(v37 + v8 + 48) = v7;
    }
    *(_QWORD *)(v39 + 56) = v7;
    v40 = v7->Link.Alignment;
    v7->Scratch = 0;
    v7->ChildRefCount = v38;
    v7->Status = v10;
    if ( v40 )
      *(_QWORD *)(v40 + 112) = v9;
    return;
  }
LABEL_31:
  v31 = v11[65];
  v32 = (void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int))v11[62];
  v33 = v11[63];
  if ( *(_BYTE *)v31 == 17 )
  {
LABEL_32:
    v32(v33, v7, v130, a4, a5);
    goto LABEL_33;
  }
  if ( (a5 & 2) == 0 && ((a5 & 1) != 0 || KeGetCurrentIrql() == 2) )
  {
    LODWORD(v6) = KeGetPcr()->Prcb.Number;
    v49 = v123;
    v7->Status = v130;
    v50 = v7->Link.Alignment;
    v107 = v6;
    v123[2] = 0;
    v123[0] = v7;
    v123[1] = v7;
    v7->Scratch = 0;
    v7->ChildRefCount = a5;
    if ( v50 )
      *(_QWORD *)(v50 + 112) = a4;
    while ( 1 )
    {
      if ( *(_BYTE *)v31 != 5 )
        goto LABEL_93;
      v51 = (struct _NET_BUFFER_LIST *)*v49;
      if ( !*v49 )
        goto LABEL_93;
      v52 = *(_QWORD *)(v31 + 424) + 96 * v6;
      if ( *(_BYTE *)(v52 + 64) )
        break;
      *(_BYTE *)(v52 + 64) = 1;
      v53 = v31;
      v54 = (struct _NET_BUFFER_LIST *)*v49;
      *v49 = 0;
      if ( v54 )
      {
        do
        {
          ChildRefCount = v54->ChildRefCount;
          NdisReserved2 = v54->NdisReserved2;
          Scratch = (struct _NET_BUFFER_LIST *)v54->Scratch;
          v126 = ChildRefCount;
          v112 = NdisReserved2;
          if ( v54->Link.Alignment )
            v133 = *(_DWORD *)(v54->Link.Alignment + 112);
          else
            v133 = 1;
          v54->ChildRefCount = 0;
          if ( byte_140123720 )
          {
            if ( *(_BYTE *)v31 == 5 )
            {
              v93 = *(_QWORD *)(v31 + 872);
              if ( v93 )
              {
                if ( (*(_DWORD *)(v93 + 56) & 1) != 0 )
                {
                  v94 = (v54->NblFlags & 0x8000) == 0;
                  Parameter = 0;
                  LODWORD(v120) = 0;
                  v119 = 0;
                  if ( v94 )
                  {
                    v110 = *(_DWORD *)(v31 + 880);
                    if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                    {
                      v95 = *(_QWORD *)(v31 + 864);
                      *(_QWORD *)((char *)&v119 + 4) = v110 | 0x100000000LL;
                      LOWORD(Parameter) = 40;
                      *((_QWORD *)&Parameter + 1) = v54;
                      LODWORD(v119) = 1;
                      v120 = 0;
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                                  + 40LL))(
                        xmmword_140123740,
                        v95,
                        &Parameter,
                        0);
                      ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                    }
                    NdisReserved2 = v112;
                    ChildRefCount = v126;
                  }
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && *(_BYTE *)v31 == 5 && (v102 = *(_QWORD *)(v31 + 776)) != 0 )
            (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int, __int64, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int)))ndisVerifierNdisDispatch
             + 14))(
              v33,
              v54,
              NdisReserved2,
              v133,
              ChildRefCount,
              v102,
              v32);
          else
            v32(v33, v54, NdisReserved2, v133, ChildRefCount);
          v54 = Scratch;
        }
        while ( Scratch );
        v53 = v31;
      }
      v6 = v107;
      v49 = (__int64 *)(v52 + 48);
      *(_BYTE *)(v52 + 64) = 0;
      v31 = *(_QWORD *)(v31 + 520);
      v32 = *(void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int))(v53 + 496);
      v33 = *(_QWORD *)(v53 + 504);
    }
    *v49 = 0;
    do
    {
      v89 = v51->ChildRefCount;
      v90 = v51->NdisReserved2;
      v91 = (struct _NET_BUFFER_LIST *)v51->Scratch;
      v136 = v89;
      v128 = v90;
      if ( v51->Link.Alignment )
        v92 = *(_DWORD *)(v51->Link.Alignment + 112);
      else
        v92 = 1;
      v51->ChildRefCount = 0;
      if ( byte_140123720 )
      {
        if ( *(_BYTE *)v31 == 5 )
        {
          v101 = *(_QWORD *)(v31 + 872);
          if ( v101 )
          {
            if ( (*(_DWORD *)(v101 + 56) & 1) != 0 )
            {
              PktMonClientNblLogNdis(v31 + 848, v51, a3, 1);
              v89 = v136;
              v90 = v128;
            }
          }
        }
      }
      if ( ndisVerifierNdisDispatch && *(_BYTE *)v31 == 5 && (v104 = *(_QWORD *)(v31 + 776)) != 0 )
        (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int, __int64, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int)))ndisVerifierNdisDispatch
         + 14))(
          v33,
          v51,
          v90,
          v92,
          v89,
          v104,
          v32);
      else
        v32(v33, v51, v90, v92, v89);
      v51 = v91;
    }
    while ( v91 );
LABEL_93:
    v58 = (struct _NET_BUFFER_LIST *)*v49;
    if ( *v49 )
    {
      *v49 = 0;
      do
      {
        v59 = v58->NdisReserved2;
        v60 = (struct _NET_BUFFER_LIST *)v58->Scratch;
        v61 = v58->ChildRefCount;
        v134 = v59;
        if ( v58->Link.Alignment )
          v62 = *(_DWORD *)(v58->Link.Alignment + 112);
        else
          v62 = 1;
        v58->ChildRefCount = 0;
        if ( byte_140123720 )
        {
          if ( *(_BYTE *)v31 == 5 )
          {
            v99 = *(_QWORD *)(v31 + 872);
            if ( v99 )
            {
              if ( (*(_DWORD *)(v99 + 56) & 1) != 0 )
              {
                PktMonClientNblLogNdis(v31 + 848, v58, a3, 1);
                v59 = v134;
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && *(_BYTE *)v31 == 5 && (v103 = *(_QWORD *)(v31 + 776)) != 0 )
          (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int, __int64, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int)))ndisVerifierNdisDispatch
           + 14))(
            v33,
            v58,
            v59,
            v62,
            v61,
            v103,
            v32);
        else
          v32(v33, v58, v59, v62, v61);
        v58 = v60;
      }
      while ( v60 );
    }
    return;
  }
  v132 = Size;
  LowLimit = 0;
  HighLimit = 0;
  v41 = KeGetPcr()->Prcb.Number << 12;
  v42 = *(_QWORD *)(v41 + qword_140122F78);
  LowLimit = v42;
  HighLimit = *(_QWORD *)(v41 + qword_140122F70);
  if ( (unsigned __int64)&retaddr >= HighLimit || v42 > (unsigned __int64)&retaddr )
  {
    IoGetStackLimits(&LowLimit, &HighLimit);
    v42 = LowLimit;
  }
  if ( (unsigned __int64)&retaddr - v42 >= v132 )
  {
    if ( byte_140123720 )
    {
      if ( *(_BYTE *)v31 == 5 )
      {
        v96 = *(_QWORD *)(v31 + 872);
        if ( v96 )
        {
          if ( (*(_DWORD *)(v96 + 56) & 1) != 0 )
          {
            v94 = (v7->NblFlags & 0x8000) == 0;
            Parameter = 0;
            LODWORD(v120) = 0;
            v119 = 0;
            if ( v94 )
            {
              v97 = *(_DWORD *)(v31 + 880);
              if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
              {
                v98 = *(_QWORD *)(v31 + 864);
                LOWORD(Parameter) = 40;
                *((_QWORD *)&Parameter + 1) = v7;
                LODWORD(v119) = 1;
                *(_QWORD *)((char *)&v119 + 4) = v97 | 0x100000000LL;
                v120 = 0;
                (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1) + 40LL))(
                  xmmword_140123740,
                  v98,
                  &Parameter,
                  0);
                ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
              }
            }
          }
        }
      }
    }
    if ( !ndisVerifierNdisDispatch )
      goto LABEL_32;
    if ( *(_BYTE *)v31 != 5 )
      goto LABEL_32;
    v48 = *(_QWORD *)(v31 + 776);
    if ( !v48 )
      goto LABEL_32;
    (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int, __int64, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int)))ndisVerifierNdisDispatch
     + 14))(
      v33,
      v7,
      v130,
      a4,
      a5,
      v48,
      v32);
LABEL_33:
    if ( !v30 )
      return;
    goto LABEL_116;
  }
  v120 = __PAIR64__(a4, v130);
  v43 = 24576;
  v122 = 0;
  *(_QWORD *)&Parameter = v31;
  *((_QWORD *)&Parameter + 1) = v33;
  *(_QWORD *)&v119 = v32;
  *((_QWORD *)&v119 + 1) = v7;
  v121 = a5;
  if ( (unsigned int)Size > 0x6000 )
    v43 = Size;
  if ( KeExpandKernelStackAndCalloutEx(
         ndisDataPathExpandStackCallback<2,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long,unsigned long)>,
         &Parameter,
         v43,
         0,
         0) >= 0 )
    goto LABEL_33;
  if ( byte_140123720 && (*(_DWORD *)(v31 + 840) & 2) != 0 )
    PktMonClientNblDropNdis(v31 + 784, (_DWORD)v7, v44, 1, -1073741670, -536866813);
  NdisSetStatusInNblChain(v7, -1073741670);
  v45 = 0;
  v46 = (_SLIST_HEADER *)v7;
  if ( v7 )
  {
    do
    {
      v46 = (_SLIST_HEADER *)v46->Alignment;
      ++v45;
    }
    while ( v46 );
  }
  _InterlockedAdd((volatile signed __int32 *)(v31 + 292), v45);
  if ( !v30 )
  {
    ndisQueueStackExpansionFallbackNbls((struct _NDIS_FILTER_BLOCK *)v31, v7, 0);
    return;
  }
LABEL_116:
  if ( !*(_DWORD *)ndisNblTrackerMode )
    return;
  v67 = a5 & 1;
  v68 = ndisNblTrackerEpoch;
  v69 = 0;
  v135 = v67;
  v70 = 0;
  v114 = 0;
  v71 = a1[81];
  v72 = (struct NDIS_NBL_TRACKER_HANDLE__ *)a1[64];
  LowLimit = (unsigned __int64)v72;
  v109 = 0;
  v127 = 0;
  if ( *(int *)ndisNblTrackerMode >= 3 )
  {
    ndisNblTrackerRecordEventInternal(v7, v72, 0x8Cu, (void *)v71, v67);
    v70 = 0;
  }
  v73 = v71 & 0xFFFFFFFFFFFFFFFDuLL;
  if ( (v71 & 1) != 0 )
  {
    v74 = (2 * v68) ^ ((2 * v68) ^ v71) & 0xFFFFFFFFFFFFFFFDuLL;
    v73 = *(_QWORD *)((v73 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
  }
  else
  {
    v74 = v71 & 0xFFFFFFFFFFFFFFFDuLL;
  }
  if ( !v7 )
    goto LABEL_137;
  do
  {
    v75 = (unsigned __int64)v7->NetBufferListInfo[27];
    v76 = LowLimit;
    while ( v7->NetBufferListInfo[27] == (void *)v75 )
    {
      if ( v75 )
      {
        if ( (v75 & 4) != 0 )
          goto LABEL_187;
      }
      else if ( !v7->SourceHandle )
      {
        v100 = v76 & 0xFFFFFFFFFFFFFFFDuLL;
        if ( (v76 & 1) != 0 )
          v100 = *(_QWORD *)((v76 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
        v7->SourceHandle = (void *)v100;
      }
      SourceHandle = (char *)v7->SourceHandle;
      if ( SourceHandle )
      {
        LODWORD(v72) = (unsigned __int8)*SourceHandle;
        if ( (unsigned __int8)((_BYTE)v72 - 17) <= 1u || (_BYTE)v72 == 5 )
        {
          if ( SourceHandle != (char *)v73 || v7->ParentNetBufferList )
          {
            ++v69;
            v78 = v74;
          }
          else
          {
            ++v70;
            v78 = 24;
            v109 = v70;
            ++v69;
          }
          goto LABEL_130;
        }
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v72) = 3;
          WPP_RECORDER_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)v72,
            27,
            12,
            (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
            (char)v7,
            *SourceHandle);
LABEL_209:
          v70 = v109;
        }
      }
      else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v72) = 3;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          (int)v72,
          27,
          11,
          (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
          (char)v7);
        goto LABEL_209;
      }
LABEL_187:
      v78 = v74 | 4;
LABEL_130:
      v7->NetBufferListInfo[27] = (void *)v78;
      v7 = (struct _NET_BUFFER_LIST *)v7->Link.Alignment;
      if ( !v7 )
        break;
    }
    v67 = v135;
    if ( (v75 & 1) == 0 )
      goto LABEL_136;
    v79 = v114 - v69;
    if ( v114 == v69 )
      goto LABEL_136;
    if ( (_BYTE)v135 || v127 )
    {
      v72 = (struct NDIS_NBL_TRACKER_HANDLE__ *)((v75 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v75 >> 1) & 1) + 3));
      if ( !(_BYTE)v135 )
        goto LABEL_145;
      goto LABEL_135;
    }
    v127 = 1;
    CurrentIrql = KeGetCurrentIrql();
    v85 = v75;
    v86 = v75 & 0xFFFFFFFFFFFFFFF8uLL;
    v87 = 16 * (((v85 >> 1) & 1) + 3);
    if ( CurrentIrql == 2 )
    {
      LOBYTE(v67) = 1;
      v72 = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v86 + v87);
      v135 = v67;
LABEL_135:
      v80 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v80 + *(_QWORD *)v72) += v79;
      goto LABEL_136;
    }
    LOBYTE(v67) = 0;
    v135 = v67;
    v72 = (struct NDIS_NBL_TRACKER_HANDLE__ *)(v86 + v87);
LABEL_145:
    _InterlockedAdd64((volatile signed __int64 *)v72 + 1, v79);
LABEL_136:
    v70 = v109;
    v114 = v69;
  }
  while ( v7 );
LABEL_137:
  if ( (v74 & 1) != 0 )
  {
    v81 = v69 - v109;
    if ( v81 )
    {
      if ( (_BYTE)v67 || v127 )
      {
        v82 = (v74 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v74 >> 1) & 1) + 3);
        if ( !(_BYTE)v67 )
          goto LABEL_148;
      }
      else
      {
        v88 = KeGetCurrentIrql();
        v82 = (v74 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v74 >> 1) & 1) + 3);
        if ( v88 != 2 )
        {
LABEL_148:
          _InterlockedAdd64((volatile signed __int64 *)(v82 + 8), v81);
          return;
        }
      }
      v83 = KeGetPcr()->Prcb.Number << 12;
      *(_QWORD *)(v83 + *(_QWORD *)v82) += v81;
    }
  }
}

```

## disassembly

```asm
0x140023960  mov     [rsp-8+arg_18], r9d
0x140023965  mov     [rsp-8+arg_10], r8d
0x14002396a  mov     [rsp-8+arg_8], rdx
0x14002396f  mov     [rsp-8+arg_0], rcx
0x140023974  push    rbp
0x140023975  push    rbx
0x140023976  push    rsi
0x140023977  push    rdi
0x140023978  push    r12
0x14002397a  push    r13
0x14002397c  push    r14
0x14002397e  push    r15
0x140023980  lea     rbp, [rsp-17h]
0x140023985  sub     rsp, 0C8h
0x14002398c  mov     r15d, gs:1A4h
0x140023995  lea     r10, WPP_RECORDER_INITIALIZED
0x14002399c  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x1400239a2  mov     r12, rdx
0x1400239a5  mov     rdx, [rcx+1A8h]
0x1400239ac  mov     edi, r9d
0x1400239af  mov     [rbp+4Fh+var_A8], rdx
0x1400239b3  mov     r14d, r8d
0x1400239b6  mov     [rbp+4Fh+var_BC], r15d
0x1400239ba  mov     rsi, rcx
0x1400239bd  test    eax, eax
0x1400239bf  jz      loc_140023B98
0x1400239c5  mov     rdx, [rcx+288h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x1400239cc  xor     r9d, r9d
0x1400239cf  mov     r8d, [rbp+4Fh+arg_20]
0x1400239d3  xor     r14d, r14d
0x1400239d6  mov     rdi, [rcx+200h]
0x1400239dd  mov     r15d, r8d
0x1400239e0  mov     ebx, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x1400239e6  xor     ecx, ecx
0x1400239e8  and     r15d, 1
0x1400239ec  mov     [rbp+4Fh+LowLimit], rdx
0x1400239f0  mov     [rbp+4Fh+var_B0], r15d
0x1400239f4  mov     [rbp+4Fh+var_90], rcx
0x1400239f8  mov     [rbp+4Fh+var_B8], r9
0x1400239fc  mov     [rbp+4Fh+var_C0], cl
0x1400239ff  cmp     eax, 3
0x140023a02  jl      short loc_140023A2C
0x140023a04  and     r8d, 2
0x140023a08  mov     dword ptr [rsp+100h+Context], r15d; unsigned int
0x140023a0d  or      r8d, 104h
0x140023a14  mov     r9, rdi; void *
0x140023a17  shr     r8d, 1; unsigned int
0x140023a1a  mov     rcx, r12; struct _NET_BUFFER_LIST *
0x140023a1d  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x140023a22  mov     r9d, r14d
0x140023a25  lea     r10, WPP_RECORDER_INITIALIZED
0x140023a2c  mov     r13, rdi
0x140023a2f  and     r13, 0FFFFFFFFFFFFFFFDh
0x140023a33  test    r13b, 1
0x140023a37  jz      loc_140023E98
0x140023a3d  mov     rax, rbx
0x140023a40  add     rax, rax
0x140023a43  mov     rbx, rax
0x140023a46  xor     rbx, rdi
0x140023a49  and     rbx, 0FFFFFFFFFFFFFFFDh
0x140023a4d  xor     rbx, rax
0x140023a50  and     r13, 0FFFFFFFFFFFFFFF8h
0x140023a54  mov     r13, [r13+18h]
0x140023a58  mov     rsi, r12
0x140023a5b  test    r12, r12
0x140023a5e  jz      loc_140023B3C
0x140023a64  mov     r12, [rbp+4Fh+LowLimit]
0x140023a68  mov     rdi, [rsi+168h]
0x140023a6f  lea     r15, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x140023a76  cmp     [rsi+168h], rdi
0x140023a7d  jnz     short loc_140023ACB
0x140023a7f  test    rdi, rdi
0x140023a82  jz      loc_140023EA0
0x140023a88  test    dil, 4
0x140023a8c  jnz     loc_140023ED4
0x140023a92  mov     rcx, [rsi+78h]
0x140023a96  test    rcx, rcx
0x140023a99  jz      loc_140023EC7
0x140023a9f  movzx   edx, byte ptr [rcx]
0x140023aa2  lea     eax, [rdx-11h]
0x140023aa5  cmp     al, 1
0x140023aa7  ja      loc_140024105
0x140023aad  cmp     rcx, r13
0x140023ab0  jz      loc_140023E79
0x140023ab6  inc     r14
0x140023ab9  mov     rax, rbx
0x140023abc  mov     [rsi+168h], rax
0x140023ac3  mov     rsi, [rsi]
0x140023ac6  test    rsi, rsi
0x140023ac9  jnz     short loc_140023A76
0x140023acb  mov     r15d, [rbp+4Fh+var_B0]
0x140023acf  test    dil, 1
0x140023ad3  jz      short loc_140023B20
0x140023ad5  mov     r9, [rbp+4Fh+var_90]
0x140023ad9  sub     r9, r14
0x140023adc  mov     [rbp+4Fh+var_90], r9
0x140023ae0  jz      short loc_140023B20
0x140023ae2  test    r15b, r15b
0x140023ae5  jz      loc_140023BFE
0x140023aeb  mov     rdx, rdi
0x140023aee  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140023af2  shr     rdx, 1
0x140023af5  and     edx, 1
0x140023af8  add     rdx, 3
0x140023afc  shl     rdx, 4
0x140023b00  add     rdx, rdi
0x140023b03  test    r15b, r15b
0x140023b06  jz      loc_140023C43
0x140023b0c  mov     eax, gs:1A4h
0x140023b14  shl     eax, 0Ch
0x140023b17  mov     ecx, eax
0x140023b19  mov     rax, [rdx]
0x140023b1c  add     [rcx+rax], r9
0x140023b20  mov     r9, [rbp+4Fh+var_B8]
0x140023b24  lea     r10, WPP_RECORDER_INITIALIZED
0x140023b2b  mov     [rbp+4Fh+var_90], r14
0x140023b2f  test    rsi, rsi
0x140023b32  jnz     loc_140023A68
0x140023b38  mov     r12, [rbp+4Fh+arg_8]
0x140023b3c  test    bl, 1
0x140023b3f  jz      short loc_140023B85
0x140023b41  sub     r14, [rbp+4Fh+var_B8]
0x140023b45  jz      short loc_140023B85
0x140023b47  test    r15b, r15b
0x140023b4a  jz      loc_140023CBB
0x140023b50  mov     rdx, rbx
0x140023b53  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140023b57  shr     rdx, 1
0x140023b5a  and     edx, 1
0x140023b5d  add     rdx, 3
0x140023b61  shl     rdx, 4
0x140023b65  add     rdx, rbx
0x140023b68  test    r15b, r15b
0x140023b6b  jz      loc_140023CF1
0x140023b71  mov     eax, gs:1A4h
0x140023b79  shl     eax, 0Ch
0x140023b7c  mov     ecx, eax
0x140023b7e  mov     rax, [rdx]
0x140023b81  add     [rcx+rax], r14
0x140023b85  mov     rdx, [rbp+4Fh+var_A8]
0x140023b89  mov     r15d, [rbp+4Fh+var_BC]
0x140023b8d  mov     r14d, [rbp+4Fh+arg_10]
0x140023b91  mov     edi, [rbp+4Fh+arg_18]
0x140023b94  mov     rsi, [rbp+4Fh+arg_0]
0x140023b98  mov     r13d, [rbp+4Fh+arg_20]
0x140023b9c  mov     ebx, r13d
0x140023b9f  and     ebx, 2
0x140023ba2  jz      loc_140023C4D
0x140023ba8  mov     rdi, [rsi+208h]
0x140023baf  mov     r14, [rsi+1F0h]
0x140023bb6  mov     r15, [rsi+1F8h]
0x140023bbd  cmp     byte ptr [rdi], 11h
0x140023bc0  jnz     loc_140023D27
0x140023bc6  mov     r9d, [rbp+4Fh+arg_18]
0x140023bca  mov     rdx, r12
0x140023bcd  mov     r8d, [rbp+4Fh+arg_10]
0x140023bd1  mov     rcx, r15
0x140023bd4  mov     rax, r14
0x140023bd7  mov     dword ptr [rsp+100h+Context], r13d
0x140023bdc  call    _guard_dispatch_icall
0x140023be1  test    ebx, ebx
0x140023be3  jnz     loc_1400241C6
0x140023be9  add     rsp, 0C8h
0x140023bf0  pop     r15
0x140023bf2  pop     r14
0x140023bf4  pop     r13
0x140023bf6  pop     r12
0x140023bf8  pop     rdi
0x140023bf9  pop     rsi
0x140023bfa  pop     rbx
0x140023bfb  pop     rbp
0x140023bfc  retn
0x140023bfe  cmp     [rbp+4Fh+var_C0], 0
0x140023c02  jnz     loc_140023AEB
0x140023c08  mov     [rbp+4Fh+var_C0], 1
0x140023c0c  call    cs:__imp_KeGetCurrentIrql
0x140023c13  nop     dword ptr [rax+rax+00h]
0x140023c18  mov     r9, [rbp+4Fh+var_90]
0x140023c1c  mov     rdx, rdi
0x140023c1f  shr     rdx, 1
0x140023c22  and     rdi, 0FFFFFFFFFFFFFFF8h
0x140023c26  and     edx, 1
0x140023c29  add     rdx, 3
0x140023c2d  shl     rdx, 4
0x140023c31  cmp     al, 2
0x140023c33  jz      loc_140023CFB
0x140023c39  xor     r15b, r15b
0x140023c3c  mov     [rbp+4Fh+var_B0], r15d
0x140023c40  add     rdx, rdi
0x140023c43  lock add [rdx+8], r9
0x140023c48  jmp     loc_140023B20
0x140023c4d  test    r13b, 1
0x140023c51  jz      loc_140023D0A
0x140023c57  mov     eax, r15d
0x140023c5a  lea     rcx, [rax+rax*2]
0x140023c5e  shl     rcx, 5
0x140023c62  cmp     byte ptr [rcx+rdx+40h], 0
0x140023c67  jz      loc_140023BA8
0x140023c6d  or      r13d, 1
0x140023c71  lea     rax, [rcx+rdx]
0x140023c75  cmp     qword ptr [rcx+rdx+30h], 0
0x140023c7b  jnz     loc_140024156
0x140023c81  mov     [rcx+rdx+30h], r12
0x140023c86  mov     [rax+38h], r12
0x140023c8a  mov     rcx, [r12]
0x140023c8e  mov     qword ptr [r12+70h], 0
0x140023c97  mov     [r12+84h], r13d
0x140023c9f  mov     [r12+8Ch], r14d
0x140023ca7  test    rcx, rcx
0x140023caa  jz      loc_140023BE9
0x140023cb0  mov     eax, edi
0x140023cb2  mov     [rcx+70h], rax
0x140023cb6  jmp     loc_140023BE9
0x140023cbb  cmp     [rbp+4Fh+var_C0], 0
0x140023cbf  jnz     loc_140023B50
0x140023cc5  call    cs:__imp_KeGetCurrentIrql
0x140023ccc  nop     dword ptr [rax+rax+00h]
0x140023cd1  mov     rdx, rbx
0x140023cd4  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140023cd8  shr     rdx, 1
0x140023cdb  and     edx, 1
0x140023cde  add     rdx, 3
0x140023ce2  shl     rdx, 4
0x140023ce6  add     rdx, rbx
0x140023ce9  cmp     al, 2
0x140023ceb  jz      loc_140023B71
0x140023cf1  lock add [rdx+8], r14
0x140023cf6  jmp     loc_140023B85
0x140023cfb  mov     r15b, 1
0x140023cfe  add     rdx, rdi
0x140023d01  mov     [rbp+4Fh+var_B0], r15d
0x140023d05  jmp     loc_140023B0C
0x140023d0a  call    cs:__imp_KeGetCurrentIrql
0x140023d11  nop     dword ptr [rax+rax+00h]
0x140023d16  cmp     al, 2
0x140023d18  jnz     loc_140023BA8
0x140023d1e  mov     rdx, [rbp+4Fh+var_A8]
0x140023d22  jmp     loc_140023C57
0x140023d27  test    ebx, ebx
0x140023d29  jnz     short loc_140023D49
0x140023d2b  test    r13b, 1
0x140023d2f  jnz     loc_140023F41
0x140023d35  call    cs:__imp_KeGetCurrentIrql
0x140023d3c  nop     dword ptr [rax+rax+00h]
0x140023d41  cmp     al, 2
0x140023d43  jz      loc_140023F41
0x140023d49  mov     eax, cs:Size
0x140023d4f  lea     rsi, [rbp+57h]
0x140023d53  mov     [rbp+4Fh+arg_20], eax
0x140023d56  mov     [rbp+4Fh+LowLimit], 0
0x140023d5e  mov     [rbp+4Fh+HighLimit], 0
0x140023d66  mov     eax, gs:1A4h
0x140023d6e  shl     eax, 0Ch
0x140023d71  mov     ecx, eax
0x140023d73  mov     rax, cs:qword_140122F78
0x140023d7a  mov     rdx, [rcx+rax]
0x140023d7e  mov     rax, cs:qword_140122F70
0x140023d85  mov     [rbp+4Fh+LowLimit], rdx
0x140023d89  mov     r8, [rcx+rax]
0x140023d8d  mov     [rbp+4Fh+HighLimit], r8
0x140023d91  cmp     rsi, r8
0x140023d94  jb      loc_14002440B
0x140023d9a  lea     rdx, [rbp+4Fh+HighLimit]; HighLimit
0x140023d9e  lea     rcx, [rbp+4Fh+LowLimit]; LowLimit
0x140023da2  call    cs:__imp_IoGetStackLimits
0x140023da9  nop     dword ptr [rax+rax+00h]
0x140023dae  mov     rdx, [rbp+4Fh+LowLimit]
0x140023db2  mov     eax, [rbp+4Fh+arg_20]
0x140023db5  sub     rsi, rdx
0x140023db8  cmp     rsi, rax
0x140023dbb  jnb     loc_140023EE0
0x140023dc1  mov     ecx, [rbp+4Fh+arg_10]
0x140023dc4  mov     eax, cs:Size
0x140023dca  mov     edx, [rbp+4Fh+arg_18]
0x140023dcd  mov     dword ptr [rbp+4Fh+var_68], ecx
0x140023dd0  mov     ecx, 6000h
0x140023dd5  mov     [rbp+4Fh+var_5C], 0
0x140023ddc  mov     qword ptr [rbp+4Fh+Parameter], rdi
0x140023de0  mov     qword ptr [rbp+4Fh+Parameter+8], r15
0x140023de4  mov     qword ptr [rbp+4Fh+var_78], r14
0x140023de8  mov     qword ptr [rbp+4Fh+var_78+8], r12
0x140023dec  mov     dword ptr [rbp+4Fh+var_68+4], edx
0x140023def  mov     [rbp+4Fh+var_60], r13d
0x140023df3  cmp     eax, ecx
0x140023df5  ja      loc_140024878
0x140023dfb  movsxd  r8, ecx; Size
0x140023dfe  lea     rdx, [rbp+4Fh+Parameter]; Parameter
0x140023e02  lea     rcx, ??$ndisDataPathExpandStackCallback@$01$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z@@YAXPEAX@Z; Callout
0x140023e09  mov     [rsp+100h+Context], 0; Context
0x140023e12  xor     r9d, r9d; Wait
0x140023e15  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140023e1c  nop     dword ptr [rax+rax+00h]
0x140023e21  test    eax, eax
0x140023e23  jns     loc_140023BE1
0x140023e29  cmp     cs:byte_140123720, 0
0x140023e30  jnz     loc_140024883
0x140023e36  mov     edx, 0C000009Ah; int
0x140023e3b  mov     rcx, r12; struct _NET_BUFFER_LIST *
0x140023e3e  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x140023e43  xor     ecx, ecx
  ... truncated ...
```
