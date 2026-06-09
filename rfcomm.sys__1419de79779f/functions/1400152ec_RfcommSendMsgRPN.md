# RfcommSendMsgRPN

- ea: `0x1400152ec`
- end: `0x140015524`
- name: `RfcommSendMsgRPN`
- size: `568`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001eec`

## callees

- `0x140003818`
- `0x140003cb4`
- `0x1400135cc`
- `0x140013abc`
- `0x140013bf8`
- `0x1400152ec`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015360`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015360`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400154a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400154a5`

## string_xrefs

- `0x140015415`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x14001548c`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommSendMsgRPN(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  __int64 v4; // rdi
  char v8; // r15
  int v9; // r12d
  KIRQL v10; // al
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 NextCmdLocked; // rbx
  unsigned int v14; // ebp
  char v15; // cl
  char v16; // al
  int v17; // edx
  unsigned int v19; // [rsp+90h] [rbp+8h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+18h]

  v20 = a3;
  v4 = *(_QWORD *)(a1 + 56);
  v19 = 10;
  v8 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      71,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      *a4);
  v9 = *a4;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 56));
  v11 = 152;
  *(_BYTE *)(v4 + 64) = v10;
  if ( v9 == 5 )
    v11 = 168;
  v12 = RfcommFrameAllocLockedEx(v4, (__int64 *)a1, 239, 36, 0, v9 == 5, &v19, a1 + v11, 0);
  NextCmdLocked = v12;
  if ( v12 )
  {
    *(_BYTE *)(v12 + 155) = -111;
    v14 = 259;
    if ( v9 != 5 )
      *(_BYTE *)(v12 + 155) = -109;
    if ( *a4 == 4 )
    {
      v15 = 3;
    }
    else
    {
      v15 = 17;
      *(_DWORD *)(v12 + 158) = a4[1];
      *(_WORD *)(v12 + 162) = *((_WORD *)a4 + 4);
      *(_BYTE *)(v12 + 164) = *((_BYTE *)a4 + 10);
    }
    v16 = (4 * *(_BYTE *)(a1 + 184)) | 3;
    *(_BYTE *)(NextCmdLocked + 156) = v15;
    *(_BYTE *)(NextCmdLocked + 157) = v16;
    RefObj_AddRefEx(a2 + 24, 1296126534, 3384, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    *(_QWORD *)(NextCmdLocked + 88) = v20;
    *(_QWORD *)(NextCmdLocked + 96) = a2 + 680;
    *(_QWORD *)(NextCmdLocked + 80) = a2;
    *(_DWORD *)(NextCmdLocked + 104) = 0;
    *(_DWORD *)(NextCmdLocked + 60) = 11;
    if ( v9 == 5 )
    {
      RefObj_AddRefEx(
        NextCmdLocked + 24,
        1346917442,
        3407,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
    else
    {
      NextCmdLocked = RfcommGetNextCmdLocked(v4, a1);
      v8 = 1;
    }
  }
  else
  {
    v14 = -1073741670;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 56), *(_BYTE *)(v4 + 64));
  if ( NextCmdLocked )
  {
    if ( v8 )
      RfcommStartTimer(*(_QWORD *)(v4 + 72));
    RfcommFrameWrite(v4, NextCmdLocked);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      3,
      72,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v14);
  return v14;
}

```

## disassembly

```asm
0x1400152ec  mov     rax, rsp
0x1400152ef  mov     [rax+10h], rbx
0x1400152f3  mov     [rax+18h], r8
0x1400152f7  push    rbp
0x1400152f8  push    rsi
0x1400152f9  push    rdi
0x1400152fa  push    r12
0x1400152fc  push    r13
0x1400152fe  push    r14
0x140015300  push    r15
0x140015302  sub     rsp, 50h
0x140015306  mov     rdi, [rcx+38h]
0x14001530a  mov     rsi, r9
0x14001530d  mov     r13, rdx
0x140015310  mov     dword ptr [rax+8], 0Ah
0x140015317  mov     r14, rcx
0x14001531a  xor     r15b, r15b
0x14001531d  lea     rax, WPP_RECORDER_INITIALIZED
0x140015324  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001532b  lea     rcx, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140015332  jz      short loc_140015359
0x140015334  mov     eax, [rsi]
0x140015336  mov     r9d, 47h ; 'G'
0x14001533c  mov     [rsp+88h+var_60], eax
0x140015340  mov     [rsp+88h+var_68], rcx
0x140015345  mov     rcx, cs:WPP_GLOBAL_Control
0x14001534c  lea     r8d, [r9-44h]
0x140015350  mov     rcx, [rcx+40h]
0x140015354  call    WPP_RECORDER_SF_d
0x140015359  mov     r12d, [rsi]
0x14001535c  lea     rcx, [rdi+38h]; SpinLock
0x140015360  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015367  nop     dword ptr [rax+rax+00h]
0x14001536c  mov     [rsp+88h+var_48], r15b
0x140015371  mov     ecx, 98h
0x140015376  mov     [rdi+40h], al
0x140015379  cmp     r12d, 5
0x14001537d  mov     r9b, 24h ; '$'
0x140015380  mov     r8b, 0EFh
0x140015383  mov     rdx, r14
0x140015386  lea     eax, [rcx+10h]
0x140015389  cmovz   ecx, eax
0x14001538c  xor     eax, eax
0x14001538e  add     rcx, r14
0x140015391  mov     [rsp+88h+var_50], rcx
0x140015396  cmp     r12d, 5
0x14001539a  lea     rcx, [rsp+88h+arg_0]
0x1400153a2  mov     [rsp+88h+var_58], rcx
0x1400153a7  setz    al
0x1400153aa  mov     [rsp+88h+var_60], eax
0x1400153ae  mov     rcx, rdi
0x1400153b1  mov     byte ptr [rsp+88h+var_68], r15b
0x1400153b6  call    RfcommFrameAllocLockedEx
0x1400153bb  mov     rbx, rax
0x1400153be  test    rax, rax
0x1400153c1  jnz     short loc_1400153CD
0x1400153c3  mov     ebp, 0C000009Ah
0x1400153c8  jmp     loc_14001549E
0x1400153cd  mov     byte ptr [rax+9Bh], 91h
0x1400153d4  mov     ebp, 103h
0x1400153d9  cmp     r12d, 5
0x1400153dd  jz      short loc_1400153E6
0x1400153df  mov     byte ptr [rax+9Bh], 93h
0x1400153e6  cmp     dword ptr [rsi], 4
0x1400153e9  jnz     short loc_1400153EF
0x1400153eb  mov     cl, 3
0x1400153ed  jmp     short loc_14001540E
0x1400153ef  mov     eax, [rsi+4]
0x1400153f2  mov     cl, 11h
0x1400153f4  mov     [rbx+9Eh], eax
0x1400153fa  movzx   eax, word ptr [rsi+8]
0x1400153fe  mov     [rbx+0A2h], ax
0x140015405  mov     al, [rsi+0Ah]
0x140015408  mov     [rbx+0A4h], al
0x14001540e  mov     al, [r14+0B8h]
0x140015415  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14001541c  shl     al, 2
0x14001541f  mov     edx, 4D415246h
0x140015424  or      al, 3
0x140015426  mov     [rbx+9Ch], cl
0x14001542c  lea     rcx, [r13+18h]
0x140015430  mov     [rbx+9Dh], al
0x140015436  mov     r8d, 0D38h
0x14001543c  call    RefObj_AddRefEx
0x140015441  mov     rax, [rsp+88h+arg_10]
0x140015449  mov     [rbx+58h], rax
0x14001544d  lea     rax, [r13+2A8h]
0x140015454  mov     [rbx+60h], rax
0x140015458  mov     [rbx+50h], r13
0x14001545c  mov     dword ptr [rbx+68h], 0
0x140015463  mov     dword ptr [rbx+3Ch], 0Bh
0x14001546a  cmp     r12d, 5
0x14001546e  jz      short loc_140015483
0x140015470  mov     rdx, r14
0x140015473  mov     rcx, rdi
0x140015476  call    RfcommGetNextCmdLocked
0x14001547b  mov     rbx, rax
0x14001547e  mov     r15b, 1
0x140015481  jmp     short loc_14001549E
0x140015483  lea     rcx, [rbx+18h]
0x140015487  mov     edx, 50485442h
0x14001548c  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140015493  mov     r8d, 0D4Fh
0x140015499  call    RefObj_AddRefEx
0x14001549e  mov     dl, [rdi+40h]; NewIrql
0x1400154a1  lea     rcx, [rdi+38h]; SpinLock
0x1400154a5  call    cs:__imp_KeReleaseSpinLock
0x1400154ac  nop     dword ptr [rax+rax+00h]
0x1400154b1  test    rbx, rbx
0x1400154b4  jz      short loc_1400154CF
0x1400154b6  test    r15b, r15b
0x1400154b9  jz      short loc_1400154C4
0x1400154bb  mov     rcx, [rdi+48h]
0x1400154bf  call    RfcommStartTimer
0x1400154c4  mov     rdx, rbx
0x1400154c7  mov     rcx, rdi
0x1400154ca  call    RfcommFrameWrite
0x1400154cf  lea     rax, WPP_RECORDER_INITIALIZED
0x1400154d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400154dd  jz      short loc_140015509
0x1400154df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400154e6  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400154ed  mov     r9d, 48h ; 'H'
0x1400154f3  mov     [rsp+88h+var_60], ebp
0x1400154f7  mov     [rsp+88h+var_68], rax
0x1400154fc  mov     rcx, [rcx+40h]
0x140015500  lea     r8d, [r9-45h]
0x140015504  call    WPP_RECORDER_SF_d
0x140015509  mov     rbx, [rsp+88h+arg_8]
0x140015511  mov     eax, ebp
0x140015513  add     rsp, 50h
0x140015517  pop     r15
0x140015519  pop     r14
0x14001551b  pop     r13
0x14001551d  pop     r12
0x14001551f  pop     rdi
0x140015520  pop     rsi
0x140015521  pop     rbp
0x140015522  retn
```
