# ValidateAndReferenceAddr

- ea: `0x14000b808`
- end: `0x14000b882`
- name: `ValidateAndReferenceAddr`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006470`
- `0x140008cdc`

## callees

- `0x14000b808`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b81d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b81d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b869`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b869`

## string_xrefs

- `0x14000b84d`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
_QWORD *__fastcall ValidateAndReferenceAddr(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rsi
  _QWORD *i; // rax

  v3 = 0;
  *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  for ( i = *(_QWORD **)(a1 + 112); i != (_QWORD *)(a1 + 112); i = (_QWORD *)*i )
  {
    if ( a2 == i )
    {
      v3 = a2;
      RefObj_AddRefEx(a2 + 3, 542134857, 4583, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      break;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
  return v3;
}

```

## disassembly

```asm
0x14000b808  push    rbx
0x14000b80a  push    rbp
0x14000b80b  push    rsi
0x14000b80c  push    rdi
0x14000b80d  sub     rsp, 28h
0x14000b811  mov     rdi, rcx
0x14000b814  xor     esi, esi
0x14000b816  add     rcx, 30h ; '0'; SpinLock
0x14000b81a  mov     rbx, rdx
0x14000b81d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b824  nop     dword ptr [rax+rax+00h]
0x14000b829  lea     rcx, [rdi+70h]
0x14000b82d  mov     [rdi+38h], al
0x14000b830  mov     rax, [rcx]
0x14000b833  jmp     short loc_14000B83D
0x14000b835  cmp     rbx, rax
0x14000b838  jz      short loc_14000B844
0x14000b83a  mov     rax, [rax]
0x14000b83d  cmp     rax, rcx
0x14000b840  jnz     short loc_14000B835
0x14000b842  jmp     short loc_14000B862
0x14000b844  lea     rcx, [rbx+18h]
0x14000b848  mov     edx, 20505249h
0x14000b84d  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000b854  mov     r8d, 11E7h
0x14000b85a  mov     rsi, rbx
0x14000b85d  call    RefObj_AddRefEx
0x14000b862  mov     dl, [rdi+38h]; NewIrql
0x14000b865  lea     rcx, [rdi+30h]; SpinLock
0x14000b869  call    cs:__imp_KeReleaseSpinLock
0x14000b870  nop     dword ptr [rax+rax+00h]
0x14000b875  mov     rax, rsi
0x14000b878  add     rsp, 28h
0x14000b87c  pop     rdi
0x14000b87d  pop     rsi
0x14000b87e  pop     rbp
0x14000b87f  pop     rbx
0x14000b880  retn
```
