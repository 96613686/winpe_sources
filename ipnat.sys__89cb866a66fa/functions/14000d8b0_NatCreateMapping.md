# NatCreateMapping

- ea: `0x14000d8b0`
- end: `0x14000e372`
- name: `NatCreateMapping`
- size: `2754`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int16, __int64, __int64, PVOID Entry, int, __int64)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x140024cc0`
- `0x14002597c`
- `0x14002665c`
- `0x1400275d0`

## callees

- `0x140001da4`
- `0x140001e78`
- `0x14000218c`
- `0x1400021bc`
- `0x140006374`
- `0x140006a08`
- `0x14000cdac`
- `0x14000ce94`
- `0x14000d66c`
- `0x14000d8b0`
- `0x14000ed8c`
- `0x14000ef60`
- `0x14000fe48`
- `0x1400101b8`
- `0x14002cbc0`

## import_xrefs

- `ntoskrnl!RtlSplay` at `0x14000e077`
- `ntoskrnl!RtlSplay` at `0x14000e1e1`
- `ntoskrnl!RtlSplay` at `0x14000e077`
- `ntoskrnl!RtlSplay` at `0x14000e1e1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000db68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000db7b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dbe9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dbfc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dc57`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dce3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000db68`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000db7b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dbe9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dbfc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dc57`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000dce3`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000da03`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000da03`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dba1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dbc9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dc22`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dc35`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dd01`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dd6b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dba1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dbc9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dc22`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dc35`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dd01`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000dd6b`

## pseudocode

```c
__int64 __fastcall NatCreateMapping(
        unsigned int a1,
        unsigned __int16 *a2,
        int *a3,
        __int64 a4,
        __int64 a5,
        __int16 a6,
        __int64 a7,
        __int64 a8,
        char *Entry,
        unsigned int a10,
        _QWORD *a11)
{
  int v15; // r14d
  char *v16; // r15
  int v18; // esi
  __int128 v19; // xmm0
  int v20; // edi
  __int64 (__fastcall *v21)(); // rax
  __int64 (__fastcall *v22)(); // rcx
  _DWORD *v23; // rax
  int v24; // ebp
  PKDPC BufferChainingDpc; // rbx
  int v26; // esi
  int ProcessorHistory; // r8d
  __int64 (__fastcall *v28)(); // rax
  int v29; // r14d
  unsigned int v30; // ebp
  int v31; // r9d
  int v32; // r10d
  int v33; // ebx
  int v34; // esi
  unsigned int v35; // edi
  int v36; // ecx
  int v37; // r8d
  int v38; // edx
  int v39; // eax
  int v40; // r9d
  int v41; // ecx
  int v42; // eax
  int v43; // r10d
  int v44; // ecx
  PDEVICE_OBJECT v45; // rcx
  __int64 v46; // rdx
  _QWORD *v47; // rbx
  struct _RTL_SPLAY_LINKS **p_LeftChild; // rax
  unsigned __int64 v49; // r9
  unsigned __int64 v50; // r8
  struct _RTL_SPLAY_LINKS *v51; // rcx
  struct _RTL_SPLAY_LINKS *v52; // rax
  PRTL_SPLAY_LINKS v53; // rbx
  _QWORD *v54; // rbx
  struct _RTL_SPLAY_LINKS **v55; // rax
  unsigned __int64 v56; // r9
  unsigned __int64 v57; // r8
  struct _RTL_SPLAY_LINKS *v58; // rcx
  struct _RTL_SPLAY_LINKS *v59; // rax
  PRTL_SPLAY_LINKS v60; // rbx
  _QWORD *v61; // rax
  int v62; // eax
  _QWORD *v63; // [rsp+30h] [rbp-58h] BYREF
  _QWORD *v64; // [rsp+38h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids, a1);
  }
  v15 = 0;
  v63 = 0;
  v64 = 0;
  Entry = 0;
  NatAllocateBlockWithLimitCheck(&MappingLookasideList, (PVOID *)&Entry, 368);
  v16 = Entry;
  if ( !Entry )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
    if ( a4 )
      NatMappingDetachInterface(a4, a5, 0);
    if ( a7 )
      NatMappingDetachDirector(a7, a8, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids, 3221225495LL);
    }
    return 3221225495LL;
  }
  LOBYTE(v18) = 0;
  memset(Entry, 0, 0x170u);
  KeInitializeSpinLock((PKSPIN_LOCK)v16 + 13);
  v19 = *(_OWORD *)a2;
  *((_DWORD *)v16 + 28) = 1;
  *((_DWORD *)v16 + 60) = a1;
  v20 = *((unsigned __int8 *)a2 + 6);
  *((_WORD *)v16 + 142) = a6;
  *((_OWORD *)v16 + 4) = v19;
  LOBYTE(Entry) = v20;
  *((_OWORD *)v16 + 5) = *(_OWORD *)a3;
  *((_DWORD *)v16 + 29) = 5;
  *((_DWORD *)v16 + 30) = 5;
  *((_QWORD *)v16 + 1) = v16;
  *(_QWORD *)v16 = v16;
  *((_QWORD *)v16 + 29) = v16 + 224;
  *((_QWORD *)v16 + 28) = v16 + 224;
  *((_QWORD *)v16 + 25) = v16 + 192;
  *((_QWORD *)v16 + 24) = v16 + 192;
  *((_QWORD *)v16 + 21) = v16 + 160;
  *((_QWORD *)v16 + 20) = v16 + 160;
  *((_QWORD *)v16 + 2) = v16 + 16;
  *((_QWORD *)v16 + 3) = 0;
  *((_QWORD *)v16 + 4) = 0;
  *((_QWORD *)v16 + 5) = v16 + 40;
  *((_QWORD *)v16 + 6) = 0;
  *((_QWORD *)v16 + 7) = 0;
  if ( *(_QWORD *)a3 == *((_QWORD *)a2 + 1) && *(_QWORD *)a2 == *((_QWORD *)a3 + 1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
    v15 = 1;
    if ( (_BYTE)v20 == 6 )
    {
      v21 = NatTranslateReverseTcpNull;
      v22 = NatTranslateForwardTcpNull;
    }
    else
    {
      v21 = NatTranslateReverseUdpNull;
      v22 = NatTranslateForwardUdpNull;
    }
  }
  else if ( (_BYTE)v20 == 6 )
  {
    v21 = NatTranslateReverseTcp;
    v22 = NatTranslateForwardTcp;
  }
  else
  {
    v21 = NatTranslateReverseUdp;
    v22 = NatTranslateForwardUdp;
  }
  *((_QWORD *)v16 + 16) = v22;
  *((_QWORD *)v16 + 17) = v21;
  ++*((_DWORD *)v16 + 28);
  *((_DWORD *)v16 + 90) = -1;
  if ( a4 )
  {
    KeAcquireSpinLockAtDpcLevel(&InterfaceLock);
    KeAcquireSpinLockAtDpcLevel(&InterfaceMappingLock);
    NatMappingAttachInterface(a4, a5, v16);
    KeReleaseSpinLockFromDpcLevel(&InterfaceMappingLock);
    v23 = *(_DWORD **)(a4 + 48);
    v18 = *(_DWORD *)(a4 + 56);
    if ( v23 )
      *((_DWORD *)v16 + 90) = *v23;
    KeReleaseSpinLockFromDpcLevel(&InterfaceLock);
  }
  if ( a7 )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext);
    NatMappingAttachDirector(a7, a8, v16);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
  }
  if ( a4 )
  {
    v24 = a2[2];
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
    BufferChainingDpc = WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
    if ( (PKDPC *)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc != &WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
    {
      v26 = v18 & 4;
      while ( 1 )
      {
        if ( !v26 && !DisablePPTPEditor
          || BufferChainingDpc != (PKDPC)qword_140032138
          && (!v26 && !DisablePPTPEditor || BufferChainingDpc != (PKDPC)qword_1400321B8) )
        {
          ProcessorHistory = BufferChainingDpc->ProcessorHistory;
          if ( ProcessorHistory == (v24 | (v20 << 24)) && (*((_DWORD *)v16 + 60) & 0x20) != 0 )
            break;
          if ( ProcessorHistory == (v24 | (v20 << 24) | 0x10000) )
            break;
        }
        BufferChainingDpc = *(PKDPC *)&BufferChainingDpc->TargetInfoAsUlong;
        if ( BufferChainingDpc == (PKDPC)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc )
          goto LABEL_57;
      }
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
      NatMappingAttachEditor(BufferChainingDpc, v16);
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
      if ( (_BYTE)v20 == 17 )
      {
        *((_QWORD *)v16 + 16) = NatTranslateForwardUdpEdit;
        v28 = NatTranslateReverseUdpEdit;
      }
      else if ( ((__int64)BufferChainingDpc->SystemArgument2 & 1) != 0 )
      {
        *((_QWORD *)v16 + 16) = NatTranslateForwardTcpResize;
        v28 = NatTranslateReverseTcpResize;
      }
      else
      {
        *((_QWORD *)v16 + 16) = NatTranslateForwardTcpEdit;
        v28 = NatTranslateReverseTcpEdit;
      }
      *((_QWORD *)v16 + 17) = v28;
    }
LABEL_57:
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  }
  if ( !v15 )
  {
    v29 = *a3;
    v30 = *a3;
    v31 = a2[4];
    v32 = a2[5];
    v33 = *a2;
    v34 = a2[1];
    a10 = a3[2];
    v35 = HIWORD(a10);
    v30 >>= 16;
    v36 = (unsigned __int16)~(_WORD)a10;
    v37 = a2[6];
    *((_DWORD *)v16 + 61) = HIWORD(a10)
                          + v32
                          + v31
                          + (unsigned __int16)a10
                          + (unsigned __int16)~(_WORD)v30
                          + (unsigned __int16)~(_WORD)v34
                          + (unsigned __int16)~(_WORD)v33
                          + (unsigned __int16)~(_WORD)v29;
    v38 = *((unsigned __int16 *)a3 + 6);
    v39 = (unsigned __int16)~(_WORD)v31;
    v40 = *((unsigned __int16 *)a3 + 2);
    v41 = v39 + v36;
    v42 = (unsigned __int16)~(_WORD)v32;
    v43 = a2[2];
    v44 = (unsigned __int16)~(_WORD)v35 + v42 + v41;
    LOWORD(v42) = ~*((_WORD *)a3 + 2);
    *((_DWORD *)v16 + 62) = v30 + v34 + v33 + (unsigned __int16)v29 + v44;
    *((_DWORD *)v16 + 63) = *((_DWORD *)v16 + 61) + v37 + v38 + (unsigned __int16)~(_WORD)v43 + (unsigned __int16)v42;
    *((_DWORD *)v16 + 64) = *((_DWORD *)v16 + 62)
                          + v43
                          + v40
                          + (unsigned __int16)~(_WORD)v37
                          + (unsigned __int16)~(_WORD)v38;
    if ( v29 == 16777343 || a10 == 16777343 )
      *((_DWORD *)v16 + 60) |= 0x800u;
    LOBYTE(v20) = (_BYTE)Entry;
  }
  if ( NatLookupForwardMapping(*(_QWORD *)a2, *(_QWORD *)a3, &v63) )
  {
    NatCleanupMapping(v16);
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v46 = 16;
LABEL_77:
    WPP_SF_d(v45->AttachedDevice, v46, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids, 3221225473LL);
    return 3221225473LL;
  }
  if ( NatLookupReverseMapping(*((_QWORD *)a2 + 1), *((_QWORD *)a3 + 1), &v64) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
    NatCleanupMapping(v16);
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v46 = 18;
    goto LABEL_77;
  }
  v47 = v63;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  if ( !v47 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
      }
    }
    p_LeftChild = (struct _RTL_SPLAY_LINKS **)v16;
    goto LABEL_113;
  }
  v49 = *((_QWORD *)v16 + 8);
  if ( v49 < v47[8] )
    goto LABEL_96;
  if ( v49 > v47[8] )
    goto LABEL_98;
  v50 = *((_QWORD *)v16 + 10);
  if ( v50 < v47[10] )
  {
LABEL_96:
    v51 = (struct _RTL_SPLAY_LINKS *)(v16 + 16);
    v52 = (struct _RTL_SPLAY_LINKS *)(v47 + 2);
    v47[3] = v16 + 16;
    goto LABEL_99;
  }
  if ( v50 > v47[10] )
  {
LABEL_98:
    v52 = (struct _RTL_SPLAY_LINKS *)(v47 + 2);
    v51 = (struct _RTL_SPLAY_LINKS *)(v16 + 16);
    v47[4] = v16 + 16;
LABEL_99:
    v51->Parent = v52;
    v53 = RtlSplay(v51);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
    p_LeftChild = &v53[-1].LeftChild;
    goto LABEL_113;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_ii(
        WPP_GLOBAL_Control->AttachedDevice,
        39,
        WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids,
        v49,
        *((_QWORD *)v16 + 10));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
  }
  p_LeftChild = 0;
LABEL_113:
  v54 = v64;
  *(_QWORD *)&MappingTree = p_LeftChild;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  if ( v54 )
  {
    v56 = *((_QWORD *)v16 + 9);
    if ( v56 >= v54[9] )
    {
      if ( v56 <= v54[9] )
      {
        v57 = *((_QWORD *)v16 + 11);
        if ( v57 < v54[11] )
          goto LABEL_130;
        if ( v57 <= v54[11] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_ii(
                WPP_GLOBAL_Control->AttachedDevice,
                45,
                WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids,
                v56,
                *((_QWORD *)v16 + 11));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
            }
          }
          v55 = 0;
          goto LABEL_147;
        }
      }
      v59 = (struct _RTL_SPLAY_LINKS *)(v54 + 5);
      v58 = (struct _RTL_SPLAY_LINKS *)(v16 + 40);
      v54[7] = v16 + 40;
LABEL_133:
      v58->Parent = v59;
      v60 = RtlSplay(v58);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
      }
      v55 = &v60[-2].LeftChild;
      goto LABEL_147;
    }
LABEL_130:
    v58 = (struct _RTL_SPLAY_LINKS *)(v16 + 40);
    v59 = (struct _RTL_SPLAY_LINKS *)(v54 + 5);
    v54[6] = v16 + 40;
    goto LABEL_133;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
  }
  v55 = (struct _RTL_SPLAY_LINKS **)v16;
LABEL_147:
  *((_QWORD *)&MappingTree + 1) = v55;
  v61 = (_QWORD *)qword_14003E2A8;
  if ( *(PVOID **)qword_14003E2A8 != &MappingList )
    __fastfail(3u);
  *(_QWORD *)v16 = &MappingList;
  *((_QWORD *)v16 + 1) = v61;
  *v61 = v16;
  qword_14003E2A8 = (__int64)v16;
  _InterlockedAdd(&MappingCount, 1u);
  *a11 = v16;
  v62 = *((_DWORD *)v16 + 60);
  if ( (v62 & 0x400) == 0 )
  {
    if ( (v62 & 0x20) != 0 )
    {
      NatLogConnectionCreation(*(_DWORD *)a2, *a3, a2[2], *((_WORD *)a3 + 2), v20, 1);
    }
    else if ( (v62 & 0x10000) != 0 )
    {
      NatLogConnectionCreation(*((_DWORD *)a2 + 2), a3[2], a2[6], *((_WORD *)a3 + 6), v20, 1);
    }
    else
    {
      NatLogConnectionCreation(*a3, *(_DWORD *)a2, *((_WORD *)a3 + 2), a2[2], v20, 0);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14000d8b0  push    rbx
0x14000d8b2  push    rbp
0x14000d8b3  push    rsi
0x14000d8b4  push    rdi
0x14000d8b5  push    r12
0x14000d8b7  push    r13
0x14000d8b9  push    r14
0x14000d8bb  push    r15
0x14000d8bd  sub     rsp, 48h
0x14000d8c1  mov     rbx, r9
0x14000d8c4  mov     r13, r8
0x14000d8c7  mov     r12, rdx
0x14000d8ca  mov     edi, ecx
0x14000d8cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8d3  lea     rsi, WPP_GLOBAL_Control
0x14000d8da  mov     ebp, 1
0x14000d8df  cmp     rcx, rsi
0x14000d8e2  jz      short loc_14000D908
0x14000d8e4  mov     eax, [rcx+2Ch]
0x14000d8e7  test    bpl, al
0x14000d8ea  jz      short loc_14000D908
0x14000d8ec  cmp     byte ptr [rcx+29h], 6
0x14000d8f0  jb      short loc_14000D908
0x14000d8f2  mov     rcx, [rcx+18h]
0x14000d8f6  lea     edx, [rbp+0Bh]
0x14000d8f9  mov     r9d, edi
0x14000d8fc  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000d903  call    WPP_SF_d
0x14000d908  xor     r14d, r14d
0x14000d90b  lea     rdx, [rsp+88h+Entry]
0x14000d913  mov     r8d, 170h
0x14000d919  mov     [rsp+88h+var_58], r14
0x14000d91e  lea     rcx, MappingLookasideList; Lookaside
0x14000d925  mov     [rsp+88h+var_50], r14
0x14000d92a  mov     [rsp+88h+Entry], r14
0x14000d932  call    NatAllocateBlockWithLimitCheck
0x14000d937  mov     r15, [rsp+88h+Entry]
0x14000d93f  test    r15, r15
0x14000d942  jnz     loc_14000D9EC
0x14000d948  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d94f  cmp     rcx, rsi
0x14000d952  jz      short loc_14000D976
0x14000d954  mov     eax, [rcx+2Ch]
0x14000d957  test    bpl, al
0x14000d95a  jz      short loc_14000D976
0x14000d95c  cmp     byte ptr [rcx+29h], 2
0x14000d960  jb      short loc_14000D976
0x14000d962  mov     rcx, [rcx+18h]
0x14000d966  lea     edx, [r14+0Dh]
0x14000d96a  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000d971  call    WPP_SF_
0x14000d976  test    rbx, rbx
0x14000d979  jz      short loc_14000D98E
0x14000d97b  mov     rdx, [rsp+88h+arg_20]
0x14000d983  xor     r8d, r8d
0x14000d986  mov     rcx, rbx
0x14000d989  call    NatMappingDetachInterface
0x14000d98e  mov     rcx, [rsp+88h+arg_30]
0x14000d996  test    rcx, rcx
0x14000d999  jz      short loc_14000D9AE
0x14000d99b  mov     rdx, [rsp+88h+arg_38]
0x14000d9a3  xor     r9d, r9d
0x14000d9a6  xor     r8d, r8d
0x14000d9a9  call    NatMappingDetachDirector
0x14000d9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9b5  mov     ebx, 0C0000017h
0x14000d9ba  cmp     rcx, rsi
0x14000d9bd  jz      short loc_14000D9E5
0x14000d9bf  mov     edx, [rcx+2Ch]
0x14000d9c2  test    bpl, dl
0x14000d9c5  jz      short loc_14000D9E5
0x14000d9c7  cmp     byte ptr [rcx+29h], 6
0x14000d9cb  jb      short loc_14000D9E5
0x14000d9cd  mov     rcx, [rcx+18h]
0x14000d9d1  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000d9d8  mov     edx, 0Eh
0x14000d9dd  mov     r9d, ebx
0x14000d9e0  call    WPP_SF_d
0x14000d9e5  mov     eax, ebx
0x14000d9e7  jmp     loc_14000E360
0x14000d9ec  xor     edx, edx; Val
0x14000d9ee  mov     r8d, 170h; Size
0x14000d9f4  mov     rcx, r15; void *
0x14000d9f7  mov     esi, r14d
0x14000d9fa  call    memset
0x14000d9ff  lea     rcx, [r15+68h]; SpinLock
0x14000da03  call    cs:__imp_KeInitializeSpinLock
0x14000da0a  nop     dword ptr [rax+rax+00h]
0x14000da0f  movups  xmm0, xmmword ptr [r12]
0x14000da14  movzx   eax, [rsp+88h+arg_28]
0x14000da1c  mov     edx, 5
0x14000da21  mov     [r15+70h], ebp
0x14000da25  mov     [r15+0F0h], edi
0x14000da2c  movzx   edi, byte ptr [r12+6]
0x14000da32  mov     [r15+11Ch], ax
0x14000da3a  lea     rax, [r15+0E0h]
0x14000da41  movups  xmmword ptr [r15+40h], xmm0
0x14000da46  mov     byte ptr [rsp+88h+Entry], dil
0x14000da4e  movups  xmm0, xmmword ptr [r13+0]
0x14000da53  movups  xmmword ptr [r15+50h], xmm0
0x14000da58  mov     [r15+74h], edx
0x14000da5c  mov     [r15+78h], edx
0x14000da60  mov     [r15+8], r15
0x14000da64  mov     [r15], r15
0x14000da67  mov     [rax+8], rax
0x14000da6b  mov     [rax], rax
0x14000da6e  lea     rax, [r15+0C0h]
0x14000da75  mov     [rax+8], rax
0x14000da79  mov     [rax], rax
0x14000da7c  lea     rax, [r15+0A0h]
0x14000da83  mov     [rax+8], rax
0x14000da87  mov     [rax], rax
0x14000da8a  lea     rax, [r15+10h]
0x14000da8e  mov     [rax], rax
0x14000da91  mov     [rax+8], r14
0x14000da95  mov     [rax+10h], r14
0x14000da99  lea     rax, [r15+28h]
0x14000da9d  mov     [rax], rax
0x14000daa0  mov     [rax+8], r14
0x14000daa4  mov     [rax+10h], r14
0x14000daa8  mov     rax, [r12+8]
0x14000daad  cmp     [r13+0], rax
0x14000dab1  jnz     short loc_14000DB1B
0x14000dab3  mov     rax, [r13+8]
0x14000dab7  cmp     [r12], rax
0x14000dabb  jnz     short loc_14000DB1B
0x14000dabd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dac4  lea     rax, WPP_GLOBAL_Control
0x14000dacb  cmp     rcx, rax
0x14000dace  jz      short loc_14000DAF2
0x14000dad0  mov     eax, [rcx+2Ch]
0x14000dad3  test    bpl, al
0x14000dad6  jz      short loc_14000DAF2
0x14000dad8  cmp     [rcx+29h], dl
0x14000dadb  jb      short loc_14000DAF2
0x14000dadd  mov     rcx, [rcx+18h]
0x14000dae1  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000dae8  mov     edx, 0Fh
0x14000daed  call    WPP_SF_
0x14000daf2  mov     r14d, ebp
0x14000daf5  cmp     dil, 6
0x14000daf9  jnz     short loc_14000DB0B
0x14000dafb  lea     rax, NatTranslateReverseTcpNull
0x14000db02  lea     rcx, NatTranslateForwardTcpNull
0x14000db09  jmp     short loc_14000DB3F
0x14000db0b  lea     rax, NatTranslateReverseUdpNull
0x14000db12  lea     rcx, NatTranslateForwardUdpNull
0x14000db19  jmp     short loc_14000DB3F
0x14000db1b  cmp     dil, 6
0x14000db1f  jnz     short loc_14000DB31
0x14000db21  lea     rax, NatTranslateReverseTcp
0x14000db28  lea     rcx, NatTranslateForwardTcp
0x14000db2f  jmp     short loc_14000DB3F
0x14000db31  lea     rax, NatTranslateReverseUdp
0x14000db38  lea     rcx, NatTranslateForwardUdp
0x14000db3f  mov     [r15+80h], rcx
0x14000db46  mov     [r15+88h], rax
0x14000db4d  add     [r15+70h], ebp
0x14000db51  mov     dword ptr [r15+168h], 0FFFFFFFFh
0x14000db5c  test    rbx, rbx
0x14000db5f  jz      short loc_14000DBD5
0x14000db61  lea     rcx, InterfaceLock; SpinLock
0x14000db68  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000db6f  nop     dword ptr [rax+rax+00h]
0x14000db74  lea     rcx, InterfaceMappingLock; SpinLock
0x14000db7b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000db82  nop     dword ptr [rax+rax+00h]
0x14000db87  mov     rdx, [rsp+88h+arg_20]
0x14000db8f  mov     r8, r15
0x14000db92  mov     rcx, rbx
0x14000db95  call    NatMappingAttachInterface
0x14000db9a  lea     rcx, InterfaceMappingLock; SpinLock
0x14000dba1  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000dba8  nop     dword ptr [rax+rax+00h]
0x14000dbad  mov     rax, [rbx+30h]
0x14000dbb1  mov     esi, [rbx+38h]
0x14000dbb4  test    rax, rax
0x14000dbb7  jz      short loc_14000DBC2
0x14000dbb9  mov     eax, [rax]
0x14000dbbb  mov     [r15+168h], eax
0x14000dbc2  lea     rcx, InterfaceLock; SpinLock
0x14000dbc9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000dbd0  nop     dword ptr [rax+rax+00h]
0x14000dbd5  mov     rbp, [rsp+88h+arg_30]
0x14000dbdd  test    rbp, rbp
0x14000dbe0  jz      short loc_14000DC41
0x14000dbe2  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x14000dbe9  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000dbf0  nop     dword ptr [rax+rax+00h]
0x14000dbf5  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x14000dbfc  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000dc03  nop     dword ptr [rax+rax+00h]
0x14000dc08  mov     rdx, [rsp+88h+arg_38]
0x14000dc10  mov     r8, r15
0x14000dc13  mov     rcx, rbp
0x14000dc16  call    NatMappingAttachDirector
0x14000dc1b  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x14000dc22  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000dc29  nop     dword ptr [rax+rax+00h]
0x14000dc2e  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x14000dc35  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000dc3c  nop     dword ptr [rax+rax+00h]
0x14000dc41  test    rbx, rbx
0x14000dc44  jz      loc_14000DD77
0x14000dc4a  movzx   ebp, word ptr [r12+4]
0x14000dc50  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000dc57  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000dc5e  nop     dword ptr [rax+rax+00h]
0x14000dc63  mov     rbx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14000dc6a  lea     r9, WPP_MAIN_CB.Queue+40h
0x14000dc71  cmp     rbx, r9
0x14000dc74  jz      loc_14000DD64
0x14000dc7a  mov     ecx, edi
0x14000dc7c  shl     ecx, 18h
0x14000dc7f  or      ecx, ebp
0x14000dc81  mov     edx, ecx
0x14000dc83  bts     edx, 10h
0x14000dc87  and     esi, 4
0x14000dc8a  test    esi, esi
0x14000dc8c  jnz     short loc_14000DC97
0x14000dc8e  cmp     cs:DisablePPTPEditor, sil
0x14000dc95  jz      short loc_14000DCB6
0x14000dc97  cmp     rbx, cs:qword_140032138
0x14000dc9e  jz      short loc_14000DCCF
0x14000dca0  test    esi, esi
0x14000dca2  jnz     short loc_14000DCAD
0x14000dca4  cmp     cs:DisablePPTPEditor, sil
0x14000dcab  jz      short loc_14000DCB6
0x14000dcad  cmp     rbx, cs:qword_1400321B8
0x14000dcb4  jz      short loc_14000DCCF
0x14000dcb6  mov     r8d, [rbx+10h]
0x14000dcba  cmp     r8d, ecx
0x14000dcbd  jnz     short loc_14000DCCA
0x14000dcbf  mov     eax, [r15+0F0h]
0x14000dcc6  test    al, 20h
0x14000dcc8  jnz     short loc_14000DCDC
0x14000dcca  cmp     r8d, edx
0x14000dccd  jz      short loc_14000DCDC
0x14000dccf  mov     rbx, [rbx]
0x14000dcd2  cmp     rbx, r9
0x14000dcd5  jnz     short loc_14000DC8A
0x14000dcd7  jmp     loc_14000DD64
0x14000dcdc  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; SpinLock
0x14000dce3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000dcea  nop     dword ptr [rax+rax+00h]
0x14000dcef  mov     rdx, r15
0x14000dcf2  mov     rcx, rbx
0x14000dcf5  call    NatMappingAttachEditor
0x14000dcfa  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; SpinLock
0x14000dd01  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000dd08  nop     dword ptr [rax+rax+00h]
0x14000dd0d  cmp     dil, 11h
0x14000dd11  jnz     short loc_14000DD2A
0x14000dd13  lea     rax, NatTranslateForwardUdpEdit
0x14000dd1a  mov     [r15+80h], rax
0x14000dd21  lea     rax, NatTranslateReverseUdpEdit
0x14000dd28  jmp     short loc_14000DD5D
0x14000dd2a  mov     eax, [rbx+30h]
0x14000dd2d  test    al, 1
0x14000dd2f  jnz     short loc_14000DD48
0x14000dd31  lea     rax, NatTranslateForwardTcpEdit
0x14000dd38  mov     [r15+80h], rax
0x14000dd3f  lea     rax, NatTranslateReverseTcpEdit
0x14000dd46  jmp     short loc_14000DD5D
0x14000dd48  lea     rax, NatTranslateForwardTcpResize
0x14000dd4f  mov     [r15+80h], rax
0x14000dd56  lea     rax, NatTranslateReverseTcpResize
0x14000dd5d  mov     [r15+88h], rax
0x14000dd64  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000dd6b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000dd72  nop     dword ptr [rax+rax+00h]
0x14000dd77  test    r14d, r14d
0x14000dd7a  jnz     loc_14000DEB2
0x14000dd80  mov     r14d, [r13+0]
0x14000dd84  mov     ebp, r14d
0x14000dd87  movzx   r8d, word ptr [r13+8]
0x14000dd8c  movzx   r9d, word ptr [r12+8]
0x14000dd92  mov     eax, [r13+8]
0x14000dd96  movzx   r10d, word ptr [r12+0Ah]
0x14000dd9c  movzx   ebx, word ptr [r12]
0x14000dda1  movzx   esi, word ptr [r12+2]
0x14000dda7  mov     [rsp+88h+arg_48], eax
0x14000ddae  shr     eax, 10h
0x14000ddb1  mov     edi, eax
0x14000ddb3  shr     ebp, 10h
0x14000ddb6  movzx   r11d, r14w
0x14000ddba  movzx   eax, r11w
0x14000ddbe  not     ax
0x14000ddc1  movzx   edx, ax
0x14000ddc4  movzx   eax, bx
0x14000ddc7  not     ax
0x14000ddca  movzx   eax, ax
0x14000ddcd  add     edx, eax
0x14000ddcf  movzx   eax, si
0x14000ddd2  not     ax
0x14000ddd5  movzx   ecx, ax
0x14000ddd8  movzx   eax, bp
0x14000dddb  add     edx, ecx
0x14000dddd  not     ax
0x14000dde0  movzx   ecx, ax
  ... truncated ...
```
