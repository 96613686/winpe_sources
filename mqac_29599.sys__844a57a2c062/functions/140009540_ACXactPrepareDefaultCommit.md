# ACXactPrepareDefaultCommit

- ea: `0x140009540`
- end: `0x1400095d9`
- name: `ACXactPrepareDefaultCommit`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x140009540`
- `0x14000b5d8`
- `0x14001a564`
- `0x14001fe88`

## pseudocode

```c
int __fastcall ACXactPrepareDefaultCommit(struct _IRP *a1, CTransaction *this)
{
  int v4; // eax
  int v5; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 182, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, this);
  }
  v4 = CQueueBase::Validate(this);
  v5 = v4;
  if ( v4 >= 0 )
    return CTransaction::PrepareDefaultCommit((struct _DEVICE_OBJECT **)this, a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      183,
      &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)v4,
      this);
  }
  return v5;
}

```

## disassembly

```asm
0x140009540  push    rbx
0x140009542  push    rbp
0x140009543  push    rsi
0x140009544  push    rdi
0x140009545  sub     rsp, 38h
0x140009549  mov     rdi, rdx
0x14000954c  mov     rsi, rcx
0x14000954f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009556  lea     rbp, WPP_GLOBAL_Control
0x14000955d  cmp     rcx, rbp
0x140009560  jz      short loc_140009581
0x140009562  mov     eax, [rcx+6Ch]
0x140009565  test    al, 4
0x140009567  jz      short loc_140009581
0x140009569  mov     rcx, [rcx+58h]
0x14000956d  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140009574  mov     edx, 0B6h
0x140009579  mov     r9, rdi
0x14000957c  call    WPP_SF_q
0x140009581  mov     rcx, rdi; struct CQueueBase *
0x140009584  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140009589  mov     ebx, eax
0x14000958b  test    eax, eax
0x14000958d  jns     short loc_1400095C4
0x14000958f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009596  cmp     rcx, rbp
0x140009599  jz      short loc_1400095C0
0x14000959b  mov     edx, [rcx+6Ch]
0x14000959e  test    dl, 1
0x1400095a1  jz      short loc_1400095C0
0x1400095a3  mov     rcx, [rcx+58h]
0x1400095a7  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400095ae  mov     edx, 0B7h
0x1400095b3  mov     [rsp+58h+var_38], rdi
0x1400095b8  mov     r9d, eax
0x1400095bb  call    WPP_SF_Dq
0x1400095c0  mov     eax, ebx
0x1400095c2  jmp     short loc_1400095CF
0x1400095c4  mov     rdx, rsi; struct _IRP *
0x1400095c7  mov     rcx, rdi; this
0x1400095ca  call    ?PrepareDefaultCommit@CTransaction@@QEAAJPEAU_IRP@@@Z; CTransaction::PrepareDefaultCommit(_IRP *)
0x1400095cf  add     rsp, 38h
0x1400095d3  pop     rdi
0x1400095d4  pop     rsi
0x1400095d5  pop     rbp
0x1400095d6  pop     rbx
0x1400095d7  retn
```
