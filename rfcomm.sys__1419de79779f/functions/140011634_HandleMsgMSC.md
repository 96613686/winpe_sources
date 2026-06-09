# HandleMsgMSC

- ea: `0x140011634`
- end: `0x140011904`
- name: `HandleMsgMSC`
- size: `720`
- prototype: `char __fastcall(__int64, _BYTE *, int, __int64 *, _BYTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140003bf4`
- `0x140005c38`
- `0x140010260`
- `0x140011634`
- `0x140019e5c`
- `0x14001a12c`
- `0x14001a164`
- `0x14001ea34`
- `0x14001ebd8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011811`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118f3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011811`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400118f3`

## string_xrefs

- `0x140011874`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
char __fastcall HandleMsgMSC(__int64 a1, _BYTE *a2, int a3, __int64 *a4, _BYTE *a5)
{
  char v7; // di
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 Locked; // rax
  __int64 v11; // rbx
  char v12; // r13
  int v13; // edx
  __int64 v14; // rbp
  bool v15; // cl
  int v16; // eax
  __int64 v17; // rdx
  int v18; // edx
  IRP *v19; // rax
  _IRP *MasterIrp; // rdx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      100,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  *a5 = 0;
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v7 = 1;
  LOBYTE(v8) = a2[2] >> 2;
  LOBYTE(v9) = 1;
  Locked = ChannelFindLocked(a1, v8, v9);
  v11 = Locked;
  if ( !Locked )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    v7 = 0;
    goto LABEL_30;
  }
  v12 = 0;
  v14 = ChannelReferenceConnLocked(Locked, 1312901187);
  v15 = (*(_BYTE *)(v11 + 208) & 2) != 0 || *(_BYTE *)(*(_QWORD *)(v11 + 56) + 464LL);
  LOBYTE(v13) = a2[3] & 0xCE;
  v16 = *(_DWORD *)(v11 + 48) - 4;
  *(_BYTE *)(v11 + 208) = v13;
  if ( (v16 & 0xFFFFFFFD) != 0 )
  {
    if ( !*(_BYTE *)(a1 + 465) && v15 && (v13 & 2) == 0 && !*(_BYTE *)(*(_QWORD *)(v11 + 56) + 464LL) )
    {
      ++*(_DWORD *)(v11 + 228);
      v12 = 1;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          9,
          102,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
    }
  }
  else
  {
    *(_BYTE *)(v11 + 52) = 1;
    if ( *(_BYTE *)(v11 + 53) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          3,
          101,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      v17 = 5;
      if ( *(_DWORD *)(v11 + 48) != 4 )
        v17 = 7;
      ChannelSetState(v11, v17);
      *a5 = 1;
    }
  }
  *(_BYTE *)(v11 + 208) = a2[3];
  if ( a3 == 2 )
    *(_BYTE *)(v11 + 209) = a2[4];
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( v14 && (v19 = (IRP *)IrpList_Dequeue(v14 + 736)) != 0 )
  {
    MasterIrp = v19->AssociatedIrp.MasterIrp;
    *(_QWORD *)&MasterIrp->Type = 0;
    LOWORD(MasterIrp->MdlAddress) = 0;
    BYTE2(MasterIrp->MdlAddress) = 0;
    *(_DWORD *)&MasterIrp->Type = 1;
    *(&MasterIrp->Size + 1) = *(_WORD *)(a2 + 3);
    RfcommCompleteTdiIrp(v19);
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)(v11 + 204), 1);
    if ( !v14 )
      goto LABEL_28;
  }
  RefObj_ReleaseEx(v14 + 24, 1312901187, 3999, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
LABEL_28:
  if ( v12 )
    ChannelSendData(v11);
LABEL_30:
  *a4 = v11;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      3,
      104,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x140011634  mov     r11, rsp
0x140011637  mov     [r11+8], rbx
0x14001163b  mov     [r11+20h], r9
0x14001163f  mov     [r11+18h], r8d
0x140011643  push    rbp
0x140011644  push    rsi
0x140011645  push    rdi
0x140011646  push    r12
0x140011648  push    r13
0x14001164a  push    r14
0x14001164c  push    r15
0x14001164e  sub     rsp, 30h
0x140011652  mov     r14, rdx
0x140011655  mov     rsi, rcx
0x140011658  lea     rax, WPP_RECORDER_INITIALIZED
0x14001165f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011666  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001166d  jz      short loc_14001168D
0x14001166f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011676  mov     r9d, 64h ; 'd'
0x14001167c  mov     [r11-48h], rbp
0x140011680  mov     rcx, [rcx+40h]
0x140011684  lea     r8d, [r9-61h]
0x140011688  call    WPP_RECORDER_SF_
0x14001168d  mov     r12, [rsp+68h+arg_20]
0x140011695  lea     r15, [rsi+38h]
0x140011699  mov     rcx, r15; SpinLock
0x14001169c  mov     byte ptr [r12], 0
0x1400116a1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400116a8  nop     dword ptr [rax+rax+00h]
0x1400116ad  mov     [rsi+40h], al
0x1400116b0  mov     edi, 1
0x1400116b5  mov     dl, [r14+2]
0x1400116b9  mov     rcx, rsi
0x1400116bc  shr     dl, 2
0x1400116bf  mov     r8b, dil
0x1400116c2  call    ChannelFindLocked
0x1400116c7  mov     rbx, rax
0x1400116ca  test    rax, rax
0x1400116cd  jz      loc_1400118ED
0x1400116d3  mov     edx, 4E414843h
0x1400116d8  mov     rcx, rax
0x1400116db  xor     r13b, r13b
0x1400116de  call    ChannelReferenceConnLocked
0x1400116e3  test    byte ptr [rbx+0D0h], 2
0x1400116ea  mov     rbp, rax
0x1400116ed  jnz     short loc_140011700
0x1400116ef  mov     rcx, [rbx+38h]
0x1400116f3  cmp     [rcx+1D0h], r13b
0x1400116fa  jnz     short loc_140011700
0x1400116fc  xor     cl, cl
0x1400116fe  jmp     short loc_140011703
0x140011700  mov     cl, dil
0x140011703  mov     dl, [r14+3]
0x140011707  mov     eax, [rbx+30h]
0x14001170a  and     dl, 0CEh
0x14001170d  sub     eax, 4
0x140011710  mov     [rbx+0D0h], dl
0x140011716  test    eax, 0FFFFFFFDh
0x14001171b  jz      short loc_140011791
0x14001171d  cmp     [rsi+1D1h], r13b
0x140011724  jnz     loc_1400117ED
0x14001172a  test    cl, cl
0x14001172c  jz      loc_1400117ED
0x140011732  test    dl, 2
0x140011735  jnz     loc_1400117ED
0x14001173b  mov     rax, [rbx+38h]
0x14001173f  cmp     [rax+1D0h], r13b
0x140011746  jnz     loc_1400117ED
0x14001174c  add     [rbx+0E4h], edi
0x140011752  mov     r13b, dil
0x140011755  lea     rax, WPP_RECORDER_INITIALIZED
0x14001175c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011763  jz      loc_1400117ED
0x140011769  mov     rcx, cs:WPP_GLOBAL_Control
0x140011770  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140011777  mov     r9d, 66h ; 'f'
0x14001177d  mov     [rsp+68h+var_48], rax
0x140011782  mov     rcx, [rcx+40h]
0x140011786  lea     r8d, [r9-5Dh]
0x14001178a  call    WPP_RECORDER_SF_
0x14001178f  jmp     short loc_1400117ED
0x140011791  mov     [rbx+34h], dil
0x140011795  cmp     [rbx+35h], r13b
0x140011799  jz      short loc_1400117ED
0x14001179b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400117a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400117a9  jz      short loc_1400117D1
0x1400117ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400117b2  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400117b9  mov     r9d, 65h ; 'e'
0x1400117bf  mov     [rsp+68h+var_48], rax
0x1400117c4  mov     rcx, [rcx+40h]
0x1400117c8  lea     r8d, [r9-62h]
0x1400117cc  call    WPP_RECORDER_SF_
0x1400117d1  cmp     dword ptr [rbx+30h], 4
0x1400117d5  mov     rcx, rbx
0x1400117d8  mov     edx, 5
0x1400117dd  jz      short loc_1400117E4
0x1400117df  mov     edx, 7
0x1400117e4  call    ChannelSetState
0x1400117e9  mov     [r12], dil
0x1400117ed  cmp     [rsp+68h+arg_10], 2
0x1400117f5  mov     al, [r14+3]
0x1400117f9  mov     [rbx+0D0h], al
0x1400117ff  jnz     short loc_14001180B
0x140011801  mov     al, [r14+4]
0x140011805  mov     [rbx+0D1h], al
0x14001180b  mov     dl, [rsi+40h]; NewIrql
0x14001180e  mov     rcx, r15; SpinLock
0x140011811  call    cs:__imp_KeReleaseSpinLock
0x140011818  nop     dword ptr [rax+rax+00h]
0x14001181d  test    rbp, rbp
0x140011820  jz      short loc_14001185E
0x140011822  lea     rcx, [rbp+2E0h]
0x140011829  call    IrpList_Dequeue
0x14001182e  test    rax, rax
0x140011831  jz      short loc_14001185E
0x140011833  mov     rdx, [rax+18h]
0x140011837  xor     ecx, ecx
0x140011839  mov     [rdx], rcx
0x14001183c  mov     [rdx+8], cx
0x140011840  mov     [rdx+0Ah], cl
0x140011843  mov     [rdx], edi
0x140011845  movzx   ecx, word ptr [r14+3]
0x14001184a  mov     [rdx+4], cx
0x14001184e  xor     edx, edx
0x140011850  mov     rcx, rax; Irp
0x140011853  lea     r8d, [rdx+0Bh]
0x140011857  call    RfcommCompleteTdiIrp
0x14001185c  jmp     short loc_14001186B
0x14001185e  mov     eax, edi
0x140011860  xchg    eax, [rbx+0CCh]
0x140011866  test    rbp, rbp
0x140011869  jz      short loc_140011886
0x14001186b  lea     rcx, [rbp+18h]
0x14001186f  mov     edx, 4E414843h
0x140011874  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001187b  mov     r8d, 0F9Fh
0x140011881  call    RefObj_ReleaseEx
0x140011886  test    r13b, r13b
0x140011889  jz      short loc_140011893
0x14001188b  mov     rcx, rbx
0x14001188e  call    ChannelSendData
0x140011893  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001189a  mov     rax, [rsp+68h+arg_18]
0x1400118a2  mov     [rax], rbx
0x1400118a5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400118ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400118b3  jz      short loc_1400118D4
0x1400118b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118bc  mov     r9d, 68h ; 'h'
0x1400118c2  mov     [rsp+68h+var_48], rbp
0x1400118c7  mov     rcx, [rcx+40h]
0x1400118cb  lea     r8d, [r9-65h]
0x1400118cf  call    WPP_RECORDER_SF_
0x1400118d4  mov     rbx, [rsp+68h+arg_0]
0x1400118d9  mov     al, dil
0x1400118dc  add     rsp, 30h
0x1400118e0  pop     r15
0x1400118e2  pop     r14
0x1400118e4  pop     r13
0x1400118e6  pop     r12
0x1400118e8  pop     rdi
0x1400118e9  pop     rsi
0x1400118ea  pop     rbp
0x1400118eb  retn
0x1400118ed  mov     dl, [rsi+40h]; NewIrql
0x1400118f0  mov     rcx, r15; SpinLock
0x1400118f3  call    cs:__imp_KeReleaseSpinLock
0x1400118fa  nop     dword ptr [rax+rax+00h]
0x1400118ff  xor     dil, dil
0x140011902  jmp     short loc_14001189A
```
