# ndisFilterIndicateReceiveNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong)

- ea: `0x14000e1e0`
- end: `0x14000eb66`
- name: `?ndisFilterIndicateReceiveNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z`
- size: `2438`
- prototype: `void(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140004890`
- `0x14000de20`
- `0x14000e1e0`
- `0x14002c970`
- `0x14002c9d0`
- `0x14002de40`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000e319`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e343`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e319`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e343`
- `ntoskrnl!IoGetStackLimits` at `0x14000e3b0`
- `ntoskrnl!IoGetStackLimits` at `0x14000e3b0`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000e461`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000e461`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000e829`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000e903`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000e829`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14000e903`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000e88e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000e96c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000e88e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000e96c`

## pseudocode

```c
void __fastcall ndisFilterIndicateReceiveNetBufferLists(
        void *a1,
        struct _NET_BUFFER_LIST *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v5; // rax
  unsigned int v8; // r13d
  __int64 v9; // rdx
  __int64 v10; // r12
  unsigned int v11; // ebx
  unsigned int v12; // r15d
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // esi
  __int64 v17; // rax
  unsigned __int64 Alignment; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // rax
  int v22; // ecx
  int v23; // r8d
  struct _NDIS_FILTER_BLOCK *v24; // r9
  unsigned int v25; // ecx
  struct _NET_BUFFER_LIST *i; // rax
  __int64 *v27; // r15
  unsigned __int64 v28; // rcx
  void (__fastcall *v29)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int); // rdi
  __int64 j; // rsi
  struct _NET_BUFFER_LIST *v31; // rbx
  __int64 v32; // r14
  unsigned __int64 v33; // r13
  struct _NET_BUFFER_LIST *v34; // rdi
  void (__fastcall *v35)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // rbx
  __int64 v36; // rsi
  unsigned int v37; // ecx
  __int64 v38; // r8
  struct _NET_BUFFER_LIST *v39; // r15
  unsigned int v40; // r12d
  struct _NET_BUFFER_LIST *v41; // rbx
  struct _NET_BUFFER_LIST *v42; // r14
  unsigned int v43; // r12d
  unsigned int v44; // r13d
  unsigned int v45; // r15d
  __int64 *v46; // rdx
  __int64 *v47; // rax
  _QWORD *v48; // rcx
  unsigned int v49; // r12d
  unsigned int NdisReserved2; // ecx
  struct _NET_BUFFER_LIST *Scratch; // r14
  unsigned int ChildRefCount; // r13d
  unsigned int v53; // r12d
  __int64 v54; // rax
  bool v55; // zf
  BOOLEAN v56; // al
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // r9
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // r8
  unsigned __int64 v66; // [rsp+40h] [rbp-71h]
  __int64 v67; // [rsp+48h] [rbp-69h]
  void (__fastcall *v68)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int); // [rsp+48h] [rbp-69h]
  unsigned int v69; // [rsp+50h] [rbp-61h]
  __int128 Parameter; // [rsp+58h] [rbp-59h] BYREF
  __int128 v71; // [rsp+68h] [rbp-49h]
  unsigned __int64 v72; // [rsp+78h] [rbp-39h]
  unsigned int v73; // [rsp+80h] [rbp-31h]
  int v74; // [rsp+84h] [rbp-2Dh]
  unsigned __int64 LowLimit; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int64 HighLimit; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v77; // [rsp+98h] [rbp-19h]
  _QWORD v78[12]; // [rsp+A0h] [rbp-11h] BYREF
  _UNKNOWN *retaddr; // [rsp+108h] [rbp+57h] BYREF
  unsigned int v80; // [rsp+110h] [rbp+5Fh]
  __int64 v81; // [rsp+110h] [rbp+5Fh]
  unsigned int v82; // [rsp+110h] [rbp+5Fh]
  unsigned int v83; // [rsp+130h] [rbp+7Fh]
  unsigned int v84; // [rsp+130h] [rbp+7Fh]
  unsigned int v85; // [rsp+130h] [rbp+7Fh]
  unsigned int v86; // [rsp+130h] [rbp+7Fh]

  LODWORD(v5) = KeGetPcr()->Prcb.Number;
  v8 = a3;
  v9 = *((_QWORD *)a1 + 53);
  v10 = a4;
  v11 = a5 & 2;
  v80 = v5;
  v12 = a5 & 1;
  v67 = v9;
  if ( *(_DWORD *)ndisNblTrackerMode )
  {
    ndisNblTrackerTransferOwnershipInternal(
      a2,
      *((struct NDIS_NBL_TRACKER_HANDLE__ **)a1 + 81),
      *((struct NDIS_NBL_TRACKER_HANDLE__ **)a1 + 64),
      (enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT)((v11 != 0) + 130),
      a5 & 1);
    v5 = v80;
    v9 = v67;
  }
  if ( (a5 & 2) != 0 )
    goto LABEL_4;
  if ( (a5 & 1) == 0 )
  {
    if ( KeGetCurrentIrql() != 2 )
      goto LABEL_4;
    v5 = v80;
    v9 = v67;
  }
  v15 = 96 * v5;
  if ( *(_BYTE *)(96 * v5 + v9 + 64) )
  {
    v16 = a5 | 1;
    v17 = v15 + v9;
    if ( *(_QWORD *)(v15 + v9 + 48) )
    {
      v46 = *(__int64 **)(v17 + 56);
      if ( v8 == *((_DWORD *)v46 + 35) && v16 == *((_DWORD *)v46 + 33) && (a5 & 0xCB00) == 0 )
      {
        v47 = (__int64 *)*v46;
        if ( *v46 )
        {
          v49 = *((_DWORD *)v47 + 28) + v10;
          do
          {
            v48 = v47;
            v47 = (__int64 *)*v47;
          }
          while ( v47 );
        }
        else
        {
          v48 = v46;
          v49 = v10 + 1;
        }
        *v48 = a2;
        if ( *v46 )
          *(_QWORD *)(*v46 + 112) = v49;
        return;
      }
      v46[14] = (__int64)a2;
    }
    else
    {
      *(_QWORD *)(v15 + v9 + 48) = a2;
    }
    *(_QWORD *)(v17 + 56) = a2;
    Alignment = a2->Link.Alignment;
    a2->Scratch = 0;
    a2->ChildRefCount = v16;
    a2->Status = v8;
    if ( Alignment )
      *(_QWORD *)(Alignment + 112) = v10;
    return;
  }
LABEL_4:
  v14 = *((_QWORD *)a1 + 65);
  v68 = (void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int))*((_QWORD *)a1 + 62);
  v81 = *((_QWORD *)a1 + 63);
  v66 = v14;
  if ( *(_BYTE *)v14 == 17 )
  {
    (*((void (__fastcall **)(_QWORD, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int))a1 + 62))(
      *((_QWORD *)a1 + 63),
      a2,
      v8,
      (unsigned int)v10,
      a5);
    goto LABEL_6;
  }
  if ( (a5 & 2) != 0 )
  {
LABEL_19:
    v83 = Size;
    LowLimit = 0;
    HighLimit = 0;
    v19 = KeGetPcr()->Prcb.Number << 12;
    v20 = *(_QWORD *)(v19 + qword_14011CF78);
    LowLimit = v20;
    HighLimit = *(_QWORD *)(v19 + qword_14011CF70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v20 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v20 = LowLimit;
    }
    v21 = v66;
    if ( (unsigned __int64)&retaddr - v20 < v83 )
    {
      *(_QWORD *)&Parameter = v66;
      v22 = 24576;
      *((_QWORD *)&Parameter + 1) = v81;
      *(_QWORD *)&v71 = v68;
      v74 = 0;
      *((_QWORD *)&v71 + 1) = a2;
      v72 = __PAIR64__(v10, v8);
      v73 = a5;
      if ( (unsigned int)Size > 0x6000 )
        v22 = Size;
      if ( KeExpandKernelStackAndCalloutEx(
             ndisDataPathExpandStackCallback<2,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long,unsigned long)>,
             &Parameter,
             v22,
             0,
             0) < 0 )
      {
        if ( byte_14011D730 && (*(_DWORD *)(v66 + 840) & 2) != 0 )
          PktMonClientNblDropNdis(v66 + 784, (_DWORD)a2, v23, 1, -1073741670, -536866813);
        NdisSetStatusInNblChain(a2, -1073741670);
        v25 = 0;
        for ( i = a2; i; ++v25 )
          i = (struct _NET_BUFFER_LIST *)i->Link.Alignment;
        _InterlockedAdd(&v24->DroppedReceiveNbls, v25);
        if ( !v11 )
        {
          ndisQueueStackExpansionFallbackNbls(v24, a2, 0);
          return;
        }
LABEL_70:
        if ( *(_DWORD *)ndisNblTrackerMode )
          ndisNblTrackerTransferOwnershipInternal(
            a2,
            *((struct NDIS_NBL_TRACKER_HANDLE__ **)a1 + 64),
            *((struct NDIS_NBL_TRACKER_HANDLE__ **)a1 + 81),
            NdisNblTrackerEvent_ReturnedToFilterResources,
            v12);
        return;
      }
    }
    else
    {
      if ( byte_14011D730 )
      {
        if ( *(_BYTE *)v66 == 5 )
        {
          v58 = *(_QWORD *)(v66 + 872);
          if ( v58 )
          {
            if ( (*(_DWORD *)(v58 + 56) & 1) != 0 )
            {
              v55 = (a2->NblFlags & 0x8000) == 0;
              Parameter = 0;
              LODWORD(v72) = 0;
              v71 = 0;
              if ( v55 )
              {
                v86 = *(_DWORD *)(v66 + 880);
                if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                {
                  LOWORD(Parameter) = 40;
                  v59 = *(_QWORD *)(v66 + 864);
                  *(_QWORD *)((char *)&v71 + 4) = v86 | 0x100000000LL;
                  *((_QWORD *)&Parameter + 1) = a2;
                  LODWORD(v71) = 1;
                  v72 = 0;
                  (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                              + 40LL))(
                    xmmword_14011D750,
                    v59,
                    &Parameter,
                    0);
                  ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                }
              }
            }
            v21 = v66;
          }
        }
      }
      if ( ndisVerifierNdisDispatch && *(_BYTE *)v21 == 5 && (v63 = *(_QWORD *)(v21 + 776)) != 0 )
        (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int, __int64, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int)))ndisVerifierNdisDispatch
         + 14))(
          v81,
          a2,
          v8,
          (unsigned int)v10,
          a5,
          v63,
          v68);
      else
        v68(v81, a2, v8, (unsigned int)v10, a5);
    }
LABEL_6:
    if ( !v11 )
      return;
    goto LABEL_70;
  }
  if ( (a5 & 1) == 0 )
  {
    if ( KeGetCurrentIrql() != 2 )
      goto LABEL_19;
    v14 = v66;
  }
  LODWORD(v5) = KeGetPcr()->Prcb.Number;
  v27 = v78;
  v28 = a2->Link.Alignment;
  v69 = v5;
  v78[2] = 0;
  v78[0] = a2;
  v78[1] = a2;
  a2->Scratch = 0;
  a2->ChildRefCount = a5;
  a2->Status = v8;
  if ( v28 )
    *(_QWORD *)(v28 + 112) = v10;
  v29 = v68;
  for ( j = v81; *(_BYTE *)v14 == 5; v81 = j )
  {
    v31 = (struct _NET_BUFFER_LIST *)*v27;
    if ( !*v27 )
      break;
    v32 = *(_QWORD *)(v14 + 424) + 96 * v5;
    if ( *(_BYTE *)(v32 + 64) )
    {
      *v27 = 0;
      do
      {
        NdisReserved2 = v31->NdisReserved2;
        Scratch = (struct _NET_BUFFER_LIST *)v31->Scratch;
        ChildRefCount = v31->ChildRefCount;
        v85 = NdisReserved2;
        if ( v31->Link.Alignment )
          v53 = *(_DWORD *)(v31->Link.Alignment + 112);
        else
          v53 = 1;
        v31->ChildRefCount = 0;
        if ( byte_14011D730 )
        {
          if ( *(_BYTE *)v14 == 5 )
          {
            v61 = *(_QWORD *)(v14 + 872);
            if ( v61 )
            {
              if ( (*(_DWORD *)(v61 + 56) & 1) != 0 )
              {
                PktMonClientNblLogNdis(v14 + 848, v31, a3, 1);
                v14 = v66;
                NdisReserved2 = v85;
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && *(_BYTE *)v14 == 5 && (v65 = *(_QWORD *)(v14 + 776)) != 0 )
          (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int, __int64, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int)))ndisVerifierNdisDispatch
           + 14))(
            j,
            v31,
            NdisReserved2,
            v53,
            ChildRefCount,
            v65,
            v29);
        else
          v29(j, v31, NdisReserved2, v53, ChildRefCount);
        v14 = v66;
        v31 = Scratch;
      }
      while ( Scratch );
      break;
    }
    *(_BYTE *)(v32 + 64) = 1;
    v33 = v14;
    v34 = (struct _NET_BUFFER_LIST *)*v27;
    LowLimit = v14;
    *v27 = 0;
    if ( v34 )
    {
      v35 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v68;
      v36 = v81;
      do
      {
        v37 = v34->ChildRefCount;
        v38 = v34->NdisReserved2;
        v39 = (struct _NET_BUFFER_LIST *)v34->Scratch;
        v84 = v37;
        v82 = v34->NdisReserved2;
        if ( v34->Link.Alignment )
          v40 = *(_DWORD *)(v34->Link.Alignment + 112);
        else
          v40 = 1;
        v34->ChildRefCount = 0;
        if ( byte_14011D730 )
        {
          if ( *(_BYTE *)v14 == 5 )
          {
            v54 = *(_QWORD *)(v14 + 872);
            if ( v54 )
            {
              if ( (*(_DWORD *)(v54 + 56) & 1) != 0 )
              {
                v55 = (v34->NblFlags & 0x8000) == 0;
                Parameter = 0;
                LODWORD(v72) = 0;
                v71 = 0;
                if ( v55 )
                {
                  v77 = *(_DWORD *)(v14 + 880);
                  v56 = ExAcquireRundownProtectionCacheAware(RunRefCacheAware);
                  v14 = v66;
                  if ( v56 )
                  {
                    v57 = *(_QWORD *)(v66 + 864);
                    *(_QWORD *)((char *)&v71 + 4) = v77 | 0x100000000LL;
                    LOWORD(Parameter) = 40;
                    *((_QWORD *)&Parameter + 1) = v34;
                    LODWORD(v71) = 1;
                    v72 = 0;
                    (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                + 40LL))(
                      xmmword_14011D750,
                      v57,
                      &Parameter,
                      0);
                    ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                    v14 = v66;
                  }
                  v38 = v82;
                  v37 = v84;
                }
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && *(_BYTE *)v14 == 5 && (v62 = *(_QWORD *)(v14 + 776)) != 0 )
        {
          (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, __int64, _QWORD, unsigned int, __int64, void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)))ndisVerifierNdisDispatch
           + 14))(
            v36,
            v34,
            v38,
            v40,
            v37,
            v62,
            v35);
        }
        else
        {
          v68(v36, v34, v38, v40, v37);
          v35 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v68;
        }
        v14 = v66;
        v34 = v39;
      }
      while ( v39 );
      v33 = LowLimit;
    }
    v5 = v69;
    v27 = (__int64 *)(v32 + 48);
    *(_BYTE *)(v32 + 64) = 0;
    v14 = *(_QWORD *)(v14 + 520);
    v29 = *(void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int))(v33 + 496);
    j = *(_QWORD *)(v33 + 504);
    v66 = v14;
    v68 = v29;
  }
  v41 = (struct _NET_BUFFER_LIST *)*v27;
  if ( *v27 )
  {
    *v27 = 0;
    do
    {
      v42 = (struct _NET_BUFFER_LIST *)v41->Scratch;
      v43 = v41->ChildRefCount;
      v44 = v41->NdisReserved2;
      if ( v41->Link.Alignment )
        v45 = *(_DWORD *)(v41->Link.Alignment + 112);
      else
        v45 = 1;
      v41->ChildRefCount = 0;
      if ( byte_14011D730 )
      {
        if ( *(_BYTE *)v14 == 5 )
        {
          v60 = *(_QWORD *)(v14 + 872);
          if ( v60 )
          {
            if ( (*(_DWORD *)(v60 + 56) & 1) != 0 )
              PktMonClientNblLogNdis(v14 + 848, v41, a3, 1);
          }
        }
      }
      if ( ndisVerifierNdisDispatch && *(_BYTE *)v66 == 5 && (v64 = *(_QWORD *)(v66 + 776)) != 0 )
        (*((void (__fastcall **)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int, __int64, void (__fastcall *)(__int64, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, unsigned int)))ndisVerifierNdisDispatch
         + 14))(
          j,
          v41,
          v44,
          v45,
          v43,
          v64,
          v29);
      else
        v29(j, v41, v44, v45, v43);
      v14 = v66;
      v41 = v42;
    }
    while ( v42 );
  }
}

```

## disassembly

```asm
0x14000e1e0  push    rbp
0x14000e1e2  push    rbx
0x14000e1e3  push    rsi
0x14000e1e4  push    rdi
0x14000e1e5  push    r12
0x14000e1e7  push    r13
0x14000e1e9  push    r14
0x14000e1eb  push    r15
0x14000e1ed  lea     rbp, [rsp-17h]
0x14000e1f2  sub     rsp, 0C8h
0x14000e1f9  mov     eax, gs:1A4h
0x14000e201  mov     r14, rdx
0x14000e204  mov     esi, [rbp+4Fh+arg_20]
0x14000e207  mov     r13d, r8d
0x14000e20a  mov     rdx, [rcx+1A8h]
0x14000e211  mov     ebx, esi
0x14000e213  mov     r15d, esi
0x14000e216  mov     r12d, r9d
0x14000e219  and     ebx, 2
0x14000e21c  mov     dword ptr [rbp+4Fh+arg_0], eax
0x14000e21f  and     r15d, 1
0x14000e223  mov     [rbp+4Fh+var_B8], rdx
0x14000e227  cmp     cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A, 0; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14000e22e  mov     rdi, rcx
0x14000e231  jz      short loc_14000E265
0x14000e233  mov     r8, [rcx+200h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000e23a  xor     r9d, r9d
0x14000e23d  mov     rdx, [rcx+288h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14000e244  test    ebx, ebx
0x14000e246  mov     rcx, r14; struct _NET_BUFFER_LIST *
0x14000e249  mov     dword ptr [rsp+100h+Context], r15d; unsigned int
0x14000e24e  setnz   r9b
0x14000e252  add     r9d, 82h; enum _NDIS_NBL_TRACKER_OWNERSHIP_EVENT
0x14000e259  call    ?ndisNblTrackerTransferOwnershipInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@1W4_NDIS_NBL_TRACKER_OWNERSHIP_EVENT@@K@Z; ndisNblTrackerTransferOwnershipInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,NDIS_NBL_TRACKER_HANDLE__ *,_NDIS_NBL_TRACKER_OWNERSHIP_EVENT,ulong)
0x14000e25e  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x14000e261  mov     rdx, [rbp+4Fh+var_B8]
0x14000e265  test    ebx, ebx
0x14000e267  jz      short loc_14000E2C5
0x14000e269  mov     rdx, [rdi+208h]
0x14000e270  mov     r10, [rdi+1F0h]
0x14000e277  mov     rcx, [rdi+1F8h]
0x14000e27e  mov     [rbp+4Fh+var_B8], r10
0x14000e282  cmp     byte ptr [rdx], 11h
0x14000e285  mov     [rbp+4Fh+arg_0], rcx
0x14000e289  mov     [rbp+4Fh+var_C0], rdx
0x14000e28d  jnz     loc_14000E336
0x14000e293  mov     dword ptr [rsp+100h+Context], esi
0x14000e297  mov     r9d, r12d
0x14000e29a  mov     r8d, r13d
0x14000e29d  mov     rdx, r14
0x14000e2a0  mov     rax, r10
0x14000e2a3  call    _guard_dispatch_icall
0x14000e2a8  test    ebx, ebx
0x14000e2aa  jnz     loc_14000E716
0x14000e2b0  add     rsp, 0C8h
0x14000e2b7  pop     r15
0x14000e2b9  pop     r14
0x14000e2bb  pop     r13
0x14000e2bd  pop     r12
0x14000e2bf  pop     rdi
0x14000e2c0  pop     rsi
0x14000e2c1  pop     rbx
0x14000e2c2  pop     rbp
0x14000e2c3  retn
0x14000e2c5  test    r15d, r15d
0x14000e2c8  jz      short loc_14000E319
0x14000e2ca  lea     rcx, [rax+rax*2]
0x14000e2ce  shl     rcx, 5
0x14000e2d2  cmp     byte ptr [rcx+rdx+40h], 0
0x14000e2d7  jz      short loc_14000E269
0x14000e2d9  or      esi, 1
0x14000e2dc  lea     rax, [rcx+rdx]
0x14000e2e0  cmp     qword ptr [rcx+rdx+30h], 0
0x14000e2e6  jnz     loc_14000E6B3
0x14000e2ec  mov     [rcx+rdx+30h], r14
0x14000e2f1  mov     [rax+38h], r14
0x14000e2f5  mov     rcx, [r14]
0x14000e2f8  mov     qword ptr [r14+70h], 0
0x14000e300  mov     [r14+84h], esi
0x14000e307  mov     [r14+8Ch], r13d
0x14000e30e  test    rcx, rcx
0x14000e311  jz      short loc_14000E2B0
0x14000e313  mov     [rcx+70h], r12
0x14000e317  jmp     short loc_14000E2B0
0x14000e319  call    cs:__imp_KeGetCurrentIrql
0x14000e320  nop     dword ptr [rax+rax+00h]
0x14000e325  cmp     al, 2
0x14000e327  jnz     loc_14000E269
0x14000e32d  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x14000e330  mov     rdx, [rbp+4Fh+var_B8]
0x14000e334  jmp     short loc_14000E2CA
0x14000e336  test    ebx, ebx
0x14000e338  jnz     short loc_14000E357
0x14000e33a  test    r15d, r15d
0x14000e33d  jnz     loc_14000E4CE
0x14000e343  call    cs:__imp_KeGetCurrentIrql
0x14000e34a  nop     dword ptr [rax+rax+00h]
0x14000e34f  cmp     al, 2
0x14000e351  jz      loc_14000E4CA
0x14000e357  mov     eax, cs:Size
0x14000e35d  lea     rdx, [rbp+57h]
0x14000e361  mov     [rbp+4Fh+arg_20], eax
0x14000e364  mov     [rbp+4Fh+LowLimit], 0
0x14000e36c  mov     [rbp+4Fh+HighLimit], 0
0x14000e374  mov     eax, gs:1A4h
0x14000e37c  shl     eax, 0Ch
0x14000e37f  mov     ecx, eax
0x14000e381  mov     rax, cs:qword_14011CF78
0x14000e388  mov     r8, [rcx+rax]
0x14000e38c  mov     rax, cs:qword_14011CF70
0x14000e393  mov     [rbp+4Fh+LowLimit], r8
0x14000e397  mov     r9, [rcx+rax]
0x14000e39b  mov     [rbp+4Fh+HighLimit], r9
0x14000e39f  cmp     rdx, r9
0x14000e3a2  jb      loc_14000E749
0x14000e3a8  lea     rdx, [rbp+4Fh+HighLimit]; HighLimit
0x14000e3ac  lea     rcx, [rbp+4Fh+LowLimit]; LowLimit
0x14000e3b0  call    cs:__imp_IoGetStackLimits
0x14000e3b7  nop     dword ptr [rax+rax+00h]
0x14000e3bc  mov     r8, [rbp+4Fh+LowLimit]
0x14000e3c0  lea     rdx, [rbp+57h]
0x14000e3c4  mov     eax, [rbp+4Fh+arg_20]
0x14000e3c7  sub     rdx, r8
0x14000e3ca  cmp     rdx, rax
0x14000e3cd  mov     rax, [rbp+4Fh+var_C0]
0x14000e3d1  jb      short loc_14000E40A
0x14000e3d3  cmp     cs:byte_14011D730, 0
0x14000e3da  jnz     loc_14000E8AA
0x14000e3e0  mov     rcx, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14000e3e7  test    rcx, rcx
0x14000e3ea  jnz     loc_14000EA54
0x14000e3f0  mov     rcx, [rbp+4Fh+arg_0]
0x14000e3f4  mov     r9d, r12d
0x14000e3f7  mov     rax, [rbp+4Fh+var_B8]
0x14000e3fb  mov     r8d, r13d
0x14000e3fe  mov     dword ptr [rsp+100h+Context], esi
0x14000e402  mov     rdx, r14
0x14000e405  jmp     loc_14000E2A3
0x14000e40a  mov     qword ptr [rbp+4Fh+Parameter], rax
0x14000e40e  mov     ecx, 6000h
0x14000e413  mov     rax, [rbp+4Fh+arg_0]
0x14000e417  mov     qword ptr [rbp+4Fh+Parameter+8], rax
0x14000e41b  mov     rax, [rbp+4Fh+var_B8]
0x14000e41f  mov     qword ptr [rbp+4Fh+var_98], rax
0x14000e423  mov     eax, cs:Size
0x14000e429  mov     [rbp+4Fh+var_7C], 0
0x14000e430  mov     qword ptr [rbp+4Fh+var_98+8], r14
0x14000e434  mov     dword ptr [rbp+4Fh+var_88+4], r12d
0x14000e438  mov     dword ptr [rbp+4Fh+var_88], r13d
0x14000e43c  mov     [rbp+4Fh+var_80], esi
0x14000e43f  cmp     eax, ecx
0x14000e441  ja      loc_14000EB22
0x14000e447  movsxd  r8, ecx; Size
0x14000e44a  lea     rdx, [rbp+4Fh+Parameter]; Parameter
0x14000e44e  lea     rcx, ??$ndisDataPathExpandStackCallback@$01$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z@@YAXPEAX@Z; Callout
0x14000e455  mov     [rsp+100h+Context], 0; Context
0x14000e45e  xor     r9d, r9d; Wait
0x14000e461  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000e468  nop     dword ptr [rax+rax+00h]
0x14000e46d  test    eax, eax
0x14000e46f  jns     loc_14000E2A8
0x14000e475  cmp     cs:byte_14011D730, 0
0x14000e47c  mov     r9, [rbp+4Fh+var_C0]
0x14000e480  jnz     loc_14000EB2D
0x14000e486  mov     edx, 0C000009Ah; int
0x14000e48b  mov     rcx, r14; struct _NET_BUFFER_LIST *
0x14000e48e  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x14000e493  xor     ecx, ecx
0x14000e495  mov     rax, r14
0x14000e498  test    r14, r14
0x14000e49b  jz      short loc_14000E4A7
0x14000e49d  mov     rax, [rax]
0x14000e4a0  inc     ecx
0x14000e4a2  test    rax, rax
0x14000e4a5  jnz     short loc_14000E49D
0x14000e4a7  lock add [r9+124h], ecx
0x14000e4af  test    ebx, ebx
0x14000e4b1  jnz     loc_14000E716
0x14000e4b7  xor     r8d, r8d; unsigned __int8
0x14000e4ba  mov     rdx, r14; struct _NET_BUFFER_LIST *
0x14000e4bd  mov     rcx, r9; struct _NDIS_FILTER_BLOCK *
0x14000e4c0  call    ?ndisQueueStackExpansionFallbackNbls@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER_LIST@@E@Z; ndisQueueStackExpansionFallbackNbls(_NDIS_FILTER_BLOCK *,_NET_BUFFER_LIST *,uchar)
0x14000e4c5  jmp     loc_14000E2B0
0x14000e4ca  mov     rdx, [rbp+4Fh+var_C0]
0x14000e4ce  mov     eax, gs:1A4h
0x14000e4d6  lea     r15, [rbp+4Fh+var_60]
0x14000e4da  mov     rcx, [r14]
0x14000e4dd  mov     [rbp+4Fh+var_B0], eax
0x14000e4e0  mov     [rbp+4Fh+var_50], 0
0x14000e4e8  mov     [rbp+4Fh+var_60], r14
0x14000e4ec  mov     [rbp+4Fh+var_58], r14
0x14000e4f0  mov     qword ptr [r14+70h], 0
0x14000e4f8  mov     [r14+84h], esi
0x14000e4ff  mov     [r14+8Ch], r13d
0x14000e506  test    rcx, rcx
0x14000e509  jz      short loc_14000E50F
0x14000e50b  mov     [rcx+70h], r12
0x14000e50f  mov     rdi, [rbp+4Fh+var_B8]
0x14000e513  mov     rsi, [rbp+4Fh+arg_0]
0x14000e517  cmp     byte ptr [rdx], 5
0x14000e51a  jnz     loc_14000E620
0x14000e520  mov     rbx, [r15]
0x14000e523  test    rbx, rbx
0x14000e526  jz      loc_14000E620
0x14000e52c  lea     r14, [rax+rax*2]
0x14000e530  shl     r14, 5
0x14000e534  add     r14, [rdx+1A8h]
0x14000e53b  cmp     byte ptr [r14+40h], 0
0x14000e540  jnz     loc_14000E757
0x14000e546  mov     byte ptr [r14+40h], 1
0x14000e54b  mov     r13, rdx
0x14000e54e  mov     rdi, [r15]
0x14000e551  mov     [rbp+4Fh+LowLimit], rdx
0x14000e555  mov     qword ptr [r15], 0
0x14000e55c  test    rdi, rdi
0x14000e55f  jz      loc_14000E5EE
0x14000e565  mov     rbx, [rbp+4Fh+var_B8]
0x14000e569  mov     r13d, 28h ; '('
0x14000e56f  mov     rsi, [rbp+4Fh+arg_0]
0x14000e573  mov     rax, [rdi]
0x14000e576  mov     ecx, [rdi+84h]
0x14000e57c  mov     r8d, [rdi+8Ch]
0x14000e583  mov     r15, [rdi+70h]
0x14000e587  mov     [rbp+4Fh+arg_20], ecx
0x14000e58a  mov     dword ptr [rbp+4Fh+arg_0], r8d
0x14000e58e  test    rax, rax
0x14000e591  jnz     loc_14000E6A4
0x14000e597  mov     r12d, 1
0x14000e59d  mov     dword ptr [rdi+84h], 0
0x14000e5a7  cmp     cs:byte_14011D730, 0
0x14000e5ae  jnz     loc_14000E7D5
0x14000e5b4  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14000e5bb  test    rax, rax
0x14000e5be  jnz     loc_14000EA16
0x14000e5c4  mov     rax, [rbp+4Fh+var_B8]
0x14000e5c8  mov     r9d, r12d
0x14000e5cb  mov     dword ptr [rsp+100h+Context], ecx
0x14000e5cf  mov     rdx, rdi
0x14000e5d2  mov     rcx, rsi
0x14000e5d5  call    _guard_dispatch_icall
0x14000e5da  mov     rbx, [rbp+4Fh+var_B8]
0x14000e5de  mov     rdx, [rbp+4Fh+var_C0]
0x14000e5e2  mov     rdi, r15
0x14000e5e5  test    r15, r15
0x14000e5e8  jnz     short loc_14000E573
0x14000e5ea  mov     r13, [rbp+4Fh+LowLimit]
0x14000e5ee  mov     eax, [rbp+4Fh+var_B0]
0x14000e5f1  lea     r15, [r14+30h]
0x14000e5f5  mov     byte ptr [r14+40h], 0
0x14000e5fa  mov     rdx, [rdx+208h]
0x14000e601  mov     rdi, [r13+1F0h]
0x14000e608  mov     rsi, [r13+1F8h]
0x14000e60f  mov     [rbp+4Fh+var_C0], rdx
0x14000e613  mov     [rbp+4Fh+var_B8], rdi
0x14000e617  mov     [rbp+4Fh+arg_0], rsi
0x14000e61b  jmp     loc_14000E517
0x14000e620  mov     rbx, [r15]
0x14000e623  test    rbx, rbx
0x14000e626  jz      loc_14000E2B0
0x14000e62c  mov     qword ptr [r15], 0
0x14000e633  mov     rax, [rbx]
0x14000e636  mov     r14, [rbx+70h]
0x14000e63a  mov     r12d, [rbx+84h]
0x14000e641  mov     r13d, [rbx+8Ch]
0x14000e648  test    rax, rax
0x14000e64b  jnz     short loc_14000E6AD
0x14000e64d  mov     r15d, 1
0x14000e653  mov     dword ptr [rbx+84h], 0
0x14000e65d  cmp     cs:byte_14011D730, 0
0x14000e664  jnz     loc_14000E98A
0x14000e66a  mov     rcx, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14000e671  test    rcx, rcx
0x14000e674  jnz     loc_14000EA9A
0x14000e67a  mov     r9d, r15d
0x14000e67d  mov     dword ptr [rsp+100h+Context], r12d
0x14000e682  mov     r8d, r13d
0x14000e685  mov     rdx, rbx
0x14000e688  mov     rcx, rsi
0x14000e68b  mov     rax, rdi
0x14000e68e  call    _guard_dispatch_icall
0x14000e693  mov     rdx, [rbp+4Fh+var_C0]
0x14000e697  mov     rbx, r14
0x14000e69a  test    r14, r14
0x14000e69d  jnz     short loc_14000E633
0x14000e69f  jmp     loc_14000E2B0
0x14000e6a4  mov     r12d, [rax+70h]
0x14000e6a8  jmp     loc_14000E59D
0x14000e6ad  mov     r15d, [rax+70h]
0x14000e6b1  jmp     short loc_14000E653
0x14000e6b3  mov     rdx, [rax+38h]
0x14000e6b7  cmp     r13d, [rdx+8Ch]
0x14000e6be  jnz     loc_14000E9C8
0x14000e6c4  cmp     esi, [rdx+84h]
0x14000e6ca  jnz     loc_14000E9C8
0x14000e6d0  test    esi, 0CB00h
0x14000e6d6  jnz     loc_14000E9C8
0x14000e6dc  mov     rax, [rdx]
0x14000e6df  test    rax, rax
0x14000e6e2  jnz     short loc_14000E6EC
0x14000e6e4  mov     rcx, rdx
  ... truncated ...
```
