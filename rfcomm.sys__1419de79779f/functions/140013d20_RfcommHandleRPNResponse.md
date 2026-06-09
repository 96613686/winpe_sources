# RfcommHandleRPNResponse

- ea: `0x140013d20`
- end: `0x140013fad`
- name: `RfcommHandleRPNResponse`
- size: `653`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x140005c38`
- `0x14001354c`
- `0x140013d20`
- `0x140019e5c`
- `0x14001ea34`
- `0x14001ec2c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013d3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013dbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f69`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013dbc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013f69`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x140013e70`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x140013e70`

## string_xrefs

- `0x140013f34`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140013f4f`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
void __fastcall RfcommHandleRPNResponse(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 Locked; // rax
  __int64 v8; // rcx
  __int64 v9; // r14
  __int64 v10; // rbx
  int v11; // edx
  int v12; // edx
  int v13; // r9d
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  __int64 v17; // rcx
  int v18; // edx
  unsigned __int64 v19; // r8
  int v20; // edx

  v2 = (KSPIN_LOCK *)(a1 + 56);
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      111,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  LOBYTE(v6) = 1;
  LOBYTE(v5) = *(_BYTE *)(a2 + 2) >> 2;
  Locked = ChannelFindLocked(a1, v5, v6);
  v9 = Locked;
  if ( Locked )
  {
    LOBYTE(v8) = 36;
    v10 = RfcommAckCmdLocked(v8, Locked + 136, Locked + 144);
    KeReleaseSpinLock(v2, *(_BYTE *)(a1 + 64));
    if ( v10 )
    {
      if ( (unsigned __int8)IrpList_DequeueIrp(*(_QWORD *)(v10 + 96), *(_QWORD *)(v10 + 88)) )
      {
        v14 = *(_QWORD *)(v10 + 80);
        if ( *(_QWORD *)(v14 + 88) )
        {
          v15 = *(_QWORD *)(v10 + 96);
          if ( v15 == v14 + 456 || v15 == v14 + 512 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v15,
                3,
                113,
                (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
            if ( (int)IoDecrementKeepAliveCount(*(_QWORD *)(*(_QWORD *)(v10 + 80) + 72LL)) < 0
              && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v16,
                2,
                114,
                (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
            }
          }
        }
        if ( (*(_BYTE *)(a2 + 1) & 0xFE) == 0x10 )
        {
          v17 = *(_QWORD *)(*(_QWORD *)(v10 + 88) + 24LL);
          v18 = 0;
          *(_QWORD *)v17 = 0;
          *(_WORD *)(v17 + 8) = 0;
          v19 = 11;
          *(_BYTE *)(v17 + 10) = 0;
          *(_DWORD *)v17 = 5;
          *(_DWORD *)(v17 + 4) = *(_DWORD *)(a2 + 3);
          *(_WORD *)(v17 + 8) = *(_WORD *)(a2 + 7);
          *(_BYTE *)(v17 + 10) = *(_BYTE *)(a2 + 9);
        }
        else
        {
          v19 = 0;
          v18 = -1073741629;
        }
        RfcommCompleteTdiIrp(*(PIRP *)(v10 + 88), v18, v19, v13);
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          15,
          115,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          *(_QWORD *)(v10 + 88));
      }
      RefObj_ReleaseEx(v10 + 24, 541803329, 4242, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        2,
        112,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
    }
    RefObj_ReleaseEx(v9 + 24, 1145981254, 4245, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  else
  {
    KeReleaseSpinLock(v2, *(_BYTE *)(a1 + 64));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v20,
      3,
      116,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
}

```

## disassembly

```asm
0x140013d20  push    rbx
0x140013d22  push    rbp
0x140013d23  push    rsi
0x140013d24  push    rdi
0x140013d25  push    r12
0x140013d27  push    r14
0x140013d29  push    r15
0x140013d2b  sub     rsp, 30h
0x140013d2f  lea     rsi, [rcx+38h]
0x140013d33  mov     rdi, rcx
0x140013d36  mov     rcx, rsi; SpinLock
0x140013d39  mov     rbp, rdx
0x140013d3c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013d43  nop     dword ptr [rax+rax+00h]
0x140013d48  mov     [rdi+40h], al
0x140013d4b  lea     r15, WPP_RECORDER_INITIALIZED
0x140013d52  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013d59  lea     r12, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140013d60  jz      short loc_140013D81
0x140013d62  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d69  mov     r9d, 6Fh ; 'o'
0x140013d6f  mov     [rsp+68h+var_48], r12
0x140013d74  mov     rcx, [rcx+40h]
0x140013d78  lea     r8d, [r9-6Ch]
0x140013d7c  call    WPP_RECORDER_SF_
0x140013d81  mov     dl, [rbp+2]
0x140013d84  mov     r8b, 1
0x140013d87  shr     dl, 2
0x140013d8a  mov     rcx, rdi
0x140013d8d  call    ChannelFindLocked
0x140013d92  mov     r14, rax
0x140013d95  test    rax, rax
0x140013d98  jz      loc_140013F63
0x140013d9e  lea     r8, [rax+90h]
0x140013da5  mov     cl, 24h ; '$'
0x140013da7  lea     rdx, [rax+88h]
0x140013dae  call    RfcommAckCmdLocked
0x140013db3  mov     dl, [rdi+40h]; NewIrql
0x140013db6  mov     rcx, rsi; SpinLock
0x140013db9  mov     rbx, rax
0x140013dbc  call    cs:__imp_KeReleaseSpinLock
0x140013dc3  nop     dword ptr [rax+rax+00h]
0x140013dc8  test    rbx, rbx
0x140013dcb  jnz     short loc_140013DFC
0x140013dcd  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013dd4  jz      loc_140013F46
0x140013dda  mov     rcx, cs:WPP_GLOBAL_Control
0x140013de1  lea     r9d, [rbx+70h]
0x140013de5  lea     r8d, [rbx+2]
0x140013de9  mov     [rsp+68h+var_48], r12
0x140013dee  mov     rcx, [rcx+40h]
0x140013df2  call    WPP_RECORDER_SF_
0x140013df7  jmp     loc_140013F46
0x140013dfc  mov     rdx, [rbx+58h]
0x140013e00  mov     rcx, [rbx+60h]
0x140013e04  call    IrpList_DequeueIrp
0x140013e09  test    al, al
0x140013e0b  jz      loc_140013EFA
0x140013e11  mov     rcx, [rbx+50h]
0x140013e15  cmp     qword ptr [rcx+58h], 0
0x140013e1a  jz      loc_140013EA8
0x140013e20  mov     rdx, [rbx+60h]
0x140013e24  lea     rax, [rcx+1C8h]
0x140013e2b  cmp     rdx, rax
0x140013e2e  jz      short loc_140013E3C
0x140013e30  lea     rax, [rcx+200h]
0x140013e37  cmp     rdx, rax
0x140013e3a  jnz     short loc_140013EA8
0x140013e3c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013e43  jz      short loc_140013E64
0x140013e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e4c  mov     r9d, 71h ; 'q'
0x140013e52  mov     [rsp+68h+var_48], r12
0x140013e57  mov     rcx, [rcx+40h]
0x140013e5b  lea     r8d, [r9-6Eh]
0x140013e5f  call    WPP_RECORDER_SF_
0x140013e64  mov     rcx, [rbx+50h]
0x140013e68  mov     rdx, [rcx+58h]
0x140013e6c  mov     rcx, [rcx+48h]
0x140013e70  call    cs:__imp_IoDecrementKeepAliveCount
0x140013e77  nop     dword ptr [rax+rax+00h]
0x140013e7c  test    eax, eax
0x140013e7e  jns     short loc_140013EA8
0x140013e80  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013e87  jz      short loc_140013EA8
0x140013e89  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e90  mov     r9d, 72h ; 'r'
0x140013e96  mov     [rsp+68h+var_48], r12
0x140013e9b  mov     rcx, [rcx+40h]
0x140013e9f  lea     r8d, [r9-70h]
0x140013ea3  call    WPP_RECORDER_SF_
0x140013ea8  mov     al, [rbp+1]
0x140013eab  and     al, 0FEh
0x140013ead  cmp     al, 10h
0x140013eaf  jnz     short loc_140013EE7
0x140013eb1  mov     rax, [rbx+58h]
0x140013eb5  mov     rcx, [rax+18h]
0x140013eb9  xor     eax, eax
0x140013ebb  xor     edx, edx
0x140013ebd  mov     [rcx], rax
0x140013ec0  mov     [rcx+8], ax
0x140013ec4  lea     r8d, [rdx+0Bh]
0x140013ec8  mov     [rcx+0Ah], al
0x140013ecb  mov     dword ptr [rcx], 5
0x140013ed1  mov     eax, [rbp+3]
0x140013ed4  mov     [rcx+4], eax
0x140013ed7  movzx   eax, word ptr [rbp+7]
0x140013edb  mov     [rcx+8], ax
0x140013edf  mov     al, [rbp+9]
0x140013ee2  mov     [rcx+0Ah], al
0x140013ee5  jmp     short loc_140013EEF
0x140013ee7  xor     r8d, r8d
0x140013eea  mov     edx, 0C00000C3h
0x140013eef  mov     rcx, [rbx+58h]; Irp
0x140013ef3  call    RfcommCompleteTdiIrp
0x140013ef8  jmp     short loc_140013F2B
0x140013efa  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013f01  jz      short loc_140013F2B
0x140013f03  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f0a  mov     r9d, 73h ; 's'
0x140013f10  mov     rax, [rbx+58h]
0x140013f14  mov     [rsp+68h+var_40], rax
0x140013f19  mov     [rsp+68h+var_48], r12
0x140013f1e  mov     rcx, [rcx+40h]
0x140013f22  lea     r8d, [r9-64h]
0x140013f26  call    WPP_RECORDER_SF_q
0x140013f2b  lea     rcx, [rbx+18h]
0x140013f2f  mov     edx, 204B4341h
0x140013f34  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140013f3b  mov     r8d, 1092h
0x140013f41  call    RefObj_ReleaseEx
0x140013f46  lea     rcx, [r14+18h]
0x140013f4a  mov     edx, 444E4946h
0x140013f4f  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140013f56  mov     r8d, 1095h
0x140013f5c  call    RefObj_ReleaseEx
0x140013f61  jmp     short loc_140013F75
0x140013f63  mov     dl, [rdi+40h]; NewIrql
0x140013f66  mov     rcx, rsi; SpinLock
0x140013f69  call    cs:__imp_KeReleaseSpinLock
0x140013f70  nop     dword ptr [rax+rax+00h]
0x140013f75  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013f7c  jz      short loc_140013F9D
0x140013f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f85  mov     r9d, 74h ; 't'
0x140013f8b  mov     [rsp+68h+var_48], r12
0x140013f90  mov     rcx, [rcx+40h]
0x140013f94  lea     r8d, [r9-71h]
0x140013f98  call    WPP_RECORDER_SF_
0x140013f9d  add     rsp, 30h
0x140013fa1  pop     r15
0x140013fa3  pop     r14
0x140013fa5  pop     r12
0x140013fa7  pop     rdi
0x140013fa8  pop     rsi
0x140013fa9  pop     rbp
0x140013faa  pop     rbx
0x140013fab  retn
```
