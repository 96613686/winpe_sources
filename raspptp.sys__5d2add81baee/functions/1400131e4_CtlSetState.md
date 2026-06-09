# CtlSetState

- ea: `0x1400131e4`
- end: `0x140013289`
- name: `CtlSetState`
- size: `165`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140011d04`
- `0x1400122b0`
- `0x1400125e0`
- `0x140012798`
- `0x140012ac0`
- `0x1400137ac`
- `0x140013954`
- `0x140014f40`
- `0x140015338`
- `0x1400154b8`

## callees

- `0x140004b98`
- `0x140005144`
- `0x1400131e4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140013271`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013271`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001324c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001324c`

## pseudocode

```c
__int64 __fastcall CtlSetState(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rbx
  unsigned int v11; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    szCtlState(a2);
    v7 = szCtlState(*(unsigned int *)(a1 + 48));
    WPP_SF_qss(*(_QWORD *)(v8 + 24), v9, v8, a1, v7, v9);
  }
  if ( !a4 )
  {
    v10 = *(_QWORD *)(a1 + 40);
    *(_BYTE *)(v10 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 8));
  }
  v11 = *(_DWORD *)(a1 + 48);
  *(_DWORD *)(a1 + 48) = a2;
  if ( !a4 )
    KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 40) + 8LL), *(_BYTE *)(*(_QWORD *)(a1 + 40) + 16LL));
  return v11;
}

```

## disassembly

```asm
0x1400131e4  push    rbx
0x1400131e6  push    rbp
0x1400131e7  push    rsi
0x1400131e8  push    rdi
0x1400131e9  sub     rsp, 38h
0x1400131ed  mov     sil, r9b
0x1400131f0  mov     ebp, edx
0x1400131f2  mov     rdi, rcx
0x1400131f5  mov     r8, cs:WPP_GLOBAL_Control
0x1400131fc  lea     rax, WPP_GLOBAL_Control
0x140013203  cmp     r8, rax
0x140013206  jz      short loc_14001323F
0x140013208  mov     eax, [r8+2Ch]
0x14001320c  test    al, 8
0x14001320e  jz      short loc_14001323F
0x140013210  cmp     byte ptr [r8+29h], 2
0x140013215  jb      short loc_14001323F
0x140013217  mov     ecx, edx
0x140013219  call    szCtlState
0x14001321e  mov     ecx, [rdi+30h]
0x140013221  mov     rdx, rax
0x140013224  call    szCtlState
0x140013229  mov     rcx, [r8+18h]
0x14001322d  mov     r9, rdi
0x140013230  mov     [rsp+58h+var_30], rdx
0x140013235  mov     [rsp+58h+var_38], rax
0x14001323a  call    WPP_SF_qss
0x14001323f  test    sil, sil
0x140013242  jnz     short loc_14001325B
0x140013244  mov     rbx, [rdi+28h]
0x140013248  lea     rcx, [rbx+8]; SpinLock
0x14001324c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013253  nop     dword ptr [rax+rax+00h]
0x140013258  mov     [rbx+10h], al
0x14001325b  mov     ebx, [rdi+30h]
0x14001325e  mov     [rdi+30h], ebp
0x140013261  test    sil, sil
0x140013264  jnz     short loc_14001327D
0x140013266  mov     rdx, [rdi+28h]
0x14001326a  lea     rcx, [rdx+8]; SpinLock
0x14001326e  mov     dl, [rdx+10h]; NewIrql
0x140013271  call    cs:__imp_KeReleaseSpinLock
0x140013278  nop     dword ptr [rax+rax+00h]
0x14001327d  mov     eax, ebx
0x14001327f  add     rsp, 38h
0x140013283  pop     rdi
0x140013284  pop     rsi
0x140013285  pop     rbp
0x140013286  pop     rbx
0x140013287  retn
```
