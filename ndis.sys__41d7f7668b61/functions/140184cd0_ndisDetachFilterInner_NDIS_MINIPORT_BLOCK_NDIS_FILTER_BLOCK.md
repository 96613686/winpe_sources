# ndisDetachFilterInner(_NDIS_MINIPORT_BLOCK *,_NDIS_FILTER_BLOCK *)

- ea: `0x140184cd0`
- end: `0x1401851fd`
- name: `?ndisDetachFilterInner@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_FILTER_BLOCK@@@Z`
- size: `1325`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, _NDIS_FILTER_BLOCK *this)`
- caller_count: `1`
- callee_count: `30`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14015dc10`

## callees

- `0x14000d4c0`
- `0x140010d20`
- `0x1400110b0`
- `0x14002ab60`
- `0x14003d970`
- `0x1400400d0`
- `0x1400509b0`
- `0x140053280`
- `0x140057b80`
- `0x140057cf0`
- `0x140058390`
- `0x14005b320`
- `0x14005c080`
- `0x14005e8b0`
- `0x14006ade0`
- `0x14006b6d0`
- `0x140075670`
- `0x140077b30`
- `0x14007adf0`
- `0x14007ba60`
- `0x14007dfd0`
- `0x14008cdf0`
- `0x140092d80`
- `0x140096840`
- `0x1400eb4c0`
- `0x14015c310`
- `0x14015c980`
- `0x14016e140`
- `0x14016fa80`
- `0x140184cd0`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x140184e31`
- `ntoskrnl!IoWMIWriteEvent` at `0x140184e31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184ea0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140184ea0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140184edf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401850c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140184edf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401850c7`

## pseudocode

```c
void __fastcall ndisDetachFilterInner(struct _NDIS_MINIPORT_BLOCK *a1, _NDIS_FILTER_BLOCK *this)
{
  _NDIS_FILTER_BLOCK *v2; // rbx
  char v4; // di
  char v5; // bp
  enum _NDIS_LWF_REFTAG v6; // dl
  _NDIS_BIND_PATHS *BindPaths; // rax
  PVOID v8; // r14
  char *v9; // rdi
  int v10; // edx
  int v11; // ecx
  NTSTATUS v12; // edi
  KIRQL v13; // dl
  int v14; // edx
  int v15; // r8d
  _NDIS_FILTER_BLOCK *LowerFilter; // rax
  _NDIS_PHYSICAL_MEDIUM PhysicalMediaType; // ecx
  struct _NDIS_FILTER_BLOCK *v18; // rcx
  struct _NDIS_FILTER_BLOCK *v19; // rcx
  KIRQL v20; // dl
  int v21; // edx
  _NDIS_FILTER_BLOCK *v22; // rcx
  int v23; // edx
  char v24; // [rsp+28h] [rbp-60h]
  unsigned __int8 v25; // [rsp+A0h] [rbp+18h] BYREF
  PVOID WnodeEventItem; // [rsp+A8h] [rbp+20h] BYREF

  v2 = this;
  v4 = 0;
  v5 = 0;
  v25 = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v24 = (char)this;
    LOBYTE(this) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)this,
      1,
      35,
      (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
      v24);
  }
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( ndisReferenceFilterByHandle(v2, v6) && (v4 = 1, ndisReferenceMiniportByHandle(a1, 0, MPREF_LWF_DETACHING)) )
  {
    v5 = 1;
    ndisFNotifyDetach(v2);
    ndisCloseRef(&v2->PnPRef.SpinLock);
    BindPaths = a1->BindPaths;
    WnodeEventItem = 0;
    ndisSetupWmiNode(
      a1,
      v2->FilterFriendlyName,
      BindPaths->Paths[0].Length + 4 + v2->FilterDriver->DefaultFilterCharacteristics.UniqueName.Length,
      &GUID_NDIS_NOTIFY_FILTER_REMOVAL,
      (struct tagWNODE_SINGLE_INSTANCE **)&WnodeEventItem);
    v8 = WnodeEventItem;
    if ( WnodeEventItem )
    {
      v9 = (char *)WnodeEventItem + *((unsigned int *)WnodeEventItem + 14);
      memmove(
        v9,
        v2->FilterDriver->DefaultFilterCharacteristics.UniqueName.Buffer,
        v2->FilterDriver->DefaultFilterCharacteristics.UniqueName.Length);
      memmove(
        &v9[v2->FilterDriver->DefaultFilterCharacteristics.UniqueName.Length + 2],
        a1->BindPaths->Paths[0].Buffer,
        a1->BindPaths->Paths[0].Length);
      v12 = IoWMIWriteEvent(v8);
      if ( v12 < 0 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v10,
            1,
            36,
            (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids);
        }
        if ( (byte_140121001 & 1) != 0 )
          McTemplateK0qqq_EtwWriteTransfer(
            v11,
            (unsigned int)FilterRemovalIndicationFailed,
            (_DWORD)v2 + 664,
            v12,
            1,
            0);
        ExFreePoolWithTag(v8, 0);
      }
    }
    NDIS_ACQUIRE_FILTER_SPIN_LOCK(v2, &v25);
    FILTER_SET_FLAG(v2, 0x100u);
    v13 = v25;
    v2->LockThread = 0;
    KeReleaseSpinLock(&v2->Lock, v13);
    v2->State = NdisFilterDetaching;
    if ( (byte_140121003 & 1) != 0 )
      McTemplateK0juqjzzz_EtwWriteTransfer(
        &v2->Miniport->InterfaceGuid,
        v2->FilterInstanceName.__ptr_.__value_,
        (_DWORD)v2 + 664,
        (_DWORD)v2 + 664,
        6,
        8,
        (__int64)&v2->Miniport->InterfaceGuid,
        (__int64)v2->Miniport->pAdapterInstanceName->Buffer,
        (__int64)v2->FilterInstanceName.__ptr_.__value_->Buffer,
        (__int64)v2->FilterFriendlyName->Buffer);
    ndisFilterWaitForPnPComplete(v2);
    PktMonClientComponentUnregister(&v2->PktMonComp.ListLink.Flink);
    ndisMakeWatchdog(
      &WnodeEventItem,
      v2,
      20,
      v2->FilterDriver->DefaultFilterCharacteristics.DetachHandler,
      ndisWatchdogPnPTimeout,
      0);
    ndisFInvokeDetach(v2);
    if ( WnodeEventItem != (PVOID)-1LL )
      ndisFreeWatchdog((struct NDISWATCHDOG__ *)WnodeEventItem);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qqZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v14,
        v15,
        37,
        (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
        (char)a1,
        (char)v2,
        (__int64)&v2->FilterDriver->DefaultFilterCharacteristics.FriendlyName,
        (__int64)a1->pAdapterInstanceName);
    while ( v2->StatusIndicationsQueued )
      NdisMSleep(0x3E8u);
    if ( FILTER_TEST_FLAG(v2, 0x8000u) )
    {
      LowerFilter = v2->LowerFilter;
      if ( LowerFilter )
      {
        a1->MediaType = LowerFilter->MediaType;
        PhysicalMediaType = v2->LowerFilter->PhysicalMediaType;
      }
      else
      {
        PhysicalMediaType = a1->MiniportPhysicalMediumType;
        a1->MediaType = a1->MiniportMediaType;
      }
      a1->PhysicalMediumType = PhysicalMediaType;
      if ( a1->HasConversionFilter )
      {
        EthFreeFilterBuffers(a1->EthDB, 0);
        a1->HasConversionFilter = 0;
      }
    }
    NDIS_ACQUIRE_FILTER_SPIN_LOCK(v2, &v25);
    FILTER_CLEAR_FLAG(v2, 0x100u);
    FILTER_CLEAR_ALL_STATE_FLAGS(v18);
    FILTER_SET_FLAG(v19, 8u);
    v20 = v25;
    v2->LockThread = 0;
    KeReleaseSpinLock(&v2->Lock, v20);
    v2->State = NdisFilterDetached;
    if ( (byte_140121003 & 1) != 0 )
      McTemplateK0juqjzzz_EtwWriteTransfer(
        &v2->Miniport->InterfaceGuid,
        v21,
        (_DWORD)v2 + 664,
        (_DWORD)v2 + 664,
        0,
        9,
        (__int64)&v2->Miniport->InterfaceGuid,
        (__int64)v2->Miniport->pAdapterInstanceName->Buffer,
        (__int64)v2->FilterInstanceName.__ptr_.__value_->Buffer,
        (__int64)v2->FilterFriendlyName->Buffer);
    if ( FILTER_TEST_FLAG(v2, 0x8000u) )
      --a1->MediaChangeFilters;
    ndisFilterAttachCleanUp(v22, a1, 1u);
    ndisDereferenceMiniport(a1, MPREF_LWF_ATTACHED);
    ndisHandleFilterHandlersChange(a1);
  }
  else
  {
    ndisHandleFilterHandlersChange(a1);
    if ( !v4 )
      goto LABEL_34;
  }
  v2->Miniport = 0;
  ndisDereferenceFilter(v2, LWFREF_DETACHING);
  if ( v5 )
    ndisDereferenceMiniport(a1, MPREF_LWF_DETACHING);
LABEL_34:
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v23) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v23,
      1,
      38,
      (struct _GUID *)&WPP_4f475340cee13bebfed3041a3a58f669_Traceguids,
      (char)v2);
  }
}

```

## disassembly

```asm
0x140184cd0  mov     rax, rsp
0x140184cd3  push    rbx
0x140184cd4  push    r13
0x140184cd6  sub     rsp, 78h
0x140184cda  mov     [rax+8], rbp
0x140184cde  mov     rbx, rdx
0x140184ce1  mov     [rax-18h], rsi
0x140184ce5  mov     rsi, rcx
0x140184ce8  mov     [rax-20h], rdi
0x140184cec  xor     dil, dil
0x140184cef  mov     [rax-28h], r12
0x140184cf3  xor     bpl, bpl
0x140184cf6  mov     [rax+18h], dil
0x140184cfa  mov     [rax-38h], r15
0x140184cfe  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140184d05  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140184d0c  lea     r13, WPP_4f475340cee13bebfed3041a3a58f669_Traceguids
0x140184d13  jz      short loc_140184D3B
0x140184d15  mov     rcx, cs:WPP_GLOBAL_Control
0x140184d1c  mov     r9d, 23h ; '#'; int
0x140184d22  mov     [rax-60h], rdx
0x140184d26  mov     r8d, 1; int
0x140184d2c  mov     dl, 4; int
0x140184d2e  mov     [rax-68h], r13
0x140184d32  mov     rcx, [rcx+40h]; int
0x140184d36  call    WPP_RECORDER_SF_q
0x140184d3b  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140184d42  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140184d47  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140184d4a  call    ?ndisReferenceFilterByHandle@@YAEPEAU_NDIS_FILTER_BLOCK@@W4_NDIS_LWF_REFTAG@@@Z; ndisReferenceFilterByHandle(_NDIS_FILTER_BLOCK *,_NDIS_LWF_REFTAG)
0x140184d4f  xor     r12d, r12d
0x140184d52  test    al, al
0x140184d54  jz      loc_140185171
0x140184d5a  mov     r8b, 29h ; ')'; enum _NDIS_MP_REFTAG
0x140184d5d  xor     edx, edx; unsigned __int8
0x140184d5f  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140184d62  mov     dil, 1
0x140184d65  call    ?ndisReferenceMiniportByHandle@@YAEPEAU_NDIS_MINIPORT_BLOCK@@EW4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniportByHandle(_NDIS_MINIPORT_BLOCK *,uchar,_NDIS_MP_REFTAG)
0x140184d6a  test    al, al
0x140184d6c  jz      loc_140185171
0x140184d72  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140184d75  mov     [rsp+88h+var_30], r14
0x140184d7a  movzx   ebp, dil
0x140184d7e  call    ?ndisFNotifyDetach@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; ndisFNotifyDetach(_NDIS_FILTER_BLOCK *)
0x140184d83  lea     rcx, [rbx+138h]; SpinLock
0x140184d8a  call    ?ndisCloseRef@@YAEPEAU_REFERENCE_EX@@@Z; ndisCloseRef(_REFERENCE_EX *)
0x140184d8f  mov     rax, [rsi+0EB8h]
0x140184d96  lea     r9, GUID_NDIS_NOTIFY_FILTER_REMOVAL; void *
0x140184d9d  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140184da0  mov     [rsp+88h+WnodeEventItem], r12
0x140184da8  movzx   edx, word ptr [rax+8]
0x140184dac  mov     rax, [rbx+10h]
0x140184db0  add     edx, 4
0x140184db3  movzx   r8d, word ptr [rax+80h]
0x140184dbb  lea     rax, [rsp+88h+WnodeEventItem]
0x140184dc3  add     r8d, edx; unsigned int
0x140184dc6  mov     [rsp+88h+var_68], rax; struct tagWNODE_SINGLE_INSTANCE **
0x140184dcb  mov     rdx, [rbx+30h]; struct _UNICODE_STRING *
0x140184dcf  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x140184dd4  mov     r14, [rsp+88h+WnodeEventItem]
0x140184ddc  test    r14, r14
0x140184ddf  jz      loc_140184EAC
0x140184de5  mov     rdx, [rbx+10h]
0x140184de9  mov     edi, [r14+38h]
0x140184ded  add     rdi, r14
0x140184df0  mov     rcx, rdi; void *
0x140184df3  movzx   r8d, word ptr [rdx+80h]; Size
0x140184dfb  mov     rdx, [rdx+88h]; Src
0x140184e02  call    memmove
0x140184e07  mov     rdx, [rsi+0EB8h]
0x140184e0e  mov     rax, [rbx+10h]
0x140184e12  movzx   r8d, word ptr [rdx+8]; Size
0x140184e17  movzx   ecx, word ptr [rax+80h]
0x140184e1e  mov     rdx, [rdx+10h]; Src
0x140184e22  add     rcx, 2
0x140184e26  add     rcx, rdi; void *
0x140184e29  call    memmove
0x140184e2e  mov     rcx, r14; WnodeEventItem
0x140184e31  call    cs:__imp_IoWMIWriteEvent
0x140184e38  nop     dword ptr [rax+rax+00h]
0x140184e3d  mov     edi, eax
0x140184e3f  test    eax, eax
0x140184e41  jns     short loc_140184EAC
0x140184e43  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140184e4a  jz      short loc_140184E6F
0x140184e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140184e53  mov     r9d, 24h ; '$'; int
0x140184e59  mov     r8d, 1; int
0x140184e5f  mov     [rsp+88h+var_68], r13; struct _GUID *
0x140184e64  mov     dl, 2; int
0x140184e66  mov     rcx, [rcx+40h]; int
0x140184e6a  call    WPP_RECORDER_SF_
0x140184e6f  test    cs:byte_140121001, bpl
0x140184e76  jz      short loc_140184E9B
0x140184e78  lea     r8, [rbx+298h]
0x140184e7f  mov     dword ptr [rsp+88h+var_60], r12d
0x140184e84  mov     r9d, edi
0x140184e87  mov     dword ptr [rsp+88h+var_68], 10001h
0x140184e8f  lea     rdx, FilterRemovalIndicationFailed
0x140184e96  call    McTemplateK0qqq_EtwWriteTransfer
0x140184e9b  xor     edx, edx; Tag
0x140184e9d  mov     rcx, r14; P
0x140184ea0  call    cs:__imp_ExFreePoolWithTag
0x140184ea7  nop     dword ptr [rax+rax+00h]
0x140184eac  lea     rdx, [rsp+88h+arg_10]; unsigned __int8 *
0x140184eb4  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140184eb7  call    ?NDIS_ACQUIRE_FILTER_SPIN_LOCK@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAE@Z; NDIS_ACQUIRE_FILTER_SPIN_LOCK(_NDIS_FILTER_BLOCK *,uchar *)
0x140184ebc  mov     edx, 100h; unsigned int
0x140184ec1  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140184ec4  call    ?FILTER_SET_FLAG@@YAXPEAU_NDIS_FILTER_BLOCK@@K@Z; FILTER_SET_FLAG(_NDIS_FILTER_BLOCK *,ulong)
0x140184ec9  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x140184ed1  lea     rcx, [rbx+90h]; SpinLock
0x140184ed8  mov     [rbx+98h], r12
0x140184edf  call    cs:__imp_KeReleaseSpinLock
0x140184ee6  nop     dword ptr [rax+rax+00h]
0x140184eeb  mov     r14, [rsp+88h+var_30]
0x140184ef0  mov     byte ptr [rbx+40h], 6
0x140184ef4  test    cs:byte_140121003, bpl
0x140184efb  jz      short loc_140184F57
0x140184efd  mov     rcx, [rbx+20h]
0x140184f01  lea     r9, [rbx+298h]
0x140184f08  mov     rax, [rbx+30h]
0x140184f0c  mov     rdx, [rbx+28h]
0x140184f10  mov     r8, [rcx+0F10h]
0x140184f17  add     rcx, 0FA8h
0x140184f1e  mov     rax, [rax+8]
0x140184f22  mov     [rsp+88h+var_40], rax
0x140184f27  mov     rax, [rdx+8]
0x140184f2b  mov     [rsp+88h+var_48], rax
0x140184f30  mov     rax, [r8+8]
0x140184f34  lea     r8, [rbx+298h]
0x140184f3b  mov     [rsp+88h+var_50], rax
0x140184f40  mov     qword ptr [rsp+88h+var_58], rcx
0x140184f45  mov     dword ptr [rsp+88h+var_60], 8
0x140184f4d  mov     byte ptr [rsp+88h+var_68], 6
0x140184f52  call    McTemplateK0juqjzzz_EtwWriteTransfer
0x140184f57  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140184f5a  call    ?ndisFilterWaitForPnPComplete@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; ndisFilterWaitForPnPComplete(_NDIS_FILTER_BLOCK *)
0x140184f5f  lea     rcx, [rbx+310h]; void *
0x140184f66  call    PktMonClientComponentUnregister
0x140184f6b  mov     r9, [rbx+10h]
0x140184f6f  lea     rcx, [rsp+88h+WnodeEventItem]
0x140184f77  mov     eax, cs:?ndisWatchdogPnPTimeout@@3KA; ulong ndisWatchdogPnPTimeout
0x140184f7d  mov     r8d, 14h
0x140184f83  mov     qword ptr [rsp+88h+var_60], r12
0x140184f88  mov     rdx, rbx
0x140184f8b  mov     dword ptr [rsp+88h+var_68], eax
0x140184f8f  mov     r9, [r9+0B8h]
0x140184f96  call    ?ndisMakeWatchdog@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUNDISWATCHDOG__@@P6AXPEAU1@@Z$1?ndisFreeWatchdog@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@_J$0?0$$T@details@wil@@@details@wil@@@wil@@PEAXK0K_K@Z; ndisMakeWatchdog(void *,ulong,void *,ulong,unsigned __int64)
0x140184f9b  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140184f9e  call    ?ndisFInvokeDetach@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; ndisFInvokeDetach(_NDIS_FILTER_BLOCK *)
0x140184fa3  mov     rcx, [rsp+88h+WnodeEventItem]; struct NDISWATCHDOG__ *
0x140184fab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140184faf  jz      short loc_140184FB6
0x140184fb1  call    ?ndisFreeWatchdog@@YAXPEAUNDISWATCHDOG__@@@Z; ndisFreeWatchdog(NDISWATCHDOG__ *)
0x140184fb6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140184fbd  jz      short loc_140184FFD
0x140184fbf  mov     rcx, [rbx+10h]
0x140184fc3  mov     r9d, 25h ; '%'; int
0x140184fc9  mov     rax, [rsi+0F10h]
0x140184fd0  add     rcx, 70h ; 'p'
0x140184fd4  mov     [rsp+88h+var_48], rax; __int64
0x140184fd9  mov     [rsp+88h+var_50], rcx; __int64
0x140184fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140184fe5  mov     qword ptr [rsp+88h+var_58], rbx; char
0x140184fea  mov     qword ptr [rsp+88h+var_60], rsi; char
0x140184fef  mov     [rsp+88h+var_68], r13; struct _GUID *
0x140184ff4  mov     rcx, [rcx+40h]; int
0x140184ff8  call    WPP_RECORDER_SF_qqZZ
0x140184ffd  movzx   eax, byte ptr [rbx+120h]
0x140185004  test    al, al
0x140185006  jz      short loc_14018501D
0x140185008  mov     ecx, 3E8h; MicrosecondsToSleep
0x14018500d  call    NdisMSleep
0x140185012  movzx   eax, byte ptr [rbx+120h]
0x140185019  test    al, al
0x14018501b  jnz     short loc_140185008
0x14018501d  mov     edx, 8000h; unsigned int
0x140185022  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140185025  call    ?FILTER_TEST_FLAG@@YAEPEBU_NDIS_FILTER_BLOCK@@K@Z; FILTER_TEST_FLAG(_NDIS_FILTER_BLOCK const *,ulong)
0x14018502a  test    al, al
0x14018502c  jz      short loc_140185085
0x14018502e  mov     rax, [rbx+70h]
0x140185032  test    rax, rax
0x140185035  jz      short loc_14018504F
0x140185037  mov     eax, [rax+150h]
0x14018503d  mov     [rsi+1D0h], eax
0x140185043  mov     rax, [rbx+70h]
0x140185047  mov     ecx, [rax+154h]
0x14018504d  jmp     short loc_140185061
0x14018504f  mov     eax, [rsi+72Ch]
0x140185055  mov     ecx, [rsi+0EC0h]
0x14018505b  mov     [rsi+1D0h], eax
0x140185061  mov     [rsi+728h], ecx
0x140185067  cmp     [rsi+17D0h], r12b
0x14018506e  jz      short loc_140185085
0x140185070  mov     rcx, [rsi+190h]; P
0x140185077  xor     edx, edx; bool
0x140185079  call    ?EthFreeFilterBuffers@@YAXPEAU_X_FILTER@@_N@Z; EthFreeFilterBuffers(_X_FILTER *,bool)
0x14018507e  mov     [rsi+17D0h], r12b
0x140185085  lea     rdx, [rsp+88h+arg_10]; unsigned __int8 *
0x14018508d  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140185090  call    ?NDIS_ACQUIRE_FILTER_SPIN_LOCK@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAE@Z; NDIS_ACQUIRE_FILTER_SPIN_LOCK(_NDIS_FILTER_BLOCK *,uchar *)
0x140185095  mov     edx, 100h; unsigned int
0x14018509a  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14018509d  call    ?FILTER_CLEAR_FLAG@@YAXPEAU_NDIS_FILTER_BLOCK@@K@Z; FILTER_CLEAR_FLAG(_NDIS_FILTER_BLOCK *,ulong)
0x1401850a2  call    ?FILTER_CLEAR_ALL_STATE_FLAGS@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; FILTER_CLEAR_ALL_STATE_FLAGS(_NDIS_FILTER_BLOCK *)
0x1401850a7  mov     edx, 8; unsigned int
0x1401850ac  call    ?FILTER_SET_FLAG@@YAXPEAU_NDIS_FILTER_BLOCK@@K@Z; FILTER_SET_FLAG(_NDIS_FILTER_BLOCK *,ulong)
0x1401850b1  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x1401850b9  lea     rcx, [rbx+90h]; SpinLock
0x1401850c0  mov     [rbx+98h], r12
0x1401850c7  call    cs:__imp_KeReleaseSpinLock
0x1401850ce  nop     dword ptr [rax+rax+00h]
0x1401850d3  mov     [rbx+40h], r12b
0x1401850d7  test    cs:byte_140121003, bpl
0x1401850de  jz      short loc_14018513A
0x1401850e0  mov     rcx, [rbx+20h]
0x1401850e4  mov     r8, [rbx+28h]
0x1401850e8  mov     rax, [rbx+30h]
0x1401850ec  mov     r9, [rcx+0F10h]
0x1401850f3  add     rcx, 0FA8h
0x1401850fa  mov     rax, [rax+8]
0x1401850fe  mov     [rsp+88h+var_40], rax
0x140185103  mov     rax, [r8+8]
0x140185107  lea     r8, [rbx+298h]
0x14018510e  mov     [rsp+88h+var_48], rax
0x140185113  mov     rax, [r9+8]
0x140185117  lea     r9, [rbx+298h]
0x14018511e  mov     [rsp+88h+var_50], rax
0x140185123  mov     qword ptr [rsp+88h+var_58], rcx
0x140185128  mov     dword ptr [rsp+88h+var_60], 9
0x140185130  mov     byte ptr [rsp+88h+var_68], r12b
0x140185135  call    McTemplateK0juqjzzz_EtwWriteTransfer
0x14018513a  mov     edx, 8000h; unsigned int
0x14018513f  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140185142  call    ?FILTER_TEST_FLAG@@YAEPEBU_NDIS_FILTER_BLOCK@@K@Z; FILTER_TEST_FLAG(_NDIS_FILTER_BLOCK const *,ulong)
0x140185147  test    al, al
0x140185149  jz      short loc_140185151
0x14018514b  dec     byte ptr [rsi+7CDh]
0x140185151  movzx   r8d, bpl; unsigned __int8
0x140185155  mov     rdx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140185158  call    ?ndisFilterAttachCleanUp@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisFilterAttachCleanUp(_NDIS_FILTER_BLOCK *,_NDIS_MINIPORT_BLOCK *,uchar)
0x14018515d  mov     dl, 28h ; '('; enum _NDIS_MP_REFTAG
0x14018515f  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140185162  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x140185167  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14018516a  call    ?ndisHandleFilterHandlersChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisHandleFilterHandlersChange(_NDIS_MINIPORT_BLOCK *)
0x14018516f  jmp     short loc_14018517E
0x140185171  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140185174  call    ?ndisHandleFilterHandlersChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisHandleFilterHandlersChange(_NDIS_MINIPORT_BLOCK *)
0x140185179  test    dil, dil
0x14018517c  jz      short loc_14018519B
0x14018517e  xor     edx, edx; enum _NDIS_LWF_REFTAG
0x140185180  mov     [rbx+20h], r12
0x140185184  mov     rcx, rbx; this
0x140185187  call    ?ndisDereferenceFilter@@YAXPEAU_NDIS_FILTER_BLOCK@@W4_NDIS_LWF_REFTAG@@@Z; ndisDereferenceFilter(_NDIS_FILTER_BLOCK *,_NDIS_LWF_REFTAG)
0x14018518c  test    bpl, bpl
0x14018518f  jz      short loc_14018519B
0x140185191  mov     dl, 29h ; ')'; enum _NDIS_MP_REFTAG
0x140185193  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140185196  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14018519b  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x1401851a2  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x1401851a7  mov     r12, [rsp+88h+var_28]
0x1401851ac  mov     rdi, [rsp+88h+var_20]
0x1401851b1  mov     rsi, [rsp+88h+var_18]
0x1401851b6  mov     rbp, [rsp+88h+arg_0]
0x1401851be  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1401851c5  mov     r15, [rsp+88h+var_38]
0x1401851ca  jz      short loc_1401851F4
0x1401851cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1401851d3  mov     r9d, 26h ; '&'; int
0x1401851d9  mov     qword ptr [rsp+88h+var_60], rbx; char
0x1401851de  mov     r8d, 1; int
0x1401851e4  mov     dl, 4; int
0x1401851e6  mov     [rsp+88h+var_68], r13; struct _GUID *
0x1401851eb  mov     rcx, [rcx+40h]; int
0x1401851ef  call    WPP_RECORDER_SF_q
0x1401851f4  add     rsp, 78h
0x1401851f8  pop     r13
0x1401851fa  pop     rbx
0x1401851fb  retn
```
