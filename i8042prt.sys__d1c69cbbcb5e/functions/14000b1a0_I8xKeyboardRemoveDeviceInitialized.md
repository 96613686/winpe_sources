# I8xKeyboardRemoveDeviceInitialized

- ea: `0x14000b1a0`
- end: `0x14000b233`
- name: `I8xKeyboardRemoveDeviceInitialized`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400197e8`

## callees

- `0x14000b1a0`
- `0x14000d128`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b1b6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b1b6`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000b1cc`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14000b1cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b208`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b208`

## pseudocode

```c
void __fastcall I8xKeyboardRemoveDeviceInitialized(__int64 a1)
{
  KSPIN_LOCK *v1; // rsi
  KIRQL v3; // bp
  __int64 v4; // rdi
  int v5; // r9d

  v1 = (KSPIN_LOCK *)(a1 + 664);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 664));
  KeRemoveQueueDpc((PRKDPC)(a1 + 600));
  v4 = *(_QWORD *)(a1 + 592);
  *(_QWORD *)(a1 + 592) = 0;
  if ( v4 && (*(_BYTE *)(v4 + 68) || !_InterlockedExchange64((volatile __int64 *)(v4 + 104), 0)) )
    v4 = 0;
  KeReleaseSpinLock(v1, v3);
  if ( v4 )
    I8xCompleteSysButtonIrp((PIRP)v4, 0, -1073741738, v5);
}

```

## disassembly

```asm
0x14000b1a0  push    rbx
0x14000b1a2  push    rbp
0x14000b1a3  push    rsi
0x14000b1a4  push    rdi
0x14000b1a5  sub     rsp, 28h
0x14000b1a9  lea     rsi, [rcx+298h]
0x14000b1b0  mov     rbx, rcx
0x14000b1b3  mov     rcx, rsi; SpinLock
0x14000b1b6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b1bd  nop     dword ptr [rax+rax+00h]
0x14000b1c2  lea     rcx, [rbx+258h]; Dpc
0x14000b1c9  mov     bpl, al
0x14000b1cc  call    cs:__imp_KeRemoveQueueDpc
0x14000b1d3  nop     dword ptr [rax+rax+00h]
0x14000b1d8  mov     rdi, [rbx+250h]
0x14000b1df  mov     qword ptr [rbx+250h], 0
0x14000b1ea  test    rdi, rdi
0x14000b1ed  jz      short loc_14000B202
0x14000b1ef  cmp     byte ptr [rdi+44h], 0
0x14000b1f3  jnz     short loc_14000B200
0x14000b1f5  xor     eax, eax
0x14000b1f7  xchg    rax, [rdi+68h]
0x14000b1fb  test    rax, rax
0x14000b1fe  jnz     short loc_14000B202
0x14000b200  xor     edi, edi
0x14000b202  mov     dl, bpl; NewIrql
0x14000b205  mov     rcx, rsi; SpinLock
0x14000b208  call    cs:__imp_KeReleaseSpinLock
0x14000b20f  nop     dword ptr [rax+rax+00h]
0x14000b214  test    rdi, rdi
0x14000b217  jz      short loc_14000B229
0x14000b219  xor     edx, edx
0x14000b21b  mov     r8d, 0C0000056h
0x14000b221  mov     rcx, rdi; Irp
0x14000b224  call    I8xCompleteSysButtonIrp
0x14000b229  add     rsp, 28h
0x14000b22d  pop     rdi
0x14000b22e  pop     rsi
0x14000b22f  pop     rbp
0x14000b230  pop     rbx
0x14000b231  retn
```
