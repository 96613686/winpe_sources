# CtlAllocPacket

- ea: `0x140011b90`
- end: `0x140011bf9`
- name: `CtlAllocPacket`
- size: `105`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f224`
- `0x14000f588`
- `0x14000fbac`
- `0x1400102fc`
- `0x140010c14`
- `0x1400114c8`
- `0x140012798`
- `0x1400138c0`
- `0x140013954`
- `0x140015338`
- `0x1400154b8`
- `0x1400162f0`

## callees

- `0x140011b90`
- `0x140013290`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140011bd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011bd5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011bb2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011bb2`

## pseudocode

```c
__int64 __fastcall CtlAllocPacket(__int64 a1, unsigned int a2)
{
  __int64 v2; // rsi

  v2 = 0;
  if ( !a1
    || *(_DWORD *)(a1 + 32) != 1414550608
    || (*(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96)),
        v2 = CtlpAllocPacketLocked(a1, a2),
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104)),
        !v2) )
  {
    ++dword_14000B478;
  }
  return v2;
}

```

## disassembly

```asm
0x140011b90  push    rbx
0x140011b92  push    rbp
0x140011b93  push    rsi
0x140011b94  push    rdi
0x140011b95  sub     rsp, 28h
0x140011b99  xor     esi, esi
0x140011b9b  mov     ebp, edx
0x140011b9d  mov     rdi, rcx
0x140011ba0  test    rcx, rcx
0x140011ba3  jz      short loc_140011BE6
0x140011ba5  cmp     dword ptr [rcx+20h], 54505450h
0x140011bac  jnz     short loc_140011BE6
0x140011bae  add     rcx, 60h ; '`'; SpinLock
0x140011bb2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011bb9  nop     dword ptr [rax+rax+00h]
0x140011bbe  mov     edx, ebp
0x140011bc0  mov     rcx, rdi
0x140011bc3  mov     [rdi+68h], al
0x140011bc6  call    CtlpAllocPacketLocked
0x140011bcb  mov     dl, [rdi+68h]; NewIrql
0x140011bce  lea     rcx, [rdi+60h]; SpinLock
0x140011bd2  mov     rsi, rax
0x140011bd5  call    cs:__imp_KeReleaseSpinLock
0x140011bdc  nop     dword ptr [rax+rax+00h]
0x140011be1  test    rsi, rsi
0x140011be4  jnz     short loc_140011BEC
0x140011be6  inc     cs:dword_14000B478
0x140011bec  mov     rax, rsi
0x140011bef  add     rsp, 28h
0x140011bf3  pop     rdi
0x140011bf4  pop     rsi
0x140011bf5  pop     rbp
0x140011bf6  pop     rbx
0x140011bf7  retn
```
