# DereferenceCall

- ea: `0x14001b830`
- end: `0x14001b88d`
- name: `DereferenceCall`
- size: `93`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140003c60`
- `0x1400106b4`
- `0x1400109d0`
- `0x140010f90`
- `0x140015190`
- `0x140017010`
- `0x1400174b0`
- `0x1400175f0`
- `0x140017fa0`
- `0x140019810`
- `0x140019a80`
- `0x14001ae40`
- `0x14001af80`
- `0x14001b1e0`

## callees

- `0x14000f2ec`
- `0x14001b830`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001b862`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001b862`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b846`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001b846`

## pseudocode

```c
void __fastcall DereferenceCall(__int64 a1)
{
  KIRQL v2; // al
  int v3; // edi

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  v3 = --*(_DWORD *)(a1 + 64);
  *(_BYTE *)(a1 + 80) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), v2);
  if ( !v3 )
    InactiveCallCleanUp((__int64 *)a1);
}

```

## disassembly

```asm
0x14001b830  mov     [rsp+arg_0], rbx
0x14001b835  mov     [rsp+arg_8], rsi
0x14001b83a  push    rdi
0x14001b83b  sub     rsp, 20h
0x14001b83f  mov     rbx, rcx
0x14001b842  add     rcx, 48h ; 'H'; SpinLock
0x14001b846  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001b84d  nop     dword ptr [rax+rax+00h]
0x14001b852  dec     dword ptr [rbx+40h]
0x14001b855  lea     rcx, [rbx+48h]; SpinLock
0x14001b859  mov     edi, [rbx+40h]
0x14001b85c  movzx   edx, al; NewIrql
0x14001b85f  mov     [rbx+50h], al
0x14001b862  call    cs:__imp_KeReleaseSpinLock
0x14001b869  nop     dword ptr [rax+rax+00h]
0x14001b86e  test    edi, edi
0x14001b870  jz      short loc_14001B883
0x14001b872  mov     rbx, [rsp+28h+arg_0]
0x14001b877  mov     rsi, [rsp+28h+arg_8]
0x14001b87c  add     rsp, 20h
0x14001b880  pop     rdi
0x14001b881  retn
0x14001b883  mov     rcx, rbx
0x14001b886  call    InactiveCallCleanUp
0x14001b88b  jmp     short loc_14001B872
```
