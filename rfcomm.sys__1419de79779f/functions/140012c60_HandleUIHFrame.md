# HandleUIHFrame

- ea: `0x140012c60`
- end: `0x1400133a8`
- name: `HandleUIHFrame`
- size: `1864`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140003bf4`
- `0x140004684`
- `0x140004a68`
- `0x140008334`
- `0x14000fd78`
- `0x140010260`
- `0x1400114c0`
- `0x140011634`
- `0x14001190c`
- `0x14001204c`
- `0x1400121d4`
- `0x140012c60`
- `0x140013d20`
- `0x140013fb4`
- `0x140014b10`
- `0x1400161d0`
- `0x1400162d0`
- `0x140016b84`
- `0x140019e5c`
- `0x14001a12c`
- `0x14001a164`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012e5c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013029`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001315e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012e5c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013029`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001315e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e91`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400132b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013348`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e91`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400132b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013348`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ee7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ee7`

## string_xrefs

- `0x140012ff2`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140013304`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140013333`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
char __fastcall HandleUIHFrame(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int8 v4; // al
  char v5; // r13
  unsigned int v6; // ebx
  unsigned int v9; // ebx
  bool v10; // r14
  unsigned __int8 *v11; // r15
  __int64 v12; // rdx
  char v13; // al
  unsigned __int8 *v14; // r14
  unsigned int v15; // esi
  char v16; // r12
  unsigned int v17; // eax
  char v18; // al
  KIRQL v19; // al
  bool v20; // cc
  KSPIN_LOCK *v21; // rcx
  unsigned int v22; // r9d
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  char v26; // si
  unsigned __int8 v27; // r15
  KIRQL v28; // al
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rax
  int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 Locked; // rax
  bool v38; // r12
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r15
  __int64 v42; // r15
  int v43; // edx
  char v44; // cl
  int v46; // [rsp+20h] [rbp-20h]
  __int64 v47; // [rsp+80h] [rbp+40h] BYREF
  __int64 v48; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int8 *v49; // [rsp+90h] [rbp+50h] BYREF

  v4 = *(_BYTE *)(a2 + 34);
  v5 = 1;
  v6 = v4;
  if ( (v4 & 1) == 0 )
    v6 = *(unsigned __int16 *)(a2 + 34);
  v9 = v6 >> 1;
  v10 = 0;
  v48 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      156,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  if ( *(_BYTE *)(a1 + 465) )
    v10 = (*(_BYTE *)(a2 + 33) & 0x10) != 0;
  if ( *(_BYTE *)(a2 + 32) >= 4u )
  {
    *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
    LOBYTE(v35) = 1;
    LOBYTE(v36) = *(_BYTE *)(a2 + 32) >> 2;
    Locked = ChannelFindLocked(a1, v36, v35);
    v48 = Locked;
    if ( !Locked )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
      goto LABEL_97;
    }
    v38 = 0;
    v39 = ChannelReferenceConnLocked(Locked, 1312901187);
    v40 = v48;
    v41 = v39;
    v47 = v39;
    if ( v10 )
    {
      v42 = (*(_BYTE *)(a2 + 34) & 1) == 0;
      *(_DWORD *)(v48 + 228) += *(unsigned __int8 *)(v42 + a2 + 35);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          *(unsigned __int8 *)(v42 + a2 + 35),
          11,
          160,
          v46,
          *(_BYTE *)(v42 + a2 + 35),
          *(_BYTE *)(v48 + 184),
          *(_DWORD *)(v48 + 228));
      v40 = v48;
      v43 = *(_DWORD *)(v48 + 228);
      if ( v43 )
        v38 = v43 == *(unsigned __int8 *)(v42 + a2 + 35);
      v41 = v47;
    }
    if ( v9 && *(_BYTE *)(a1 + 465) )
    {
      if ( *(int *)(v40 + 192) > 0 )
      {
        --*(_DWORD *)(v40 + 188);
        --*(_DWORD *)(v48 + 192);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_Dd(
            WPP_GLOBAL_Control->DeviceExtension,
            *(unsigned __int8 *)(v48 + 184),
            9,
            161,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
            *(_BYTE *)(v48 + 184),
            *(_DWORD *)(v48 + 192));
      }
      else
      {
        v9 = 0;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    if ( v38 )
      ChannelSendData(v48);
    if ( v9 )
    {
      v44 = ~*(_BYTE *)(a2 + 34);
      *(_DWORD *)(a2 + 28) = v9;
      *(_DWORD *)(a2 + 24) = v10 + (v44 & 1) + 3;
      if ( v41 )
        v5 = TdiDataInd(v41, (_QWORD *)a2);
    }
    RefObj_ReleaseEx(v48 + 24, 1145981254, 5699, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    if ( !v41 )
      goto LABEL_97;
    v23 = v41 + 24;
    v24 = 1312901187;
    v25 = 5703;
LABEL_95:
    RefObj_ReleaseEx(v23, v24, v25, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    goto LABEL_97;
  }
  v11 = 0;
  v12 = 2;
  v13 = ~*(_BYTE *)(a2 + 34);
  v49 = 0;
  v14 = (unsigned __int8 *)((v13 & 1) + a2 + 35);
  v15 = *v14;
  if ( (v15 & 2) != 0 )
  {
    v16 = 0;
    v17 = v15 >> 2;
    LOBYTE(v47) = 0;
    if ( v15 >> 2 == 8 )
      goto LABEL_30;
    switch ( v17 )
    {
      case 0x14u:
        if ( v9 < 4 )
          goto LABEL_18;
        v18 = HandleMsgRLS(a1, v14, &WPP_RECORDER_INITIALIZED, &v48);
        break;
      case 0x18u:
        LOBYTE(a4) = 1;
LABEL_22:
        v18 = HandleMsgFC(a1, 2, &WPP_RECORDER_INITIALIZED, a4);
        break;
      case 0x20u:
        if ( v9 < 0xA )
          goto LABEL_18;
        v18 = HandleMsgPN(a1, (_DWORD)v14, v9, (unsigned int)&v48, 1);
        break;
      case 0x24u:
        v18 = HandleMsgRPN(a1, (_DWORD)v14, (unsigned int)&WPP_RECORDER_INITIALIZED, (unsigned int)&v48, (__int64)&v49);
        v11 = v49;
        break;
      case 0x28u:
        a4 = 0;
        goto LABEL_22;
      case 0x38u:
        if ( v9 >= 4 )
        {
          v18 = HandleMsgMSC(a1, (_DWORD)v14, v9, (unsigned int)&v48, (__int64)&v47);
          v16 = v47;
          break;
        }
LABEL_18:
        BYTE2(v47) = *v14;
        LOWORD(v47) = 785;
        SessionSendResponse(a1, 0, &v47, 3);
LABEL_39:
        if ( !v48 )
          goto LABEL_97;
        v23 = v48 + 24;
        v24 = 1145981254;
        v25 = 5426;
        goto LABEL_95;
      default:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            2,
            157,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
            (char)v14);
        goto LABEL_18;
    }
    if ( !v18 )
    {
LABEL_37:
      if ( v16 )
        ChannelSendData(v48);
      goto LABEL_39;
    }
LABEL_30:
    v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
    v20 = *(_DWORD *)(a1 + 48) <= 4;
    v21 = (KSPIN_LOCK *)(a1 + 56);
    *(_BYTE *)(a1 + 64) = v19;
    if ( v20 )
    {
      KeReleaseSpinLock(v21, v19);
      if ( v11 )
      {
        v22 = v11[1];
        if ( (v11[1] & 1) == 0 )
          v22 = *(unsigned __int16 *)(v11 + 1);
        SessionSendResponse(a1, v48, v11, (v22 >> 1) + 2);
        ExFreePoolWithTag(v11, 0);
      }
      else
      {
        *v14 &= ~2u;
        SessionSendResponse(a1, v48, v14, v9);
      }
    }
    else
    {
      KeReleaseSpinLock(v21, v19);
      RfcommSendDMEx(a1, 0, 0);
    }
    goto LABEL_37;
  }
  v26 = (unsigned __int8)v15 >> 2;
  switch ( v26 )
  {
    case 4:
      v26 = 0;
      goto LABEL_74;
    case 8:
      if ( v9 >= 2 )
        RfcommHandleTestResponse(a1, v14, v9);
      goto LABEL_97;
    case 20:
      goto LABEL_56;
    case 24:
      goto LABEL_74;
    case 32:
      if ( v9 < 0xA )
        goto LABEL_97;
      v27 = v14[2];
      HandleMsgPN(a1, (_DWORD)v14, v9, (unsigned int)&v48, 0);
      if ( v48 )
        RefObj_ReleaseEx(v48 + 24, 1145981254, 5514, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
LABEL_58:
      if ( !v27 )
        goto LABEL_97;
      v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
      LOBYTE(v29) = 1;
      LOBYTE(v30) = v27;
      *(_BYTE *)(a1 + 64) = v28;
      v31 = ChannelFindLocked(a1, v30, v29);
      v48 = v31;
      if ( !v31 )
        goto LABEL_68;
      if ( v26 == 56
        && ((*(_DWORD *)(v31 + 48) - 4) & 0xFFFFFFFD) == 0
        && (*(_BYTE *)(v31 + 53) = 1, v33 = v48, *(_BYTE *)(v48 + 52)) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v32,
            3,
            159,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
          v33 = v48;
        }
        v34 = 5;
        if ( *(_DWORD *)(v33 + 48) != 4 )
          v34 = 7;
        ChannelSetState(v33, v34);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
        ChannelSendData(v48);
      }
      else
      {
LABEL_68:
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
      }
      if ( !v48 )
        goto LABEL_97;
      LOBYTE(v12) = v26;
      ChannelAckCommand(v48, v12, 0);
      v25 = 5599;
      v23 = v48 + 24;
      v24 = 1145981254;
      goto LABEL_95;
    case 36:
      if ( v9 >= 0xA )
        RfcommHandleRPNResponse(a1, v14);
      goto LABEL_97;
    case 40:
LABEL_74:
      LOBYTE(v12) = v26;
      SessionAckCommand(a1, v12, 0);
      goto LABEL_97;
    case 56:
LABEL_56:
      if ( v9 < 4 )
        goto LABEL_97;
      v27 = v14[2] >> 2;
      goto LABEL_58;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v5;
  WPP_RECORDER_SF_q(
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    2,
    158,
    (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
    (char)v14);
LABEL_97:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      3,
      162,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x140012c60  mov     [rsp-38h+arg_18], rbx
0x140012c65  push    rbp
0x140012c66  push    rsi
0x140012c67  push    rdi
0x140012c68  push    r12
0x140012c6a  push    r13
0x140012c6c  push    r14
0x140012c6e  push    r15
0x140012c70  mov     rbp, rsp
0x140012c73  sub     rsp, 40h
0x140012c77  mov     al, [rdx+22h]
0x140012c7a  mov     r13d, 1
0x140012c80  movzx   ebx, al
0x140012c83  mov     rsi, rdx
0x140012c86  mov     rdi, rcx
0x140012c89  test    r13b, al
0x140012c8c  jnz     short loc_140012C92
0x140012c8e  movzx   ebx, word ptr [rdx+22h]
0x140012c92  shr     ebx, 1
0x140012c94  xor     r14b, r14b
0x140012c97  mov     [rbp+arg_8], 0
0x140012c9f  lea     r8, WPP_RECORDER_INITIALIZED
0x140012ca6  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140012cad  lea     r10, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012cb4  jz      short loc_140012CE5
0x140012cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140012cbd  mov     r9d, 9Ch
0x140012cc3  mov     r8d, 3
0x140012cc9  mov     [rsp+40h+var_20], r10
0x140012cce  mov     rcx, [rcx+40h]
0x140012cd2  call    WPP_RECORDER_SF_
0x140012cd7  lea     r8, WPP_RECORDER_INITIALIZED
0x140012cde  lea     r10, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012ce5  cmp     [rdi+1D1h], r14b
0x140012cec  jz      short loc_140012CFB
0x140012cee  mov     al, [rsi+21h]
0x140012cf1  test    al, 10h
0x140012cf3  movzx   r14d, r14b
0x140012cf7  cmovnz  r14d, r13d
0x140012cfb  mov     ecx, 4
0x140012d00  cmp     [rsi+20h], cl
0x140012d03  jnb     loc_14001315A
0x140012d09  mov     al, [rsi+22h]
0x140012d0c  lea     r14, [rsi+23h]
0x140012d10  xor     r15d, r15d
0x140012d13  lea     edx, [rcx-2]
0x140012d16  not     al
0x140012d18  mov     [rbp+arg_10], r15
0x140012d1c  and     rax, r13
0x140012d1f  add     r14, rax
0x140012d22  movzx   esi, byte ptr [r14]
0x140012d26  test    dl, sil
0x140012d29  jz      loc_140012F22
0x140012d2f  xor     r12b, r12b
0x140012d32  mov     eax, esi
0x140012d34  shr     eax, 2
0x140012d37  mov     byte ptr [rbp+arg_0], r12b
0x140012d3b  cmp     eax, 8
0x140012d3e  jz      loc_140012E55
0x140012d44  cmp     eax, 14h
0x140012d47  jz      loc_140012E36
0x140012d4d  cmp     eax, 18h
0x140012d50  jz      loc_140012E31
0x140012d56  cmp     eax, 20h ; ' '
0x140012d59  jz      loc_140012E13
0x140012d5f  cmp     eax, 24h ; '$'
0x140012d62  jz      loc_140012DF5
0x140012d68  cmp     eax, 28h ; '('
0x140012d6b  jz      short loc_140012DE8
0x140012d6d  cmp     eax, 38h ; '8'
0x140012d70  jz      short loc_140012DC3
0x140012d72  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140012d79  jz      short loc_140012D9E
0x140012d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d82  mov     r9d, 9Dh
0x140012d88  mov     [rsp+40h+var_18], r14
0x140012d8d  mov     r8d, edx
0x140012d90  mov     [rsp+40h+var_20], r10
0x140012d95  mov     rcx, [rcx+40h]
0x140012d99  call    WPP_RECORDER_SF_q
0x140012d9e  mov     al, [r14]
0x140012da1  lea     r8, [rbp+arg_0]
0x140012da5  mov     r9d, 3
0x140012dab  mov     byte ptr [rbp+arg_0+2], al
0x140012dae  xor     edx, edx
0x140012db0  mov     word ptr [rbp+arg_0], 311h
0x140012db6  mov     rcx, rdi
0x140012db9  call    SessionSendResponse
0x140012dbe  jmp     loc_140012F01
0x140012dc3  cmp     ebx, ecx
0x140012dc5  jb      short loc_140012D9E
0x140012dc7  lea     rax, [rbp+arg_0]
0x140012dcb  mov     r8d, ebx
0x140012dce  lea     r9, [rbp+arg_8]
0x140012dd2  mov     [rsp+40h+var_20], rax
0x140012dd7  mov     rdx, r14
0x140012dda  mov     rcx, rdi
0x140012ddd  call    HandleMsgMSC
0x140012de2  mov     r12b, byte ptr [rbp+arg_0]
0x140012de6  jmp     short loc_140012E4D
0x140012de8  xor     r9d, r9d
0x140012deb  mov     rcx, rdi
0x140012dee  call    HandleMsgFC
0x140012df3  jmp     short loc_140012E4D
0x140012df5  lea     rax, [rbp+arg_10]
0x140012df9  mov     rdx, r14
0x140012dfc  lea     r9, [rbp+arg_8]
0x140012e00  mov     [rsp+40h+var_20], rax
0x140012e05  mov     rcx, rdi
0x140012e08  call    HandleMsgRPN
0x140012e0d  mov     r15, [rbp+arg_10]
0x140012e11  jmp     short loc_140012E4D
0x140012e13  cmp     ebx, 0Ah
0x140012e16  jb      short loc_140012D9E
0x140012e18  lea     r9, [rbp+arg_8]
0x140012e1c  mov     byte ptr [rsp+40h+var_20], r13b
0x140012e21  mov     r8d, ebx
0x140012e24  mov     rdx, r14
0x140012e27  mov     rcx, rdi
0x140012e2a  call    HandleMsgPN
0x140012e2f  jmp     short loc_140012E4D
0x140012e31  mov     r9b, r13b
0x140012e34  jmp     short loc_140012DEB
0x140012e36  cmp     ebx, ecx
0x140012e38  jb      loc_140012D9E
0x140012e3e  lea     r9, [rbp+arg_8]
0x140012e42  mov     rdx, r14
0x140012e45  mov     rcx, rdi
0x140012e48  call    HandleMsgRLS
0x140012e4d  test    al, al
0x140012e4f  jz      loc_140012EF3
0x140012e55  lea     rsi, [rdi+38h]
0x140012e59  mov     rcx, rsi; SpinLock
0x140012e5c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012e63  nop     dword ptr [rax+rax+00h]
0x140012e68  cmp     dword ptr [rdi+30h], 4
0x140012e6c  mov     rcx, rsi; SpinLock
0x140012e6f  mov     [rdi+40h], al
0x140012e72  mov     dl, al; NewIrql
0x140012e74  jle     short loc_140012E91
0x140012e76  call    cs:__imp_KeReleaseSpinLock
0x140012e7d  nop     dword ptr [rax+rax+00h]
0x140012e82  xor     r8d, r8d
0x140012e85  xor     edx, edx
0x140012e87  mov     rcx, rdi
0x140012e8a  call    RfcommSendDMEx
0x140012e8f  jmp     short loc_140012EF3
0x140012e91  call    cs:__imp_KeReleaseSpinLock
0x140012e98  nop     dword ptr [rax+rax+00h]
0x140012e9d  test    r15, r15
0x140012ea0  jnz     short loc_140012EBA
0x140012ea2  and     byte ptr [r14], 0FDh
0x140012ea6  mov     r9d, ebx
0x140012ea9  mov     rdx, [rbp+arg_8]
0x140012ead  mov     r8, r14
0x140012eb0  mov     rcx, rdi
0x140012eb3  call    SessionSendResponse
0x140012eb8  jmp     short loc_140012EF3
0x140012eba  movzx   eax, byte ptr [r15+1]
0x140012ebf  mov     r9d, eax
0x140012ec2  test    r13b, al
0x140012ec5  jnz     short loc_140012ECC
0x140012ec7  movzx   r9d, word ptr [r15+1]
0x140012ecc  mov     rdx, [rbp+arg_8]
0x140012ed0  mov     r8, r15
0x140012ed3  shr     r9d, 1
0x140012ed6  mov     rcx, rdi
0x140012ed9  add     r9d, 2
0x140012edd  call    SessionSendResponse
0x140012ee2  xor     edx, edx; Tag
0x140012ee4  mov     rcx, r15; P
0x140012ee7  call    cs:__imp_ExFreePoolWithTag
0x140012eee  nop     dword ptr [rax+rax+00h]
0x140012ef3  test    r12b, r12b
0x140012ef6  jz      short loc_140012F01
0x140012ef8  mov     rcx, [rbp+arg_8]
0x140012efc  call    ChannelSendData
0x140012f01  mov     rcx, [rbp+arg_8]
0x140012f05  test    rcx, rcx
0x140012f08  jz      loc_140013354
0x140012f0e  add     rcx, 18h
0x140012f12  mov     edx, 444E4946h
0x140012f17  mov     r8d, 1532h
0x140012f1d  jmp     loc_140013333
0x140012f22  shr     sil, 2
0x140012f26  cmp     sil, cl
0x140012f29  jz      loc_140013144
0x140012f2f  cmp     sil, 8
0x140012f33  jz      loc_140013129
0x140012f39  mov     r12d, 444E4946h
0x140012f3f  cmp     sil, 14h
0x140012f43  jz      loc_140013009
0x140012f49  cmp     sil, 18h
0x140012f4d  jz      loc_140013147
0x140012f53  cmp     sil, 20h ; ' '
0x140012f57  jz      short loc_140012FC1
0x140012f59  cmp     sil, 24h ; '$'
0x140012f5d  jz      short loc_140012FA8
0x140012f5f  cmp     sil, 28h ; '('
0x140012f63  jz      loc_140013147
0x140012f69  cmp     sil, 38h ; '8'
0x140012f6d  jz      loc_140013009
0x140012f73  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140012f7a  jz      loc_14001338C
0x140012f80  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f87  mov     r9d, 9Eh
0x140012f8d  mov     [rsp+40h+var_18], r14
0x140012f92  mov     r8d, edx
0x140012f95  mov     [rsp+40h+var_20], r10
0x140012f9a  mov     rcx, [rcx+40h]
0x140012f9e  call    WPP_RECORDER_SF_q
0x140012fa3  jmp     loc_140013354
0x140012fa8  cmp     ebx, 0Ah
0x140012fab  jb      loc_140013354
0x140012fb1  mov     rdx, r14
0x140012fb4  mov     rcx, rdi
0x140012fb7  call    RfcommHandleRPNResponse
0x140012fbc  jmp     loc_140013354
0x140012fc1  cmp     ebx, 0Ah
0x140012fc4  jb      loc_140013354
0x140012fca  mov     r15b, [r14+2]
0x140012fce  lea     r9, [rbp+arg_8]
0x140012fd2  mov     r8d, ebx
0x140012fd5  mov     byte ptr [rsp+40h+var_20], 0
0x140012fda  mov     rdx, r14
0x140012fdd  mov     rcx, rdi
0x140012fe0  call    HandleMsgPN
0x140012fe5  mov     rcx, [rbp+arg_8]
0x140012fe9  test    rcx, rcx
0x140012fec  jz      short loc_140013019
0x140012fee  add     rcx, 18h
0x140012ff2  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140012ff9  mov     r8d, 158Ah
0x140012fff  mov     rdx, r12
0x140013002  call    RefObj_ReleaseEx
0x140013007  jmp     short loc_140013019
0x140013009  cmp     ebx, ecx
0x14001300b  jb      loc_140013354
0x140013011  mov     r15b, [r14+2]
0x140013015  shr     r15b, 2
0x140013019  test    r15b, r15b
0x14001301c  jz      loc_140013354
0x140013022  lea     rbx, [rdi+38h]
0x140013026  mov     rcx, rbx; SpinLock
0x140013029  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013030  nop     dword ptr [rax+rax+00h]
0x140013035  mov     r8b, r13b
0x140013038  mov     dl, r15b
0x14001303b  mov     rcx, rdi
0x14001303e  mov     [rdi+40h], al
0x140013041  call    ChannelFindLocked
0x140013046  mov     [rbp+arg_8], rax
0x14001304a  mov     rcx, rax
0x14001304d  test    rax, rax
0x140013050  jz      loc_1400130E9
0x140013056  cmp     sil, 38h ; '8'
0x14001305a  jnz     loc_1400130E9
0x140013060  mov     eax, [rax+30h]
0x140013063  sub     eax, 4
0x140013066  test    eax, 0FFFFFFFDh
0x14001306b  jnz     short loc_1400130E9
0x14001306d  mov     [rcx+35h], r13b
0x140013071  mov     rcx, [rbp+arg_8]
0x140013075  cmp     byte ptr [rcx+34h], 0
0x140013079  jz      short loc_1400130E9
0x14001307b  lea     rax, WPP_RECORDER_INITIALIZED
0x140013082  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140013089  jz      short loc_1400130B7
0x14001308b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013092  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140013099  mov     r9d, 9Fh
0x14001309f  mov     [rsp+40h+var_20], rax
0x1400130a4  mov     r8d, 3
0x1400130aa  mov     rcx, [rcx+40h]
0x1400130ae  call    WPP_RECORDER_SF_
0x1400130b3  mov     rcx, [rbp+arg_8]
0x1400130b7  cmp     dword ptr [rcx+30h], 4
0x1400130bb  mov     edx, 5
0x1400130c0  jz      short loc_1400130C7
0x1400130c2  mov     edx, 7
0x1400130c7  call    ChannelSetState
0x1400130cc  mov     dl, [rdi+40h]; NewIrql
0x1400130cf  mov     rcx, rbx; SpinLock
0x1400130d2  call    cs:__imp_KeReleaseSpinLock
0x1400130d9  nop     dword ptr [rax+rax+00h]
0x1400130de  mov     rcx, [rbp+arg_8]
0x1400130e2  call    ChannelSendData
0x1400130e7  jmp     short loc_1400130FB
0x1400130e9  mov     dl, [rdi+40h]; NewIrql
0x1400130ec  mov     rcx, rbx; SpinLock
0x1400130ef  call    cs:__imp_KeReleaseSpinLock
0x1400130f6  nop     dword ptr [rax+rax+00h]
0x1400130fb  mov     rcx, [rbp+arg_8]
0x1400130ff  test    rcx, rcx
0x140013102  jz      loc_140013354
0x140013108  xor     r8d, r8d
0x14001310b  mov     dl, sil
0x14001310e  call    ChannelAckCommand
0x140013113  mov     rcx, [rbp+arg_8]
0x140013117  mov     r8d, 15DFh
  ... truncated ...
```
