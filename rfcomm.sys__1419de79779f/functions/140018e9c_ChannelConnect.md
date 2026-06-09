# ChannelConnect

- ea: `0x140018e9c`
- end: `0x1400195c9`
- name: `ChannelConnect`
- size: `1837`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400077cc`
- `0x140012590`
- `0x14001291c`
- `0x140017ab8`
- `0x140018330`
- `0x1400186b4`
- `0x140019f70`

## callees

- `0x140003868`
- `0x1400048b0`
- `0x140004a68`
- `0x140005050`
- `0x140007350`
- `0x14000ab70`
- `0x14000dd28`
- `0x140010150`
- `0x140014eb4`
- `0x1400157dc`
- `0x14001737c`
- `0x1400178b8`
- `0x14001812c`
- `0x1400185c8`
- `0x140018e9c`
- `0x1400195d0`
- `0x140019e5c`
- `0x14001a164`
- `0x14001bfa8`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f13`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f7d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f13`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018f7d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f69`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400190e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019101`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019262`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019276`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001943a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001944e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018f69`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018fd6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400190e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019101`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019262`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019276`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001943a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001944e`

## string_xrefs

- `0x140018ff7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x14001905c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x1400191db`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x140019294`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x1400192cd`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x140019393`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x14001947a`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x1400194cd`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x140019522`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x14001953c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`

## pseudocode

```c
__int64 __fastcall ChannelConnect(__int64 a1, int a2)
{
  unsigned int v2; // r14d
  char v3; // r12
  __int64 v5; // rax
  KIRQL v6; // dl
  __int64 v7; // rdi
  KSPIN_LOCK *v8; // rcx
  int v9; // edi
  char v10; // r13
  __int64 v11; // r15
  __int64 Locked; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // r8
  _QWORD *v20; // rdx
  __int64 v21; // r14
  int v22; // esi
  int v23; // esi
  int v24; // esi
  int v25; // eax
  __int64 v26; // rax
  int v27; // edx
  __int64 v28; // rsi
  _QWORD *v29; // rdi
  _QWORD *v30; // rcx
  _QWORD *v31; // rdx
  _QWORD *v32; // rdx
  __int64 v33; // rax
  _QWORD *v34; // r8
  int v35; // eax
  __int64 result; // rax
  void *DeviceExtension; // rbx
  const char *v38; // rax
  int v39; // edx
  char v40; // [rsp+80h] [rbp+8h] BYREF
  __int64 v41; // [rsp+88h] [rbp+10h]
  __int64 v42; // [rsp+90h] [rbp+18h]

  v2 = *(_DWORD *)(a1 + 140);
  v3 = 0;
  v40 = 0;
  v41 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      15,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      v2,
      a1);
  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v5 = TdiReferenceAddrLocked(a1, 1145981254);
  v6 = *(_BYTE *)(a1 + 56);
  v7 = v5;
  v42 = v5;
  v8 = (KSPIN_LOCK *)(a1 + 48);
  if ( v5 )
  {
    v10 = *(_BYTE *)(a1 + 830);
    KeReleaseSpinLock(v8, v6);
    v11 = *(_QWORD *)(v7 + 80);
    *(_BYTE *)(v11 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 24));
    Locked = SessionFindLocked(v11, a1 + 116);
    v15 = Locked;
    if ( Locked )
    {
      v25 = *(_DWORD *)(Locked + 256);
      v17 = 4;
      if ( _bittest(&v25, v2) )
      {
        LOBYTE(v13) = ((*(_BYTE *)(v15 + 272) & 1) == 0) | (2 * (v2 & 0x1F));
        LOBYTE(v14) = 1;
        v26 = ChannelFindLocked(v15, v13, v14);
        v28 = v26;
        if ( v26 && *(int *)(v26 + 48) > 5 && (v29 = (_QWORD *)(v26 + 72), (_QWORD *)*v29 == v29) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v27,
              2,
              16,
              (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
              v26);
          RefObj_AddRefEx(a1 + 24, 1313754947, 276, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
          v30 = (_QWORD *)v29[1];
          if ( (_QWORD *)*v30 != v29 )
            goto LABEL_50;
          *(_QWORD *)(a1 + 280) = v29;
          *(_QWORD *)(a1 + 288) = v30;
          *v30 = a1 + 280;
          v29[1] = a1 + 280;
          v9 = 259;
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dq(
              WPP_GLOBAL_Control->DeviceExtension,
              v27,
              2,
              17,
              (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
              v2,
              v26);
          v9 = -1073741302;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v15 + 56), *(_BYTE *)(v15 + 64));
        KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 24), *(_BYTE *)(v11 + 32));
        if ( v28 )
          RefObj_ReleaseEx(
            v28 + 24,
            1145981254,
            292,
            "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
        goto LABEL_57;
      }
    }
    else
    {
      LOBYTE(v14) = 1;
      v16 = SessionCreateLocked(v11, *(_QWORD *)(a1 + 116), v14, &v40);
      v15 = v16;
      if ( !v16 )
      {
        v9 = -1073741670;
        KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 24), *(_BYTE *)(v11 + 32));
        goto LABEL_58;
      }
      RefObj_AddRefEx(v16 + 24, 1145981254, 241, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
      v17 = 0;
      RfcommSetState(v15, 1);
      v3 = v40;
    }
    v18 = v42;
    v19 = 393216;
    *(_DWORD *)(v15 + 472) |= *(_DWORD *)(v42 + 212) & 0x60000;
    *(_DWORD *)(v15 + 288) |= *(_DWORD *)(v18 + 204) & 3;
    if ( *(_DWORD *)(v15 + 48) == 4 )
    {
      if ( (*(_DWORD *)(v18 + 212) & 0x60000 & *(_DWORD *)(v15 + 476)) == (*(_DWORD *)(v18 + 212) & 0x60000) )
      {
        if ( !v10
          || (*(_DWORD *)(v18 + 204) & 3 & (*(_DWORD *)(v15 + 292) | *(_DWORD *)(v15 + 296))) == (*(_DWORD *)(v18 + 204)
                                                                                                & 3) )
        {
          LOBYTE(v19) = 1;
          v33 = ChannelCreateLocked(v15, v2, v19);
          v41 = v33;
          v21 = v33;
          if ( !v33 )
          {
            v9 = -1073741670;
            KeReleaseSpinLock((PKSPIN_LOCK)(v15 + 56), *(_BYTE *)(v15 + 64));
            KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 24), *(_BYTE *)(v11 + 32));
            goto LABEL_57;
          }
          ChannelPairConnLocked(v33, a1);
          RefObj_AddRefEx(a1 + 24, 1313754947, 367, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
          v34 = *(_QWORD **)(v21 + 80);
          if ( *v34 == v21 + 72 )
          {
            *(_QWORD *)(a1 + 280) = v21 + 72;
            v17 = 3;
            *(_QWORD *)(a1 + 288) = v34;
            *v34 = a1 + 280;
            *(_QWORD *)(v21 + 80) = a1 + 280;
            ChannelSetState(v21, 1);
            RefObj_AddRefEx(
              v21 + 24,
              1313754947,
              377,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
            goto LABEL_14;
          }
        }
        else
        {
          RefObj_AddRefEx(a1 + 24, 1313754947, 339, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
          v32 = *(_QWORD **)(v15 + 104);
          if ( *v32 == v15 + 96 )
          {
            *(_QWORD *)(a1 + 280) = v15 + 96;
            *(_QWORD *)(a1 + 288) = v32;
            *v32 = a1 + 280;
            *(_QWORD *)(v15 + 104) = a1 + 280;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_q(
                WPP_GLOBAL_Control->DeviceExtension,
                (_DWORD)v32,
                2,
                20,
                (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
                v15);
            v17 = 2;
            goto LABEL_13;
          }
        }
      }
      else
      {
        RefObj_AddRefEx(a1 + 24, 1313754947, 321, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
        v31 = *(_QWORD **)(v15 + 104);
        if ( *v31 == v15 + 96 )
        {
          *(_QWORD *)(a1 + 280) = v15 + 96;
          *(_QWORD *)(a1 + 288) = v31;
          *v31 = a1 + 280;
          *(_QWORD *)(v15 + 104) = a1 + 280;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              (_DWORD)v31,
              2,
              19,
              (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
              v15);
          v21 = v41;
          if ( !*(_DWORD *)(v15 + 468) )
          {
            v17 = 1;
            *(_DWORD *)(v15 + 468) = 1;
          }
          goto LABEL_14;
        }
      }
    }
    else
    {
      RefObj_AddRefEx(a1 + 24, 1313754947, 310, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
      v20 = *(_QWORD **)(v15 + 104);
      if ( *v20 == v15 + 96 )
      {
        *(_QWORD *)(a1 + 280) = v15 + 96;
        *(_QWORD *)(a1 + 288) = v20;
        *v20 = a1 + 280;
        *(_QWORD *)(v15 + 104) = a1 + 280;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v20,
            2,
            18,
            (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
            v15);
LABEL_13:
        v21 = v41;
LABEL_14:
        v9 = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)(v15 + 56), *(_BYTE *)(v15 + 64));
        if ( v3 )
          RfcommStartTimerLocked(v11);
        KeReleaseSpinLock((PKSPIN_LOCK)(v11 + 24), *(_BYTE *)(v11 + 32));
        if ( v17 )
        {
          v22 = v17 - 1;
          if ( v22 )
          {
            v23 = v22 - 1;
            if ( v23 )
            {
              v24 = v23 - 1;
              if ( v24 )
              {
                if ( v24 == 1 )
                  v9 = 259;
                goto LABEL_57;
              }
              v35 = RfcommSendMsgPN(v15, v21, a1);
            }
            else
            {
              v35 = SessionReconfig(v15);
            }
          }
          else
          {
            v35 = BrbUpdate(v15);
          }
        }
        else
        {
          v35 = SessionConnect(v15);
        }
        v9 = v35;
LABEL_57:
        RefObj_ReleaseEx(v15 + 24, 1145981254, 430, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
LABEL_58:
        result = RefObj_ReleaseEx(
                   v42 + 24,
                   1145981254,
                   435,
                   "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
        if ( v9 >= 0 )
          goto LABEL_60;
        goto LABEL_59;
      }
    }
LABEL_50:
    __fastfail(3u);
  }
  KeReleaseSpinLock(v8, v6);
  v9 = -1073741503;
LABEL_59:
  result = TdiCompleteConnect(a1, (unsigned int)v9);
LABEL_60:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v38 = NtStatusTxt(v9);
    return WPP_RECORDER_SF_qs(
             (_DWORD)DeviceExtension,
             v39,
             3,
             21,
             (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
             v41,
             (__int64)v38);
  }
  return result;
}

```

## disassembly

```asm
0x140018e9c  mov     r11, rsp
0x140018e9f  mov     [r11+20h], rbx
0x140018ea3  push    rbp
0x140018ea4  push    rsi
0x140018ea5  push    rdi
0x140018ea6  push    r12
0x140018ea8  push    r13
0x140018eaa  push    r14
0x140018eac  push    r15
0x140018eae  sub     rsp, 40h
0x140018eb2  mov     r14d, [rcx+8Ch]
0x140018eb9  xor     r12b, r12b
0x140018ebc  mov     [r11+8], r12b
0x140018ec0  mov     rbp, rcx
0x140018ec3  mov     [rsp+78h+arg_8], 0
0x140018ecf  lea     rax, WPP_RECORDER_INITIALIZED
0x140018ed6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018edd  lea     rcx, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140018ee4  jz      short loc_140018F0C
0x140018ee6  mov     [r11-48h], rbp
0x140018eea  mov     r9d, 0Fh
0x140018ef0  mov     [r11-50h], r14d
0x140018ef4  mov     [r11-58h], rcx
0x140018ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x140018eff  lea     r8d, [r9-0Ch]
0x140018f03  mov     rcx, [rcx+40h]
0x140018f07  call    WPP_RECORDER_SF_dq
0x140018f0c  lea     rbx, [rbp+30h]
0x140018f10  mov     rcx, rbx; SpinLock
0x140018f13  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018f1a  nop     dword ptr [rax+rax+00h]
0x140018f1f  mov     edx, 444E4946h
0x140018f24  mov     rcx, rbp
0x140018f27  mov     [rbp+38h], al
0x140018f2a  call    TdiReferenceAddrLocked
0x140018f2f  mov     dl, [rbp+38h]; NewIrql
0x140018f32  mov     rdi, rax
0x140018f35  mov     [rsp+78h+arg_10], rax
0x140018f3d  mov     rcx, rbx; SpinLock
0x140018f40  test    rax, rax
0x140018f43  jnz     short loc_140018F62
0x140018f45  call    cs:__imp_KeReleaseSpinLock
0x140018f4c  nop     dword ptr [rax+rax+00h]
0x140018f51  mov     edi, 0C0000141h
0x140018f56  lea     r13, WPP_RECORDER_INITIALIZED
0x140018f5d  jmp     loc_14001955B
0x140018f62  mov     r13b, [rbp+33Eh]
0x140018f69  call    cs:__imp_KeReleaseSpinLock
0x140018f70  nop     dword ptr [rax+rax+00h]
0x140018f75  mov     r15, [rdi+50h]
0x140018f79  lea     rcx, [r15+18h]; SpinLock
0x140018f7d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018f84  nop     dword ptr [rax+rax+00h]
0x140018f89  lea     rdx, [rbp+74h]
0x140018f8d  mov     rcx, r15
0x140018f90  mov     [r15+20h], al
0x140018f94  call    SessionFindLocked
0x140018f99  mov     rbx, rax
0x140018f9c  mov     edi, 1
0x140018fa1  test    rax, rax
0x140018fa4  jnz     loc_140019143
0x140018faa  mov     rdx, [rbp+74h]
0x140018fae  lea     r9, [rsp+78h+arg_0]
0x140018fb6  mov     r8b, dil
0x140018fb9  mov     rcx, r15
0x140018fbc  call    SessionCreateLocked
0x140018fc1  mov     rbx, rax
0x140018fc4  test    rax, rax
0x140018fc7  jnz     short loc_140018FEE
0x140018fc9  mov     dl, [r15+20h]; NewIrql
0x140018fcd  lea     rcx, [r15+18h]; SpinLock
0x140018fd1  mov     edi, 0C000009Ah
0x140018fd6  call    cs:__imp_KeReleaseSpinLock
0x140018fdd  nop     dword ptr [rax+rax+00h]
0x140018fe2  lea     r13, WPP_RECORDER_INITIALIZED
0x140018fe9  jmp     loc_140019534
0x140018fee  lea     rcx, [rax+18h]
0x140018ff2  mov     edx, 444E4946h
0x140018ff7  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140018ffe  mov     r8d, 0F1h
0x140019004  call    RefObj_AddRefEx
0x140019009  mov     edx, edi
0x14001900b  mov     rcx, rbx
0x14001900e  xor     esi, esi
0x140019010  call    RfcommSetState
0x140019015  mov     r12b, [rsp+78h+arg_0]
0x14001901d  mov     rdx, [rsp+78h+arg_10]
0x140019025  mov     r8d, 60000h
0x14001902b  mov     eax, [rdx+0D4h]
0x140019031  and     eax, r8d
0x140019034  or      [rbx+1D8h], eax
0x14001903a  mov     eax, [rdx+0CCh]
0x140019040  and     eax, 3
0x140019043  or      [rbx+120h], eax
0x140019049  cmp     dword ptr [rbx+30h], 4
0x14001904d  jz      loc_1400192AB
0x140019053  lea     rcx, [rbp+18h]
0x140019057  mov     edx, 4E4E4F43h
0x14001905c  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140019063  mov     r8d, 136h
0x140019069  call    RefObj_AddRefEx
0x14001906e  lea     rcx, [rbx+60h]
0x140019072  mov     rdx, [rcx+8]
0x140019076  cmp     [rdx], rcx
0x140019079  jnz     loc_140019499
0x14001907f  lea     rax, [rbp+118h]
0x140019086  mov     [rax], rcx
0x140019089  mov     [rax+8], rdx
0x14001908d  mov     [rdx], rax
0x140019090  mov     [rcx+8], rax
0x140019094  lea     r13, WPP_RECORDER_INITIALIZED
0x14001909b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400190a2  jz      short loc_1400190CF
0x1400190a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190ab  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x1400190b2  mov     r9d, 12h
0x1400190b8  mov     [rsp+78h+var_50], rbx
0x1400190bd  mov     [rsp+78h+var_58], rax
0x1400190c2  mov     rcx, [rcx+40h]
0x1400190c6  lea     r8d, [r9-10h]
0x1400190ca  call    WPP_RECORDER_SF_q
0x1400190cf  mov     r14, [rsp+78h+arg_8]
0x1400190d7  mov     dl, [rbx+40h]; NewIrql
0x1400190da  lea     rcx, [rbx+38h]; SpinLock
0x1400190de  xor     edi, edi
0x1400190e0  call    cs:__imp_KeReleaseSpinLock
0x1400190e7  nop     dword ptr [rax+rax+00h]
0x1400190ec  test    r12b, r12b
0x1400190ef  jz      short loc_1400190F9
0x1400190f1  mov     rcx, r15
0x1400190f4  call    RfcommStartTimerLocked
0x1400190f9  mov     dl, [r15+20h]; NewIrql
0x1400190fd  lea     rcx, [r15+18h]; SpinLock
0x140019101  call    cs:__imp_KeReleaseSpinLock
0x140019108  nop     dword ptr [rax+rax+00h]
0x14001910d  test    esi, esi
0x14001910f  jz      loc_14001950F
0x140019115  sub     esi, 1
0x140019118  jz      loc_140019505
0x14001911e  sub     esi, 1
0x140019121  jz      loc_1400194FB
0x140019127  sub     esi, 1
0x14001912a  jz      loc_1400194EB
0x140019130  cmp     esi, 1
0x140019133  jnz     loc_140019519
0x140019139  mov     edi, 103h
0x14001913e  jmp     loc_140019519
0x140019143  mov     eax, [rax+100h]
0x140019149  mov     esi, 4
0x14001914e  bt      eax, r14d
0x140019152  jnb     loc_14001901D
0x140019158  mov     al, [rbx+110h]
0x14001915e  mov     dl, r14b
0x140019161  and     dl, 1Fh
0x140019164  not     al
0x140019166  add     dl, dl
0x140019168  and     al, dil
0x14001916b  or      dl, al
0x14001916d  mov     r8b, dil
0x140019170  mov     rcx, rbx
0x140019173  call    ChannelFindLocked
0x140019178  mov     rsi, rax
0x14001917b  test    rax, rax
0x14001917e  jz      loc_140019216
0x140019184  cmp     dword ptr [rax+30h], 5
0x140019188  jle     loc_140019216
0x14001918e  lea     rdi, [rax+48h]
0x140019192  cmp     [rdi], rdi
0x140019195  jnz     short loc_140019216
0x140019197  lea     r13, WPP_RECORDER_INITIALIZED
0x14001919e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400191a5  jz      short loc_1400191D2
0x1400191a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191ae  mov     r9d, 10h
0x1400191b4  mov     [rsp+78h+var_50], rax
0x1400191b9  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x1400191c0  mov     [rsp+78h+var_58], rax
0x1400191c5  mov     rcx, [rcx+40h]
0x1400191c9  lea     r8d, [r9-0Eh]
0x1400191cd  call    WPP_RECORDER_SF_q
0x1400191d2  lea     rcx, [rbp+18h]
0x1400191d6  mov     edx, 4E4E4F43h
0x1400191db  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400191e2  mov     r8d, 114h
0x1400191e8  call    RefObj_AddRefEx
0x1400191ed  mov     rcx, [rdi+8]
0x1400191f1  cmp     [rcx], rdi
0x1400191f4  jnz     loc_140019499
0x1400191fa  lea     rax, [rbp+118h]
0x140019201  mov     [rax], rdi
0x140019204  mov     [rax+8], rcx
0x140019208  mov     [rcx], rax
0x14001920b  mov     [rdi+8], rax
0x14001920f  mov     edi, 103h
0x140019214  jmp     short loc_14001925B
0x140019216  lea     r13, WPP_RECORDER_INITIALIZED
0x14001921d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140019224  jz      short loc_140019256
0x140019226  mov     rcx, cs:WPP_GLOBAL_Control
0x14001922d  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019234  mov     r9d, 11h
0x14001923a  mov     [rsp+78h+var_48], rsi
0x14001923f  mov     dword ptr [rsp+78h+var_50], r14d
0x140019244  mov     [rsp+78h+var_58], rax
0x140019249  mov     rcx, [rcx+40h]
0x14001924d  lea     r8d, [r9-0Fh]
0x140019251  call    WPP_RECORDER_SF_dq
0x140019256  mov     edi, 0C000020Ah
0x14001925b  mov     dl, [rbx+40h]; NewIrql
0x14001925e  lea     rcx, [rbx+38h]; SpinLock
0x140019262  call    cs:__imp_KeReleaseSpinLock
0x140019269  nop     dword ptr [rax+rax+00h]
0x14001926e  mov     dl, [r15+20h]; NewIrql
0x140019272  lea     rcx, [r15+18h]; SpinLock
0x140019276  call    cs:__imp_KeReleaseSpinLock
0x14001927d  nop     dword ptr [rax+rax+00h]
0x140019282  test    rsi, rsi
0x140019285  jz      loc_140019519
0x14001928b  lea     rcx, [rsi+18h]
0x14001928f  mov     edx, 444E4946h
0x140019294  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001929b  mov     r8d, 124h
0x1400192a1  call    RefObj_ReleaseEx
0x1400192a6  jmp     loc_140019519
0x1400192ab  mov     ecx, [rdx+0D4h]
0x1400192b1  mov     eax, [rbx+1DCh]
0x1400192b7  and     ecx, r8d
0x1400192ba  and     eax, ecx
0x1400192bc  cmp     eax, ecx
0x1400192be  jz      loc_140019362
0x1400192c4  lea     rcx, [rbp+18h]
0x1400192c8  mov     edx, 4E4E4F43h
0x1400192cd  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400192d4  mov     r8d, 141h
0x1400192da  call    RefObj_AddRefEx
0x1400192df  lea     rcx, [rbx+60h]
0x1400192e3  mov     rdx, [rcx+8]
0x1400192e7  cmp     [rdx], rcx
0x1400192ea  jnz     loc_140019499
0x1400192f0  lea     rax, [rbp+118h]
0x1400192f7  mov     [rax], rcx
0x1400192fa  mov     [rax+8], rdx
0x1400192fe  mov     [rdx], rax
0x140019301  mov     [rcx+8], rax
0x140019305  lea     r13, WPP_RECORDER_INITIALIZED
0x14001930c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140019313  jz      short loc_140019340
0x140019315  mov     rcx, cs:WPP_GLOBAL_Control
0x14001931c  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019323  mov     r9d, 13h
0x140019329  mov     [rsp+78h+var_50], rbx
0x14001932e  mov     [rsp+78h+var_58], rax
0x140019333  mov     rcx, [rcx+40h]
0x140019337  lea     r8d, [r9-11h]
0x14001933b  call    WPP_RECORDER_SF_q
0x140019340  cmp     dword ptr [rbx+1D4h], 0
0x140019347  mov     r14, [rsp+78h+arg_8]
0x14001934f  jnz     loc_1400190D7
0x140019355  mov     esi, edi
0x140019357  mov     [rbx+1D4h], edi
0x14001935d  jmp     loc_1400190D7
0x140019362  test    r13b, r13b
0x140019365  jz      loc_140019410
0x14001936b  mov     edx, [rdx+0CCh]
0x140019371  mov     ecx, [rbx+128h]
0x140019377  and     edx, 3
0x14001937a  or      ecx, [rbx+124h]
0x140019380  and     ecx, edx
0x140019382  cmp     ecx, edx
0x140019384  jz      loc_140019410
0x14001938a  lea     rcx, [rbp+18h]
0x14001938e  mov     edx, 4E4E4F43h
0x140019393  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001939a  mov     r8d, 153h
0x1400193a0  call    RefObj_AddRefEx
0x1400193a5  lea     rcx, [rbx+60h]
0x1400193a9  mov     rdx, [rcx+8]
0x1400193ad  cmp     [rdx], rcx
0x1400193b0  jnz     loc_140019499
0x1400193b6  lea     rax, [rbp+118h]
0x1400193bd  mov     [rax], rcx
0x1400193c0  mov     [rax+8], rdx
0x1400193c4  mov     [rdx], rax
0x1400193c7  mov     [rcx+8], rax
0x1400193cb  lea     r13, WPP_RECORDER_INITIALIZED
0x1400193d2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400193d9  jz      short loc_140019406
0x1400193db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193e2  lea     rax, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x1400193e9  mov     r9d, 14h
0x1400193ef  mov     [rsp+78h+var_50], rbx
0x1400193f4  mov     [rsp+78h+var_58], rax
0x1400193f9  mov     rcx, [rcx+40h]
0x1400193fd  lea     r8d, [r9-12h]
0x140019401  call    WPP_RECORDER_SF_q
0x140019406  mov     esi, 2
0x14001940b  jmp     loc_1400190CF
0x140019410  mov     r8b, dil
0x140019413  mov     edx, r14d
0x140019416  mov     rcx, rbx
  ... truncated ...
```
