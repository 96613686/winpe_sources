# FastEncoderFindMatch

- ea: `0x180001a20`
- end: `0x180001b84`
- name: `FastEncoderFindMatch`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180001a20`

## pseudocode

```c
__int64 __fastcall FastEncoderFindMatch(__int64 a1, __int64 a2, int a3, int a4, unsigned int *a5, int a6, int a7)
{
  int v7; // r10d
  int v11; // r15d
  char v12; // di
  int i; // ebx
  unsigned int v15; // ecx
  int j; // r8d
  __int64 v18; // rcx
  _BYTE *v19; // rbp

  v7 = 0;
  v11 = 0;
  v12 = *(_BYTE *)(a3 + a1);
  for ( i = a3 - 0x2000; a4 > i; a4 = *(unsigned __int16 *)(a2 + 2LL * (a4 & 0x1FFF)) )
  {
    if ( *(_BYTE *)(v7 + a4 + a1) == v12 )
    {
      for ( j = 0; j < 258; j += 6 )
      {
        v18 = j + a4;
        v19 = (_BYTE *)(a1 + j + a3);
        if ( *v19 != *(_BYTE *)(v18 + a1) )
          break;
        if ( v19[1] != *(_BYTE *)(v18 + a1 + 1) )
        {
          ++j;
          break;
        }
        if ( v19[2] != *(_BYTE *)(v18 + a1 + 2) )
        {
          j += 2;
          break;
        }
        if ( v19[3] != *(_BYTE *)(v18 + a1 + 3) )
        {
          j += 3;
          break;
        }
        if ( v19[4] != *(_BYTE *)(v18 + a1 + 4) )
        {
          j += 4;
          break;
        }
        if ( v19[5] != *(_BYTE *)(v18 + a1 + 5) )
        {
          j += 5;
          break;
        }
      }
      if ( j > v7 )
      {
        v7 = j;
        v11 = a4;
        if ( j > a7 )
          break;
        v12 = *(_BYTE *)(j + a3 + a1);
      }
    }
    if ( !--a6 )
      break;
  }
  v15 = a3 - v11 - 1;
  *a5 = v15;
  if ( v7 == 3 && v15 >= 0x4000 )
    return 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180001a20  sub     rsp, 18h
0x180001a24  mov     [rsp+18h+arg_0], rbx
0x180001a29  xor     r10d, r10d
0x180001a2c  mov     [rsp+18h+arg_10], rsi
0x180001a31  mov     r11, rcx
0x180001a34  mov     [rsp+18h+var_8], rdi
0x180001a39  mov     rsi, rdx
0x180001a3c  mov     [rsp+18h+var_10], r14
0x180001a41  movsxd  r14, r8d
0x180001a44  mov     [rsp+18h+var_18], r15
0x180001a48  xor     r15d, r15d
0x180001a4b  movzx   edi, byte ptr [r14+rcx]
0x180001a50  lea     ebx, [r14-2000h]
0x180001a57  cmp     r9d, ebx
0x180001a5a  jle     short loc_180001A98
0x180001a5c  mov     edx, [rsp+18h+arg_28]
0x180001a60  mov     [rsp+18h+arg_8], rbp
0x180001a65  nop     word ptr [rax+rax+00000000h]
0x180001a70  lea     eax, [r10+r9]
0x180001a74  movsxd  rcx, eax
0x180001a77  cmp     [rcx+r11], dil
0x180001a7b  jz      short loc_180001ACC
0x180001a7d  sub     edx, 1
0x180001a80  jz      short loc_180001A93
0x180001a82  and     r9d, 1FFFh
0x180001a89  movzx   r9d, word ptr [rsi+r9*2]
0x180001a8e  cmp     r9d, ebx
0x180001a91  jg      short loc_180001A70
0x180001a93  mov     rbp, [rsp+18h+arg_8]
0x180001a98  mov     rax, [rsp+18h+arg_20]
0x180001a9d  sub     r14d, r15d
0x180001aa0  mov     r15, [rsp+18h+var_18]
0x180001aa4  mov     rdi, [rsp+18h+var_8]
0x180001aa9  mov     rsi, [rsp+18h+arg_10]
0x180001aae  mov     rbx, [rsp+18h+arg_0]
0x180001ab3  lea     ecx, [r14-1]
0x180001ab7  mov     r14, [rsp+18h+var_10]
0x180001abc  mov     [rax], ecx
0x180001abe  cmp     r10d, 3
0x180001ac2  jz      short loc_180001B30
0x180001ac4  mov     eax, r10d
0x180001ac7  add     rsp, 18h
0x180001acb  retn
0x180001acc  xor     r8d, r8d
0x180001acf  lea     eax, [r8+r14]
0x180001ad3  movsxd  rbp, eax
0x180001ad6  lea     eax, [r8+r9]
0x180001ada  movsxd  rcx, eax
0x180001add  add     rbp, r11
0x180001ae0  movzx   eax, byte ptr [rcx+r11]
0x180001ae5  cmp     [rbp+0], al
0x180001ae8  jnz     short loc_180001B41
0x180001aea  movzx   eax, byte ptr [rcx+r11+1]
0x180001af0  cmp     [rbp+1], al
0x180001af3  jnz     short loc_180001B3E
0x180001af5  movzx   eax, byte ptr [rcx+r11+2]
0x180001afb  cmp     [rbp+2], al
0x180001afe  jnz     short loc_180001B6C
0x180001b00  movzx   eax, byte ptr [rcx+r11+3]
0x180001b06  cmp     [rbp+3], al
0x180001b09  jnz     short loc_180001B72
0x180001b0b  movzx   eax, byte ptr [rcx+r11+4]
0x180001b11  cmp     [rbp+4], al
0x180001b14  jnz     short loc_180001B78
0x180001b16  movzx   eax, byte ptr [rcx+r11+5]
0x180001b1c  cmp     [rbp+5], al
0x180001b1f  jnz     short loc_180001B7E
0x180001b21  add     r8d, 6
0x180001b25  cmp     r8d, 102h
0x180001b2c  jl      short loc_180001ACF
0x180001b2e  jmp     short loc_180001B41
0x180001b30  xor     eax, eax
0x180001b32  cmp     ecx, 4000h
0x180001b38  cmovnb  r10d, eax
0x180001b3c  jmp     short loc_180001AC4
0x180001b3e  inc     r8d
0x180001b41  cmp     r8d, r10d
0x180001b44  jle     loc_180001A7D
0x180001b4a  mov     r10d, r8d
0x180001b4d  mov     r15d, r9d
0x180001b50  cmp     r8d, [rsp+18h+arg_30]
0x180001b55  jg      loc_180001A93
0x180001b5b  lea     eax, [r8+r14]
0x180001b5f  movsxd  rcx, eax
0x180001b62  movzx   edi, byte ptr [rcx+r11]
0x180001b67  jmp     loc_180001A7D
0x180001b6c  add     r8d, 2
0x180001b70  jmp     short loc_180001B41
0x180001b72  add     r8d, 3
0x180001b76  jmp     short loc_180001B41
0x180001b78  add     r8d, 4
0x180001b7c  jmp     short loc_180001B41
0x180001b7e  add     r8d, 5
0x180001b82  jmp     short loc_180001B41
```
