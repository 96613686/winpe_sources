# HandleMsgPN

- ea: `0x14001190c`
- end: `0x140012045`
- name: `HandleMsgPN`
- size: `1849`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64 *, char)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140003bf4`
- `0x140004684`
- `0x140004a68`
- `0x140009658`
- `0x14000ab70`
- `0x140010080`
- `0x14001190c`
- `0x140014b10`
- `0x14001552c`
- `0x140016b84`
- `0x140017088`
- `0x1400195d0`
- `0x140019cd0`
- `0x140019e5c`
- `0x14001a12c`
- `0x14001a164`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400119a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a7f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400119a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011a7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011a34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011aa7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011e44`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011ec9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011a34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011aa7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011e44`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011ec9`

## string_xrefs

- `0x140011a51`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140011fa7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140011fd3`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140011ff1`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140012010`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
char __fastcall HandleMsgPN(__int64 a1, __int64 a2, __int64 a3, __int64 *a4, char a5)
{
  __int64 v5; // r12
  __int64 v9; // r13
  char v10; // r14
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 Locked; // rdi
  __int64 v14; // rax
  int v15; // edx
  __int64 v16; // r12
  __int64 v17; // rdx
  int v18; // r8d
  char v19; // bl
  __int64 v20; // rax
  int v21; // edx
  __int64 v22; // r15
  __int64 v23; // rbx
  int v24; // r9d
  unsigned __int16 v25; // ax
  unsigned __int16 v26; // ax
  __int64 v27; // rdx
  unsigned __int16 v28; // r10
  _UNKNOWN **v29; // r11
  int v30; // eax
  int v31; // ecx
  int v32; // edx
  int v34; // [rsp+20h] [rbp-68h]
  int v35; // [rsp+20h] [rbp-68h]
  __int64 v36; // [rsp+90h] [rbp+8h]
  __int64 Listener; // [rsp+98h] [rbp+10h]
  char v38; // [rsp+A0h] [rbp+18h]

  v5 = *(_QWORD *)(a1 + 72);
  v9 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(WPP_GLOBAL_Control->DeviceExtension, a2, *(unsigned __int16 *)(a2 + 6), 122);
  *a4 = 0;
  Listener = TdiFindListener(v5, (*(unsigned __int8 *)(a2 + 2) >> 1) & 0x1F);
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v10 = 1;
  LOBYTE(v11) = *(_BYTE *)(a2 + 2);
  LOBYTE(v12) = 1;
  Locked = ChannelFindLocked(a1, v11, v12);
  if ( !Locked )
  {
    v14 = ChannelCreateLocked(a1, (*(unsigned __int8 *)(a2 + 2) >> 1) & 0x1F, 0);
    Locked = v14;
    if ( !v14 )
    {
      v16 = 0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          1,
          123,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
      v19 = 0;
      goto LABEL_58;
    }
    RefObj_AddRefEx(v14 + 24, 1145981254, 4466, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  v20 = ChannelReferenceConnLocked(Locked, 1145981254);
  v36 = v20;
  v22 = v20;
  if ( v20
    && (*(_BYTE *)(v20 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v20 + 48)),
        v9 = TdiReferenceAddrLocked(v22, 1145981254),
        KeReleaseSpinLock((PKSPIN_LOCK)(v22 + 48), *(_BYTE *)(v22 + 56)),
        v9) )
  {
    v23 = v9;
  }
  else
  {
    if ( !Listener )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = 124;
LABEL_56:
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          1,
          v24,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      }
LABEL_57:
      v19 = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
      v16 = v36;
LABEL_58:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          2,
          136,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      if ( a5 )
      {
        LOBYTE(v17) = *(_BYTE *)(a2 + 2);
        RfcommSendDMEx(a1, v17, 0);
      }
      if ( Locked )
        ChannelDisconnectRequest(Locked, 4);
      goto LABEL_52;
    }
    v23 = Listener;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      15,
      125,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v23);
  if ( *(_BYTE *)(a2 + 5) || *(_BYTE *)(a2 + 8) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = 126;
      goto LABEL_56;
    }
    goto LABEL_57;
  }
  v25 = 23;
  if ( *(_DWORD *)(v23 + 196) && *(_WORD *)(v23 + 196) >= 0x17u )
    v25 = *(_WORD *)(v23 + 196);
  if ( *(_WORD *)(a2 + 6) < v25 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = 127;
      goto LABEL_56;
    }
    goto LABEL_57;
  }
  v38 = 0;
  v26 = ChannelMaxMTULocked(a1, v23);
  if ( v28 >= v26 )
    v28 = ChannelMaxMTULocked(a1, v27);
  *(_WORD *)(a2 + 6) = v28;
  *(_WORD *)(Locked + 232) = v28;
  *(_BYTE *)(Locked + 234) = *(_BYTE *)(a2 + 4);
  if ( a5 )
  {
    *a4 = Locked;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)v29 )
    {
      WPP_RECORDER_SF_Dd(
        WPP_GLOBAL_Control->DeviceExtension,
        v27,
        9,
        129,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
        *(_BYTE *)(a2 + 2),
        *(_WORD *)(a2 + 6));
      v29 = &WPP_RECORDER_INITIALIZED;
    }
    if ( *(_BYTE *)(v5 + 265) && (*(_BYTE *)(a2 + 3) & 0xF0) == 0xF0 )
    {
      *(_BYTE *)(a1 + 465) = 1;
      v30 = *(_BYTE *)(a2 + 9) & 7;
      *(_DWORD *)(Locked + 192) = 7;
      *(_DWORD *)(Locked + 228) = v30;
      *(_DWORD *)(Locked + 188) = 32;
      *(_BYTE *)(a2 + 9) = 7;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)v29 )
      {
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          9,
          130,
          v34,
          *(_DWORD *)(Locked + 228),
          *(_BYTE *)(Locked + 184),
          *(_DWORD *)(Locked + 228));
        v29 = &WPP_RECORDER_INITIALIZED;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_dDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v27,
            9,
            131,
            v35,
            *(_DWORD *)(Locked + 192),
            *(_BYTE *)(Locked + 184),
            *(_DWORD *)(Locked + 192));
          v29 = &WPP_RECORDER_INITIALIZED;
        }
      }
      *(_BYTE *)(a2 + 3) = *(_BYTE *)(a2 + 3) & 0xF | 0xE0;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)v29 )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          9,
          132,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)v29 )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          2,
          133,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      *(_BYTE *)(a1 + 465) = 0;
      *(_BYTE *)(a2 + 3) = 0;
      *(_BYTE *)(a2 + 9) = 0;
      *(_DWORD *)(Locked + 228) = 1;
    }
  }
  else
  {
    if ( *(_BYTE *)(v5 + 265) && (*(_BYTE *)(a2 + 3) & 0xF0) == 0xE0 )
    {
      *(_BYTE *)(a1 + 465) = 1;
      v31 = *(_BYTE *)(a2 + 9) & 7;
      *(_DWORD *)(Locked + 192) = 7;
      *(_DWORD *)(Locked + 228) = v31;
      *(_DWORD *)(Locked + 188) = 32;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)v29 )
      {
        WPP_RECORDER_SF_dDd(WPP_GLOBAL_Control->DeviceExtension, v27, 9, 134, v34, v31, *(_BYTE *)(Locked + 184), v31);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v32,
            9,
            135,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      }
    }
    else
    {
      *(_BYTE *)(a1 + 465) = 0;
      *(_DWORD *)(Locked + 228) = 1;
    }
    if ( *(_DWORD *)(Locked + 48) == 1 )
    {
      ChannelSetState(Locked, 2);
      v38 = 1;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  v19 = 1;
  if ( v38 )
    RfcommSendSABM(a1, Locked);
  v16 = v36;
LABEL_52:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sqd(WPP_GLOBAL_Control->DeviceExtension, (unsigned int)"FAILURE", v18, 137);
  if ( Locked && !*a4 )
    RefObj_ReleaseEx(Locked + 24, 1145981254, 4646, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( Listener )
    RefObj_ReleaseEx(
      Listener + 24,
      1145981254,
      4651,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( v9 )
    RefObj_ReleaseEx(v9 + 24, 1145981254, 4656, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( v16 )
    RefObj_ReleaseEx(v16 + 24, 1145981254, 4661, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  if ( !v19 || !a5 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x14001190c  mov     r11, rsp
0x14001190f  mov     [r11+20h], r9
0x140011913  mov     [r11+18h], r8d
0x140011917  push    rbx
0x140011918  push    rbp
0x140011919  push    rsi
0x14001191a  push    rdi
0x14001191b  push    r12
0x14001191d  push    r13
0x14001191f  push    r14
0x140011921  push    r15
0x140011923  sub     rsp, 48h
0x140011927  mov     r12, [rcx+48h]
0x14001192b  mov     rbx, r9
0x14001192e  mov     rsi, rdx
0x140011931  mov     rbp, rcx
0x140011934  xor     r13d, r13d
0x140011937  lea     rax, WPP_RECORDER_INITIALIZED
0x14001193e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011945  jz      short loc_140011986
0x140011947  cmp     [rsp+88h+arg_20], r13b
0x14001194f  lea     rcx, aRsp; "Rsp"
0x140011956  movzx   r8d, word ptr [rdx+6]
0x14001195b  lea     rax, aCmd; "Cmd"
0x140011962  cmovz   rax, rcx
0x140011966  mov     [r11-50h], r8d
0x14001196a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011971  lea     r9d, [r13+7Ah]
0x140011975  mov     [r11-58h], rbp
0x140011979  mov     [r11-60h], rax
0x14001197d  mov     rcx, [rcx+40h]
0x140011981  call    WPP_RECORDER_SF_sqd
0x140011986  mov     [rbx], r13
0x140011989  mov     rcx, r12
0x14001198c  movzx   edx, byte ptr [rsi+2]
0x140011990  shr     edx, 1
0x140011992  and     edx, 1Fh
0x140011995  call    TdiFindListener
0x14001199a  lea     rcx, [rbp+38h]; SpinLock
0x14001199e  mov     [rsp+88h+arg_8], rax
0x1400119a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400119ad  nop     dword ptr [rax+rax+00h]
0x1400119b2  mov     [rbp+40h], al
0x1400119b5  mov     r14d, 1
0x1400119bb  mov     dl, [rsi+2]
0x1400119be  mov     rcx, rbp
0x1400119c1  mov     r8b, r14b
0x1400119c4  call    ChannelFindLocked
0x1400119c9  mov     rdi, rax
0x1400119cc  mov     r15d, 444E4946h
0x1400119d2  test    rax, rax
0x1400119d5  jnz     loc_140011A60
0x1400119db  movzx   edx, byte ptr [rsi+2]
0x1400119df  xor     r8d, r8d
0x1400119e2  shr     edx, 1
0x1400119e4  mov     rcx, rbp
0x1400119e7  and     edx, 1Fh
0x1400119ea  call    ChannelCreateLocked
0x1400119ef  mov     rdi, rax
0x1400119f2  test    rax, rax
0x1400119f5  jnz     short loc_140011A47
0x1400119f7  xor     r12d, r12d
0x1400119fa  lea     rax, WPP_RECORDER_INITIALIZED
0x140011a01  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011a08  lea     r15, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140011a0f  jz      short loc_140011A2D
0x140011a11  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a18  lea     r9d, [r14+7Ah]
0x140011a1c  mov     r8d, r14d
0x140011a1f  mov     [rsp+88h+var_68], r15
0x140011a24  mov     rcx, [rcx+40h]
0x140011a28  call    WPP_RECORDER_SF_
0x140011a2d  mov     dl, [rbp+40h]; NewIrql
0x140011a30  lea     rcx, [rbp+38h]; SpinLock
0x140011a34  call    cs:__imp_KeReleaseSpinLock
0x140011a3b  nop     dword ptr [rax+rax+00h]
0x140011a40  xor     bl, bl
0x140011a42  jmp     loc_140011EDD
0x140011a47  lea     rcx, [rax+18h]
0x140011a4b  mov     r8d, 1172h
0x140011a51  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140011a58  mov     rdx, r15
0x140011a5b  call    RefObj_AddRefEx
0x140011a60  mov     edx, r15d
0x140011a63  mov     rcx, rdi
0x140011a66  call    ChannelReferenceConnLocked
0x140011a6b  mov     [rsp+88h+arg_0], rax
0x140011a73  mov     r15, rax
0x140011a76  test    rax, rax
0x140011a79  jz      short loc_140011ABD
0x140011a7b  lea     rcx, [rax+30h]; SpinLock
0x140011a7f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011a86  nop     dword ptr [rax+rax+00h]
0x140011a8b  mov     edx, 444E4946h
0x140011a90  mov     rcx, r15
0x140011a93  mov     [r15+38h], al
0x140011a97  call    TdiReferenceAddrLocked
0x140011a9c  mov     dl, [r15+38h]; NewIrql
0x140011aa0  lea     rcx, [r15+30h]; SpinLock
0x140011aa4  mov     r13, rax
0x140011aa7  call    cs:__imp_KeReleaseSpinLock
0x140011aae  nop     dword ptr [rax+rax+00h]
0x140011ab3  test    r13, r13
0x140011ab6  jz      short loc_140011ABD
0x140011ab8  mov     rbx, r13
0x140011abb  jmp     short loc_140011AF3
0x140011abd  mov     rax, [rsp+88h+arg_8]
0x140011ac5  test    rax, rax
0x140011ac8  jnz     short loc_140011AF0
0x140011aca  lea     rax, WPP_RECORDER_INITIALIZED
0x140011ad1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011ad8  lea     r15, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140011adf  jz      loc_140011EC0
0x140011ae5  mov     r9d, 7Ch ; '|'
0x140011aeb  jmp     loc_140011EA8
0x140011af0  mov     rbx, rax
0x140011af3  lea     r11, WPP_RECORDER_INITIALIZED
0x140011afa  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011b01  lea     r15, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140011b08  jz      short loc_140011B35
0x140011b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b11  mov     r9d, 7Dh ; '}'
0x140011b17  mov     [rsp+88h+var_60], rbx
0x140011b1c  mov     [rsp+88h+var_68], r15
0x140011b21  mov     rcx, [rcx+40h]
0x140011b25  lea     r8d, [r9-6Eh]
0x140011b29  call    WPP_RECORDER_SF_q
0x140011b2e  lea     r11, WPP_RECORDER_INITIALIZED
0x140011b35  cmp     byte ptr [rsi+5], 0
0x140011b39  jnz     loc_140011E99
0x140011b3f  cmp     byte ptr [rsi+8], 0
0x140011b43  jnz     loc_140011E99
0x140011b49  cmp     dword ptr [rbx+0C4h], 0
0x140011b50  mov     eax, 17h
0x140011b55  jbe     short loc_140011B66
0x140011b57  movzx   ecx, word ptr [rbx+0C4h]
0x140011b5e  cmp     ax, cx
0x140011b61  ja      short loc_140011B66
0x140011b63  movzx   eax, cx
0x140011b66  movzx   r10d, word ptr [rsi+6]
0x140011b6b  cmp     r10w, ax
0x140011b6f  jnb     short loc_140011B89
0x140011b71  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011b78  jz      loc_140011EC0
0x140011b7e  mov     r9d, 7Fh
0x140011b84  jmp     loc_140011EA8
0x140011b89  mov     rdx, rbx
0x140011b8c  mov     [rsp+88h+arg_10], 0
0x140011b94  mov     rcx, rbp
0x140011b97  call    ChannelMaxMTULocked
0x140011b9c  cmp     r10w, ax
0x140011ba0  jb      short loc_140011BAE
0x140011ba2  mov     rcx, rbp
0x140011ba5  call    ChannelMaxMTULocked
0x140011baa  movzx   r10d, ax
0x140011bae  cmp     [rsp+88h+arg_20], 0
0x140011bb6  mov     [rsi+6], r10w
0x140011bbb  mov     [rdi+0E8h], r10w
0x140011bc3  mov     al, [rsi+4]
0x140011bc6  mov     [rdi+0EAh], al
0x140011bcc  jz      loc_140011D69
0x140011bd2  mov     rax, [rsp+88h+arg_18]
0x140011bda  mov     [rax], rdi
0x140011bdd  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011be4  mov     ebx, 9
0x140011be9  jz      short loc_140011C1E
0x140011beb  movzx   ecx, byte ptr [rsi+2]
0x140011bef  lea     r9d, [rbx+78h]
0x140011bf3  movzx   eax, word ptr [rsi+6]
0x140011bf7  mov     r8d, ebx
0x140011bfa  mov     dword ptr [rsp+88h+var_58], eax
0x140011bfe  mov     dword ptr [rsp+88h+var_60], ecx
0x140011c02  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c09  mov     [rsp+88h+var_68], r15
0x140011c0e  mov     rcx, [rcx+40h]
0x140011c12  call    WPP_RECORDER_SF_Dd
0x140011c17  lea     r11, WPP_RECORDER_INITIALIZED
0x140011c1e  cmp     byte ptr [r12+109h], 0
0x140011c27  jz      loc_140011D24
0x140011c2d  mov     al, [rsi+3]
0x140011c30  and     al, 0F0h
0x140011c32  cmp     al, 0F0h
0x140011c34  jnz     loc_140011D24
0x140011c3a  mov     [rbp+1D1h], r14b
0x140011c41  movzx   eax, byte ptr [rsi+9]
0x140011c45  and     eax, 7
0x140011c48  mov     dword ptr [rdi+0C0h], 7
0x140011c52  mov     [rdi+0E4h], eax
0x140011c58  mov     dword ptr [rdi+0BCh], 20h ; ' '
0x140011c62  mov     byte ptr [rsi+9], 7
0x140011c66  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011c6d  jz      short loc_140011CEA
0x140011c6f  mov     ecx, [rdi+0E4h]
0x140011c75  mov     r9d, 82h
0x140011c7b  movzx   eax, byte ptr [rdi+0B8h]
0x140011c82  mov     r8d, ebx
0x140011c85  mov     [rsp+88h+var_50], ecx
0x140011c89  mov     dword ptr [rsp+88h+var_58], eax
0x140011c8d  mov     dword ptr [rsp+88h+var_60], ecx
0x140011c91  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c98  mov     rcx, [rcx+40h]
0x140011c9c  call    WPP_RECORDER_SF_dDd
0x140011ca1  lea     r11, WPP_RECORDER_INITIALIZED
0x140011ca8  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011caf  jz      short loc_140011CEA
0x140011cb1  mov     ecx, [rdi+0C0h]
0x140011cb7  mov     r9d, 83h
0x140011cbd  movzx   eax, byte ptr [rdi+0B8h]
0x140011cc4  mov     r8d, ebx
0x140011cc7  mov     [rsp+88h+var_50], ecx
0x140011ccb  mov     dword ptr [rsp+88h+var_58], eax
0x140011ccf  mov     dword ptr [rsp+88h+var_60], ecx
0x140011cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cda  mov     rcx, [rcx+40h]
0x140011cde  call    WPP_RECORDER_SF_dDd
0x140011ce3  lea     r11, WPP_RECORDER_INITIALIZED
0x140011cea  mov     al, [rsi+3]
0x140011ced  and     al, 0Fh
0x140011cef  or      al, 0E0h
0x140011cf1  mov     [rsi+3], al
0x140011cf4  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011cfb  jz      loc_140011E3D
0x140011d01  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d08  mov     r9d, 84h
0x140011d0e  mov     r8d, ebx
0x140011d11  mov     [rsp+88h+var_68], r15
0x140011d16  mov     rcx, [rcx+40h]
0x140011d1a  call    WPP_RECORDER_SF_
0x140011d1f  jmp     loc_140011E3D
0x140011d24  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011d2b  jz      short loc_140011D4E
0x140011d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d34  mov     r9d, 85h
0x140011d3a  mov     r8d, 2
0x140011d40  mov     [rsp+88h+var_68], r15
0x140011d45  mov     rcx, [rcx+40h]
0x140011d49  call    WPP_RECORDER_SF_
0x140011d4e  mov     byte ptr [rbp+1D1h], 0
0x140011d55  mov     byte ptr [rsi+3], 0
0x140011d59  mov     byte ptr [rsi+9], 0
0x140011d5d  mov     [rdi+0E4h], r14d
0x140011d64  jmp     loc_140011E3D
0x140011d69  cmp     byte ptr [r12+109h], 0
0x140011d72  jz      loc_140011E14
0x140011d78  mov     al, [rsi+3]
0x140011d7b  and     al, 0F0h
0x140011d7d  cmp     al, 0E0h
0x140011d7f  jnz     loc_140011E14
0x140011d85  mov     [rbp+1D1h], r14b
0x140011d8c  movzx   ecx, byte ptr [rsi+9]
0x140011d90  and     ecx, 7
0x140011d93  mov     dword ptr [rdi+0C0h], 7
0x140011d9d  mov     [rdi+0E4h], ecx
0x140011da3  mov     dword ptr [rdi+0BCh], 20h ; ' '
0x140011dad  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x140011db4  jz      short loc_140011E22
0x140011db6  movzx   eax, byte ptr [rdi+0B8h]
0x140011dbd  mov     r9d, 86h
0x140011dc3  mov     [rsp+88h+var_50], ecx
0x140011dc7  mov     dword ptr [rsp+88h+var_58], eax
0x140011dcb  mov     dword ptr [rsp+88h+var_60], ecx
0x140011dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140011dd6  lea     ebx, [r9-7Dh]
0x140011dda  mov     r8d, ebx
0x140011ddd  mov     rcx, [rcx+40h]
0x140011de1  call    WPP_RECORDER_SF_dDd
0x140011de6  lea     rax, WPP_RECORDER_INITIALIZED
0x140011ded  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011df4  jz      short loc_140011E22
0x140011df6  mov     rcx, cs:WPP_GLOBAL_Control
0x140011dfd  lea     r9d, [rbx+7Eh]
0x140011e01  mov     r8d, ebx
0x140011e04  mov     [rsp+88h+var_68], r15
0x140011e09  mov     rcx, [rcx+40h]
0x140011e0d  call    WPP_RECORDER_SF_
0x140011e12  jmp     short loc_140011E22
0x140011e14  mov     byte ptr [rbp+1D1h], 0
0x140011e1b  mov     [rdi+0E4h], r14d
0x140011e22  cmp     [rdi+30h], r14d
0x140011e26  jnz     short loc_140011E3D
0x140011e28  mov     edx, 2
0x140011e2d  mov     rcx, rdi
0x140011e30  call    ChannelSetState
0x140011e35  mov     [rsp+88h+arg_10], r14b
0x140011e3d  mov     dl, [rbp+40h]; NewIrql
0x140011e40  lea     rcx, [rbp+38h]; SpinLock
0x140011e44  call    cs:__imp_KeReleaseSpinLock
0x140011e4b  nop     dword ptr [rax+rax+00h]
0x140011e50  cmp     [rsp+88h+arg_10], 0
0x140011e58  mov     bl, r14b
0x140011e5b  jz      short loc_140011E68
0x140011e5d  mov     rdx, rdi
0x140011e60  mov     rcx, rbp
0x140011e63  call    RfcommSendSABM
0x140011e68  mov     r12, [rsp+88h+arg_0]
0x140011e70  lea     rax, WPP_RECORDER_INITIALIZED
0x140011e77  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011e7e  jz      loc_140011F85
0x140011e84  test    rdi, rdi
0x140011e87  jz      loc_140011F41
  ... truncated ...
```
