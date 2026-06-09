# UpSampling(uchar const *,uchar const *,uchar *,uchar *,long,long,long,long,long,long,int,int,long,long,long,long,long)

- ea: `0x1800140a8`
- end: `0x18001436b`
- name: `?UpSampling@@YAXPEBE0PEAE1JJJJJJHHJJJJJ@Z`
- size: `707`
- prototype: `void __fastcall(const unsigned __int8 *, const unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int, int, int, int, int, int, int, int, int, int, int, int, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180012120`
- `0x18001ffa0`
- `0x180020bb0`
- `0x1800248f0`
- `0x180027c50`
- `0x1800283c0`

## callees

- `0x1800140a8`
- `0x180014790`

## pseudocode

```c
void __fastcall UpSampling(
        const unsigned __int8 *a1,
        const unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        int a16,
        int a17)
{
  const unsigned __int8 *v17; // rsi
  unsigned __int8 *v18; // r12
  unsigned __int8 *v19; // r15
  const unsigned __int8 *v20; // r14
  unsigned int v21; // r10d
  __int64 v22; // r8
  const unsigned __int8 *v23; // rbx
  const unsigned __int8 *v24; // rdi
  unsigned __int8 *v25; // r10
  const unsigned __int8 *v26; // r13
  const unsigned __int8 *v27; // rcx
  unsigned __int8 *v28; // r9
  int v29; // r11d
  int v30; // eax
  unsigned __int8 *v31; // rdx
  unsigned __int8 *v32; // rax
  __int64 v33; // rsi
  int v34; // r14d
  const unsigned __int8 *v35; // r15
  const unsigned __int8 *v36; // r12
  unsigned __int8 *v37; // r14
  unsigned __int8 *v38; // r13
  int v39; // ecx
  int v40; // edx
  int v41; // ecx
  int v42; // edx
  int i; // ecx
  int j; // ecx
  int v45; // [rsp+20h] [rbp-48h]
  unsigned __int8 *v46; // [rsp+28h] [rbp-40h]
  const unsigned __int8 *v47; // [rsp+30h] [rbp-38h]
  const unsigned __int8 *v48; // [rsp+38h] [rbp-30h]
  unsigned __int8 *v49; // [rsp+40h] [rbp-28h]
  int v54; // [rsp+F8h] [rbp+90h]

  v17 = a1;
  v18 = a4;
  a13 = 0;
  v19 = a3;
  a15 = 0;
  v20 = a2;
  a14 = 0;
  a16 = 0;
  getRoundShift(3, 1, &a13, &a14);
  getRoundShift(1, v21, &a15, &a16);
  v22 = a6;
  v23 = v17;
  v24 = v20;
  a17 = 1;
  v25 = &v18[a6];
  v26 = &v17[a5];
  v27 = &v20[a5];
  v47 = v26;
  v48 = v27;
  v46 = &v25[a6];
  v28 = &v19[a6];
  v30 = v29;
  v31 = &v28[a6];
  LOBYTE(v30) = a12 == v29;
  v54 = v30 + a10;
  v49 = v31;
  if ( v54 > 1 )
  {
    v32 = &v25[a6];
    v33 = a5;
    v34 = a17;
    do
    {
      v45 = 0;
      v35 = v26;
      v36 = v27;
      if ( a9 > 0 )
      {
        v37 = v31;
        v38 = v32;
        do
        {
          *v28 = (a13 + *v23 + 2 * *v23 + *v35) >> a14;
          v28 += a8;
          v39 = *v35;
          v35 += a7;
          v40 = *v23;
          v23 += a7;
          *v37 = (a15 + v39 + 2 * v39 + v40) >> a16;
          v37 += a8;
          *v25 = (a13 + *v24 + 2 * *v24 + *v36) >> a14;
          v25 += a8;
          v41 = *v36;
          v36 += a7;
          v42 = *v24;
          v24 += a7;
          *v38 = (a15 + v41 + 2 * v41 + v42) >> a16;
          v38 += a8;
          ++v45;
        }
        while ( v45 < a9 );
        v22 = a6;
        v26 = v47;
        v27 = v48;
        v31 = v49;
        v32 = v46;
        v33 = a5;
        v34 = a17;
      }
      ++v34;
      v28 = &v31[v22];
      v23 = v26;
      a17 = v34;
      v26 += v33;
      v25 = &v32[v22];
      v24 = v27;
      v47 = v26;
      v27 += v33;
      v31 += 2 * v22;
      v32 += 2 * v22;
      v48 = v27;
      v49 = v31;
      v46 = v32;
    }
    while ( v34 < v54 );
    v17 = a1;
    v20 = a2;
    v19 = a3;
    v18 = a4;
  }
  if ( a11 )
  {
    for ( i = 0; i < a9; v18 += a8 )
    {
      ++i;
      *v19 = *v17;
      v17 += a7;
      v19 += a8;
      *v18 = *v20;
      v20 += a7;
    }
  }
  if ( a12 )
  {
    for ( j = 0; j < a9; v25 += a8 )
    {
      ++j;
      *v28 = *v23;
      v23 += a7;
      v28 += a8;
      *v25 = *v24;
      v24 += a7;
    }
  }
}

```

## disassembly

```asm
0x1800140a8  mov     rax, rsp
0x1800140ab  mov     [rax+20h], r9
0x1800140af  mov     [rax+18h], r8
0x1800140b3  mov     [rax+10h], rdx
0x1800140b7  mov     [rax+8], rcx
0x1800140bb  push    rbp
0x1800140bc  push    rbx
0x1800140bd  push    rsi
0x1800140be  push    rdi
0x1800140bf  push    r12
0x1800140c1  push    r13
0x1800140c3  push    r14
0x1800140c5  push    r15
0x1800140c7  mov     rbp, rsp
0x1800140ca  sub     rsp, 68h
0x1800140ce  xor     r11d, r11d
0x1800140d1  mov     rsi, rcx
0x1800140d4  mov     r12, r9
0x1800140d7  mov     [rbp+arg_60], r11d
0x1800140de  mov     r15, r8
0x1800140e1  mov     [rbp+arg_70], r11d
0x1800140e8  mov     r14, rdx
0x1800140eb  mov     [rbp+arg_68], r11d
0x1800140f2  lea     ebx, [r11+1]
0x1800140f6  mov     [rbp+arg_78], r11d
0x1800140fd  lea     r10d, [r11+3]
0x180014101  mov     edx, ebx
0x180014103  mov     ecx, r10d
0x180014106  lea     r9, [rbp+arg_68]
0x18001410d  lea     r8, [rbp+arg_60]
0x180014114  call    getRoundShift
0x180014119  mov     ecx, ebx
0x18001411b  lea     r9, [rbp+arg_78]
0x180014122  lea     r8, [rbp+arg_70]
0x180014129  mov     edx, r10d
0x18001412c  call    getRoundShift
0x180014131  movsxd  r8, [rbp+arg_28]
0x180014135  mov     rbx, rsi
0x180014138  movsxd  rax, [rbp+arg_20]
0x18001413c  mov     rdi, r14
0x18001413f  cmp     [rbp+arg_58], r11d
0x180014146  mov     [rbp+arg_80], 1
0x180014150  lea     r10, [r8+r12]
0x180014154  lea     r13, [rax+rsi]
0x180014158  lea     rcx, [rax+r14]
0x18001415c  mov     [rbp+var_38], r13
0x180014160  lea     rax, [r8+r10]
0x180014164  mov     [rbp+var_30], rcx
0x180014168  mov     [rbp+var_40], rax
0x18001416c  lea     r9, [r8+r15]
0x180014170  mov     eax, r11d
0x180014173  lea     rdx, [r8+r9]
0x180014177  mov     r11d, [rbp+arg_40]
0x18001417e  setz    al
0x180014181  add     [rbp+arg_48], eax
0x180014187  cmp     [rbp+arg_48], 1
0x18001418e  mov     [rbp+var_28], rdx
0x180014192  jle     loc_1800142E8
0x180014198  mov     rax, [rbp+var_40]
0x18001419c  movsxd  rsi, [rbp+arg_20]
0x1800141a0  mov     r14d, [rbp+arg_80]
0x1800141a7  mov     [rbp+var_48], 0
0x1800141ae  mov     r15, r13
0x1800141b1  mov     r12, rcx
0x1800141b4  test    r11d, r11d
0x1800141b7  jle     loc_180014295
0x1800141bd  movsxd  r8, [rbp+arg_30]
0x1800141c1  mov     r14, rdx
0x1800141c4  movsxd  rsi, [rbp+arg_38]
0x1800141cb  mov     r13, rax
0x1800141ce  movzx   ecx, byte ptr [rbx]
0x1800141d1  movzx   edx, byte ptr [r15]
0x1800141d5  mov     eax, ecx
0x1800141d7  add     eax, [rbp+arg_60]
0x1800141dd  lea     eax, [rax+rcx*2]
0x1800141e0  mov     ecx, [rbp+arg_68]
0x1800141e6  add     edx, eax
0x1800141e8  sar     edx, cl
0x1800141ea  mov     [r9], dl
0x1800141ed  add     r9, rsi
0x1800141f0  movzx   ecx, byte ptr [r15]
0x1800141f4  add     r15, r8
0x1800141f7  movzx   edx, byte ptr [rbx]
0x1800141fa  mov     eax, ecx
0x1800141fc  add     eax, [rbp+arg_70]
0x180014202  add     rbx, r8
0x180014205  lea     eax, [rax+rcx*2]
0x180014208  mov     ecx, [rbp+arg_78]
0x18001420e  add     edx, eax
0x180014210  sar     edx, cl
0x180014212  mov     [r14], dl
0x180014215  add     r14, rsi
0x180014218  movzx   ecx, byte ptr [rdi]
0x18001421b  movzx   edx, byte ptr [r12]
0x180014220  mov     eax, ecx
0x180014222  add     eax, [rbp+arg_60]
0x180014228  lea     eax, [rax+rcx*2]
0x18001422b  mov     ecx, [rbp+arg_68]
0x180014231  add     edx, eax
0x180014233  sar     edx, cl
0x180014235  mov     [r10], dl
0x180014238  add     r10, rsi
0x18001423b  movzx   ecx, byte ptr [r12]
0x180014240  add     r12, r8
0x180014243  movzx   edx, byte ptr [rdi]
0x180014246  mov     eax, ecx
0x180014248  add     eax, [rbp+arg_70]
0x18001424e  add     rdi, r8
0x180014251  lea     eax, [rax+rcx*2]
0x180014254  mov     ecx, [rbp+arg_78]
0x18001425a  add     edx, eax
0x18001425c  mov     eax, [rbp+var_48]
0x18001425f  sar     edx, cl
0x180014261  inc     eax
0x180014263  mov     [r13+0], dl
0x180014267  add     r13, rsi
0x18001426a  mov     [rbp+var_48], eax
0x18001426d  cmp     eax, r11d
0x180014270  jl      loc_1800141CE
0x180014276  movsxd  r8, [rbp+arg_28]
0x18001427a  mov     r13, [rbp+var_38]
0x18001427e  mov     rcx, [rbp+var_30]
0x180014282  mov     rdx, [rbp+var_28]
0x180014286  mov     rax, [rbp+var_40]
0x18001428a  movsxd  rsi, [rbp+arg_20]
0x18001428e  mov     r14d, [rbp+arg_80]
0x180014295  inc     r14d
0x180014298  lea     r9, [r8+rdx]
0x18001429c  mov     rbx, r13
0x18001429f  mov     [rbp+arg_80], r14d
0x1800142a6  add     r13, rsi
0x1800142a9  lea     r10, [r8+rax]
0x1800142ad  mov     rdi, rcx
0x1800142b0  mov     [rbp+var_38], r13
0x1800142b4  add     rcx, rsi
0x1800142b7  lea     rdx, [rdx+r8*2]
0x1800142bb  lea     rax, [rax+r8*2]
0x1800142bf  mov     [rbp+var_30], rcx
0x1800142c3  mov     [rbp+var_28], rdx
0x1800142c7  mov     [rbp+var_40], rax
0x1800142cb  cmp     r14d, [rbp+arg_48]
0x1800142d2  jl      loc_1800141A7
0x1800142d8  mov     rsi, [rbp+arg_0]
0x1800142dc  mov     r14, [rbp+arg_8]
0x1800142e0  mov     r15, [rbp+arg_10]
0x1800142e4  mov     r12, [rbp+arg_18]
0x1800142e8  cmp     [rbp+arg_50], 0
0x1800142ef  jz      short loc_180014322
0x1800142f1  xor     ecx, ecx
0x1800142f3  test    r11d, r11d
0x1800142f6  jle     short loc_180014322
0x1800142f8  movsxd  rdx, [rbp+arg_30]
0x1800142fc  movsxd  r8, [rbp+arg_38]
0x180014303  mov     al, [rsi]
0x180014305  inc     ecx
0x180014307  mov     [r15], al
0x18001430a  add     rsi, rdx
0x18001430d  mov     al, [r14]
0x180014310  add     r15, r8
0x180014313  mov     [r12], al
0x180014317  add     r14, rdx
0x18001431a  add     r12, r8
0x18001431d  cmp     ecx, r11d
0x180014320  jl      short loc_180014303
0x180014322  cmp     [rbp+arg_58], 0
0x180014329  jz      short loc_18001435A
0x18001432b  xor     ecx, ecx
0x18001432d  test    r11d, r11d
0x180014330  jle     short loc_18001435A
0x180014332  movsxd  rdx, [rbp+arg_30]
0x180014336  movsxd  r8, [rbp+arg_38]
0x18001433d  mov     al, [rbx]
0x18001433f  inc     ecx
0x180014341  mov     [r9], al
0x180014344  add     rbx, rdx
0x180014347  mov     al, [rdi]
0x180014349  add     r9, r8
0x18001434c  mov     [r10], al
0x18001434f  add     rdi, rdx
0x180014352  add     r10, r8
0x180014355  cmp     ecx, r11d
0x180014358  jl      short loc_18001433D
0x18001435a  add     rsp, 68h
0x18001435e  pop     r15
0x180014360  pop     r14
0x180014362  pop     r13
0x180014364  pop     r12
0x180014366  pop     rdi
0x180014367  pop     rsi
0x180014368  pop     rbx
0x180014369  pop     rbp
0x18001436a  retn
```
