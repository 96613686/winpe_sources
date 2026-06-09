# NbtUpdateSmbBinding

- ea: `0x1400225e8`
- end: `0x1400226c8`
- name: `NbtUpdateSmbBinding`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140047b84`

## callees

- `0x140006900`
- `0x14000dc40`
- `0x1400225e8`
- `0x14002e8c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400225fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400225fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022620`
- `ntoskrnl!KeReleaseSpinLock` at `0x140022620`

## pseudocode

```c
void NbtUpdateSmbBinding()
{
  PDEVICE_OBJECT v0; // rbx
  KIRQL v1; // di
  __int64 v2; // r8
  _DWORD v3[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v4; // [rsp+28h] [rbp-20h]
  PVOID v5; // [rsp+30h] [rbp-18h]

  v0 = 0;
  v1 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( pNbtSmbDevice && !gbDestroyingSmbDevice )
  {
    LOBYTE(v2) = 1;
    v0 = pNbtSmbDevice;
    NBT_REFERENCE_DEVICE(pNbtSmbDevice, 15, v2);
  }
  KeReleaseSpinLock(&SpinLock, v1);
  if ( v0 )
  {
    v3[0] = 0;
    v5 = qword_140039730;
    v4 = 0;
    v3[1] = 1;
    if ( qword_140039730 )
      NbtSetSmbBindingInfo2(v0, v3);
    v3[0] = 1;
    v5 = qword_140039738;
    if ( qword_140039738 )
      NbtSetSmbBindingInfo2(v0, v3);
    NBT_DEREFERENCE_DEVICE(v0, 15);
  }
}

```

## disassembly

```asm
0x1400225e8  mov     [rsp+arg_0], rbx
0x1400225ed  push    rdi
0x1400225ee  sub     rsp, 40h
0x1400225f2  lea     rcx, SpinLock; SpinLock
0x1400225f9  xor     ebx, ebx
0x1400225fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140022602  nop     dword ptr [rax+rax+00h]
0x140022607  mov     rcx, cs:pNbtSmbDevice
0x14002260e  mov     dil, al
0x140022611  test    rcx, rcx
0x140022614  jnz     short loc_14002263D
0x140022616  mov     dl, dil; NewIrql
0x140022619  lea     rcx, SpinLock; SpinLock
0x140022620  call    cs:__imp_KeReleaseSpinLock
0x140022627  nop     dword ptr [rax+rax+00h]
0x14002262c  test    rbx, rbx
0x14002262f  jnz     short loc_140022657
0x140022631  mov     rbx, [rsp+48h+arg_0]
0x140022636  add     rsp, 40h
0x14002263a  pop     rdi
0x14002263b  retn
0x14002263d  cmp     cs:gbDestroyingSmbDevice, ebx
0x140022643  jnz     short loc_140022616
0x140022645  mov     r8b, 1
0x140022648  mov     edx, 0Fh
0x14002264d  mov     rbx, rcx
0x140022650  call    NBT_REFERENCE_DEVICE
0x140022655  jmp     short loc_140022616
0x140022657  mov     rax, cs:qword_140039730
0x14002265e  mov     [rsp+48h+var_28], 0
0x140022666  mov     [rsp+48h+var_18], rax
0x14002266b  mov     [rsp+48h+var_20], 0
0x140022674  mov     [rsp+48h+var_24], 1
0x14002267c  test    rax, rax
0x14002267f  jz      short loc_14002268E
0x140022681  lea     rdx, [rsp+48h+var_28]
0x140022686  mov     rcx, rbx
0x140022689  call    NbtSetSmbBindingInfo2
0x14002268e  mov     rax, cs:qword_140039738
0x140022695  mov     [rsp+48h+var_28], 1
0x14002269d  mov     [rsp+48h+var_18], rax
0x1400226a2  test    rax, rax
0x1400226a5  jz      short loc_1400226B4
0x1400226a7  lea     rdx, [rsp+48h+var_28]
0x1400226ac  mov     rcx, rbx
0x1400226af  call    NbtSetSmbBindingInfo2
0x1400226b4  xor     r8d, r8d
0x1400226b7  mov     rcx, rbx
0x1400226ba  lea     edx, [r8+0Fh]
0x1400226be  call    NBT_DEREFERENCE_DEVICE
0x1400226c3  jmp     loc_140022631
```
