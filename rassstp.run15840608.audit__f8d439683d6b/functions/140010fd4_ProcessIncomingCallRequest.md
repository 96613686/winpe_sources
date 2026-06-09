# ProcessIncomingCallRequest

- ea: `0x140010fd4`
- end: `0x1400114f9`
- name: `ProcessIncomingCallRequest`
- size: `1317`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002060`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140002c08`
- `0x140002f88`
- `0x140003068`
- `0x1400038d8`
- `0x140003938`
- `0x1400039f8`
- `0x140003ce0`
- `0x140003fc0`
- `0x140010254`
- `0x140010fd4`
- `0x140013eb0`
- `0x140019e70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001126c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400112ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001134f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001126c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400112ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001134f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011281`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011308`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001136a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011281`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011308`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001136a`
- `NDIS!NdisMCmCreateVc` at `0x140011198`
- `NDIS!NdisMCmCreateVc` at `0x140011198`
- `NDIS!NdisCmDispatchIncomingCall` at `0x1400113cf`
- `NDIS!NdisCmDispatchIncomingCall` at `0x1400113cf`
- `NDIS!NdisMCmDeleteVc` at `0x140011333`
- `NDIS!NdisMCmDeleteVc` at `0x140011333`

## pseudocode

```c
__int64 __fastcall ProcessIncomingCallRequest(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // r9
  __int64 v4; // r14
  unsigned int v5; // ecx
  unsigned int v6; // edx
  NDIS_STATUS Vc; // ebx
  char *v8; // rsi
  NDIS_HANDLE *v9; // r12
  __int64 v10; // rax
  struct _CO_CALL_PARAMETERS *v11; // r13
  KIRQL v12; // al
  KIRQL v13; // al
  KIRQL v14; // al
  __int64 v15; // rcx
  __int64 v16; // rcx
  NDIS_STATUS v17; // ebx
  __int64 v18; // r8
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  NDIS_HANDLE MiniportVcContext; // [rsp+60h] [rbp+8h] BYREF

  MiniportVcContext = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  v2 = *(_QWORD *)(a1 + 184);
  v3 = *(unsigned int *)(v2 + 16);
  if ( (unsigned int)v3 < 0x78 || *(_DWORD *)(v2 + 8) < 0x78u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_ddd(WPP_GLOBAL_Control->AttachedDevice);
    }
    goto LABEL_57;
  }
  v4 = *(_QWORD *)(a1 + 24);
  if ( *(unsigned int *)(v4 + 4) > (unsigned __int64)(v3 - 16)
    || *(unsigned int *)(v4 + 8) > (unsigned __int64)(v3 - 16) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_57;
    }
    v20 = 35;
    goto LABEL_48;
  }
  v5 = *(_DWORD *)(v4 + 112);
  v6 = v5 + *(_DWORD *)(v4 + 116);
  if ( v6 < v5 || v6 > (unsigned int)v3 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_57;
    }
    v20 = 36;
LABEL_48:
    WPP_SF_(v19->AttachedDevice, v20, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
LABEL_57:
    Vc = -1073741811;
    goto LABEL_58;
  }
  Vc = ScmCmCreateVc(0, 0, &MiniportVcContext);
  if ( Vc >= 0 )
  {
    v8 = (char *)MiniportVcContext;
    *((_BYTE *)MiniportVcContext + 505) = 1;
    *((_QWORD *)v8 + 2638) = *(_QWORD *)(v4 + 16);
    *((_QWORD *)v8 + 2639) = *(_QWORD *)(v4 + 24);
    *(_OWORD *)(v8 + 297) = *(_OWORD *)(v4 + 40);
    *(_DWORD *)(v8 + 313) = *(_DWORD *)(v4 + 56);
    *(_OWORD *)(v8 + 317) = *(_OWORD *)(v4 + 60);
    *(_OWORD *)(v8 + 333) = *(_OWORD *)(v4 + 76);
    *(_OWORD *)(v8 + 484) = *(_OWORD *)(v4 + 96);
    v8[296] = *(_BYTE *)(v4 + 92);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, v8 + 484);
    }
    v9 = (NDIS_HANDLE *)(v8 + 40);
    Vc = NdisMCmCreateVc(
           *((NDIS_HANDLE *)SstpGlobals + 21),
           *((NDIS_HANDLE *)SstpGlobals + 6),
           v8,
           (PNDIS_HANDLE)v8 + 5);
    if ( Vc )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF__guid_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          (unsigned int)WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
          (_DWORD)v8 + 484,
          Vc,
          Vc);
      }
    }
    else
    {
      v10 = BuildCallParams(v4);
      v11 = (struct _CO_CALL_PARAMETERS *)v10;
      if ( v10 )
      {
        *((_QWORD *)v8 + 2631) = v10;
        *(_QWORD *)(a1 + 120) = v8;
        *((_DWORD *)v8 + 29) = *(_DWORD *)v4;
        _InterlockedIncrement((volatile signed __int32 *)v8);
        v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v8 + 4);
        *((_QWORD *)v8 + 7) = a1;
        KeReleaseSpinLock((PKSPIN_LOCK)v8 + 4, v12);
        if ( (unsigned __int8)SetCancelRoutineSafe(a1, &DispatchIncomingCallCancelIrp) )
        {
          v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v8 + 4);
          *((_DWORD *)v8 + 5272) |= 0x101u;
          KeReleaseSpinLock((PKSPIN_LOCK)v8 + 4, v14);
          v15 = *((_QWORD *)v8 + 2638) >> 3;
          v11->CallMgrParameters->Transmit.TokenRate = v15;
          v11->CallMgrParameters->Transmit.PeakBandwidth = v15;
          v11->CallMgrParameters->Transmit.MaxSduSize = 4095;
          v16 = *((_QWORD *)v8 + 2639) >> 3;
          v11->CallMgrParameters->Receive.TokenRate = v16;
          v11->CallMgrParameters->Receive.PeakBandwidth = v16;
          v11->CallMgrParameters->Receive.MaxSduSize = 4095;
          v17 = NdisCmDispatchIncomingCall(*((NDIS_HANDLE *)SstpGlobals + 57), *v9, v11);
          if ( v17 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF__guid_dD(WPP_GLOBAL_Control->AttachedDevice, 42, v18, v8 + 484, v17, v17);
            }
            ScmCmIncomingCallComplete((unsigned int)v17, v8, v11);
          }
          Vc = 259;
          goto LABEL_58;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF__guid_(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
            v8 + 484);
        }
        Vc = -1073741536;
        *(_QWORD *)(a1 + 56) = 0;
        *(_DWORD *)(a1 + 48) = -1073741536;
        v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v8 + 4);
        *((_QWORD *)v8 + 7) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)v8 + 4, v13);
        DereferenceRefCount(v8);
        FreeCallParams(v11);
        *((_QWORD *)v8 + 2631) = 0;
      }
      else
      {
        Vc = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF__guid_(
            WPP_GLOBAL_Control->AttachedDevice,
            40,
            WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
            v8 + 484);
        }
      }
      NdisMCmDeleteVc(*v9);
    }
    ScmCmDeleteVc(v8);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)Vc;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  }
LABEL_58:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x82) == 0x82 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids);
  return (unsigned int)Vc;
}

```

## disassembly

```asm
0x140010fd4  mov     [rsp+arg_8], rbx
0x140010fd9  mov     [rsp+arg_10], rbp
0x140010fde  push    rsi
0x140010fdf  push    r12
0x140010fe1  push    r13
0x140010fe3  push    r14
0x140010fe5  push    r15
0x140010fe7  sub     rsp, 30h
0x140010feb  mov     rbp, rcx
0x140010fee  mov     [rsp+58h+MiniportVcContext], 0
0x140010ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ffe  lea     r13, WPP_GLOBAL_Control
0x140011005  cmp     rcx, r13
0x140011008  jz      short loc_14001102B
0x14001100a  mov     eax, [rcx+2Ch]
0x14001100d  and     eax, 82h
0x140011012  cmp     al, 82h
0x140011014  jnz     short loc_14001102B
0x140011016  mov     rcx, [rcx+18h]
0x14001101a  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011021  mov     edx, 21h ; '!'
0x140011026  call    WPP_SF_
0x14001102b  mov     rax, [rbp+0B8h]
0x140011032  mov     r9d, [rax+10h]
0x140011036  mov     edx, [rax+8]
0x140011039  cmp     r9d, 78h ; 'x'
0x14001103d  jb      loc_14001147F
0x140011043  cmp     edx, 78h ; 'x'
0x140011046  jb      loc_14001147F
0x14001104c  mov     r14, [rbp+18h]
0x140011050  lea     rcx, [r9-10h]
0x140011054  mov     eax, [r14+4]
0x140011058  cmp     rax, rcx
0x14001105b  ja      loc_14001145F
0x140011061  mov     eax, [r14+8]
0x140011065  cmp     rax, rcx
0x140011068  ja      loc_14001145F
0x14001106e  mov     ecx, [r14+70h]
0x140011072  mov     edx, [r14+74h]
0x140011076  add     edx, ecx
0x140011078  cmp     edx, ecx
0x14001107a  jb      loc_14001142F
0x140011080  cmp     edx, r9d
0x140011083  ja      loc_14001142F
0x140011089  lea     r8, [rsp+58h+MiniportVcContext]
0x14001108e  xor     edx, edx
0x140011090  xor     ecx, ecx
0x140011092  call    ScmCmCreateVc
0x140011097  mov     ebx, eax
0x140011099  test    eax, eax
0x14001109b  jns     short loc_1400110E0
0x14001109d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110a4  cmp     rcx, r13
0x1400110a7  jz      loc_1400114DE
0x1400110ad  mov     edx, [rcx+2Ch]
0x1400110b0  test    dl, 2
0x1400110b3  jz      loc_1400114AA
0x1400110b9  cmp     byte ptr [rcx+29h], 1
0x1400110bd  jb      loc_1400114AA
0x1400110c3  mov     rcx, [rcx+18h]
0x1400110c7  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400110ce  mov     edx, 25h ; '%'
0x1400110d3  mov     r9d, eax
0x1400110d6  call    WPP_SF_d
0x1400110db  jmp     loc_1400114AA
0x1400110e0  mov     rsi, [rsp+58h+MiniportVcContext]
0x1400110e5  mov     byte ptr [rsi+1F9h], 1
0x1400110ec  lea     r15, [rsi+1E4h]
0x1400110f3  mov     rax, [r14+10h]
0x1400110f7  mov     [rsi+5270h], rax
0x1400110fe  mov     rax, [r14+18h]
0x140011102  mov     [rsi+5278h], rax
0x140011109  movups  xmm0, xmmword ptr [r14+28h]
0x14001110e  movups  xmmword ptr [rsi+129h], xmm0
0x140011115  mov     eax, [r14+38h]
0x140011119  mov     [rsi+139h], eax
0x14001111f  movups  xmm0, xmmword ptr [r14+3Ch]
0x140011124  movups  xmmword ptr [rsi+13Dh], xmm0
0x14001112b  movups  xmm1, xmmword ptr [r14+4Ch]
0x140011130  movups  xmmword ptr [rsi+14Dh], xmm1
0x140011137  movups  xmm0, xmmword ptr [r14+60h]
0x14001113c  movdqu  xmmword ptr [r15], xmm0
0x140011141  mov     al, [r14+5Ch]
0x140011145  mov     [rsi+128h], al
0x14001114b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011152  cmp     rcx, r13
0x140011155  jz      short loc_14001117C
0x140011157  mov     eax, [rcx+2Ch]
0x14001115a  test    al, 2
0x14001115c  jz      short loc_14001117C
0x14001115e  cmp     byte ptr [rcx+29h], 3
0x140011162  jb      short loc_14001117C
0x140011164  mov     rcx, [rcx+18h]
0x140011168  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001116f  mov     edx, 26h ; '&'
0x140011174  mov     r9, r15
0x140011177  call    WPP_SF__guid_
0x14001117c  mov     rcx, cs:SstpGlobals
0x140011183  lea     r12, [rsi+28h]
0x140011187  mov     r9, r12; NdisVcHandle
0x14001118a  mov     r8, rsi; MiniportVcContext
0x14001118d  mov     rdx, [rcx+30h]; NdisAfHandle
0x140011191  mov     rcx, [rcx+0A8h]; MiniportAdapterHandle
0x140011198  call    cs:__imp_NdisMCmCreateVc
0x14001119f  nop     dword ptr [rax+rax+00h]
0x1400111a4  mov     ebx, eax
0x1400111a6  test    eax, eax
0x1400111a8  jz      short loc_1400111F4
0x1400111aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111b1  cmp     rcx, r13
0x1400111b4  jz      loc_14001133F
0x1400111ba  mov     eax, [rcx+2Ch]
0x1400111bd  test    al, 1
0x1400111bf  jz      loc_14001133F
0x1400111c5  cmp     byte ptr [rcx+29h], 1
0x1400111c9  jb      loc_14001133F
0x1400111cf  mov     rcx, [rcx+18h]
0x1400111d3  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400111da  mov     edx, 27h ; '''
0x1400111df  mov     [rsp+58h+var_30], ebx
0x1400111e3  mov     r9, r15
0x1400111e6  mov     [rsp+58h+var_38], ebx
0x1400111ea  call    WPP_SF__guid_dd
0x1400111ef  jmp     loc_14001133F
0x1400111f4  mov     rcx, r14
0x1400111f7  call    BuildCallParams
0x1400111fc  mov     r13, rax
0x1400111ff  test    rax, rax
0x140011202  jnz     short loc_140011251
0x140011204  mov     ebx, 0C000009Ah
0x140011209  mov     rcx, cs:WPP_GLOBAL_Control
0x140011210  lea     rax, WPP_GLOBAL_Control
0x140011217  cmp     rcx, rax
0x14001121a  jz      loc_14001132F
0x140011220  mov     eax, [rcx+2Ch]
0x140011223  test    al, 1
0x140011225  jz      loc_14001132F
0x14001122b  cmp     byte ptr [rcx+29h], 1
0x14001122f  jb      loc_14001132F
0x140011235  mov     rcx, [rcx+18h]
0x140011239  lea     edx, [r13+28h]
0x14001123d  mov     r9, r15
0x140011240  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011247  call    WPP_SF__guid_
0x14001124c  jmp     loc_14001132F
0x140011251  mov     [rsi+5238h], r13
0x140011258  mov     [rbp+78h], rsi
0x14001125c  mov     eax, [r14]
0x14001125f  mov     [rsi+74h], eax
0x140011262  lock inc dword ptr [rsi]
0x140011265  lea     r14, [rsi+20h]
0x140011269  mov     rcx, r14; SpinLock
0x14001126c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011273  nop     dword ptr [rax+rax+00h]
0x140011278  mov     rcx, r14; SpinLock
0x14001127b  mov     [rsi+38h], rbp
0x14001127f  mov     dl, al; NewIrql
0x140011281  call    cs:__imp_KeReleaseSpinLock
0x140011288  nop     dword ptr [rax+rax+00h]
0x14001128d  lea     rdx, DispatchIncomingCallCancelIrp
0x140011294  mov     rcx, rbp
0x140011297  call    SetCancelRoutineSafe
0x14001129c  test    al, al
0x14001129e  jnz     loc_14001134C
0x1400112a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112ab  lea     rax, WPP_GLOBAL_Control
0x1400112b2  cmp     rcx, rax
0x1400112b5  jz      short loc_1400112DC
0x1400112b7  mov     eax, [rcx+2Ch]
0x1400112ba  test    al, 2
0x1400112bc  jz      short loc_1400112DC
0x1400112be  cmp     byte ptr [rcx+29h], 1
0x1400112c2  jb      short loc_1400112DC
0x1400112c4  mov     rcx, [rcx+18h]
0x1400112c8  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400112cf  mov     edx, 29h ; ')'
0x1400112d4  mov     r9, r15
0x1400112d7  call    WPP_SF__guid_
0x1400112dc  mov     ebx, 0C0000120h
0x1400112e1  mov     qword ptr [rbp+38h], 0
0x1400112e9  mov     rcx, r14; SpinLock
0x1400112ec  mov     [rbp+30h], ebx
0x1400112ef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400112f6  nop     dword ptr [rax+rax+00h]
0x1400112fb  mov     rcx, r14; SpinLock
0x1400112fe  mov     qword ptr [rsi+38h], 0
0x140011306  mov     dl, al; NewIrql
0x140011308  call    cs:__imp_KeReleaseSpinLock
0x14001130f  nop     dword ptr [rax+rax+00h]
0x140011314  mov     rcx, rsi
0x140011317  call    DereferenceRefCount
0x14001131c  mov     rcx, r13
0x14001131f  call    FreeCallParams
0x140011324  mov     qword ptr [rsi+5238h], 0
0x14001132f  mov     rcx, [r12]; NdisVcHandle
0x140011333  call    cs:__imp_NdisMCmDeleteVc
0x14001133a  nop     dword ptr [rax+rax+00h]
0x14001133f  mov     rcx, rsi
0x140011342  call    ScmCmDeleteVc
0x140011347  jmp     loc_1400114AA
0x14001134c  mov     rcx, r14; SpinLock
0x14001134f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011356  nop     dword ptr [rax+rax+00h]
0x14001135b  or      dword ptr [rsi+5260h], 101h
0x140011365  mov     rcx, r14; SpinLock
0x140011368  mov     dl, al; NewIrql
0x14001136a  call    cs:__imp_KeReleaseSpinLock
0x140011371  nop     dword ptr [rax+rax+00h]
0x140011376  mov     rax, [r13+8]
0x14001137a  mov     edx, 0FFFh
0x14001137f  mov     rcx, [rsi+5270h]
0x140011386  mov     r8, r13; CallParameters
0x140011389  shr     rcx, 3
0x14001138d  mov     [rax], ecx
0x14001138f  mov     rax, [r13+8]
0x140011393  mov     [rax+8], ecx
0x140011396  mov     rax, [r13+8]
0x14001139a  mov     [rax+18h], edx
0x14001139d  mov     rax, [r13+8]
0x1400113a1  mov     rcx, [rsi+5278h]
0x1400113a8  shr     rcx, 3
0x1400113ac  mov     [rax+20h], ecx
0x1400113af  mov     rax, [r13+8]
0x1400113b3  mov     [rax+28h], ecx
0x1400113b6  mov     rax, [r13+8]
0x1400113ba  mov     [rax+38h], edx
0x1400113bd  mov     rcx, cs:SstpGlobals
0x1400113c4  mov     rdx, [r12]; NdisVcHandle
0x1400113c8  mov     rcx, [rcx+1C8h]; NdisSapHandle
0x1400113cf  call    cs:__imp_NdisCmDispatchIncomingCall
0x1400113d6  nop     dword ptr [rax+rax+00h]
0x1400113db  mov     ebx, eax
0x1400113dd  test    eax, eax
0x1400113df  jns     short loc_140011428
0x1400113e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113e8  lea     rax, WPP_GLOBAL_Control
0x1400113ef  cmp     rcx, rax
0x1400113f2  jz      short loc_14001141B
0x1400113f4  mov     edx, [rcx+2Ch]
0x1400113f7  test    dl, 1
0x1400113fa  jz      short loc_14001141B
0x1400113fc  cmp     byte ptr [rcx+29h], 1
0x140011400  jb      short loc_14001141B
0x140011402  mov     rcx, [rcx+18h]
0x140011406  mov     edx, 2Ah ; '*'
0x14001140b  mov     [rsp+58h+var_30], ebx
0x14001140f  mov     r9, r15
0x140011412  mov     [rsp+58h+var_38], ebx
0x140011416  call    WPP_SF__guid_dD
0x14001141b  mov     r8, r13
0x14001141e  mov     rdx, rsi
0x140011421  mov     ecx, ebx
0x140011423  call    ScmCmIncomingCallComplete
0x140011428  mov     ebx, 103h
0x14001142d  jmp     short loc_1400114AA
0x14001142f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011436  cmp     rcx, r13
0x140011439  jz      short loc_1400114A5
0x14001143b  mov     eax, [rcx+2Ch]
0x14001143e  test    al, 2
0x140011440  jz      short loc_1400114A5
0x140011442  cmp     byte ptr [rcx+29h], 1
0x140011446  jb      short loc_1400114A5
0x140011448  mov     edx, 24h ; '$'
0x14001144d  mov     rcx, [rcx+18h]
0x140011451  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140011458  call    WPP_SF_
0x14001145d  jmp     short loc_1400114A5
0x14001145f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011466  cmp     rcx, r13
0x140011469  jz      short loc_1400114A5
0x14001146b  mov     eax, [rcx+2Ch]
0x14001146e  test    al, 2
0x140011470  jz      short loc_1400114A5
0x140011472  cmp     byte ptr [rcx+29h], 1
0x140011476  jb      short loc_1400114A5
0x140011478  mov     edx, 23h ; '#'
0x14001147d  jmp     short loc_14001144D
0x14001147f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011486  cmp     rcx, r13
0x140011489  jz      short loc_1400114A5
0x14001148b  mov     eax, [rcx+2Ch]
0x14001148e  test    al, 2
0x140011490  jz      short loc_1400114A5
0x140011492  cmp     byte ptr [rcx+29h], 1
0x140011496  jb      short loc_1400114A5
0x140011498  mov     rcx, [rcx+18h]
0x14001149c  mov     [rsp+58h+var_38], edx
0x1400114a0  call    WPP_SF_ddd
0x1400114a5  mov     ebx, 0C000000Dh
0x1400114aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114b1  lea     rax, WPP_GLOBAL_Control
0x1400114b8  cmp     rcx, rax
0x1400114bb  jz      short loc_1400114DE
0x1400114bd  mov     eax, [rcx+2Ch]
0x1400114c0  and     eax, 82h
0x1400114c5  cmp     al, 82h
0x1400114c7  jnz     short loc_1400114DE
0x1400114c9  mov     rcx, [rcx+18h]
0x1400114cd  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
  ... truncated ...
```
