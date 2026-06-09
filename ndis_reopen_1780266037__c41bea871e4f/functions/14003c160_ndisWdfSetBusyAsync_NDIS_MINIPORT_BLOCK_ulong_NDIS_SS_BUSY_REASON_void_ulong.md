# ndisWdfSetBusyAsync(_NDIS_MINIPORT_BLOCK *,ulong,_NDIS_SS_BUSY_REASON,void *,ulong)

- ea: `0x14003c160`
- end: `0x14003cab4`
- name: `?ndisWdfSetBusyAsync@@YAEPEAU_NDIS_MINIPORT_BLOCK@@KW4_NDIS_SS_BUSY_REASON@@PEAXK@Z`
- size: `2388`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14003a140`
- `0x14003a3e0`
- `0x14003c010`
- `0x14007abf0`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x1400260b0`
- `0x140038090`
- `0x14003a0e0`
- `0x14003c160`
- `0x14003cac0`
- `0x14003cec0`
- `0x14003d670`
- `0x140047500`
- `0x14008c0f0`
- `0x1400c72d0`
- `0x1400c738c`
- `0x1400c74d4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14003c493`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003c74a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003c493`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003c74a`
- `ntoskrnl!KeReadStateEvent` at `0x14003c1f8`
- `ntoskrnl!KeReadStateEvent` at `0x14003c1f8`
- `ntoskrnl!KeClearEvent` at `0x14003c588`
- `ntoskrnl!KeClearEvent` at `0x14003c588`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c277`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c5f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c9c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ef4f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c277`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c5f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c9c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ef4f6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c1ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c1ae`

## pseudocode

```c
bool __fastcall ndisWdfSetBusyAsync(__int64 a1, int a2, unsigned int a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rsi
  __int64 v6; // r15
  unsigned int v8; // r14d
  unsigned __int64 (*v10)(void *, struct _NET_BUFFER_LIST *); // rdx
  KIRQL v11; // di
  char v12; // bl
  __int64 v13; // rax
  char *v15; // rdx
  unsigned __int64 v16; // rdi
  __int64 v17; // rbx
  char *v18; // r10
  unsigned __int64 v19; // r12
  unsigned __int64 v20; // rbx
  _QWORD *v21; // r15
  unsigned __int64 v22; // rdi
  char *v23; // rcx
  char v24; // r8
  __int64 v25; // rax
  __int64 v26; // r10
  _QWORD *v27; // r8
  __int64 v28; // rcx
  _QWORD *v29; // rdx
  __int64 v30; // rcx
  char *v31; // rax
  struct _NET_BUFFER_LIST *v32; // r12
  unsigned int v33; // ebx
  char v34; // di
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // r8d
  __int64 v38; // rax
  __int64 v39; // rax
  _QWORD *v40; // rdx
  char **v41; // rbx
  struct _NET_BUFFER_LIST *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  KIRQL v45; // [rsp+42h] [rbp-3Eh]
  char *v46; // [rsp+48h] [rbp-38h]
  signed __int64 v47; // [rsp+48h] [rbp-38h]
  _QWORD v48[2]; // [rsp+50h] [rbp-30h] BYREF
  char *v49; // [rsp+60h] [rbp-20h] BYREF
  char **v50; // [rsp+68h] [rbp-18h]
  struct _LIST_ENTRY v51; // [rsp+70h] [rbp-10h] BYREF

  v5 = *(_QWORD *)(a1 + 4448);
  v51.Blink = &v51;
  v6 = a1;
  v51.Flink = &v51;
  v8 = a3;
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5);
  v45 = v11;
  if ( (*(_DWORD *)(v5 + 512)
     || *(_DWORD *)(v5 + 516)
     || *(_DWORD *)(v5 + 528)
     || *(_DWORD *)(v5 + 532)
     || *(_DWORD *)(v5 + 520)
     || *(_DWORD *)(v5 + 524)
     || *(_DWORD *)(v5 + 576)
     || *(_DWORD *)(v5 + 508))
    && KeReadStateEvent((PRKEVENT)(v5 + 272)) )
  {
    v12 = 1;
    if ( v8 == 52 )
    {
      v13 = *(_QWORD *)(v5 + 600);
      *(_DWORD *)(v5 + 144) = 0;
      *(_BYTE *)(v13 + 20) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 44LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 68LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 92LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 116LL) = 0;
      *(_DWORD *)(v5 + 520) += a2;
    }
    else if ( v8 == 54 )
    {
      v38 = *(_QWORD *)(v5 + 600);
      *(_DWORD *)(v5 + 144) = 0;
      *(_BYTE *)(v38 + 20) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 44LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 68LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 92LL) = 0;
      *(_BYTE *)(*(_QWORD *)(v5 + 600) + 116LL) = 0;
      *(_DWORD *)(v5 + 576) += a2;
    }
    else
    {
      switch ( v8 )
      {
        case '1':
          *(_DWORD *)(v5 + 512) |= 0x10u;
          goto LABEL_9;
        case '2':
          v44 = *(_QWORD *)(v5 + 600);
          *(_DWORD *)(v5 + 144) = 0;
          *(_BYTE *)(v44 + 20) = 0;
          *(_BYTE *)(*(_QWORD *)(v5 + 600) + 44LL) = 0;
          *(_BYTE *)(*(_QWORD *)(v5 + 600) + 68LL) = 0;
          *(_BYTE *)(*(_QWORD *)(v5 + 600) + 92LL) = 0;
          *(_BYTE *)(*(_QWORD *)(v5 + 600) + 116LL) = 0;
          *(_DWORD *)(v5 + 528) += a2;
          goto LABEL_9;
        case '3':
          if ( *(_DWORD *)(v5 + 528) )
          {
            *(_DWORD *)(v5 + 532) += a2;
            goto LABEL_9;
          }
          break;
        default:
          if ( v8 == 53 && *(_DWORD *)(v5 + 520) )
          {
            *(_DWORD *)(v5 + 524) += a2;
            goto LABEL_9;
          }
          break;
      }
      v12 = 0;
    }
LABEL_9:
    ndisSelectiveSuspendSetResumeBusyReason(v5, 0, v8, 0);
    KeReleaseSpinLock((PKSPIN_LOCK)v5, v11);
    return v12;
  }
  if ( v8 == 54 )
  {
LABEL_46:
    v32 = 0;
    v33 = 0;
    v34 = 0;
    if ( !*(_DWORD *)(v5 + 512)
      && !*(_DWORD *)(v5 + 516)
      && !*(_DWORD *)(v5 + 528)
      && !*(_DWORD *)(v5 + 532)
      && !*(_DWORD *)(v5 + 520)
      && !*(_DWORD *)(v5 + 524)
      && !*(_DWORD *)(v5 + 576)
      && !*(_DWORD *)(v5 + 508) )
    {
      v34 = 1;
      KeClearEvent((PRKEVENT)(v5 + 272));
      v33 = v8;
    }
    switch ( v8 )
    {
      case '4':
        v35 = *(_QWORD *)(v5 + 600);
        *(_DWORD *)(v5 + 144) = 0;
        *(_BYTE *)(v35 + 20) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 44LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 68LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 92LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 116LL) = 0;
        *(_DWORD *)(v5 + 520) += a2;
        break;
      case '6':
        v39 = *(_QWORD *)(v5 + 600);
        *(_DWORD *)(v5 + 144) = 0;
        *(_BYTE *)(v39 + 20) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 44LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 68LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 92LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 116LL) = 0;
        *(_DWORD *)(v5 + 576) += a2;
        break;
      case '1':
        *(_DWORD *)(v5 + 512) |= 0x10u;
        break;
      case '2':
        v43 = *(_QWORD *)(v5 + 600);
        *(_DWORD *)(v5 + 144) = 0;
        *(_BYTE *)(v43 + 20) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 44LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 68LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 92LL) = 0;
        *(_BYTE *)(*(_QWORD *)(v5 + 600) + 116LL) = 0;
        *(_DWORD *)(v5 + 528) += a2;
        break;
      case '3':
        if ( *(_DWORD *)(v5 + 528) )
          *(_DWORD *)(v5 + 532) += a2;
        break;
      default:
        if ( v8 == 53 && *(_DWORD *)(v5 + 520) )
          *(_DWORD *)(v5 + 524) += a2;
        break;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v5, v45);
    if ( v34 )
      ndisWdfAcquirePowerReferenceHelper((struct _NDIS_MINIPORT_BLOCK *)v6, 0, 1u);
LABEL_59:
    if ( v32 )
    {
      if ( byte_140123720 && (*(_DWORD *)(v6 + 5872) & 2) != 0 )
        PktMonClientNblDropNdis(v6 + 5816, (_DWORD)v32, v37, 2, -1071448017, -536866804);
      NdisSetStatusInNblChain(v32, -1071448052);
      ndisMSendNetBufferListsCompleteInternal((struct _NDIS_MINIPORT_BLOCK *)v6, v32, 0, 0);
    }
    goto LABEL_60;
  }
  v51.Blink = &v51;
  v51.Flink = &v51;
  if ( v8 != 49 )
  {
    if ( v8 == 51 )
    {
      ndisDequeueDirectOidsByRequestId((struct _NDIS_SELECTIVE_SUSPEND *)v5, (void *)a4, &v51);
    }
    else
    {
      if ( v8 != 53 )
      {
        if ( v8 == 52 )
        {
          v15 = 0;
          if ( *(_DWORD *)ndisNblTrackerMode )
          {
            v16 = *(_QWORD *)(v5 + 608);
            v17 = ndisNblTrackerEpoch;
            v18 = 0;
            v46 = 0;
            v48[0] = 0;
            v49 = 0;
            if ( *(int *)ndisNblTrackerMode >= 3 )
            {
              ndisNblTrackerRecordEventInternal((struct _NET_BUFFER_LIST *)a4, 0, 1u, (void *)v16, 1u);
              v15 = 0;
              v18 = 0;
            }
            v19 = v16 & 0xFFFFFFFFFFFFFFFDuLL;
            if ( (v16 & 1) != 0 )
            {
              v20 = (2 * v17) ^ (v16 ^ (2 * v17)) & 0xFFFFFFFFFFFFFFFDuLL;
              v19 = *(_QWORD *)((v16 & 0xFFFFFFFFFFFFFFF8uLL) + 24);
            }
            else
            {
              v20 = v16 & 0xFFFFFFFFFFFFFFFDuLL;
            }
            if ( a4 )
            {
              v21 = (_QWORD *)a4;
              while ( 1 )
              {
                v22 = v21[45];
                while ( v21[45] == v22 )
                {
                  if ( v22 )
                  {
                    if ( (v22 & 4) != 0 )
                      goto LABEL_87;
                  }
                  else if ( !v21[15] )
                  {
                    v21[15] = 0;
                  }
                  v23 = (char *)v21[15];
                  if ( v23 )
                  {
                    v24 = *v23;
                    if ( (unsigned __int8)(*v23 - 17) <= 1u || v24 == 5 )
                    {
                      if ( v23 != (char *)v19 || v21[3] )
                      {
                        ++v15;
                        v25 = v20;
                        v46 = v15;
                      }
                      else
                      {
                        ++v18;
                        v25 = 24;
                        ++v15;
                        v49 = v18;
                        v46 = v15;
                      }
                      goto LABEL_33;
                    }
                    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v15) = 3;
                      WPP_RECORDER_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 8),
                        (int)v15,
                        27,
                        12,
                        (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                        (char)v21,
                        v24);
LABEL_114:
                      v15 = v46;
                      v18 = v49;
                    }
                  }
                  else if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v15) = 3;
                    WPP_RECORDER_SF_q(
                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                      (int)v15,
                      27,
                      11,
                      (struct _GUID *)&WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids,
                      (char)v21);
                    goto LABEL_114;
                  }
LABEL_87:
                  v25 = v20 | 4;
LABEL_33:
                  v21[45] = v25;
                  v21 = (_QWORD *)*v21;
                  if ( !v21 )
                    break;
                }
                if ( (v22 & 1) != 0 )
                {
                  v26 = v48[0] - (_QWORD)v15;
                  v48[0] -= v15;
                  if ( v48[0] )
                  {
                    v27 = (_QWORD *)((v22 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v22 >> 1) & 1) + 3));
                    v28 = KeGetPcr()->Prcb.Number << 12;
                    *(_QWORD *)(v28 + *v27) += v26;
                  }
                }
                v18 = v49;
                v48[0] = v15;
                if ( !v21 )
                {
                  v8 = a3;
                  v6 = a1;
                  break;
                }
              }
            }
            if ( (v20 & 1) != 0 )
            {
              v47 = v15 - v49;
              if ( v15 != v49 )
              {
                v29 = (_QWORD *)((v20 & 0xFFFFFFFFFFFFFFF8uLL) + 16 * (((v20 >> 1) & 1) + 3));
                v30 = KeGetPcr()->Prcb.Number << 12;
                *(_QWORD *)(v30 + *v29) += v47;
              }
            }
            v15 = 0;
          }
          v31 = (char *)a4;
          if ( a4 )
          {
            do
            {
              *((_QWORD *)v31 + 14) = a5;
              v15 = v31;
              v31 = *(char **)v31;
            }
            while ( v31 );
          }
          **(_QWORD **)(v5 + 552) = a4;
          *(_QWORD *)(v5 + 552) = v15;
          *(_DWORD *)(v5 + 632) = 0;
        }
        else if ( v8 == 50 )
        {
          v40 = *(_QWORD **)(v5 + 592);
          if ( *v40 != v5 + 584 )
            __fastfail(3u);
          *(_QWORD *)(a4 + 72) = v5 + 584;
          *(_QWORD *)(a4 + 80) = v40;
          *v40 = a4 + 72;
          *(_QWORD *)(v5 + 592) = a4 + 72;
          *(_DWORD *)(v5 + 632) = *(_DWORD *)(a4 + 32);
        }
        goto LABEL_46;
      }
      v41 = (char **)(v5 + 544);
      v42 = *(struct _NET_BUFFER_LIST **)(v5 + 544);
      if ( v42 )
      {
        v49 = 0;
        v50 = &v49;
        v48[0] = 0;
        v48[1] = v48;
        NdisClassifyNblChain2(v42, v10, (void *)a4, (struct NBL_QUEUE_t *)&v49, (struct NBL_QUEUE_t *)v48);
        if ( *v41 != v49 )
        {
          if ( v49 )
          {
            *v41 = v49;
            *(_QWORD *)(v5 + 552) = v50;
            v50 = &v49;
            v49 = 0;
          }
          else
          {
            *v41 = 0;
            *(_QWORD *)(v5 + 552) = v5 + 544;
          }
        }
        v32 = (struct _NET_BUFFER_LIST *)v48[0];
        v33 = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)v5, v11);
        goto LABEL_59;
      }
    }
  }
  v33 = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)v5, v11);
LABEL_60:
  if ( v51.Flink != &v51 )
    ndisCancelDequeuedDirectOidRequests((struct _NDIS_MINIPORT_BLOCK *)v6, &v51);
  if ( v33 && (byte_140121001 & 8) != 0 )
    McTemplateK0qq_EtwWriteTransfer(v36, ">(", v6 + 4008, (*(_QWORD *)(v6 + 4024) >> 24) & 0xFFFFFFLL, v33);
  return v8 == 54;
}

```

## disassembly

```asm
0x14003c160  mov     [rsp-38h+arg_18], rbx
0x14003c165  mov     [rsp-38h+arg_10], r8d
0x14003c16a  mov     [rsp-38h+arg_8], edx
0x14003c16e  mov     [rsp-38h+arg_0], rcx
0x14003c173  push    rbp
0x14003c174  push    rsi
0x14003c175  push    rdi
0x14003c176  push    r12
0x14003c178  push    r13
0x14003c17a  push    r14
0x14003c17c  push    r15
0x14003c17e  mov     rbp, rsp
0x14003c181  sub     rsp, 80h
0x14003c188  mov     rsi, [rcx+1160h]
0x14003c18f  lea     rax, [rbp+var_10]
0x14003c193  mov     [rbp+var_10.Blink], rax
0x14003c197  mov     r15, rcx
0x14003c19a  lea     rax, [rbp+var_10]
0x14003c19e  mov     rcx, rsi; SpinLock
0x14003c1a1  mov     [rbp+var_10.Flink], rax
0x14003c1a5  mov     r13, r9
0x14003c1a8  mov     r14d, r8d
0x14003c1ab  mov     r12d, edx
0x14003c1ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003c1b5  nop     dword ptr [rax+rax+00h]
0x14003c1ba  cmp     dword ptr [rsi+200h], 0
0x14003c1c1  movzx   edi, al
0x14003c1c4  mov     [rbp+var_3E], al
0x14003c1c7  jnz     short loc_14003C1F1
0x14003c1c9  cmp     dword ptr [rsi+204h], 0
0x14003c1d0  jnz     short loc_14003C1F1
0x14003c1d2  cmp     dword ptr [rsi+210h], 0
0x14003c1d9  jnz     short loc_14003C1F1
0x14003c1db  cmp     dword ptr [rsi+214h], 0
0x14003c1e2  jnz     short loc_14003C1F1
0x14003c1e4  cmp     dword ptr [rsi+208h], 0
0x14003c1eb  jz      loc_14003C28B
0x14003c1f1  lea     rcx, [rsi+110h]; Event
0x14003c1f8  call    cs:__imp_KeReadStateEvent
0x14003c1ff  nop     dword ptr [rax+rax+00h]
0x14003c204  test    eax, eax
0x14003c206  jz      loc_14003C2B2
0x14003c20c  mov     bl, 1
0x14003c20e  cmp     r14d, 34h ; '4'
0x14003c212  jnz     loc_14003C68D
0x14003c218  mov     rax, [rsi+258h]
0x14003c21f  mov     dword ptr [rsi+90h], 0
0x14003c229  mov     byte ptr [rax+14h], 0
0x14003c22d  mov     rax, [rsi+258h]
0x14003c234  mov     byte ptr [rax+2Ch], 0
0x14003c238  mov     rax, [rsi+258h]
0x14003c23f  mov     byte ptr [rax+44h], 0
0x14003c243  mov     rax, [rsi+258h]
0x14003c24a  mov     byte ptr [rax+5Ch], 0
0x14003c24e  mov     rcx, [rsi+258h]
0x14003c255  mov     byte ptr [rcx+74h], 0
0x14003c259  add     [rsi+208h], r12d
0x14003c260  xor     r9d, r9d
0x14003c263  mov     r8d, r14d
0x14003c266  xor     edx, edx
0x14003c268  mov     rcx, rsi
0x14003c26b  call    ndisSelectiveSuspendSetResumeBusyReason
0x14003c270  movzx   edx, dil; NewIrql
0x14003c274  mov     rcx, rsi; SpinLock
0x14003c277  call    cs:__imp_KeReleaseSpinLock
0x14003c27e  nop     dword ptr [rax+rax+00h]
0x14003c283  movzx   eax, bl
0x14003c286  jmp     loc_14003C671
0x14003c28b  cmp     dword ptr [rsi+20Ch], 0
0x14003c292  jnz     loc_14003C1F1
0x14003c298  cmp     dword ptr [rsi+240h], 0
0x14003c29f  jnz     loc_14003C1F1
0x14003c2a5  cmp     dword ptr [rsi+1FCh], 0
0x14003c2ac  jnz     loc_14003C1F1
0x14003c2b2  cmp     r14d, 36h ; '6'
0x14003c2b6  jz      loc_14003C532
0x14003c2bc  lea     rax, [rbp+var_10]
0x14003c2c0  mov     ecx, r14d
0x14003c2c3  mov     [rbp+var_10.Blink], rax
0x14003c2c7  lea     rax, [rbp+var_10]
0x14003c2cb  mov     [rbp+var_10.Flink], rax
0x14003c2cf  sub     ecx, 31h ; '1'
0x14003c2d2  jz      loc_14003C9BB
0x14003c2d8  sub     ecx, 2
0x14003c2db  jz      loc_14003CA18
0x14003c2e1  sub     ecx, 2
0x14003c2e4  jz      loc_14003C8E5
0x14003c2ea  cmp     ecx, 1
0x14003c2ed  jz      loc_14003C9B0
0x14003c2f3  cmp     r14d, 34h ; '4'
0x14003c2f7  jnz     loc_14003C92B
0x14003c2fd  mov     eax, cs:?ndisNblTrackerMode@@3W4_NDIS_NBL_TRACKER_MODE@@A; _NDIS_NBL_TRACKER_MODE ndisNblTrackerMode
0x14003c303  xor     edx, edx; struct NDIS_NBL_TRACKER_HANDLE__ *
0x14003c305  test    eax, eax
0x14003c307  jz      loc_14003C4FD
0x14003c30d  mov     rdi, [rsi+260h]
0x14003c314  xor     ecx, ecx
0x14003c316  mov     ebx, cs:?ndisNblTrackerEpoch@@3KA; ulong ndisNblTrackerEpoch
0x14003c31c  xor     r10d, r10d
0x14003c31f  mov     [rbp+var_38], rdx
0x14003c323  mov     r9b, 1
0x14003c326  mov     [rbp+var_30], rcx
0x14003c32a  mov     [rbp+var_20], r10
0x14003c32e  mov     [rbp+var_40], r9b
0x14003c332  mov     [rbp+var_3F], cl
0x14003c335  cmp     eax, 3
0x14003c338  jl      short loc_14003C35B
0x14003c33a  mov     r9, rdi; void *
0x14003c33d  mov     dword ptr [rsp+80h+var_60], 1; unsigned int
0x14003c345  mov     r8d, 1; unsigned int
0x14003c34b  mov     rcx, r13; struct _NET_BUFFER_LIST *
0x14003c34e  call    ?ndisNblTrackerRecordEventInternal@@YAXPEAU_NET_BUFFER_LIST@@PEAUNDIS_NBL_TRACKER_HANDLE__@@KPEAXK@Z; ndisNblTrackerRecordEventInternal(_NET_BUFFER_LIST *,NDIS_NBL_TRACKER_HANDLE__ *,ulong,void *,ulong)
0x14003c353  xor     edx, edx
0x14003c355  mov     r9b, 1
0x14003c358  xor     r10d, r10d
0x14003c35b  mov     r12, rdi
0x14003c35e  and     r12, 0FFFFFFFFFFFFFFFDh
0x14003c362  test    r12b, 1
0x14003c366  jz      loc_14003C7BE
0x14003c36c  mov     rax, rbx
0x14003c36f  add     rax, rax
0x14003c372  mov     rbx, rax
0x14003c375  xor     rbx, rdi
0x14003c378  and     rbx, 0FFFFFFFFFFFFFFFDh
0x14003c37c  xor     rbx, rax
0x14003c37f  and     r12, 0FFFFFFFFFFFFFFF8h
0x14003c383  mov     r12, [r12+18h]
0x14003c388  test    r13, r13
0x14003c38b  jz      loc_14003C479
0x14003c391  mov     r15, r13
0x14003c394  mov     rdi, [r15+168h]
0x14003c39b  lea     r9, WPP_RECORDER_INITIALIZED
0x14003c3a2  lea     r14, WPP_78a33c75b2d2335d1cf1dcc315edf7b8_Traceguids
0x14003c3a9  cmp     [r15+168h], rdi
0x14003c3b0  jnz     short loc_14003C404
0x14003c3b2  test    rdi, rdi
0x14003c3b5  jz      loc_14003C7C6
0x14003c3bb  test    dil, 4
0x14003c3bf  jnz     loc_14003C85B
0x14003c3c5  mov     rcx, [r15+78h]
0x14003c3c9  test    rcx, rcx
0x14003c3cc  jz      loc_14003C84E
0x14003c3d2  movzx   r8d, byte ptr [rcx]
0x14003c3d6  lea     eax, [r8-11h]
0x14003c3da  cmp     al, 1
0x14003c3dc  ja      loc_14003C867
0x14003c3e2  cmp     rcx, r12
0x14003c3e5  jz      loc_14003C79B
0x14003c3eb  inc     rdx
0x14003c3ee  mov     rax, rbx
0x14003c3f1  mov     [rbp+var_38], rdx
0x14003c3f5  mov     [r15+168h], rax
0x14003c3fc  mov     r15, [r15]
0x14003c3ff  test    r15, r15
0x14003c402  jnz     short loc_14003C3A9
0x14003c404  movzx   r14d, [rbp+var_3F]
0x14003c409  movzx   r9d, [rbp+var_40]
0x14003c40e  test    dil, 1
0x14003c412  jz      short loc_14003C460
0x14003c414  mov     r10, [rbp+var_30]
0x14003c418  sub     r10, rdx
0x14003c41b  mov     [rbp+var_30], r10
0x14003c41f  jz      short loc_14003C460
0x14003c421  test    r9b, r9b
0x14003c424  jz      loc_14003C73D
0x14003c42a  mov     r8, rdi
0x14003c42d  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14003c431  shr     r8, 1
0x14003c434  and     r8d, 1
0x14003c438  add     r8, 3
0x14003c43c  shl     r8, 4
0x14003c440  add     r8, rdi
0x14003c443  test    r9b, r9b
0x14003c446  jz      loc_14003C782
0x14003c44c  mov     eax, gs:1A4h
0x14003c454  shl     eax, 0Ch
0x14003c457  mov     ecx, eax
0x14003c459  mov     rax, [r8]
0x14003c45c  add     [rcx+rax], r10
0x14003c460  mov     r10, [rbp+var_20]
0x14003c464  mov     [rbp+var_30], rdx
0x14003c468  test    r15, r15
0x14003c46b  jnz     loc_14003C394
0x14003c471  mov     r14d, [rbp+arg_10]
0x14003c475  mov     r15, [rbp+arg_0]
0x14003c479  test    bl, 1
0x14003c47c  jz      short loc_14003C4FB
0x14003c47e  sub     rdx, [rbp+var_20]
0x14003c482  mov     [rbp+var_38], rdx
0x14003c486  jz      short loc_14003C4FB
0x14003c488  test    r9b, r9b
0x14003c48b  jnz     short loc_14003C4C6
0x14003c48d  cmp     [rbp+var_3F], r9b
0x14003c491  jnz     short loc_14003C4C6
0x14003c493  call    cs:__imp_KeGetCurrentIrql
0x14003c49a  nop     dword ptr [rax+rax+00h]
0x14003c49f  mov     rdx, rbx
0x14003c4a2  and     rbx, 0FFFFFFFFFFFFFFF8h
0x14003c4a6  shr     rdx, 1
0x14003c4a9  and     edx, 1
0x14003c4ac  add     rdx, 3
0x14003c4b0  shl     rdx, 4
0x14003c4b4  add     rdx, rbx
0x14003c4b7  cmp     al, 2
0x14003c4b9  jz      short loc_14003C4E3
0x14003c4bb  mov     r8, [rbp+var_38]
0x14003c4bf  lock add [rdx+8], r8
0x14003c4c4  jmp     short loc_14003C4FB
0x14003c4c6  mov     rdx, rbx
0x14003c4c9  and     rbx, 0FFFFFFFFFFFFFFF8h
0x14003c4cd  shr     rdx, 1
0x14003c4d0  and     edx, 1
0x14003c4d3  add     rdx, 3
0x14003c4d7  shl     rdx, 4
0x14003c4db  add     rdx, rbx
0x14003c4de  test    r9b, r9b
0x14003c4e1  jz      short loc_14003C4BB
0x14003c4e3  mov     eax, gs:1A4h
0x14003c4eb  mov     r8, [rbp+var_38]
0x14003c4ef  shl     eax, 0Ch
0x14003c4f2  mov     ecx, eax
0x14003c4f4  mov     rax, [rdx]
0x14003c4f7  add     [rcx+rax], r8
0x14003c4fb  xor     edx, edx
0x14003c4fd  mov     rax, r13
0x14003c500  test    r13, r13
0x14003c503  jz      short loc_14003C517
0x14003c505  mov     ecx, [rbp+arg_20]
0x14003c508  mov     [rax+70h], rcx
0x14003c50c  mov     rdx, rax
0x14003c50f  mov     rax, [rax]
0x14003c512  test    rax, rax
0x14003c515  jnz     short loc_14003C508
0x14003c517  mov     rax, [rsi+228h]
0x14003c51e  mov     [rax], r13
0x14003c521  mov     [rsi+228h], rdx
0x14003c528  mov     dword ptr [rsi+278h], 0
0x14003c532  xor     r12d, r12d
0x14003c535  xor     ebx, ebx
0x14003c537  xor     dil, dil
0x14003c53a  mov     r13b, 1
0x14003c53d  cmp     [rsi+200h], ebx
0x14003c543  jnz     short loc_14003C597
0x14003c545  cmp     [rsi+204h], ebx
0x14003c54b  jnz     short loc_14003C597
0x14003c54d  cmp     [rsi+210h], ebx
0x14003c553  jnz     short loc_14003C597
0x14003c555  cmp     [rsi+214h], ebx
0x14003c55b  jnz     short loc_14003C597
0x14003c55d  cmp     [rsi+208h], ebx
0x14003c563  jnz     short loc_14003C597
0x14003c565  cmp     [rsi+20Ch], ebx
0x14003c56b  jnz     short loc_14003C597
0x14003c56d  cmp     [rsi+240h], ebx
0x14003c573  jnz     short loc_14003C597
0x14003c575  cmp     [rsi+1FCh], ebx
0x14003c57b  jnz     short loc_14003C597
0x14003c57d  lea     rcx, [rsi+110h]; Event
0x14003c584  movzx   edi, r13b
0x14003c588  call    cs:__imp_KeClearEvent
0x14003c58f  nop     dword ptr [rax+rax+00h]
0x14003c594  mov     ebx, r14d
0x14003c597  cmp     r14d, 34h ; '4'
0x14003c59b  jnz     loc_14003C6E4
0x14003c5a1  mov     rax, [rsi+258h]
0x14003c5a8  mov     dword ptr [rsi+90h], 0
0x14003c5b2  mov     byte ptr [rax+14h], 0
0x14003c5b6  mov     rax, [rsi+258h]
0x14003c5bd  mov     byte ptr [rax+2Ch], 0
0x14003c5c1  mov     rax, [rsi+258h]
0x14003c5c8  mov     byte ptr [rax+44h], 0
0x14003c5cc  mov     rax, [rsi+258h]
0x14003c5d3  mov     byte ptr [rax+5Ch], 0
0x14003c5d7  mov     rax, [rsi+258h]
0x14003c5de  mov     byte ptr [rax+74h], 0
0x14003c5e2  mov     eax, [rbp+arg_8]
0x14003c5e5  add     [rsi+208h], eax
0x14003c5eb  movzx   edx, [rbp+var_3E]; NewIrql
0x14003c5ef  mov     rcx, rsi; SpinLock
0x14003c5f2  call    cs:__imp_KeReleaseSpinLock
0x14003c5f9  nop     dword ptr [rax+rax+00h]
0x14003c5fe  test    r13b, r13b
0x14003c601  jz      short loc_14003C615
0x14003c603  test    dil, dil
0x14003c606  jz      short loc_14003C615
0x14003c608  mov     r8b, 1; unsigned __int8
0x14003c60b  xor     edx, edx; unsigned __int8
0x14003c60d  mov     rcx, r15; struct _NDIS_MINIPORT_BLOCK *
0x14003c610  call    ?ndisWdfAcquirePowerReferenceHelper@@YAXPEAU_NDIS_MINIPORT_BLOCK@@EE@Z; ndisWdfAcquirePowerReferenceHelper(_NDIS_MINIPORT_BLOCK *,uchar,uchar)
0x14003c615  test    r12, r12
0x14003c618  jnz     loc_14003C9D5
0x14003c61e  lea     rax, [rbp+var_10]
0x14003c622  cmp     [rbp+var_10.Flink], rax
0x14003c626  jz      short loc_14003C634
0x14003c628  lea     rdx, [rbp+var_10]; struct _LIST_ENTRY *
0x14003c62c  mov     rcx, r15; struct _NDIS_MINIPORT_BLOCK *
0x14003c62f  call    ?ndisCancelDequeuedDirectOidRequests@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_LIST_ENTRY@@@Z; ndisCancelDequeuedDirectOidRequests(_NDIS_MINIPORT_BLOCK *,_LIST_ENTRY *)
0x14003c634  test    ebx, ebx
0x14003c636  jz      short loc_14003C66A
0x14003c638  test    cs:byte_140121001, 8
  ... truncated ...
```
