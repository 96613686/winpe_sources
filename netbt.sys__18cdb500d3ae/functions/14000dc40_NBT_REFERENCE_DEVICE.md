# NBT_REFERENCE_DEVICE

- ea: `0x14000dc40`
- end: `0x14000dcc6`
- name: `NBT_REFERENCE_DEVICE`
- size: `134`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cbbc`
- `0x14000da94`
- `0x14000e268`
- `0x14000e408`
- `0x140017a3c`
- `0x14001a2b8`
- `0x140020900`
- `0x1400225e8`
- `0x140022ed0`
- `0x1400281b0`
- `0x140029570`
- `0x14002bd9c`
- `0x14002c018`
- `0x14002cda0`
- `0x14002e6fc`
- `0x14002e8c0`
- `0x14002edd8`
- `0x1400304c8`
- `0x140047d90`
- `0x14004b7a0`
- `0x14004ce30`
- `0x14004d120`
- `0x140052100`

## callees

- `0x14000dc40`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dc66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000dc66`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dca2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dca2`

## pseudocode

```c
__int64 __fastcall NBT_REFERENCE_DEVICE(__int64 a1, unsigned int a2, char a3)
{
  __int64 v3; // rsi
  KIRQL v6; // al
  unsigned __int8 v7; // bl

  v3 = a2;
  v6 = -1;
  if ( !a3 )
    v6 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( a1 && *(_DWORD *)(a1 + 360) == 1131832644 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 364));
    ++*(_DWORD *)(a1 + 4 * v3 + 1084);
    v7 = 1;
  }
  else
  {
    v7 = 0;
  }
  if ( !a3 )
    KeReleaseSpinLock(&SpinLock, v6);
  return v7;
}

```

## disassembly

```asm
0x14000dc40  mov     [rsp+arg_0], rbx
0x14000dc45  mov     [rsp+arg_8], rsi
0x14000dc4a  push    rdi
0x14000dc4b  sub     rsp, 20h
0x14000dc4f  mov     esi, edx
0x14000dc51  movzx   edi, r8b
0x14000dc55  mov     rbx, rcx
0x14000dc58  mov     al, 0FFh
0x14000dc5a  test    r8b, r8b
0x14000dc5d  jnz     short loc_14000DC72
0x14000dc5f  lea     rcx, SpinLock; SpinLock
0x14000dc66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000dc6d  nop     dword ptr [rax+rax+00h]
0x14000dc72  test    rbx, rbx
0x14000dc75  jz      short loc_14000DCC2
0x14000dc77  cmp     dword ptr [rbx+168h], 43766544h
0x14000dc81  jnz     short loc_14000DCC2
0x14000dc83  lock inc dword ptr [rbx+16Ch]
0x14000dc8a  inc     dword ptr [rbx+rsi*4+43Ch]
0x14000dc91  mov     bl, 1
0x14000dc93  test    dil, dil
0x14000dc96  jnz     short loc_14000DCAE
0x14000dc98  movzx   edx, al; NewIrql
0x14000dc9b  lea     rcx, SpinLock; SpinLock
0x14000dca2  call    cs:__imp_KeReleaseSpinLock
0x14000dca9  nop     dword ptr [rax+rax+00h]
0x14000dcae  mov     rsi, [rsp+28h+arg_8]
0x14000dcb3  movzx   eax, bl
0x14000dcb6  mov     rbx, [rsp+28h+arg_0]
0x14000dcbb  add     rsp, 20h
0x14000dcbf  pop     rdi
0x14000dcc0  retn
0x14000dcc2  xor     bl, bl
0x14000dcc4  jmp     short loc_14000DC93
```
