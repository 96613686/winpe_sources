# IsBundleValid

- ea: `0x140003870`
- end: `0x14000395b`
- name: `IsBundleValid`
- size: `235`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140001be0`
- `0x140025c80`
- `0x140026c80`
- `0x1400274e0`
- `0x140027a50`
- `0x140028610`
- `0x140028f60`
- `0x14002a0f0`

## callees

- `0x140003870`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400038e3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400038e3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003904`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000394d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003904`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000394d`
- `NDIS!NdisAcquireRWLockRead` at `0x1400038a6`
- `NDIS!NdisAcquireRWLockRead` at `0x1400038a6`
- `NDIS!NdisReleaseRWLock` at `0x140003927`
- `NDIS!NdisReleaseRWLock` at `0x140003927`

## pseudocode

```c
__int64 __fastcall IsBundleValid(unsigned int a1, char a2, _QWORD *a3)
{
  unsigned __int8 v6; // si
  __int64 v7; // rbx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  *a3 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = 0;
  NdisAcquireRWLockRead(ConnTableLock, &LockState, 0);
  if ( a1 <= *((_DWORD *)ConnectionTable + 1) )
  {
    _mm_lfence();
    v7 = *(_QWORD *)(*((_QWORD *)ConnectionTable + 8) + 8LL * a1);
    if ( v7 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v7 + 1768));
      if ( a2 && *(_DWORD *)(v7 + 20) != 2 )
      {
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v7 + 1768));
      }
      else
      {
        ++*(_DWORD *)(v7 + 24);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v7 + 1768));
        *a3 = v7;
        v6 = 1;
      }
    }
  }
  NdisReleaseRWLock(ConnTableLock, &LockState);
  return v6;
}

```

## disassembly

```asm
0x140003870  mov     [rsp+arg_10], rbx
0x140003875  push    rbp
0x140003876  push    rsi
0x140003877  push    r14
0x140003879  sub     rsp, 20h
0x14000387d  xor     eax, eax
0x14000387f  mov     r14, r8
0x140003882  mov     [r8], rax
0x140003885  movzx   ebp, dl
0x140003888  mov     rbx, rcx
0x14000388b  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x140003890  mov     rcx, cs:ConnTableLock; Lock
0x140003897  lea     rdx, [rsp+38h+LockState]; LockState
0x14000389c  xor     r8d, r8d; Flags
0x14000389f  mov     [rsp+38h+LockState.Flags], al
0x1400038a3  xor     sil, sil
0x1400038a6  call    cs:__imp_NdisAcquireRWLockRead
0x1400038ad  nop     dword ptr [rax+rax+00h]
0x1400038b2  mov     rax, cs:ConnectionTable
0x1400038b9  cmp     ebx, [rax+4]
0x1400038bc  ja      short loc_14000391B
0x1400038be  lfence
0x1400038c1  mov     rax, cs:ConnectionTable
0x1400038c8  mov     ecx, ebx
0x1400038ca  mov     rbx, [rax+40h]
0x1400038ce  mov     rbx, [rbx+rcx*8]
0x1400038d2  test    rbx, rbx
0x1400038d5  jz      short loc_14000391B
0x1400038d7  lea     rcx, [rbx+6E8h]; SpinLock
0x1400038de  mov     [rsp+38h+arg_8], rdi
0x1400038e3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400038ea  nop     dword ptr [rax+rax+00h]
0x1400038ef  test    bpl, bpl
0x1400038f2  jz      short loc_1400038FA
0x1400038f4  cmp     dword ptr [rbx+14h], 2
0x1400038f8  jnz     short loc_140003946
0x1400038fa  inc     dword ptr [rbx+18h]
0x1400038fd  lea     rcx, [rbx+6E8h]; SpinLock
0x140003904  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000390b  nop     dword ptr [rax+rax+00h]
0x140003910  mov     [r14], rbx
0x140003913  mov     sil, 1
0x140003916  mov     rdi, [rsp+38h+arg_8]
0x14000391b  mov     rcx, cs:ConnTableLock; Lock
0x140003922  lea     rdx, [rsp+38h+LockState]; LockState
0x140003927  call    cs:__imp_NdisReleaseRWLock
0x14000392e  nop     dword ptr [rax+rax+00h]
0x140003933  mov     rbx, [rsp+38h+arg_10]
0x140003938  movzx   eax, sil
0x14000393c  add     rsp, 20h
0x140003940  pop     r14
0x140003942  pop     rsi
0x140003943  pop     rbp
0x140003944  retn
0x140003946  lea     rcx, [rbx+6E8h]; SpinLock
0x14000394d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003954  nop     dword ptr [rax+rax+00h]
0x140003959  jmp     short loc_140003916
```
