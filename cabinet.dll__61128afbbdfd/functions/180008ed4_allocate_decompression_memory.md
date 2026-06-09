# allocate_decompression_memory

- ea: `0x180008ed4`
- end: `0x180008f35`
- name: `allocate_decompression_memory`
- size: `97`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008e38`

## callees

- `0x180008ed4`
- `0x18001c010`

## pseudocode

```c
_BOOL8 __fastcall allocate_decompression_memory(__int64 a1)
{
  unsigned int v1; // r9d
  unsigned int v2; // r8d
  unsigned __int8 v3; // dl
  __int64 v5; // rcx
  __int64 (__fastcall *v6)(_QWORD); // rax
  __int64 v7; // rax

  v1 = *(_DWORD *)(a1 + 8);
  v2 = 4;
  v3 = 4;
  do
  {
    v5 = v3++;
    v2 += 1 << dec_extra_bits[v5];
  }
  while ( v2 < v1 );
  v6 = *(__int64 (__fastcall **)(_QWORD))(a1 + 12016);
  *(_BYTE *)(a1 + 11973) = v3;
  v7 = v6(v1 + 261);
  *(_QWORD *)a1 = v7;
  return v7 != 0;
}

```

## disassembly

```asm
0x180008ed4  push    rbx
0x180008ed6  sub     rsp, 20h
0x180008eda  mov     r9d, [rcx+8]
0x180008ede  mov     r8d, 4
0x180008ee4  mov     dl, r8b
0x180008ee7  mov     rbx, rcx
0x180008eea  movzx   ecx, dl
0x180008eed  lea     rax, dec_extra_bits
0x180008ef4  inc     dl
0x180008ef6  mov     cl, [rcx+rax]
0x180008ef9  mov     eax, 1
0x180008efe  shl     eax, cl
0x180008f00  add     r8d, eax
0x180008f03  cmp     r8d, r9d
0x180008f06  jb      short loc_180008EEA
0x180008f08  mov     rax, [rbx+2EF0h]
0x180008f0f  lea     ecx, [r9+105h]
0x180008f16  mov     [rbx+2EC5h], dl
0x180008f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f21  mov     rcx, rax
0x180008f24  mov     [rbx], rax
0x180008f27  xor     eax, eax
0x180008f29  test    rcx, rcx
0x180008f2c  setnz   al
0x180008f2f  add     rsp, 20h
0x180008f33  pop     rbx
0x180008f34  retn
```
