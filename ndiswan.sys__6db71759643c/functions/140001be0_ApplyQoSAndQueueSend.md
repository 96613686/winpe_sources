# ApplyQoSAndQueueSend

- ea: `0x140001be0`
- end: `0x14000252a`
- name: `ApplyQoSAndQueueSend`
- size: `2378`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1400019a0`
- `0x14000ce70`

## callees

- `0x140001be0`
- `0x140002530`
- `0x140002974`
- `0x1400035f0`
- `0x140003870`
- `0x140005494`
- `0x1400084d8`
- `0x140008e5c`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a648`
- `0x14000a68c`
- `0x14000a744`
- `0x14000bdb0`
- `0x14000ed38`
- `0x140010ff8`
- `0x140011bd4`
- `0x140011c4c`
- `0x1400161f0`
- `0x14002e898`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002067`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002067`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400020c3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000214a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400020c3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000214a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001f14`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000246b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001e95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001f14`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400023a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000246b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d60`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001eee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000230a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002375`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d60`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001eee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000230a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002375`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400024ac`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400024ac`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400024d6`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x1400024d6`
- `NDIS!NdisFreeNetBufferListContext` at `0x140002486`
- `NDIS!NdisFreeNetBufferListContext` at `0x140002486`
- `NDIS!NdisGetDataBuffer` at `0x140001c7d`
- `NDIS!NdisGetDataBuffer` at `0x140001c7d`
- `NDIS!NdisAcquireRWLockRead` at `0x140001cfb`
- `NDIS!NdisAcquireRWLockRead` at `0x140001cfb`
- `NDIS!NdisReleaseRWLock` at `0x140001d33`
- `NDIS!NdisReleaseRWLock` at `0x14000204f`
- `NDIS!NdisReleaseRWLock` at `0x1400020db`
- `NDIS!NdisReleaseRWLock` at `0x14000216a`
- `NDIS!NdisReleaseRWLock` at `0x140001d33`
- `NDIS!NdisReleaseRWLock` at `0x14000204f`
- `NDIS!NdisReleaseRWLock` at `0x1400020db`
- `NDIS!NdisReleaseRWLock` at `0x14000216a`

## pseudocode

```c
void __fastcall ApplyQoSAndQueueSend(__int64 a1, struct _NET_BUFFER_LIST *a2)
{
  __int64 v2; // rdi
  _QWORD *v5; // rbp
  struct _NET_BUFFER *FirstNetBuffer; // rcx
  __int64 v7; // r13
  char *DataBuffer; // rax
  __int64 v9; // rdx
  unsigned __int8 *v10; // rbx
  __int64 v11; // rsi
  __int64 v12; // rax
  unsigned __int64 v13; // rbx
  __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rbx
  volatile signed __int32 *v19; // rcx
  int v20; // r8d
  _QWORD *v21; // rbx
  KIRQL v22; // al
  bool v23; // zf
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r13
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  _QWORD *v30; // rax
  _QWORD *v31; // r13
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r14
  __int64 v35; // r15
  __int64 v36; // rbp
  KIRQL v37; // al
  __int64 LockState; // [rsp+40h] [rbp-78h] BYREF
  __int64 v39; // [rsp+48h] [rbp-70h]
  PNET_BUFFER_LIST NetBufferList; // [rsp+50h] [rbp-68h] BYREF
  _QWORD *v41; // [rsp+58h] [rbp-60h] BYREF
  __int64 v42; // [rsp+60h] [rbp-58h]
  _BYTE Storage[16]; // [rsp+68h] [rbp-50h] BYREF

  v2 = 0;
  LockState = 0;
  v41 = 0;
  NetBufferList = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
  }
  _InterlockedIncrement(&glSendCount);
  v5 = (PNET_BUFFER_LIST_CONTEXT *)((char *)&a2->Context->Next + a2->Context->Offset);
  FirstNetBuffer = a2->FirstNetBuffer;
  v7 = v5[11];
  v39 = v7;
  DataBuffer = (char *)NdisGetDataBuffer(FirstNetBuffer, 0xEu, Storage, 1u, 0);
  v10 = (unsigned __int8 *)DataBuffer;
  if ( !DataBuffer )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      goto LABEL_107;
    }
    v25 = 22;
LABEL_39:
    WPP_SF_(v24->AttachedDevice, v25, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
LABEL_107:
    NdisFreeNetBufferListContext(a2, 0x80u);
    a2->Status = 0;
    if ( v7 )
    {
      NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(v7 + 40), a2, 0);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 24), 0xFFFFFFFF) == 1 )
        DoDerefCmVcCBWork(v7);
    }
    else
    {
      NdisMSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), a2, 0);
    }
    _InterlockedIncrement(&glSendCompleteCount);
    goto LABEL_21;
  }
  if ( *(_DWORD *)(DataBuffer + 2) == *((_DWORD *)DataBuffer + 2) && *(_WORD *)DataBuffer == *((_WORD *)DataBuffer + 3) )
  {
    NdisWanIndicateLoopbackPacket(a1, a2);
    goto LABEL_107;
  }
  if ( (*DataBuffer & 1) != 0 )
    NdisWanIndicateLoopbackPacket(a1, a2);
  if ( a1 == qword_14001E2D8 )
    goto LABEL_107;
  v11 = v10[3];
  v12 = v10[4];
  v13 = v10[5];
  v14 = v12 | (v11 << 8);
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v15 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v15 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  if ( v15 )
  {
    LOWORD(LockState) = 0;
    BYTE2(LockState) = 0;
    NdisAcquireRWLockRead(ConnTableLock, (PLOCK_STATE_EX)&LockState, 0);
    if ( (unsigned int)v14 > *((_DWORD *)ConnectionTable + 1) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids, v14);
      }
      NdisReleaseRWLock(ConnTableLock, (PLOCK_STATE_EX)&LockState);
      goto LABEL_58;
    }
    _mm_lfence();
    v26 = *(_QWORD *)(*((_QWORD *)ConnectionTable + 8) + 8LL * (unsigned int)v14);
    if ( !v26 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids, v14);
      }
      NdisReleaseRWLock(ConnTableLock, (PLOCK_STATE_EX)&LockState);
LABEL_57:
      v7 = v39;
LABEL_58:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_DqDq(
          WPP_GLOBAL_Control->AttachedDevice,
          v16,
          v17,
          (unsigned int)v14,
          a1,
          *(unsigned __int16 *)(a1 + 132),
          a2);
      }
      goto LABEL_107;
    }
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v26 + 1768));
    v27 = *(unsigned int *)(v26 + 20);
    if ( (_DWORD)v27 != 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 19, v27, v26, v14, *(_DWORD *)(v26 + 20));
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v26 + 1768));
      NdisReleaseRWLock(ConnTableLock, (PLOCK_STATE_EX)&LockState);
      goto LABEL_57;
    }
    ++*(_DWORD *)(v26 + 24);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v26 + 1768));
    v2 = v26;
    v42 = v26;
    NdisReleaseRWLock(ConnTableLock, (PLOCK_STATE_EX)&LockState);
    v7 = v39;
  }
  else
  {
    LOBYTE(v9) = 1;
    if ( !(unsigned __int8)IsBundleValid(v14, v9, &LockState) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            24,
            WPP_8149dd890ba53a7fe788edfac8207806_Traceguids,
            (unsigned int)v14);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qDq(WPP_GLOBAL_Control->AttachedDevice, v28, v29, a1, *(unsigned __int16 *)(a1 + 132), a2);
        }
      }
      v2 = LockState;
      goto LABEL_107;
    }
    v2 = LockState;
    v42 = LockState;
  }
  if ( !*(_BYTE *)(v2 + 1784) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_107;
    }
    v25 = 26;
    goto LABEL_39;
  }
  *(_BYTE *)(v2 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 1768));
  if ( v13 >= 0x20 )
  {
    v18 = 0;
    goto LABEL_102;
  }
  _mm_lfence();
  v18 = *(_QWORD *)(*(_QWORD *)(v2 + 264) + 8 * v13);
  if ( (unsigned __int64)(v18 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_102:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_8149dd890ba53a7fe788edfac8207806_Traceguids,
        v18,
        a1,
        *(unsigned __int16 *)(a1 + 132));
    }
    goto LABEL_106;
  }
  if ( *(_DWORD *)(v18 + 20) != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          WPP_8149dd890ba53a7fe788edfac8207806_Traceguids,
          v18,
          *(_DWORD *)(v18 + 20));
      }
    }
LABEL_106:
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 1768), *(_BYTE *)(v2 + 1776));
    goto LABEL_107;
  }
  v5[9] = v2;
  v5[8] = v18;
  v5[10] = a1;
  v19 = *(volatile signed __int32 **)(v2 + 2448);
  if ( v19 && _InterlockedCompareExchange(v19, 1, 1) == 1 && *(_QWORD *)(*(_QWORD *)(v2 + 2448) + 16LL) )
  {
    ++*(_DWORD *)(v2 + 24);
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 24));
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 24));
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 1768), *(_BYTE *)(v2 + 1776));
    BwcSendNbls(
      *(_QWORD *)(*(_QWORD *)(v2 + 2448) + 16LL),
      (_DWORD)a2,
      v20,
      (unsigned int)&v41,
      (__int64)&NetBufferList);
    DropQoSSendNetBufferList(NetBufferList);
    v21 = v41;
    if ( v41 )
    {
      do
      {
        v30 = v21;
        v31 = v21;
        v21 = (_QWORD *)*v21;
        v32 = v31[2];
        *v30 = 0;
        v33 = *(unsigned __int16 *)(v32 + 10);
        v34 = *(_QWORD *)(v33 + v32 + 72);
        v35 = *(_QWORD *)(v33 + v32 + 64);
        v36 = *(_QWORD *)(v33 + v32 + 88);
        *(_BYTE *)(v34 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v34 + 1768));
        _InterlockedIncrement((volatile signed __int32 *)(v35 + 24));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids, v35, v31);
        }
        _InterlockedIncrement((volatile signed __int32 *)(v35 + 104));
        NdisWanQueueSend(v31);
        DereferenceRefCount(v35 + 24);
        v37 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v34 + 1768));
        v23 = (*(_DWORD *)(v34 + 24))-- == 1;
        *(_BYTE *)(v34 + 1776) = v37;
        if ( v23 )
          DoDerefBundleCBWork((PVOID)v34);
        else
          KeReleaseSpinLock((PKSPIN_LOCK)(v34 + 1768), v37);
        if ( v36 && _InterlockedExchangeAdd((volatile signed __int32 *)(v36 + 24), 0xFFFFFFFF) == 1 )
          DoDerefCmVcCBWork(v36);
      }
      while ( v21 );
      v2 = v42;
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 24));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids, v18, a2);
    }
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 104));
    NdisWanQueueSend(a2);
  }
LABEL_21:
  if ( v2 )
  {
    v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 1768));
    *(_BYTE *)(v2 + 1776) = v22;
    v23 = (*(_DWORD *)(v2 + 24))-- == 1;
    if ( v23 )
      DoDerefBundleCBWork((PVOID)v2);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 1768), v22);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
  }
}

```

## disassembly

```asm
0x140001be0  mov     r11, rsp
0x140001be3  sub     rsp, 0B8h
0x140001bea  mov     rax, cs:__security_cookie
0x140001bf1  xor     rax, rsp
0x140001bf4  mov     [rsp+0B8h+var_40], rax
0x140001bf9  mov     [r11+18h], rbx
0x140001bfd  xor     ebx, ebx
0x140001bff  mov     [r11-8], rbp
0x140001c03  mov     [r11-18h], rdi
0x140001c07  mov     edi, ebx
0x140001c09  mov     [r11-20h], r12
0x140001c0d  mov     [r11-28h], r13
0x140001c11  mov     [r11-30h], r14
0x140001c15  mov     r14, rdx
0x140001c18  mov     [r11-38h], r15
0x140001c1c  mov     r15, rcx
0x140001c1f  mov     [r11-78h], rbx
0x140001c23  mov     [r11-60h], rbx
0x140001c27  mov     [r11-68h], rbx
0x140001c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c32  lea     r12, WPP_GLOBAL_Control
0x140001c39  cmp     rcx, r12
0x140001c3c  jnz     loc_140001F25
0x140001c42  mov     [rsp+0B8h+var_10], rsi
0x140001c4a  lock inc cs:glSendCount
0x140001c51  mov     rcx, [r14+10h]
0x140001c55  lea     r8, [rsp+0B8h+Storage]; Storage
0x140001c5a  mov     r9d, 1; AlignMultiple
0x140001c60  mov     [rsp+0B8h+AlignOffset], ebx; AlignOffset
0x140001c64  mov     edx, 0Eh; BytesNeeded
0x140001c69  movzx   ebp, word ptr [rcx+0Ah]
0x140001c6d  add     rbp, rcx
0x140001c70  mov     rcx, [r14+8]; NetBuffer
0x140001c74  mov     r13, [rbp+58h]
0x140001c78  mov     [rsp+0B8h+var_70], r13
0x140001c7d  call    cs:__imp_NdisGetDataBuffer
0x140001c84  nop     dword ptr [rax+rax+00h]
0x140001c89  mov     rbx, rax
0x140001c8c  test    rax, rax
0x140001c8f  jz      loc_140001F54
0x140001c95  mov     eax, [rax+8]
0x140001c98  cmp     [rbx+2], eax
0x140001c9b  jz      loc_140001F9A
0x140001ca1  test    byte ptr [rbx], 1
0x140001ca4  jnz     loc_140001FB7
0x140001caa  cmp     r15, cs:qword_14001E2D8
0x140001cb1  jz      loc_14000247E
0x140001cb7  movzx   esi, byte ptr [rbx+3]
0x140001cbb  movzx   eax, byte ptr [rbx+4]
0x140001cbf  movzx   ebx, byte ptr [rbx+5]
0x140001cc3  shl     rsi, 8
0x140001cc7  or      rsi, rax
0x140001cca  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x140001cd0  test    al, 10h
0x140001cd2  jnz     short loc_140001D44
0x140001cd4  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x140001cd9  test    eax, eax
0x140001cdb  jz      loc_140002187
0x140001ce1  mov     rcx, cs:ConnTableLock; Lock
0x140001ce8  lea     rdx, [rsp+0B8h+LockState]; LockState
0x140001ced  xor     eax, eax
0x140001cef  xor     r8d, r8d; Flags
0x140001cf2  mov     word ptr [rsp+0B8h+LockState], ax
0x140001cf7  mov     byte ptr [rsp+0B8h+LockState+2], al
0x140001cfb  call    cs:__imp_NdisAcquireRWLockRead
0x140001d02  nop     dword ptr [rax+rax+00h]
0x140001d07  mov     rax, cs:ConnectionTable
0x140001d0e  cmp     esi, [rax+4]
0x140001d11  jbe     loc_140001FF9
0x140001d17  mov     rcx, cs:WPP_GLOBAL_Control
0x140001d1e  cmp     rcx, r12
0x140001d21  jnz     loc_140001FC7
0x140001d27  mov     rcx, cs:ConnTableLock; Lock
0x140001d2e  lea     rdx, [rsp+0B8h+LockState]; LockState
0x140001d33  call    cs:__imp_NdisReleaseRWLock
0x140001d3a  nop     dword ptr [rax+rax+00h]
0x140001d3f  jmp     loc_1400020F3
0x140001d44  and     eax, 1
0x140001d47  jmp     short loc_140001CD9
0x140001d49  cmp     byte ptr [rdi+6F8h], 0
0x140001d50  jz      loc_14000221A
0x140001d56  lea     rcx, [rdi+6E8h]; SpinLock
0x140001d5d  mov     rsi, rbx
0x140001d60  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d67  nop     dword ptr [rax+rax+00h]
0x140001d6c  mov     [rdi+6F0h], al
0x140001d72  cmp     rbx, 20h ; ' '
0x140001d76  jnb     loc_140002412
0x140001d7c  lfence
0x140001d7f  mov     rbx, [rdi+108h]
0x140001d86  mov     rbx, [rbx+rsi*8]
0x140001d8a  lea     rax, [rbx-1]
0x140001d8e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001d92  ja      loc_140002414
0x140001d98  cmp     dword ptr [rbx+14h], 3
0x140001d9c  jnz     loc_140002244
0x140001da2  mov     [rbp+48h], rdi
0x140001da6  mov     [rbp+40h], rbx
0x140001daa  mov     [rbp+50h], r15
0x140001dae  mov     rcx, [rdi+990h]
0x140001db5  test    rcx, rcx
0x140001db8  jnz     loc_140001E54
0x140001dbe  lock inc dword ptr [rbx+18h]
0x140001dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140001dc9  lea     r12, WPP_GLOBAL_Control
0x140001dd0  cmp     rcx, r12
0x140001dd3  jnz     loc_1400023DB
0x140001dd9  lock inc dword ptr [rbx+68h]
0x140001ddd  mov     rcx, r14
0x140001de0  call    NdisWanQueueSend
0x140001de5  mov     r15, [rsp+0B8h+var_38]
0x140001ded  mov     r14, [rsp+0B8h+var_30]
0x140001df5  mov     r13, [rsp+0B8h+var_28]
0x140001dfd  mov     rsi, [rsp+0B8h+var_10]
0x140001e05  mov     rbp, [rsp+0B8h+var_8]
0x140001e0d  test    rdi, rdi
0x140001e10  jnz     loc_140001EE7
0x140001e16  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e1d  mov     rdi, [rsp+0B8h+var_18]
0x140001e25  cmp     rcx, r12
0x140001e28  mov     r12, [rsp+0B8h+var_20]
0x140001e30  mov     rbx, [rsp+0B8h+arg_10]
0x140001e38  jnz     loc_1400024FB
0x140001e3e  mov     rcx, [rsp+0B8h+var_40]
0x140001e43  xor     rcx, rsp; StackCookie
0x140001e46  call    __security_check_cookie
0x140001e4b  add     rsp, 0B8h
0x140001e52  retn
0x140001e54  mov     edx, 1
0x140001e59  mov     eax, edx
0x140001e5b  lock cmpxchg [rcx], edx
0x140001e5f  jnz     loc_140001DBE
0x140001e65  mov     rax, [rdi+990h]
0x140001e6c  cmp     qword ptr [rax+10h], 0
0x140001e71  jz      loc_140001DBE
0x140001e77  inc     dword ptr [rdi+18h]
0x140001e7a  lock inc dword ptr [rbx+18h]
0x140001e7e  test    r13, r13
0x140001e81  jnz     loc_1400022C6
0x140001e87  movzx   edx, byte ptr [rdi+6F0h]; NewIrql
0x140001e8e  lea     rcx, [rdi+6E8h]; SpinLock
0x140001e95  call    cs:__imp_KeReleaseSpinLock
0x140001e9c  nop     dword ptr [rax+rax+00h]
0x140001ea1  mov     rcx, [rdi+990h]
0x140001ea8  lea     rax, [rsp+0B8h+NetBufferList]
0x140001ead  lea     r9, [rsp+0B8h+var_60]
0x140001eb2  mov     qword ptr [rsp+0B8h+AlignOffset], rax
0x140001eb7  mov     rdx, r14
0x140001eba  mov     rcx, [rcx+10h]
0x140001ebe  call    BwcSendNbls
0x140001ec3  mov     rcx, [rsp+0B8h+NetBufferList]; NetBufferList
0x140001ec8  call    DropQoSSendNetBufferList
0x140001ecd  mov     rbx, [rsp+0B8h+var_60]
0x140001ed2  test    rbx, rbx
0x140001ed5  jnz     loc_1400022D0
0x140001edb  lea     r12, WPP_GLOBAL_Control
0x140001ee2  jmp     loc_140001DE5
0x140001ee7  lea     rcx, [rdi+6E8h]; SpinLock
0x140001eee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001ef5  nop     dword ptr [rax+rax+00h]
0x140001efa  mov     [rdi+6F0h], al
0x140001f00  add     dword ptr [rdi+18h], 0FFFFFFFFh
0x140001f04  jz      loc_1400024EE
0x140001f0a  movzx   edx, al; NewIrql
0x140001f0d  lea     rcx, [rdi+6E8h]; SpinLock
0x140001f14  call    cs:__imp_KeReleaseSpinLock
0x140001f1b  nop     dword ptr [rax+rax+00h]
0x140001f20  jmp     loc_140001E16
0x140001f25  mov     eax, [rcx+2Ch]
0x140001f28  test    al, 8
0x140001f2a  jz      loc_140001C42
0x140001f30  cmp     byte ptr [rcx+29h], 5
0x140001f34  jb      loc_140001C42
0x140001f3a  mov     rcx, [rcx+18h]
0x140001f3e  lea     r8, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids
0x140001f45  mov     edx, 15h
0x140001f4a  call    WPP_SF_
0x140001f4f  jmp     loc_140001C42
0x140001f54  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f5b  cmp     rcx, r12
0x140001f5e  jz      loc_14000247E
0x140001f64  mov     eax, [rcx+2Ch]
0x140001f67  test    al, 8
0x140001f69  jz      loc_14000247E
0x140001f6f  cmp     byte ptr [rcx+29h], 3
0x140001f73  jb      loc_14000247E
0x140001f79  mov     edx, 16h
0x140001f7e  jmp     short loc_140001F85
0x140001f80  mov     edx, 1Ah
0x140001f85  mov     rcx, [rcx+18h]
0x140001f89  lea     r8, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids
0x140001f90  call    WPP_SF_
0x140001f95  jmp     loc_14000247E
0x140001f9a  movzx   eax, word ptr [rbx+6]
0x140001f9e  cmp     [rbx], ax
0x140001fa1  jnz     loc_140001CA1
0x140001fa7  mov     rdx, r14
0x140001faa  mov     rcx, r15
0x140001fad  call    NdisWanIndicateLoopbackPacket
0x140001fb2  jmp     loc_14000247E
0x140001fb7  mov     rdx, r14
0x140001fba  mov     rcx, r15
0x140001fbd  call    NdisWanIndicateLoopbackPacket
0x140001fc2  jmp     loc_140001CAA
0x140001fc7  mov     eax, [rcx+2Ch]
0x140001fca  test    al, 8
0x140001fcc  jz      loc_140001D27
0x140001fd2  cmp     byte ptr [rcx+29h], 4
0x140001fd6  jb      loc_140001D27
0x140001fdc  mov     rcx, [rcx+18h]
0x140001fe0  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x140001fe7  mov     edx, 11h
0x140001fec  mov     r9, rsi
0x140001fef  call    WPP_SF_q
0x140001ff4  jmp     loc_140001D27
0x140001ff9  lfence
0x140001ffc  mov     rax, cs:ConnectionTable
0x140002003  mov     edx, esi
0x140002005  mov     rcx, [rax+40h]
0x140002009  mov     r13, [rcx+rdx*8]
0x14000200d  test    r13, r13
0x140002010  jnz     short loc_140002060
0x140002012  mov     rcx, cs:WPP_GLOBAL_Control
0x140002019  cmp     rcx, r12
0x14000201c  jz      short loc_140002043
0x14000201e  mov     eax, [rcx+2Ch]
0x140002021  test    al, 8
0x140002023  jz      short loc_140002043
0x140002025  cmp     byte ptr [rcx+29h], 4
0x140002029  jb      short loc_140002043
0x14000202b  mov     rcx, [rcx+18h]
0x14000202f  lea     r8, WPP_bb51234ffcee333b063474a2b6c2f0ff_Traceguids
0x140002036  mov     edx, 12h
0x14000203b  mov     r9, rsi
0x14000203e  call    WPP_SF_q
0x140002043  mov     rcx, cs:ConnTableLock; Lock
0x14000204a  lea     rdx, [rsp+0B8h+LockState]; LockState
0x14000204f  call    cs:__imp_NdisReleaseRWLock
0x140002056  nop     dword ptr [rax+rax+00h]
0x14000205b  jmp     loc_1400020EE
0x140002060  lea     rcx, [r13+6E8h]; SpinLock
0x140002067  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000206e  nop     dword ptr [rax+rax+00h]
0x140002073  mov     r8d, [r13+14h]
0x140002077  cmp     r8d, 2
0x14000207b  jz      loc_14000213F
0x140002081  mov     rcx, cs:WPP_GLOBAL_Control
0x140002088  lea     rax, WPP_GLOBAL_Control
0x14000208f  cmp     rcx, rax
0x140002092  jz      short loc_1400020BC
0x140002094  mov     eax, [rcx+2Ch]
0x140002097  test    al, 8
0x140002099  jz      short loc_1400020BC
0x14000209b  cmp     byte ptr [rcx+29h], 4
0x14000209f  jb      short loc_1400020BC
0x1400020a1  mov     rcx, [rcx+18h]
0x1400020a5  mov     edx, 13h
0x1400020aa  mov     dword ptr [rsp+0B8h+var_90], r8d
0x1400020af  mov     r9, r13
0x1400020b2  mov     qword ptr [rsp+0B8h+AlignOffset], rsi
0x1400020b7  call    WPP_SF_qqd
0x1400020bc  lea     rcx, [r13+6E8h]; SpinLock
0x1400020c3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400020ca  nop     dword ptr [rax+rax+00h]
0x1400020cf  mov     rcx, cs:ConnTableLock; Lock
0x1400020d6  lea     rdx, [rsp+0B8h+LockState]; LockState
0x1400020db  call    cs:__imp_NdisReleaseRWLock
0x1400020e2  nop     dword ptr [rax+rax+00h]
0x1400020e7  lea     r12, WPP_GLOBAL_Control
0x1400020ee  mov     r13, [rsp+0B8h+var_70]
0x1400020f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020fa  cmp     rcx, r12
0x1400020fd  jz      loc_14000247E
0x140002103  mov     eax, [rcx+2Ch]
0x140002106  test    al, 8
0x140002108  jz      loc_14000247E
0x14000210e  cmp     byte ptr [rcx+29h], 3
0x140002112  jb      loc_14000247E
0x140002118  movzx   eax, word ptr [r15+84h]
0x140002120  mov     r9d, esi
0x140002123  mov     rcx, [rcx+18h]
0x140002127  mov     [rsp+0B8h+var_88], r14
0x14000212c  mov     dword ptr [rsp+0B8h+var_90], eax
0x140002130  mov     qword ptr [rsp+0B8h+AlignOffset], r15
0x140002135  call    WPP_SF_DqDq
0x14000213a  jmp     loc_14000247E
0x14000213f  inc     dword ptr [r13+18h]
0x140002143  lea     rcx, [r13+6E8h]; SpinLock
0x14000214a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002151  nop     dword ptr [rax+rax+00h]
0x140002156  mov     rcx, cs:ConnTableLock; Lock
0x14000215d  lea     rdx, [rsp+0B8h+LockState]; LockState
0x140002162  mov     rdi, r13
0x140002165  mov     [rsp+0B8h+var_58], r13
0x14000216a  call    cs:__imp_NdisReleaseRWLock
0x140002171  nop     dword ptr [rax+rax+00h]
0x140002176  mov     r13, [rsp+0B8h+var_70]
0x14000217b  lea     r12, WPP_GLOBAL_Control
0x140002182  jmp     loc_140001D49
0x140002187  lea     r8, [rsp+0B8h+LockState]
  ... truncated ...
```
