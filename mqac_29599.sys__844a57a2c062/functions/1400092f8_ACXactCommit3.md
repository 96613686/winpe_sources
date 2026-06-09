# ACXactCommit3

- ea: `0x1400092f8`
- end: `0x140009398`
- name: `ACXactCommit3`
- size: `160`
- prototype: `__int64 __fastcall(struct CQueueBase *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x1400092f8`
- `0x14000b5d8`
- `0x14001a564`
- `0x14001f8d4`

## pseudocode

```c
__int64 __fastcall ACXactCommit3(struct CQueueBase *a1)
{
  int v2; // eax
  unsigned int v3; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 174, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
  }
  v2 = CQueueBase::Validate(a1);
  v3 = v2;
  if ( v2 >= 0 )
    return CTransaction::Commit3(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      175,
      &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)v2,
      a1);
  }
  return v3;
}

```

## disassembly

```asm
0x1400092f8  mov     [rsp+arg_0], rbx
0x1400092fd  mov     [rsp+arg_8], rsi
0x140009302  push    rdi
0x140009303  sub     rsp, 30h
0x140009307  mov     rbx, rcx
0x14000930a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009311  lea     rsi, WPP_GLOBAL_Control
0x140009318  cmp     rcx, rsi
0x14000931b  jz      short loc_14000933C
0x14000931d  mov     eax, [rcx+6Ch]
0x140009320  test    al, 4
0x140009322  jz      short loc_14000933C
0x140009324  mov     rcx, [rcx+58h]
0x140009328  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000932f  mov     edx, 0AEh
0x140009334  mov     r9, rbx
0x140009337  call    WPP_SF_q
0x14000933c  mov     rcx, rbx; struct CQueueBase *
0x14000933f  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140009344  mov     edi, eax
0x140009346  test    eax, eax
0x140009348  jns     short loc_14000937F
0x14000934a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009351  cmp     rcx, rsi
0x140009354  jz      short loc_14000937B
0x140009356  mov     edx, [rcx+6Ch]
0x140009359  test    dl, 1
0x14000935c  jz      short loc_14000937B
0x14000935e  mov     rcx, [rcx+58h]
0x140009362  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140009369  mov     edx, 0AFh
0x14000936e  mov     [rsp+38h+var_18], rbx
0x140009373  mov     r9d, eax
0x140009376  call    WPP_SF_Dq
0x14000937b  mov     eax, edi
0x14000937d  jmp     short loc_140009387
0x14000937f  mov     rcx, rbx; this
0x140009382  call    ?Commit3@CTransaction@@QEAAJXZ; CTransaction::Commit3(void)
0x140009387  mov     rbx, [rsp+38h+arg_0]
0x14000938c  mov     rsi, [rsp+38h+arg_8]
0x140009391  add     rsp, 30h
0x140009395  pop     rdi
0x140009396  retn
```
