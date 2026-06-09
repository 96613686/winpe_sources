# L2tpReceive

- ea: `0x140019a80`
- end: `0x14001a28c`
- name: `L2tpReceive`
- size: `2060`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400012e0`
- `0x1400013f0`
- `0x140003050`
- `0x140003080`
- `0x1400031ec`
- `0x1400032f0`
- `0x140003a58`
- `0x140013edc`
- `0x1400154b8`
- `0x1400181a8`
- `0x140019a80`
- `0x14001a2a0`
- `0x14001a640`
- `0x14001ac30`
- `0x14001b830`
- `0x14001c400`
- `0x140020d10`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140019c7e`
- `ntoskrnl!RtlCompareMemory` at `0x14001a092`
- `ntoskrnl!RtlCompareMemory` at `0x140019c7e`
- `ntoskrnl!RtlCompareMemory` at `0x14001a092`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140019b34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140019ff8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a0b9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140019b34`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140019ff8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a0b9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ce5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d32`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019dce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a1dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ce5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019d32`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019dce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a1dd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019e9b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a23c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140019e9b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a23c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019cb4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019d0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019d51`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019cb4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019d0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019d51`
- `NDIS!NdisGetDataBuffer` at `0x140019b05`
- `NDIS!NdisGetDataBuffer` at `0x140019b05`
- `NDIS!NdisFreeNetBufferList` at `0x140019f40`
- `NDIS!NdisFreeNetBufferList` at `0x140019f40`

## pseudocode

```c
void __fastcall L2tpReceive(__int64 *a1, _QWORD *a2, struct _NET_BUFFER_LIST *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rax
  char v7; // r15
  struct _NET_BUFFER *FirstNetBuffer; // rcx
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rbp
  ULONG DataLength; // r12d
  char *v13; // rax
  char *v14; // rsi
  __int16 v15; // cx
  __int16 **v16; // r12
  _WORD *v17; // rax
  char v18; // al
  KIRQL v19; // al
  bool v20; // zf
  KIRQL v21; // al
  KSPIN_LOCK *v22; // rcx
  struct _NET_BUFFER_LIST *v23; // r12
  _QWORD *v24; // rdx
  PDEVICE_OBJECT v25; // rcx
  unsigned __int16 *v26; // rax
  int v27; // r10d
  unsigned __int16 *v28; // rax
  __int64 v29; // r8
  unsigned __int16 *v30; // rax
  __int64 v31; // rdx
  unsigned __int16 *v32; // rax
  __int64 v33; // r9
  __int64 v34; // rdx
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  PVOID v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // rdx
  UINT AlignOffset[2]; // [rsp+20h] [rbp-A8h]
  __int64 v41; // [rsp+38h] [rbp-90h]
  _WORD *Entry; // [rsp+50h] [rbp-78h]
  char *DataBuffer; // [rsp+58h] [rbp-70h]
  __int64 v44; // [rsp+60h] [rbp-68h] BYREF
  _WORD *v45; // [rsp+68h] [rbp-60h] BYREF
  __int64 v46; // [rsp+70h] [rbp-58h]
  __int16 v47; // [rsp+D0h] [rbp+8h]
  char v48; // [rsp+D0h] [rbp+8h]
  int v49; // [rsp+D8h] [rbp+10h]
  int v51; // [rsp+E8h] [rbp+20h]

  v3 = *a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids);
  }
  v46 = a2[1];
  v6 = 240;
  v7 = 1;
  FirstNetBuffer = a3->FirstNetBuffer;
  if ( *(_WORD *)v46 != 2 )
    v6 = 280;
  v9 = 0;
  v10 = 0;
  v45 = 0;
  v11 = v3 - v6;
  v44 = 0;
  DataLength = FirstNetBuffer->DataLength;
  DataBuffer = (char *)NdisGetDataBuffer(FirstNetBuffer, DataLength, 0, 1u, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    *(_QWORD *)AlignOffset = *(_QWORD *)(*a2 + 384LL);
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids);
  }
  v13 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v11 + 1216));
  v14 = v13;
  if ( v13 )
  {
    *(_OWORD *)v13 = 0;
    *((_OWORD *)v13 + 1) = 0;
    *((_OWORD *)v13 + 2) = 0;
    *((_OWORD *)v13 + 3) = 0;
    *((_OWORD *)v13 + 4) = 0;
    v15 = ExplodeL2tpHeader(DataBuffer, DataLength, v13 + 16);
    v47 = v15;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids, DataLength);
      v15 = v47;
    }
    if ( v15 == 2 )
      goto LABEL_102;
    v16 = (__int16 **)(v14 + 16);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v26 = (unsigned __int16 *)*((_QWORD *)v14 + 7);
      if ( v26 )
        v27 = *v26;
      else
        v27 = 0;
      v28 = (unsigned __int16 *)*((_QWORD *)v14 + 6);
      if ( v28 )
        v29 = *v28;
      else
        v29 = 0;
      v30 = (unsigned __int16 *)*((_QWORD *)v14 + 5);
      if ( v30 )
        v31 = *v30;
      else
        v31 = 0;
      v32 = (unsigned __int16 *)*((_QWORD *)v14 + 4);
      if ( v32 )
        v33 = *v32;
      else
        v33 = 0;
      AlignOffset[0] = v31;
      WPP_SF_dddd(WPP_GLOBAL_Control->AttachedDevice, v31, v29, v33, *(_QWORD *)AlignOffset, v29, v27);
    }
    if ( v47 )
    {
LABEL_102:
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_50;
      }
      v36 = 15;
    }
    else
    {
      if ( **v16 >= 0 )
      {
        v17 = 0;
        Entry = 0;
        v49 = 0;
        v51 = 0;
        goto LABEL_16;
      }
      v17 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v11 + 1088));
      Entry = v17;
      if ( v17 )
      {
        v34 = *((unsigned int *)v14 + 17);
        v51 = *((_DWORD *)v14 + 16);
        v49 = v34;
        if ( (_DWORD)v34 )
        {
          ExplodeControlAvps(&DataBuffer[*((unsigned int *)v14 + 16)], v34, v17);
          v17 = Entry;
        }
        else
        {
          *v17 = 3;
        }
LABEL_16:
        v48 = 1;
        v18 = LookUpTunnelAndVcCbs(
                v11,
                *((_QWORD *)v14 + 4),
                *((_QWORD *)v14 + 5),
                (int)v14 + 16,
                (__int64)v17,
                (__int64)&v45,
                (__int64)&v44);
        v10 = v44;
        v9 = (__int64)v45;
        if ( !v18 )
          goto LABEL_48;
        if ( !v45 )
          goto LABEL_27;
        if ( *(_WORD *)v46 == v45[24] )
        {
          if ( *(_WORD *)v46 == 2 )
          {
            if ( RtlCompareMemory((const void *)(v46 + 4), v45 + 26, 4u) == 4 )
            {
              v16 = (__int16 **)(v14 + 16);
              goto LABEL_22;
            }
          }
          else if ( RtlCompareMemory((const void *)(v46 + 8), v45 + 28, 0x10u) == 16 )
          {
LABEL_22:
            v46 = *(_QWORD *)(v9 + 24);
            if ( *(_DWORD *)(v46 + 20) )
            {
              v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 32));
              v20 = *(_DWORD *)(v9 + 124) == 0;
              *(_BYTE *)(v9 + 40) = v19;
              if ( !v20 )
              {
                if ( *(_QWORD *)(v9 + 264) )
                {
                  ++*(_DWORD *)(v9 + 276);
                }
                else
                {
                  v37 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v46 + 576));
                  *(_QWORD *)(v9 + 264) = v37;
                  if ( v37 )
                  {
                    *(_DWORD *)(v9 + 276) = 1;
                    *(_DWORD *)(v9 + 272) = 0;
                    ReferenceTunnel(v9, 0);
                    v38 = *(_QWORD **)(v9 + 264);
                    v38[1] = v38;
                    *v38 = v38;
                    TimerQScheduleItem(
                      *(_QWORD *)(v9 + 304),
                      *(_QWORD *)(v9 + 264),
                      0,
                      (unsigned int)HelloTimerEvent,
                      v9);
                  }
                }
              }
              KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 32), *(_BYTE *)(v9 + 40));
            }
LABEL_27:
            if ( **v16 >= 0 )
            {
              if ( v10 )
              {
                v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 72));
                v20 = (*(_DWORD *)(v10 + 60) & 0x200) == 0;
                v22 = (KSPIN_LOCK *)(v10 + 72);
                *(_BYTE *)(v10 + 80) = v21;
                if ( !v20 )
                {
                  ++*(_DWORD *)(v10 + 64);
                  KeReleaseSpinLock(v22, v21);
                  v23 = a3;
                  *((_QWORD *)v14 + 9) = a3;
                  *(_BYTE *)(v10 + 472) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 464));
                  v24 = *(_QWORD **)(v10 + 448);
                  if ( *v24 != v10 + 440 )
                    __fastfail(3u);
                  *(_QWORD *)v14 = v10 + 440;
                  v7 = 0;
                  *((_QWORD *)v14 + 1) = v24;
                  *v24 = v14;
                  *(_QWORD *)(v10 + 448) = v14;
                  v48 = 0;
                  if ( *(_BYTE *)(v10 + 456) || (unsigned int)ScheduleWork(v11, &ReceivePayloadPassive, v10) )
                    DereferenceCall(v10);
                  else
                    *(_BYTE *)(v10 + 456) = 1;
                  KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 464), *(_BYTE *)(v10 + 472));
LABEL_36:
                  if ( Entry )
                    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v11 + 1088), Entry);
                  if ( !v48 )
                  {
LABEL_39:
                    ReceiveDataComplete(*a2);
                    if ( !v7 )
                      goto LABEL_40;
                    goto LABEL_59;
                  }
LABEL_51:
                  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v11 + 1216), v14);
                  goto LABEL_39;
                }
                KeReleaseSpinLock(v22, v21);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) )
                {
                  WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids, v10);
                }
LABEL_48:
                v23 = a3;
                goto LABEL_36;
              }
              v25 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
                || !BYTE1(WPP_GLOBAL_Control->Timer) )
              {
                goto LABEL_48;
              }
              v39 = 19;
LABEL_91:
              WPP_SF_(v25->AttachedDevice, v39, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids);
              goto LABEL_48;
            }
            if ( Entry )
            {
              v41 = (__int64)v16;
              v23 = a3;
              v7 = ReceiveControl(v11, v9, v10, (_DWORD)a3, v51, v49, (__int64)a2, v41, (__int64)Entry);
              goto LABEL_36;
            }
LABEL_50:
            v23 = a3;
            goto LABEL_51;
          }
        }
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_48;
        }
        v39 = 18;
        goto LABEL_91;
      }
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_50;
      }
      v36 = 17;
    }
    WPP_SF_(v35->AttachedDevice, v36, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids);
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
    || !BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v23 = a3;
    goto LABEL_39;
  }
  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids);
  ReceiveDataComplete(*a2);
  v23 = a3;
LABEL_59:
  NdisFreeNetBufferList(v23);
LABEL_40:
  if ( v9 )
    DereferenceTunnel(v9);
  if ( v10 )
    DereferenceVc(v10);
}

```

## disassembly

```asm
0x140019a80  mov     [rsp+NetBufferList], r8
0x140019a85  push    rbx
0x140019a86  push    rbp
0x140019a87  push    rsi
0x140019a88  push    rdi
0x140019a89  push    r12
0x140019a8b  push    r13
0x140019a8d  push    r14
0x140019a8f  push    r15
0x140019a91  sub     rsp, 88h
0x140019a98  mov     rbp, [rcx]
0x140019a9b  mov     rsi, r8
0x140019a9e  mov     r14, rdx
0x140019aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140019aa8  lea     r13, WPP_GLOBAL_Control
0x140019aaf  cmp     rcx, r13
0x140019ab2  jz      short loc_140019ABF
0x140019ab4  mov     eax, [rcx+2Ch]
0x140019ab7  test    al, 20h
0x140019ab9  jnz     loc_140019EAC
0x140019abf  mov     rcx, [r14+8]
0x140019ac3  mov     edx, 118h
0x140019ac8  mov     [rsp+0C8h+var_58], rcx
0x140019acd  mov     eax, 0F0h
0x140019ad2  mov     r9d, 1; AlignMultiple
0x140019ad8  mov     r15b, 1
0x140019adb  cmp     word ptr [rcx], 2
0x140019adf  mov     rcx, [rsi+8]; NetBuffer
0x140019ae3  cmovnz  eax, edx
0x140019ae6  xor     edi, edi
0x140019ae8  xor     ebx, ebx
0x140019aea  mov     [rsp+0C8h+var_60], rdi
0x140019aef  sub     rbp, rax
0x140019af2  mov     [rsp+0C8h+var_68], rbx
0x140019af7  mov     r12d, [rcx+18h]
0x140019afb  xor     r8d, r8d; Storage
0x140019afe  mov     edx, r12d; BytesNeeded
0x140019b01  mov     [rsp+0C8h+AlignOffset], ebx; AlignOffset
0x140019b05  call    cs:__imp_NdisGetDataBuffer
0x140019b0c  nop     dword ptr [rax+rax+00h]
0x140019b11  mov     [rsp+0C8h+var_70], rax
0x140019b16  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b1d  cmp     rcx, r13
0x140019b20  jz      short loc_140019B2D
0x140019b22  mov     eax, [rcx+2Ch]
0x140019b25  test    al, 20h
0x140019b27  jnz     loc_140019ED0
0x140019b2d  lea     rcx, [rbp+4C0h]; Lookaside
0x140019b34  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140019b3b  nop     dword ptr [rax+rax+00h]
0x140019b40  mov     rsi, rax
0x140019b43  test    rax, rax
0x140019b46  jz      loc_140019E36
0x140019b4c  mov     rcx, [rsp+0C8h+var_70]
0x140019b51  lea     r8, [rax+10h]
0x140019b55  xorps   xmm0, xmm0
0x140019b58  mov     edx, r12d
0x140019b5b  movups  xmmword ptr [rax], xmm0
0x140019b5e  movups  xmmword ptr [rax+10h], xmm0
0x140019b62  movups  xmmword ptr [rax+20h], xmm0
0x140019b66  movups  xmmword ptr [rax+30h], xmm0
0x140019b6a  movups  xmmword ptr [rax+40h], xmm0
0x140019b6e  call    ExplodeL2tpHeader
0x140019b73  movzx   ecx, ax
0x140019b76  mov     [rsp+0C8h+arg_0], ax
0x140019b7e  mov     r10, cs:WPP_GLOBAL_Control
0x140019b85  lea     rax, WPP_GLOBAL_Control
0x140019b8c  cmp     r10, rax
0x140019b8f  jz      short loc_140019BA4
0x140019b91  mov     eax, [r10+2Ch]
0x140019b95  test    al, 2
0x140019b97  jnz     loc_140019F51
0x140019b9d  lea     rax, WPP_GLOBAL_Control
0x140019ba4  cmp     cx, 2
0x140019ba8  jz      loc_14001A24D
0x140019bae  mov     rcx, cs:WPP_GLOBAL_Control
0x140019bb5  lea     r12, [rsi+10h]
0x140019bb9  cmp     rcx, rax
0x140019bbc  jz      short loc_140019BD0
0x140019bbe  mov     eax, [rcx+2Ch]
0x140019bc1  test    al, 2
0x140019bc3  jnz     loc_140019F81
0x140019bc9  lea     rax, WPP_GLOBAL_Control
0x140019bd0  cmp     [rsp+0C8h+arg_0], bx
0x140019bd8  jnz     loc_14001A24D
0x140019bde  mov     rax, [r12]
0x140019be2  cmp     [rax], bx
0x140019be5  jl      loc_140019FF1
0x140019beb  xor     eax, eax
0x140019bed  mov     [rsp+0C8h+Entry], rax
0x140019bf2  mov     [rsp+0C8h+arg_8], eax
0x140019bf9  mov     [rsp+0C8h+arg_18], eax
0x140019c00  mov     r8, [r12+18h]
0x140019c05  lea     rcx, [rsp+0C8h+var_68]
0x140019c0a  mov     rdx, [r12+10h]
0x140019c0f  mov     r9, r12
0x140019c12  mov     [rsp+0C8h+var_98], rcx
0x140019c17  lea     rcx, [rsp+0C8h+var_60]
0x140019c1c  mov     [rsp+0C8h+var_A0], rcx
0x140019c21  mov     rcx, rbp
0x140019c24  mov     byte ptr [rsp+0C8h+arg_0], r15b
0x140019c2c  mov     qword ptr [rsp+0C8h+AlignOffset], rax
0x140019c31  call    LookUpTunnelAndVcCbs
0x140019c36  mov     rbx, [rsp+0C8h+var_68]
0x140019c3b  mov     rdi, [rsp+0C8h+var_60]
0x140019c40  test    al, al
0x140019c42  jz      loc_140019E6E
0x140019c48  test    rdi, rdi
0x140019c4b  jz      loc_140019CF1
0x140019c51  mov     rcx, [rsp+0C8h+var_58]
0x140019c56  movzx   eax, word ptr [rcx]
0x140019c59  cmp     ax, [rdi+30h]
0x140019c5d  jnz     loc_140019E57
0x140019c63  cmp     ax, 2
0x140019c67  jnz     loc_14001A084
0x140019c6d  lea     rdx, [rdi+34h]; Source2
0x140019c71  add     rcx, 4; Source1
0x140019c75  mov     r8d, 4; Length
0x140019c7b  xor     r12b, r12b
0x140019c7e  call    cs:__imp_RtlCompareMemory
0x140019c85  nop     dword ptr [rax+rax+00h]
0x140019c8a  cmp     rax, 4
0x140019c8e  jnz     short loc_140019C94
0x140019c90  movzx   r12d, r15b
0x140019c94  test    r12b, r12b
0x140019c97  jz      loc_140019E57
0x140019c9d  lea     r12, [rsi+10h]
0x140019ca1  mov     rax, [rdi+18h]
0x140019ca5  mov     [rsp+0C8h+var_58], rax
0x140019caa  cmp     dword ptr [rax+14h], 0
0x140019cae  jz      short loc_140019CF1
0x140019cb0  lea     rcx, [rdi+20h]; SpinLock
0x140019cb4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019cbb  nop     dword ptr [rax+rax+00h]
0x140019cc0  cmp     dword ptr [rdi+7Ch], 0
0x140019cc4  mov     [rdi+28h], al
0x140019cc7  jz      short loc_140019CDD
0x140019cc9  cmp     qword ptr [rdi+108h], 0
0x140019cd1  jz      loc_14001A0AD
0x140019cd7  inc     dword ptr [rdi+114h]
0x140019cdd  movzx   edx, byte ptr [rdi+28h]; NewIrql
0x140019ce1  lea     rcx, [rdi+20h]; SpinLock
0x140019ce5  call    cs:__imp_KeReleaseSpinLock
0x140019cec  nop     dword ptr [rax+rax+00h]
0x140019cf1  mov     rax, [r12]
0x140019cf5  cmp     word ptr [rax], 0
0x140019cf9  jl      loc_140019E7B
0x140019cff  test    rbx, rbx
0x140019d02  jz      loc_14001A1A5
0x140019d08  lea     rcx, [rbx+48h]; SpinLock
0x140019d0c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019d13  nop     dword ptr [rax+rax+00h]
0x140019d18  test    dword ptr [rbx+3Ch], 200h
0x140019d1f  lea     rcx, [rbx+48h]; SpinLock
0x140019d23  mov     [rbx+50h], al
0x140019d26  movzx   edx, al; NewIrql
0x140019d29  jz      loc_14001A1DD
0x140019d2f  inc     dword ptr [rbx+40h]
0x140019d32  call    cs:__imp_KeReleaseSpinLock
0x140019d39  nop     dword ptr [rax+rax+00h]
0x140019d3e  mov     r12, [rsp+0C8h+NetBufferList]
0x140019d46  lea     rcx, [rbx+1D0h]; SpinLock
0x140019d4d  mov     [rsi+48h], r12
0x140019d51  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019d58  nop     dword ptr [rax+rax+00h]
0x140019d5d  mov     [rbx+1D8h], al
0x140019d63  lea     rax, [rbx+1B8h]
0x140019d6a  mov     rdx, [rax+8]
0x140019d6e  cmp     [rdx], rax
0x140019d71  jnz     loc_14001A1D6
0x140019d77  mov     [rsi], rax
0x140019d7a  xor     r15b, r15b
0x140019d7d  mov     [rsi+8], rdx
0x140019d81  mov     [rdx], rsi
0x140019d84  mov     [rax+8], rsi
0x140019d88  mov     byte ptr [rsp+0C8h+arg_0], r15b
0x140019d90  cmp     [rbx+1C8h], r15b
0x140019d97  jnz     short loc_140019DB8
0x140019d99  mov     r8, rbx
0x140019d9c  lea     rdx, ReceivePayloadPassive
0x140019da3  mov     rcx, rbp
0x140019da6  call    ScheduleWork
0x140019dab  test    eax, eax
0x140019dad  jnz     short loc_140019DB8
0x140019daf  mov     byte ptr [rbx+1C8h], 1
0x140019db6  jmp     short loc_140019DC0
0x140019db8  mov     rcx, rbx
0x140019dbb  call    DereferenceCall
0x140019dc0  movzx   edx, byte ptr [rbx+1D8h]; NewIrql
0x140019dc7  lea     rcx, [rbx+1D0h]; SpinLock
0x140019dce  call    cs:__imp_KeReleaseSpinLock
0x140019dd5  nop     dword ptr [rax+rax+00h]
0x140019dda  mov     rax, [rsp+0C8h+Entry]
0x140019ddf  test    rax, rax
0x140019de2  jnz     loc_14001A232
0x140019de8  cmp     byte ptr [rsp+0C8h+arg_0], 0
0x140019df0  jnz     loc_140019E91
0x140019df6  mov     rcx, [r14]
0x140019df9  call    ReceiveDataComplete
0x140019dfe  test    r15b, r15b
0x140019e01  jnz     loc_140019F3D
0x140019e07  test    rdi, rdi
0x140019e0a  jz      short loc_140019E14
0x140019e0c  mov     rcx, rdi
0x140019e0f  call    DereferenceTunnel
0x140019e14  test    rbx, rbx
0x140019e17  jz      short loc_140019E21
0x140019e19  mov     rcx, rbx
0x140019e1c  call    DereferenceVc
0x140019e21  add     rsp, 88h
0x140019e28  pop     r15
0x140019e2a  pop     r14
0x140019e2c  pop     r13
0x140019e2e  pop     r12
0x140019e30  pop     rdi
0x140019e31  pop     rsi
0x140019e32  pop     rbp
0x140019e33  pop     rbx
0x140019e34  retn
0x140019e36  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e3d  lea     rax, WPP_GLOBAL_Control
0x140019e44  cmp     rcx, rax
0x140019e47  jnz     loc_140019F03
0x140019e4d  mov     r12, [rsp+0C8h+NetBufferList]
0x140019e55  jmp     short loc_140019DF6
0x140019e57  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e5e  lea     rax, WPP_GLOBAL_Control
0x140019e65  cmp     rcx, rax
0x140019e68  jnz     loc_14001A128
0x140019e6e  mov     r12, [rsp+0C8h+NetBufferList]
0x140019e76  jmp     loc_140019DDA
0x140019e7b  mov     rax, [rsp+0C8h+Entry]
0x140019e80  test    rax, rax
0x140019e83  jnz     loc_14001A15E
0x140019e89  mov     r12, [rsp+0C8h+NetBufferList]
0x140019e91  mov     rdx, rsi; Entry
0x140019e94  lea     rcx, [rbp+4C0h]; Lookaside
0x140019e9b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019ea2  nop     dword ptr [rax+rax+00h]
0x140019ea7  jmp     loc_140019DF6
0x140019eac  cmp     byte ptr [rcx+29h], 1
0x140019eb0  jb      loc_140019ABF
0x140019eb6  mov     rcx, [rcx+18h]
0x140019eba  lea     r8, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids
0x140019ec1  mov     edx, 0Ah
0x140019ec6  call    WPP_SF_
0x140019ecb  jmp     loc_140019ABF
0x140019ed0  cmp     [rcx+29h], r15b
0x140019ed4  jb      loc_140019B2D
0x140019eda  mov     r9, [r14]
0x140019edd  lea     r8, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids
0x140019ee4  mov     rcx, [rcx+18h]
0x140019ee8  mov     edx, 0Bh
0x140019eed  mov     rax, [r9+180h]
0x140019ef4  mov     qword ptr [rsp+0C8h+AlignOffset], rax
0x140019ef9  call    WPP_SF_qq
0x140019efe  jmp     loc_140019B2D
0x140019f03  mov     eax, [rcx+2Ch]
0x140019f06  test    al, 20h
0x140019f08  jz      loc_140019E4D
0x140019f0e  cmp     [rcx+29h], r15b
0x140019f12  jb      loc_140019E4D
0x140019f18  mov     rcx, [rcx+18h]
0x140019f1c  lea     r8, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids
0x140019f23  mov     edx, 0Ch
0x140019f28  call    WPP_SF_
0x140019f2d  mov     rcx, [r14]
0x140019f30  call    ReceiveDataComplete
0x140019f35  mov     r12, [rsp+0C8h+NetBufferList]
0x140019f3d  mov     rcx, r12; NetBufferList
0x140019f40  call    cs:__imp_NdisFreeNetBufferList
0x140019f47  nop     dword ptr [rax+rax+00h]
0x140019f4c  jmp     loc_140019E07
0x140019f51  cmp     byte ptr [r10+29h], 2
0x140019f56  jb      loc_140019B9D
0x140019f5c  mov     rcx, [r10+18h]
0x140019f60  lea     r8, WPP_78ecd6a644a13ea942ea320d1e2812df_Traceguids
0x140019f67  mov     edx, 0Dh
0x140019f6c  mov     r9d, r12d
0x140019f6f  call    WPP_SF_d
0x140019f74  movzx   ecx, [rsp+0C8h+arg_0]
0x140019f7c  jmp     loc_140019B9D
0x140019f81  cmp     byte ptr [rcx+29h], 2
0x140019f85  jb      loc_140019BC9
0x140019f8b  mov     rax, [r12+28h]
0x140019f90  test    rax, rax
0x140019f93  jz      short loc_140019F9B
0x140019f95  movzx   r10d, word ptr [rax]
0x140019f99  jmp     short loc_140019F9E
0x140019f9b  xor     r10d, r10d
0x140019f9e  mov     rax, [r12+20h]
0x140019fa3  test    rax, rax
0x140019fa6  jz      short loc_140019FAE
0x140019fa8  movzx   r8d, word ptr [rax]
0x140019fac  jmp     short loc_140019FB1
0x140019fae  xor     r8d, r8d
0x140019fb1  mov     rax, [r12+18h]
0x140019fb6  test    rax, rax
0x140019fb9  jz      short loc_140019FC0
0x140019fbb  movzx   edx, word ptr [rax]
  ... truncated ...
```
