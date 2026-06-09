# ChannelUnpairConn

- ea: `0x140010688`
- end: `0x140010809`
- name: `ChannelUnpairConn`
- size: `385`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006a04`
- `0x1400197ec`

## callees

- `0x140003bf4`
- `0x140004e58`
- `0x14000877c`
- `0x140010688`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001071d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010734`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010756`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001076d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001071d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010734`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010756`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001076d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001078f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001078f`

## string_xrefs

- `0x1400107a4`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x1400107bf`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
void __fastcall ChannelUnpairConn(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rbx
  KIRQL v7; // al
  int v8; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      170,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a2,
      a1);
  v6 = *(_QWORD *)(a1 + 56);
  *(_BYTE *)(v6 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 56));
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 48));
  *(_BYTE *)(a2 + 56) = v7;
  if ( *(_QWORD *)(a2 + 272) )
  {
    *(_QWORD *)(a2 + 272) = 0;
    *(_QWORD *)(a1 + 64) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 48), *(_BYTE *)(a2 + 56));
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 56) + 56LL), *(_BYTE *)(*(_QWORD *)(a1 + 56) + 64LL));
    TdiDisconnectInd(a2, a3);
    ObfDereferenceObject(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 72LL) + 80LL));
    RefObj_ReleaseEx(a1 + 24, 1313754947, 6024, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    RefObj_ReleaseEx(a2 + 24, 1111705667, 6025, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        171,
        (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 48), v7);
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 56) + 56LL), *(_BYTE *)(*(_QWORD *)(a1 + 56) + 64LL));
  }
}

```

## disassembly

```asm
0x140010688  push    rbx
0x14001068a  push    rbp
0x14001068b  push    rsi
0x14001068c  push    rdi
0x14001068d  push    r12
0x14001068f  push    r15
0x140010691  sub     rsp, 48h
0x140010695  mov     ebp, r8d
0x140010698  mov     rdi, rdx
0x14001069b  mov     rsi, rcx
0x14001069e  lea     r12, WPP_RECORDER_INITIALIZED
0x1400106a5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400106ac  lea     r15, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400106b3  jz      short loc_1400106E0
0x1400106b5  mov     [rsp+78h+var_48], rcx
0x1400106ba  mov     r9d, 0AAh
0x1400106c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400106c7  mov     r8d, 3
0x1400106cd  mov     [rsp+78h+var_50], rdx
0x1400106d2  mov     [rsp+78h+var_58], r15
0x1400106d7  mov     rcx, [rcx+40h]
0x1400106db  call    WPP_RECORDER_SF_qq
0x1400106e0  mov     rbx, [rsi+38h]
0x1400106e4  lea     rcx, [rbx+38h]; SpinLock
0x1400106e8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400106ef  nop     dword ptr [rax+rax+00h]
0x1400106f4  mov     [rbx+40h], al
0x1400106f7  lea     rbx, [rdi+30h]
0x1400106fb  mov     rcx, rbx; SpinLock
0x1400106fe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010705  nop     dword ptr [rax+rax+00h]
0x14001070a  xor     ecx, ecx
0x14001070c  mov     [rdi+38h], al
0x14001070f  cmp     [rdi+110h], rcx
0x140010716  jnz     short loc_140010745
0x140010718  mov     dl, al; NewIrql
0x14001071a  mov     rcx, rbx; SpinLock
0x14001071d  call    cs:__imp_KeReleaseSpinLock
0x140010724  nop     dword ptr [rax+rax+00h]
0x140010729  mov     rdx, [rsi+38h]
0x14001072d  lea     rcx, [rdx+38h]; SpinLock
0x140010731  mov     dl, [rdx+40h]; NewIrql
0x140010734  call    cs:__imp_KeReleaseSpinLock
0x14001073b  nop     dword ptr [rax+rax+00h]
0x140010740  jmp     loc_1400107FB
0x140010745  mov     [rdi+110h], rcx
0x14001074c  mov     [rsi+40h], rcx
0x140010750  mov     rcx, rbx; SpinLock
0x140010753  mov     dl, [rdi+38h]; NewIrql
0x140010756  call    cs:__imp_KeReleaseSpinLock
0x14001075d  nop     dword ptr [rax+rax+00h]
0x140010762  mov     rdx, [rsi+38h]
0x140010766  lea     rcx, [rdx+38h]; SpinLock
0x14001076a  mov     dl, [rdx+40h]; NewIrql
0x14001076d  call    cs:__imp_KeReleaseSpinLock
0x140010774  nop     dword ptr [rax+rax+00h]
0x140010779  mov     edx, ebp
0x14001077b  mov     rcx, rdi
0x14001077e  call    TdiDisconnectInd
0x140010783  mov     rax, [rsi+38h]
0x140010787  mov     rcx, [rax+48h]
0x14001078b  mov     rcx, [rcx+50h]; Object
0x14001078f  call    cs:__imp_ObfDereferenceObject
0x140010796  nop     dword ptr [rax+rax+00h]
0x14001079b  lea     rcx, [rsi+18h]
0x14001079f  mov     edx, 4E4E4F43h
0x1400107a4  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400107ab  mov     r8d, 1788h
0x1400107b1  call    RefObj_ReleaseEx
0x1400107b6  lea     rcx, [rdi+18h]
0x1400107ba  mov     edx, 42434843h
0x1400107bf  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400107c6  mov     r8d, 1789h
0x1400107cc  call    RefObj_ReleaseEx
0x1400107d1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400107d8  jz      short loc_1400107FB
0x1400107da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400107e1  mov     r9d, 0ABh
0x1400107e7  mov     r8d, 3
0x1400107ed  mov     [rsp+78h+var_58], r15
0x1400107f2  mov     rcx, [rcx+40h]
0x1400107f6  call    WPP_RECORDER_SF_
0x1400107fb  add     rsp, 48h
0x1400107ff  pop     r15
0x140010801  pop     r12
0x140010803  pop     rdi
0x140010804  pop     rsi
0x140010805  pop     rbp
0x140010806  pop     rbx
0x140010807  retn
```
