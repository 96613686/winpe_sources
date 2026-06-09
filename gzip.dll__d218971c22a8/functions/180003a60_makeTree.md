# makeTree

- ea: `0x180003a60`
- end: `0x180003ddf`
- name: `makeTree`
- size: `895`
- prototype: `__int64 __fastcall(int, int, _WORD *, _WORD *, __int64)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x1800026e0`
- `0x180003930`
- `0x180003a60`
- `0x180004220`
- `0x180005cf8`
- `0x180005e58`

## callees

- `0x180003860`
- `0x180003a60`
- `0x1800040d0`
- `0x1800045c0`
- `0x180006ad5`
- `0x180006b00`

## pseudocode

```c
__int64 __fastcall makeTree(int a1, int a2, _WORD *a3, _WORD *a4, __int64 a5)
{
  __int64 v9; // r8
  int v10; // edx
  int v11; // eax
  _WORD *v12; // r9
  int v13; // ebx
  int v14; // r13d
  _WORD *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rax
  int v18; // r8d
  int v19; // edx
  int v20; // ebx
  __int64 v21; // r11
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r9
  int v25; // r14d
  __int64 v26; // r15
  int v27; // r8d
  int v28; // r11d
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  _DWORD v35[577]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v36[288]; // [rsp+944h] [rbp+844h]
  int v37; // [rsp+DC4h] [rbp+CC4h]
  int v38; // [rsp+DC8h] [rbp+CC8h]
  _WORD *v39; // [rsp+DD0h] [rbp+CD0h]
  _WORD *v40; // [rsp+DD8h] [rbp+CD8h]
  _WORD *v41; // [rsp+DE0h] [rbp+CE0h]
  int v42; // [rsp+DECh] [rbp+CECh]
  char v43[80]; // [rsp+DF0h] [rbp+CF0h] BYREF

  memset_0(v35, 0, 0xDF8u);
  v10 = 0;
  v39 = a3;
  v11 = 0;
  v40 = a4;
  v37 = a1;
  v12 = a3;
  v38 = a2;
  v42 = 0;
  v36[0] = 0;
  if ( a1 <= 0 )
    goto LABEL_34;
  do
  {
    *(_BYTE *)(v11 + a5) = 0;
    if ( v12[v11] )
    {
      v42 = v10 + 1;
      v35[v42 + 576] = v11;
      v10 = v42;
      v12 = v39;
    }
    ++v11;
  }
  while ( v11 < v37 );
  if ( v10 < 2 )
  {
    if ( v10 )
    {
      if ( v36[0] )
        *v12 = 1;
      else
        v12[1] = 1;
      return makeTree(a1, a2, (_DWORD)a3, (_DWORD)a4, a5);
    }
LABEL_34:
    *v12 = 1;
    v39[1] = 1;
    return makeTree(a1, a2, (_DWORD)a3, (_DWORD)a4, a5);
  }
  v13 = v10 >> 1;
  v14 = a1;
  if ( v10 >> 1 >= 1 )
  {
    do
      downHeap(v35, (unsigned int)v13--, v9, v12);
    while ( v13 >= 1 );
    v10 = v42;
    v12 = v39;
  }
  v15 = v40;
  v41 = v40;
  while ( 1 )
  {
    v16 = v36[0];
    if ( v36[0] < v37 )
    {
      *v15 = v36[0];
      ++v41;
      v10 = v42;
      v12 = v39;
    }
    v17 = v10;
    v18 = 2;
    v19 = v10 - 1;
    v20 = 1;
    v21 = (int)v35[v17 + 576];
    v36[0] = v35[v17 + 576];
    v42 = v19;
    if ( v19 >= 2 )
    {
      while ( 1 )
      {
        if ( v18 < v19 && v12[v35[v18 + 576]] > v12[v36[v18]] )
          ++v18;
        v22 = (int)v35[v18 + 576];
        if ( v12[v21] <= v12[v22] )
          break;
        v23 = v20;
        v20 = v18;
        v18 *= 2;
        v35[v23 + 576] = v22;
        v19 = v42;
        if ( v18 > v42 )
          break;
        v12 = v39;
      }
    }
    v35[v20 + 576] = v21;
    v24 = v36[0];
    if ( v36[0] < v37 )
      *v41++ = v36[0];
    v25 = v14;
    v26 = v14;
    v27 = 2;
    ++v14;
    v28 = 1;
    v39[v26] = v39[v16] + v39[v24];
    v29 = v42;
    v36[0] = v26;
    if ( v42 >= 2 )
    {
      do
      {
        if ( v27 < v29 && v39[v35[v27 + 576]] > v39[v36[v27]] )
          ++v27;
        v30 = (int)v35[v27 + 576];
        if ( v39[v26] <= v39[v30] )
          break;
        v31 = v28;
        v28 = v27;
        v27 *= 2;
        v35[v31 + 576] = v30;
        v29 = v42;
      }
      while ( v27 <= v42 );
    }
    v35[v28 + 576] = v25;
    v35[v26] = v16 | ((_DWORD)v24 << 16);
    v10 = v42;
    if ( v42 <= 1 )
      break;
    v15 = v41;
    v12 = v39;
  }
  v41 = v40;
  makeLen(v35, (unsigned int)v26, a5);
  return makeCode((unsigned int)a1, v43, a5, a4);
}

```

## disassembly

```asm
0x180003a60  push    rbp
0x180003a62  push    rbx
0x180003a63  push    rsi
0x180003a64  push    rdi
0x180003a65  push    r12
0x180003a67  push    r14
0x180003a69  push    r15
0x180003a6b  lea     rbp, [rsp-0D60h]
0x180003a73  sub     rsp, 0E60h
0x180003a7a  mov     rax, cs:__security_cookie
0x180003a81  xor     rax, rsp
0x180003a84  mov     [rbp+0D90h+var_50], rax
0x180003a8b  mov     rdi, [rbp+0D90h+arg_20]
0x180003a92  mov     rsi, r8
0x180003a95  mov     ebx, edx
0x180003a97  mov     [rsp+0E90h+var_E60], ecx
0x180003a9b  mov     r14d, ecx
0x180003a9e  mov     [rsp+0E90h+var_E58], r9
0x180003aa3  xor     edx, edx; Val
0x180003aa5  lea     rcx, [rsp+0E90h+var_E50]; void *
0x180003aaa  mov     r8d, 0DF8h; Size
0x180003ab0  mov     r15, r9
0x180003ab3  call    memset_0
0x180003ab8  xor     edx, edx
0x180003aba  mov     [rbp+0D90h+var_C0], rsi
0x180003ac1  xor     eax, eax
0x180003ac3  mov     [rbp+0D90h+var_B8], r15
0x180003aca  mov     [rbp+0D90h+var_CC], r14d
0x180003ad1  mov     r9, rsi
0x180003ad4  mov     [rbp+0D90h+var_C8], ebx
0x180003ada  mov     [rbp+0D90h+var_A4], edx
0x180003ae0  mov     [rbp+0D90h+var_54C], edx
0x180003ae6  test    r14d, r14d
0x180003ae9  jle     loc_180003D93
0x180003aef  nop
0x180003af0  movsxd  rcx, eax
0x180003af3  mov     byte ptr [rcx+rdi], 0
0x180003af7  cmp     word ptr [r9+rcx*2], 0
0x180003afd  jz      short loc_180003B1E
0x180003aff  inc     edx
0x180003b01  movsxd  rcx, edx
0x180003b04  mov     [rbp+0D90h+var_A4], edx
0x180003b0a  mov     [rbp+rcx*4+0D90h+var_550], eax
0x180003b11  mov     edx, [rbp+0D90h+var_A4]
0x180003b17  mov     r9, [rbp+0D90h+var_C0]
0x180003b1e  inc     eax
0x180003b20  cmp     eax, [rbp+0D90h+var_CC]
0x180003b26  jl      short loc_180003AF0
0x180003b28  cmp     edx, 2
0x180003b2b  jge     short loc_180003B55
0x180003b2d  test    edx, edx
0x180003b2f  jz      loc_180003D93
0x180003b35  cmp     [rbp+0D90h+var_54C], 0
0x180003b3c  jnz     short loc_180003B4A
0x180003b3e  mov     word ptr [r9+2], 1
0x180003b45  jmp     loc_180003DA9
0x180003b4a  mov     word ptr [r9], 1
0x180003b50  jmp     loc_180003DA9
0x180003b55  mov     ebx, edx
0x180003b57  mov     [rsp+0E90h+var_38], r13
0x180003b5f  sar     ebx, 1
0x180003b61  mov     r13d, r14d
0x180003b64  cmp     ebx, 1
0x180003b67  jl      short loc_180003B89
0x180003b69  mov     edx, ebx
0x180003b6b  lea     rcx, [rsp+0E90h+var_E50]
0x180003b70  call    downHeap
0x180003b75  dec     ebx
0x180003b77  cmp     ebx, 1
0x180003b7a  jge     short loc_180003B69
0x180003b7c  mov     edx, [rbp+0D90h+var_A4]
0x180003b82  mov     r9, [rbp+0D90h+var_C0]
0x180003b89  mov     rax, [rbp+0D90h+var_B8]
0x180003b90  mov     r12d, 1
0x180003b96  mov     [rbp+0D90h+var_B0], rax
0x180003b9d  nop     dword ptr [rax]
0x180003ba0  movsxd  rsi, [rbp+0D90h+var_54C]
0x180003ba7  cmp     esi, [rbp+0D90h+var_CC]
0x180003bad  jge     short loc_180003BC7
0x180003baf  mov     [rax], si
0x180003bb2  add     [rbp+0D90h+var_B0], 2
0x180003bba  mov     edx, [rbp+0D90h+var_A4]
0x180003bc0  mov     r9, [rbp+0D90h+var_C0]
0x180003bc7  movsxd  rax, edx
0x180003bca  mov     r8d, 2
0x180003bd0  dec     edx
0x180003bd2  mov     ebx, r12d
0x180003bd5  movsxd  r11, [rbp+rax*4+0D90h+var_550]
0x180003bdd  mov     [rbp+0D90h+var_54C], r11d
0x180003be4  mov     [rbp+0D90h+var_A4], edx
0x180003bea  cmp     edx, r8d
0x180003bed  jl      short loc_180003C57
0x180003bef  mov     r10, r11
0x180003bf2  add     r10, r10
0x180003bf5  cmp     r8d, edx
0x180003bf8  jge     short loc_180003C1C
0x180003bfa  movsxd  rax, r8d
0x180003bfd  movsxd  rdx, [rbp+rax*4+0D90h+var_550]
0x180003c05  movsxd  rcx, [rbp+rax*4+0D90h+var_54C]
0x180003c0d  movzx   eax, word ptr [r9+rcx*2]
0x180003c12  cmp     [r9+rdx*2], ax
0x180003c17  jbe     short loc_180003C1C
0x180003c19  inc     r8d
0x180003c1c  movsxd  rax, r8d
0x180003c1f  movsxd  rdx, [rbp+rax*4+0D90h+var_550]
0x180003c27  movzx   ecx, word ptr [r9+rdx*2]
0x180003c2c  cmp     [r10+r9], cx
0x180003c31  jbe     short loc_180003C57
0x180003c33  movsxd  rax, ebx
0x180003c36  mov     ebx, r8d
0x180003c39  add     r8d, r8d
0x180003c3c  mov     [rbp+rax*4+0D90h+var_550], edx
0x180003c43  mov     edx, [rbp+0D90h+var_A4]
0x180003c49  cmp     r8d, edx
0x180003c4c  jg      short loc_180003C57
0x180003c4e  mov     r9, [rbp+0D90h+var_C0]
0x180003c55  jmp     short loc_180003BF5
0x180003c57  movsxd  rax, ebx
0x180003c5a  mov     [rbp+rax*4+0D90h+var_550], r11d
0x180003c62  movsxd  r9, [rbp+0D90h+var_54C]
0x180003c69  cmp     r9d, [rbp+0D90h+var_CC]
0x180003c70  jge     short loc_180003C85
0x180003c72  mov     rax, [rbp+0D90h+var_B0]
0x180003c79  mov     [rax], r9w
0x180003c7d  add     [rbp+0D90h+var_B0], 2
0x180003c85  mov     rdx, [rbp+0D90h+var_C0]
0x180003c8c  mov     r14d, r13d
0x180003c8f  movsxd  r15, r13d
0x180003c92  mov     r8d, 2
0x180003c98  inc     r13d
0x180003c9b  mov     r11d, r12d
0x180003c9e  movzx   ecx, word ptr [rdx+r9*2]
0x180003ca3  add     cx, [rdx+rsi*2]
0x180003ca7  mov     [rdx+r15*2], cx
0x180003cac  mov     eax, [rbp+0D90h+var_A4]
0x180003cb2  mov     [rbp+0D90h+var_54C], r15d
0x180003cb9  cmp     eax, r8d
0x180003cbc  jl      short loc_180003D1E
0x180003cbe  mov     r10, [rbp+0D90h+var_C0]
0x180003cc5  cmp     r8d, eax
0x180003cc8  jge     short loc_180003CEC
0x180003cca  movsxd  rax, r8d
0x180003ccd  movsxd  rdx, [rbp+rax*4+0D90h+var_550]
0x180003cd5  movsxd  rcx, [rbp+rax*4+0D90h+var_54C]
0x180003cdd  movzx   eax, word ptr [r10+rcx*2]
0x180003ce2  cmp     [r10+rdx*2], ax
0x180003ce7  jbe     short loc_180003CEC
0x180003ce9  inc     r8d
0x180003cec  movsxd  rax, r8d
0x180003cef  movsxd  rdx, [rbp+rax*4+0D90h+var_550]
0x180003cf7  movzx   ecx, word ptr [r10+rdx*2]
0x180003cfc  cmp     [r10+r15*2], cx
0x180003d01  jbe     short loc_180003D1E
0x180003d03  movsxd  rax, r11d
0x180003d06  mov     r11d, r8d
0x180003d09  add     r8d, r8d
0x180003d0c  mov     [rbp+rax*4+0D90h+var_550], edx
0x180003d13  mov     eax, [rbp+0D90h+var_A4]
0x180003d19  cmp     r8d, eax
0x180003d1c  jle     short loc_180003CBE
0x180003d1e  shl     r9d, 10h
0x180003d22  or      r9d, esi
0x180003d25  movsxd  rax, r11d
0x180003d28  mov     [rbp+rax*4+0D90h+var_550], r14d
0x180003d30  mov     [rsp+r15*4+0E90h+var_E50], r9d
0x180003d35  mov     edx, [rbp+0D90h+var_A4]
0x180003d3b  cmp     edx, r12d
0x180003d3e  jle     short loc_180003D53
0x180003d40  mov     rax, [rbp+0D90h+var_B0]
0x180003d47  mov     r9, [rbp+0D90h+var_C0]
0x180003d4e  jmp     loc_180003BA0
0x180003d53  mov     rax, [rbp+0D90h+var_B8]
0x180003d5a  lea     rcx, [rsp+0E90h+var_E50]
0x180003d5f  mov     r8, rdi
0x180003d62  mov     [rbp+0D90h+var_B0], rax
0x180003d69  mov     edx, r15d
0x180003d6c  call    makeLen
0x180003d71  mov     r9, [rsp+0E90h+var_E58]
0x180003d76  lea     rdx, [rbp+0D90h+var_A0]
0x180003d7d  mov     ecx, [rsp+0E90h+var_E60]
0x180003d81  mov     r8, rdi
0x180003d84  call    makeCode
0x180003d89  mov     r13, [rsp+0E90h+var_38]
0x180003d91  jmp     short loc_180003DBE
0x180003d93  mov     r12d, 1
0x180003d99  mov     [r9], r12w
0x180003d9d  mov     rax, [rbp+0D90h+var_C0]
0x180003da4  mov     [rax+2], r12w
0x180003da9  mov     r9, r15
0x180003dac  mov     [rsp+0E90h+var_E70], rdi
0x180003db1  mov     r8, rsi
0x180003db4  mov     edx, ebx
0x180003db6  mov     ecx, r14d
0x180003db9  call    makeTree
0x180003dbe  mov     rcx, [rbp+0D90h+var_50]
0x180003dc5  xor     rcx, rsp; StackCookie
0x180003dc8  call    __security_check_cookie
0x180003dcd  add     rsp, 0E60h
0x180003dd4  pop     r15
0x180003dd6  pop     r14
0x180003dd8  pop     r12
0x180003dda  pop     rdi
0x180003ddb  pop     rsi
0x180003ddc  pop     rbx
0x180003ddd  pop     rbp
0x180003dde  retn
```
