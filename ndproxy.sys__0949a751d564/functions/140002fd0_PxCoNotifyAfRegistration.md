# PxCoNotifyAfRegistration

- ea: `0x140002fd0`
- end: `0x140003727`
- name: `PxCoNotifyAfRegistration`
- size: `1879`
- prototype: `__int64 __fastcall(PVOID P, PCO_ADDRESS_FAMILY AddressFamily)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140001030`
- `0x140001b54`
- `0x140001bc8`
- `0x140001c0c`
- `0x140002fd0`
- `0x140004628`
- `0x1400062c0`
- `0x1400078f0`
- `0x140007b44`
- `0x140007bf8`
- `0x140007fc0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003104`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000335c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000348e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003533`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000362f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003665`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400030c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003104`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000335c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400033b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000348e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003533`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000362f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003665`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000322a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000322a`
- `ntoskrnl!ExAllocatePool2` at `0x1400031bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400031bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003304`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400033ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003416`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003524`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003551`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003590`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400035c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003656`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400036df`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400036f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003304`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400033ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003416`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003524`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003551`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003590`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400035c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003656`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400036df`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400036f5`
- `NDIS!NdisInitializeEvent` at `0x140003214`
- `NDIS!NdisInitializeEvent` at `0x1400032e9`
- `NDIS!NdisInitializeEvent` at `0x140003313`
- `NDIS!NdisInitializeEvent` at `0x140003214`
- `NDIS!NdisInitializeEvent` at `0x1400032e9`
- `NDIS!NdisInitializeEvent` at `0x140003313`
- `NDIS!NdisWaitEvent` at `0x1400030f5`
- `NDIS!NdisWaitEvent` at `0x140003347`
- `NDIS!NdisWaitEvent` at `0x1400030f5`
- `NDIS!NdisWaitEvent` at `0x140003347`
- `NDIS!NdisSetEvent` at `0x140003691`
- `NDIS!NdisSetEvent` at `0x140003691`
- `NDIS!NdisClOpenAddressFamilyEx` at `0x14000332d`
- `NDIS!NdisClOpenAddressFamilyEx` at `0x14000332d`
- `NDIS!NdisCmRegisterAddressFamilyEx` at `0x14000347d`
- `NDIS!NdisCmRegisterAddressFamilyEx` at `0x14000347d`
- `NDIS!NdisClCloseAddressFamily` at `0x140003561`
- `NDIS!NdisClCloseAddressFamily` at `0x140003561`

## pseudocode

```c
void __fastcall PxCoNotifyAfRegistration(char *P, PCO_ADDRESS_FAMILY AddressFamily)
{
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  KIRQL v6; // al
  char *v7; // r15
  char *v8; // rax
  int v9; // r8d
  __int64 Pool2; // rax
  __int64 v11; // rdi
  struct _NDIS_EVENT *v12; // r13
  KIRQL v13; // dl
  NDIS_STATUS v14; // ebp
  __int64 v15; // rdx
  __int64 v16; // r8
  KIRQL v17; // al
  __int64 *v18; // rax
  int v19; // eax
  char v20; // bp
  KIRQL v21; // dl
  ULONG MinorVersion; // eax
  NDIS_STATUS v23; // ebp
  KIRQL v24; // al
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 *v27; // rdx
  KIRQL v28; // al
  NDIS_STATUS v29; // eax
  KIRQL v30; // al
  KIRQL v31; // al
  bool v32; // zf
  KSPIN_LOCK *v33; // rcx
  KIRQL v34; // dl
  $0563D17F902D53081481BDEBB46755BB AddressFamilya; // [rsp+38h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
  if ( AddressFamily->AddressFamily == 2048 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v5 = 30;
LABEL_8:
      WPP_SF_(v4->AttachedDevice, v5, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
      return;
    }
    return;
  }
  if ( AddressFamily->AddressFamily == 2049 )
  {
    if ( *(_DWORD *)P == 538996035 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v5 = 32;
        goto LABEL_8;
      }
      return;
    }
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 78);
    ++*((_DWORD *)P + 6);
    P[632] = v6;
    KeReleaseSpinLock((PKSPIN_LOCK)P + 78, v6);
    NdisWaitEvent((PNDIS_EVENT)P + 23, 0);
    P[632] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 78);
    if ( *((_DWORD *)P + 5) <= 1u )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_55e376f2a9f936ee4a212904c2347983_Traceguids,
          P,
          *((_DWORD *)P + 5));
      goto LABEL_79;
    }
    v7 = P + 40;
    v8 = (char *)*((_QWORD *)P + 5);
    if ( v8 != P + 40 )
    {
      while ( 1 )
      {
        v9 = *((_DWORD *)v8 + 35);
        if ( v9 == AddressFamily->AddressFamily )
          break;
        v8 = *(char **)v8;
        if ( v8 == v7 )
          goto LABEL_21;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids, P, v9);
      goto LABEL_79;
    }
LABEL_21:
    if ( AddressFamily->AddressFamily != 2049 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids);
      goto LABEL_29;
    }
    Pool2 = ExAllocatePool2(64, 208, 6838352);
    v11 = Pool2;
    if ( !Pool2 )
    {
LABEL_29:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
LABEL_79:
      v32 = (*((_DWORD *)P + 6))-- == 1;
      v33 = (KSPIN_LOCK *)(P + 624);
      v34 = P[632];
      if ( v32 )
      {
        KeReleaseSpinLock(v33, v34);
        PxFreeAdapter(P);
      }
      else
      {
        KeReleaseSpinLock(v33, v34);
      }
      return;
    }
    v12 = (struct _NDIS_EVENT *)(Pool2 + 152);
    NdisInitializeEvent((PNDIS_EVENT)(Pool2 + 152));
    KeInitializeSpinLock((PKSPIN_LOCK)(v11 + 184));
    *(_QWORD *)(v11 + 140) = *(_QWORD *)&AddressFamily->AddressFamily;
    *(_DWORD *)(v11 + 148) = AddressFamily->MinorVersion;
    *(_QWORD *)(v11 + 48) = v11 + 40;
    *(_QWORD *)(v11 + 40) = v11 + 40;
    *(_QWORD *)(v11 + 64) = v11 + 56;
    *(_QWORD *)(v11 + 56) = v11 + 56;
    *(_QWORD *)(v11 + 80) = v11 + 72;
    *(_QWORD *)(v11 + 72) = v11 + 72;
    *(_QWORD *)(v11 + 96) = v11 + 88;
    *(_QWORD *)(v11 + 88) = v11 + 88;
    *(_QWORD *)(v11 + 112) = PxAfTapiTranslateTapiCallParams;
    *(_QWORD *)(v11 + 120) = PxAfTapiTranslateNdisCallParams;
    *(_QWORD *)(v11 + 128) = PxAfTapiTranslateTapiSap;
    *(_DWORD *)(v11 + 16) = 2;
    *(_DWORD *)(v11 + 20) = 1;
    *(_QWORD *)(v11 + 32) = P;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids, v11);
    if ( !*((_DWORD *)P + 154) )
      NdisInitializeEvent((PNDIS_EVENT)(P + 584));
    v13 = P[632];
    ++*((_DWORD *)P + 154);
    KeReleaseSpinLock((PKSPIN_LOCK)P + 78, v13);
    NdisInitializeEvent(v12);
    v14 = NdisClOpenAddressFamilyEx(*((NDIS_HANDLE *)P + 4), AddressFamily, (NDIS_HANDLE)v11, (PNDIS_HANDLE)(v11 + 24));
    if ( v14 == 259 )
    {
      NdisWaitEvent(v12, 0);
      v14 = *(_DWORD *)(v11 + 176);
    }
    P[632] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 78);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_DqD(WPP_GLOBAL_Control->AttachedDevice, v15, v16, AddressFamily->AddressFamily, P, v14);
      PxFreeClAf((PVOID)v11);
      goto LABEL_73;
    }
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 184));
    *(_DWORD *)(v11 + 16) = 3;
    *(_BYTE *)(v11 + 192) = v17;
    KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 184), v17);
    v18 = (__int64 *)*((_QWORD *)P + 6);
    if ( (char *)*v18 != v7 )
      goto LABEL_75;
    *(_QWORD *)v11 = v7;
    *(_QWORD *)(v11 + 8) = v18;
    *v18 = v11;
    *((_QWORD *)P + 6) = v11;
    v19 = *((_DWORD *)P + 7);
    if ( (v19 & 2) != 0 )
    {
      v20 = 1;
    }
    else
    {
      v20 = 0;
      *((_DWORD *)P + 7) = v19 | 1;
    }
    v21 = P[632];
    ++*((_DWORD *)P + 6);
    KeReleaseSpinLock((PKSPIN_LOCK)P + 78, v21);
    if ( !v20 )
    {
      MinorVersion = AddressFamily->MinorVersion;
      AddressFamilya.MajorVersion = HIDWORD(*(_QWORD *)&AddressFamily->AddressFamily);
      AddressFamilya.AddressFamily = 2048;
      AddressFamilya.MinorVersion = MinorVersion;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids);
      v23 = NdisCmRegisterAddressFamilyEx(*((NDIS_HANDLE *)P + 9), &AddressFamilya);
      v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 78);
      *((_DWORD *)P + 7) &= ~1u;
      P[632] = v24;
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            38,
            WPP_55e376f2a9f936ee4a212904c2347983_Traceguids,
            *((_QWORD *)P + 9),
            v23);
        v25 = *(_QWORD *)v11;
        if ( *(_QWORD *)(*(_QWORD *)v11 + 8LL) == v11 )
        {
          v26 = *(_QWORD **)(v11 + 8);
          if ( *v26 == v11 )
          {
            *v26 = v25;
            *(_QWORD *)(v25 + 8) = v26;
            v27 = (__int64 *)*((_QWORD *)P + 8);
            if ( (char *)*v27 == P + 56 )
            {
              *(_QWORD *)v11 = P + 56;
              *(_QWORD *)(v11 + 8) = v27;
              *v27 = v11;
              *((_QWORD *)P + 8) = v11;
              KeReleaseSpinLock((PKSPIN_LOCK)P + 78, P[632]);
              v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 184));
              *(_DWORD *)(v11 + 16) = 1;
              *(_BYTE *)(v11 + 192) = v28;
              KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 184), v28);
              v29 = NdisClCloseAddressFamily(*(NDIS_HANDLE *)(v11 + 24));
              if ( v29 != 259 )
                PxClCloseAfComplete(v29, (void *)v11);
LABEL_72:
              P[632] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 78);
LABEL_73:
              v32 = (*((_DWORD *)P + 154))-- == 1;
              if ( v32 )
              {
                *((_DWORD *)P + 152) = 0;
                NdisSetEvent((PNDIS_EVENT)(P + 584));
              }
              goto LABEL_79;
            }
          }
        }
LABEL_75:
        __fastfail(3u);
      }
      *((_DWORD *)P + 7) |= 2u;
      KeReleaseSpinLock((PKSPIN_LOCK)P + 78, v24);
    }
    v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 184));
    ++*(_DWORD *)(v11 + 20);
    *(_BYTE *)(v11 + 192) = v30;
    KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 184), v30);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    if ( !AllocateTapiProvider((__int64)P, v11)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    }
    v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 184));
    v32 = (*(_DWORD *)(v11 + 20))-- == 1;
    *(_BYTE *)(v11 + 192) = v31;
    if ( v32 )
      DoDerefClAfWork(v11);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 184), v31);
    goto LABEL_72;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v5 = 31;
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x140002fd0  mov     [rsp+arg_10], rbx
0x140002fd5  push    rbp
0x140002fd6  push    rsi
0x140002fd7  push    rdi
0x140002fd8  push    r12
0x140002fda  push    r13
0x140002fdc  push    r14
0x140002fde  push    r15
0x140002fe0  sub     rsp, 50h
0x140002fe4  mov     rax, cs:__security_cookie
0x140002feb  xor     rax, rsp
0x140002fee  mov     [rsp+88h+var_40], rax
0x140002ff3  mov     r14, rdx
0x140002ff6  mov     rbx, rcx
0x140002ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003000  lea     rbp, WPP_GLOBAL_Control
0x140003007  lea     rdi, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x14000300e  mov     r12b, 5
0x140003011  cmp     rcx, rbp
0x140003014  jz      short loc_14000302D
0x140003016  cmp     [rcx+29h], r12b
0x14000301a  jb      short loc_14000302D
0x14000301c  mov     rcx, [rcx+18h]
0x140003020  mov     edx, 1Dh
0x140003025  mov     r8, rdi
0x140003028  call    WPP_SF_
0x14000302d  mov     eax, [r14]
0x140003030  cmp     eax, 800h
0x140003035  jnz     short loc_140003067
0x140003037  mov     rcx, cs:WPP_GLOBAL_Control
0x14000303e  cmp     rcx, rbp
0x140003041  jz      loc_140003701
0x140003047  cmp     [rcx+29h], r12b
0x14000304b  jb      loc_140003701
0x140003051  mov     edx, 1Eh
0x140003056  mov     rcx, [rcx+18h]
0x14000305a  mov     r8, rdi
0x14000305d  call    WPP_SF_
0x140003062  jmp     loc_140003701
0x140003067  mov     r13d, 801h
0x14000306d  cmp     eax, r13d
0x140003070  jz      short loc_140003093
0x140003072  mov     rcx, cs:WPP_GLOBAL_Control
0x140003079  cmp     rcx, rbp
0x14000307c  jz      loc_140003701
0x140003082  cmp     [rcx+29h], r12b
0x140003086  jb      loc_140003701
0x14000308c  mov     edx, 1Fh
0x140003091  jmp     short loc_140003056
0x140003093  cmp     dword ptr [rbx], 20206D43h
0x140003099  jnz     short loc_1400030BC
0x14000309b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030a2  cmp     rcx, rbp
0x1400030a5  jz      loc_140003701
0x1400030ab  cmp     [rcx+29h], r12b
0x1400030af  jb      loc_140003701
0x1400030b5  mov     edx, 20h ; ' '
0x1400030ba  jmp     short loc_140003056
0x1400030bc  lea     rsi, [rbx+270h]
0x1400030c3  mov     rcx, rsi; SpinLock
0x1400030c6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400030cd  nop     dword ptr [rax+rax+00h]
0x1400030d2  inc     dword ptr [rbx+18h]
0x1400030d5  mov     rcx, rsi; SpinLock
0x1400030d8  mov     dl, al; NewIrql
0x1400030da  mov     [rbx+278h], al
0x1400030e0  call    cs:__imp_KeReleaseSpinLock
0x1400030e7  nop     dword ptr [rax+rax+00h]
0x1400030ec  lea     rcx, [rbx+228h]; Event
0x1400030f3  xor     edx, edx; MsToWait
0x1400030f5  call    cs:__imp_NdisWaitEvent
0x1400030fc  nop     dword ptr [rax+rax+00h]
0x140003101  mov     rcx, rsi; SpinLock
0x140003104  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000310b  nop     dword ptr [rax+rax+00h]
0x140003110  mov     [rbx+278h], al
0x140003116  mov     eax, [rbx+14h]
0x140003119  cmp     eax, 1
0x14000311c  jbe     loc_1400036A6
0x140003122  lea     r15, [rbx+28h]
0x140003126  mov     rax, [r15]
0x140003129  cmp     rax, r15
0x14000312c  jz      short loc_140003145
0x14000312e  mov     ecx, [r14]
0x140003131  mov     r8d, [rax+8Ch]
0x140003138  cmp     r8d, ecx
0x14000313b  jz      short loc_140003177
0x14000313d  mov     rax, [rax]
0x140003140  cmp     rax, r15
0x140003143  jnz     short loc_140003131
0x140003145  cmp     [r14], r13d
0x140003148  jz      short loc_1400031AF
0x14000314a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003151  cmp     rcx, rbp
0x140003154  jz      loc_1400031DA
0x14000315a  cmp     [rcx+29h], r12b
0x14000315e  jb      short loc_1400031DA
0x140003160  mov     rcx, [rcx+18h]
0x140003164  lea     r8, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids
0x14000316b  mov     edx, 0Eh
0x140003170  call    WPP_SF_
0x140003175  jmp     short loc_1400031DA
0x140003177  mov     rcx, cs:WPP_GLOBAL_Control
0x14000317e  cmp     rcx, rbp
0x140003181  jz      loc_1400036D0
0x140003187  cmp     byte ptr [rcx+29h], 1
0x14000318b  jb      loc_1400036D0
0x140003191  mov     rcx, [rcx+18h]
0x140003195  mov     edx, 22h ; '"'
0x14000319a  mov     dword ptr [rsp+88h+var_68], r8d
0x14000319f  mov     r9, rbx
0x1400031a2  mov     r8, rdi
0x1400031a5  call    WPP_SF_qD
0x1400031aa  jmp     loc_1400036D0
0x1400031af  mov     edx, 0D0h
0x1400031b4  mov     ecx, 40h ; '@'
0x1400031b9  mov     r8d, 685850h
0x1400031bf  call    cs:__imp_ExAllocatePool2
0x1400031c6  nop     dword ptr [rax+rax+00h]
0x1400031cb  mov     rdi, rax
0x1400031ce  test    rax, rax
0x1400031d1  jnz     short loc_14000320A
0x1400031d3  lea     rdi, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x1400031da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400031e1  cmp     rcx, rbp
0x1400031e4  jz      loc_1400036D0
0x1400031ea  cmp     byte ptr [rcx+29h], 3
0x1400031ee  jb      loc_1400036D0
0x1400031f4  mov     rcx, [rcx+18h]
0x1400031f8  mov     edx, 23h ; '#'
0x1400031fd  mov     r8, rdi
0x140003200  call    WPP_SF_
0x140003205  jmp     loc_1400036D0
0x14000320a  lea     r13, [rax+98h]
0x140003211  mov     rcx, r13; Event
0x140003214  call    cs:__imp_NdisInitializeEvent
0x14000321b  nop     dword ptr [rax+rax+00h]
0x140003220  lea     r12, [rdi+0B8h]
0x140003227  mov     rcx, r12; SpinLock
0x14000322a  call    cs:__imp_KeInitializeSpinLock
0x140003231  nop     dword ptr [rax+rax+00h]
0x140003236  movsd   xmm0, qword ptr [r14]
0x14000323b  movsd   qword ptr [rdi+8Ch], xmm0
0x140003243  mov     eax, [r14+8]
0x140003247  mov     [rdi+94h], eax
0x14000324d  lea     rax, [rdi+28h]
0x140003251  mov     [rax+8], rax
0x140003255  mov     [rax], rax
0x140003258  lea     rax, [rdi+38h]
0x14000325c  mov     [rax+8], rax
0x140003260  mov     [rax], rax
0x140003263  lea     rax, [rdi+48h]
0x140003267  mov     [rax+8], rax
0x14000326b  mov     [rax], rax
0x14000326e  lea     rax, [rdi+58h]
0x140003272  mov     [rax+8], rax
0x140003276  mov     [rax], rax
0x140003279  lea     rax, PxAfTapiTranslateTapiCallParams
0x140003280  mov     [rdi+70h], rax
0x140003284  lea     rax, PxAfTapiTranslateNdisCallParams
0x14000328b  mov     [rdi+78h], rax
0x14000328f  lea     rax, PxAfTapiTranslateTapiSap
0x140003296  mov     [rdi+80h], rax
0x14000329d  mov     dword ptr [rdi+10h], 2
0x1400032a4  mov     dword ptr [rdi+14h], 1
0x1400032ab  mov     [rdi+20h], rbx
0x1400032af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032b6  cmp     rcx, rbp
0x1400032b9  jz      short loc_1400032D9
0x1400032bb  cmp     byte ptr [rcx+29h], 4
0x1400032bf  jb      short loc_1400032D9
0x1400032c1  mov     rcx, [rcx+18h]
0x1400032c5  lea     r8, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids
0x1400032cc  mov     edx, 0Fh
0x1400032d1  mov     r9, rdi
0x1400032d4  call    WPP_SF_q
0x1400032d9  cmp     dword ptr [rbx+268h], 0
0x1400032e0  jnz     short loc_1400032F5
0x1400032e2  lea     rcx, [rbx+248h]; Event
0x1400032e9  call    cs:__imp_NdisInitializeEvent
0x1400032f0  nop     dword ptr [rax+rax+00h]
0x1400032f5  mov     dl, [rbx+278h]; NewIrql
0x1400032fb  mov     rcx, rsi; SpinLock
0x1400032fe  inc     dword ptr [rbx+268h]
0x140003304  call    cs:__imp_KeReleaseSpinLock
0x14000330b  nop     dword ptr [rax+rax+00h]
0x140003310  mov     rcx, r13; Event
0x140003313  call    cs:__imp_NdisInitializeEvent
0x14000331a  nop     dword ptr [rax+rax+00h]
0x14000331f  mov     rcx, [rbx+20h]; NdisBindingHandle
0x140003323  lea     r9, [rdi+18h]; NdisAfHandle
0x140003327  mov     r8, rdi; ClientAfContext
0x14000332a  mov     rdx, r14; AddressFamily
0x14000332d  call    cs:__imp_NdisClOpenAddressFamilyEx
0x140003334  nop     dword ptr [rax+rax+00h]
0x140003339  mov     ebp, eax
0x14000333b  cmp     eax, 103h
0x140003340  jnz     short loc_140003359
0x140003342  xor     edx, edx; MsToWait
0x140003344  mov     rcx, r13; Event
0x140003347  call    cs:__imp_NdisWaitEvent
0x14000334e  nop     dword ptr [rax+rax+00h]
0x140003353  mov     ebp, [rdi+0B0h]
0x140003359  mov     rcx, rsi; SpinLock
0x14000335c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003363  nop     dword ptr [rax+rax+00h]
0x140003368  mov     [rbx+278h], al
0x14000336e  test    ebp, ebp
0x140003370  jz      short loc_1400033AD
0x140003372  mov     rcx, cs:WPP_GLOBAL_Control
0x140003379  lea     r15, WPP_GLOBAL_Control
0x140003380  cmp     rcx, r15
0x140003383  jz      short loc_1400033A0
0x140003385  cmp     byte ptr [rcx+29h], 3
0x140003389  jb      short loc_1400033A0
0x14000338b  mov     r9d, [r14]
0x14000338e  mov     rcx, [rcx+18h]
0x140003392  mov     [rsp+88h+var_60], ebp
0x140003396  mov     [rsp+88h+var_68], rbx
0x14000339b  call    WPP_SF_DqD
0x1400033a0  mov     rcx, rdi; P
0x1400033a3  call    PxFreeClAf
0x1400033a8  jmp     loc_140003677
0x1400033ad  mov     rcx, r12; SpinLock
0x1400033b0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400033b7  nop     dword ptr [rax+rax+00h]
0x1400033bc  mov     rcx, r12; SpinLock
0x1400033bf  mov     dword ptr [rdi+10h], 3
0x1400033c6  mov     dl, al; NewIrql
0x1400033c8  mov     [rdi+0C0h], al
0x1400033ce  call    cs:__imp_KeReleaseSpinLock
0x1400033d5  nop     dword ptr [rax+rax+00h]
0x1400033da  mov     rax, [r15+8]
0x1400033de  cmp     [rax], r15
0x1400033e1  jnz     loc_14000369F
0x1400033e7  mov     [rdi], r15
0x1400033ea  mov     [rdi+8], rax
0x1400033ee  mov     [rax], rdi
0x1400033f1  mov     [r15+8], rdi
0x1400033f5  mov     eax, [rbx+1Ch]
0x1400033f8  test    al, 2
0x1400033fa  jz      short loc_140003401
0x1400033fc  mov     bpl, 1
0x1400033ff  jmp     short loc_14000340A
0x140003401  xor     bpl, bpl
0x140003404  or      eax, 1
0x140003407  mov     [rbx+1Ch], eax
0x14000340a  mov     dl, [rbx+278h]; NewIrql
0x140003410  mov     rcx, rsi; SpinLock
0x140003413  inc     dword ptr [rbx+18h]
0x140003416  call    cs:__imp_KeReleaseSpinLock
0x14000341d  nop     dword ptr [rax+rax+00h]
0x140003422  test    bpl, bpl
0x140003425  jnz     loc_14000359E
0x14000342b  movsd   xmm0, qword ptr [r14]
0x140003430  mov     eax, [r14+8]
0x140003434  movsd   qword ptr [rsp+88h+AddressFamily.AddressFamily], xmm0
0x14000343a  mov     [rsp+88h+AddressFamily.AddressFamily], 800h
0x140003442  mov     [rsp+88h+AddressFamily.MinorVersion], eax
0x140003446  mov     rcx, cs:WPP_GLOBAL_Control
0x14000344d  lea     r15, WPP_GLOBAL_Control
0x140003454  cmp     rcx, r15
0x140003457  jz      short loc_140003474
0x140003459  cmp     byte ptr [rcx+29h], 5
0x14000345d  jb      short loc_140003474
0x14000345f  mov     rcx, [rcx+18h]
0x140003463  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x14000346a  mov     edx, 25h ; '%'
0x14000346f  call    WPP_SF_
0x140003474  mov     rcx, [rbx+48h]; NdisBindingHandle
0x140003478  lea     rdx, [rsp+88h+AddressFamily]; AddressFamily
0x14000347d  call    cs:__imp_NdisCmRegisterAddressFamilyEx
0x140003484  nop     dword ptr [rax+rax+00h]
0x140003489  mov     rcx, rsi; SpinLock
0x14000348c  mov     ebp, eax
0x14000348e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003495  nop     dword ptr [rax+rax+00h]
0x14000349a  and     dword ptr [rbx+1Ch], 0FFFFFFFEh
0x14000349e  mov     [rbx+278h], al
0x1400034a4  test    ebp, ebp
0x1400034a6  jz      loc_140003587
0x1400034ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400034b3  cmp     rcx, r15
0x1400034b6  jz      short loc_1400034DB
0x1400034b8  cmp     byte ptr [rcx+29h], 1
0x1400034bc  jb      short loc_1400034DB
0x1400034be  mov     r9, [rbx+48h]
0x1400034c2  lea     r8, WPP_55e376f2a9f936ee4a212904c2347983_Traceguids
0x1400034c9  mov     rcx, [rcx+18h]
0x1400034cd  mov     edx, 26h ; '&'
0x1400034d2  mov     dword ptr [rsp+88h+var_68], ebp
0x1400034d6  call    WPP_SF_qD
0x1400034db  mov     rcx, [rdi]
0x1400034de  cmp     [rcx+8], rdi
0x1400034e2  jnz     loc_14000369F
0x1400034e8  mov     rax, [rdi+8]
0x1400034ec  cmp     [rax], rdi
0x1400034ef  jnz     loc_14000369F
0x1400034f5  mov     [rax], rcx
0x1400034f8  mov     [rcx+8], rax
  ... truncated ...
```
