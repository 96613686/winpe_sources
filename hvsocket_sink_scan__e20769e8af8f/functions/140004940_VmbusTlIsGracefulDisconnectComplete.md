# VmbusTlIsGracefulDisconnectComplete

- ea: `0x140004940`
- end: `0x140004997`
- name: `VmbusTlIsGracefulDisconnectComplete`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ab20`
- `0x14000b220`

## callees

- `0x140004940`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004954`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004954`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000497d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000497d`

## pseudocode

```c
bool __fastcall VmbusTlIsGracefulDisconnectComplete(__int64 a1)
{
  KSPIN_LOCK *v1; // rdi
  KIRQL v3; // al
  bool v4; // bl

  v1 = (KSPIN_LOCK *)(a1 + 72);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  v4 = *(_DWORD *)(a1 + 520) == 4 && *(_DWORD *)(a1 + 524) == 19;
  KeReleaseSpinLock(v1, v3);
  return v4;
}

```

## disassembly

```asm
0x140004940  mov     [rsp+arg_0], rbx
0x140004945  push    rdi
0x140004946  sub     rsp, 20h
0x14000494a  lea     rdi, [rcx+48h]
0x14000494e  mov     rbx, rcx
0x140004951  mov     rcx, rdi; SpinLock
0x140004954  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000495b  nop     dword ptr [rax+rax+00h]
0x140004960  cmp     dword ptr [rbx+208h], 4
0x140004967  jnz     short loc_140004976
0x140004969  cmp     dword ptr [rbx+20Ch], 13h
0x140004970  jnz     short loc_140004976
0x140004972  mov     bl, 1
0x140004974  jmp     short loc_140004978
0x140004976  xor     bl, bl
0x140004978  mov     dl, al; NewIrql
0x14000497a  mov     rcx, rdi; SpinLock
0x14000497d  call    cs:__imp_KeReleaseSpinLock
0x140004984  nop     dword ptr [rax+rax+00h]
0x140004989  mov     al, bl
0x14000498b  mov     rbx, [rsp+28h+arg_0]
0x140004990  add     rsp, 20h
0x140004994  pop     rdi
0x140004995  retn
```
