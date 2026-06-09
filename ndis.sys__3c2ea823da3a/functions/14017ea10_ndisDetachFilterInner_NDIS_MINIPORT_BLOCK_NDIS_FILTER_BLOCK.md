# ndisDetachFilterInner(_NDIS_MINIPORT_BLOCK *,_NDIS_FILTER_BLOCK *)

- ea: `0x14017ea10`
- end: `0x14017ef3d`
- name: `?ndisDetachFilterInner@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_FILTER_BLOCK@@@Z`
- size: `1325`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, _NDIS_FILTER_BLOCK *this)`
- caller_count: `1`
- callee_count: `30`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140156c70`

## callees

- `0x140013f70`
- `0x140019420`
- `0x14001cc80`
- `0x14001cf50`
- `0x140029620`
- `0x14003d920`
- `0x14004bfe0`
- `0x14004e050`
- `0x140052880`
- `0x1400529f0`
- `0x140053090`
- `0x140056ae0`
- `0x140057510`
- `0x14005a1c0`
- `0x1400656a0`
- `0x140065740`
- `0x14006f5c0`
- `0x1400720e0`
- `0x140075710`
- `0x140076380`
- `0x140078900`
- `0x140087b00`
- `0x14008e340`
- `0x1400915c0`
- `0x1400e62c0`
- `0x140155370`
- `0x1401559e0`
- `0x1401672a0`
- `0x140168b90`
- `0x14017ea10`

## import_xrefs

- `ntoskrnl!IoWMIWriteEvent` at `0x14017eb71`
- `ntoskrnl!IoWMIWriteEvent` at `0x14017eb71`
- `ntoskrnl!ExFreePoolWithTag` at `0x14017ebe0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14017ebe0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ec1f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ee07`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ec1f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017ee07`

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
      (__int128 *)&GUID_NDIS_NOTIFY_FILTER_REMOVAL,
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
        if ( (byte_14011B001 & 1) != 0 )
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
    if ( (byte_14011B003 & 1) != 0 )
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
    if ( (byte_14011B003 & 1) != 0 )
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
0x14017ea10  mov     rax, rsp
0x14017ea13  push    rbx
0x14017ea14  push    r13
0x14017ea16  sub     rsp, 78h
0x14017ea1a  mov     [rax+8], rbp
0x14017ea1e  mov     rbx, rdx
0x14017ea21  mov     [rax-18h], rsi
0x14017ea25  mov     rsi, rcx
0x14017ea28  mov     [rax-20h], rdi
0x14017ea2c  xor     dil, dil
0x14017ea2f  mov     [rax-28h], r12
0x14017ea33  xor     bpl, bpl
0x14017ea36  mov     [rax+18h], dil
0x14017ea3a  mov     [rax-38h], r15
0x14017ea3e  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14017ea45  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017ea4c  lea     r13, WPP_4f475340cee13bebfed3041a3a58f669_Traceguids
0x14017ea53  jz      short loc_14017EA7B
0x14017ea55  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ea5c  mov     r9d, 23h ; '#'; int
0x14017ea62  mov     [rax-60h], rdx
0x14017ea66  mov     r8d, 1; int
0x14017ea6c  mov     dl, 4; int
0x14017ea6e  mov     [rax-68h], r13
0x14017ea72  mov     rcx, [rcx+40h]; int
0x14017ea76  call    WPP_RECORDER_SF_q
0x14017ea7b  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14017ea82  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14017ea87  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017ea8a  call    ?ndisReferenceFilterByHandle@@YAEPEAU_NDIS_FILTER_BLOCK@@W4_NDIS_LWF_REFTAG@@@Z; ndisReferenceFilterByHandle(_NDIS_FILTER_BLOCK *,_NDIS_LWF_REFTAG)
0x14017ea8f  xor     r12d, r12d
0x14017ea92  test    al, al
0x14017ea94  jz      loc_14017EEB1
0x14017ea9a  mov     r8b, 29h ; ')'; enum _NDIS_MP_REFTAG
0x14017ea9d  xor     edx, edx; unsigned __int8
0x14017ea9f  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14017eaa2  mov     dil, 1
0x14017eaa5  call    ?ndisReferenceMiniportByHandle@@YAEPEAU_NDIS_MINIPORT_BLOCK@@EW4_NDIS_MP_REFTAG@@@Z; ndisReferenceMiniportByHandle(_NDIS_MINIPORT_BLOCK *,uchar,_NDIS_MP_REFTAG)
0x14017eaaa  test    al, al
0x14017eaac  jz      loc_14017EEB1
0x14017eab2  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017eab5  mov     [rsp+88h+var_30], r14
0x14017eaba  movzx   ebp, dil
0x14017eabe  call    ?ndisFNotifyDetach@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; ndisFNotifyDetach(_NDIS_FILTER_BLOCK *)
0x14017eac3  lea     rcx, [rbx+138h]; SpinLock
0x14017eaca  call    ?ndisCloseRef@@YAEPEAU_REFERENCE_EX@@@Z; ndisCloseRef(_REFERENCE_EX *)
0x14017eacf  mov     rax, [rsi+0EB8h]
0x14017ead6  lea     r9, GUID_NDIS_NOTIFY_FILTER_REMOVAL; void *
0x14017eadd  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14017eae0  mov     [rsp+88h+WnodeEventItem], r12
0x14017eae8  movzx   edx, word ptr [rax+8]
0x14017eaec  mov     rax, [rbx+10h]
0x14017eaf0  add     edx, 4
0x14017eaf3  movzx   r8d, word ptr [rax+80h]
0x14017eafb  lea     rax, [rsp+88h+WnodeEventItem]
0x14017eb03  add     r8d, edx; unsigned int
0x14017eb06  mov     [rsp+88h+var_68], rax; struct tagWNODE_SINGLE_INSTANCE **
0x14017eb0b  mov     rdx, [rbx+30h]; struct _UNICODE_STRING *
0x14017eb0f  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x14017eb14  mov     r14, [rsp+88h+WnodeEventItem]
0x14017eb1c  test    r14, r14
0x14017eb1f  jz      loc_14017EBEC
0x14017eb25  mov     rdx, [rbx+10h]
0x14017eb29  mov     edi, [r14+38h]
0x14017eb2d  add     rdi, r14
0x14017eb30  mov     rcx, rdi; void *
0x14017eb33  movzx   r8d, word ptr [rdx+80h]; Size
0x14017eb3b  mov     rdx, [rdx+88h]; Src
0x14017eb42  call    memmove
0x14017eb47  mov     rdx, [rsi+0EB8h]
0x14017eb4e  mov     rax, [rbx+10h]
0x14017eb52  movzx   r8d, word ptr [rdx+8]; Size
0x14017eb57  movzx   ecx, word ptr [rax+80h]
0x14017eb5e  mov     rdx, [rdx+10h]; Src
0x14017eb62  add     rcx, 2
0x14017eb66  add     rcx, rdi; void *
0x14017eb69  call    memmove
0x14017eb6e  mov     rcx, r14; WnodeEventItem
0x14017eb71  call    cs:__imp_IoWMIWriteEvent
0x14017eb78  nop     dword ptr [rax+rax+00h]
0x14017eb7d  mov     edi, eax
0x14017eb7f  test    eax, eax
0x14017eb81  jns     short loc_14017EBEC
0x14017eb83  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14017eb8a  jz      short loc_14017EBAF
0x14017eb8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14017eb93  mov     r9d, 24h ; '$'; int
0x14017eb99  mov     r8d, 1; int
0x14017eb9f  mov     [rsp+88h+var_68], r13; struct _GUID *
0x14017eba4  mov     dl, 2; int
0x14017eba6  mov     rcx, [rcx+40h]; int
0x14017ebaa  call    WPP_RECORDER_SF_
0x14017ebaf  test    cs:byte_14011B001, bpl
0x14017ebb6  jz      short loc_14017EBDB
0x14017ebb8  lea     r8, [rbx+298h]
0x14017ebbf  mov     dword ptr [rsp+88h+var_60], r12d
0x14017ebc4  mov     r9d, edi
0x14017ebc7  mov     dword ptr [rsp+88h+var_68], 10001h
0x14017ebcf  lea     rdx, FilterRemovalIndicationFailed
0x14017ebd6  call    McTemplateK0qqq_EtwWriteTransfer
0x14017ebdb  xor     edx, edx; Tag
0x14017ebdd  mov     rcx, r14; P
0x14017ebe0  call    cs:__imp_ExFreePoolWithTag
0x14017ebe7  nop     dword ptr [rax+rax+00h]
0x14017ebec  lea     rdx, [rsp+88h+arg_10]; unsigned __int8 *
0x14017ebf4  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017ebf7  call    ?NDIS_ACQUIRE_FILTER_SPIN_LOCK@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAE@Z; NDIS_ACQUIRE_FILTER_SPIN_LOCK(_NDIS_FILTER_BLOCK *,uchar *)
0x14017ebfc  mov     edx, 100h; unsigned int
0x14017ec01  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017ec04  call    ?FILTER_SET_FLAG@@YAXPEAU_NDIS_FILTER_BLOCK@@K@Z; FILTER_SET_FLAG(_NDIS_FILTER_BLOCK *,ulong)
0x14017ec09  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x14017ec11  lea     rcx, [rbx+90h]; SpinLock
0x14017ec18  mov     [rbx+98h], r12
0x14017ec1f  call    cs:__imp_KeReleaseSpinLock
0x14017ec26  nop     dword ptr [rax+rax+00h]
0x14017ec2b  mov     r14, [rsp+88h+var_30]
0x14017ec30  mov     byte ptr [rbx+40h], 6
0x14017ec34  test    cs:byte_14011B003, bpl
0x14017ec3b  jz      short loc_14017EC97
0x14017ec3d  mov     rcx, [rbx+20h]
0x14017ec41  lea     r9, [rbx+298h]
0x14017ec48  mov     rax, [rbx+30h]
0x14017ec4c  mov     rdx, [rbx+28h]
0x14017ec50  mov     r8, [rcx+0F10h]
0x14017ec57  add     rcx, 0FA8h
0x14017ec5e  mov     rax, [rax+8]
0x14017ec62  mov     [rsp+88h+var_40], rax
0x14017ec67  mov     rax, [rdx+8]
0x14017ec6b  mov     [rsp+88h+var_48], rax
0x14017ec70  mov     rax, [r8+8]
0x14017ec74  lea     r8, [rbx+298h]
0x14017ec7b  mov     [rsp+88h+var_50], rax
0x14017ec80  mov     qword ptr [rsp+88h+var_58], rcx
0x14017ec85  mov     dword ptr [rsp+88h+var_60], 8
0x14017ec8d  mov     byte ptr [rsp+88h+var_68], 6
0x14017ec92  call    McTemplateK0juqjzzz_EtwWriteTransfer
0x14017ec97  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017ec9a  call    ?ndisFilterWaitForPnPComplete@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; ndisFilterWaitForPnPComplete(_NDIS_FILTER_BLOCK *)
0x14017ec9f  lea     rcx, [rbx+310h]; void *
0x14017eca6  call    PktMonClientComponentUnregister
0x14017ecab  mov     r9, [rbx+10h]
0x14017ecaf  lea     rcx, [rsp+88h+WnodeEventItem]
0x14017ecb7  mov     eax, cs:?ndisWatchdogPnPTimeout@@3KA; ulong ndisWatchdogPnPTimeout
0x14017ecbd  mov     r8d, 14h
0x14017ecc3  mov     qword ptr [rsp+88h+var_60], r12
0x14017ecc8  mov     rdx, rbx
0x14017eccb  mov     dword ptr [rsp+88h+var_68], eax
0x14017eccf  mov     r9, [r9+0B8h]
0x14017ecd6  call    ?ndisMakeWatchdog@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUNDISWATCHDOG__@@P6AXPEAU1@@Z$1?ndisFreeWatchdog@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@_J$0?0$$T@details@wil@@@details@wil@@@wil@@PEAXK0K_K@Z; ndisMakeWatchdog(void *,ulong,void *,ulong,unsigned __int64)
0x14017ecdb  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017ecde  call    ?ndisFInvokeDetach@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; ndisFInvokeDetach(_NDIS_FILTER_BLOCK *)
0x14017ece3  mov     rcx, [rsp+88h+WnodeEventItem]; struct NDISWATCHDOG__ *
0x14017eceb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14017ecef  jz      short loc_14017ECF6
0x14017ecf1  call    ?ndisFreeWatchdog@@YAXPEAUNDISWATCHDOG__@@@Z; ndisFreeWatchdog(NDISWATCHDOG__ *)
0x14017ecf6  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14017ecfd  jz      short loc_14017ED3D
0x14017ecff  mov     rcx, [rbx+10h]
0x14017ed03  mov     r9d, 25h ; '%'; int
0x14017ed09  mov     rax, [rsi+0F10h]
0x14017ed10  add     rcx, 70h ; 'p'
0x14017ed14  mov     [rsp+88h+var_48], rax; __int64
0x14017ed19  mov     [rsp+88h+var_50], rcx; __int64
0x14017ed1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ed25  mov     qword ptr [rsp+88h+var_58], rbx; char
0x14017ed2a  mov     qword ptr [rsp+88h+var_60], rsi; char
0x14017ed2f  mov     [rsp+88h+var_68], r13; struct _GUID *
0x14017ed34  mov     rcx, [rcx+40h]; int
0x14017ed38  call    WPP_RECORDER_SF_qqZZ
0x14017ed3d  movzx   eax, byte ptr [rbx+120h]
0x14017ed44  test    al, al
0x14017ed46  jz      short loc_14017ED5D
0x14017ed48  mov     ecx, 3E8h; MicrosecondsToSleep
0x14017ed4d  call    NdisMSleep
0x14017ed52  movzx   eax, byte ptr [rbx+120h]
0x14017ed59  test    al, al
0x14017ed5b  jnz     short loc_14017ED48
0x14017ed5d  mov     edx, 8000h; unsigned int
0x14017ed62  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017ed65  call    ?FILTER_TEST_FLAG@@YAEPEBU_NDIS_FILTER_BLOCK@@K@Z; FILTER_TEST_FLAG(_NDIS_FILTER_BLOCK const *,ulong)
0x14017ed6a  test    al, al
0x14017ed6c  jz      short loc_14017EDC5
0x14017ed6e  mov     rax, [rbx+70h]
0x14017ed72  test    rax, rax
0x14017ed75  jz      short loc_14017ED8F
0x14017ed77  mov     eax, [rax+150h]
0x14017ed7d  mov     [rsi+1D0h], eax
0x14017ed83  mov     rax, [rbx+70h]
0x14017ed87  mov     ecx, [rax+154h]
0x14017ed8d  jmp     short loc_14017EDA1
0x14017ed8f  mov     eax, [rsi+72Ch]
0x14017ed95  mov     ecx, [rsi+0EC0h]
0x14017ed9b  mov     [rsi+1D0h], eax
0x14017eda1  mov     [rsi+728h], ecx
0x14017eda7  cmp     [rsi+17D0h], r12b
0x14017edae  jz      short loc_14017EDC5
0x14017edb0  mov     rcx, [rsi+190h]; P
0x14017edb7  xor     edx, edx; bool
0x14017edb9  call    ?EthFreeFilterBuffers@@YAXPEAU_X_FILTER@@_N@Z; EthFreeFilterBuffers(_X_FILTER *,bool)
0x14017edbe  mov     [rsi+17D0h], r12b
0x14017edc5  lea     rdx, [rsp+88h+arg_10]; unsigned __int8 *
0x14017edcd  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017edd0  call    ?NDIS_ACQUIRE_FILTER_SPIN_LOCK@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAE@Z; NDIS_ACQUIRE_FILTER_SPIN_LOCK(_NDIS_FILTER_BLOCK *,uchar *)
0x14017edd5  mov     edx, 100h; unsigned int
0x14017edda  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017eddd  call    ?FILTER_CLEAR_FLAG@@YAXPEAU_NDIS_FILTER_BLOCK@@K@Z; FILTER_CLEAR_FLAG(_NDIS_FILTER_BLOCK *,ulong)
0x14017ede2  call    ?FILTER_CLEAR_ALL_STATE_FLAGS@@YAXPEAU_NDIS_FILTER_BLOCK@@@Z; FILTER_CLEAR_ALL_STATE_FLAGS(_NDIS_FILTER_BLOCK *)
0x14017ede7  mov     edx, 8; unsigned int
0x14017edec  call    ?FILTER_SET_FLAG@@YAXPEAU_NDIS_FILTER_BLOCK@@K@Z; FILTER_SET_FLAG(_NDIS_FILTER_BLOCK *,ulong)
0x14017edf1  movzx   edx, [rsp+88h+arg_10]; NewIrql
0x14017edf9  lea     rcx, [rbx+90h]; SpinLock
0x14017ee00  mov     [rbx+98h], r12
0x14017ee07  call    cs:__imp_KeReleaseSpinLock
0x14017ee0e  nop     dword ptr [rax+rax+00h]
0x14017ee13  mov     [rbx+40h], r12b
0x14017ee17  test    cs:byte_14011B003, bpl
0x14017ee1e  jz      short loc_14017EE7A
0x14017ee20  mov     rcx, [rbx+20h]
0x14017ee24  mov     r8, [rbx+28h]
0x14017ee28  mov     rax, [rbx+30h]
0x14017ee2c  mov     r9, [rcx+0F10h]
0x14017ee33  add     rcx, 0FA8h
0x14017ee3a  mov     rax, [rax+8]
0x14017ee3e  mov     [rsp+88h+var_40], rax
0x14017ee43  mov     rax, [r8+8]
0x14017ee47  lea     r8, [rbx+298h]
0x14017ee4e  mov     [rsp+88h+var_48], rax
0x14017ee53  mov     rax, [r9+8]
0x14017ee57  lea     r9, [rbx+298h]
0x14017ee5e  mov     [rsp+88h+var_50], rax
0x14017ee63  mov     qword ptr [rsp+88h+var_58], rcx
0x14017ee68  mov     dword ptr [rsp+88h+var_60], 9
0x14017ee70  mov     byte ptr [rsp+88h+var_68], r12b
0x14017ee75  call    McTemplateK0juqjzzz_EtwWriteTransfer
0x14017ee7a  mov     edx, 8000h; unsigned int
0x14017ee7f  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x14017ee82  call    ?FILTER_TEST_FLAG@@YAEPEBU_NDIS_FILTER_BLOCK@@K@Z; FILTER_TEST_FLAG(_NDIS_FILTER_BLOCK const *,ulong)
0x14017ee87  test    al, al
0x14017ee89  jz      short loc_14017EE91
0x14017ee8b  dec     byte ptr [rsi+7CDh]
0x14017ee91  movzx   r8d, bpl; unsigned __int8
0x14017ee95  mov     rdx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14017ee98  call    ?ndisFilterAttachCleanUp@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisFilterAttachCleanUp(_NDIS_FILTER_BLOCK *,_NDIS_MINIPORT_BLOCK *,uchar)
0x14017ee9d  mov     dl, 28h ; '('; enum _NDIS_MP_REFTAG
0x14017ee9f  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14017eea2  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14017eea7  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14017eeaa  call    ?ndisHandleFilterHandlersChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisHandleFilterHandlersChange(_NDIS_MINIPORT_BLOCK *)
0x14017eeaf  jmp     short loc_14017EEBE
0x14017eeb1  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14017eeb4  call    ?ndisHandleFilterHandlersChange@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisHandleFilterHandlersChange(_NDIS_MINIPORT_BLOCK *)
0x14017eeb9  test    dil, dil
0x14017eebc  jz      short loc_14017EEDB
0x14017eebe  xor     edx, edx; enum _NDIS_LWF_REFTAG
0x14017eec0  mov     [rbx+20h], r12
0x14017eec4  mov     rcx, rbx; this
0x14017eec7  call    ?ndisDereferenceFilter@@YAXPEAU_NDIS_FILTER_BLOCK@@W4_NDIS_LWF_REFTAG@@@Z; ndisDereferenceFilter(_NDIS_FILTER_BLOCK *,_NDIS_LWF_REFTAG)
0x14017eecc  test    bpl, bpl
0x14017eecf  jz      short loc_14017EEDB
0x14017eed1  mov     dl, 29h ; ')'; enum _NDIS_MP_REFTAG
0x14017eed3  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x14017eed6  call    ?ndisDereferenceMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_MP_REFTAG@@@Z; ndisDereferenceMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_MP_REFTAG)
0x14017eedb  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14017eee2  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14017eee7  mov     r12, [rsp+88h+var_28]
0x14017eeec  mov     rdi, [rsp+88h+var_20]
0x14017eef1  mov     rsi, [rsp+88h+var_18]
0x14017eef6  mov     rbp, [rsp+88h+arg_0]
0x14017eefe  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x14017ef05  mov     r15, [rsp+88h+var_38]
0x14017ef0a  jz      short loc_14017EF34
0x14017ef0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ef13  mov     r9d, 26h ; '&'; int
0x14017ef19  mov     qword ptr [rsp+88h+var_60], rbx; char
0x14017ef1e  mov     r8d, 1; int
0x14017ef24  mov     dl, 4; int
0x14017ef26  mov     [rsp+88h+var_68], r13; struct _GUID *
0x14017ef2b  mov     rcx, [rcx+40h]; int
0x14017ef2f  call    WPP_RECORDER_SF_q
0x14017ef34  add     rsp, 78h
0x14017ef38  pop     r13
0x14017ef3a  pop     rbx
0x14017ef3b  retn
```
