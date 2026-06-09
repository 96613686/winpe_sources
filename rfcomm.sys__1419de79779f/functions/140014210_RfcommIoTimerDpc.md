# RfcommIoTimerDpc

- ea: `0x140014210`
- end: `0x140014798`
- name: `RfcommIoTimerDpc`
- size: `1416`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400038fc`
- `0x140003bf4`
- `0x14000fd78`
- `0x140010260`
- `0x140014210`
- `0x1400161d0`
- `0x140017db4`
- `0x140019b64`
- `0x14001a164`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001428a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014367`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400146c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001428a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014367`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400146c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400142a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001455c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014596`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014743`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400142a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001455c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014596`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400146e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014743`

## string_xrefs

- `0x140014315`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140014435`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140014508`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x14001462f`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140014766`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
void __fastcall RfcommIoTimerDpc(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  KSPIN_LOCK *p_DpcData; // r14
  KIRQL v5; // al
  _QWORD *v6; // rdx
  bool v7; // zf
  char v8; // si
  KSPIN_LOCK v9; // rbx
  int v10; // ecx
  __int64 v11; // rcx
  volatile signed __int32 *i; // rdi
  int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // r8
  char v16; // cl
  int v17; // edx
  __int64 v18; // rcx
  unsigned int v19; // r8d
  int v20; // edx
  int v21; // r9d
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rbx
  _QWORD *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rsi
  KIRQL v33; // al
  int v34; // edx
  __int64 v35; // rdx
  _QWORD v36[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v37[3]; // [rsp+40h] [rbp-18h] BYREF

  v36[1] = v36;
  p_DpcData = (KSPIN_LOCK *)&Dpc[-4].DpcData;
  v36[0] = v36;
  v37[1] = v37;
  v37[0] = v37;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)DeferredContext,
      3,
      179,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  v5 = KeAcquireSpinLockRaiseToDpc(p_DpcData + 3);
  v7 = *((_BYTE *)p_DpcData + 129) == 0;
  *((_BYTE *)p_DpcData + 32) = v5;
  if ( !v7 )
  {
    KeReleaseSpinLock(p_DpcData + 3, v5);
    return;
  }
  v8 = 1;
  v9 = p_DpcData[36];
  *((_BYTE *)p_DpcData + 129) = 1;
LABEL_44:
  if ( (KSPIN_LOCK *)v9 != p_DpcData + 36 )
  {
    v10 = _InterlockedDecrement((volatile signed __int32 *)(v9 + 184));
    if ( !v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v6,
          3,
          180,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
      RefObj_AddRefEx(v9 + 24, 1129531716, 6381, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      v11 = v36[0];
      if ( *(_QWORD **)(v36[0] + 8LL) != v36 )
        goto LABEL_69;
      *(_QWORD *)(v9 + 144) = v36[0];
      v6 = v36;
      *(_QWORD *)(v9 + 152) = v36;
      *(_QWORD *)(v11 + 8) = v9 + 144;
      v36[0] = v9 + 144;
      goto LABEL_43;
    }
    if ( v10 >= 0 )
      v8 = 0;
    *(_BYTE *)(v9 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 56));
    for ( i = *(volatile signed __int32 **)(v9 + 80); ; i = *(volatile signed __int32 **)i )
    {
      if ( i == (volatile signed __int32 *)(v9 + 80) )
      {
        v19 = *(_DWORD *)(v9 + 188);
        v20 = *(_DWORD *)(v9 + 48);
        *(_DWORD *)(v9 + 188) = v19 + 1;
        if ( ((v20 - 3) & 0xFFFFFFFD) != 0 )
          goto LABEL_42;
        if ( v19 == 59 )
        {
          if ( v20 == 5 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v21 = 183;
              goto LABEL_37;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v21 = 184;
LABEL_37:
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v20,
              3,
              v21,
              (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
          }
          RefObj_AddRefEx(v9 + 24, 1129531716, 6491, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
          v22 = v36[0];
          if ( *(_QWORD **)(v36[0] + 8LL) == v36 )
          {
            *(_QWORD *)(v9 + 144) = v36[0];
            *(_QWORD *)(v9 + 152) = v36;
            *(_QWORD *)(v22 + 8) = v9 + 144;
            v36[0] = v9 + 144;
            goto LABEL_42;
          }
LABEL_69:
          __fastfail(3u);
        }
        if ( v19 <= 0x3A )
          v8 = 0;
LABEL_42:
        KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 56), *(_BYTE *)(v9 + 64));
LABEL_43:
        v9 = *(_QWORD *)v9;
        goto LABEL_44;
      }
      v13 = _InterlockedDecrement(i + 36);
      if ( v13 )
      {
        v16 = v8;
        if ( v13 > 0 )
          v16 = 0;
        v8 = v16;
        v17 = _InterlockedDecrement(i + 37);
        if ( v17 )
        {
          if ( v17 > 0 )
            v8 = 0;
          continue;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            3,
            182,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
        v14 = 1111705667;
        v15 = 6438;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            3,
            181,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
        v14 = 1129531716;
        v15 = 6416;
      }
      RefObj_AddRefEx(i + 6, v14, v15, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      v18 = v37[0];
      if ( *(_QWORD **)(v37[0] + 8LL) != v37 )
        goto LABEL_69;
      *((_QWORD *)i + 11) = v37[0];
      *((_QWORD *)i + 12) = v37;
      *(_QWORD *)(v18 + 8) = i + 22;
      v37[0] = i + 22;
    }
  }
  if ( v8 )
    RfcommStopTimerLocked(p_DpcData);
  KeReleaseSpinLock(p_DpcData + 3, *((_BYTE *)p_DpcData + 32));
  while ( 1 )
  {
    v23 = (_QWORD *)v36[0];
    if ( (_QWORD *)v36[0] == v36 )
      break;
    if ( *(_QWORD **)(v36[0] + 8LL) != v36 )
      goto LABEL_69;
    v24 = *(_QWORD *)v36[0];
    if ( *(_QWORD *)(*(_QWORD *)v36[0] + 8LL) != v36[0] )
      goto LABEL_69;
    v36[0] = *(_QWORD *)v36[0];
    v25 = v23 - 18;
    v26 = v36;
    *(_QWORD *)(v24 + 8) = v36;
    v23[1] = v23;
    *v23 = v23;
    if ( ((*((_DWORD *)v23 - 24) - 3) & 0xFFFFFFFD) != 0 || *((_DWORD *)v25 + 47) != 60 )
      SessionAckCommand(v25, 0, 3221225653LL);
    LOBYTE(v26) = 1;
    SessionDisconnectInd(v25, v26, 3221225653LL);
    RefObj_ReleaseEx(v25 + 3, 1129531716, 6541, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  while ( 1 )
  {
    v27 = v37[0];
    if ( (_QWORD *)v37[0] == v37 )
      break;
    if ( *(_QWORD **)(v37[0] + 8LL) != v37 )
      goto LABEL_69;
    v28 = *(_QWORD *)v37[0];
    if ( *(_QWORD *)(*(_QWORD *)v37[0] + 8LL) != v37[0] )
      goto LABEL_69;
    v37[0] = *(_QWORD *)v37[0];
    *(_QWORD *)(v28 + 8) = v37;
    v29 = v27 - 88;
    *(_QWORD *)(v27 + 8) = v27;
    *(_QWORD *)v27 = v27;
    if ( *(_DWORD *)(v27 + 56) )
    {
      v32 = *(_QWORD *)(v27 - 32);
      v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v32 + 56));
      *(_BYTE *)(v32 + 64) = v33;
      v34 = *(_DWORD *)(v29 + 48) - 4;
      if ( (v34 & 0xFFFFFFFD) != 0 )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(v32 + 56), v33);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v34,
            3,
            185,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
        v35 = 5;
        if ( *(_DWORD *)(v29 + 48) != 4 )
          v35 = 7;
        ChannelSetState(v29, v35);
        KeReleaseSpinLock((PKSPIN_LOCK)(v32 + 56), *(_BYTE *)(v32 + 64));
        ChannelSendData(v29);
      }
      v30 = 1111705667;
      v31 = 6592;
    }
    else
    {
      ChannelAckCommand(v27 - 88, 0, 3221225653LL);
      ChannelDisconnectInd(v29, 2, 3221225653LL);
      v30 = 1129531716;
      v31 = 6564;
    }
    RefObj_ReleaseEx(v29 + 24, v30, v31, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  *((_BYTE *)p_DpcData + 129) = 0;
}

```

## disassembly

```asm
0x140014210  push    rbp
0x140014212  push    rbx
0x140014213  push    rsi
0x140014214  push    rdi
0x140014215  push    r12
0x140014217  push    r13
0x140014219  push    r14
0x14001421b  push    r15
0x14001421d  mov     rbp, rsp
0x140014220  sub     rsp, 58h
0x140014224  lea     rax, [rbp+var_28]
0x140014228  mov     [rbp+var_20], rax
0x14001422c  lea     r14, [rcx-0C8h]
0x140014233  lea     rax, [rbp+var_28]
0x140014237  mov     [rbp+var_28], rax
0x14001423b  lea     rax, [rbp+var_18]
0x14001423f  mov     [rbp+var_10], rax
0x140014243  lea     rax, [rbp+var_18]
0x140014247  mov     [rbp+var_18], rax
0x14001424b  lea     r12, WPP_RECORDER_INITIALIZED
0x140014252  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140014259  lea     rdi, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140014260  jz      short loc_140014283
0x140014262  mov     rcx, cs:WPP_GLOBAL_Control
0x140014269  mov     r9d, 0B3h
0x14001426f  mov     r8d, 3
0x140014275  mov     [rsp+58h+var_38], rdi
0x14001427a  mov     rcx, [rcx+40h]
0x14001427e  call    WPP_RECORDER_SF_
0x140014283  lea     r15, [r14+18h]
0x140014287  mov     rcx, r15; SpinLock
0x14001428a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014291  nop     dword ptr [rax+rax+00h]
0x140014296  cmp     byte ptr [r14+81h], 0
0x14001429e  mov     [r14+20h], al
0x1400142a2  jz      short loc_1400142BA
0x1400142a4  mov     dl, al; NewIrql
0x1400142a6  mov     rcx, r15; SpinLock
0x1400142a9  call    cs:__imp_KeReleaseSpinLock
0x1400142b0  nop     dword ptr [rax+rax+00h]
0x1400142b5  jmp     loc_140014786
0x1400142ba  mov     sil, 1
0x1400142bd  lea     r13, [r14+120h]
0x1400142c4  mov     rbx, [r13+0]
0x1400142c8  mov     [r14+81h], sil
0x1400142cf  jmp     loc_140014579
0x1400142d4  or      ecx, 0FFFFFFFFh
0x1400142d7  lock xadd [rbx+0B8h], ecx
0x1400142df  sub     ecx, 1
0x1400142e2  jnz     short loc_140014358
0x1400142e4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400142eb  jz      short loc_14001430C
0x1400142ed  lea     r8d, [rcx+3]
0x1400142f1  mov     [rsp+58h+var_38], rdi
0x1400142f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400142fd  mov     r9d, 0B4h
0x140014303  mov     rcx, [rcx+40h]
0x140014307  call    WPP_RECORDER_SF_
0x14001430c  lea     rcx, [rbx+18h]
0x140014310  mov     edx, 43534944h
0x140014315  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001431c  mov     r8d, 18EDh
0x140014322  call    RefObj_AddRefEx
0x140014327  mov     rcx, [rbp+var_28]
0x14001432b  lea     rax, [rbp+var_28]
0x14001432f  cmp     [rcx+8], rax
0x140014333  jnz     loc_140014777
0x140014339  lea     rax, [rbx+90h]
0x140014340  mov     [rax], rcx
0x140014343  lea     rdx, [rbp+var_28]
0x140014347  mov     [rax+8], rdx
0x14001434b  mov     [rcx+8], rax
0x14001434f  mov     [rbp+var_28], rax
0x140014353  jmp     loc_140014576
0x140014358  xor     eax, eax
0x14001435a  movzx   esi, sil
0x14001435e  test    ecx, ecx
0x140014360  lea     rcx, [rbx+38h]; SpinLock
0x140014364  cmovg   esi, eax
0x140014367  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001436e  nop     dword ptr [rax+rax+00h]
0x140014373  lea     r12, [rbx+50h]
0x140014377  mov     [rbx+40h], al
0x14001437a  mov     rdi, [r12]
0x14001437e  jmp     loc_140014478
0x140014383  or      edx, 0FFFFFFFFh
0x140014386  lock xadd [rdi+90h], edx
0x14001438e  sub     edx, 1
0x140014391  jnz     short loc_1400143D6
0x140014393  lea     rax, WPP_RECORDER_INITIALIZED
0x14001439a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400143a1  jz      short loc_1400143C9
0x1400143a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400143aa  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400143b1  mov     r9d, 0B5h
0x1400143b7  mov     [rsp+58h+var_38], rax
0x1400143bc  lea     r8d, [rdx+3]
0x1400143c0  mov     rcx, [rcx+40h]
0x1400143c4  call    WPP_RECORDER_SF_
0x1400143c9  mov     edx, 43534944h
0x1400143ce  mov     r8d, 1910h
0x1400143d4  jmp     short loc_140014435
0x1400143d6  xor     eax, eax
0x1400143d8  movzx   ecx, sil
0x1400143dc  test    edx, edx
0x1400143de  cmovg   ecx, eax
0x1400143e1  or      edx, 0FFFFFFFFh
0x1400143e4  movzx   esi, cl
0x1400143e7  lock xadd [rdi+94h], edx
0x1400143ef  sub     edx, 1
0x1400143f2  jnz     short loc_140014470
0x1400143f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400143fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014402  jz      short loc_14001442A
0x140014404  mov     rcx, cs:WPP_GLOBAL_Control
0x14001440b  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140014412  mov     r9d, 0B6h
0x140014418  mov     [rsp+58h+var_38], rax
0x14001441d  lea     r8d, [rdx+3]
0x140014421  mov     rcx, [rcx+40h]
0x140014425  call    WPP_RECORDER_SF_
0x14001442a  mov     edx, 42434843h
0x14001442f  mov     r8d, 1926h
0x140014435  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001443c  lea     rcx, [rdi+18h]
0x140014440  call    RefObj_AddRefEx
0x140014445  mov     rcx, [rbp+var_18]
0x140014449  lea     rax, [rbp+var_18]
0x14001444d  cmp     [rcx+8], rax
0x140014451  jnz     loc_140014777
0x140014457  lea     rax, [rdi+58h]
0x14001445b  mov     [rax], rcx
0x14001445e  lea     rdx, [rbp+var_18]
0x140014462  mov     [rax+8], rdx
0x140014466  mov     [rcx+8], rax
0x14001446a  mov     [rbp+var_18], rax
0x14001446e  jmp     short loc_140014475
0x140014470  test    edx, edx
0x140014472  cmovg   esi, eax
0x140014475  mov     rdi, [rdi]
0x140014478  cmp     rdi, r12
0x14001447b  jnz     loc_140014383
0x140014481  mov     r8d, [rbx+0BCh]
0x140014488  mov     edx, [rbx+30h]
0x14001448b  lea     ecx, [r8+1]
0x14001448f  lea     eax, [rdx-3]
0x140014492  mov     [rbx+0BCh], ecx
0x140014498  test    eax, 0FFFFFFFDh
0x14001449d  jnz     loc_140014555
0x1400144a3  cmp     ecx, 3Ch ; '<'
0x1400144a6  jnz     loc_140014548
0x1400144ac  cmp     edx, 5
0x1400144af  jnz     short loc_1400144C7
0x1400144b1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400144b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400144bf  jz      short loc_1400144FF
0x1400144c1  lea     r9d, [rcx+7Bh]
0x1400144c5  jmp     short loc_1400144DD
0x1400144c7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400144ce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400144d5  jz      short loc_1400144FF
0x1400144d7  mov     r9d, 0B8h
0x1400144dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400144e4  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400144eb  mov     r8d, 3
0x1400144f1  mov     [rsp+58h+var_38], rax
0x1400144f6  mov     rcx, [rcx+40h]
0x1400144fa  call    WPP_RECORDER_SF_
0x1400144ff  lea     rcx, [rbx+18h]
0x140014503  mov     edx, 43534944h
0x140014508  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001450f  mov     r8d, 195Bh
0x140014515  call    RefObj_AddRefEx
0x14001451a  mov     rcx, [rbp+var_28]
0x14001451e  lea     rax, [rbp+var_28]
0x140014522  cmp     [rcx+8], rax
0x140014526  jnz     loc_140014777
0x14001452c  lea     rax, [rbx+90h]
0x140014533  mov     [rax], rcx
0x140014536  lea     rdx, [rbp+var_28]
0x14001453a  mov     [rax+8], rdx
0x14001453e  mov     [rcx+8], rax
0x140014542  mov     [rbp+var_28], rax
0x140014546  jmp     short loc_140014555
0x140014548  xor     eax, eax
0x14001454a  movzx   esi, sil
0x14001454e  cmp     r8d, 3Ah ; ':'
0x140014552  cmovbe  esi, eax
0x140014555  mov     dl, [rbx+40h]; NewIrql
0x140014558  lea     rcx, [rbx+38h]; SpinLock
0x14001455c  call    cs:__imp_KeReleaseSpinLock
0x140014563  nop     dword ptr [rax+rax+00h]
0x140014568  lea     r12, WPP_RECORDER_INITIALIZED
0x14001456f  lea     rdi, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140014576  mov     rbx, [rbx]
0x140014579  cmp     rbx, r13
0x14001457c  jnz     loc_1400142D4
0x140014582  test    sil, sil
0x140014585  jz      short loc_14001458F
0x140014587  mov     rcx, r14
0x14001458a  call    RfcommStopTimerLocked
0x14001458f  mov     dl, [r14+20h]; NewIrql
0x140014593  mov     rcx, r15; SpinLock
0x140014596  call    cs:__imp_KeReleaseSpinLock
0x14001459d  nop     dword ptr [rax+rax+00h]
0x1400145a2  mov     r15d, 0C00000B5h
0x1400145a8  mov     r13d, 0FFFFFFFDh
0x1400145ae  mov     rax, [rbp+var_28]
0x1400145b2  lea     rcx, [rbp+var_28]
0x1400145b6  cmp     rax, rcx
0x1400145b9  jz      loc_140014646
0x1400145bf  lea     rcx, [rbp+var_28]
0x1400145c3  cmp     [rax+8], rcx
0x1400145c7  jnz     loc_140014777
0x1400145cd  mov     rcx, [rax]
0x1400145d0  cmp     [rcx+8], rax
0x1400145d4  jnz     loc_140014777
0x1400145da  mov     [rbp+var_28], rcx
0x1400145de  lea     rbx, [rax-90h]
0x1400145e5  lea     rdx, [rbp+var_28]
0x1400145e9  mov     [rcx+8], rdx
0x1400145ed  mov     [rax+8], rax
0x1400145f1  mov     [rax], rax
0x1400145f4  mov     eax, [rbx+30h]
0x1400145f7  sub     eax, 3
0x1400145fa  test    r13d, eax
0x1400145fd  jnz     short loc_140014608
0x1400145ff  cmp     dword ptr [rbx+0BCh], 3Ch ; '<'
0x140014606  jz      short loc_140014615
0x140014608  mov     r8d, r15d
0x14001460b  xor     edx, edx
0x14001460d  mov     rcx, rbx
0x140014610  call    SessionAckCommand
0x140014615  mov     r9b, 1
0x140014618  mov     r8d, r15d
0x14001461b  mov     dl, r9b
0x14001461e  mov     rcx, rbx
0x140014621  call    SessionDisconnectInd
0x140014626  lea     rcx, [rbx+18h]
0x14001462a  mov     edx, 43534944h
0x14001462f  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140014636  mov     r8d, 198Dh
0x14001463c  call    RefObj_ReleaseEx
0x140014641  jmp     loc_1400145AE
0x140014646  mov     rax, [rbp+var_18]
0x14001464a  lea     rcx, [rbp+var_18]
0x14001464e  cmp     rax, rcx
0x140014651  jz      loc_14001477E
0x140014657  lea     rcx, [rbp+var_18]
0x14001465b  cmp     [rax+8], rcx
0x14001465f  jnz     loc_140014777
0x140014665  mov     rcx, [rax]
0x140014668  cmp     [rcx+8], rax
0x14001466c  jnz     loc_140014777
0x140014672  mov     [rbp+var_18], rcx
0x140014676  lea     rdx, [rbp+var_18]
0x14001467a  mov     [rcx+8], rdx
0x14001467e  lea     rbx, [rax-58h]
0x140014682  mov     [rax+8], rax
0x140014686  mov     [rax], rax
0x140014689  cmp     dword ptr [rax+38h], 0
0x14001468d  jnz     short loc_1400146BC
0x14001468f  mov     r8d, r15d
0x140014692  xor     edx, edx
0x140014694  mov     rcx, rbx
0x140014697  call    ChannelAckCommand
0x14001469c  mov     r8d, r15d
0x14001469f  mov     edx, 2
0x1400146a4  mov     rcx, rbx
0x1400146a7  call    ChannelDisconnectInd
0x1400146ac  mov     edx, 43534944h
0x1400146b1  mov     r8d, 19A4h
0x1400146b7  jmp     loc_140014762
0x1400146bc  mov     rsi, [rax-20h]
0x1400146c0  lea     rdi, [rsi+38h]
0x1400146c4  mov     rcx, rdi; SpinLock
0x1400146c7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400146ce  nop     dword ptr [rax+rax+00h]
0x1400146d3  mov     [rsi+40h], al
0x1400146d6  mov     edx, [rbx+30h]
0x1400146d9  sub     edx, 4
0x1400146dc  test    r13d, edx
0x1400146df  jz      short loc_1400146F4
0x1400146e1  mov     dl, al; NewIrql
0x1400146e3  mov     rcx, rdi; SpinLock
0x1400146e6  call    cs:__imp_KeReleaseSpinLock
0x1400146ed  nop     dword ptr [rax+rax+00h]
0x1400146f2  jmp     short loc_140014757
0x1400146f4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400146fb  jz      short loc_140014725
0x1400146fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140014704  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001470b  mov     r9d, 0B9h
0x140014711  mov     [rsp+58h+var_38], rax
0x140014716  mov     r8d, 3
0x14001471c  mov     rcx, [rcx+40h]
0x140014720  call    WPP_RECORDER_SF_
0x140014725  cmp     dword ptr [rbx+30h], 4
0x140014729  mov     rcx, rbx
0x14001472c  mov     edx, 5
  ... truncated ...
```
