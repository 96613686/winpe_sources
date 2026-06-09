# QueuePacketForSend

- ea: `0x140019860`
- end: `0x140019a7b`
- name: `QueuePacketForSend`
- size: `539`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013350`

## callees

- `0x140002f88`
- `0x140005ef0`
- `0x140019860`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019877`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019877`
- `ntoskrnl!IofCompleteRequest` at `0x140019921`
- `ntoskrnl!IofCompleteRequest` at `0x140019921`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019903`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400199d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019a6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019903`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400199d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019a6a`

## pseudocode

```c
void __fastcall QueuePacketForSend(__int64 a1, __int64 a2)
{
  KIRQL v4; // bp
  bool v5; // zf
  __int64 v6; // rdi

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  if ( *(_QWORD *)(a1 + 96) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, a1 + 484);
    }
    if ( *(_BYTE *)(a2 + 8) )
    {
      *(_QWORD *)a2 = *(_QWORD *)(a1 + 96);
      *(_QWORD *)(a1 + 96) = a2;
    }
    else
    {
      **(_QWORD **)(a1 + 104) = a2;
      *(_QWORD *)(a1 + 104) = a2;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v4);
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 80) == 0;
    *(_QWORD *)(a1 + 96) = a2;
    if ( v5 )
    {
      *(_BYTE *)(a1 + 88) = 1;
      v6 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, a1 + 484);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids, a1 + 484);
      }
      v6 = *(_QWORD *)(a1 + 80);
      *(_QWORD *)(a1 + 80) = 0;
      if ( _InterlockedExchange64((volatile __int64 *)(v6 + 104), 0) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(__int64))(a1 + 8))(a1);
      }
      else
      {
        *(_BYTE *)(a1 + 88) = 1;
        v6 = 0;
      }
    }
    *(_QWORD *)(a1 + 104) = a2;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v4);
    if ( v6 )
    {
      *(_DWORD *)(v6 + 48) = 0;
      *(_QWORD *)(v6 + 56) = 0;
      IofCompleteRequest((PIRP)v6, 2);
    }
  }
}

```

## disassembly

```asm
0x140019860  mov     [rsp+arg_10], rbx
0x140019865  push    rbp
0x140019866  push    rsi
0x140019867  push    r14
0x140019869  sub     rsp, 20h
0x14001986d  mov     rbx, rcx
0x140019870  mov     r14, rdx
0x140019873  add     rcx, 20h ; ' '; SpinLock
0x140019877  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001987e  nop     dword ptr [rax+rax+00h]
0x140019883  cmp     qword ptr [rbx+60h], 0
0x140019888  movzx   ebp, al
0x14001988b  jnz     loc_140019993
0x140019891  cmp     qword ptr [rbx+50h], 0
0x140019896  mov     [rsp+38h+arg_0], rdi
0x14001989b  mov     [rsp+38h+arg_8], r15
0x1400198a0  mov     [rbx+60h], r14
0x1400198a4  jz      loc_140019946
0x1400198aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400198b1  lea     rax, WPP_GLOBAL_Control
0x1400198b8  cmp     rcx, rax
0x1400198bb  jz      short loc_1400198CA
0x1400198bd  test    dword ptr [rcx+2Ch], 100h
0x1400198c4  jnz     loc_1400199F8
0x1400198ca  mov     rdi, [rbx+50h]
0x1400198ce  xor     r15d, r15d
0x1400198d1  mov     eax, r15d
0x1400198d4  mov     [rbx+50h], r15
0x1400198d8  xchg    rax, [rdi+68h]
0x1400198dc  test    rax, rax
0x1400198df  jz      loc_1400199EC
0x1400198e5  mov     eax, 0FFFFFFFFh
0x1400198ea  lock xadd [rbx], eax
0x1400198ee  cmp     eax, 1
0x1400198f1  jz      loc_140019A23
0x1400198f7  movzx   edx, bpl; NewIrql
0x1400198fb  mov     [rbx+68h], r14
0x1400198ff  lea     rcx, [rbx+20h]; SpinLock
0x140019903  call    cs:__imp_KeReleaseSpinLock
0x14001990a  nop     dword ptr [rax+rax+00h]
0x14001990f  test    rdi, rdi
0x140019912  jz      short loc_14001992D
0x140019914  mov     dl, 2; PriorityBoost
0x140019916  mov     [rdi+30h], r15d
0x14001991a  mov     rcx, rdi; Irp
0x14001991d  mov     [rdi+38h], r15
0x140019921  call    cs:__imp_IofCompleteRequest
0x140019928  nop     dword ptr [rax+rax+00h]
0x14001992d  mov     r15, [rsp+38h+arg_8]
0x140019932  mov     rdi, [rsp+38h+arg_0]
0x140019937  mov     rbx, [rsp+38h+arg_10]
0x14001993c  add     rsp, 20h
0x140019940  pop     r14
0x140019942  pop     rsi
0x140019943  pop     rbp
0x140019944  retn
0x140019946  xor     r15d, r15d
0x140019949  mov     byte ptr [rbx+58h], 1
0x14001994d  mov     edi, r15d
0x140019950  mov     rcx, cs:WPP_GLOBAL_Control
0x140019957  lea     rax, WPP_GLOBAL_Control
0x14001995e  cmp     rcx, rax
0x140019961  jz      short loc_1400198F7
0x140019963  test    dword ptr [rcx+2Ch], 100h
0x14001996a  jz      short loc_1400198F7
0x14001996c  cmp     byte ptr [rcx+29h], 4
0x140019970  jb      short loc_1400198F7
0x140019972  mov     rcx, [rcx+18h]
0x140019976  lea     r9, [rbx+1E4h]
0x14001997d  mov     edx, 4Ch ; 'L'
0x140019982  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140019989  call    WPP_SF__guid_
0x14001998e  jmp     loc_1400198F7
0x140019993  mov     rcx, cs:WPP_GLOBAL_Control
0x14001999a  lea     rax, WPP_GLOBAL_Control
0x1400199a1  cmp     rcx, rax
0x1400199a4  jz      short loc_1400199B3
0x1400199a6  test    dword ptr [rcx+2Ch], 100h
0x1400199ad  jnz     loc_140019A34
0x1400199b3  cmp     byte ptr [r14+8], 0
0x1400199b8  lea     rcx, [rbx+20h]; SpinLock
0x1400199bc  movzx   edx, bpl; NewIrql
0x1400199c0  jnz     loc_140019A5F
0x1400199c6  mov     rax, [rbx+68h]
0x1400199ca  mov     [rax], r14
0x1400199cd  mov     [rbx+68h], r14
0x1400199d1  call    cs:__imp_KeReleaseSpinLock
0x1400199d8  nop     dword ptr [rax+rax+00h]
0x1400199dd  mov     rbx, [rsp+38h+arg_10]
0x1400199e2  add     rsp, 20h
0x1400199e6  pop     r14
0x1400199e8  pop     rsi
0x1400199e9  pop     rbp
0x1400199ea  retn
0x1400199ec  mov     byte ptr [rbx+58h], 1
0x1400199f0  mov     rdi, r15
0x1400199f3  jmp     loc_1400198F7
0x1400199f8  cmp     byte ptr [rcx+29h], 4
0x1400199fc  jb      loc_1400198CA
0x140019a02  mov     rcx, [rcx+18h]
0x140019a06  lea     r9, [rbx+1E4h]
0x140019a0d  mov     edx, 4Bh ; 'K'
0x140019a12  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140019a19  call    WPP_SF__guid_
0x140019a1e  jmp     loc_1400198CA
0x140019a23  mov     rax, [rbx+8]
0x140019a27  mov     rcx, rbx
0x140019a2a  call    _guard_dispatch_icall
0x140019a2f  jmp     loc_1400198F7
0x140019a34  cmp     byte ptr [rcx+29h], 4
0x140019a38  jb      loc_1400199B3
0x140019a3e  mov     rcx, [rcx+18h]
0x140019a42  lea     r9, [rbx+1E4h]
0x140019a49  mov     edx, 4Dh ; 'M'
0x140019a4e  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x140019a55  call    WPP_SF__guid_
0x140019a5a  jmp     loc_1400199B3
0x140019a5f  mov     rax, [rbx+60h]
0x140019a63  mov     [r14], rax
0x140019a66  mov     [rbx+60h], r14
0x140019a6a  call    cs:__imp_KeReleaseSpinLock
0x140019a71  nop     dword ptr [rax+rax+00h]
0x140019a76  jmp     loc_140019937
```
