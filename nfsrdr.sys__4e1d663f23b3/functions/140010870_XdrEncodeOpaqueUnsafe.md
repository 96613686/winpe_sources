# XdrEncodeOpaqueUnsafe

- ea: `0x140010870`
- end: `0x1400108fb`
- name: `XdrEncodeOpaqueUnsafe`
- size: `139`
- prototype: `void *__fastcall(__int64, unsigned int, const void *)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000f274`
- `0x14000fa80`
- `0x14000fb64`
- `0x14000fbc0`
- `0x140010904`
- `0x1400124ec`
- `0x14002ba00`

## callees

- `0x140010870`
- `0x14003adc0`
- `0x14003b0c0`

## pseudocode

```c
void *__fastcall XdrEncodeOpaqueUnsafe(__int64 a1, unsigned int a2, const void *a3)
{
  __int64 v3; // rax
  void *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rdx
  char *v8; // rcx
  __int64 v9; // rax
  char v10; // r8
  void *result; // rax
  char *v12; // r8

  v3 = *(_QWORD *)(a1 + 72);
  if ( v3 )
    v5 = *(void **)(v3 + 64);
  else
    v5 = 0;
  v6 = a2;
  memmove(v5, a3, a2);
  *(_QWORD *)(*(_QWORD *)(a1 + 72) + 64LL) += v6;
  v7 = *(_QWORD *)(a1 + 72);
  if ( v7 )
  {
    v9 = *(_QWORD *)(v7 + 56);
    v8 = *(char **)(v7 + 64);
    v10 = (char)v8;
  }
  else
  {
    v8 = 0;
    LOBYTE(v9) = 0;
    v10 = 0;
  }
  result = (void *)(*(_QWORD *)(v7 + 64) + (((_BYTE)v9 - v10) & 3));
  *(_QWORD *)(v7 + 64) = result;
  v12 = *(char **)(a1 + 72);
  if ( v12 )
    v12 = (char *)*((_QWORD *)v12 + 8);
  if ( v8 != v12 )
    return memset(v8, 0, v12 - v8);
  return result;
}

```

## disassembly

```asm
0x140010870  mov     [rsp+arg_0], rbx
0x140010875  push    rdi
0x140010876  sub     rsp, 20h
0x14001087a  mov     rax, [rcx+48h]
0x14001087e  mov     r9, r8
0x140010881  mov     rdi, rcx
0x140010884  test    rax, rax
0x140010887  jnz     short loc_14001088D
0x140010889  xor     ecx, ecx
0x14001088b  jmp     short loc_140010891
0x14001088d  mov     rcx, [rax+40h]; void *
0x140010891  mov     ebx, edx
0x140010893  mov     r8d, edx; Size
0x140010896  mov     rdx, r9; Src
0x140010899  call    memmove
0x14001089e  mov     rax, [rdi+48h]
0x1400108a2  add     [rax+40h], rbx
0x1400108a6  mov     rdx, [rdi+48h]
0x1400108aa  mov     r9, [rdx+40h]
0x1400108ae  test    rdx, rdx
0x1400108b1  jnz     short loc_1400108BC
0x1400108b3  xor     ecx, ecx
0x1400108b5  xor     eax, eax
0x1400108b7  xor     r8d, r8d
0x1400108ba  jmp     short loc_1400108C6
0x1400108bc  mov     rax, [rdx+38h]
0x1400108c0  mov     rcx, r9; void *
0x1400108c3  mov     r8, r9
0x1400108c6  sub     rax, r8
0x1400108c9  and     eax, 3
0x1400108cc  add     rax, r9
0x1400108cf  mov     [rdx+40h], rax
0x1400108d3  mov     r8, [rdi+48h]
0x1400108d7  test    r8, r8
0x1400108da  jz      short loc_1400108E0
0x1400108dc  mov     r8, [r8+40h]
0x1400108e0  cmp     rcx, r8
0x1400108e3  jz      short loc_1400108EF
0x1400108e5  sub     r8, rcx; Size
0x1400108e8  xor     edx, edx; Val
0x1400108ea  call    memset
0x1400108ef  mov     rbx, [rsp+28h+arg_0]
0x1400108f4  add     rsp, 20h
0x1400108f8  pop     rdi
0x1400108f9  retn
```
