# NbtRemovePermanentName

- ea: `0x140001e64`
- end: `0x140001ede`
- name: `NbtRemovePermanentName`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ee4`
- `0x140010c90`
- `0x14004f988`

## callees

- `0x140001e64`
- `0x140003d04`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001e78`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ea4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ed0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ea4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ed0`

## pseudocode

```c
void __fastcall NbtRemovePermanentName(__int64 a1)
{
  KIRQL v2; // al
  void *v3; // rdi

  v2 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v3 = *(void **)(a1 + 448);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 448) = 0;
    KeReleaseSpinLock(&SpinLock, v2);
    NbtDereferenceClient(v3);
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v2);
  }
}

```

## disassembly

```asm
0x140001e64  mov     [rsp+arg_0], rbx
0x140001e69  push    rdi
0x140001e6a  sub     rsp, 20h
0x140001e6e  mov     rbx, rcx
0x140001e71  lea     rcx, SpinLock; SpinLock
0x140001e78  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001e7f  nop     dword ptr [rax+rax+00h]
0x140001e84  mov     rdi, [rbx+1C0h]
0x140001e8b  lea     rcx, SpinLock; SpinLock
0x140001e92  mov     dl, al; NewIrql
0x140001e94  test    rdi, rdi
0x140001e97  jz      short loc_140001ED0
0x140001e99  mov     qword ptr [rbx+1C0h], 0
0x140001ea4  call    cs:__imp_KeReleaseSpinLock
0x140001eab  nop     dword ptr [rax+rax+00h]
0x140001eb0  lea     r8, aMinioNetbtSysN_1; "minio\\netbt\\sys\\nbtutils.c"
0x140001eb7  mov     edx, 241h
0x140001ebc  mov     rcx, rdi; P
0x140001ebf  call    NbtDereferenceClient
0x140001ec4  mov     rbx, [rsp+28h+arg_0]
0x140001ec9  add     rsp, 20h
0x140001ecd  pop     rdi
0x140001ece  retn
0x140001ed0  call    cs:__imp_KeReleaseSpinLock
0x140001ed7  nop     dword ptr [rax+rax+00h]
0x140001edc  jmp     short loc_140001EC4
```
