# CopyName

- ea: `0x140035ab8`
- end: `0x140035ddd`
- name: `CopyName`
- size: `805`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140034ef8`
- `0x140035de4`

## callees

- `0x140035ab8`

## pseudocode

```c
__int64 __fastcall CopyName(
        __int64 a1,
        unsigned int a2,
        __int16 a3,
        _BYTE *a4,
        int a5,
        char a6,
        __int16 a7,
        _WORD *a8,
        _QWORD *a9)
{
  unsigned int v10; // ebx
  _WORD *v11; // r15
  _WORD *v12; // r14
  _WORD *v13; // rsi
  _WORD *v14; // r13
  _WORD *v15; // r8
  _WORD *v16; // r10
  unsigned __int64 v17; // r12
  _WORD *v18; // rdx
  _WORD *v19; // rdi
  __int16 v20; // r8
  __int16 v21; // cx
  __int16 v22; // ax
  _WORD *v23; // rcx
  __int16 v24; // cx
  _BYTE *v25; // rdx
  __int64 v26; // r8
  unsigned __int16 v27; // cx
  _BYTE *v28; // r8
  _WORD *v30; // [rsp+8h] [rbp-90h]
  _WORD *v31; // [rsp+28h] [rbp-70h]

  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v31 = 0;
  v14 = 0;
  v15 = 0;
  v30 = 0;
  v16 = 0;
  if ( a2 >= 0x12 && !__ROR2__(*(_WORD *)a1, 8) )
  {
    v17 = a1 + a2;
    if ( a9 && *a9 )
      v18 = (_WORD *)(*a9 + 12LL);
    else
      v18 = (_WORD *)(a1 + 6);
    v19 = &v18[6 * (*(unsigned __int8 *)(a1 + 3) | (unsigned __int64)(unsigned __int16)(*(_WORD *)(a1 + 2) << 8))];
    if ( (unsigned __int64)v19 <= v17 )
    {
      while ( v18 < v19 )
      {
        v20 = __ROR2__(v18[2], 8);
        v21 = a7;
        if ( !a7 )
          v21 = v20;
        a7 = v21;
        if ( __ROR2__(v18[3], 8) == a3 && __ROR2__(*v18, 8) == 3 && __ROR2__(v18[1], 8) == 1 )
        {
          if ( v20 == v21 )
          {
            v12 = v18;
            v15 = v30;
            break;
          }
          if ( !v11 )
            v11 = v18;
          v22 = v21 & 0x3FF;
          v23 = v31;
          if ( v20 == (a7 & 0x3FF) )
            v23 = v18;
          v31 = v23;
          v24 = v20 & 0x3FF;
          if ( (v20 & 0x3FF) == v22 )
            v13 = v18;
          if ( !v20 )
            v14 = v18;
          v15 = v30;
          if ( v24 == 9 )
            v15 = v18;
          v30 = v15;
        }
        else
        {
          v15 = v30;
        }
        v18 += 6;
      }
      if ( v11 )
        v16 = v11;
      if ( v15 )
        v16 = v15;
      if ( v14 )
        v16 = v14;
      if ( v13 )
        v16 = v13;
      if ( v31 )
        v16 = v13;
      if ( v12 )
        v16 = v12;
      if ( v16 )
      {
        v25 = (_BYTE *)(a1
                      + (*(unsigned __int8 *)(a1 + 5) | (unsigned __int64)(unsigned __int16)(*(_WORD *)(a1 + 4) << 8))
                      + (*((unsigned __int8 *)v16 + 11) | (unsigned __int64)(unsigned __int16)(v16[5] << 8)));
        v26 = (unsigned __int16)__ROR2__(v16[4], 8);
        if ( (unsigned __int64)&v25[v26] <= v17 )
        {
          if ( (int)v26 + 2 > (a5 & 0xFFFFFFFE) )
          {
            if ( !a6 )
              goto LABEL_53;
            v27 = (a5 & 0xFFFE) - 2;
          }
          else
          {
            v27 = v26;
          }
          if ( (v27 & 1) == 0 )
          {
            v10 = v27 + 2;
            while ( 1 )
            {
              v28 = a4 + 1;
              if ( !v27 )
                break;
              *a4 = v25[1];
              *v28 = *v25;
              a4 += 2;
              v25 += 2;
              v27 -= 2;
            }
            *a4 = 0;
            *v28 = 0;
            if ( a8 )
              *a8 = __ROR2__(v16[2], 8);
          }
        }
      }
    }
  }
LABEL_53:
  if ( a9 )
    *a9 = v16;
  return v10;
}

```

## disassembly

```asm
0x140035ab8  mov     [rsp+arg_0], rbx
0x140035abd  mov     [rsp+arg_8], rsi
0x140035ac2  mov     [rsp+arg_10], r8w
0x140035ac8  push    rdi
0x140035ac9  push    r12
0x140035acb  push    r13
0x140035acd  push    r14
0x140035acf  push    r15
0x140035ad1  sub     rsp, 70h
0x140035ad5  mov     r11, rcx
0x140035ad8  xor     edi, edi
0x140035ada  mov     ebx, edi
0x140035adc  mov     r15d, edi
0x140035adf  mov     r14d, edi
0x140035ae2  mov     esi, edi
0x140035ae4  mov     eax, edi
0x140035ae6  mov     [rsp+98h+var_70], rax
0x140035aeb  mov     r13d, edi
0x140035aee  mov     r8d, edi
0x140035af1  mov     [rsp+98h+var_90], rdi
0x140035af6  mov     r10d, edi
0x140035af9  mov     [rsp+98h+var_98], rdi
0x140035afd  cmp     edx, 12h
0x140035b00  jb      loc_140035DAF
0x140035b06  movzx   eax, word ptr [rcx]
0x140035b09  ror     ax, 8
0x140035b0d  test    ax, ax
0x140035b10  jnz     loc_140035DAF
0x140035b16  mov     r12d, edx
0x140035b19  add     r12, rcx
0x140035b1c  mov     rax, [rsp+98h+arg_40]
0x140035b24  test    rax, rax
0x140035b27  jnz     loc_140035D83
0x140035b2d  lea     rdx, [rcx+6]
0x140035b31  mov     [rsp+98h+var_78], rdx
0x140035b36  movzx   eax, word ptr [rcx+2]
0x140035b3a  shl     ax, 8
0x140035b3e  movzx   ecx, ax
0x140035b41  movzx   eax, byte ptr [r11+3]
0x140035b46  or      rcx, rax
0x140035b49  lea     rax, [rcx+rcx*2]
0x140035b4d  lea     rdi, [rdx+rax*4]
0x140035b51  cmp     rdi, r12
0x140035b54  ja      loc_140035DAF
0x140035b5a  mov     [rsp+98h+var_80], 3FFh
0x140035b62  cmp     rdx, rdi
0x140035b65  jnb     loc_140035C4D
0x140035b6b  movzx   r8d, word ptr [rdx+4]
0x140035b70  ror     r8w, 8
0x140035b75  movzx   ecx, [rsp+98h+arg_30]
0x140035b7d  xor     eax, eax
0x140035b7f  test    cx, cx
0x140035b82  cmovz   cx, r8w
0x140035b87  mov     [rsp+98h+arg_30], cx
0x140035b8f  movzx   eax, word ptr [rdx+6]
0x140035b93  ror     ax, 8
0x140035b97  cmp     ax, [rsp+98h+arg_10]
0x140035b9f  jz      short loc_140035BB1
0x140035ba1  mov     r8, [rsp+98h+var_90]
0x140035ba6  add     rdx, 0Ch
0x140035baa  mov     [rsp+98h+var_78], rdx
0x140035baf  jmp     short loc_140035B62
0x140035bb1  movzx   eax, word ptr [rdx]
0x140035bb4  ror     ax, 8
0x140035bb8  cmp     ax, 3
0x140035bbc  jnz     short loc_140035BA1
0x140035bbe  movzx   eax, word ptr [rdx+2]
0x140035bc2  ror     ax, 8
0x140035bc6  cmp     ax, 1
0x140035bca  jnz     short loc_140035BA1
0x140035bcc  cmp     r8w, cx
0x140035bd0  jz      short loc_140035C45
0x140035bd2  test    r15, r15
0x140035bd5  cmovz   r15, rdx
0x140035bd9  mov     [rsp+98h+var_58], r15
0x140035bde  movzx   eax, [rsp+98h+arg_30]
0x140035be6  mov     ecx, 3FFh
0x140035beb  and     ax, cx
0x140035bee  mov     rcx, [rsp+98h+var_70]
0x140035bf3  cmp     r8w, ax
0x140035bf7  cmovz   rcx, rdx
0x140035bfb  mov     [rsp+98h+var_70], rcx
0x140035c00  mov     [rsp+98h+var_50], rcx
0x140035c05  movzx   ecx, r8w
0x140035c09  and     cx, word ptr [rsp+98h+var_80]
0x140035c0e  cmp     cx, ax
0x140035c11  cmovz   rsi, rdx
0x140035c15  mov     [rsp+98h+var_48], rsi
0x140035c1a  xor     eax, eax
0x140035c1c  test    r8w, r8w
0x140035c20  cmovz   r13, rdx
0x140035c24  mov     [rsp+98h+var_40], r13
0x140035c29  mov     r8, [rsp+98h+var_90]
0x140035c2e  cmp     cx, 9
0x140035c32  cmovz   r8, rdx
0x140035c36  mov     [rsp+98h+var_90], r8
0x140035c3b  mov     [rsp+98h+var_38], r8
0x140035c40  jmp     loc_140035BA6
0x140035c45  mov     r14, rdx
0x140035c48  mov     r8, [rsp+98h+var_90]
0x140035c4d  xor     edi, edi
0x140035c4f  test    r15, r15
0x140035c52  cmovnz  r10, r15
0x140035c56  mov     [rsp+98h+var_98], r10
0x140035c5a  test    r8, r8
0x140035c5d  cmovnz  r10, r8
0x140035c61  mov     [rsp+98h+var_98], r10
0x140035c65  test    r13, r13
0x140035c68  cmovnz  r10, r13
0x140035c6c  mov     [rsp+98h+var_98], r10
0x140035c70  test    rsi, rsi
0x140035c73  cmovnz  r10, rsi
0x140035c77  mov     [rsp+98h+var_98], r10
0x140035c7b  mov     rax, [rsp+98h+var_70]
0x140035c80  test    rax, rax
0x140035c83  cmovnz  r10, rsi
0x140035c87  mov     [rsp+98h+var_98], r10
0x140035c8b  test    r14, r14
0x140035c8e  cmovnz  r10, r14
0x140035c92  mov     [rsp+98h+var_98], r10
0x140035c96  test    r10, r10
0x140035c99  jz      loc_140035DAF
0x140035c9f  movzx   eax, word ptr [r11+4]
0x140035ca4  shl     ax, 8
0x140035ca8  movzx   ecx, ax
0x140035cab  movzx   eax, byte ptr [r11+5]
0x140035cb0  or      rcx, rax
0x140035cb3  movzx   eax, word ptr [r10+0Ah]
0x140035cb8  shl     ax, 8
0x140035cbc  movzx   edx, ax
0x140035cbf  movzx   eax, byte ptr [r10+0Bh]
0x140035cc4  or      rdx, rax
0x140035cc7  lea     rax, [r11+rcx]
0x140035ccb  add     rdx, rax
0x140035cce  mov     [rsp+98h+var_60], rdx
0x140035cd3  mov     [rsp+98h+var_88], r9
0x140035cd8  movzx   eax, word ptr [r10+8]
0x140035cdd  ror     ax, 8
0x140035ce1  movzx   r8d, ax
0x140035ce5  lea     rax, [rdx+r8]
0x140035ce9  cmp     rax, r12
0x140035cec  ja      loc_140035DAF
0x140035cf2  mov     ecx, [rsp+98h+arg_20]
0x140035cf9  and     ecx, 0FFFFFFFEh
0x140035cfc  lea     esi, [rdi+2]
0x140035cff  lea     eax, [rsi+r8]
0x140035d03  cmp     eax, ecx
0x140035d05  ja      loc_140035D9D
0x140035d0b  movzx   ecx, r8w
0x140035d0f  test    cl, 1
0x140035d12  jnz     loc_140035DAF
0x140035d18  movzx   ebx, cx
0x140035d1b  add     ebx, esi
0x140035d1d  mov     [rsp+98h+var_68], ebx
0x140035d21  lea     r8, [r9+1]
0x140035d25  lea     r11, [r8+1]
0x140035d29  test    cx, cx
0x140035d2c  jz      short loc_140035D58
0x140035d2e  mov     al, [rdx+1]
0x140035d31  mov     [r9], al
0x140035d34  mov     [rsp+98h+var_88], r8
0x140035d39  mov     al, [rdx]
0x140035d3b  mov     [r8], al
0x140035d3e  mov     r9, r11
0x140035d41  mov     [rsp+98h+var_88], r11
0x140035d46  add     rdx, rsi
0x140035d49  mov     [rsp+98h+var_60], rdx
0x140035d4e  mov     eax, 0FFFEh
0x140035d53  add     cx, ax
0x140035d56  jmp     short loc_140035D21
0x140035d58  mov     [r9], dil
0x140035d5b  mov     [rsp+98h+var_88], r8
0x140035d60  mov     [r8], dil
0x140035d63  mov     [rsp+98h+var_88], r11
0x140035d68  mov     rcx, [rsp+98h+arg_38]
0x140035d70  test    rcx, rcx
0x140035d73  jz      short loc_140035DAF
0x140035d75  movzx   eax, word ptr [r10+4]
0x140035d7a  ror     ax, 8
0x140035d7e  mov     [rcx], ax
0x140035d81  jmp     short loc_140035DAF
0x140035d83  mov     rdx, [rax]
0x140035d86  test    rdx, rdx
0x140035d89  jz      loc_140035B2D
0x140035d8f  mov     [rsp+98h+var_78], rdx
0x140035d94  add     rdx, 0Ch
0x140035d98  jmp     loc_140035B31
0x140035d9d  cmp     [rsp+98h+arg_28], dil
0x140035da5  jz      short loc_140035DAF
0x140035da7  sub     cx, si
0x140035daa  jmp     loc_140035D0F
0x140035daf  mov     rax, [rsp+98h+arg_40]
0x140035db7  test    rax, rax
0x140035dba  jnz     short loc_140035DD8
0x140035dbc  mov     eax, ebx
0x140035dbe  lea     r11, [rsp+98h+var_28]
0x140035dc3  mov     rbx, [r11+30h]
0x140035dc7  mov     rsi, [r11+38h]
0x140035dcb  mov     rsp, r11
0x140035dce  pop     r15
0x140035dd0  pop     r14
0x140035dd2  pop     r13
0x140035dd4  pop     r12
0x140035dd6  pop     rdi
0x140035dd7  retn
0x140035dd8  mov     [rax], r10
0x140035ddb  jmp     short loc_140035DBC
0x140096937  push    rbp
0x140096939  mov     rbp, rdx
0x14009693c  mov     rcx, [rbp+0E0h]
0x140096943  test    rcx, rcx
0x140096946  jz      short loc_14009694F
0x140096948  mov     rax, [rbp+0]
0x14009694c  mov     [rcx], rax
0x14009694f  pop     rbp
0x140096950  retn
```
