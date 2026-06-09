# NdisFSendNetBufferLists

- ea: `0x140026410`
- end: `0x140026c40`
- name: `NdisFSendNetBufferLists`
- size: `2096`
- prototype: `void __stdcall(NDIS_HANDLE NdisFilterHandle, PNET_BUFFER_LIST NetBufferList, NDIS_PORT_NUMBER PortNumber, ULONG SendFlags)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a4e30`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x1400260b0`
- `0x140026410`
- `0x140028250`
- `0x1400285b0`
- `0x14002aa30`
- `0x140034bc0`
- `0x140035540`
- `0x140035640`
- `0x14004ad70`
- `0x140088a2c`
- `0x140088ca0`
- `0x1400a4e78`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14002674e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002679f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400268ae`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002674e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002679f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400268ae`
- `ntoskrnl!MmBadPointer` at `0x1400ee7a4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140026ab4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140026ab4`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140026b1d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140026b1d`

## pseudocode

```c
void __stdcall NdisFSendNetBufferLists(
        NDIS_HANDLE NdisFilterHandle,
        PNET_BUFFER_LIST NetBufferList,
        NDIS_PORT_NUMBER PortNumber,
        ULONG SendFlags)
{
  __int64 v4; // rbx
  ULONG v5; // r12d
  NDIS_PORT_NUMBER v6; // r15d
  unsigned int *v8; // r14
  struct NDIS_NBL_TRACKER_HANDLE__ *v9; // rdx
  unsigned __int64 v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rdi
  unsigned int v13; // r8d
  __int64 v14; // r13
  unsigned __int64 v15; // rcx
  PNET_BUFFER_LIST Alignment; // r15
  unsigned __int64 v17; // rdi
  struct NDIS_NBL_TRACKER_HANDLE__ *v18; // r12
  char *SourceHandle; // rdx
  char v20; // r8
  __int64 v21; // rax
  unsigned __int64 v22; // r9
  unsigned __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned __int64 v25; // r13
  unsigned __int64 v26; // rdx
  void **v27; // rdx
  __int64 v28; // rcx
  void (*v29)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int); // rax
  __int64 v30; // r10
  const struct _NDIS_MINIPORT_BLOCK *v31; // rcx
  __int64 v32; // rdi
  __int64 v33; // rcx
  int v34; // r12d
  __int64 v35; // rax
  KIRQL CurrentIrql; // al
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rdi
  __int64 v39; // rdx
  KIRQL v40; // al
  unsigned __int64 v41; // rdx
  struct _NET_BUFFER_LIST *v42; // rcx
  __int64 v43; // rdx
  int v44; // eax
  unsigned __int64 v45; // rax
  int v46; // r9d
  char v47; // al
  __int64 v48; // rax
  bool v49; // zf
  __int64 v50; // rdx
  struct _NDIS_OBJECT_HEADER *v51; // r9
  void *v52; // rax
  void (*v53)(void *, struct _NET_BUFFER_LIST *, unsigned int); // rcx
  __int64 v54; // rdi
  PNET_BUFFER_LIST v55; // rbx
  unsigned int *v56; // r8
  char v57; // r15
  unsigned int v58; // eax
  unsigned int v59; // eax
  _NET_BUFFER_LIST_CONTEXT *i; // rdi
  char v61; // [rsp+40h] [rbp-C0h]
  char v62; // [rsp+44h] [rbp-BCh]
  __int64 v63; // [rsp+48h] [rbp-B8h]
  __int64 v64; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v65; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v66; // [rsp+58h] [rbp-A8h]
  struct _NET_BUFFER_LIST *v67; // [rsp+60h] [rbp-A0h] BYREF
  PNET_BUFFER_LIST v68; // [rsp+68h] [rbp-98h]
  __int128 v69; // [rsp+70h] [rbp-90h] BYREF
  __int128 v70; // [rsp+80h] [rbp-80h]
  __int64 v71; // [rsp+90h] [rbp-70h]
  struct NDIS_NBL_TRACKER_HANDLE__ *v72; // [rsp+98h] [rbp-68h]
  _QWORD v73[54]; // [rsp+A0h] [rbp-60h] BYREF
  struct _NET_BUFFER_LIST *v74; // [rsp+260h] [rbp+160h] BYREF
  NDIS_PORT_NUMBER v75; // [rsp+270h] [rbp+170h]
  ULONG v76; // [rsp+278h] [rbp+178h]

  v76 = SendFlags;
  v75 = PortNumber;
  v74 = (struct _NET_BUFFER_LIST *)NdisFilterHandle;
  v5 = SendFlags;
  v6 = PortNumber;
  v8 = (unsigned int *)NdisFilterHandle;
  if ( !ndisNblContextVerifierMode )
    goto LABEL_2;
  if ( ndisNblContextVerifierMode == 3 )
    goto LABEL_2;
  v43 = *((_QWORD *)NdisFilterHandle + 57);
  if ( !v43 )
    goto LABEL_2;
  if ( *(_BYTE *)v43 == 5 )
  {
    v44 = *(_DWORD *)(v43 + 56) >> 10;
    goto LABEL_78;
  }
  if ( *(_BYTE *)v43 == 17 )
  {
    v44 = *(_DWORD *)(v43 + 3688) >> 12;
LABEL_78:
    LOBYTE(v44) = v44 & 1;
    goto LABEL_79;
  }
  if ( *(_BYTE *)v43 != 18 )
    goto LABEL_2;
  v44 = *(_DWORD *)(v43 + 224) >> 31;
LABEL_79:
  if ( !(_BYTE)v44 )
    goto LABEL_2;
  v4 = 0;
  v67 = 0;
  v68 = (PNET_BUFFER_LIST)&v67;
  memset(&v73[1], 0, 0x178u);
  v73[0] = NetBufferList;
  if ( NetBufferList )
  {
    v54 = *((_QWORD *)v8 + 57);
    v55 = (PNET_BUFFER_LIST)v73;
    do
    {
      if ( NdisAllocateNetBufferListContext(NetBufferList, 8u, 0, 0x6376444Eu) )
      {
        TrackNblContextVerifierFailure(NetBufferList, v54);
        v55->Link.Alignment = NetBufferList->Link.Alignment;
        NetBufferList->Link.Alignment = 0;
        v68->Link.Alignment = (unsigned __int64)NetBufferList;
        v68 = NetBufferList;
        NetBufferList = (PNET_BUFFER_LIST)v55->Link.Alignment;
      }
      else
      {
        v55 = NetBufferList;
        *(_QWORD *)&NetBufferList->Context->ContextData[NetBufferList->Context->Offset] = v54;
        NetBufferList = (PNET_BUFFER_LIST)NetBufferList->Link.Alignment;
      }
    }
    while ( NetBufferList );
    v4 = (__int64)v67;
    NetBufferList = (PNET_BUFFER_LIST)v73[0];
  }
  v67 = 0;
  v68 = (PNET_BUFFER_LIST)&v67;
  if ( !v4 )
    goto LABEL_2;
  if ( byte_140123720 && (v8[210] & 2) != 0 )
    PktMonClientNblDrop((_DWORD)v8 + 784, v4, v8[209], v46);
  v47 = *(_BYTE *)v8;
  if ( *(_BYTE *)v8 == 5 )
  {
    v56 = (unsigned int *)*((_QWORD *)v8 + 57);
  }
  else
  {
    if ( v47 != 17 )
      goto LABEL_87;
    v56 = (unsigned int *)*((_QWORD *)v8 + 321);
  }
  if ( v56 )
  {
    if ( *(_BYTE *)v56 != 5 )
    {
      if ( *(_BYTE *)v56 == 17 )
      {
        v51 = (struct _NDIS_OBJECT_HEADER *)*((_QWORD *)v56 + 324);
        v52 = (void *)*((_QWORD *)v56 + 322);
        v53 = (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int))*((_QWORD *)v56 + 327);
        goto LABEL_102;
      }
LABEL_87:
      NblContextVerifierBugcheckInternalError((ULONG_PTR)v8, v4);
    }
    v51 = (struct _NDIS_OBJECT_HEADER *)*((_QWORD *)v56 + 61);
    v52 = (void *)*((_QWORD *)v56 + 59);
    v53 = (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int))*((_QWORD *)v56 + 58);
  }
  else
  {
    if ( v47 != 17 )
      goto LABEL_87;
    v51 = (struct _NDIS_OBJECT_HEADER *)*((_QWORD *)v8 + 301);
    v56 = v8;
    v52 = (void *)*((_QWORD *)v8 + 299);
    v53 = (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int))*((_QWORD *)v8 + 304);
  }
LABEL_102:
  ndisInvokeNextSendCompleteHandler(
    (struct _NET_BUFFER_LIST *)v4,
    v5 & 1,
    (struct _NDIS_OBJECT_HEADER *)v56,
    v51,
    v52,
    v53);
  if ( !NetBufferList )
    return;
LABEL_2:
  if ( (v8[14] & 0x200) != 0 )
  {
    ndisNblVerifyTxIndication(NetBufferList, v6, v5, (const struct _NDIS_OBJECT_HEADER *)v8);
    v4 = (__int64)NetBufferList;
    if ( NetBufferList )
    {
      v57 = byte_140122DF0;
      do
      {
        v58 = *(_DWORD *)(v4 + 136);
        *(_QWORD *)(v4 + 112) = MmBadPointer;
        *(_DWORD *)(v4 + 132) = -892679478;
        if ( v57 )
        {
          v57 = 0;
          v59 = v58 & 0xFFF0FFFF;
        }
        else
        {
          v57 = 1;
          v59 = v58 | 0xF0000;
        }
        byte_140122DF0 = v57;
        *(_DWORD *)(v4 + 136) = v59;
        for ( i = *(_NET_BUFFER_LIST_CONTEXT **)(v4 + 16); i; i = i->Next )
          memset(i->ContextData, 202, i->Offset);
        v4 = *(_QWORD *)v4;
      }
      while ( v4 );
      v6 = v75;
    }
  }
  if ( *(_DWORD *)ndisNblTrackerMode )
  {
    v9 = (struct NDIS_NBL_TRACKER_HANDLE__ *)*((_QWORD *)v8 + 81);
    v10 = *((_QWORD *)v8 + 56);
    v11 = 0;
    v12 = ndisNblTrackerEpoch;
    v13 = v5 & 1;
    v14 = 0;
    v62 = v5 & 1;
    v72 = v9;
    v64 = 0;
    v63 = 0;
    v61 = 0;
    if ( *(int *)ndisNblTrackerMode >= 3 )
    {
      ndisNblTrackerRecordEventInternal(NetBufferList, v9, 0x90u, (void *)v10, v13);
      LOBYTE(v13) = v5 & 1;
      v11 = 0;
    }
    v15 = v10 & 0xFFFFFFFFFFFFFFFDuLL;
    v66 = v10 & 0xFFFFFFFFFFFFFFFDuLL;
    if ( (v10 & 1) != 0 )
    {
      v4 = (2 * v12) ^ ((2 * v12) ^ v10) & 0xFFFFFFFFFFFFFFFDuLL;
      v15 = *(_QWORD *)((v15 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
      v66 = v15;
    }
    else
    {
      v4 = v10 & 0xFFFFFFFFFFFFFFFDuLL;
    }
    Alignment = NetBufferList;
    if ( NetBufferList )
    {
      while ( 1 )
      {
        v17 = (unsigned __int64)Alignment->NetBufferListInfo[27];
        v18 = v72;
        while ( Alignment->NetBufferListInfo[27] == (void *)v17 )
        {
          if ( v17 )
          {
            if ( (v17 & 4) != 0 )
              goto LABEL_72;
          }
          else if ( !Alignment->SourceHandle )
          {
            v45 = (unsigned __int64)v18 & 0xFFFFFFFFFFFFFFFDuLL;
            if ( ((unsigned __int8)v18 & 1) != 0 )
              v45 = *(_QWORD *)(((unsigned __int64)v18 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
            Alignment->SourceHandle = (void *)v45;
          }
          SourceHandle = (char *)Alignment->SourceHandle;
          if ( SourceHandle )
          {
            v20 = *SourceHandle;
            if ( (unsigned __int8)(*SourceHandle - 17) <= 1u || v20 == 5 )
            {
              if ( SourceHandle != (char *)v15 || Alignment->ParentNetBufferList )
              {
                ++v14;
                v21 = v4;
              }
              else
              {
                ++v11;
                v21 = 24;
                v63 = v11;
                ++v14;
              }
              goto LABEL_18;
            }
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(SourceHandle) = 3;
              WPP_RECORDER_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                (int)SourceHandle,
                27,
                12,
                (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                (char)Alignment,
                v20);
LABEL_128:
              v15 = v66;
              v11 = v63;
            }
          }
          else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(SourceHandle) = 3;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              (int)SourceHandle,
              27,
              11,
              (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
              (char)Alignment);
            goto LABEL_128;
          }
LABEL_72:
          v21 = v4 | 4;
LABEL_18:
          Alignment->NetBufferListInfo[27] = (void *)v21;
          Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
          if ( !Alignment )
            break;
        }
        LOBYTE(v13) = v62;
        if ( (v17 & 1) == 0 )
          goto LABEL_24;
        v22 = v64 - v14;
        v65 = v64 - v14;
        if ( !v65 )
          goto LABEL_24;
        if ( v62 || v61 )
        {
          v23 = (v17 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v17 >> 1) & 1) + 3);
          if ( !v62 )
            goto LABEL_47;
          goto LABEL_23;
        }
        v61 = 1;
        CurrentIrql = KeGetCurrentIrql();
        v22 = v65;
        v37 = v17;
        v38 = v17 & 0xFFFFFFFFFFFFFFF8uLL;
        v39 = 16 * (((v37 >> 1) & 1) + 3);
        if ( CurrentIrql == 2 )
        {
          LOBYTE(v13) = 1;
          v23 = v38 + v39;
          v62 = 1;
LABEL_23:
          v24 = KeGetPcr()->Prcb.Number << 12;
          *(_QWORD *)(v24 + *(_QWORD *)v23) += v22;
          goto LABEL_24;
        }
        LOBYTE(v13) = 0;
        v62 = 0;
        v23 = v38 + v39;
LABEL_47:
        _InterlockedAdd64((volatile signed __int64 *)(v23 + 8), v22);
LABEL_24:
        v15 = v66;
        v11 = v63;
        v64 = v14;
        if ( !Alignment )
        {
          v8 = (unsigned int *)v74;
          v5 = v76;
          break;
        }
      }
    }
    if ( (v4 & 1) == 0 )
      goto LABEL_31;
    v25 = v14 - v63;
    if ( !v25 )
      goto LABEL_31;
    if ( (_BYTE)v13 || v61 )
    {
      v26 = v4;
      v4 &= 0xFFFFFFFFFFFFFFF8uLL;
      v27 = (void **)(v4 + 16 * (((v26 >> 1) & 1) + 3));
      if ( !(_BYTE)v13 )
      {
LABEL_50:
        _InterlockedAdd64((volatile signed __int64 *)v27 + 1, v25);
        goto LABEL_31;
      }
    }
    else
    {
      v40 = KeGetCurrentIrql();
      v41 = v4;
      v4 &= 0xFFFFFFFFFFFFFFF8uLL;
      v27 = (void **)(v4 + 16 * (((v41 >> 1) & 1) + 3));
      if ( v40 != 2 )
        goto LABEL_50;
    }
    v28 = KeGetPcr()->Prcb.Number << 12;
    *(_QWORD *)((char *)*v27 + v28) += v25;
LABEL_31:
    v6 = v75;
  }
  if ( byte_140123720 )
  {
    v48 = *((_QWORD *)v8 + 109);
    if ( v48 )
    {
      if ( (*(_DWORD *)(v48 + 56) & 1) != 0 )
      {
        v49 = (NetBufferList->NblFlags & 0x8000) == 0;
        v69 = 0;
        LODWORD(v71) = 0;
        v70 = 0;
        if ( v49 )
        {
          v4 = v8[220];
          if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
          {
            v50 = *((_QWORD *)v8 + 108);
            LOWORD(v69) = 40;
            *((_QWORD *)&v69 + 1) = NetBufferList;
            LODWORD(v70) = 1;
            *(_QWORD *)((char *)&v70 + 4) = (unsigned int)v4 | 0x200000000LL;
            v71 = 0;
            (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1) + 40LL))(
              xmmword_140123740,
              v50,
              &v69,
              0);
            ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
          }
        }
      }
    }
  }
  v29 = (void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int))*((_QWORD *)v8 + 78);
  if ( v29 == ndisFilterSendNetBufferLists )
  {
    v30 = *((_QWORD *)v8 + 57);
    v74 = NetBufferList;
    if ( *(_BYTE *)v30 == 5 )
    {
      v31 = (const struct _NDIS_MINIPORT_BLOCK *)*((_QWORD *)v8 + 4);
      if ( (*(_DWORD *)(v30 + 56) & 0x8000) != 0
        && !*(_DWORD *)(v30 + 336)
        && (v31->LoopbackOpens && (v31->NumOpens > 1u || v31->ReceiveFilters)
         || (v5 & 2) != 0
         || MINIPORT_TEST_FLAG(v31, 0x4000u)) )
      {
        ndisFLoopbackNetBufferLists((struct _NDIS_FILTER_BLOCK *)v30, NetBufferList, v6, v5, &v74);
        NetBufferList = v74;
      }
    }
    if ( NetBufferList )
    {
      LODWORD(v4) = KeGetPcr()->Prcb.Number;
      v32 = *((_QWORD *)v8 + 53);
      if ( ((v5 & 1) != 0 || KeGetCurrentIrql() == 2) && (v33 = 96 * v4, *(_BYTE *)(96 * v4 + v32 + 16)) )
      {
        v34 = v5 | 1;
        v35 = v33 + v32;
        if ( *(_QWORD *)(v33 + v32) )
        {
          v42 = *(struct _NET_BUFFER_LIST **)(v35 + 8);
          if ( v6 == v42->Status && v34 == v42->ChildRefCount && (v34 & 0x34) == 0 )
          {
            NdisLastNblInNblChain(v42)->Link.Alignment = (unsigned __int64)NetBufferList;
            return;
          }
          v42->Scratch = NetBufferList;
        }
        else
        {
          *(_QWORD *)(v33 + v32) = NetBufferList;
        }
        *(_QWORD *)(v35 + 8) = NetBufferList;
        NetBufferList->Scratch = 0;
        NetBufferList->ChildRefCount = v34;
        NetBufferList->Status = v6;
      }
      else
      {
        ndisInvokeNextSendHandler(
          NetBufferList,
          v6,
          v5,
          *((struct _NDIS_OBJECT_HEADER **)v8 + 57),
          *((void **)v8 + 55),
          *((void (**)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int))v8 + 54));
      }
    }
  }
  else
  {
    ((void (__fastcall *)(unsigned int *, PNET_BUFFER_LIST, _QWORD, _QWORD))v29)(v8, NetBufferList, v6, v5);
  }
}

```

## disassembly

```asm
0x140026410  mov     [rsp-8+arg_18], r9d
0x140026415  mov     [rsp-8+arg_10], r8d
0x14002641a  mov     [rsp-8+arg_0], rcx
0x14002641f  push    rbp
0x140026420  push    rbx
0x140026421  push    rsi
0x140026422  push    rdi
0x140026423  push    r12
0x140026425  push    r14
0x140026427  push    r15
0x140026429  lea     rbp, [rsp-120h]
0x140026431  sub     rsp, 220h
0x140026438  mov     eax, cs:?ndisNblContextVerifierMode@@3W4NDIS_NBL_CONTEXT_VERIFIER_MODE@@A; NDIS_NBL_CONTEXT_VERIFIER_MODE ndisNblContextVerifierMode
0x14002643e  mov     r12d, r9d
0x140026441  mov     r15d, r8d
0x140026444  mov     rsi, rdx
0x140026447  mov     r14, rcx
0x14002644a  test    eax, eax
0x14002644c  jnz     loc_140026842
0x140026452  mov     eax, [r14+38h]
0x140026456  bt      eax, 9
0x14002645a  jnb     short loc_140026479
0x14002645c  mov     r9, r14; struct _NDIS_OBJECT_HEADER *
0x14002645f  mov     r8d, r12d; unsigned int
0x140026462  mov     edx, r15d; unsigned int
0x140026465  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x140026468  call    ?ndisNblVerifyTxIndication@@YAXPEBU_NET_BUFFER_LIST@@KKPEBU_NDIS_OBJECT_HEADER@@@Z; ndisNblVerifyTxIndication(_NET_BUFFER_LIST const *,ulong,ulong,_NDIS_OBJECT_HEADER const *)
0x14002646d  mov     rbx, rsi
0x140026470  test    rsi, rsi
0x140026473  jnz     loc_140026BCF
0x140026479  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14002647f  test    eax, eax
0x140026481  jz      loc_140026677
0x140026487  mov     rdx, [r14+288h]; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14002648e  xor     ecx, ecx
0x140026490  mov     rbx, [r14+1C0h]
0x140026497  xor     r9d, r9d
0x14002649a  mov     edi, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x1400264a0  mov     r8d, r12d
0x1400264a3  and     r8d, 1
0x1400264a7  mov     [rsp+250h+arg_8], r13
0x1400264af  xor     r13d, r13d
0x1400264b2  mov     [rsp+250h+var_20C], r8d
0x1400264b7  mov     [rbp+150h+var_1B8], rdx
0x1400264bb  mov     [rsp+250h+var_200], rcx
0x1400264c0  mov     [rsp+250h+var_208], r9
0x1400264c5  mov     [rsp+250h+var_210], cl
0x1400264c9  cmp     eax, 3
0x1400264cc  jl      short loc_1400264EC
0x1400264ce  mov     dword ptr [rsp+250h+var_230], r8d; unsigned int
0x1400264d3  mov     r9, rbx; void *
0x1400264d6  mov     r8d, 90h; unsigned int
0x1400264dc  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x1400264df  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x1400264e4  mov     r8d, [rsp+250h+var_20C]
0x1400264e9  mov     r9d, r13d
0x1400264ec  mov     rcx, rbx
0x1400264ef  and     rcx, 0FFFFFFFFFFFFFFFDh
0x1400264f3  mov     [rsp+250h+var_1F8], rcx
0x1400264f8  test    cl, 1
0x1400264fb  jz      loc_14002683A
0x140026501  mov     rax, rdi
0x140026504  add     rax, rax
0x140026507  xor     rbx, rax
0x14002650a  and     rbx, 0FFFFFFFFFFFFFFFDh
0x14002650e  xor     rbx, rax
0x140026511  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140026515  mov     rcx, [rcx+18h]
0x140026519  mov     [rsp+250h+var_1F8], rcx
0x14002651e  mov     r15, rsi
0x140026521  test    rsi, rsi
0x140026524  jz      loc_14002661E
0x14002652a  lea     r10, WPP_RECORDER_INITIALIZED
0x140026531  lea     r14, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x140026538  mov     rdi, [r15+168h]
0x14002653f  mov     r12, [rbp+150h+var_1B8]
0x140026543  cmp     [r15+168h], rdi
0x14002654a  jnz     short loc_14002659A
0x14002654c  test    rdi, rdi
0x14002654f  jz      loc_140026887
0x140026555  test    dil, 4
0x140026559  jnz     loc_140026901
0x14002655f  mov     rdx, [r15+78h]
0x140026563  test    rdx, rdx
0x140026566  jz      loc_1400268F4
0x14002656c  movzx   r8d, byte ptr [rdx]
0x140026570  lea     eax, [r8-11h]
0x140026574  cmp     al, 1
0x140026576  ja      loc_140026A20
0x14002657c  cmp     rdx, rcx
0x14002657f  jz      loc_1400267E5
0x140026585  inc     r13
0x140026588  mov     rax, rbx
0x14002658b  mov     [r15+168h], rax
0x140026592  mov     r15, [r15]
0x140026595  test    r15, r15
0x140026598  jnz     short loc_140026543
0x14002659a  movzx   r12d, [rsp+250h+var_210]
0x1400265a0  mov     r8d, [rsp+250h+var_20C]
0x1400265a5  test    dil, 1
0x1400265a9  jz      short loc_1400265F8
0x1400265ab  mov     r9, [rsp+250h+var_200]
0x1400265b0  sub     r9, r13
0x1400265b3  mov     [rsp+250h+var_200], r9
0x1400265b8  jz      short loc_1400265F8
0x1400265ba  test    r8b, r8b
0x1400265bd  jz      loc_140026740
0x1400265c3  mov     rdx, rdi
0x1400265c6  and     rdi, 0FFFFFFFFFFFFFFF8h
0x1400265ca  shr     rdx, 1
0x1400265cd  and     edx, 1
0x1400265d0  add     rdx, 3
0x1400265d4  shl     rdx, 4
0x1400265d8  add     rdx, rdi
0x1400265db  test    r8b, r8b
0x1400265de  jz      loc_14002678A
0x1400265e4  mov     eax, gs:1A4h
0x1400265ec  shl     eax, 0Ch
0x1400265ef  mov     ecx, eax
0x1400265f1  mov     rax, [rdx]
0x1400265f4  add     [rcx+rax], r9
0x1400265f8  mov     rcx, [rsp+250h+var_1F8]
0x1400265fd  mov     r9, [rsp+250h+var_208]
0x140026602  mov     [rsp+250h+var_200], r13
0x140026607  test    r15, r15
0x14002660a  jnz     loc_140026538
0x140026610  mov     r14, [rbp+150h+arg_0]
0x140026617  mov     r12d, [rbp+150h+arg_18]
0x14002661e  test    bl, 1
0x140026621  jz      short loc_140026668
0x140026623  sub     r13, [rsp+250h+var_208]
0x140026628  jz      short loc_140026668
0x14002662a  test    r8b, r8b
0x14002662d  jz      loc_140026794
0x140026633  mov     rdx, rbx
0x140026636  and     rbx, 0FFFFFFFFFFFFFFF8h
0x14002663a  shr     rdx, 1
0x14002663d  and     edx, 1
0x140026640  add     rdx, 3
0x140026644  shl     rdx, 4
0x140026648  add     rdx, rbx
0x14002664b  test    r8b, r8b
0x14002664e  jz      loc_1400267CB
0x140026654  mov     eax, gs:1A4h
0x14002665c  shl     eax, 0Ch
0x14002665f  mov     ecx, eax
0x140026661  mov     rax, [rdx]
0x140026664  add     [rcx+rax], r13
0x140026668  mov     r15d, [rbp+150h+arg_10]
0x14002666f  mov     r13, [rsp+250h+arg_8]
0x140026677  cmp     cs:byte_140123720, 0
0x14002667e  jnz     loc_140026A6A
0x140026684  mov     rax, [r14+270h]
0x14002668b  lea     rcx, ?ndisFilterSendNetBufferLists@@YAXPEAXPEAU_NET_BUFFER_LIST@@KK@Z; ndisFilterSendNetBufferLists(void *,_NET_BUFFER_LIST *,ulong,ulong)
0x140026692  cmp     rax, rcx
0x140026695  jnz     loc_140026C2A
0x14002669b  mov     r10, [r14+1C8h]
0x1400266a2  mov     [rbp+150h+arg_0], rsi
0x1400266a9  cmp     byte ptr [r10], 5
0x1400266ad  jnz     short loc_1400266CB
0x1400266af  mov     eax, [r10+38h]
0x1400266b3  mov     rcx, [r14+20h]; struct _NDIS_MINIPORT_BLOCK *
0x1400266b7  bt      eax, 0Fh
0x1400266bb  jnb     short loc_1400266CB
0x1400266bd  cmp     dword ptr [r10+150h], 0
0x1400266c5  jz      loc_14002690D
0x1400266cb  test    rsi, rsi
0x1400266ce  jz      short loc_14002672D
0x1400266d0  mov     ebx, gs:1A4h
0x1400266d8  mov     rdi, [r14+1A8h]
0x1400266df  test    r12b, 1
0x1400266e3  jz      loc_1400268AE
0x1400266e9  lea     rcx, [rbx+rbx*2]
0x1400266ed  shl     rcx, 5
0x1400266f1  cmp     byte ptr [rcx+rdi+10h], 0
0x1400266f6  jz      loc_1400268C2
0x1400266fc  or      r12d, 1
0x140026700  lea     rax, [rcx+rdi]
0x140026704  cmp     qword ptr [rcx+rdi], 0
0x140026709  jnz     loc_140026805
0x14002670f  mov     [rcx+rdi], rsi
0x140026713  mov     [rax+8], rsi
0x140026717  mov     qword ptr [rsi+70h], 0
0x14002671f  mov     [rsi+84h], r12d
0x140026726  mov     [rsi+8Ch], r15d
0x14002672d  add     rsp, 220h
0x140026734  pop     r15
0x140026736  pop     r14
0x140026738  pop     r12
0x14002673a  pop     rdi
0x14002673b  pop     rsi
0x14002673c  pop     rbx
0x14002673d  pop     rbp
0x14002673e  retn
0x140026740  test    r12b, r12b
0x140026743  jnz     loc_1400265C3
0x140026749  mov     [rsp+250h+var_210], 1
0x14002674e  call    cs:__imp_KeGetCurrentIrql
0x140026755  nop     dword ptr [rax+rax+00h]
0x14002675a  mov     r9, [rsp+250h+var_200]
0x14002675f  lea     r10, WPP_RECORDER_INITIALIZED
0x140026766  mov     rdx, rdi
0x140026769  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14002676d  shr     rdx, 1
0x140026770  and     edx, 1
0x140026773  add     rdx, 3
0x140026777  shl     rdx, 4
0x14002677b  cmp     al, 2
0x14002677d  jz      short loc_1400267D5
0x14002677f  xor     r8b, r8b
0x140026782  mov     [rsp+250h+var_20C], r8d
0x140026787  add     rdx, rdi
0x14002678a  lock add [rdx+8], r9
0x14002678f  jmp     loc_1400265F8
0x140026794  cmp     [rsp+250h+var_210], 0
0x140026799  jnz     loc_140026633
0x14002679f  call    cs:__imp_KeGetCurrentIrql
0x1400267a6  nop     dword ptr [rax+rax+00h]
0x1400267ab  mov     rdx, rbx
0x1400267ae  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1400267b2  shr     rdx, 1
0x1400267b5  and     edx, 1
0x1400267b8  add     rdx, 3
0x1400267bc  shl     rdx, 4
0x1400267c0  add     rdx, rbx
0x1400267c3  cmp     al, 2
0x1400267c5  jz      loc_140026654
0x1400267cb  lock add [rdx+8], r13
0x1400267d0  jmp     loc_140026668
0x1400267d5  mov     r8b, 1
0x1400267d8  add     rdx, rdi
0x1400267db  mov     [rsp+250h+var_20C], r8d
0x1400267e0  jmp     loc_1400265E4
0x1400267e5  cmp     qword ptr [r15+18h], 0
0x1400267ea  jnz     loc_140026585
0x1400267f0  inc     r9
0x1400267f3  mov     eax, 18h
0x1400267f8  mov     [rsp+250h+var_208], r9
0x1400267fd  inc     r13
0x140026800  jmp     loc_14002658B
0x140026805  mov     rcx, [rax+8]; struct _NET_BUFFER_LIST *
0x140026809  cmp     r15d, [rcx+8Ch]
0x140026810  jnz     loc_140026B2E
0x140026816  cmp     r12d, [rcx+84h]
0x14002681d  jnz     loc_140026B2E
0x140026823  test    r12b, 34h
0x140026827  jnz     loc_140026B2E
0x14002682d  call    ?NdisLastNblInNblChain@@YAPEAU_NET_BUFFER_LIST@@PEAU1@@Z; NdisLastNblInNblChain(_NET_BUFFER_LIST *)
0x140026832  mov     [rax], rsi
0x140026835  jmp     loc_14002672D
0x14002683a  mov     rbx, rcx
0x14002683d  jmp     loc_14002651E
0x140026842  cmp     eax, 3
0x140026845  jz      loc_140026452
0x14002684b  mov     rdx, [rcx+1C8h]
0x140026852  test    rdx, rdx
0x140026855  jz      loc_140026452
0x14002685b  movzx   ecx, byte ptr [rdx]
0x14002685e  sub     ecx, 5
0x140026861  jz      loc_140026A15
0x140026867  sub     ecx, 0Ch
0x14002686a  jz      loc_140026958
0x140026870  cmp     ecx, 1
0x140026873  jnz     loc_140026452
0x140026879  mov     eax, [rdx+0E0h]
0x14002687f  shr     eax, 1Fh
0x140026882  jmp     loc_140026963
0x140026887  cmp     qword ptr [r15+78h], 0
0x14002688c  jnz     loc_14002655F
0x140026892  mov     rax, r12
0x140026895  and     rax, 0FFFFFFFFFFFFFFFDh
0x140026899  test    al, 1
0x14002689b  jz      short loc_1400268A5
0x14002689d  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400268a1  mov     rax, [rax+18h]
0x1400268a5  mov     [r15+78h], rax
0x1400268a9  jmp     loc_14002655F
0x1400268ae  call    cs:__imp_KeGetCurrentIrql
0x1400268b5  nop     dword ptr [rax+rax+00h]
0x1400268ba  cmp     al, 2
0x1400268bc  jz      loc_1400266E9
0x1400268c2  mov     rax, [r14+1B0h]
0x1400268c9  mov     r8d, r12d; unsigned int
0x1400268cc  mov     r9, [r14+1C8h]; struct _NDIS_OBJECT_HEADER *
0x1400268d3  mov     edx, r15d; unsigned int
0x1400268d6  mov     [rsp+250h+var_228], rax; void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)
0x1400268db  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x1400268de  mov     rax, [r14+1B8h]
0x1400268e5  mov     [rsp+250h+var_230], rax; void *
0x1400268ea  call    ?ndisInvokeNextSendHandler@@YAXPEAU_NET_BUFFER_LIST@@KKPEAU_NDIS_OBJECT_HEADER@@PEAXP6AX20KK@Z@Z; ndisInvokeNextSendHandler(_NET_BUFFER_LIST *,ulong,ulong,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong,ulong))
0x1400268ef  jmp     loc_14002672D
0x1400268f4  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x1400268fb  jnz     loc_140026BDC
0x140026901  mov     rax, rbx
0x140026904  or      rax, 4
0x140026908  jmp     loc_14002658B
0x14002690d  cmp     byte ptr [rcx+5Bh], 0
0x140026911  ja      loc_140026C0A
0x140026917  test    r12b, 2
0x14002691b  jnz     short loc_14002692F
  ... truncated ...
```
