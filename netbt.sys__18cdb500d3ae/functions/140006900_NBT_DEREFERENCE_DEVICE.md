# NBT_DEREFERENCE_DEVICE

- ea: `0x140006900`
- end: `0x140006995`
- name: `NBT_DEREFERENCE_DEVICE`
- size: `149`
- prototype: ``
- caller_count: `55`
- callee_count: `2`
- tags: ``

## callers

- `0x140004038`
- `0x140004920`
- `0x140004cb0`
- `0x140005de0`
- `0x140005fb0`
- `0x140006080`
- `0x1400061ac`
- `0x1400062b0`
- `0x1400067e0`
- `0x14000a7b0`
- `0x14000b540`
- `0x14000bbcc`
- `0x14000cbbc`
- `0x14000d070`
- `0x14000da94`
- `0x14000e408`
- `0x14000efd4`
- `0x140017a3c`
- `0x140019a10`
- `0x140019e84`
- `0x14001a2b8`
- `0x14001b7d0`
- `0x14001ba80`
- `0x14001f8d0`
- `0x140020900`
- `0x1400225e8`
- `0x140022ed0`
- `0x140025430`
- `0x140027200`
- `0x1400281b0`
- `0x140029570`
- `0x14002984c`
- `0x14002b9c8`
- `0x14002bb80`
- `0x14002bd9c`
- `0x14002c018`
- `0x14002c240`
- `0x14002c360`
- `0x14002c5e0`
- `0x14002ca6c`
- `0x14002cda0`
- `0x14002e6fc`
- `0x14002e8c0`
- `0x14002edd8`
- `0x1400304c8`
- `0x1400471c0`
- `0x140047630`
- `0x1400478c0`
- `0x140047d90`
- `0x14004b7a0`

## callees

- `0x140006900`
- `0x14000da94`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006920`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006920`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000694e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000694e`

## pseudocode

```c
void __fastcall NBT_DEREFERENCE_DEVICE(__int64 a1, unsigned int a2, char a3)
{
  __int64 v3; // rbp
  KIRQL v6; // bl

  v3 = a2;
  v6 = -1;
  if ( !a3 )
    v6 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  --*(_DWORD *)(a1 + 4 * v3 + 1084);
  if ( (*(_DWORD *)(a1 + 364))-- == 1 )
    NTQueueToWorkerThread(a1 + 984, (__int64)DelayedNbtDeleteDevice, 0, a1, 0, 0, 1, 15);
  if ( !a3 )
    KeReleaseSpinLock(&SpinLock, v6);
}

```

## disassembly

```asm
0x140006900  push    rbx
0x140006902  push    rbp
0x140006903  push    rsi
0x140006904  push    rdi
0x140006905  sub     rsp, 48h
0x140006909  mov     ebp, edx
0x14000690b  movzx   esi, r8b
0x14000690f  mov     rdi, rcx
0x140006912  mov     bl, 0FFh
0x140006914  test    r8b, r8b
0x140006917  jnz     short loc_14000692F
0x140006919  lea     rcx, SpinLock; SpinLock
0x140006920  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006927  nop     dword ptr [rax+rax+00h]
0x14000692c  movzx   ebx, al
0x14000692f  dec     dword ptr [rdi+rbp*4+43Ch]
0x140006936  add     dword ptr [rdi+16Ch], 0FFFFFFFFh
0x14000693d  jz      short loc_140006964
0x14000693f  test    sil, sil
0x140006942  jnz     short loc_14000695A
0x140006944  movzx   edx, bl; NewIrql
0x140006947  lea     rcx, SpinLock; SpinLock
0x14000694e  call    cs:__imp_KeReleaseSpinLock
0x140006955  nop     dword ptr [rax+rax+00h]
0x14000695a  add     rsp, 48h
0x14000695e  pop     rdi
0x14000695f  pop     rsi
0x140006960  pop     rbp
0x140006961  pop     rbx
0x140006962  retn
0x140006964  mov     [rsp+68h+var_30], 0Fh
0x140006969  lea     rcx, [rdi+3D8h]
0x140006970  xor     eax, eax
0x140006972  mov     [rsp+68h+var_38], 1
0x140006977  mov     [rsp+68h+var_40], rax
0x14000697c  lea     rdx, DelayedNbtDeleteDevice
0x140006983  mov     r9, rdi
0x140006986  mov     [rsp+68h+var_48], rax
0x14000698b  xor     r8d, r8d
0x14000698e  call    NTQueueToWorkerThread
0x140006993  jmp     short loc_14000693F
```
