# RfcommSendPageScanCompletionRoutine

- ea: `0x1400031d0`
- end: `0x14000331b`
- name: `RfcommSendPageScanCompletionRoutine`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400031d0`
- `0x140003bf4`
- `0x140003cb4`
- `0x140005c38`
- `0x14001a49c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400032d5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400032d5`

## string_xrefs

- `0x140003282`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x1400032a1`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
__int64 __fastcall RfcommSendPageScanCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v6; // rsi
  IRP *v7; // rcx
  int v8; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      111,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
  v6 = *(_QWORD *)(a1 + 64);
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        3,
        112,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        a2->IoStatus.Status);
    if ( a2->IoStatus.Status >= 0 )
      _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(a3 + 16) + 220LL), *(unsigned __int8 *)(a3 + 1));
    v7 = *(IRP **)(a3 + 24);
    if ( v7 )
      RfcommCompleteTdiIrp(v7);
    RefObj_ReleaseEx(
      *(_QWORD *)(a3 + 16) + 24LL,
      542134857,
      2740,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
    RefObj_ReleaseEx(
      *(_QWORD *)(a3 + 8) + 24LL,
      542134857,
      2741,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
    IrpFreeWithContext(a2);
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v6 + 40), RfcommSetPageScanForAddress, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      3,
      113,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400031d0  push    rbx
0x1400031d2  push    rsi
0x1400031d3  push    rdi
0x1400031d4  push    r12
0x1400031d6  push    r14
0x1400031d8  sub     rsp, 30h
0x1400031dc  mov     rbx, r8
0x1400031df  mov     rdi, rdx
0x1400031e2  mov     rsi, rcx
0x1400031e5  lea     r14, WPP_RECORDER_INITIALIZED
0x1400031ec  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400031f3  lea     r12, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400031fa  jz      short loc_14000321B
0x1400031fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140003203  mov     r9d, 6Fh ; 'o'
0x140003209  mov     [rsp+58h+var_38], r12
0x14000320e  mov     rcx, [rcx+40h]
0x140003212  lea     r8d, [r9-6Ch]
0x140003216  call    WPP_RECORDER_SF_
0x14000321b  mov     rsi, [rsi+40h]
0x14000321f  test    rdi, rdi
0x140003222  jz      loc_1400032C4
0x140003228  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14000322f  jz      short loc_140003257
0x140003231  mov     rcx, cs:WPP_GLOBAL_Control
0x140003238  mov     r9d, 70h ; 'p'
0x14000323e  mov     eax, [rdi+30h]
0x140003241  mov     [rsp+58h+var_30], eax
0x140003245  mov     [rsp+58h+var_38], r12
0x14000324a  mov     rcx, [rcx+40h]
0x14000324e  lea     r8d, [r9-6Dh]
0x140003252  call    WPP_RECORDER_SF_d
0x140003257  cmp     dword ptr [rdi+30h], 0
0x14000325b  jl      short loc_14000326B
0x14000325d  mov     rax, [rbx+10h]
0x140003261  movzx   ecx, byte ptr [rbx+1]
0x140003265  xchg    ecx, [rax+0DCh]
0x14000326b  mov     rcx, [rbx+18h]; Irp
0x14000326f  test    rcx, rcx
0x140003272  jz      short loc_14000327E
0x140003274  xor     r8d, r8d
0x140003277  xor     edx, edx
0x140003279  call    RfcommCompleteTdiIrp
0x14000327e  mov     rcx, [rbx+10h]
0x140003282  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140003289  add     rcx, 18h
0x14000328d  mov     edx, 20505249h
0x140003292  mov     r8d, 0AB4h
0x140003298  call    RefObj_ReleaseEx
0x14000329d  mov     rcx, [rbx+8]
0x1400032a1  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400032a8  add     rcx, 18h
0x1400032ac  mov     edx, 20505249h
0x1400032b1  mov     r8d, 0AB5h
0x1400032b7  call    RefObj_ReleaseEx
0x1400032bc  mov     rcx, rdi; Irp
0x1400032bf  call    IrpFreeWithContext
0x1400032c4  lea     rcx, [rsi+28h]; RemoveLock
0x1400032c8  mov     r8d, 20h ; ' '; RemlockSize
0x1400032ce  lea     rdx, RfcommSetPageScanForAddress; Tag
0x1400032d5  call    cs:__imp_IoReleaseRemoveLockEx
0x1400032dc  nop     dword ptr [rax+rax+00h]
0x1400032e1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400032e8  jz      short loc_140003309
0x1400032ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032f1  mov     r9d, 71h ; 'q'
0x1400032f7  mov     [rsp+58h+var_38], r12
0x1400032fc  mov     rcx, [rcx+40h]
0x140003300  lea     r8d, [r9-6Eh]
0x140003304  call    WPP_RECORDER_SF_
0x140003309  mov     eax, 0C0000016h
0x14000330e  add     rsp, 30h
0x140003312  pop     r14
0x140003314  pop     r12
0x140003316  pop     rdi
0x140003317  pop     rsi
0x140003318  pop     rbx
0x140003319  retn
```
