# ChannelDisconnect

- ea: `0x1400197ec`
- end: `0x140019b5c`
- name: `ChannelDisconnect`
- size: `880`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019b64`
- `0x140019cd0`

## callees

- `0x140003bf4`
- `0x140005050`
- `0x1400105ec`
- `0x140010688`
- `0x1400133b0`
- `0x1400197ec`
- `0x14001a12c`
- `0x14001a164`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019866`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019aee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019866`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019aee`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019a2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019b16`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019a2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019b16`

## string_xrefs

- `0x140019918`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x140019a67`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x140019ab9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x140019ad9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`

## pseudocode

```c
__int64 __fastcall ChannelDisconnect(__int64 a1, unsigned int a2, char a3)
{
  __int64 v3; // rsi
  __int64 *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rdi
  _QWORD *v14; // r8
  _QWORD *v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int128 v31; // [rsp+40h] [rbp-10h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v31 = 0;
  v7 = WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = ChannelStateTxt(*(unsigned int *)(a1 + 48), WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids);
    WPP_RECORDER_SF_qs(WPP_GLOBAL_Control->DeviceExtension, v9, 3, 28, v9, a1, v8);
  }
  if ( !a3 )
    *(_BYTE *)(v3 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 56));
  if ( *(_DWORD *)(a1 + 48) == 9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = ChannelStateTxt(9, v7);
      WPP_RECORDER_SF_qs(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        3,
        29,
        (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
        a1,
        v10);
    }
    goto LABEL_42;
  }
  v12 = ChannelReferenceConnLocked(a1, 1312901187);
  v13 = v12;
  if ( v12 )
  {
    v14 = (_QWORD *)(a1 + 72);
    v15 = *(_QWORD **)(a1 + 72);
    if ( v15 == (_QWORD *)(v12 + 280) )
    {
      if ( (_QWORD *)v15[1] != v14 )
        goto LABEL_36;
      v16 = *v15;
      if ( *(_QWORD **)(*v15 + 8LL) != v15 )
        goto LABEL_36;
      *v14 = v16;
      *(_QWORD *)(v16 + 8) = v14;
      v15[1] = v15;
      *v15 = v15;
      RefObj_ReleaseEx(v13 + 24, 1313754947, 790, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
    }
  }
  v17 = ~(1 << (*(_BYTE *)(a1 + 184) >> 1));
  if ( *(_BYTE *)(a1 + 185) )
    *(_DWORD *)(v3 + 256) &= v17;
  else
    *(_DWORD *)(v3 + 260) &= v17;
  v18 = *(_DWORD *)(a1 + 48);
  if ( !v18 )
    goto LABEL_27;
  v19 = v18 - 1;
  if ( !v19 )
    goto LABEL_27;
  v20 = v19 - 1;
  if ( !v20 )
    goto LABEL_27;
  v21 = v20 - 1;
  if ( !v21 || (v22 = v21 - 1) == 0 || (v23 = v22 - 1) == 0 || (v24 = v23 - 1) == 0 || (v25 = v24 - 1) == 0 )
  {
    ChannelSetState(a1, 8);
    goto LABEL_27;
  }
  if ( v25 == 1 )
LABEL_27:
    ChannelSetState(a1, 9);
  *((_QWORD *)&v31 + 1) = &v31;
  *(_QWORD *)&v31 = &v31;
  ListDrainLocked(&v31, a1 + 104);
  ListDrainLocked(&v31, a1 + 152);
  ListDrainLocked(&v31, a1 + 168);
  v26 = *(_QWORD **)(a1 + 136);
  *(_QWORD *)(a1 + 136) = 0;
  if ( !v26 )
    goto LABEL_31;
  v27 = (_QWORD *)*((_QWORD *)&v31 + 1);
  if ( **((__int128 ***)&v31 + 1) != &v31 )
LABEL_36:
    __fastfail(3u);
  v26[1] = *((_QWORD *)&v31 + 1);
  *v26 = &v31;
  *v27 = v26;
  *((_QWORD *)&v31 + 1) = v26;
  _InterlockedExchange((volatile __int32 *)(a1 + 144), 0);
LABEL_31:
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 56), *(_BYTE *)(v3 + 64));
  while ( 1 )
  {
    v28 = v31;
    if ( (__int128 *)v31 == &v31 )
      break;
    if ( *(__int128 **)(v31 + 8) != &v31 )
      goto LABEL_36;
    v29 = *(_QWORD *)v31;
    if ( *(_QWORD *)(*(_QWORD *)v31 + 8LL) != (_QWORD)v31 )
      goto LABEL_36;
    *(_QWORD *)&v31 = *(_QWORD *)v31;
    *(_QWORD *)(v29 + 8) = &v31;
    *(_QWORD *)(v28 + 8) = v28;
    *(_QWORD *)v28 = v28;
    *(_DWORD *)(v28 + 104) = a2;
    *(_DWORD *)(v28 + 60) = 0;
    RefObj_ReleaseEx(v28 + 24, 541803329, 893, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  }
  if ( v13 )
    ChannelUnpairConn(a1, v13, a2);
  RefObj_ReleaseEx(a1 + 24, 1414090313, 901, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  if ( v13 )
    RefObj_ReleaseEx(v13 + 24, 1312901187, 904, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  *(_BYTE *)(v3 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 56));
LABEL_42:
  if ( !a3 )
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 56), *(_BYTE *)(v3 + 64));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v7,
      3,
      30,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400197ec  push    rbp
0x1400197ee  push    rbx
0x1400197ef  push    rsi
0x1400197f0  push    rdi
0x1400197f1  push    r12
0x1400197f3  push    r14
0x1400197f5  push    r15
0x1400197f7  mov     rbp, rsp
0x1400197fa  sub     rsp, 50h
0x1400197fe  mov     rsi, [rcx+38h]
0x140019802  xorps   xmm0, xmm0
0x140019805  movups  [rbp+var_10], xmm0
0x140019809  mov     r15b, r8b
0x14001980c  mov     r12d, edx
0x14001980f  mov     rbx, rcx
0x140019812  lea     rax, WPP_RECORDER_INITIALIZED
0x140019819  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019820  lea     rdx, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019827  jz      short loc_14001985A
0x140019829  mov     ecx, [rcx+30h]
0x14001982c  call    ChannelStateTxt
0x140019831  mov     rcx, cs:WPP_GLOBAL_Control
0x140019838  mov     r9d, 1Ch
0x14001983e  mov     [rsp+50h+var_20], rax
0x140019843  mov     [rsp+50h+var_28], rbx
0x140019848  mov     [rsp+50h+var_30], rdx
0x14001984d  mov     rcx, [rcx+40h]
0x140019851  lea     r8d, [r9-19h]
0x140019855  call    WPP_RECORDER_SF_qs
0x14001985a  lea     r14, [rsi+38h]
0x14001985e  test    r15b, r15b
0x140019861  jnz     short loc_140019875
0x140019863  mov     rcx, r14; SpinLock
0x140019866  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001986d  nop     dword ptr [rax+rax+00h]
0x140019872  mov     [rsi+40h], al
0x140019875  cmp     dword ptr [rbx+30h], 9
0x140019879  jnz     short loc_1400198CE
0x14001987b  lea     rdi, WPP_RECORDER_INITIALIZED
0x140019882  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140019889  jz      loc_140019B04
0x14001988f  mov     ecx, 9
0x140019894  call    ChannelStateTxt
0x140019899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400198a0  mov     r9d, 1Dh
0x1400198a6  mov     [rsp+50h+var_20], rax
0x1400198ab  mov     [rsp+50h+var_28], rbx
0x1400198b0  lea     rbx, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x1400198b7  mov     [rsp+50h+var_30], rbx
0x1400198bc  mov     rcx, [rcx+40h]
0x1400198c0  lea     r8d, [r9-1Ah]
0x1400198c4  call    WPP_RECORDER_SF_qs
0x1400198c9  jmp     loc_140019B0B
0x1400198ce  mov     edx, 4E414843h
0x1400198d3  mov     rcx, rbx
0x1400198d6  call    ChannelReferenceConnLocked
0x1400198db  mov     rdi, rax
0x1400198de  test    rax, rax
0x1400198e1  jz      short loc_140019936
0x1400198e3  lea     r8, [rbx+48h]
0x1400198e7  mov     rdx, [r8]
0x1400198ea  lea     rcx, [rax+118h]
0x1400198f1  cmp     rdx, rcx
0x1400198f4  jnz     short loc_140019936
0x1400198f6  cmp     [rdx+8], r8
0x1400198fa  jnz     loc_140019A96
0x140019900  mov     rax, [rdx]
0x140019903  cmp     [rax+8], rdx
0x140019907  jnz     loc_140019A96
0x14001990d  mov     [r8], rax
0x140019910  lea     rcx, [rdi+18h]
0x140019914  mov     [rax+8], r8
0x140019918  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001991f  mov     [rdx+8], rdx
0x140019923  mov     r8d, 316h
0x140019929  mov     [rdx], rdx
0x14001992c  mov     edx, 4E4E4F43h
0x140019931  call    RefObj_ReleaseEx
0x140019936  movzx   ecx, byte ptr [rbx+0B8h]
0x14001993d  mov     eax, 1
0x140019942  shr     ecx, 1
0x140019944  shl     eax, cl
0x140019946  cmp     byte ptr [rbx+0B9h], 0
0x14001994d  not     eax
0x14001994f  jz      short loc_140019959
0x140019951  and     [rsi+100h], eax
0x140019957  jmp     short loc_14001995F
0x140019959  and     [rsi+104h], eax
0x14001995f  mov     ecx, [rbx+30h]
0x140019962  test    ecx, ecx
0x140019964  jz      short loc_14001999D
0x140019966  sub     ecx, 1
0x140019969  jz      short loc_14001999D
0x14001996b  sub     ecx, 1
0x14001996e  jz      short loc_14001999D
0x140019970  sub     ecx, 1
0x140019973  jz      short loc_140019990
0x140019975  sub     ecx, 1
0x140019978  jz      short loc_140019990
0x14001997a  sub     ecx, 1
0x14001997d  jz      short loc_140019990
0x14001997f  sub     ecx, 1
0x140019982  jz      short loc_140019990
0x140019984  sub     ecx, 1
0x140019987  jz      short loc_140019990
0x140019989  cmp     ecx, 1
0x14001998c  jz      short loc_14001999D
0x14001998e  jmp     short loc_1400199AA
0x140019990  mov     edx, 8
0x140019995  mov     rcx, rbx
0x140019998  call    ChannelSetState
0x14001999d  mov     edx, 9
0x1400199a2  mov     rcx, rbx
0x1400199a5  call    ChannelSetState
0x1400199aa  lea     rax, [rbp+var_10]
0x1400199ae  mov     qword ptr [rbp+var_10+8], rax
0x1400199b2  lea     rdx, [rbx+68h]
0x1400199b6  lea     rax, [rbp+var_10]
0x1400199ba  lea     rcx, [rbp+var_10]
0x1400199be  mov     qword ptr [rbp+var_10], rax
0x1400199c2  call    ListDrainLocked
0x1400199c7  lea     rcx, [rbp+var_10]
0x1400199cb  lea     rdx, [rbx+98h]
0x1400199d2  call    ListDrainLocked
0x1400199d7  lea     rcx, [rbp+var_10]
0x1400199db  lea     rdx, [rbx+0A8h]
0x1400199e2  call    ListDrainLocked
0x1400199e7  mov     rax, [rbx+88h]
0x1400199ee  mov     qword ptr [rbx+88h], 0
0x1400199f9  test    rax, rax
0x1400199fc  jz      short loc_140019A29
0x1400199fe  mov     rcx, qword ptr [rbp+var_10+8]
0x140019a02  lea     rdx, [rbp+var_10]
0x140019a06  cmp     [rcx], rdx
0x140019a09  jnz     loc_140019A96
0x140019a0f  mov     [rax+8], rcx
0x140019a13  lea     rdx, [rbp+var_10]
0x140019a17  mov     [rax], rdx
0x140019a1a  mov     [rcx], rax
0x140019a1d  mov     qword ptr [rbp+var_10+8], rax
0x140019a21  xor     eax, eax
0x140019a23  xchg    eax, [rbx+90h]
0x140019a29  mov     dl, [rsi+40h]; NewIrql
0x140019a2c  mov     rcx, r14; SpinLock
0x140019a2f  call    cs:__imp_KeReleaseSpinLock
0x140019a36  nop     dword ptr [rax+rax+00h]
0x140019a3b  mov     rcx, qword ptr [rbp+var_10]
0x140019a3f  lea     rax, [rbp+var_10]
0x140019a43  cmp     rcx, rax
0x140019a46  jz      short loc_140019A9D
0x140019a48  lea     rax, [rbp+var_10]
0x140019a4c  cmp     [rcx+8], rax
0x140019a50  jnz     short loc_140019A96
0x140019a52  mov     rax, [rcx]
0x140019a55  cmp     [rax+8], rcx
0x140019a59  jnz     short loc_140019A96
0x140019a5b  mov     qword ptr [rbp+var_10], rax
0x140019a5f  lea     rdx, [rbp+var_10]
0x140019a63  mov     [rax+8], rdx
0x140019a67  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140019a6e  mov     [rcx+8], rcx
0x140019a72  mov     edx, 204B4341h
0x140019a77  mov     [rcx], rcx
0x140019a7a  mov     r8d, 37Dh
0x140019a80  mov     [rcx+68h], r12d
0x140019a84  mov     dword ptr [rcx+3Ch], 0
0x140019a8b  add     rcx, 18h
0x140019a8f  call    RefObj_ReleaseEx
0x140019a94  jmp     short loc_140019A3B
0x140019a96  mov     ecx, 3
0x140019a9b  int     29h; Win8: RtlFailFast(ecx)
0x140019a9d  test    rdi, rdi
0x140019aa0  jz      short loc_140019AB0
0x140019aa2  mov     r8d, r12d
0x140019aa5  mov     rdx, rdi
0x140019aa8  mov     rcx, rbx
0x140019aab  call    ChannelUnpairConn
0x140019ab0  lea     rcx, [rbx+18h]
0x140019ab4  mov     edx, 54494E49h
0x140019ab9  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140019ac0  mov     r8d, 385h
0x140019ac6  call    RefObj_ReleaseEx
0x140019acb  test    rdi, rdi
0x140019ace  jz      short loc_140019AEB
0x140019ad0  lea     rcx, [rdi+18h]
0x140019ad4  mov     edx, 4E414843h
0x140019ad9  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140019ae0  mov     r8d, 388h
0x140019ae6  call    RefObj_ReleaseEx
0x140019aeb  mov     rcx, r14; SpinLock
0x140019aee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019af5  nop     dword ptr [rax+rax+00h]
0x140019afa  mov     [rsi+40h], al
0x140019afd  lea     rdi, WPP_RECORDER_INITIALIZED
0x140019b04  lea     rbx, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140019b0b  test    r15b, r15b
0x140019b0e  jnz     short loc_140019B22
0x140019b10  mov     dl, [rsi+40h]; NewIrql
0x140019b13  mov     rcx, r14; SpinLock
0x140019b16  call    cs:__imp_KeReleaseSpinLock
0x140019b1d  nop     dword ptr [rax+rax+00h]
0x140019b22  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140019b29  jz      short loc_140019B4A
0x140019b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b32  mov     r9d, 1Eh
0x140019b38  mov     [rsp+50h+var_30], rbx
0x140019b3d  mov     rcx, [rcx+40h]
0x140019b41  lea     r8d, [r9-1Bh]
0x140019b45  call    WPP_RECORDER_SF_
0x140019b4a  xor     eax, eax
0x140019b4c  add     rsp, 50h
0x140019b50  pop     r15
0x140019b52  pop     r14
0x140019b54  pop     r12
0x140019b56  pop     rdi
0x140019b57  pop     rsi
0x140019b58  pop     rbx
0x140019b59  pop     rbp
0x140019b5a  retn
```
