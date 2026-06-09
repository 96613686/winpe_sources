# PrRemoveCallFromBinding

- ea: `0x140015aec`
- end: `0x140015ba7`
- name: `PrRemoveCallFromBinding`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400035b8`
- `0x140016534`

## callees

- `0x14000110c`
- `0x14000400c`
- `0x140015aec`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015b5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015b5b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015b34`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015b34`

## pseudocode

```c
__int64 __fastcall PrRemoveCallFromBinding(__int64 a1, __int64 a2)
{
  KIRQL v4; // al
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 56));
  *(_QWORD *)(a2 + 728) = 0;
  *(_BYTE *)(a2 + 64) = v4;
  *(_DWORD *)(a2 + 120) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), v4);
  result = DereferenceBinding(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140015aec  push    rbx
0x140015aee  push    rbp
0x140015aef  push    rsi
0x140015af0  push    rdi
0x140015af1  sub     rsp, 28h
0x140015af5  mov     rdi, rdx
0x140015af8  mov     rsi, rcx
0x140015afb  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b02  lea     rbp, WPP_GLOBAL_Control
0x140015b09  cmp     rcx, rbp
0x140015b0c  jz      short loc_140015B30
0x140015b0e  mov     eax, [rcx+2Ch]
0x140015b11  test    al, 4
0x140015b13  jz      short loc_140015B30
0x140015b15  cmp     byte ptr [rcx+29h], 3
0x140015b19  jb      short loc_140015B30
0x140015b1b  mov     rcx, [rcx+18h]
0x140015b1f  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140015b26  mov     edx, 4Bh ; 'K'
0x140015b2b  call    WPP_SF_
0x140015b30  lea     rcx, [rdi+38h]; SpinLock
0x140015b34  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015b3b  nop     dword ptr [rax+rax+00h]
0x140015b40  lea     rcx, [rdi+38h]; SpinLock
0x140015b44  mov     qword ptr [rdi+2D8h], 0
0x140015b4f  mov     dl, al; NewIrql
0x140015b51  mov     [rdi+40h], al
0x140015b54  mov     dword ptr [rdi+78h], 0
0x140015b5b  call    cs:__imp_KeReleaseSpinLock
0x140015b62  nop     dword ptr [rax+rax+00h]
0x140015b67  mov     rcx, rsi
0x140015b6a  call    DereferenceBinding
0x140015b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b76  cmp     rcx, rbp
0x140015b79  jz      short loc_140015B9D
0x140015b7b  mov     eax, [rcx+2Ch]
0x140015b7e  test    al, 4
0x140015b80  jz      short loc_140015B9D
0x140015b82  cmp     byte ptr [rcx+29h], 3
0x140015b86  jb      short loc_140015B9D
0x140015b88  mov     rcx, [rcx+18h]
0x140015b8c  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140015b93  mov     edx, 4Ch ; 'L'
0x140015b98  call    WPP_SF_
0x140015b9d  add     rsp, 28h
0x140015ba1  pop     rdi
0x140015ba2  pop     rsi
0x140015ba3  pop     rbp
0x140015ba4  pop     rbx
0x140015ba5  retn
```
