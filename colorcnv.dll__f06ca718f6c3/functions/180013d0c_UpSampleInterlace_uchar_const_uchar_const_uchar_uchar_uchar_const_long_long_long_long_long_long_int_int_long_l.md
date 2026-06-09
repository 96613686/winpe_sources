# UpSampleInterlace(uchar const *,uchar const *,uchar *,uchar *,uchar const *,long,long,long,long,long,long,int,int,long,long,long,long,long)

- ea: `0x180013d0c`
- end: `0x1800140a1`
- name: `?UpSampleInterlace@@YAXPEBE0PEAE10JJJJJJHHJJJJJ@Z`
- size: `917`
- prototype: `void __fastcall(const unsigned __int8 *, const unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int, int, int, int, int, int, int, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180020eb0`
- `0x180022ee0`
- `0x180025020`
- `0x180027fe0`
- `0x180028740`

## callees

- `0x180013d0c`

## pseudocode

```c
void __fastcall UpSampleInterlace(
        const unsigned __int8 *a1,
        const unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
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
        int a17,
        int a18)
{
  const unsigned __int8 *v18; // rdi
  const unsigned __int8 *v19; // rbp
  const unsigned __int8 *v20; // r12
  const unsigned __int8 *v21; // rsi
  unsigned __int8 *v22; // r14
  unsigned __int8 *v23; // r13
  __int64 v24; // r15
  unsigned __int8 *v25; // r11
  unsigned __int8 *v26; // r8
  unsigned __int8 *v27; // r9
  int v28; // edx
  unsigned __int8 *v29; // r10
  const unsigned __int8 *v30; // rax
  const unsigned __int8 *v31; // rcx
  __int64 v32; // rbp
  int v33; // r12d
  int v34; // r13d
  char v35; // r14
  unsigned __int64 v36; // rcx
  const unsigned __int8 *v37; // rbp
  int v38; // edx
  int i; // ecx
  int j; // ecx
  const unsigned __int8 *v41; // [rsp+0h] [rbp-A8h]
  unsigned __int8 *v42; // [rsp+8h] [rbp-A0h]
  char v43; // [rsp+10h] [rbp-98h]
  _BYTE *v44; // [rsp+18h] [rbp-90h]
  const unsigned __int8 *v45; // [rsp+20h] [rbp-88h]
  const unsigned __int8 *v46; // [rsp+28h] [rbp-80h]
  __int64 v47; // [rsp+30h] [rbp-78h]
  unsigned __int8 *v48; // [rsp+38h] [rbp-70h]
  unsigned __int8 *v49; // [rsp+40h] [rbp-68h]
  __int64 v50; // [rsp+50h] [rbp-58h]
  int v55; // [rsp+D8h] [rbp+30h]
  int v56; // [rsp+E0h] [rbp+38h]
  int v57; // [rsp+100h] [rbp+58h]

  v18 = a1;
  v19 = a1;
  v20 = a2;
  v47 = 2 * a6;
  v21 = a2;
  v22 = a4;
  v23 = a3;
  v45 = &a1[v47];
  v46 = &a2[v47];
  v24 = 2 * a7;
  v50 = v24;
  v25 = &a3[v24];
  v26 = &a4[v24];
  v27 = &v25[v24];
  v48 = &v25[v24];
  v28 = 1;
  v29 = &v26[v24];
  v49 = &v26[v24];
  v56 = 1;
  v43 = 3 - ((a18 + a17) / 2 != 4);
  v57 = a11 + (a13 == 0);
  if ( v57 > 1 )
  {
    v30 = &a1[v47];
    v31 = v46;
    v32 = 2 * a6;
    v33 = (a16 + a15) / 2;
    v34 = (a18 + a17) / 2;
    v35 = 3 - (v33 != 4);
    do
    {
      v41 = v31;
      v42 = v27;
      v44 = v29;
      v55 = 0;
      if ( a10 > 0 )
      {
        v36 = (unsigned __int64)v29;
        v37 = v30;
        do
        {
          if ( v36 > (unsigned __int64)a5 )
            break;
          *v25 = (v33 + a16 * *v37 + a15 * *v18) >> v35;
          *v42 = (v34 + a18 * *v37 + a17 * *v18) >> v43;
          *v26 = (v33 + a16 * *v41 + a15 * *v21) >> v35;
          v38 = v34 + a18 * *v41 + a17 * *v21;
          v41 += a8;
          v18 += a8;
          v37 += a8;
          v21 += a8;
          v42 += a9;
          v25 += a9;
          v26 += a9;
          *v44 = v38 >> v43;
          v36 = (unsigned __int64)&v44[a9];
          v44 = (_BYTE *)v36;
          ++v55;
        }
        while ( v55 < a10 );
        v27 = v48;
        v29 = v49;
        v24 = v50;
        v30 = v45;
        v31 = v46;
        v28 = v56;
        v32 = v47;
      }
      ++v28;
      v25 = &v27[v24];
      v18 = v30;
      v56 = v28;
      v30 += v32;
      v26 = &v29[v24];
      v21 = v31;
      v45 = v30;
      v31 += v32;
      v27 += 2 * v24;
      v29 += 2 * v24;
      v46 = v31;
      v48 = v27;
      v49 = v29;
    }
    while ( v28 < v57 );
    v22 = a4;
    v19 = a1;
    v20 = a2;
    v23 = a3;
  }
  if ( a12 )
  {
    for ( i = 0; i < a10; v22 += a9 )
    {
      if ( v22 > a5 )
        break;
      ++i;
      *v23 = *v19;
      *v22 = *v20;
      v19 += a8;
      v20 += a8;
      v23 += a9;
    }
  }
  if ( a13 )
  {
    if ( a14 > 0 )
    {
      for ( j = 0; j < a10; v29 += a9 )
      {
        if ( v26 > a5 )
          break;
        *v25 = *v18;
        *v26 = *v21;
        if ( a14 > 1 )
        {
          *v27 = *v25;
          *v29 = *v26;
        }
        ++j;
        v18 += a8;
        v21 += a8;
        v25 += a9;
        v26 += a9;
        v27 += a9;
      }
    }
  }
}

```

## disassembly

```asm
0x180013d0c  mov     rax, rsp
0x180013d0f  mov     [rax+20h], r9
0x180013d13  mov     [rax+18h], r8
0x180013d17  mov     [rax+10h], rdx
0x180013d1b  mov     [rax+8], rcx
0x180013d1f  push    rbx
0x180013d20  push    rbp
0x180013d21  push    rsi
0x180013d22  push    rdi
0x180013d23  push    r12
0x180013d25  push    r13
0x180013d27  push    r14
0x180013d29  push    r15
0x180013d2b  sub     rsp, 68h
0x180013d2f  mov     eax, [rsp+0A8h+arg_28]
0x180013d36  mov     rdi, rcx
0x180013d39  add     eax, eax
0x180013d3b  mov     rbp, rcx
0x180013d3e  movsxd  rcx, eax
0x180013d41  mov     r12, rdx
0x180013d44  mov     [rsp+0A8h+var_78], rcx
0x180013d49  mov     rsi, rdx
0x180013d4c  mov     r14, r9
0x180013d4f  mov     r13, r8
0x180013d52  lea     rax, [rcx+rdi]
0x180013d56  mov     [rsp+0A8h+var_88], rax
0x180013d5b  lea     rax, [rcx+rdx]
0x180013d5f  mov     [rsp+0A8h+var_80], rax
0x180013d64  mov     ecx, 2
0x180013d69  mov     eax, [rsp+0A8h+arg_30]
0x180013d70  add     eax, eax
0x180013d72  movsxd  r15, eax
0x180013d75  mov     eax, [rsp+0A8h+arg_70]
0x180013d7c  add     eax, [rsp+0A8h+arg_78]
0x180013d83  cdq
0x180013d84  mov     [rsp+0A8h+var_58], r15
0x180013d89  idiv    ecx
0x180013d8b  lea     r11, [r15+r8]
0x180013d8f  mov     ebx, eax
0x180013d91  mov     [rsp+0A8h+arg_28], eax
0x180013d98  mov     eax, [rsp+0A8h+arg_80]
0x180013d9f  lea     r8, [r15+r14]
0x180013da3  add     eax, [rsp+0A8h+arg_88]
0x180013daa  lea     r9, [r15+r11]
0x180013dae  cdq
0x180013daf  mov     [rsp+0A8h+var_70], r9
0x180013db4  idiv    ecx
0x180013db6  lea     ecx, [rbx-4]
0x180013db9  mov     edx, 1
0x180013dbe  mov     ebx, [rsp+0A8h+arg_48]
0x180013dc5  lea     r10, [r15+r8]
0x180013dc9  neg     ecx
0x180013dcb  mov     dword ptr [rsp+0A8h+var_A0], eax
0x180013dcf  mov     [rsp+0A8h+var_68], r10
0x180013dd4  sbb     ecx, ecx
0x180013dd6  mov     [rsp+0A8h+arg_30], edx
0x180013ddd  add     ecx, 3
0x180013de0  mov     dword ptr [rsp+0A8h+var_A8], ecx
0x180013de3  lea     ecx, [rax-4]
0x180013de6  neg     ecx
0x180013de8  sbb     eax, eax
0x180013dea  add     eax, 3
0x180013ded  mov     dword ptr [rsp+0A8h+var_98], eax
0x180013df1  xor     eax, eax
0x180013df3  cmp     [rsp+0A8h+arg_60], eax
0x180013dfa  setz    al
0x180013dfd  add     eax, [rsp+0A8h+arg_50]
0x180013e04  mov     [rsp+0A8h+arg_50], eax
0x180013e0b  cmp     eax, edx
0x180013e0d  jle     loc_180013FDE
0x180013e13  mov     rax, [rsp+0A8h+var_88]
0x180013e18  mov     rcx, [rsp+0A8h+var_80]
0x180013e1d  mov     rbp, [rsp+0A8h+var_78]
0x180013e22  mov     r12d, [rsp+0A8h+arg_28]
0x180013e2a  mov     r13d, dword ptr [rsp+0A8h+var_A0]
0x180013e2f  mov     r14d, dword ptr [rsp+0A8h+var_A8]
0x180013e33  mov     [rsp+0A8h+var_A8], rcx
0x180013e37  mov     [rsp+0A8h+var_A0], r9
0x180013e3c  mov     [rsp+0A8h+var_90], r10
0x180013e41  mov     [rsp+0A8h+arg_28], 0
0x180013e4c  test    ebx, ebx
0x180013e4e  jle     loc_180013F78
0x180013e54  mov     r15d, dword ptr [rsp+0A8h+var_98]
0x180013e59  mov     rcx, r10
0x180013e5c  mov     r10d, [rsp+0A8h+arg_78]
0x180013e64  mov     rbp, rax
0x180013e67  mov     r9d, [rsp+0A8h+arg_70]
0x180013e6f  cmp     rcx, [rsp+0A8h+arg_20]
0x180013e77  ja      loc_180013F53
0x180013e7d  movzx   eax, byte ptr [rbp+0]
0x180013e81  mov     ecx, r14d
0x180013e84  movzx   edx, byte ptr [rdi]
0x180013e87  imul    eax, r10d
0x180013e8b  imul    edx, r9d
0x180013e8f  add     eax, r12d
0x180013e92  add     edx, eax
0x180013e94  sar     edx, cl
0x180013e96  mov     ecx, r15d
0x180013e99  mov     [r11], dl
0x180013e9c  movzx   eax, byte ptr [rbp+0]
0x180013ea0  imul    eax, [rsp+0A8h+arg_88]
0x180013ea8  movzx   edx, byte ptr [rdi]
0x180013eab  imul    edx, [rsp+0A8h+arg_80]
0x180013eb3  add     eax, r13d
0x180013eb6  add     edx, eax
0x180013eb8  mov     rax, [rsp+0A8h+var_A0]
0x180013ebd  sar     edx, cl
0x180013ebf  mov     ecx, r14d
0x180013ec2  mov     [rax], dl
0x180013ec4  movzx   edx, byte ptr [rsi]
0x180013ec7  mov     rax, [rsp+0A8h+var_A8]
0x180013ecb  imul    edx, r9d
0x180013ecf  movzx   eax, byte ptr [rax]
0x180013ed2  imul    eax, r10d
0x180013ed6  add     eax, r12d
0x180013ed9  add     edx, eax
0x180013edb  mov     rax, [rsp+0A8h+var_A8]
0x180013edf  sar     edx, cl
0x180013ee1  mov     ecx, r15d
0x180013ee4  mov     [r8], dl
0x180013ee7  movzx   edx, byte ptr [rsi]
0x180013eea  movzx   eax, byte ptr [rax]
0x180013eed  imul    eax, [rsp+0A8h+arg_88]
0x180013ef5  imul    edx, [rsp+0A8h+arg_80]
0x180013efd  add     eax, r13d
0x180013f00  add     edx, eax
0x180013f02  movsxd  rax, [rsp+0A8h+arg_38]
0x180013f0a  add     [rsp+0A8h+var_A8], rax
0x180013f0e  add     rdi, rax
0x180013f11  sar     edx, cl
0x180013f13  add     rbp, rax
0x180013f16  mov     rcx, [rsp+0A8h+var_90]
0x180013f1b  add     rsi, rax
0x180013f1e  movsxd  rax, [rsp+0A8h+arg_40]
0x180013f26  add     [rsp+0A8h+var_A0], rax
0x180013f2b  add     r11, rax
0x180013f2e  add     r8, rax
0x180013f31  mov     [rcx], dl
0x180013f33  add     rcx, rax
0x180013f36  mov     eax, [rsp+0A8h+arg_28]
0x180013f3d  inc     eax
0x180013f3f  mov     [rsp+0A8h+var_90], rcx
0x180013f44  mov     [rsp+0A8h+arg_28], eax
0x180013f4b  cmp     eax, ebx
0x180013f4d  jl      loc_180013E6F
0x180013f53  mov     r9, [rsp+0A8h+var_70]
0x180013f58  mov     r10, [rsp+0A8h+var_68]
0x180013f5d  mov     r15, [rsp+0A8h+var_58]
0x180013f62  mov     rax, [rsp+0A8h+var_88]
0x180013f67  mov     rcx, [rsp+0A8h+var_80]
0x180013f6c  mov     edx, [rsp+0A8h+arg_30]
0x180013f73  mov     rbp, [rsp+0A8h+var_78]
0x180013f78  inc     edx
0x180013f7a  lea     r11, [r15+r9]
0x180013f7e  mov     rdi, rax
0x180013f81  mov     [rsp+0A8h+arg_30], edx
0x180013f88  add     rax, rbp
0x180013f8b  lea     r8, [r15+r10]
0x180013f8f  mov     rsi, rcx
0x180013f92  mov     [rsp+0A8h+var_88], rax
0x180013f97  add     rcx, rbp
0x180013f9a  lea     r9, [r9+r15*2]
0x180013f9e  lea     r10, [r10+r15*2]
0x180013fa2  mov     [rsp+0A8h+var_80], rcx
0x180013fa7  mov     [rsp+0A8h+var_70], r9
0x180013fac  mov     [rsp+0A8h+var_68], r10
0x180013fb1  cmp     edx, [rsp+0A8h+arg_50]
0x180013fb8  jl      loc_180013E33
0x180013fbe  mov     r14, [rsp+0A8h+arg_18]
0x180013fc6  mov     rbp, [rsp+0A8h+arg_0]
0x180013fce  mov     r12, [rsp+0A8h+arg_8]
0x180013fd6  mov     r13, [rsp+0A8h+arg_10]
0x180013fde  cmp     [rsp+0A8h+arg_58], 0
0x180013fe6  jz      short loc_180014028
0x180013fe8  xor     ecx, ecx
0x180013fea  test    ebx, ebx
0x180013fec  jle     short loc_180014028
0x180013fee  cmp     r14, [rsp+0A8h+arg_20]
0x180013ff6  ja      short loc_180014028
0x180013ff8  mov     al, [rbp+0]
0x180013ffb  inc     ecx
0x180013ffd  mov     [r13+0], al
0x180014001  mov     al, [r12]
0x180014005  mov     [r14], al
0x180014008  movsxd  rax, [rsp+0A8h+arg_38]
0x180014010  add     rbp, rax
0x180014013  add     r12, rax
0x180014016  movsxd  rax, [rsp+0A8h+arg_40]
0x18001401e  add     r13, rax
0x180014021  add     r14, rax
0x180014024  cmp     ecx, ebx
0x180014026  jl      short loc_180013FEE
0x180014028  cmp     [rsp+0A8h+arg_60], 0
0x180014030  jz      short loc_180014090
0x180014032  mov     edx, [rsp+0A8h+arg_68]
0x180014039  test    edx, edx
0x18001403b  jle     short loc_180014090
0x18001403d  xor     ecx, ecx
0x18001403f  test    ebx, ebx
0x180014041  jle     short loc_180014090
0x180014043  cmp     r8, [rsp+0A8h+arg_20]
0x18001404b  ja      short loc_180014090
0x18001404d  mov     al, [rdi]
0x18001404f  mov     [r11], al
0x180014052  mov     al, [rsi]
0x180014054  mov     [r8], al
0x180014057  cmp     edx, 1
0x18001405a  jle     short loc_180014068
0x18001405c  mov     al, [r11]
0x18001405f  mov     [r9], al
0x180014062  mov     al, [r8]
0x180014065  mov     [r10], al
0x180014068  movsxd  rax, [rsp+0A8h+arg_38]
0x180014070  inc     ecx
0x180014072  add     rdi, rax
0x180014075  add     rsi, rax
0x180014078  movsxd  rax, [rsp+0A8h+arg_40]
0x180014080  add     r11, rax
0x180014083  add     r8, rax
0x180014086  add     r9, rax
0x180014089  add     r10, rax
0x18001408c  cmp     ecx, ebx
0x18001408e  jl      short loc_180014043
0x180014090  add     rsp, 68h
0x180014094  pop     r15
0x180014096  pop     r14
0x180014098  pop     r13
0x18001409a  pop     r12
0x18001409c  pop     rdi
0x18001409d  pop     rsi
0x18001409e  pop     rbp
0x18001409f  pop     rbx
0x1800140a0  retn
```
