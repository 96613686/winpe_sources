# ndisMDisableOpportunisticPowerSavings(_NDIS_MINIPORT_BLOCK *,bool *)

- ea: `0x14015dd60`
- end: `0x14015def9`
- name: `?ndisMDisableOpportunisticPowerSavings@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEA_N@Z`
- size: `409`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14015da90`

## callees

- `0x140014de0`
- `0x14003a1b0`
- `0x14004ee10`
- `0x140080990`
- `0x14008ac60`
- `0x1400c26f4`
- `0x14015dd60`
- `0x140166200`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015de51`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015ded7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015de51`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14015ded7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015de10`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14015de10`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015de77`
- `ntoskrnl!KeWaitForSingleObject` at `0x14015de77`
- `ntoskrnl!KeReadStateEvent` at `0x14015de30`
- `ntoskrnl!KeReadStateEvent` at `0x14015de30`
- `ntoskrnl!KeClearEvent` at `0x14015deb4`
- `ntoskrnl!KeClearEvent` at `0x14015deb4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015de21`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14015de21`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015de45`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015decb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015de45`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14015decb`

## pseudocode

```c
void __fastcall ndisMDisableOpportunisticPowerSavings(struct _NDIS_MINIPORT_BLOCK *a1, bool *a2)
{
  int IsEnabledDeviceUsageNoInline; // eax
  struct _NDIS_SELECTIVE_SUSPEND *SelectiveSuspend; // rcx
  Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER> *p_MiniportOwner; // rsi
  bool v7; // zf
  KPushLock *p_m_lock; // rdi
  KWaitEvent *i; // rbx

  *a2 = 0;
  ndisCancelMediaDisconnectTimer(a1);
  IsEnabledDeviceUsageNoInline = Feature_SSSurpriseRemoval_Fix__private_IsEnabledDeviceUsageNoInline();
  SelectiveSuspend = a1->SelectiveSuspend;
  if ( !IsEnabledDeviceUsageNoInline )
  {
    if ( !SelectiveSuspend )
      goto LABEL_4;
    goto LABEL_3;
  }
  if ( SelectiveSuspend )
  {
    if ( (mem::ReadNoFence<unsigned long,void>(&a1->Flags) & 0x80u) == 0LL )
    {
LABEL_3:
      ndisSelectiveSuspendStop(a1, 8u);
      goto LABEL_4;
    }
    ndisSelectiveSuspendStopWdf(a1, 8);
  }
LABEL_4:
  p_MiniportOwner = &a1->MiniportOwner;
  if ( !(unsigned __int8)Rtl::KNeutralLock<enum NDIS_MINIPORT_POLICY_OWNER>::TryAcquire(&a1->MiniportOwner, 2) )
  {
    v7 = a1->AoAc == 0;
    a1->PmInterruptedByPnp = 1;
    *a2 = 1;
    if ( !v7 )
      ndisAoAcStop(a1, 8, 1);
    if ( !a1->DoNotBlockOnMiniportLock )
    {
      p_m_lock = &a1->MiniportOwner.m_lock;
      for ( i = &a1->MiniportOwner.m_isUnowned; ; KeWaitForSingleObject(i, Executive, 0, 0, 0) )
      {
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(p_m_lock, 0);
        if ( KeReadStateEvent(&i->m_event) )
          break;
        ExReleasePushLockExclusiveEx(p_m_lock, 0);
        KeLeaveCriticalRegion();
      }
      KeClearEvent(&i->m_event);
      p_MiniportOwner->m_owner = MiniportOwnedByBindEngine;
      ExReleasePushLockExclusiveEx(p_m_lock, 0);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x14015dd60  mov     [rsp+arg_8], rbx
0x14015dd65  mov     [rsp+arg_10], rsi
0x14015dd6a  push    rdi
0x14015dd6b  sub     rsp, 30h
0x14015dd6f  mov     rdi, rdx
0x14015dd72  mov     byte ptr [rdx], 0
0x14015dd75  mov     rbx, rcx
0x14015dd78  call    ?ndisCancelMediaDisconnectTimer@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelMediaDisconnectTimer(_NDIS_MINIPORT_BLOCK *)
0x14015dd7d  call    Feature_SSSurpriseRemoval_Fix__private_IsEnabledDeviceUsageNoInline
0x14015dd82  mov     rcx, [rbx+1160h]
0x14015dd89  test    eax, eax
0x14015dd8b  jnz     loc_14015DE85
0x14015dd91  test    rcx, rcx
0x14015dd94  jz      short loc_14015DDA3
0x14015dd96  mov     edx, 8
0x14015dd9b  mov     rcx, rbx
0x14015dd9e  call    ?ndisSelectiveSuspendStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisSelectiveSuspendStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x14015dda3  lea     rsi, [rbx+1478h]
0x14015ddaa  mov     edx, 2
0x14015ddaf  mov     rcx, rsi
0x14015ddb2  call    ?TryAcquire@?$KNeutralLock@W4NDIS_MINIPORT_POLICY_OWNER@@@Rtl@@QEAA_NW4NDIS_MINIPORT_POLICY_OWNER@@@Z; Rtl::KNeutralLock<NDIS_MINIPORT_POLICY_OWNER>::TryAcquire(NDIS_MINIPORT_POLICY_OWNER)
0x14015ddb7  test    al, al
0x14015ddb9  jnz     loc_14015DEE8
0x14015ddbf  cmp     qword ptr [rbx+1168h], 0
0x14015ddc7  mov     byte ptr [rbx+14A0h], 1
0x14015ddce  mov     byte ptr [rdi], 1
0x14015ddd1  jz      short loc_14015DDE6
0x14015ddd3  mov     edx, 8
0x14015ddd8  mov     r8d, 1
0x14015ddde  mov     rcx, rbx
0x14015dde1  call    ?ndisAoAcStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@W4CallRunMode@@@Z; ndisAoAcStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON,CallRunMode)
0x14015dde6  cmp     byte ptr [rbx+14A1h], 0
0x14015dded  jnz     loc_14015DEE8
0x14015ddf3  lea     rdi, [rbx+1480h]
0x14015ddfa  mov     [rsp+38h+arg_0], rbp
0x14015ddff  add     rbx, 1488h
0x14015de06  xor     ebp, ebp
0x14015de08  nop     dword ptr [rax+rax+00000000h]
0x14015de10  call    cs:__imp_KeEnterCriticalRegion
0x14015de17  nop     dword ptr [rax+rax+00h]
0x14015de1c  xor     edx, edx
0x14015de1e  mov     rcx, rdi
0x14015de21  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14015de28  nop     dword ptr [rax+rax+00h]
0x14015de2d  mov     rcx, rbx; Event
0x14015de30  call    cs:__imp_KeReadStateEvent
0x14015de37  nop     dword ptr [rax+rax+00h]
0x14015de3c  test    eax, eax
0x14015de3e  jnz     short loc_14015DEB1
0x14015de40  xor     edx, edx
0x14015de42  mov     rcx, rdi
0x14015de45  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14015de4c  nop     dword ptr [rax+rax+00h]
0x14015de51  call    cs:__imp_KeLeaveCriticalRegion
0x14015de58  nop     dword ptr [rax+rax+00h]
0x14015de5d  mov     rax, ds:0FFFFF78000000014h
0x14015de67  xor     r9d, r9d; Alertable
0x14015de6a  xor     r8d, r8d; WaitMode
0x14015de6d  mov     [rsp+38h+Timeout], rbp; Timeout
0x14015de72  xor     edx, edx; WaitReason
0x14015de74  mov     rcx, rbx; Object
0x14015de77  call    cs:__imp_KeWaitForSingleObject
0x14015de7e  nop     dword ptr [rax+rax+00h]
0x14015de83  jmp     short loc_14015DE10
0x14015de85  test    rcx, rcx
0x14015de88  jz      loc_14015DDA3
0x14015de8e  lea     rcx, [rbx+78h]
0x14015de92  call    ??$ReadNoFence@KX@mem@@YAKPEDK@Z; mem::ReadNoFence<ulong,void>(ulong const volatile *)
0x14015de97  test    al, al
0x14015de99  jns     loc_14015DD96
0x14015de9f  mov     edx, 8
0x14015dea4  mov     rcx, rbx
0x14015dea7  call    ?ndisSelectiveSuspendStopWdf@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisSelectiveSuspendStopWdf(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x14015deac  jmp     loc_14015DDA3
0x14015deb1  mov     rcx, rbx; Event
0x14015deb4  call    cs:__imp_KeClearEvent
0x14015debb  nop     dword ptr [rax+rax+00h]
0x14015dec0  xor     edx, edx
0x14015dec2  mov     dword ptr [rsi], 2
0x14015dec8  mov     rcx, rdi
0x14015decb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14015ded2  nop     dword ptr [rax+rax+00h]
0x14015ded7  call    cs:__imp_KeLeaveCriticalRegion
0x14015dede  nop     dword ptr [rax+rax+00h]
0x14015dee3  mov     rbp, [rsp+38h+arg_0]
0x14015dee8  mov     rbx, [rsp+38h+arg_8]
0x14015deed  mov     rsi, [rsp+38h+arg_10]
0x14015def2  add     rsp, 30h
0x14015def6  pop     rdi
0x14015def7  retn
```
