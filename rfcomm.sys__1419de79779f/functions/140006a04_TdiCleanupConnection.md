# TdiCleanupConnection

- ea: `0x140006a04`
- end: `0x140006bb8`
- name: `TdiCleanupConnection`
- size: `436`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006750`
- `0x140007200`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x140006a04`
- `0x140007488`
- `0x1400085a0`
- `0x140008fd4`
- `0x14000aba8`
- `0x140010688`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ac6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ae5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ac6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ae5`
- `ntoskrnl!ObfDereferenceObject` at `0x140006a77`
- `ntoskrnl!ObfDereferenceObject` at `0x140006a77`

## string_xrefs

- `0x140006b68`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiCleanupConnection(__int64 a1, int a2)
{
  void *v3; // rcx
  __int64 v4; // rax
  KIRQL v5; // dl
  __int64 v6; // rdi
  KSPIN_LOCK *v7; // rcx
  int v8; // edx
  char v10; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      90,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a1);
  TdiDisassociateAddress(*(_QWORD *)(a1 + 64), 0, a1, 0, (__int64)&v10);
  v3 = *(void **)(a1 + 88);
  if ( v3 )
  {
    ObfDereferenceObject(v3);
    *(_QWORD *)(a1 + 88) = 0;
  }
  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  TdiConnStateLocked(a1, 0);
  v4 = TdiReferenceChannelLocked(a1, 1313754947);
  v5 = *(_BYTE *)(a1 + 56);
  v6 = v4;
  v7 = (KSPIN_LOCK *)(a1 + 48);
  if ( v4 )
  {
    KeReleaseSpinLock(v7, v5);
    ChannelUnpairConn(v6, a1, 0xC000013B);
  }
  else
  {
    KeReleaseSpinLock(v7, v5);
  }
  TdiDrainAndComplete(a1, a1 + 344);
  TdiDrainAndComplete(a1, a1 + 568);
  TdiDrainAndComplete(a1, a1 + 512);
  TdiDrainAndComplete(a1, a1 + 456);
  TdiDrainAndComplete(a1, a1 + 400);
  TdiDrainAndComplete(a1, a1 + 680);
  TdiDrainAndComplete(a1, a1 + 736);
  if ( v6 )
    RefObj_ReleaseEx(v6 + 24, 1313754947, 2671, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      15,
      91,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140006a04  mov     rax, rsp
0x140006a07  mov     [rax+10h], rbx
0x140006a0b  mov     [rax+18h], rbp
0x140006a0f  push    rsi
0x140006a10  push    rdi
0x140006a11  push    r15
0x140006a13  sub     rsp, 30h
0x140006a17  mov     rbx, rcx
0x140006a1a  lea     rbp, WPP_RECORDER_INITIALIZED
0x140006a21  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006a28  lea     r15, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140006a2f  jz      short loc_140006A53
0x140006a31  mov     [rax-20h], rcx
0x140006a35  mov     r9d, 5Ah ; 'Z'
0x140006a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a42  mov     [rax-28h], r15
0x140006a46  lea     r8d, [r9-4Bh]
0x140006a4a  mov     rcx, [rcx+40h]
0x140006a4e  call    WPP_RECORDER_SF_q
0x140006a53  mov     rcx, [rbx+40h]
0x140006a57  lea     rax, [rsp+48h+arg_0]
0x140006a5c  xor     r9d, r9d
0x140006a5f  mov     [rsp+48h+var_28], rax
0x140006a64  mov     r8, rbx
0x140006a67  xor     edx, edx
0x140006a69  call    TdiDisassociateAddress
0x140006a6e  mov     rcx, [rbx+58h]; Object
0x140006a72  test    rcx, rcx
0x140006a75  jz      short loc_140006A8B
0x140006a77  call    cs:__imp_ObfDereferenceObject
0x140006a7e  nop     dword ptr [rax+rax+00h]
0x140006a83  mov     qword ptr [rbx+58h], 0
0x140006a8b  lea     rsi, [rbx+30h]
0x140006a8f  mov     rcx, rsi; SpinLock
0x140006a92  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006a99  nop     dword ptr [rax+rax+00h]
0x140006a9e  xor     edx, edx
0x140006aa0  mov     rcx, rbx
0x140006aa3  mov     [rbx+38h], al
0x140006aa6  call    TdiConnStateLocked
0x140006aab  mov     edx, 4E4E4F43h
0x140006ab0  mov     rcx, rbx
0x140006ab3  call    TdiReferenceChannelLocked
0x140006ab8  mov     dl, [rbx+38h]; NewIrql
0x140006abb  mov     rdi, rax
0x140006abe  mov     rcx, rsi; SpinLock
0x140006ac1  test    rax, rax
0x140006ac4  jz      short loc_140006AE5
0x140006ac6  call    cs:__imp_KeReleaseSpinLock
0x140006acd  nop     dword ptr [rax+rax+00h]
0x140006ad2  mov     r8d, 0C000013Bh
0x140006ad8  mov     rdx, rbx
0x140006adb  mov     rcx, rdi
0x140006ade  call    ChannelUnpairConn
0x140006ae3  jmp     short loc_140006AF1
0x140006ae5  call    cs:__imp_KeReleaseSpinLock
0x140006aec  nop     dword ptr [rax+rax+00h]
0x140006af1  lea     rdx, [rbx+158h]
0x140006af8  mov     rcx, rbx
0x140006afb  call    TdiDrainAndComplete
0x140006b00  lea     rdx, [rbx+238h]
0x140006b07  mov     rcx, rbx
0x140006b0a  call    TdiDrainAndComplete
0x140006b0f  lea     rdx, [rbx+200h]
0x140006b16  mov     rcx, rbx
0x140006b19  call    TdiDrainAndComplete
0x140006b1e  lea     rdx, [rbx+1C8h]
0x140006b25  mov     rcx, rbx
0x140006b28  call    TdiDrainAndComplete
0x140006b2d  lea     rdx, [rbx+190h]
0x140006b34  mov     rcx, rbx
0x140006b37  call    TdiDrainAndComplete
0x140006b3c  lea     rdx, [rbx+2A8h]
0x140006b43  mov     rcx, rbx
0x140006b46  call    TdiDrainAndComplete
0x140006b4b  lea     rdx, [rbx+2E0h]
0x140006b52  mov     rcx, rbx
0x140006b55  call    TdiDrainAndComplete
0x140006b5a  test    rdi, rdi
0x140006b5d  jz      short loc_140006B7A
0x140006b5f  lea     rcx, [rdi+18h]
0x140006b63  mov     edx, 4E4E4F43h
0x140006b68  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006b6f  mov     r8d, 0A6Fh
0x140006b75  call    RefObj_ReleaseEx
0x140006b7a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140006b81  jz      short loc_140006BA2
0x140006b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b8a  mov     r9d, 5Bh ; '['
0x140006b90  mov     [rsp+48h+var_28], r15
0x140006b95  mov     rcx, [rcx+40h]
0x140006b99  lea     r8d, [r9-4Ch]
0x140006b9d  call    WPP_RECORDER_SF_
0x140006ba2  mov     rbx, [rsp+48h+arg_8]
0x140006ba7  xor     eax, eax
0x140006ba9  mov     rbp, [rsp+48h+arg_10]
0x140006bae  add     rsp, 30h
0x140006bb2  pop     r15
0x140006bb4  pop     rdi
0x140006bb5  pop     rsi
0x140006bb6  retn
```
