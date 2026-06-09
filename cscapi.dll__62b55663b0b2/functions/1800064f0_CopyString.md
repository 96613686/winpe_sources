# CopyString

- ea: `0x1800064f0`
- end: `0x18000654e`
- name: `CopyString`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002080`
- `0x180006750`

## callees

- `0x1800064f0`
- `0x180009456`

## pseudocode

```c
__int64 __fastcall CopyString(__int64 a1, void **a2, unsigned int a3, const void **a4)
{
  void **v4; // r8
  void *v5; // rdi
  size_t v6; // rbx
  __int64 result; // rax

  if ( a3 != -1 )
  {
    v4 = (void **)(a1 + a3);
    if ( v4 )
    {
      *a2 = (char *)*a2 - 2LL - *(unsigned __int16 *)a4;
      v5 = *a2;
      *v4 = *a2;
      v6 = *(unsigned __int16 *)a4;
      memcpy_0(v5, a4[1], v6);
      result = 0;
      *((_WORD *)v5 + (v6 >> 1)) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800064f0  sub     rsp, 28h
0x1800064f4  cmp     r8d, 0FFFFFFFFh
0x1800064f8  jz      short loc_180006549
0x1800064fa  mov     r8d, r8d
0x1800064fd  add     r8, rcx
0x180006500  jz      short loc_180006549
0x180006502  movzx   eax, word ptr [r9]
0x180006506  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x18000650d  sub     rcx, rax
0x180006510  mov     [rsp+28h+arg_0], rbx
0x180006515  add     [rdx], rcx
0x180006518  mov     [rsp+28h+var_8], rdi
0x18000651d  mov     rdi, [rdx]
0x180006520  mov     [r8], rdi
0x180006523  mov     rcx, rdi; void *
0x180006526  movzx   ebx, word ptr [r9]
0x18000652a  mov     rdx, [r9+8]; Src
0x18000652e  mov     r8d, ebx; Size
0x180006531  call    memcpy_0
0x180006536  shr     rbx, 1
0x180006539  xor     eax, eax
0x18000653b  mov     [rdi+rbx*2], ax
0x18000653f  mov     rdi, [rsp+28h+var_8]
0x180006544  mov     rbx, [rsp+28h+arg_0]
0x180006549  add     rsp, 28h
0x18000654d  retn
```
