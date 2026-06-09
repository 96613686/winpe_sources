# HandleUAFrame

- ea: `0x14001291c`
- end: `0x140012c5a`
- name: `HandleUAFrame`
- size: `830`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140003818`
- `0x140003bf4`
- `0x140007350`
- `0x14000fd78`
- `0x14001291c`
- `0x1400133b0`
- `0x140014c64`
- `0x1400157dc`
- `0x140015bdc`
- `0x1400161d0`
- `0x140016ca8`
- `0x140017db4`
- `0x140018e9c`
- `0x140019b64`
- `0x140019cd0`
- `0x140019e5c`
- `0x14001a164`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012997`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012a80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012997`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012a80`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400129d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012abf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012ad0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012b43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400129d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012abf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012ad0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012b43`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c0f`

## string_xrefs

- `0x140012a6c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140012bb3`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140012bee`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall HandleUAFrame(__int64 a1, _BYTE *a2)
{
  unsigned __int8 *v4; // rdx
  int v5; // r9d
  KSPIN_LOCK *v6; // rcx
  KIRQL v7; // al
  bool v8; // zf
  char v9; // di
  __int64 v10; // rdx
  __int64 v11; // rdx
  _QWORD *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 Locked; // rax
  __int64 v17; // rdi
  int v18; // eax
  KIRQL v19; // dl
  KSPIN_LOCK *v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rbp
  __int64 v25; // rdx
  int v26; // edx
  char v27; // bl
  _QWORD v29[9]; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    RfcommStateTxt(*(unsigned int *)(a1 + 48));
    WPP_RECORDER_SF_ds(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v4, *v4 >> 3, v5);
  }
  v6 = (KSPIN_LOCK *)(a1 + 56);
  if ( *a2 >= 4u )
  {
    *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc(v6);
    LOBYTE(v14) = 1;
    LOBYTE(v15) = *a2 >> 2;
    Locked = ChannelFindLocked(a1, v15, v14);
    v17 = Locked;
    if ( Locked )
    {
      v18 = *(_DWORD *)(Locked + 48);
      if ( v18 == 2 )
      {
        v22 = (_QWORD *)(v17 + 72);
        v23 = *(_QWORD **)(v17 + 72);
        if ( v23 == (_QWORD *)(v17 + 72) )
        {
          v24 = 0;
        }
        else
        {
          if ( (_QWORD *)v23[1] != v22 || (v25 = *v23, *(_QWORD **)(*v23 + 8LL) != v23) )
LABEL_31:
            __fastfail(3u);
          *v22 = v25;
          v24 = v23 - 35;
          *(_QWORD *)(v25 + 8) = v22;
          v23[1] = v23;
          *v23 = v23;
        }
        ChannelSetState(v17, 4);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
        RfcommStartTimer(*(_QWORD *)(a1 + 72));
        if ( (int)RfcommSendMsgMSC(v17, 0, 0, 0, 1) < 0
          && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            1,
            154,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
        }
        if ( !v24
          || (v27 = TdiCompleteConnect(v24, 0),
              RefObj_ReleaseEx(
                v24 + 3,
                1313754947,
                5199,
                "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c"),
              !v27) )
        {
          ChannelDisconnectRequest(v17, 2);
        }
      }
      else
      {
        v19 = *(_BYTE *)(a1 + 64);
        v20 = (KSPIN_LOCK *)(a1 + 56);
        if ( v18 == 8 )
        {
          KeReleaseSpinLock(v20, v19);
          ChannelDisconnectInd(v17, 2, 3221226039LL);
        }
        else
        {
          KeReleaseSpinLock(v20, v19);
        }
      }
      LOBYTE(v21) = -1;
      ChannelAckCommand(v17, v21, 0);
      RefObj_ReleaseEx(v17 + 24, 1145981254, 5232, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    }
  }
  else
  {
    v29[1] = v29;
    v29[0] = v29;
    v7 = KeAcquireSpinLockRaiseToDpc(v6);
    v8 = *(_DWORD *)(a1 + 48) == 2;
    *(_BYTE *)(a1 + 64) = v7;
    if ( v8 && (unsigned __int8)RfcommSetState(a1, 4) )
    {
      v9 = 0;
      ListDrainLocked(v29, a1 + 96);
    }
    else
    {
      v9 = 1;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    LOBYTE(v10) = -1;
    SessionAckCommand(a1, v10, 0);
    if ( v9 )
    {
      LOBYTE(v11) = 1;
      SessionDisconnectInd(a1, v11, 3221225787LL);
    }
    else
    {
      while ( 1 )
      {
        v12 = (_QWORD *)v29[0];
        if ( (_QWORD *)v29[0] == v29 )
          break;
        if ( *(_QWORD **)(v29[0] + 8LL) != v29 )
          goto LABEL_31;
        v13 = *(_QWORD *)v29[0];
        if ( *(_QWORD *)(*(_QWORD *)v29[0] + 8LL) != v29[0] )
          goto LABEL_31;
        v29[0] = *(_QWORD *)v29[0];
        *(_QWORD *)(v13 + 8) = v29;
        v12[1] = v12;
        *v12 = v12;
        ChannelConnect(v12 - 35);
        RefObj_ReleaseEx(v12 - 32, 1313754947, 5124, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      }
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      3,
      155,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return 4;
}

```

## disassembly

```asm
0x14001291c  push    rbx
0x14001291e  push    rbp
0x14001291f  push    rsi
0x140012920  push    rdi
0x140012921  push    r12
0x140012923  push    r13
0x140012925  push    r14
0x140012927  sub     rsp, 50h
0x14001292b  mov     r14, rdx
0x14001292e  mov     rbx, rcx
0x140012931  lea     r12, WPP_RECORDER_INITIALIZED
0x140012938  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001293f  jz      short loc_14001296B
0x140012941  mov     ecx, [rcx+30h]
0x140012944  call    RfcommStateTxt
0x140012949  mov     rcx, cs:WPP_GLOBAL_Control
0x140012950  movzx   r8d, byte ptr [rdx]
0x140012954  shr     r8d, 3
0x140012958  mov     [rsp+88h+var_58], rax
0x14001295d  mov     rcx, [rcx+40h]
0x140012961  mov     [rsp+88h+var_60], r8d
0x140012966  call    WPP_RECORDER_SF_ds
0x14001296b  cmp     byte ptr [r14], 4
0x14001296f  lea     rsi, [rbx+38h]
0x140012973  mov     rcx, rsi; SpinLock
0x140012976  lea     r13, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001297d  jnb     loc_140012A80
0x140012983  lea     rax, [rsp+88h+var_48]
0x140012988  mov     [rsp+88h+var_40], rax
0x14001298d  lea     rax, [rsp+88h+var_48]
0x140012992  mov     [rsp+88h+var_48], rax
0x140012997  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001299e  nop     dword ptr [rax+rax+00h]
0x1400129a3  cmp     dword ptr [rbx+30h], 2
0x1400129a7  mov     [rbx+40h], al
0x1400129aa  jnz     short loc_1400129BD
0x1400129ac  mov     edx, 4
0x1400129b1  mov     rcx, rbx
0x1400129b4  call    RfcommSetState
0x1400129b9  test    al, al
0x1400129bb  jnz     short loc_1400129C2
0x1400129bd  mov     dil, 1
0x1400129c0  jmp     short loc_1400129D3
0x1400129c2  xor     dil, dil
0x1400129c5  lea     rdx, [rbx+60h]
0x1400129c9  lea     rcx, [rsp+88h+var_48]
0x1400129ce  call    ListDrainLocked
0x1400129d3  mov     dl, [rbx+40h]; NewIrql
0x1400129d6  mov     rcx, rsi; SpinLock
0x1400129d9  call    cs:__imp_KeReleaseSpinLock
0x1400129e0  nop     dword ptr [rax+rax+00h]
0x1400129e5  xor     r8d, r8d
0x1400129e8  mov     dl, 0FFh
0x1400129ea  mov     rcx, rbx
0x1400129ed  call    SessionAckCommand
0x1400129f2  test    dil, dil
0x1400129f5  jz      short loc_140012A10
0x1400129f7  mov     r9b, 1
0x1400129fa  mov     r8d, 0C000013Bh
0x140012a00  mov     dl, r9b
0x140012a03  mov     rcx, rbx
0x140012a06  call    SessionDisconnectInd
0x140012a0b  jmp     loc_140012C1B
0x140012a10  mov     rbx, [rsp+88h+var_48]
0x140012a15  lea     rax, [rsp+88h+var_48]
0x140012a1a  cmp     rbx, rax
0x140012a1d  jz      loc_140012C1B
0x140012a23  lea     rax, [rsp+88h+var_48]
0x140012a28  cmp     [rbx+8], rax
0x140012a2c  jnz     loc_140012C02
0x140012a32  mov     rax, [rbx]
0x140012a35  cmp     [rax+8], rbx
0x140012a39  jnz     loc_140012C02
0x140012a3f  mov     [rsp+88h+var_48], rax
0x140012a44  lea     rcx, [rsp+88h+var_48]
0x140012a49  mov     [rax+8], rcx
0x140012a4d  lea     rcx, [rbx-118h]
0x140012a54  mov     [rbx+8], rbx
0x140012a58  mov     [rbx], rbx
0x140012a5b  call    ChannelConnect
0x140012a60  lea     rcx, [rbx-100h]
0x140012a67  mov     edx, 4E4E4F43h
0x140012a6c  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140012a73  mov     r8d, 1404h
0x140012a79  call    RefObj_ReleaseEx
0x140012a7e  jmp     short loc_140012A10
0x140012a80  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012a87  nop     dword ptr [rax+rax+00h]
0x140012a8c  mov     [rbx+40h], al
0x140012a8f  mov     r8b, 1
0x140012a92  mov     dl, [r14]
0x140012a95  mov     rcx, rbx
0x140012a98  shr     dl, 2
0x140012a9b  call    ChannelFindLocked
0x140012aa0  mov     rdi, rax
0x140012aa3  test    rax, rax
0x140012aa6  jz      loc_140012C09
0x140012aac  mov     eax, [rax+30h]
0x140012aaf  cmp     eax, 2
0x140012ab2  jz      short loc_140012AF4
0x140012ab4  mov     dl, [rbx+40h]; NewIrql
0x140012ab7  mov     rcx, rsi; SpinLock
0x140012aba  cmp     eax, 8
0x140012abd  jz      short loc_140012AD0
0x140012abf  call    cs:__imp_KeReleaseSpinLock
0x140012ac6  nop     dword ptr [rax+rax+00h]
0x140012acb  jmp     loc_140012BD8
0x140012ad0  call    cs:__imp_KeReleaseSpinLock
0x140012ad7  nop     dword ptr [rax+rax+00h]
0x140012adc  mov     edx, 2
0x140012ae1  mov     r8d, 0C0000237h
0x140012ae7  mov     rcx, rdi
0x140012aea  call    ChannelDisconnectInd
0x140012aef  jmp     loc_140012BD8
0x140012af4  lea     rcx, [rdi+48h]
0x140012af8  mov     rax, [rcx]
0x140012afb  cmp     rax, rcx
0x140012afe  jnz     short loc_140012B04
0x140012b00  xor     ebp, ebp
0x140012b02  jmp     short loc_140012B30
0x140012b04  cmp     [rax+8], rcx
0x140012b08  jnz     loc_140012C02
0x140012b0e  mov     rdx, [rax]
0x140012b11  cmp     [rdx+8], rax
0x140012b15  jnz     loc_140012C02
0x140012b1b  mov     [rcx], rdx
0x140012b1e  lea     rbp, [rax-118h]
0x140012b25  mov     [rdx+8], rcx
0x140012b29  mov     [rax+8], rax
0x140012b2d  mov     [rax], rax
0x140012b30  mov     edx, 4
0x140012b35  mov     rcx, rdi
0x140012b38  call    ChannelSetState
0x140012b3d  mov     dl, [rbx+40h]; NewIrql
0x140012b40  mov     rcx, rsi; SpinLock
0x140012b43  call    cs:__imp_KeReleaseSpinLock
0x140012b4a  nop     dword ptr [rax+rax+00h]
0x140012b4f  mov     rcx, [rbx+48h]
0x140012b53  call    RfcommStartTimer
0x140012b58  xor     r9d, r9d
0x140012b5b  mov     byte ptr [rsp+88h+var_68], 1
0x140012b60  xor     r8d, r8d
0x140012b63  xor     edx, edx
0x140012b65  mov     rcx, rdi
0x140012b68  call    RfcommSendMsgMSC
0x140012b6d  test    eax, eax
0x140012b6f  jns     short loc_140012B9B
0x140012b71  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012b78  jz      short loc_140012B9B
0x140012b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b81  mov     r9d, 9Ah
0x140012b87  mov     r8d, 1
0x140012b8d  mov     [rsp+88h+var_68], r13
0x140012b92  mov     rcx, [rcx+40h]
0x140012b96  call    WPP_RECORDER_SF_
0x140012b9b  test    rbp, rbp
0x140012b9e  jz      short loc_140012BCB
0x140012ba0  xor     edx, edx
0x140012ba2  mov     rcx, rbp
0x140012ba5  call    TdiCompleteConnect
0x140012baa  lea     rcx, [rbp+18h]
0x140012bae  mov     edx, 4E4E4F43h
0x140012bb3  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140012bba  mov     r8d, 144Fh
0x140012bc0  mov     bl, al
0x140012bc2  call    RefObj_ReleaseEx
0x140012bc7  test    bl, bl
0x140012bc9  jnz     short loc_140012BD8
0x140012bcb  mov     edx, 2
0x140012bd0  mov     rcx, rdi
0x140012bd3  call    ChannelDisconnectRequest
0x140012bd8  xor     r8d, r8d
0x140012bdb  mov     dl, 0FFh
0x140012bdd  mov     rcx, rdi
0x140012be0  call    ChannelAckCommand
0x140012be5  lea     rcx, [rdi+18h]
0x140012be9  mov     edx, 444E4946h
0x140012bee  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140012bf5  mov     r8d, 1470h
0x140012bfb  call    RefObj_ReleaseEx
0x140012c00  jmp     short loc_140012C1B
0x140012c02  mov     ecx, 3
0x140012c07  int     29h; Win8: RtlFailFast(ecx)
0x140012c09  mov     dl, [rbx+40h]; NewIrql
0x140012c0c  mov     rcx, rsi; SpinLock
0x140012c0f  call    cs:__imp_KeReleaseSpinLock
0x140012c16  nop     dword ptr [rax+rax+00h]
0x140012c1b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140012c22  jz      short loc_140012C45
0x140012c24  mov     rcx, cs:WPP_GLOBAL_Control
0x140012c2b  mov     r9d, 9Bh
0x140012c31  mov     r8d, 3
0x140012c37  mov     [rsp+88h+var_68], r13
0x140012c3c  mov     rcx, [rcx+40h]
0x140012c40  call    WPP_RECORDER_SF_
0x140012c45  mov     eax, 4
0x140012c4a  add     rsp, 50h
0x140012c4e  pop     r14
0x140012c50  pop     r13
0x140012c52  pop     r12
0x140012c54  pop     rdi
0x140012c55  pop     rsi
0x140012c56  pop     rbp
0x140012c57  pop     rbx
0x140012c58  retn
```
