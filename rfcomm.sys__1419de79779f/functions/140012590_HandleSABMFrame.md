# HandleSABMFrame

- ea: `0x140012590`
- end: `0x140012913`
- name: `HandleSABMFrame`
- size: `899`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140005f2c`
- `0x140012590`
- `0x1400133b0`
- `0x140014b10`
- `0x140015688`
- `0x1400157dc`
- `0x140018e9c`
- `0x1400195d0`
- `0x140019b64`
- `0x140019e5c`
- `0x14001a164`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012600`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400126ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012600`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400126ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012646`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400126d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400127cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012827`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400128f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012646`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400126d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400127cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012827`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400128f9`

## string_xrefs

- `0x1400126b8`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x1400127a8`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140012860`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall HandleSABMFrame(__int64 a1, _BYTE *a2)
{
  KSPIN_LOCK *v4; // rcx
  KIRQL v5; // al
  bool v6; // zf
  KIRQL v7; // dl
  int v8; // edx
  _QWORD *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdx
  KIRQL v12; // al
  __int64 v13; // rdx
  __int64 v14; // r8
  char v15; // bp
  __int64 Locked; // rdi
  _QWORD *v17; // r8
  __int64 v18; // r14
  __int64 v19; // rdx
  _QWORD v21[9]; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      148,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  v4 = (KSPIN_LOCK *)(a1 + 56);
  if ( *a2 >= 4u )
  {
    v12 = KeAcquireSpinLockRaiseToDpc(v4);
    v6 = *(_DWORD *)(a1 + 48) == 4;
    *(_BYTE *)(a1 + 64) = v12;
    if ( !v6 || (v13 = (unsigned __int8)*a2, (*a2 & 4) != (*(_BYTE *)(a1 + 272) != 0 ? 4 : 0)) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          11,
          150,
          (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
          *a2 >> 3);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
      LOBYTE(v11) = *a2 >> 2;
      goto LABEL_14;
    }
    v15 = 1;
    LOBYTE(v13) = (unsigned __int8)v13 >> 2;
    LOBYTE(v14) = 1;
    Locked = ChannelFindLocked(a1, v13, v14);
    if ( Locked || (v15 = 0, (Locked = ChannelCreateLocked(a1, (unsigned __int8)*a2 >> 3, 0)) != 0) )
    {
      if ( *(_DWORD *)(Locked + 48) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v8,
            11,
            149,
            (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
            *a2 >> 3);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
        LOBYTE(v19) = *a2 >> 2;
        RfcommSendDMEx(a1, v19, 0);
        ChannelDisconnectInd(Locked, 2, 3221225667LL);
        v18 = Locked + 24;
      }
      else
      {
        ChannelSetState(Locked, 3);
        if ( !v15 )
          *(_DWORD *)(Locked + 228) = 1;
        v17 = *(_QWORD **)(a1 + 120);
        if ( *v17 != a1 + 112 )
LABEL_23:
          __fastfail(3u);
        *(_QWORD *)(Locked + 240) = a1 + 112;
        v18 = Locked + 24;
        *(_QWORD *)(Locked + 248) = v17;
        *v17 = Locked + 240;
        *(_QWORD *)(a1 + 120) = Locked + 240;
        RefObj_AddRefEx(
          Locked + 24,
          1414546241,
          4971,
          "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
        TdiAccept(Locked);
      }
      if ( v15 )
        RefObj_ReleaseEx(v18, 1145981254, 5002, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
  }
  else
  {
    v21[1] = v21;
    v21[0] = v21;
    v5 = KeAcquireSpinLockRaiseToDpc(v4);
    v6 = *(_DWORD *)(a1 + 48) == 3;
    *(_BYTE *)(a1 + 64) = v5;
    if ( !v6 )
    {
      v7 = v5;
      goto LABEL_13;
    }
    if ( !(unsigned __int8)RfcommSetState(a1, 4) )
    {
      v7 = *(_BYTE *)(a1 + 64);
LABEL_13:
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v7);
      v11 = 0;
LABEL_14:
      RfcommSendDMEx(a1, v11, 0);
      goto LABEL_30;
    }
    ListDrainLocked(v21, a1 + 96);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    RfcommSendUA(a1, 0);
    while ( 1 )
    {
      v9 = (_QWORD *)v21[0];
      if ( (_QWORD *)v21[0] == v21 )
        break;
      if ( *(_QWORD **)(v21[0] + 8LL) != v21 )
        goto LABEL_23;
      v10 = *(_QWORD *)v21[0];
      if ( *(_QWORD *)(*(_QWORD *)v21[0] + 8LL) != v21[0] )
        goto LABEL_23;
      v21[0] = *(_QWORD *)v21[0];
      *(_QWORD *)(v10 + 8) = v21;
      v9[1] = v9;
      *v9 = v9;
      ChannelConnect(v9 - 35);
      RefObj_ReleaseEx(v9 - 32, 1313754947, 4924, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
  }
LABEL_30:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3,
      151,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return 4;
}

```

## disassembly

```asm
0x140012590  push    rbx
0x140012592  push    rbp
0x140012593  push    rsi
0x140012594  push    rdi
0x140012595  push    r13
0x140012597  push    r14
0x140012599  sub     rsp, 48h
0x14001259d  mov     r14, rdx
0x1400125a0  mov     rbx, rcx
0x1400125a3  lea     r13, WPP_RECORDER_INITIALIZED
0x1400125aa  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400125b1  lea     rdi, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400125b8  jz      short loc_1400125DB
0x1400125ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125c1  mov     r9d, 94h
0x1400125c7  mov     r8d, 3
0x1400125cd  mov     [rsp+78h+var_58], rdi
0x1400125d2  mov     rcx, [rcx+40h]
0x1400125d6  call    WPP_RECORDER_SF_
0x1400125db  cmp     byte ptr [r14], 4
0x1400125df  lea     rsi, [rbx+38h]
0x1400125e3  mov     rcx, rsi; SpinLock
0x1400125e6  jnb     loc_1400126EF
0x1400125ec  lea     rax, [rsp+78h+var_48]
0x1400125f1  mov     [rsp+78h+var_40], rax
0x1400125f6  lea     rax, [rsp+78h+var_48]
0x1400125fb  mov     [rsp+78h+var_48], rax
0x140012600  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012607  nop     dword ptr [rax+rax+00h]
0x14001260c  cmp     dword ptr [rbx+30h], 3
0x140012610  mov     [rbx+40h], al
0x140012613  jnz     loc_1400126CC
0x140012619  mov     edx, 4
0x14001261e  mov     rcx, rbx
0x140012621  call    RfcommSetState
0x140012626  test    al, al
0x140012628  jnz     short loc_140012632
0x14001262a  mov     dl, [rbx+40h]
0x14001262d  jmp     loc_1400126CE
0x140012632  lea     rdx, [rbx+60h]
0x140012636  lea     rcx, [rsp+78h+var_48]
0x14001263b  call    ListDrainLocked
0x140012640  mov     dl, [rbx+40h]; NewIrql
0x140012643  mov     rcx, rsi; SpinLock
0x140012646  call    cs:__imp_KeReleaseSpinLock
0x14001264d  nop     dword ptr [rax+rax+00h]
0x140012652  xor     edx, edx
0x140012654  mov     rcx, rbx
0x140012657  call    RfcommSendUA
0x14001265c  mov     rbx, [rsp+78h+var_48]
0x140012661  lea     rax, [rsp+78h+var_48]
0x140012666  cmp     rbx, rax
0x140012669  jz      loc_140012881
0x14001266f  lea     rax, [rsp+78h+var_48]
0x140012674  cmp     [rbx+8], rax
0x140012678  jnz     loc_14001278F
0x14001267e  mov     rax, [rbx]
0x140012681  cmp     [rax+8], rbx
0x140012685  jnz     loc_14001278F
0x14001268b  mov     [rsp+78h+var_48], rax
0x140012690  lea     rcx, [rsp+78h+var_48]
0x140012695  mov     [rax+8], rcx
0x140012699  lea     rcx, [rbx-118h]
0x1400126a0  mov     [rbx+8], rbx
0x1400126a4  mov     [rbx], rbx
0x1400126a7  call    ChannelConnect
0x1400126ac  lea     rcx, [rbx-100h]
0x1400126b3  mov     edx, 4E4E4F43h
0x1400126b8  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400126bf  mov     r8d, 133Ch
0x1400126c5  call    RefObj_ReleaseEx
0x1400126ca  jmp     short loc_14001265C
0x1400126cc  mov     dl, al; NewIrql
0x1400126ce  mov     rcx, rsi; SpinLock
0x1400126d1  call    cs:__imp_KeReleaseSpinLock
0x1400126d8  nop     dword ptr [rax+rax+00h]
0x1400126dd  xor     r8d, r8d
0x1400126e0  xor     edx, edx
0x1400126e2  mov     rcx, rbx
0x1400126e5  call    RfcommSendDMEx
0x1400126ea  jmp     loc_140012881
0x1400126ef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400126f6  nop     dword ptr [rax+rax+00h]
0x1400126fb  cmp     dword ptr [rbx+30h], 4
0x1400126ff  mov     [rbx+40h], al
0x140012702  jnz     loc_1400128BE
0x140012708  mov     al, [rbx+110h]
0x14001270e  movzx   edx, byte ptr [r14]
0x140012712  neg     al
0x140012714  mov     eax, edx
0x140012716  sbb     ecx, ecx
0x140012718  and     eax, 4
0x14001271b  and     ecx, 4
0x14001271e  cmp     eax, ecx
0x140012720  jnz     loc_1400128BE
0x140012726  mov     bpl, 1
0x140012729  shr     dl, 2
0x14001272c  mov     r8b, bpl
0x14001272f  mov     rcx, rbx
0x140012732  call    ChannelFindLocked
0x140012737  mov     rdi, rax
0x14001273a  test    rax, rax
0x14001273d  jnz     short loc_140012760
0x14001273f  movzx   edx, byte ptr [r14]
0x140012743  xor     r8d, r8d
0x140012746  shr     edx, 3
0x140012749  mov     rcx, rbx
0x14001274c  xor     bpl, bpl
0x14001274f  call    ChannelCreateLocked
0x140012754  mov     rdi, rax
0x140012757  test    rax, rax
0x14001275a  jz      loc_14001287A
0x140012760  cmp     dword ptr [rdi+30h], 0
0x140012764  jnz     short loc_1400127E5
0x140012766  mov     edx, 3
0x14001276b  mov     rcx, rdi
0x14001276e  call    ChannelSetState
0x140012773  test    bpl, bpl
0x140012776  jnz     short loc_140012782
0x140012778  mov     dword ptr [rdi+0E4h], 1
0x140012782  lea     rdx, [rbx+70h]
0x140012786  mov     r8, [rdx+8]
0x14001278a  cmp     [r8], rdx
0x14001278d  jz      short loc_140012796
0x14001278f  mov     ecx, 3
0x140012794  int     29h; Win8: RtlFailFast(ecx)
0x140012796  lea     rax, [rdi+0F0h]
0x14001279d  mov     [rax], rdx
0x1400127a0  lea     r14, [rdi+18h]
0x1400127a4  mov     [rax+8], r8
0x1400127a8  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400127af  mov     [r8], rax
0x1400127b2  mov     rcx, r14
0x1400127b5  mov     [rdx+8], rax
0x1400127b9  mov     r8d, 136Bh
0x1400127bf  mov     edx, 54504341h
0x1400127c4  call    RefObj_AddRefEx
0x1400127c9  mov     dl, [rbx+40h]; NewIrql
0x1400127cc  mov     rcx, rsi; SpinLock
0x1400127cf  call    cs:__imp_KeReleaseSpinLock
0x1400127d6  nop     dword ptr [rax+rax+00h]
0x1400127db  mov     rcx, rdi
0x1400127de  call    TdiAccept
0x1400127e3  jmp     short loc_14001285B
0x1400127e5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400127ec  jz      short loc_140012821
0x1400127ee  movzx   eax, byte ptr [r14]
0x1400127f2  mov     r9d, 95h
0x1400127f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400127ff  mov     r8d, 0Bh
0x140012805  shr     eax, 3
0x140012808  mov     [rsp+78h+var_50], eax
0x14001280c  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012813  mov     [rsp+78h+var_58], rax
0x140012818  mov     rcx, [rcx+40h]
0x14001281c  call    WPP_RECORDER_SF_d
0x140012821  mov     dl, [rbx+40h]; NewIrql
0x140012824  mov     rcx, rsi; SpinLock
0x140012827  call    cs:__imp_KeReleaseSpinLock
0x14001282e  nop     dword ptr [rax+rax+00h]
0x140012833  mov     dl, [r14]
0x140012836  xor     r8d, r8d
0x140012839  shr     dl, 2
0x14001283c  mov     rcx, rbx
0x14001283f  call    RfcommSendDMEx
0x140012844  mov     edx, 2
0x140012849  mov     r8d, 0C00000C3h
0x14001284f  mov     rcx, rdi
0x140012852  call    ChannelDisconnectInd
0x140012857  lea     r14, [rdi+18h]
0x14001285b  test    bpl, bpl
0x14001285e  jz      short loc_14001287A
0x140012860  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140012867  mov     edx, 444E4946h
0x14001286c  mov     r8d, 138Ah
0x140012872  mov     rcx, r14
0x140012875  call    RefObj_ReleaseEx
0x14001287a  lea     rdi, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012881  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140012888  jz      short loc_1400128AB
0x14001288a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012891  mov     r9d, 97h
0x140012897  mov     r8d, 3
0x14001289d  mov     [rsp+78h+var_58], rdi
0x1400128a2  mov     rcx, [rcx+40h]
0x1400128a6  call    WPP_RECORDER_SF_
0x1400128ab  mov     eax, 4
0x1400128b0  add     rsp, 48h
0x1400128b4  pop     r14
0x1400128b6  pop     r13
0x1400128b8  pop     rdi
0x1400128b9  pop     rsi
0x1400128ba  pop     rbp
0x1400128bb  pop     rbx
0x1400128bc  retn
0x1400128be  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400128c5  jz      short loc_1400128F3
0x1400128c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128ce  mov     r9d, 96h
0x1400128d4  movzx   eax, byte ptr [r14]
0x1400128d8  mov     r8d, 0Bh
0x1400128de  shr     eax, 3
0x1400128e1  mov     [rsp+78h+var_50], eax
0x1400128e5  mov     rcx, [rcx+40h]
0x1400128e9  mov     [rsp+78h+var_58], rdi
0x1400128ee  call    WPP_RECORDER_SF_d
0x1400128f3  mov     dl, [rbx+40h]; NewIrql
0x1400128f6  mov     rcx, rsi; SpinLock
0x1400128f9  call    cs:__imp_KeReleaseSpinLock
0x140012900  nop     dword ptr [rax+rax+00h]
0x140012905  mov     dl, [r14]
0x140012908  shr     dl, 2
0x14001290b  xor     r8d, r8d
0x14001290e  jmp     loc_1400126E2
```
