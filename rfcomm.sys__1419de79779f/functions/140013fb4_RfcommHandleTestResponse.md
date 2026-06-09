# RfcommHandleTestResponse

- ea: `0x140013fb4`
- end: `0x1400141fc`
- name: `RfcommHandleTestResponse`
- size: `584`
- prototype: `void __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140003bf4`
- `0x140004e58`
- `0x140005c38`
- `0x14001354c`
- `0x140013fb4`
- `0x14001ea34`
- `0x14001ec2c`
- `0x140020380`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013fd0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013fd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014034`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014034`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x1400140e8`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x1400140e8`

## string_xrefs

- `0x1400141b2`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
void __fastcall RfcommHandleTestResponse(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // r14
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rbx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // edx
  size_t v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  void *v18; // rcx
  unsigned int v19; // edx

  v4 = a3;
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      3,
      105,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  LOBYTE(v7) = 8;
  v8 = RfcommAckCmdLocked(v7, a1 + 176, a1 + 184);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( v8 )
  {
    if ( (unsigned __int8)IrpList_DequeueIrp(*(_QWORD *)(v8 + 96), *(_QWORD *)(v8 + 88)) )
    {
      v12 = *(_QWORD *)(v8 + 80);
      if ( *(_QWORD *)(v12 + 88) )
      {
        v13 = *(_QWORD *)(v8 + 96);
        if ( v13 == v12 + 456 || v13 == v12 + 512 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v13,
              3,
              107,
              (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
          if ( (int)IoDecrementKeepAliveCount(*(_QWORD *)(*(_QWORD *)(v8 + 80) + 72LL)) < 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              2,
              108,
              (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
          }
        }
      }
      v15 = *(unsigned __int8 *)(a2 + 1) >> 1;
      if ( v15 <= v4 - 2 )
      {
        v16 = *(_QWORD *)(v8 + 88);
        v17 = *(_QWORD *)(v16 + 184);
        v18 = *(void **)(v16 + 24);
        v19 = *(_DWORD *)(v17 + 8);
        if ( (unsigned int)v15 >= v19 )
          v15 = v19;
        memmove(v18, (const void *)(a2 + 2), v15);
      }
      RfcommCompleteTdiIrp(*(PIRP *)(v8 + 88));
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        15,
        109,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
        *(_QWORD *)(v8 + 88),
        *(_QWORD *)(v8 + 96));
    }
    RefObj_ReleaseEx(v8 + 24, 541803329, 4134, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      2,
      106,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      110,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
}

```

## disassembly

```asm
0x140013fb4  push    rbx
0x140013fb6  push    rbp
0x140013fb7  push    rsi
0x140013fb8  push    rdi
0x140013fb9  push    r12
0x140013fbb  push    r14
0x140013fbd  push    r15
0x140013fbf  sub     rsp, 40h
0x140013fc3  mov     rdi, rcx
0x140013fc6  mov     r14d, r8d
0x140013fc9  add     rcx, 38h ; '8'; SpinLock
0x140013fcd  mov     rbp, rdx
0x140013fd0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013fd7  nop     dword ptr [rax+rax+00h]
0x140013fdc  mov     [rdi+40h], al
0x140013fdf  lea     r15, WPP_RECORDER_INITIALIZED
0x140013fe6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140013fed  lea     r12, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140013ff4  jz      short loc_140014015
0x140013ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x140013ffd  mov     r9d, 69h ; 'i'
0x140014003  mov     [rsp+78h+var_58], r12
0x140014008  mov     rcx, [rcx+40h]
0x14001400c  lea     r8d, [r9-66h]
0x140014010  call    WPP_RECORDER_SF_
0x140014015  lea     r8, [rdi+0B8h]
0x14001401c  mov     cl, 8
0x14001401e  lea     rdx, [rdi+0B0h]
0x140014025  call    RfcommAckCmdLocked
0x14001402a  mov     dl, [rdi+40h]; NewIrql
0x14001402d  lea     rcx, [rdi+38h]; SpinLock
0x140014031  mov     rbx, rax
0x140014034  call    cs:__imp_KeReleaseSpinLock
0x14001403b  nop     dword ptr [rax+rax+00h]
0x140014040  test    rbx, rbx
0x140014043  jnz     short loc_140014074
0x140014045  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001404c  jz      loc_1400141EC
0x140014052  mov     rcx, cs:WPP_GLOBAL_Control
0x140014059  lea     r9d, [rbx+6Ah]
0x14001405d  lea     r8d, [rbx+2]
0x140014061  mov     [rsp+78h+var_58], r12
0x140014066  mov     rcx, [rcx+40h]
0x14001406a  call    WPP_RECORDER_SF_
0x14001406f  jmp     loc_1400141C4
0x140014074  mov     rdx, [rbx+58h]
0x140014078  mov     rcx, [rbx+60h]
0x14001407c  call    IrpList_DequeueIrp
0x140014081  test    al, al
0x140014083  jz      loc_14001416F
0x140014089  mov     rcx, [rbx+50h]
0x14001408d  cmp     qword ptr [rcx+58h], 0
0x140014092  jz      loc_140014120
0x140014098  mov     rdx, [rbx+60h]
0x14001409c  lea     rax, [rcx+1C8h]
0x1400140a3  cmp     rdx, rax
0x1400140a6  jz      short loc_1400140B4
0x1400140a8  lea     rax, [rcx+200h]
0x1400140af  cmp     rdx, rax
0x1400140b2  jnz     short loc_140014120
0x1400140b4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400140bb  jz      short loc_1400140DC
0x1400140bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400140c4  mov     r9d, 6Bh ; 'k'
0x1400140ca  mov     [rsp+78h+var_58], r12
0x1400140cf  mov     rcx, [rcx+40h]
0x1400140d3  lea     r8d, [r9-68h]
0x1400140d7  call    WPP_RECORDER_SF_
0x1400140dc  mov     rcx, [rbx+50h]
0x1400140e0  mov     rdx, [rcx+58h]
0x1400140e4  mov     rcx, [rcx+48h]
0x1400140e8  call    cs:__imp_IoDecrementKeepAliveCount
0x1400140ef  nop     dword ptr [rax+rax+00h]
0x1400140f4  test    eax, eax
0x1400140f6  jns     short loc_140014120
0x1400140f8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400140ff  jz      short loc_140014120
0x140014101  mov     rcx, cs:WPP_GLOBAL_Control
0x140014108  mov     r9d, 6Ch ; 'l'
0x14001410e  mov     [rsp+78h+var_58], r12
0x140014113  mov     rcx, [rcx+40h]
0x140014117  lea     r8d, [r9-6Ah]
0x14001411b  call    WPP_RECORDER_SF_
0x140014120  movzx   r8d, byte ptr [rbp+1]
0x140014125  lea     rax, [r14-2]
0x140014129  shr     r8d, 1
0x14001412c  cmp     r8, rax
0x14001412f  ja      short loc_14001415A
0x140014131  mov     rcx, [rbx+58h]
0x140014135  mov     rax, [rcx+0B8h]
0x14001413c  mov     rcx, [rcx+18h]; void *
0x140014140  mov     edx, [rax+8]
0x140014143  cmp     r8d, edx
0x140014146  cmovnb  r8d, edx; Size
0x14001414a  lea     rdx, [rbp+2]; Src
0x14001414e  mov     edi, r8d
0x140014151  call    memmove
0x140014156  xor     edx, edx
0x140014158  jmp     short loc_140014161
0x14001415a  xor     edi, edi
0x14001415c  mov     edx, 0C00000C3h
0x140014161  mov     rcx, [rbx+58h]; Irp
0x140014165  mov     r8, rdi
0x140014168  call    RfcommCompleteTdiIrp
0x14001416d  jmp     short loc_1400141A9
0x14001416f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140014176  jz      short loc_1400141A9
0x140014178  mov     rax, [rbx+60h]
0x14001417c  mov     r9d, 6Dh ; 'm'
0x140014182  mov     rcx, cs:WPP_GLOBAL_Control
0x140014189  mov     [rsp+78h+var_48], rax
0x14001418e  mov     rax, [rbx+58h]
0x140014192  mov     [rsp+78h+var_50], rax
0x140014197  lea     r8d, [r9-5Eh]
0x14001419b  mov     rcx, [rcx+40h]
0x14001419f  mov     [rsp+78h+var_58], r12
0x1400141a4  call    WPP_RECORDER_SF_qq
0x1400141a9  lea     rcx, [rbx+18h]
0x1400141ad  mov     edx, 204B4341h
0x1400141b2  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400141b9  mov     r8d, 1026h
0x1400141bf  call    RefObj_ReleaseEx
0x1400141c4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400141cb  jz      short loc_1400141EC
0x1400141cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400141d4  mov     r9d, 6Eh ; 'n'
0x1400141da  mov     [rsp+78h+var_58], r12
0x1400141df  mov     rcx, [rcx+40h]
0x1400141e3  lea     r8d, [r9-6Bh]
0x1400141e7  call    WPP_RECORDER_SF_
0x1400141ec  add     rsp, 40h
0x1400141f0  pop     r15
0x1400141f2  pop     r14
0x1400141f4  pop     r12
0x1400141f6  pop     rdi
0x1400141f7  pop     rsi
0x1400141f8  pop     rbp
0x1400141f9  pop     rbx
0x1400141fa  retn
```
