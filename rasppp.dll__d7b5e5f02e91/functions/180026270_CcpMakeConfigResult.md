# CcpMakeConfigResult

- ea: `0x180026270`
- end: `0x1800264e0`
- name: `CcpMakeConfigResult`
- size: `624`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800062f0`
- `0x1800258b0`
- `0x180026270`
- `0x1800264e8`
- `0x180033a80`

## pseudocode

```c
__int64 __fastcall CcpMakeConfigResult(_DWORD *a1, unsigned __int8 *a2, char *a3, int a4, int a5)
{
  _BYTE *v5; // r14
  unsigned int v7; // ecx
  ULONG v8; // esi
  unsigned __int8 *v9; // r13
  int *v10; // rdi
  int v11; // eax
  int v12; // edx
  unsigned int v14; // edx
  int v15; // ebx
  char v16; // r12
  __int64 result; // rax
  int v18; // ecx
  int v19; // eax
  int v20; // eax
  unsigned int v21; // edx
  char v22; // al
  unsigned int v23; // r14d
  __int64 v24; // rdx
  unsigned __int8 *v25; // r8
  __int16 v26; // r9
  ULONG v27; // [rsp+30h] [rbp-58h]
  int v28; // [rsp+34h] [rbp-54h]
  ULONG pulResult; // [rsp+90h] [rbp+8h] BYREF
  unsigned int v30; // [rsp+98h] [rbp+10h]
  int v31; // [rsp+A0h] [rbp+18h] BYREF
  int v32; // [rsp+A8h] [rbp+20h]

  v32 = a4;
  v5 = a2 + 4;
  v7 = 0;
  v27 = a4 - 4;
  v8 = a4 - 4;
  pulResult = a4 - 4;
  v9 = (unsigned __int8 *)(a3 + 4);
  v10 = a1 + 287;
  v11 = a2[3] - 4;
  v12 = a2[2] << 8;
  v31 = 0;
  v14 = v11 + v12;
  a1[287] = 0;
  v15 = 2;
  v16 = 3;
  while ( 1 )
  {
    v30 = v7;
    if ( v14 < 2 )
      break;
    v28 = v14 - (unsigned __int8)v5[1];
    if ( v28 < 0 )
      return 722;
    result = CcpCheckOption(a1, (__int64)(a1 + 194), v5, &v31, 1);
    if ( (_DWORD)result )
      return result;
    v18 = v31;
    if ( v15 == 2 && v31 != 2 )
      goto LABEL_9;
    if ( v15 != 3 )
      goto LABEL_10;
    if ( v31 == 4 )
    {
LABEL_9:
      v8 = v27;
      v9 = (unsigned __int8 *)(a3 + 4);
      pulResult = v27;
      v15 = v31;
LABEL_10:
      if ( v31 == 4 )
        goto LABEL_18;
    }
    if ( *v5 != 0xFF )
    {
      v19 = *v10;
      if ( *v5 )
      {
        if ( *v5 == 18 )
          v20 = v19 | 1;
        else
          v20 = v19 | 4;
      }
      else
      {
        v20 = v19 | 2;
      }
      *v10 = v20;
    }
LABEL_18:
    if ( v18 == v15 && (v18 == 4 || v18 == 3 && a5) )
    {
      if ( ULongSub(v8, (unsigned __int8)v5[1], &pulResult) < 0 )
        return 722;
      memcpy_0(v9, v5, v21);
      v8 = pulResult;
      v9 += v9[1];
    }
    v7 = v30 + 1;
    v14 = v28;
    v5 += (unsigned __int8)v5[1];
  }
  if ( v15 != 3 || (v22 = 4, !a5) )
    v22 = v15;
  *a3 = v22;
  if ( !v7 && a1[4] )
  {
    v23 = 1;
    *v10 = 1;
    v15 = 3;
    goto LABEL_34;
  }
  if ( (unsigned int)(v15 - 2) <= 1 && v7 )
  {
    v23 = v30;
LABEL_34:
    if ( (*(_BYTE *)v10 & 1) != 0 )
    {
      *v10 = 1;
      v24 = 18;
      v25 = v9;
    }
    else
    {
      v25 = v9;
      if ( (*(_BYTE *)v10 & 2) != 0 )
      {
        *v10 = 2;
        v24 = 0;
      }
      else
      {
        *v10 = 4;
        v24 = 254;
      }
    }
    result = CcpMakeOption(a1 + 287, v24, v25, v8);
    if ( !(_DWORD)result )
    {
      if ( v23 <= 1 || v15 != 2 )
        v16 = v15;
      *a3 = v16;
      if ( ULongSub(v8, v9[1], &pulResult) < 0 )
        return 722;
      LOWORD(v8) = pulResult;
      goto LABEL_46;
    }
  }
  else
  {
LABEL_46:
    if ( *a3 == 4 )
      a1[6] = a1[7];
    else
      a1[7] = a1[6];
    v26 = v32 - v8;
    a3[3] = v32 - v8;
    a3[2] = HIBYTE(v26);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180026270  mov     r11, rsp
0x180026273  mov     [r11+20h], r9d
0x180026277  push    rbx
0x180026278  push    rbp
0x180026279  push    rsi
0x18002627a  push    rdi
0x18002627b  push    r12
0x18002627d  push    r13
0x18002627f  push    r14
0x180026281  push    r15
0x180026283  sub     rsp, 48h
0x180026287  mov     rax, rdx
0x18002628a  lea     r14, [rdx+4]
0x18002628e  lea     edx, [r9-4]
0x180026292  mov     rbp, rcx
0x180026295  xor     ecx, ecx
0x180026297  mov     [rsp+88h+var_58], edx
0x18002629b  mov     esi, edx
0x18002629d  mov     [r11+8], edx
0x1800262a1  movzx   edx, byte ptr [rax+2]
0x1800262a5  lea     r13, [r8+4]
0x1800262a9  movzx   eax, byte ptr [rax+3]
0x1800262ad  lea     rdi, [rbp+47Ch]
0x1800262b4  add     eax, 0FFFFFFFCh
0x1800262b7  shl     edx, 8
0x1800262ba  mov     r15, r8
0x1800262bd  mov     [r11+18h], ecx
0x1800262c1  add     edx, eax
0x1800262c3  mov     [rdi], ecx
0x1800262c5  lea     ebx, [rcx+2]
0x1800262c8  lea     r8d, [rcx+1]
0x1800262cc  lea     r12d, [rcx+3]
0x1800262d0  mov     [rsp+88h+arg_8], ecx
0x1800262d7  cmp     edx, 2
0x1800262da  jb      loc_1800263DD
0x1800262e0  movzx   eax, byte ptr [r14+1]
0x1800262e5  sub     edx, eax
0x1800262e7  mov     [rsp+88h+var_54], edx
0x1800262eb  js      loc_18002646F
0x1800262f1  mov     [rsp+88h+var_68], r8d
0x1800262f6  lea     rdx, [rbp+308h]
0x1800262fd  mov     r8, r14
0x180026300  lea     r9, [rsp+88h+arg_10]
0x180026308  mov     rcx, rbp
0x18002630b  call    CcpCheckOption
0x180026310  test    eax, eax
0x180026312  jnz     loc_1800264CE
0x180026318  mov     ecx, [rsp+88h+arg_10]
0x18002631f  cmp     ebx, 2
0x180026322  jnz     short loc_180026328
0x180026324  cmp     ecx, ebx
0x180026326  jnz     short loc_180026332
0x180026328  cmp     ebx, r12d
0x18002632b  jnz     short loc_180026343
0x18002632d  cmp     ecx, 4
0x180026330  jnz     short loc_180026348
0x180026332  mov     esi, [rsp+88h+var_58]
0x180026336  lea     r13, [r15+4]
0x18002633a  mov     [rsp+88h+pulResult], esi
0x180026341  mov     ebx, ecx
0x180026343  cmp     ecx, 4
0x180026346  jz      short loc_18002636B
0x180026348  cmp     byte ptr [r14], 0FEh
0x18002634c  ja      short loc_18002636B
0x18002634e  cmp     byte ptr [r14], 0
0x180026352  mov     eax, [rdi]
0x180026354  jz      short loc_180026366
0x180026356  cmp     byte ptr [r14], 12h
0x18002635a  jz      short loc_180026361
0x18002635c  or      eax, 4
0x18002635f  jmp     short loc_180026369
0x180026361  or      eax, 1
0x180026364  jmp     short loc_180026369
0x180026366  or      eax, 2
0x180026369  mov     [rdi], eax
0x18002636b  cmp     ecx, ebx
0x18002636d  jnz     short loc_1800263BC
0x18002636f  cmp     ecx, 4
0x180026372  jz      short loc_180026383
0x180026374  cmp     ecx, r12d
0x180026377  jnz     short loc_1800263BC
0x180026379  cmp     [rsp+88h+arg_20], 0
0x180026381  jz      short loc_1800263BC
0x180026383  movzx   edx, byte ptr [r14+1]; ulSubtrahend
0x180026388  lea     r8, [rsp+88h+pulResult]; pulResult
0x180026390  mov     ecx, esi; ulMinuend
0x180026392  call    ULongSub
0x180026397  test    eax, eax
0x180026399  js      loc_18002646F
0x18002639f  mov     r8d, edx; Size
0x1800263a2  mov     rcx, r13; void *
0x1800263a5  mov     rdx, r14; Src
0x1800263a8  call    memcpy_0
0x1800263ad  movzx   eax, byte ptr [r13+1]
0x1800263b2  mov     esi, [rsp+88h+pulResult]
0x1800263b9  add     r13, rax
0x1800263bc  mov     ecx, [rsp+88h+arg_8]
0x1800263c3  mov     r8d, 1
0x1800263c9  movzx   eax, byte ptr [r14+1]
0x1800263ce  add     ecx, r8d
0x1800263d1  mov     edx, [rsp+88h+var_54]
0x1800263d5  add     r14, rax
0x1800263d8  jmp     loc_1800262D0
0x1800263dd  cmp     ebx, r12d
0x1800263e0  jnz     short loc_1800263EE
0x1800263e2  cmp     [rsp+88h+arg_20], 0
0x1800263ea  mov     al, 4
0x1800263ec  jnz     short loc_1800263F0
0x1800263ee  mov     al, bl
0x1800263f0  mov     [r15], al
0x1800263f3  test    ecx, ecx
0x1800263f5  jnz     short loc_180026407
0x1800263f7  cmp     [rbp+10h], ecx
0x1800263fa  jz      short loc_180026407
0x1800263fc  mov     r14d, r8d
0x1800263ff  mov     [rdi], r8d
0x180026402  mov     ebx, r12d
0x180026405  jmp     short loc_180026423
0x180026407  lea     eax, [rbx-2]
0x18002640a  cmp     eax, r8d
0x18002640d  ja      loc_18002649C
0x180026413  test    ecx, ecx
0x180026415  jz      loc_18002649C
0x18002641b  mov     r14d, [rsp+88h+arg_8]
0x180026423  mov     r9d, esi
0x180026426  mov     rcx, rdi
0x180026429  test    [rdi], r8b
0x18002642c  jz      short loc_180026476
0x18002642e  mov     [rdi], r8d
0x180026431  mov     edx, 12h
0x180026436  mov     r8, r13
0x180026439  call    CcpMakeOption
0x18002643e  test    eax, eax
0x180026440  jnz     loc_1800264CE
0x180026446  cmp     r14d, 1
0x18002644a  jbe     short loc_180026451
0x18002644c  cmp     ebx, 2
0x18002644f  jz      short loc_180026454
0x180026451  mov     r12b, bl
0x180026454  mov     [r15], r12b
0x180026457  lea     r8, [rsp+88h+pulResult]; pulResult
0x18002645f  movzx   edx, byte ptr [r13+1]; ulSubtrahend
0x180026464  mov     ecx, esi; ulMinuend
0x180026466  call    ULongSub
0x18002646b  test    eax, eax
0x18002646d  jns     short loc_180026495
0x18002646f  mov     eax, 2D2h
0x180026474  jmp     short loc_1800264CE
0x180026476  test    byte ptr [rdi], 2
0x180026479  mov     r8, r13
0x18002647c  jz      short loc_180026488
0x18002647e  mov     dword ptr [rdi], 2
0x180026484  xor     edx, edx
0x180026486  jmp     short loc_180026439
0x180026488  mov     dword ptr [rdi], 4
0x18002648e  mov     edx, 0FEh
0x180026493  jmp     short loc_180026439
0x180026495  mov     esi, [rsp+88h+pulResult]
0x18002649c  cmp     byte ptr [r15], 4
0x1800264a0  jnz     short loc_1800264AA
0x1800264a2  mov     eax, [rbp+1Ch]
0x1800264a5  mov     [rbp+18h], eax
0x1800264a8  jmp     short loc_1800264B0
0x1800264aa  mov     eax, [rbp+18h]
0x1800264ad  mov     [rbp+1Ch], eax
0x1800264b0  mov     r9d, [rsp+88h+arg_18]
0x1800264b8  sub     r9w, si
0x1800264bc  movzx   eax, r9w
0x1800264c0  mov     [r15+3], r9b
0x1800264c4  shr     ax, 8
0x1800264c8  mov     [r15+2], al
0x1800264cc  xor     eax, eax
0x1800264ce  add     rsp, 48h
0x1800264d2  pop     r15
0x1800264d4  pop     r14
0x1800264d6  pop     r13
0x1800264d8  pop     r12
0x1800264da  pop     rdi
0x1800264db  pop     rsi
0x1800264dc  pop     rbp
0x1800264dd  pop     rbx
0x1800264de  retn
```
