# QuicLookupRemoveLocalCidInt

- ea: `0x14001d7f4`
- end: `0x14001d885`
- name: `QuicLookupRemoveLocalCidInt`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d6fc`
- `0x14001dfec`
- `0x1400452d0`

## callees

- `0x14001d7f4`
- `0x140038bc8`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001d871`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001d871`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001d850`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001d850`

## pseudocode

```c
void __fastcall QuicLookupRemoveLocalCidInt(__int64 a1, __int64 *a2)
{
  int v2; // r9d
  int v3; // eax
  volatile LONG *v5; // rbx
  KIRQL v6; // r9

  v2 = *(unsigned __int16 *)(a1 + 12);
  v3 = *(_DWORD *)(a1 + 4) - 1;
  *(_DWORD *)(a1 + 4) = v3;
  if ( (_WORD)v2 )
  {
    v5 = (volatile LONG *)(*(_QWORD *)(a1 + 16)
                         + ((unsigned __int64)(unsigned __int16)((unsigned __int16)(word_14005C55E
                                                                                  & *(_WORD *)((_BYTE *)a2
                                                                                             + (unsigned __int8)byte_14005C561
                                                                                             + 56))
                                                               % v2) << 6));
    ExAcquireSpinLockExclusive(v5);
    CxPlatHashtableRemove((__int64)(v5 + 2), a2);
    ExReleaseSpinLockExclusive(v5, v6);
  }
  else if ( !v3 )
  {
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x14001d7f4  mov     [rsp+arg_0], rbx
0x14001d7f9  push    rdi
0x14001d7fa  sub     rsp, 20h
0x14001d7fe  mov     eax, [rcx+4]
0x14001d801  mov     r8, rcx
0x14001d804  movzx   r9d, word ptr [rcx+0Ch]
0x14001d809  dec     eax
0x14001d80b  mov     [rcx+4], eax
0x14001d80e  mov     rdi, rdx
0x14001d811  xor     ecx, ecx
0x14001d813  test    r9w, r9w
0x14001d817  jnz     short loc_14001D829
0x14001d819  test    eax, eax
0x14001d81b  jz      short loc_14001D87F
0x14001d81d  mov     rbx, [rsp+28h+arg_0]
0x14001d822  add     rsp, 20h
0x14001d826  pop     rdi
0x14001d827  retn
0x14001d829  movzx   ecx, cs:word_14005C55E
0x14001d830  movzx   eax, cs:byte_14005C561
0x14001d837  movzx   eax, word ptr [rax+rdx+38h]
0x14001d83c  and     eax, ecx
0x14001d83e  cdq
0x14001d83f  idiv    r9d
0x14001d842  movzx   ebx, dx
0x14001d845  shl     rbx, 6
0x14001d849  add     rbx, [r8+10h]
0x14001d84d  mov     rcx, rbx; SpinLock
0x14001d850  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001d857  nop     dword ptr [rax+rax+00h]
0x14001d85c  lea     rcx, [rbx+8]
0x14001d860  mov     rdx, rdi
0x14001d863  mov     r9b, al
0x14001d866  call    CxPlatHashtableRemove
0x14001d86b  mov     rcx, rbx; SpinLock
0x14001d86e  mov     dl, r9b; OldIrql
0x14001d871  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001d878  nop     dword ptr [rax+rax+00h]
0x14001d87d  jmp     short loc_14001D81D
0x14001d87f  mov     [r8+10h], rcx
0x14001d883  jmp     short loc_14001D81D
```
