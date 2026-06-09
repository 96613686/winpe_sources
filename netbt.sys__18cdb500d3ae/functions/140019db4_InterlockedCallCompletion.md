# InterlockedCallCompletion

- ea: `0x140019db4`
- end: `0x140019e41`
- name: `InterlockedCallCompletion`
- size: `141`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c570`
- `0x140019870`
- `0x140019a10`

## callees

- `0x140019db4`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019dcf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019dcf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e01`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e2e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e01`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019e2e`

## pseudocode

```c
__int64 __fastcall InterlockedCallCompletion(_QWORD *a1, unsigned int a2)
{
  KIRQL v4; // al
  void (__fastcall *v5)(_QWORD, _QWORD); // rdi

  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v5 = (void (__fastcall *)(_QWORD, _QWORD))a1[9];
  a1[9] = 0;
  if ( v5 )
  {
    *(_QWORD *)(a1[10] + 112LL) = 0;
    KeReleaseSpinLock(&SpinLock, v4);
    v5(a1[8], a2);
    return 0;
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v4);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x140019db4  mov     [rsp+arg_0], rbx
0x140019db9  mov     [rsp+arg_8], rsi
0x140019dbe  push    rdi
0x140019dbf  sub     rsp, 20h
0x140019dc3  mov     rbx, rcx
0x140019dc6  mov     esi, edx
0x140019dc8  lea     rcx, SpinLock; SpinLock
0x140019dcf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019dd6  nop     dword ptr [rax+rax+00h]
0x140019ddb  mov     rdi, [rbx+48h]
0x140019ddf  lea     rcx, SpinLock; SpinLock
0x140019de6  mov     qword ptr [rbx+48h], 0
0x140019dee  mov     dl, al; NewIrql
0x140019df0  test    rdi, rdi
0x140019df3  jz      short loc_140019E2E
0x140019df5  mov     r8, [rbx+50h]
0x140019df9  mov     qword ptr [r8+70h], 0
0x140019e01  call    cs:__imp_KeReleaseSpinLock
0x140019e08  nop     dword ptr [rax+rax+00h]
0x140019e0d  mov     rcx, [rbx+40h]
0x140019e11  mov     edx, esi
0x140019e13  mov     rax, rdi
0x140019e16  call    _guard_dispatch_icall
0x140019e1b  xor     eax, eax
0x140019e1d  mov     rbx, [rsp+28h+arg_0]
0x140019e22  mov     rsi, [rsp+28h+arg_8]
0x140019e27  add     rsp, 20h
0x140019e2b  pop     rdi
0x140019e2c  retn
0x140019e2e  call    cs:__imp_KeReleaseSpinLock
0x140019e35  nop     dword ptr [rax+rax+00h]
0x140019e3a  mov     eax, 0C0000001h
0x140019e3f  jmp     short loc_140019E1D
```
