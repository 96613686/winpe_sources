# TdiDisconnectInd

- ea: `0x14000877c`
- end: `0x140008ab2`
- name: `TdiDisconnectInd`
- size: `822`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400097f4`
- `0x14000b318`
- `0x140010688`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x140005050`
- `0x140005c38`
- `0x140007350`
- `0x140007488`
- `0x14000877c`
- `0x140008ac0`
- `0x1400097f4`
- `0x14000ab70`
- `0x14000c92c`
- `0x14001e74c`
- `0x14001ea34`
- `0x14001ebd8`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400087a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400087a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008926`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400088c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008926`

## string_xrefs

- `0x14000880e`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140008a45`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140008a57`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiDisconnectInd(__int64 a1, unsigned int a2)
{
  KSPIN_LOCK *v2; // r13
  KIRQL *v4; // rdi
  int v5; // edx
  __int64 v6; // rbp
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // r14
  int v10; // edx
  void (__fastcall *v11)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, __int64, int); // r12
  char v12; // si
  char v13; // r15
  char v14; // r14
  int v15; // eax
  int v16; // edx
  int v17; // edx
  int v18; // r9d
  __int64 result; // rax
  int v20; // edx
  __int64 v21; // [rsp+30h] [rbp-48h]
  int v22; // [rsp+38h] [rbp-40h]
  IRP *Irp; // [rsp+90h] [rbp+18h]

  v2 = (KSPIN_LOCK *)(a1 + 48);
  v4 = (KIRQL *)(a1 + 56);
  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v6 = TdiReferenceAddrLocked(a1, 1129531716);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = *(_DWORD *)(a1 + 80);
    HIDWORD(v21) = HIDWORD(a1);
    WPP_RECORDER_SF_qqL(WPP_GLOBAL_Control->DeviceExtension, v5, v7, v8);
    v4 = (KIRQL *)(a1 + 56);
  }
  v9 = a1 + 24;
  RefObj_AddRefEx(a1 + 24, 1129531716, 2382, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  Irp = (IRP *)IrpList_Dequeue(a1 + 568);
  if ( Irp )
  {
    TdiConnStateLocked(a1, 0);
    goto LABEL_5;
  }
  v15 = *(_DWORD *)(a1 + 80);
  if ( v15 == 2 )
  {
    TdiConnStateLocked(a1, 3);
    if ( *(_QWORD *)(a1 + 792) != a1 + 792 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v16,
          15,
          85,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
LABEL_13:
      KeReleaseSpinLock(v2, *v4);
      goto LABEL_32;
    }
    v4 = (KIRQL *)(a1 + 56);
  }
  else if ( !v15 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        15,
        86,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        a1);
    goto LABEL_13;
  }
LABEL_5:
  v11 = 0;
  v12 = 1;
  *(_WORD *)(a1 + 96) = 0;
  v13 = 1;
  if ( v6 )
    v11 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, __int64, int))(v6 + 160);
  if ( *(_QWORD *)(a1 + 344) == a1 + 344 )
  {
    v14 = 0;
  }
  else
  {
    v14 = 1;
    TdiConnStateLocked(a1, 0);
  }
  KeReleaseSpinLock(v2, *v4);
  if ( v14 )
  {
    TdiCompleteConnect(a1, a2);
    v13 = 0;
  }
  if ( Irp )
  {
    RfcommCompleteTdiIrp(Irp, 0, 0, v18);
LABEL_24:
    if ( v11 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qs(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          15,
          87,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
          a1,
          (__int64)"GRACEFUL");
      LODWORD(v21) = 4;
      v11(*(_QWORD *)(v6 + 168), *(_QWORD *)(a1 + 328), 0, 0, 0, 0, v21, v22);
    }
    else
    {
      TdiDisconnectRequest(*(_QWORD *)(a1 + 64), 0, a1, 0, 0);
    }
    if ( v12 )
      TdiIndicateReceive(a1);
    goto LABEL_31;
  }
  v12 = 0;
  if ( v13 )
    goto LABEL_24;
LABEL_31:
  v9 = a1 + 24;
LABEL_32:
  if ( v6 )
    RefObj_ReleaseEx(v6 + 24, 1129531716, 2534, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  result = RefObj_ReleaseEx(v9, 1129531716, 2537, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v20,
             15,
             88,
             (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000877c  mov     [rsp+arg_18], rbx
0x140008781  mov     [rsp+arg_8], edx
0x140008785  push    rbp
0x140008786  push    rsi
0x140008787  push    rdi
0x140008788  push    r12
0x14000878a  push    r13
0x14000878c  push    r14
0x14000878e  push    r15
0x140008790  sub     rsp, 40h
0x140008794  lea     r13, [rcx+30h]
0x140008798  mov     rbx, rcx
0x14000879b  lea     rdi, [rcx+38h]
0x14000879f  mov     rcx, r13; SpinLock
0x1400087a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400087a9  nop     dword ptr [rax+rax+00h]
0x1400087ae  mov     r12d, 43534944h
0x1400087b4  mov     rcx, rbx
0x1400087b7  mov     edx, r12d
0x1400087ba  mov     [rdi], al
0x1400087bc  call    TdiReferenceAddrLocked
0x1400087c1  mov     rbp, rax
0x1400087c4  lea     r15, WPP_RECORDER_INITIALIZED
0x1400087cb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400087d2  jz      short loc_1400087F9
0x1400087d4  mov     ecx, [rbx+50h]
0x1400087d7  mov     [rsp+78h+var_40], ecx
0x1400087db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087e2  mov     [rsp+78h+var_48], rbx
0x1400087e7  mov     [rsp+78h+var_50], rax
0x1400087ec  mov     rcx, [rcx+40h]
0x1400087f0  call    WPP_RECORDER_SF_qqL
0x1400087f5  lea     rdi, [rbx+38h]
0x1400087f9  lea     r14, [rbx+18h]
0x1400087fd  mov     r8d, 94Eh
0x140008803  mov     rcx, r14
0x140008806  mov     [rsp+78h+arg_0], r14
0x14000880e  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008815  mov     rdx, r12
0x140008818  call    RefObj_AddRefEx
0x14000881d  lea     rcx, [rbx+238h]
0x140008824  call    IrpList_Dequeue
0x140008829  mov     [rsp+78h+Irp], rax
0x140008831  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140008838  test    rax, rax
0x14000883b  jz      short loc_140008879
0x14000883d  xor     edx, edx
0x14000883f  mov     rcx, rbx
0x140008842  call    TdiConnStateLocked
0x140008847  xor     r12d, r12d
0x14000884a  mov     sil, 1
0x14000884d  mov     [rbx+60h], r12w
0x140008852  mov     r15b, sil
0x140008855  test    rbp, rbp
0x140008858  jz      short loc_140008861
0x14000885a  mov     r12, [rbp+0A0h]
0x140008861  lea     rax, [rbx+158h]
0x140008868  cmp     [rax], rax
0x14000886b  jnz     loc_140008914
0x140008871  xor     r14b, r14b
0x140008874  jmp     loc_140008921
0x140008879  mov     eax, [rbx+50h]
0x14000887c  cmp     eax, 2
0x14000887f  jnz     short loc_1400088DF
0x140008881  lea     edx, [rax+1]
0x140008884  mov     rcx, rbx
0x140008887  call    TdiConnStateLocked
0x14000888c  lea     rax, [rbx+318h]
0x140008893  cmp     [rax], rax
0x140008896  jz      short loc_1400088D6
0x140008898  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000889f  jz      short loc_1400088C0
0x1400088a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088a8  mov     r9d, 55h ; 'U'
0x1400088ae  mov     [rsp+78h+var_58], r12
0x1400088b3  mov     rcx, [rcx+40h]
0x1400088b7  lea     r8d, [r9-46h]
0x1400088bb  call    WPP_RECORDER_SF_
0x1400088c0  mov     dl, [rdi]; NewIrql
0x1400088c2  mov     rcx, r13; SpinLock
0x1400088c5  call    cs:__imp_KeReleaseSpinLock
0x1400088cc  nop     dword ptr [rax+rax+00h]
0x1400088d1  jmp     loc_140008A37
0x1400088d6  lea     rdi, [rbx+38h]
0x1400088da  jmp     loc_140008847
0x1400088df  test    eax, eax
0x1400088e1  jnz     loc_140008847
0x1400088e7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400088ee  jz      short loc_1400088C0
0x1400088f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088f7  lea     r9d, [rax+56h]
0x1400088fb  mov     [rsp+78h+var_50], rbx
0x140008900  lea     r8d, [rax+0Fh]
0x140008904  mov     [rsp+78h+var_58], r12
0x140008909  mov     rcx, [rcx+40h]
0x14000890d  call    WPP_RECORDER_SF_q
0x140008912  jmp     short loc_1400088C0
0x140008914  xor     edx, edx
0x140008916  mov     rcx, rbx
0x140008919  mov     r14b, sil
0x14000891c  call    TdiConnStateLocked
0x140008921  mov     dl, [rdi]; NewIrql
0x140008923  mov     rcx, r13; SpinLock
0x140008926  call    cs:__imp_KeReleaseSpinLock
0x14000892d  nop     dword ptr [rax+rax+00h]
0x140008932  test    r14b, r14b
0x140008935  jz      short loc_140008949
0x140008937  mov     edx, [rsp+78h+arg_8]
0x14000893e  mov     rcx, rbx
0x140008941  call    TdiCompleteConnect
0x140008946  xor     r15b, r15b
0x140008949  mov     rcx, [rsp+78h+Irp]; Irp
0x140008951  test    rcx, rcx
0x140008954  jz      short loc_140008962
0x140008956  xor     r8d, r8d
0x140008959  xor     edx, edx
0x14000895b  call    RfcommCompleteTdiIrp
0x140008960  jmp     short loc_14000896E
0x140008962  xor     sil, sil
0x140008965  test    r15b, r15b
0x140008968  jz      loc_140008A21
0x14000896e  test    r12, r12
0x140008971  jz      short loc_1400089F1
0x140008973  lea     r15, WPP_RECORDER_INITIALIZED
0x14000897a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008981  jz      short loc_1400089BA
0x140008983  mov     rcx, cs:WPP_GLOBAL_Control
0x14000898a  lea     rax, aGraceful; "GRACEFUL"
0x140008991  mov     [rsp+78h+var_48], rax
0x140008996  mov     r9d, 57h ; 'W'
0x14000899c  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400089a3  mov     [rsp+78h+var_50], rbx
0x1400089a8  mov     [rsp+78h+var_58], rax
0x1400089ad  mov     rcx, [rcx+40h]
0x1400089b1  lea     r8d, [r9-48h]
0x1400089b5  call    WPP_RECORDER_SF_qs
0x1400089ba  mov     rdx, [rbx+148h]
0x1400089c1  xor     r9d, r9d
0x1400089c4  mov     rcx, [rbp+0A8h]
0x1400089cb  xor     r8d, r8d
0x1400089ce  mov     dword ptr [rsp+78h+var_48], 4
0x1400089d6  mov     rax, r12
0x1400089d9  mov     [rsp+78h+var_50], 0
0x1400089e2  mov     dword ptr [rsp+78h+var_58], 0
0x1400089ea  call    _guard_dispatch_icall
0x1400089ef  jmp     short loc_140008A12
0x1400089f1  mov     rcx, [rbx+40h]
0x1400089f5  xor     r9d, r9d
0x1400089f8  mov     r8, rbx
0x1400089fb  mov     [rsp+78h+var_58], 0
0x140008a04  xor     edx, edx
0x140008a06  call    TdiDisconnectRequest
0x140008a0b  lea     r15, WPP_RECORDER_INITIALIZED
0x140008a12  test    sil, sil
0x140008a15  jz      short loc_140008A28
0x140008a17  mov     rcx, rbx
0x140008a1a  call    TdiIndicateReceive
0x140008a1f  jmp     short loc_140008A28
0x140008a21  lea     r15, WPP_RECORDER_INITIALIZED
0x140008a28  mov     r14, [rsp+78h+arg_0]
0x140008a30  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140008a37  test    rbp, rbp
0x140008a3a  jz      short loc_140008A57
0x140008a3c  lea     rcx, [rbp+18h]
0x140008a40  mov     edx, 43534944h
0x140008a45  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008a4c  mov     r8d, 9E6h
0x140008a52  call    RefObj_ReleaseEx
0x140008a57  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008a5e  mov     edx, 43534944h
0x140008a63  mov     r8d, 9E9h
0x140008a69  mov     rcx, r14
0x140008a6c  call    RefObj_ReleaseEx
0x140008a71  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008a78  jz      short loc_140008A99
0x140008a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a81  mov     r9d, 58h ; 'X'
0x140008a87  mov     [rsp+78h+var_58], r12
0x140008a8c  mov     rcx, [rcx+40h]
0x140008a90  lea     r8d, [r9-49h]
0x140008a94  call    WPP_RECORDER_SF_
0x140008a99  mov     rbx, [rsp+78h+arg_18]
0x140008aa1  add     rsp, 40h
0x140008aa5  pop     r15
0x140008aa7  pop     r14
0x140008aa9  pop     r13
0x140008aab  pop     r12
0x140008aad  pop     rdi
0x140008aae  pop     rsi
0x140008aaf  pop     rbp
0x140008ab0  retn
```
