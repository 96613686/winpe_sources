# CallConnectToCtl

- ea: `0x14000f008`
- end: `0x14000f0cf`
- name: `CallConnectToCtl`
- size: `199`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f588`
- `0x14000fbac`
- `0x140011d04`

## callees

- `0x14000f008`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000f098`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f0b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f098`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f0b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f02c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f043`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f02c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f043`

## pseudocode

```c
char __fastcall CallConnectToCtl(__int64 a1, __int64 a2, char a3)
{
  char v3; // bp
  __int64 v7; // rbx
  _QWORD *v8; // rdx

  v3 = 0;
  if ( !a3 )
    *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  v7 = *(_QWORD *)(a1 + 56);
  *(_BYTE *)(v7 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 8));
  if ( !*(_QWORD *)(a1 + 80) )
  {
    *(_QWORD *)(a1 + 80) = a2;
    v8 = *(_QWORD **)(a2 + 64);
    if ( *v8 != a2 + 56 )
      __fastfail(3u);
    v3 = 1;
    *(_QWORD *)(a1 + 16) = a2 + 56;
    *(_QWORD *)(a1 + 24) = v8;
    *v8 = a1 + 16;
    *(_QWORD *)(a2 + 64) = a1 + 16;
    _InterlockedAdd((volatile signed __int32 *)(a2 + 16), 1u);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 56) + 8LL), *(_BYTE *)(*(_QWORD *)(a1 + 56) + 16LL));
  if ( !a3 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
  return v3;
}

```

## disassembly

```asm
0x14000f008  push    rbx
0x14000f00a  push    rbp
0x14000f00b  push    rsi
0x14000f00c  push    rdi
0x14000f00d  push    r12
0x14000f00f  push    r14
0x14000f011  push    r15
0x14000f013  sub     rsp, 20h
0x14000f017  xor     bpl, bpl
0x14000f01a  mov     r12b, r8b
0x14000f01d  mov     r14, rdx
0x14000f020  mov     rdi, rcx
0x14000f023  test    r8b, r8b
0x14000f026  jnz     short loc_14000F03B
0x14000f028  add     rcx, 60h ; '`'; SpinLock
0x14000f02c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f033  nop     dword ptr [rax+rax+00h]
0x14000f038  mov     [rdi+68h], al
0x14000f03b  mov     rbx, [rdi+38h]
0x14000f03f  lea     rcx, [rbx+8]; SpinLock
0x14000f043  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f04a  nop     dword ptr [rax+rax+00h]
0x14000f04f  mov     [rbx+10h], al
0x14000f052  cmp     qword ptr [rdi+50h], 0
0x14000f057  jnz     short loc_14000F08D
0x14000f059  lea     rcx, [r14+38h]
0x14000f05d  mov     [rdi+50h], r14
0x14000f061  mov     rdx, [rcx+8]
0x14000f065  cmp     [rdx], rcx
0x14000f068  jz      short loc_14000F071
0x14000f06a  mov     ecx, 3
0x14000f06f  int     29h; Win8: RtlFailFast(ecx)
0x14000f071  lea     rax, [rdi+10h]
0x14000f075  mov     ebp, 1
0x14000f07a  mov     [rax], rcx
0x14000f07d  mov     [rax+8], rdx
0x14000f081  mov     [rdx], rax
0x14000f084  mov     [rcx+8], rax
0x14000f088  lock add [r14+10h], ebp
0x14000f08d  mov     rdx, [rdi+38h]
0x14000f091  lea     rcx, [rdx+8]; SpinLock
0x14000f095  mov     dl, [rdx+10h]; NewIrql
0x14000f098  call    cs:__imp_KeReleaseSpinLock
0x14000f09f  nop     dword ptr [rax+rax+00h]
0x14000f0a4  test    r12b, r12b
0x14000f0a7  jnz     short loc_14000F0BC
0x14000f0a9  mov     dl, [rdi+68h]; NewIrql
0x14000f0ac  lea     rcx, [rdi+60h]; SpinLock
0x14000f0b0  call    cs:__imp_KeReleaseSpinLock
0x14000f0b7  nop     dword ptr [rax+rax+00h]
0x14000f0bc  mov     al, bpl
0x14000f0bf  add     rsp, 20h
0x14000f0c3  pop     r15
0x14000f0c5  pop     r14
0x14000f0c7  pop     r12
0x14000f0c9  pop     rdi
0x14000f0ca  pop     rsi
0x14000f0cb  pop     rbp
0x14000f0cc  pop     rbx
0x14000f0cd  retn
```
