# ConvertFromBufferToClassInfo

- ea: `0x1800074a8`
- end: `0x180007736`
- name: `ConvertFromBufferToClassInfo`
- size: `654`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e10`

## callees

- `0x1800074a8`
- `0x18000773c`
- `0x180007891`
- `0x18000809c`
- `0x1800082d0`

## pseudocode

```c
__int64 __fastcall ConvertFromBufferToClassInfo(unsigned __int8 *a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  int v4; // r12d
  unsigned int v5; // esi
  __int64 v6; // rdi
  unsigned __int8 *i; // rdx
  int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r11d
  unsigned __int8 *v15; // r10
  int v16; // eax
  int v17; // r9d
  int v18; // esi
  unsigned __int8 *v19; // r11
  int v20; // eax
  int v21; // edx
  unsigned int v22; // ecx
  unsigned int v23; // ebx
  char *v24; // rdx
  char *v25; // rsi
  __int64 v26; // rbp
  unsigned __int8 *v27; // rdi
  __int64 v28; // r13
  unsigned int v29; // ebx
  __int64 v30; // rdx
  unsigned __int8 *v31; // r12
  int v32; // ebx
  int v33; // eax
  char *v34; // rdi
  size_t v35; // rsi
  char *v36; // rax
  char *v37; // rdi
  __int64 v38; // r12
  char *v41; // [rsp+80h] [rbp+8h]
  char *v42; // [rsp+80h] [rbp+8h]

  v4 = 0;
  v5 = 0;
  LODWORD(v6) = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_dd(a1, 10, WPP_36a3d2b25b333c88c463e99d733f09dc_Traceguids, a2, *a4);
  for ( i = a1; ; i = &v19[v21 + 2] )
  {
    if ( v5 + 2 > a2 )
      goto LABEL_23;
    v12 = i[1] + (*i << 8);
    if ( !v12 )
      goto LABEL_23;
    v13 = (v12 + 3) & 0xFFFFFFFC;
    v14 = v5 + v13 + 2;
    if ( v14 + 2 > a2 )
      goto LABEL_23;
    v15 = &i[v13 + 2];
    v16 = v15[1];
    v17 = v16 + (*v15 << 8);
    if ( (v16 & 1) != 0
      || (v18 = v17 + v14, v17 + v14 + 4 > a2)
      || (v19 = &v15[v17 + 2], v20 = v19[1], v21 = v20 + (*v19 << 8), (v20 & 1) != 0)
      || (v5 = v21 + v18 + 4, v5 + 2 > a2) )
    {
LABEL_23:
      v23 = 1359;
      goto LABEL_24;
    }
    v6 = (unsigned int)(v6 + 1);
    v4 += v13 + v21 + v17 + 4;
    if ( v5 >= a2 )
      break;
  }
  v22 = v4 + 40 * v6;
  if ( *a4 >= v22 )
  {
    v24 = (char *)a1;
    v25 = (char *)(a3 + 40 * v6);
    *a4 = v6;
    v26 = 0;
    do
    {
      v27 = (unsigned __int8 *)(v24 + 2);
      v28 = 5 * v26;
      *(_DWORD *)(a3 + 8 * v28) = 0;
      v29 = (unsigned __int8)v24[1] + ((unsigned __int8)*v24 << 8);
      *(_QWORD *)(a3 + 8 * v28 + 24) = v25;
      *(_DWORD *)(a3 + 8 * v28 + 32) = v29;
      memcpy_0(v25, v24 + 2, v29);
      v30 = (v29 + 3) & 0xFFFFFFFC;
      v31 = &v27[v30 + 2];
      v41 = (char *)v31;
      v32 = v27[v30];
      v33 = v27[v30 + 1];
      v34 = &v25[v30];
      *(_QWORD *)(a3 + 40 * v26 + 8) = &v25[v30];
      v35 = (unsigned int)(v33 + (v32 << 8));
      memcpy_0(v34, v31, v35);
      v23 = ConvertNetworkString(v34, v35);
      if ( v23 )
        break;
      *(_WORD *)&v34[v35] = 0;
      v36 = (char *)&v31[v35 + 2];
      v37 = &v34[v35 + 2];
      v38 = (v31[v35] << 8) + (unsigned int)v31[v35 + 1];
      v42 = &v41[v35 + 2];
      if ( (_DWORD)v38 )
      {
        *(_QWORD *)(a3 + 40 * v26 + 16) = v37;
        memcpy_0(v37, v36, (unsigned int)v38);
        v23 = ConvertNetworkString(v37, (unsigned int)v38);
        if ( v23 )
          break;
        v36 = v42;
      }
      else
      {
        *(_QWORD *)(a3 + 40 * v26 + 16) = 0;
      }
      v24 = &v36[v38];
      v25 = &v37[(unsigned int)v38 + 2];
      v26 = (unsigned int)(v26 + 1);
      *(_WORD *)&v37[v38] = 0;
    }
    while ( (unsigned int)v26 < *a4 );
  }
  else
  {
    *a4 = v22;
    v23 = 234;
  }
LABEL_24:
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_D(1028, 11, WPP_36a3d2b25b333c88c463e99d733f09dc_Traceguids, v23);
  return v23;
}

```

## disassembly

```asm
0x1800074a8  mov     [rsp+arg_0], rcx
0x1800074ad  push    rbx
0x1800074ae  push    rbp
0x1800074af  push    rsi
0x1800074b0  push    rdi
0x1800074b1  push    r12
0x1800074b3  push    r13
0x1800074b5  push    r14
0x1800074b7  push    r15
0x1800074b9  sub     rsp, 38h
0x1800074bd  xor     r12d, r12d
0x1800074c0  xor     esi, esi
0x1800074c2  xor     edi, edi
0x1800074c4  mov     r14, r9
0x1800074c7  mov     r15, r8
0x1800074ca  mov     ebx, edx
0x1800074cc  mov     rbp, rcx
0x1800074cf  test    byte ptr cs:xmmword_18000F160, 10h
0x1800074d6  jz      short loc_1800074F1
0x1800074d8  mov     eax, [r9]
0x1800074db  lea     edx, [rsi+0Ah]
0x1800074de  mov     r9d, ebx
0x1800074e1  mov     [rsp+78h+var_58], eax
0x1800074e5  lea     r8, WPP_36a3d2b25b333c88c463e99d733f09dc_Traceguids
0x1800074ec  call    WPP_SF_dd
0x1800074f1  mov     rdx, rbp
0x1800074f4  lea     eax, [rsi+2]
0x1800074f7  mov     r9d, 0FFFFFFFCh
0x1800074fd  cmp     eax, ebx
0x1800074ff  ja      loc_1800076FC
0x180007505  movzx   r8d, byte ptr [rdx]
0x180007509  movzx   eax, byte ptr [rdx+1]
0x18000750d  shl     r8d, 8
0x180007511  add     r8d, eax
0x180007514  jz      loc_1800076FC
0x18000751a  add     r8d, 3
0x18000751e  and     r8d, r9d
0x180007521  lea     r11d, [r8+2]
0x180007525  add     r11d, esi
0x180007528  lea     eax, [r11+2]
0x18000752c  cmp     eax, ebx
0x18000752e  ja      loc_1800076FC
0x180007534  lea     r10d, [r8+2]
0x180007538  add     r10, rdx
0x18000753b  movzx   r9d, byte ptr [r10]
0x18000753f  movzx   eax, byte ptr [r10+1]
0x180007544  shl     r9d, 8
0x180007548  add     r9d, eax
0x18000754b  test    r9b, 1
0x18000754f  jnz     loc_1800076FC
0x180007555  lea     esi, [r9+r11]
0x180007559  lea     eax, [rsi+4]
0x18000755c  cmp     eax, ebx
0x18000755e  ja      loc_1800076FC
0x180007564  lea     r11d, [r9+2]
0x180007568  add     r11, r10
0x18000756b  movzx   edx, byte ptr [r11]
0x18000756f  movzx   eax, byte ptr [r11+1]
0x180007574  shl     edx, 8
0x180007577  add     edx, eax
0x180007579  test    dl, 1
0x18000757c  jnz     loc_1800076FC
0x180007582  add     esi, 4
0x180007585  add     esi, edx
0x180007587  lea     eax, [rsi+2]
0x18000758a  cmp     eax, ebx
0x18000758c  ja      loc_1800076FC
0x180007592  lea     eax, [r9+4]
0x180007596  inc     edi
0x180007598  add     eax, edx
0x18000759a  add     eax, r8d
0x18000759d  add     r12d, eax
0x1800075a0  cmp     esi, ebx
0x1800075a2  jnb     short loc_1800075AF
0x1800075a4  add     edx, 2
0x1800075a7  add     rdx, r11
0x1800075aa  jmp     loc_1800074F4
0x1800075af  lea     eax, [rdi+rdi*4]
0x1800075b2  lea     ecx, [r12+rax*8]
0x1800075b6  cmp     [r14], ecx
0x1800075b9  jnb     short loc_1800075C8
0x1800075bb  mov     [r14], ecx
0x1800075be  mov     ebx, 0EAh
0x1800075c3  jmp     loc_180007701
0x1800075c8  mov     rdx, [rsp+78h+arg_0]
0x1800075d0  lea     rcx, [rdi+rdi*4]
0x1800075d4  lea     rsi, [r15+rcx*8]
0x1800075d8  mov     [r14], edi
0x1800075db  xor     ebp, ebp
0x1800075dd  lea     rdi, [rdx+2]
0x1800075e1  mov     rcx, rsi; void *
0x1800075e4  lea     r13, ds:0[rbp*4]
0x1800075ec  add     r13, rbp
0x1800075ef  mov     dword ptr [r15+r13*8], 0
0x1800075f7  movzx   ebx, byte ptr [rdx]
0x1800075fa  movzx   eax, byte ptr [rdx+1]
0x1800075fe  mov     rdx, rdi; Src
0x180007601  shl     ebx, 8
0x180007604  add     ebx, eax
0x180007606  mov     [r15+r13*8+18h], rsi
0x18000760b  mov     r8d, ebx; Size
0x18000760e  mov     [r15+r13*8+20h], ebx
0x180007613  call    memcpy_0
0x180007618  lea     edx, [rbx+3]
0x18000761b  mov     eax, 0FFFFFFFCh
0x180007620  and     rdx, rax
0x180007623  lea     r12, [rdi+2]
0x180007627  add     r12, rdx
0x18000762a  mov     [rsp+78h+arg_0], r12
0x180007632  movzx   ebx, byte ptr [rdx+rdi]
0x180007636  movzx   eax, byte ptr [rdx+rdi+1]
0x18000763b  lea     rdi, [rdx+rsi]
0x18000763f  shl     ebx, 8
0x180007642  mov     rdx, r12; Src
0x180007645  add     ebx, eax
0x180007647  mov     [r15+r13*8+8], rdi
0x18000764c  mov     r8d, ebx; Size
0x18000764f  mov     rcx, rdi; void *
0x180007652  mov     esi, ebx
0x180007654  call    memcpy_0
0x180007659  mov     edx, ebx
0x18000765b  mov     rcx, rdi
0x18000765e  call    ConvertNetworkString
0x180007663  mov     ebx, eax
0x180007665  test    eax, eax
0x180007667  jnz     loc_180007701
0x18000766d  mov     rax, [rsp+78h+arg_0]
0x180007675  xor     ecx, ecx
0x180007677  mov     [rdi+rsi], cx
0x18000767b  add     rax, 2
0x18000767f  movzx   edx, byte ptr [rsi+r12]
0x180007684  add     rax, rsi
0x180007687  movzx   r12d, byte ptr [rsi+r12+1]
0x18000768d  add     rdi, 2
0x180007691  shl     edx, 8
0x180007694  add     rdi, rsi
0x180007697  add     r12d, edx
0x18000769a  mov     [rsp+78h+arg_0], rax
0x1800076a2  mov     esi, r12d
0x1800076a5  test    r12d, r12d
0x1800076a8  jnz     short loc_1800076B1
0x1800076aa  mov     [r15+r13*8+10h], rcx
0x1800076af  jmp     short loc_1800076DD
0x1800076b1  mov     r8, rsi; Size
0x1800076b4  mov     [r15+r13*8+10h], rdi
0x1800076b9  mov     rdx, rax; Src
0x1800076bc  mov     rcx, rdi; void *
0x1800076bf  call    memcpy_0
0x1800076c4  mov     edx, r12d
0x1800076c7  mov     rcx, rdi
0x1800076ca  call    ConvertNetworkString
0x1800076cf  mov     ebx, eax
0x1800076d1  test    eax, eax
0x1800076d3  jnz     short loc_180007701
0x1800076d5  mov     rax, [rsp+78h+arg_0]
0x1800076dd  add     rsi, 2
0x1800076e1  lea     rdx, [r12+rax]
0x1800076e5  xor     eax, eax
0x1800076e7  add     rsi, rdi
0x1800076ea  inc     ebp
0x1800076ec  mov     [rdi+r12], ax
0x1800076f1  cmp     ebp, [r14]
0x1800076f4  jb      loc_1800075DD
0x1800076fa  jmp     short loc_180007701
0x1800076fc  mov     ebx, 54Fh
0x180007701  test    byte ptr cs:xmmword_18000F160, 10h
0x180007708  jz      short loc_180007723
0x18000770a  mov     edx, 0Bh
0x18000770f  lea     r8, WPP_36a3d2b25b333c88c463e99d733f09dc_Traceguids
0x180007716  mov     ecx, 404h
0x18000771b  mov     r9d, ebx
0x18000771e  call    WPP_SF_D
0x180007723  mov     eax, ebx
0x180007725  add     rsp, 38h
0x180007729  pop     r15
0x18000772b  pop     r14
0x18000772d  pop     r13
0x18000772f  pop     r12
0x180007731  pop     rdi
0x180007732  pop     rsi
0x180007733  pop     rbp
0x180007734  pop     rbx
0x180007735  retn
```
