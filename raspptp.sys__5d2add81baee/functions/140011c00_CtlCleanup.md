# CtlCleanup

- ea: `0x140011c00`
- end: `0x140011cfd`
- name: `CtlCleanup`
- size: `253`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140011d04`
- `0x1400122b0`
- `0x140012798`
- `0x140012ac0`
- `0x140012cf4`
- `0x1400137ac`
- `0x140013954`
- `0x140014f40`

## callees

- `0x1400028f0`
- `0x140003e08`
- `0x140007710`
- `0x140011c00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140011ce0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011ce0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011c53`

## pseudocode

```c
void __fastcall CtlCleanup(__int64 a1, char a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Au,
      (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
  }
  if ( !a2 )
    *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  if ( !*(_BYTE *)(a1 + 112) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    *(_BYTE *)(a1 + 112) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x1Bu,
        (__int64)WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
    }
    if ( (unsigned int)ScheduleWorkItem(CtlpCleanup, a1, 0, 0) )
    {
      *(_BYTE *)(a1 + 112) = 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(__int64))(a1 + 24))(a1);
    }
  }
  if ( !a2 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
}

```

## disassembly

```asm
0x140011c00  mov     [rsp+arg_0], rbx
0x140011c05  mov     [rsp+arg_10], rsi
0x140011c0a  push    rdi
0x140011c0b  sub     rsp, 20h
0x140011c0f  mov     dil, dl
0x140011c12  mov     rbx, rcx
0x140011c15  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c1c  lea     rsi, WPP_GLOBAL_Control
0x140011c23  cmp     rcx, rsi
0x140011c26  jz      short loc_140011C4A
0x140011c28  mov     eax, [rcx+2Ch]
0x140011c2b  test    al, 8
0x140011c2d  jz      short loc_140011C4A
0x140011c2f  cmp     byte ptr [rcx+29h], 2
0x140011c33  jb      short loc_140011C4A
0x140011c35  mov     rcx, [rcx+18h]
0x140011c39  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140011c40  mov     edx, 1Ah
0x140011c45  call    WPP_SF_
0x140011c4a  test    dil, dil
0x140011c4d  jnz     short loc_140011C62
0x140011c4f  lea     rcx, [rbx+60h]; SpinLock
0x140011c53  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011c5a  nop     dword ptr [rax+rax+00h]
0x140011c5f  mov     [rbx+68h], al
0x140011c62  cmp     byte ptr [rbx+70h], 0
0x140011c66  jnz     short loc_140011CD4
0x140011c68  lock inc dword ptr [rbx+10h]
0x140011c6c  mov     byte ptr [rbx+70h], 1
0x140011c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c77  cmp     rcx, rsi
0x140011c7a  jz      short loc_140011C9E
0x140011c7c  mov     eax, [rcx+2Ch]
0x140011c7f  test    al, 8
0x140011c81  jz      short loc_140011C9E
0x140011c83  cmp     byte ptr [rcx+29h], 2
0x140011c87  jb      short loc_140011C9E
0x140011c89  mov     rcx, [rcx+18h]
0x140011c8d  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140011c94  mov     edx, 1Bh
0x140011c99  call    WPP_SF_
0x140011c9e  xor     r9d, r9d
0x140011ca1  lea     rcx, CtlpCleanup
0x140011ca8  xor     r8d, r8d
0x140011cab  mov     rdx, rbx
0x140011cae  call    ScheduleWorkItem
0x140011cb3  test    eax, eax
0x140011cb5  jz      short loc_140011CD4
0x140011cb7  mov     byte ptr [rbx+70h], 0
0x140011cbb  or      eax, 0FFFFFFFFh
0x140011cbe  lock xadd [rbx+10h], eax
0x140011cc3  cmp     eax, 1
0x140011cc6  jnz     short loc_140011CD4
0x140011cc8  mov     rax, [rbx+18h]
0x140011ccc  mov     rcx, rbx
0x140011ccf  call    _guard_dispatch_icall
0x140011cd4  test    dil, dil
0x140011cd7  jnz     short loc_140011CEC
0x140011cd9  mov     dl, [rbx+68h]; NewIrql
0x140011cdc  lea     rcx, [rbx+60h]; SpinLock
0x140011ce0  call    cs:__imp_KeReleaseSpinLock
0x140011ce7  nop     dword ptr [rax+rax+00h]
0x140011cec  mov     rbx, [rsp+28h+arg_0]
0x140011cf1  mov     rsi, [rsp+28h+arg_10]
0x140011cf6  add     rsp, 20h
0x140011cfa  pop     rdi
0x140011cfb  retn
```
