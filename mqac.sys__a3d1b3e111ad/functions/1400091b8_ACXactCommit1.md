# ACXactCommit1

- ea: `0x1400091b8`
- end: `0x140009251`
- name: `ACXactCommit1`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x1400091b8`
- `0x14000b5d8`
- `0x14001a564`
- `0x14001f56c`

## pseudocode

```c
int __fastcall ACXactCommit1(struct _IRP *a1, CTransaction *this)
{
  int v4; // eax
  int v5; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 170, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, this);
  }
  v4 = CQueueBase::Validate(this);
  v5 = v4;
  if ( v4 >= 0 )
    return CTransaction::Commit1(this, a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      171,
      WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)v4,
      this);
  }
  return v5;
}

```

## disassembly

```asm
0x1400091b8  push    rbx
0x1400091ba  push    rbp
0x1400091bb  push    rsi
0x1400091bc  push    rdi
0x1400091bd  sub     rsp, 38h
0x1400091c1  mov     rdi, rdx
0x1400091c4  mov     rsi, rcx
0x1400091c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400091ce  lea     rbp, WPP_GLOBAL_Control
0x1400091d5  cmp     rcx, rbp
0x1400091d8  jz      short loc_1400091F9
0x1400091da  mov     eax, [rcx+6Ch]
0x1400091dd  test    al, 4
0x1400091df  jz      short loc_1400091F9
0x1400091e1  mov     rcx, [rcx+58h]
0x1400091e5  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400091ec  mov     edx, 0AAh
0x1400091f1  mov     r9, rdi
0x1400091f4  call    WPP_SF_q
0x1400091f9  mov     rcx, rdi; struct CQueueBase *
0x1400091fc  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140009201  mov     ebx, eax
0x140009203  test    eax, eax
0x140009205  jns     short loc_14000923C
0x140009207  mov     rcx, cs:WPP_GLOBAL_Control
0x14000920e  cmp     rcx, rbp
0x140009211  jz      short loc_140009238
0x140009213  mov     edx, [rcx+6Ch]
0x140009216  test    dl, 1
0x140009219  jz      short loc_140009238
0x14000921b  mov     rcx, [rcx+58h]
0x14000921f  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140009226  mov     edx, 0ABh
0x14000922b  mov     [rsp+58h+var_38], rdi
0x140009230  mov     r9d, eax
0x140009233  call    WPP_SF_Dq
0x140009238  mov     eax, ebx
0x14000923a  jmp     short loc_140009247
0x14000923c  mov     rdx, rsi; struct _IRP *
0x14000923f  mov     rcx, rdi; this
0x140009242  call    ?Commit1@CTransaction@@QEAAJPEAU_IRP@@@Z; CTransaction::Commit1(_IRP *)
0x140009247  add     rsp, 38h
0x14000924b  pop     rdi
0x14000924c  pop     rsi
0x14000924d  pop     rbp
0x14000924e  pop     rbx
0x14000924f  retn
```
