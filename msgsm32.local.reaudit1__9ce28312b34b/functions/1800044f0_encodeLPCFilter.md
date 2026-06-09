# encodeLPCFilter

- ea: `0x1800044f0`
- end: `0x18000478a`
- name: `encodeLPCFilter`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005350`

## callees

- `0x180001400`
- `0x180002e34`
- `0x180003250`
- `0x1800044f0`

## pseudocode

```c
void __fastcall encodeLPCFilter(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 i; // rdx
  int v9; // r8d
  int v10; // eax
  int v11; // ecx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // r8d
  __int16 v16; // ax
  int v17; // r9d
  int v18; // eax
  int v19; // r10d
  int v20; // eax
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  _WORD v25[12]; // [rsp+30h] [rbp-49h] BYREF
  _WORD v26[12]; // [rsp+48h] [rbp-31h] BYREF
  _WORD v27[12]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v28[2]; // [rsp+78h] [rbp-1h] BYREF
  __int128 v29; // [rsp+7Ah] [rbp+1h]
  __int16 v30; // [rsp+90h] [rbp+17h] BYREF
  __int128 v31; // [rsp+92h] [rbp+19h]

  for ( i = 1; i != 9; ++i )
  {
    v9 = MIC[i] + *(__int16 *)(a2 + 2 * i);
    if ( v9 >= -32768 )
    {
      if ( v9 > 0x7FFF )
        LOWORD(v9) = 0x7FFF;
    }
    else
    {
      LOWORD(v9) = 0x8000;
    }
    v10 = (__int16)((_WORD)v9 << 10) - (__int16)(2 * B[i]);
    if ( v10 >= -32768 )
    {
      if ( v10 > 0x7FFF )
        LOWORD(v10) = 0x7FFF;
    }
    else
    {
      LOWORD(v10) = 0x8000;
    }
    v11 = (__int16)v10 * INVA[i] + 0x4000;
    if ( v11 >= 0x40000000 )
      v11 = 0x3FFFFFFF;
    v12 = (unsigned int)v11 >> 15;
    v13 = 2 * (__int16)v12;
    if ( v13 >= -32768 )
    {
      if ( v13 > 0x7FFF )
        LOWORD(v13) = 0x7FFF;
    }
    else
    {
      LOWORD(v13) = 0x8000;
    }
    *(&v30 + i) = v13;
  }
  v14 = 1;
  v29 = v31;
  do
  {
    v15 = (*(&v30 + v14) >> 2) + (*(__int16 *)(a1 + 2 * v14 + 580) >> 2);
    if ( v15 >= -32768 )
    {
      if ( v15 <= 0x7FFF )
        v16 = (*(&v30 + v14) >> 2) + (*(__int16 *)(a1 + 2 * v14 + 580) >> 2);
      else
        v16 = 0x7FFF;
    }
    else
    {
      v16 = 0x8000;
    }
    v17 = *(__int16 *)(a1 + 2 * v14 + 580) >> 1;
    v18 = v17 + v16;
    if ( v18 >= -32768 )
    {
      if ( v18 > 0x7FFF )
        LOWORD(v18) = 0x7FFF;
    }
    else
    {
      LOWORD(v18) = 0x8000;
    }
    v19 = *(&v30 + v14) >> 1;
    v25[v14] = v18;
    v20 = v19 + v17;
    if ( v19 + v17 >= -32768 )
    {
      if ( v20 > 0x7FFF )
        LOWORD(v20) = 0x7FFF;
    }
    else
    {
      LOWORD(v20) = 0x8000;
    }
    v26[v14] = v20;
    if ( v15 >= -32768 )
    {
      if ( v15 > 0x7FFF )
        LOWORD(v15) = 0x7FFF;
    }
    else
    {
      LOWORD(v15) = 0x8000;
    }
    v21 = v19 + (__int16)v15;
    if ( v21 >= -32768 )
    {
      if ( v21 > 0x7FFF )
        LOWORD(v21) = 0x7FFF;
    }
    else
    {
      LOWORD(v21) = 0x8000;
    }
    v27[v14++] = v21;
  }
  while ( v14 != 9 );
  *(_OWORD *)(a1 + 582) = v31;
  Comprp(v12, (__int64)v25, (__int64)&v30);
  Compd(a1, (__int64)&v30, a3, a4, 0, 0xCu);
  Comprp(v22, (__int64)v26, (__int64)&v30);
  Compd(a1, (__int64)&v30, a3, a4, 0xDu, 0x1Au);
  Comprp(v23, (__int64)v27, (__int64)&v30);
  Compd(a1, (__int64)&v30, a3, a4, 0x1Bu, 0x27u);
  Comprp(v24, (__int64)v28, (__int64)&v30);
  Compd(a1, (__int64)&v30, a3, a4, 0x28u, 0x9Fu);
}

```

## disassembly

```asm
0x1800044f0  mov     [rsp-8+arg_8], rbx
0x1800044f5  push    rbp
0x1800044f6  push    rsi
0x1800044f7  push    rdi
0x1800044f8  push    r12
0x1800044fa  push    r14
0x1800044fc  lea     rbp, [rsp-37h]
0x180004501  sub     rsp, 0B0h
0x180004508  mov     rax, cs:__security_cookie
0x18000450f  xor     rax, rsp
0x180004512  mov     [rbp+57h+var_28], rax
0x180004516  mov     rsi, r9
0x180004519  lea     r10, __ImageBase
0x180004520  mov     r9, rdx
0x180004523  mov     rdi, r8
0x180004526  mov     edx, 1
0x18000452b  mov     rbx, rcx
0x18000452e  mov     r14d, 0FFFF8000h
0x180004534  mov     r11d, 7FFFh
0x18000453a  movsx   r8d, word ptr [r9+rdx*2]
0x18000453f  movsx   eax, ds:rva MIC[r10+rdx*2]
0x180004548  add     r8d, eax
0x18000454b  cmp     r8d, r14d
0x18000454e  jge     short loc_180004556
0x180004550  movzx   r8d, r14w
0x180004554  jmp     short loc_18000455E
0x180004556  cmp     r8d, r11d
0x180004559  jle     short loc_18000455E
0x18000455b  mov     r8d, r11d
0x18000455e  movzx   eax, ds:rva B[r10+rdx*2]
0x180004567  add     ax, ax
0x18000456a  shl     r8w, 0Ah
0x18000456f  movsx   ecx, ax
0x180004572  movsx   eax, r8w
0x180004576  sub     eax, ecx
0x180004578  cmp     eax, r14d
0x18000457b  jge     short loc_180004583
0x18000457d  movzx   eax, r14w
0x180004581  jmp     short loc_18000458B
0x180004583  cmp     eax, r11d
0x180004586  jle     short loc_18000458B
0x180004588  mov     eax, r11d
0x18000458b  movsx   ecx, ds:rva INVA[r10+rdx*2]
0x180004594  cwde
0x180004595  imul    ecx, eax
0x180004598  mov     eax, 3FFFFFFFh
0x18000459d  add     ecx, 4000h
0x1800045a3  cmp     ecx, 40000000h
0x1800045a9  cmovge  ecx, eax
0x1800045ac  shr     ecx, 0Fh
0x1800045af  movsx   eax, cx
0x1800045b2  add     eax, eax
0x1800045b4  cmp     eax, r14d
0x1800045b7  jge     short loc_1800045BF
0x1800045b9  movzx   eax, r14w
0x1800045bd  jmp     short loc_1800045C7
0x1800045bf  cmp     eax, r11d
0x1800045c2  jle     short loc_1800045C7
0x1800045c4  mov     eax, r11d
0x1800045c7  mov     [rbp+rdx*2+57h+var_40], ax
0x1800045cc  inc     rdx
0x1800045cf  cmp     rdx, 9
0x1800045d3  jnz     loc_18000453A
0x1800045d9  movups  xmm0, [rbp+57h+var_3E]
0x1800045dd  lea     r12, [rbp+57h+var_3E]
0x1800045e1  mov     edx, 1
0x1800045e6  movups  [rbp+57h+var_56], xmm0
0x1800045ea  movsx   r10d, [rbp+rdx*2+57h+var_40]
0x1800045f0  movsx   r9d, word ptr [rbx+rdx*2+244h]
0x1800045f9  mov     eax, r10d
0x1800045fc  sar     eax, 2
0x1800045ff  mov     r8d, r9d
0x180004602  sar     r8d, 2
0x180004606  add     r8d, eax
0x180004609  cmp     r8d, r14d
0x18000460c  jge     short loc_180004614
0x18000460e  movzx   eax, r14w
0x180004612  jmp     short loc_180004622
0x180004614  cmp     r8d, r11d
0x180004617  jle     short loc_18000461E
0x180004619  mov     eax, r11d
0x18000461c  jmp     short loc_180004622
0x18000461e  movzx   eax, r8w
0x180004622  sar     r9d, 1
0x180004625  cwde
0x180004626  add     eax, r9d
0x180004629  cmp     eax, r14d
0x18000462c  jge     short loc_180004634
0x18000462e  movzx   eax, r14w
0x180004632  jmp     short loc_18000463C
0x180004634  cmp     eax, r11d
0x180004637  jle     short loc_18000463C
0x180004639  mov     eax, r11d
0x18000463c  sar     r10d, 1
0x18000463f  mov     [rbp+rdx*2+57h+var_A0], ax
0x180004644  lea     eax, [r10+r9]
0x180004648  cmp     eax, r14d
0x18000464b  jge     short loc_180004653
0x18000464d  movzx   eax, r14w
0x180004651  jmp     short loc_18000465B
0x180004653  cmp     eax, r11d
0x180004656  jle     short loc_18000465B
0x180004658  mov     eax, r11d
0x18000465b  mov     [rbp+rdx*2+57h+var_88], ax
0x180004660  cmp     r8d, r14d
0x180004663  jge     short loc_18000466B
0x180004665  movzx   r8d, r14w
0x180004669  jmp     short loc_180004673
0x18000466b  cmp     r8d, r11d
0x18000466e  jle     short loc_180004673
0x180004670  mov     r8d, r11d
0x180004673  movsx   eax, r8w
0x180004677  add     eax, r10d
0x18000467a  cmp     eax, r14d
0x18000467d  jge     short loc_180004685
0x18000467f  movzx   eax, r14w
0x180004683  jmp     short loc_18000468D
0x180004685  cmp     eax, r11d
0x180004688  jle     short loc_18000468D
0x18000468a  mov     eax, r11d
0x18000468d  mov     [rbp+rdx*2+57h+var_70], ax
0x180004692  inc     rdx
0x180004695  cmp     rdx, 9
0x180004699  jnz     loc_1800045EA
0x18000469f  movups  xmm0, xmmword ptr [r12]
0x1800046a4  lea     r8, [rbp+57h+var_40]
0x1800046a8  lea     rdx, [rbp+57h+var_A0]
0x1800046ac  movups  xmmword ptr [rbx+246h], xmm0
0x1800046b3  call    Comprp
0x1800046b8  mov     r9, rsi
0x1800046bb  mov     [rsp+0D0h+var_A8], 0Ch
0x1800046c3  mov     r8, rdi
0x1800046c6  mov     [rsp+0D0h+var_B0], 0
0x1800046ce  mov     rcx, rbx
0x1800046d1  lea     rdx, [rbp+57h+var_40]
0x1800046d5  call    Compd
0x1800046da  lea     r8, [rbp+57h+var_40]
0x1800046de  lea     rdx, [rbp+57h+var_88]
0x1800046e2  call    Comprp
0x1800046e7  mov     r9, rsi
0x1800046ea  mov     [rsp+0D0h+var_A8], 1Ah
0x1800046f2  mov     r8, rdi
0x1800046f5  mov     [rsp+0D0h+var_B0], 0Dh
0x1800046fd  mov     rcx, rbx
0x180004700  lea     rdx, [rbp+57h+var_40]
0x180004704  call    Compd
0x180004709  lea     r8, [rbp+57h+var_40]
0x18000470d  lea     rdx, [rbp+57h+var_70]
0x180004711  call    Comprp
0x180004716  mov     r9, rsi
0x180004719  mov     [rsp+0D0h+var_A8], 27h ; '''
0x180004721  mov     r8, rdi
0x180004724  mov     [rsp+0D0h+var_B0], 1Bh
0x18000472c  mov     rcx, rbx
0x18000472f  lea     rdx, [rbp+57h+var_40]
0x180004733  call    Compd
0x180004738  lea     r8, [rbp+57h+var_40]
0x18000473c  lea     rdx, [rbp+57h+var_58]
0x180004740  call    Comprp
0x180004745  mov     r9, rsi
0x180004748  mov     [rsp+0D0h+var_A8], 9Fh
0x180004750  mov     r8, rdi
0x180004753  mov     [rsp+0D0h+var_B0], 28h ; '('
0x18000475b  mov     rcx, rbx
0x18000475e  lea     rdx, [rbp+57h+var_40]
0x180004762  call    Compd
0x180004767  mov     rcx, [rbp+57h+var_28]
0x18000476b  xor     rcx, rsp; StackCookie
0x18000476e  call    __security_check_cookie
0x180004773  mov     rbx, [rsp+0D0h+arg_8]
0x18000477b  add     rsp, 0B0h
0x180004782  pop     r14
0x180004784  pop     r12
0x180004786  pop     rdi
0x180004787  pop     rsi
0x180004788  pop     rbp
0x180004789  retn
```
