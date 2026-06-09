# MoveToCallConnectedPassive

- ea: `0x1400168d0`
- end: `0x14001699c`
- name: `MoveToCallConnectedPassive`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140002030`
- `0x140002f88`
- `0x140005398`
- `0x1400168d0`
- `0x1400169a4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400168e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400168e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001697d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001697d`

## pseudocode

```c
__int64 __fastcall MoveToCallConnectedPassive(__int64 a1)
{
  KIRQL v2; // di
  __int64 v3; // r8

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 16));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
  }
  v3 = *(unsigned int *)(a1 + 24);
  if ( (_DWORD)v3 == 3 )
  {
    MoveToCallConnectedState(a1, v2);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF__guid_L(WPP_GLOBAL_Control->AttachedDevice, 68, v3, a1 + 364, *(_DWORD *)(a1 + 24));
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 16), v2);
  return DereferenceRefCount(a1 + 32);
}

```

## disassembly

```asm
0x1400168d0  push    rbx
0x1400168d2  push    rbp
0x1400168d3  push    rsi
0x1400168d4  push    rdi
0x1400168d5  sub     rsp, 38h
0x1400168d9  mov     rbx, rcx
0x1400168dc  add     rcx, 10h; SpinLock
0x1400168e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400168e7  nop     dword ptr [rax+rax+00h]
0x1400168ec  mov     dil, al
0x1400168ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400168f6  lea     rbp, WPP_GLOBAL_Control
0x1400168fd  cmp     rcx, rbp
0x140016900  jz      short loc_14001692C
0x140016902  mov     edx, [rcx+2Ch]
0x140016905  test    dl, 4
0x140016908  jz      short loc_14001692C
0x14001690a  cmp     byte ptr [rcx+29h], 3
0x14001690e  jb      short loc_14001692C
0x140016910  mov     rcx, [rcx+18h]
0x140016914  lea     r9, [rbx+16Ch]
0x14001691b  mov     edx, 43h ; 'C'
0x140016920  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016927  call    WPP_SF__guid_
0x14001692c  mov     r8d, [rbx+18h]
0x140016930  cmp     r8d, 3
0x140016934  jz      short loc_14001696B
0x140016936  mov     rcx, cs:WPP_GLOBAL_Control
0x14001693d  cmp     rcx, rbp
0x140016940  jz      short loc_140016976
0x140016942  mov     eax, [rcx+2Ch]
0x140016945  test    al, 4
0x140016947  jz      short loc_140016976
0x140016949  cmp     byte ptr [rcx+29h], 1
0x14001694d  jb      short loc_140016976
0x14001694f  mov     rcx, [rcx+18h]
0x140016953  lea     r9, [rbx+16Ch]
0x14001695a  mov     edx, 44h ; 'D'
0x14001695f  mov     [rsp+58h+var_38], r8d
0x140016964  call    WPP_SF__guid_L
0x140016969  jmp     short loc_140016976
0x14001696b  mov     dl, dil
0x14001696e  mov     rcx, rbx
0x140016971  call    MoveToCallConnectedState
0x140016976  mov     dl, dil; NewIrql
0x140016979  lea     rcx, [rbx+10h]; SpinLock
0x14001697d  call    cs:__imp_KeReleaseSpinLock
0x140016984  nop     dword ptr [rax+rax+00h]
0x140016989  lea     rcx, [rbx+20h]
0x14001698d  call    DereferenceRefCount
0x140016992  add     rsp, 38h
0x140016996  pop     rdi
0x140016997  pop     rsi
0x140016998  pop     rbp
0x140016999  pop     rbx
0x14001699a  retn
```
