# DecryptCopy

- ea: `0x140081efc`
- end: `0x140081f9f`
- name: `DecryptCopy`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14003f708`
- `0x1400823e0`

## callees

- `0x140081efc`

## pseudocode

```c
char __fastcall DecryptCopy(_BYTE *a1, unsigned __int8 *a2, unsigned int *a3, unsigned int a4, __int16 a5)
{
  unsigned __int8 *v5; // r10
  __int64 v7; // rax
  unsigned __int64 v8; // r11
  unsigned int v10; // eax
  __int16 v11; // cx

  v5 = a2;
  v7 = *a3;
  v8 = (unsigned __int64)&a2[v7];
  if ( (unsigned int)v7 < a4 )
    a4 = *a3;
  *a3 = v7 - a4;
  while ( 1 )
  {
    v10 = a4--;
    if ( !v10 )
      break;
    a5 = 22719 - 12691 * (a5 + *v5++);
  }
  while ( (unsigned __int64)v5 < v8 )
  {
    v11 = *v5++;
    LOBYTE(v10) = v11 ^ HIBYTE(a5);
    *a1++ = v11 ^ HIBYTE(a5);
    a5 = 22719 - 12691 * (a5 + v11);
  }
  return v10;
}

```

## disassembly

```asm
0x140081efc  mov     [rsp+arg_10], rbx
0x140081f01  push    rsi
0x140081f02  mov     r10, rdx
0x140081f05  mov     rbx, rcx
0x140081f08  mov     eax, [r8]
0x140081f0b  lea     r11, [rdx+rax]
0x140081f0f  cmp     eax, r9d
0x140081f12  cmovb   r9d, eax
0x140081f16  mov     [rsp+8+arg_18], r9d
0x140081f1b  sub     eax, r9d
0x140081f1e  mov     [r8], eax
0x140081f21  mov     esi, 3193h
0x140081f26  movzx   r8d, [rsp+8+arg_20]
0x140081f2c  mov     eax, r9d
0x140081f2f  dec     r9d
0x140081f32  mov     [rsp+8+arg_18], r9d
0x140081f37  test    eax, eax
0x140081f39  jz      short loc_140081F5D
0x140081f3b  movzx   ecx, byte ptr [r10]
0x140081f3f  add     cx, r8w
0x140081f43  movzx   edx, cx
0x140081f46  imul    edx, esi
0x140081f49  mov     r8d, 58BFh
0x140081f4f  sub     r8w, dx
0x140081f53  inc     r10
0x140081f56  mov     [rsp+8+arg_8], r10
0x140081f5b  jmp     short loc_140081F2C
0x140081f5d  cmp     r10, r11
0x140081f60  jnb     short loc_140081F98
0x140081f62  movzx   ecx, byte ptr [r10]
0x140081f66  inc     r10
0x140081f69  mov     [rsp+8+arg_8], r10
0x140081f6e  movzx   eax, r8w
0x140081f72  shr     ax, 8
0x140081f76  xor     al, cl
0x140081f78  mov     [rbx], al
0x140081f7a  inc     rbx
0x140081f7d  mov     [rsp+8+arg_0], rbx
0x140081f82  add     cx, r8w
0x140081f86  movzx   edx, cx
0x140081f89  imul    edx, esi
0x140081f8c  mov     r8d, 58BFh
0x140081f92  sub     r8w, dx
0x140081f96  jmp     short loc_140081F5D
0x140081f98  mov     rbx, [rsp+8+arg_10]
0x140081f9d  pop     rsi
0x140081f9e  retn
0x140097679  push    rbp
0x14009767b  mov     rbp, rdx
0x14009767e  pop     rbp
0x14009767f  retn
```
