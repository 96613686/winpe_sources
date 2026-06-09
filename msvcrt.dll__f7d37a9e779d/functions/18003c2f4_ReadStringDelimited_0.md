# ReadStringDelimited_0

- ea: `0x18003c2f4`
- end: `0x18003c45e`
- name: `ReadStringDelimited_0`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003c568`

## callees

- `0x18003c0d4`
- `0x18003c2f4`

## pseudocode

```c
__int64 __fastcall ReadStringDelimited_0(
        char a1,
        unsigned __int8 **a2,
        int *a3,
        _DWORD *a4,
        _WORD **SrcCh,
        int a6,
        FILE *Stream,
        __int64 a8,
        _DWORD *a9)
{
  unsigned __int8 *v9; // rax
  char v13; // bl
  unsigned __int8 *v14; // rdx
  bool v15; // zf
  unsigned __int8 v16; // r9
  char v17; // al
  unsigned __int8 *v18; // rcx
  unsigned __int8 *v19; // r8
  unsigned __int8 v20; // al
  unsigned __int8 v21; // r9
  unsigned __int8 v22; // cl
  unsigned __int8 v23; // r10
  unsigned __int8 v24; // r11
  int v26[4]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v27; // [rsp+60h] [rbp-38h]

  v9 = *a2;
  v13 = a1;
  v14 = *a2 + 1;
  *a2 = v14;
  v15 = *v14 == 94;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  if ( v15 )
  {
    v16 = v14[1];
    v13 = a1 | 8;
  }
  else
  {
    v16 = *v14;
  }
  if ( *v14 != 94 )
    v14 = v9;
  v17 = HIBYTE(v26[2]);
  if ( v16 == 93 )
    v17 = 32;
  v18 = v14 + 1;
  HIBYTE(v26[2]) = v17;
  if ( v16 != 93 )
    v18 = v14;
  v19 = v18 + 1;
  v20 = v18[1];
  if ( v20 != 93 )
  {
    v21 = v16 != 93 ? 0 : 0x5D;
    do
    {
      ++v19;
      if ( v20 == 45 && v21 && (v22 = *v19, *v19 != 93) )
      {
        ++v19;
        v23 = v21;
        v24 = v22;
        if ( v21 >= v22 )
        {
          v24 = v21;
          v23 = v22;
        }
        while ( v23 <= v24 )
        {
          *((_BYTE *)v26 + ((unsigned __int64)v23 >> 3)) |= 1 << (v23 & 7);
          ++v23;
        }
        v21 = 0;
      }
      else
      {
        v21 = v20;
        *((_BYTE *)v26 + ((unsigned __int64)v20 >> 3)) |= 1 << (v20 & 7);
      }
      v20 = *v19;
    }
    while ( *v19 != 93 );
  }
  *a2 = v19;
  return ReadString_0(v13, (__int64)v26, a3, a4, SrcCh, a6, Stream, a8, a9);
}

```

## disassembly

```asm
0x18003c2f4  mov     [rsp+arg_18], rbx
0x18003c2f9  push    rbp
0x18003c2fa  push    rsi
0x18003c2fb  push    rdi
0x18003c2fc  push    r14
0x18003c2fe  push    r15
0x18003c300  sub     rsp, 70h
0x18003c304  mov     rax, [rdx]
0x18003c307  mov     rdi, rdx
0x18003c30a  mov     r14, [rsp+98h+arg_20]
0x18003c312  xorps   xmm0, xmm0
0x18003c315  mov     r15, [rsp+98h+arg_30]
0x18003c31d  mov     rsi, r9
0x18003c320  mov     rbp, r8
0x18003c323  mov     ebx, ecx
0x18003c325  lea     rdx, [rax+1]
0x18003c329  mov     [rdi], rdx
0x18003c32c  cmp     byte ptr [rdx], 5Eh ; '^'
0x18003c32f  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x18003c334  movups  [rsp+98h+var_38], xmm0
0x18003c339  jnz     short loc_18003C344
0x18003c33b  mov     r9b, [rdx+1]
0x18003c33f  or      ebx, 8
0x18003c342  jmp     short loc_18003C347
0x18003c344  mov     r9b, [rdx]
0x18003c347  cmp     byte ptr [rdx], 5Eh ; '^'
0x18003c34a  mov     r8d, 20h ; ' '
0x18003c350  cmovnz  rdx, rax
0x18003c354  movzx   eax, byte ptr [rsp+98h+var_48+0Bh]
0x18003c359  cmp     r9b, 5Dh ; ']'
0x18003c35d  cmovz   eax, r8d
0x18003c361  lea     rcx, [rdx+1]
0x18003c365  mov     byte ptr [rsp+98h+var_48+0Bh], al
0x18003c369  cmovnz  rcx, rdx
0x18003c36d  lea     r8, [rcx+1]
0x18003c371  mov     al, [r8]
0x18003c374  cmp     al, 5Dh ; ']'
0x18003c376  jz      loc_18003C406
0x18003c37c  cmp     r9b, 5Dh ; ']'
0x18003c380  setnz   r9b
0x18003c384  dec     r9b
0x18003c387  and     r9b, 5Dh
0x18003c38b  inc     r8
0x18003c38e  cmp     al, 2Dh ; '-'
0x18003c390  jnz     short loc_18003C3E3
0x18003c392  test    r9b, r9b
0x18003c395  jz      short loc_18003C3E3
0x18003c397  movzx   ecx, byte ptr [r8]
0x18003c39b  cmp     cl, 5Dh ; ']'
0x18003c39e  jz      short loc_18003C3E3
0x18003c3a0  inc     r8
0x18003c3a3  movzx   eax, r9b
0x18003c3a7  cmp     r9b, cl
0x18003c3aa  movzx   r10d, r9b
0x18003c3ae  mov     r11d, ecx
0x18003c3b1  cmovnb  r11d, eax
0x18003c3b5  cmovnb  r10d, ecx
0x18003c3b9  jmp     short loc_18003C3D9
0x18003c3bb  movzx   edx, r10b
0x18003c3bf  shr     rdx, 3
0x18003c3c3  movzx   eax, r10b
0x18003c3c7  and     eax, 7
0x18003c3ca  movsx   ecx, byte ptr [rsp+rdx+98h+var_48]
0x18003c3cf  bts     ecx, eax
0x18003c3d2  mov     byte ptr [rsp+rdx+98h+var_48], cl
0x18003c3d6  inc     r10b
0x18003c3d9  cmp     r10b, r11b
0x18003c3dc  jbe     short loc_18003C3BB
0x18003c3de  xor     r9b, r9b
0x18003c3e1  jmp     short loc_18003C3FF
0x18003c3e3  movzx   edx, al
0x18003c3e6  mov     r9b, al
0x18003c3e9  shr     rdx, 3
0x18003c3ed  movzx   eax, al
0x18003c3f0  and     eax, 7
0x18003c3f3  movsx   ecx, byte ptr [rsp+rdx+98h+var_48]
0x18003c3f8  bts     ecx, eax
0x18003c3fb  mov     byte ptr [rsp+rdx+98h+var_48], cl
0x18003c3ff  mov     al, [r8]
0x18003c402  cmp     al, 5Dh ; ']'
0x18003c404  jnz     short loc_18003C38B
0x18003c406  mov     rax, [rsp+98h+arg_40]
0x18003c40e  lea     rdx, [rsp+98h+var_48]; int
0x18003c413  mov     [rsp+98h+var_58], rax; __int64
0x18003c418  mov     r9, rsi; int
0x18003c41b  mov     rax, [rsp+98h+arg_38]
0x18003c423  mov     ecx, ebx; int
0x18003c425  mov     [rsp+98h+var_60], rax; __int64
0x18003c42a  mov     eax, [rsp+98h+arg_28]
0x18003c431  mov     [rsp+98h+Stream], r15; Stream
0x18003c436  mov     [rdi], r8
0x18003c439  mov     r8, rbp; int
0x18003c43c  mov     [rsp+98h+var_70], eax; int
0x18003c440  mov     qword ptr [rsp+98h+SrcCh], r14; SrcCh
0x18003c445  call    ReadString_0
0x18003c44a  mov     rbx, [rsp+98h+arg_18]
0x18003c452  add     rsp, 70h
0x18003c456  pop     r15
0x18003c458  pop     r14
0x18003c45a  pop     rdi
0x18003c45b  pop     rsi
0x18003c45c  pop     rbp
0x18003c45d  retn
```
