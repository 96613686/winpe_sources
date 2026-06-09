# ACXactCommit2

- ea: `0x140009258`
- end: `0x1400092f1`
- name: `ACXactCommit2`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x140009258`
- `0x14000b5d8`
- `0x14001a564`
- `0x14001f714`

## pseudocode

```c
int __fastcall ACXactCommit2(struct _IRP *a1, CTransaction *this)
{
  int v4; // eax
  int v5; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 172, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, this);
  }
  v4 = CQueueBase::Validate(this);
  v5 = v4;
  if ( v4 >= 0 )
    return CTransaction::Commit2(this, a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      173,
      &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)v4,
      this);
  }
  return v5;
}

```

## disassembly

```asm
0x140009258  push    rbx
0x14000925a  push    rbp
0x14000925b  push    rsi
0x14000925c  push    rdi
0x14000925d  sub     rsp, 38h
0x140009261  mov     rdi, rdx
0x140009264  mov     rsi, rcx
0x140009267  mov     rcx, cs:WPP_GLOBAL_Control
0x14000926e  lea     rbp, WPP_GLOBAL_Control
0x140009275  cmp     rcx, rbp
0x140009278  jz      short loc_140009299
0x14000927a  mov     eax, [rcx+6Ch]
0x14000927d  test    al, 4
0x14000927f  jz      short loc_140009299
0x140009281  mov     rcx, [rcx+58h]
0x140009285  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000928c  mov     edx, 0ACh
0x140009291  mov     r9, rdi
0x140009294  call    WPP_SF_q
0x140009299  mov     rcx, rdi; struct CQueueBase *
0x14000929c  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x1400092a1  mov     ebx, eax
0x1400092a3  test    eax, eax
0x1400092a5  jns     short loc_1400092DC
0x1400092a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400092ae  cmp     rcx, rbp
0x1400092b1  jz      short loc_1400092D8
0x1400092b3  mov     edx, [rcx+6Ch]
0x1400092b6  test    dl, 1
0x1400092b9  jz      short loc_1400092D8
0x1400092bb  mov     rcx, [rcx+58h]
0x1400092bf  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400092c6  mov     edx, 0ADh
0x1400092cb  mov     [rsp+58h+var_38], rdi
0x1400092d0  mov     r9d, eax
0x1400092d3  call    WPP_SF_Dq
0x1400092d8  mov     eax, ebx
0x1400092da  jmp     short loc_1400092E7
0x1400092dc  mov     rdx, rsi; struct _IRP *
0x1400092df  mov     rcx, rdi; this
0x1400092e2  call    ?Commit2@CTransaction@@QEAAJPEAU_IRP@@@Z; CTransaction::Commit2(_IRP *)
0x1400092e7  add     rsp, 38h
0x1400092eb  pop     rdi
0x1400092ec  pop     rsi
0x1400092ed  pop     rbp
0x1400092ee  pop     rbx
0x1400092ef  retn
```
