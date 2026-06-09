# RfcommShutdown

- ea: `0x140015904`
- end: `0x140015afb`
- name: `RfcommShutdown`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400011ac`
- `0x140002ec8`

## callees

- `0x140003bf4`
- `0x140015904`
- `0x140017db4`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015968`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400159b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015968`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400159b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015985`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400159cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015a3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015985`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400159cf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015a3c`

## string_xrefs

- `0x1400159e9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140015a98`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
void __fastcall RfcommShutdown(__int64 a1, int a2)
{
  KIRQL v3; // al
  bool v4; // zf
  __int64 v5; // rdx
  KSPIN_LOCK *i; // r14
  KIRQL v7; // al
  int v8; // ebx
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  __int64 v11; // rax
  _QWORD v12[2]; // [rsp+30h] [rbp-10h] BYREF

  v12[1] = v12;
  v12[0] = v12;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      172,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
  v4 = *(_BYTE *)(a1 + 128) == 0;
  *(_BYTE *)(a1 + 32) = v3;
  if ( v4 )
  {
    *(_BYTE *)(a1 + 128) = 1;
    for ( i = *(KSPIN_LOCK **)(a1 + 288); i != (KSPIN_LOCK *)(a1 + 288); i = (KSPIN_LOCK *)*i )
    {
      v7 = KeAcquireSpinLockRaiseToDpc(i + 7);
      v8 = *((_DWORD *)i + 12);
      *((_BYTE *)i + 64) = v7;
      KeReleaseSpinLock(i + 7, v7);
      if ( v8 != 6 )
      {
        RefObj_AddRefEx(i + 3, 1129531716, 6088, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
        v9 = v12[0];
        if ( *(_QWORD **)(v12[0] + 8LL) != v12 )
LABEL_15:
          __fastfail(3u);
        i[16] = v12[0];
        i[17] = (KSPIN_LOCK)v12;
        *(_QWORD *)(v9 + 8) = i + 16;
        v12[0] = i + 16;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), *(_BYTE *)(a1 + 32));
    while ( 1 )
    {
      v10 = (_QWORD *)v12[0];
      if ( (_QWORD *)v12[0] == v12 )
        break;
      if ( *(_QWORD **)(v12[0] + 8LL) != v12 )
        goto LABEL_15;
      v11 = *(_QWORD *)v12[0];
      if ( *(_QWORD *)(*(_QWORD *)v12[0] + 8LL) != v12[0] )
        goto LABEL_15;
      v12[0] = *(_QWORD *)v12[0];
      *(_QWORD *)(v11 + 8) = v12;
      v10[1] = v10;
      *v10 = v10;
      LOBYTE(v5) = 1;
      SessionDisconnectInd(v10 - 16, v5, 3221225860LL);
      RefObj_ReleaseEx(v10 - 13, 1129531716, 6105, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
    *(_BYTE *)(a1 + 128) = 0;
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), v3);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      173,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
}

```

## disassembly

```asm
0x140015904  push    rbp
0x140015906  push    rbx
0x140015907  push    rsi
0x140015908  push    rdi
0x140015909  push    r12
0x14001590b  push    r14
0x14001590d  push    r15
0x14001590f  mov     rbp, rsp
0x140015912  sub     rsp, 40h
0x140015916  lea     rax, [rbp+var_10]
0x14001591a  mov     rsi, rcx
0x14001591d  mov     [rbp+var_8], rax
0x140015921  lea     rax, [rbp+var_10]
0x140015925  mov     [rbp+var_10], rax
0x140015929  lea     rdi, WPP_RECORDER_INITIALIZED
0x140015930  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140015937  lea     rbx, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001593e  jz      short loc_140015961
0x140015940  mov     rcx, cs:WPP_GLOBAL_Control
0x140015947  mov     r9d, 0ACh
0x14001594d  mov     r8d, 3
0x140015953  mov     [rsp+40h+var_20], rbx
0x140015958  mov     rcx, [rcx+40h]
0x14001595c  call    WPP_RECORDER_SF_
0x140015961  lea     r15, [rsi+18h]
0x140015965  mov     rcx, r15; SpinLock
0x140015968  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001596f  nop     dword ptr [rax+rax+00h]
0x140015974  cmp     byte ptr [rsi+80h], 0
0x14001597b  mov     [rsi+20h], al
0x14001597e  jz      short loc_140015996
0x140015980  mov     dl, al; NewIrql
0x140015982  mov     rcx, r15; SpinLock
0x140015985  call    cs:__imp_KeReleaseSpinLock
0x14001598c  nop     dword ptr [rax+rax+00h]
0x140015991  jmp     loc_140015AC1
0x140015996  lea     r12, [rsi+120h]
0x14001599d  mov     byte ptr [rsi+80h], 1
0x1400159a4  mov     r14, [r12]
0x1400159a8  cmp     r14, r12
0x1400159ab  jz      loc_140015A36
0x1400159b1  lea     rcx, [r14+38h]; SpinLock
0x1400159b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400159bc  nop     dword ptr [rax+rax+00h]
0x1400159c1  mov     ebx, [r14+30h]
0x1400159c5  lea     rcx, [r14+38h]; SpinLock
0x1400159c9  mov     dl, al; NewIrql
0x1400159cb  mov     [r14+40h], al
0x1400159cf  call    cs:__imp_KeReleaseSpinLock
0x1400159d6  nop     dword ptr [rax+rax+00h]
0x1400159db  cmp     ebx, 6
0x1400159de  jz      short loc_140015A27
0x1400159e0  lea     rcx, [r14+18h]
0x1400159e4  mov     edx, 43534944h
0x1400159e9  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400159f0  mov     r8d, 17C8h
0x1400159f6  call    RefObj_AddRefEx
0x1400159fb  mov     rcx, [rbp+var_10]
0x1400159ff  lea     rax, [rbp+var_10]
0x140015a03  cmp     [rcx+8], rax
0x140015a07  jnz     loc_140015AAC
0x140015a0d  lea     rax, [r14+80h]
0x140015a14  mov     [rax], rcx
0x140015a17  lea     rdx, [rbp+var_10]
0x140015a1b  mov     [rax+8], rdx
0x140015a1f  mov     [rcx+8], rax
0x140015a23  mov     [rbp+var_10], rax
0x140015a27  mov     r14, [r14]
0x140015a2a  cmp     r14, r12
0x140015a2d  jnz     short loc_1400159B1
0x140015a2f  lea     rdi, WPP_RECORDER_INITIALIZED
0x140015a36  mov     dl, [rsi+20h]; NewIrql
0x140015a39  mov     rcx, r15; SpinLock
0x140015a3c  call    cs:__imp_KeReleaseSpinLock
0x140015a43  nop     dword ptr [rax+rax+00h]
0x140015a48  mov     rbx, [rbp+var_10]
0x140015a4c  lea     rax, [rbp+var_10]
0x140015a50  cmp     rbx, rax
0x140015a53  jz      short loc_140015AB3
0x140015a55  lea     rax, [rbp+var_10]
0x140015a59  cmp     [rbx+8], rax
0x140015a5d  jnz     short loc_140015AAC
0x140015a5f  mov     rax, [rbx]
0x140015a62  cmp     [rax+8], rbx
0x140015a66  jnz     short loc_140015AAC
0x140015a68  mov     [rbp+var_10], rax
0x140015a6c  lea     rcx, [rbp+var_10]
0x140015a70  mov     [rax+8], rcx
0x140015a74  xor     r9d, r9d
0x140015a77  lea     rcx, [rbx-80h]
0x140015a7b  mov     [rbx+8], rbx
0x140015a7f  mov     r8d, 0C0000184h
0x140015a85  mov     [rbx], rbx
0x140015a88  mov     dl, 1
0x140015a8a  call    SessionDisconnectInd
0x140015a8f  lea     rcx, [rbx-68h]
0x140015a93  mov     edx, 43534944h
0x140015a98  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140015a9f  mov     r8d, 17D9h
0x140015aa5  call    RefObj_ReleaseEx
0x140015aaa  jmp     short loc_140015A48
0x140015aac  mov     ecx, 3
0x140015ab1  int     29h; Win8: RtlFailFast(ecx)
0x140015ab3  mov     byte ptr [rsi+80h], 0
0x140015aba  lea     rbx, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140015ac1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140015ac8  jz      short loc_140015AEB
0x140015aca  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ad1  mov     r9d, 0ADh
0x140015ad7  mov     r8d, 3
0x140015add  mov     [rsp+40h+var_20], rbx
0x140015ae2  mov     rcx, [rcx+40h]
0x140015ae6  call    WPP_RECORDER_SF_
0x140015aeb  add     rsp, 40h
0x140015aef  pop     r15
0x140015af1  pop     r14
0x140015af3  pop     r12
0x140015af5  pop     rdi
0x140015af6  pop     rsi
0x140015af7  pop     rbx
0x140015af8  pop     rbp
0x140015af9  retn
```
