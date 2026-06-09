# PixelMap::BitBlt(PixelMap &,uint,uint,uint,uint,uint,uint)

- ea: `0x180026228`
- end: `0x18002658b`
- name: `?BitBlt@PixelMap@@QEBA_NAEAV1@IIIIII@Z`
- size: `867`
- prototype: `bool __fastcall(PixelMap *__hidden this, struct PixelMap *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800306fc`
- `0x18009deb0`
- `0x1800d9510`

## callees

- `0x18000f5d0`
- `0x18000faac`
- `0x18000fc94`
- `0x180026228`
- `0x18014c328`
- `0x18014c334`

## import_xrefs

- `RDPBASE!MemMoveReverseAligned_SSE` at `0x18002649a`
- `RDPBASE!MemMoveReverseAligned_SSE` at `0x18002649a`
- `RDPBASE!MemCopyAligned_AVX2` at `0x1800264d8`
- `RDPBASE!MemCopyAligned_AVX2` at `0x1800264d8`
- `RDPBASE!GetSupportedSSELevel_SSE` at `0x180026453`
- `RDPBASE!GetSupportedSSELevel_SSE` at `0x1800264b3`
- `RDPBASE!GetSupportedSSELevel_SSE` at `0x180026453`
- `RDPBASE!GetSupportedSSELevel_SSE` at `0x1800264b3`
- `RDPBASE!MemCopyAligned_SSE` at `0x180026501`
- `RDPBASE!MemCopyAligned_SSE` at `0x180026501`

## pseudocode

```c
char __fastcall PixelMap::BitBlt(
        PixelMap *this,
        struct PixelMap *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  int v10; // r9d
  int v11; // eax
  int v12; // r11d
  int v13; // edx
  int v14; // ecx
  int v15; // r13d
  int v16; // eax
  __int64 v17; // rbp
  __int64 v18; // r14
  int v19; // r15d
  unsigned __int8 *v20; // rdi
  unsigned __int8 *v21; // rbx
  unsigned int v22; // r10d
  char v23; // r11
  unsigned int v24; // ecx
  char v25; // r11
  unsigned int v26; // r11d
  unsigned __int8 *v27; // rdx
  BOOL v28; // ecx
  int v29; // r13d
  int v30; // eax
  size_t v31; // r15
  unsigned int i; // r12d
  unsigned int v33; // r12d
  unsigned int v34; // r12d
  int v36; // [rsp+30h] [rbp-58h]
  unsigned __int8 *StartPtr; // [rsp+38h] [rbp-50h]
  unsigned __int8 *EndPtr; // [rsp+40h] [rbp-48h]
  unsigned __int8 *v39; // [rsp+48h] [rbp-40h]

  if ( !PixelMap::RectIsContained(*(_DWORD *)this, *((_DWORD *)this + 1), a3, a4, a5, a6)
    || !PixelMap::RectIsContained(*(_DWORD *)a2, *((_DWORD *)a2 + 1), a7, a8, a5, a6) )
  {
    return 0;
  }
  v11 = *((_DWORD *)a2 + 3);
  v12 = 16;
  if ( v11 == 15 )
  {
    v14 = 15;
    v13 = 16;
  }
  else
  {
    v13 = v11 + 1;
    v14 = (v11 + 1) & 0xF8;
  }
  v15 = *((_DWORD *)this + 3);
  if ( v15 == 15 )
  {
    v16 = 15;
  }
  else
  {
    v12 = v15 + 1;
    v16 = (v15 + 1) & 0xF8;
  }
  if ( v14 != v16 )
    return 0;
  v17 = *((int *)this + 2);
  v18 = *((int *)a2 + 2);
  v19 = (unsigned __int8)(v12 >> 3);
  v36 = 0;
  v20 = (unsigned __int8 *)(a4 * (int)v17 + (unsigned __int64)(unsigned int)(a3 * v19) + *((_QWORD *)this + 3));
  v21 = (unsigned __int8 *)(v10 * (int)v18 + (unsigned __int64)(a7 * (unsigned __int8)(v13 >> 3)) + *((_QWORD *)a2 + 3));
  StartPtr = PixelMap::GetStartPtr(v20, a6, v17);
  if ( v15 == v22 )
    v24 = v22;
  else
    v24 = v23 & 0xF8;
  EndPtr = PixelMap::GetEndPtr(v20, a5, a6, v17, v24);
  v39 = PixelMap::GetStartPtr(v21, a6, v18);
  if ( v15 == 15 )
    v26 = 15;
  else
    v26 = v25 & 0xF8;
  v27 = PixelMap::GetEndPtr(v21, a5, a6, v18, v26);
  if ( StartPtr < v27 && v39 < EndPtr )
  {
    if ( (int)(v17 ^ v18) >= 0 )
    {
      v28 = v39 > StartPtr;
      if ( v28 == &v27[-v18] > &EndPtr[-v17] )
      {
        v29 = 1;
        if ( v28 == (int)v17 > 0 )
        {
          v36 = 1;
          v30 = v17 * (a6 - 1);
          LODWORD(v17) = -(int)v17;
          v20 += v30;
          v21 += (int)(v18 * (a6 - 1));
          LODWORD(v18) = -(int)v18;
        }
        goto LABEL_23;
      }
    }
    return 0;
  }
  v29 = 0;
LABEL_23:
  v31 = a5 * v19;
  if ( (int)GetSupportedSSELevel_SSE() < 2 || (v31 & 3) != 0 || (((unsigned __int8)v20 | (unsigned __int8)v21) & 3) != 0 )
  {
    v34 = 0;
    if ( v29 )
    {
      if ( a6 )
      {
        do
        {
          memmove_0(v21, v20, v31);
          v20 += (int)v17;
          v21 += (int)v18;
          ++v34;
        }
        while ( v34 < a6 );
      }
    }
    else if ( a6 )
    {
      do
      {
        memcpy_0(v21, v20, v31);
        v20 += (int)v17;
        v21 += (int)v18;
        ++v34;
      }
      while ( v34 < a6 );
    }
  }
  else if ( v36 )
  {
    for ( i = 0; i < a6; ++i )
    {
      MemMoveReverseAligned_SSE(v21, v20, (unsigned int)v31);
      v20 += (int)v17;
      v21 += (int)v18;
    }
  }
  else
  {
    v33 = 0;
    if ( (int)GetSupportedSSELevel_SSE() < 5 )
    {
      if ( a6 )
      {
        do
        {
          MemCopyAligned_SSE(v21, v20, (unsigned int)v31);
          v20 += (int)v17;
          v21 += (int)v18;
          ++v33;
        }
        while ( v33 < a6 );
      }
    }
    else if ( a6 )
    {
      do
      {
        MemCopyAligned_AVX2(v21, v20, (unsigned int)v31);
        v20 += (int)v17;
        v21 += (int)v18;
        ++v33;
      }
      while ( v33 < a6 );
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180026228  mov     rax, rsp
0x18002622b  mov     [rax+10h], rbx
0x18002622f  mov     [rax+20h], r9d
0x180026233  mov     [rax+18h], r8d
0x180026237  push    rbp
0x180026238  push    rsi
0x180026239  push    rdi
0x18002623a  push    r12
0x18002623c  push    r13
0x18002623e  push    r14
0x180026240  push    r15
0x180026242  sub     rsp, 50h
0x180026246  mov     esi, [rsp+88h+arg_28]
0x18002624d  mov     rbx, rdx
0x180026250  mov     edx, [rcx+4]; int
0x180026253  mov     rdi, rcx
0x180026256  mov     ecx, [rcx]; int
0x180026258  mov     r12d, [rsp+88h+arg_20]
0x180026260  mov     [rax-60h], esi
0x180026263  mov     [rax-68h], r12d
0x180026267  call    ?RectIsContained@PixelMap@@SA_NHHHHHH@Z; PixelMap::RectIsContained(int,int,int,int,int,int)
0x18002626c  test    al, al
0x18002626e  jz      loc_180026571
0x180026274  mov     r8d, [rsp+88h+arg_30]; int
0x18002627c  mov     edx, [rbx+4]; int
0x18002627f  mov     ecx, [rbx]; int
0x180026281  mov     r9d, [rsp+88h+arg_38]; int
0x180026289  mov     [rsp+88h+var_60], esi; int
0x18002628d  mov     [rsp+88h+var_68], r12d; int
0x180026292  call    ?RectIsContained@PixelMap@@SA_NHHHHHH@Z; PixelMap::RectIsContained(int,int,int,int,int,int)
0x180026297  test    al, al
0x180026299  jz      loc_180026571
0x18002629f  mov     eax, [rbx+0Ch]
0x1800262a2  mov     r11d, 10h
0x1800262a8  mov     r8d, 0F8h
0x1800262ae  lea     r10d, [r11-1]
0x1800262b2  cmp     eax, r10d
0x1800262b5  jz      short loc_1800262C1
0x1800262b7  lea     edx, [rax+1]
0x1800262ba  mov     ecx, edx
0x1800262bc  and     ecx, r8d
0x1800262bf  jmp     short loc_1800262C7
0x1800262c1  mov     ecx, r10d
0x1800262c4  mov     edx, r11d
0x1800262c7  mov     r13d, [rdi+0Ch]
0x1800262cb  cmp     r13d, r10d
0x1800262ce  jz      short loc_1800262DC
0x1800262d0  lea     r11d, [r13+1]
0x1800262d4  mov     eax, r11d
0x1800262d7  and     eax, r8d
0x1800262da  jmp     short loc_1800262DF
0x1800262dc  mov     eax, r10d
0x1800262df  cmp     ecx, eax
0x1800262e1  jnz     loc_180026571
0x1800262e7  movsxd  rbp, dword ptr [rdi+8]
0x1800262eb  mov     eax, r11d
0x1800262ee  movsxd  r14, dword ptr [rbx+8]
0x1800262f2  mov     r8d, ebp; int
0x1800262f5  mov     rdi, [rdi+18h]
0x1800262f9  mov     rbx, [rbx+18h]
0x1800262fd  sar     eax, 3
0x180026300  movzx   r15d, al
0x180026304  mov     eax, ebp
0x180026306  imul    eax, [rsp+88h+arg_18]
0x18002630e  mov     ecx, r15d
0x180026311  imul    ecx, [rsp+88h+arg_10]
0x180026319  sar     edx, 3
0x18002631c  mov     [rsp+88h+var_58], 0
0x180026324  mov     [rsp+88h+arg_0], 0
0x18002632f  cdqe
0x180026331  add     rcx, rax
0x180026334  mov     eax, r14d
0x180026337  add     rdi, rcx
0x18002633a  imul    eax, r9d
0x18002633e  movzx   ecx, dl
0x180026341  mov     edx, esi; unsigned int
0x180026343  imul    ecx, [rsp+88h+arg_30]
0x18002634b  cdqe
0x18002634d  add     rcx, rax
0x180026350  add     rbx, rcx
0x180026353  mov     rcx, rdi; unsigned __int8 *
0x180026356  call    ?GetStartPtr@PixelMap@@SAPEAEPEAEIH@Z; PixelMap::GetStartPtr(uchar *,uint,int)
0x18002635b  mov     [rsp+88h+var_50], rax
0x180026360  cmp     r13d, r10d
0x180026363  jz      short loc_180026370
0x180026365  mov     ecx, r11d
0x180026368  and     ecx, 0F8h
0x18002636e  jmp     short loc_180026373
0x180026370  mov     ecx, r10d
0x180026373  mov     [rsp+88h+var_68], ecx; unsigned int
0x180026377  mov     r9d, ebp; int
0x18002637a  mov     rcx, rdi; unsigned __int8 *
0x18002637d  mov     r8d, esi; unsigned int
0x180026380  mov     edx, r12d; unsigned int
0x180026383  call    ?GetEndPtr@PixelMap@@SAPEAEPEAEIIHI@Z; PixelMap::GetEndPtr(uchar *,uint,uint,int,uint)
0x180026388  mov     rcx, rbx; unsigned __int8 *
0x18002638b  mov     [rsp+88h+var_48], rax
0x180026390  mov     r8d, r14d; int
0x180026393  mov     edx, esi; unsigned int
0x180026395  call    ?GetStartPtr@PixelMap@@SAPEAEPEAEIH@Z; PixelMap::GetStartPtr(uchar *,uint,int)
0x18002639a  mov     [rsp+88h+var_40], rax
0x18002639f  cmp     r13d, 0Fh
0x1800263a3  jz      short loc_1800263AE
0x1800263a5  and     r11d, 0F8h
0x1800263ac  jmp     short loc_1800263B4
0x1800263ae  mov     r11d, 0Fh
0x1800263b4  mov     r9d, r14d; int
0x1800263b7  mov     [rsp+88h+var_68], r11d; unsigned int
0x1800263bc  mov     r8d, esi; unsigned int
0x1800263bf  mov     edx, r12d; unsigned int
0x1800263c2  mov     rcx, rbx; unsigned __int8 *
0x1800263c5  call    ?GetEndPtr@PixelMap@@SAPEAEPEAEIIHI@Z; PixelMap::GetEndPtr(uchar *,uint,uint,int,uint)
0x1800263ca  mov     r9, [rsp+88h+var_50]
0x1800263cf  mov     rdx, rax
0x1800263d2  mov     r10d, 1
0x1800263d8  cmp     r9, rax
0x1800263db  jnb     short loc_180026447
0x1800263dd  mov     r8, [rsp+88h+var_48]
0x1800263e2  mov     rax, [rsp+88h+var_40]
0x1800263e7  cmp     rax, r8
0x1800263ea  jnb     short loc_180026447
0x1800263ec  mov     ecx, r14d
0x1800263ef  xor     ecx, ebp
0x1800263f1  js      loc_180026571
0x1800263f7  xor     ecx, ecx
0x1800263f9  cmp     rax, r9
0x1800263fc  setnbe  cl
0x1800263ff  xor     eax, eax
0x180026401  sub     rdx, r14
0x180026404  sub     r8, rbp
0x180026407  cmp     rdx, r8
0x18002640a  setnbe  al
0x18002640d  cmp     ecx, eax
0x18002640f  jnz     loc_180026571
0x180026415  xor     eax, eax
0x180026417  mov     r13d, r10d
0x18002641a  test    ebp, ebp
0x18002641c  setnle  al
0x18002641f  cmp     ecx, eax
0x180026421  jnz     short loc_18002644F
0x180026423  lea     edx, [rsi-1]
0x180026426  mov     [rsp+88h+var_58], r10d
0x18002642b  mov     eax, edx
0x18002642d  imul    edx, r14d
0x180026431  imul    eax, ebp
0x180026434  neg     ebp
0x180026436  movsxd  rcx, eax
0x180026439  movsxd  rax, edx
0x18002643c  add     rdi, rcx
0x18002643f  add     rbx, rax
0x180026442  neg     r14d
0x180026445  jmp     short loc_18002644F
0x180026447  mov     r13d, [rsp+88h+arg_0]
0x18002644f  imul    r15d, r12d
0x180026453  call    cs:__imp_GetSupportedSSELevel_SSE
0x180026459  cmp     eax, 2
0x18002645c  jl      loc_180026517
0x180026462  test    r15b, 3
0x180026466  jnz     loc_180026517
0x18002646c  mov     al, bl
0x18002646e  or      al, dil
0x180026471  test    al, 3
0x180026473  jnz     loc_180026517
0x180026479  cmp     [rsp+88h+var_58], 0
0x18002647e  jz      short loc_1800264B3
0x180026480  xor     r12d, r12d
0x180026483  test    esi, esi
0x180026485  jz      loc_18002656D
0x18002648b  movsxd  rbp, ebp
0x18002648e  movsxd  r14, r14d
0x180026491  mov     r8d, r15d
0x180026494  mov     rdx, rdi
0x180026497  mov     rcx, rbx
0x18002649a  call    cs:__imp_MemMoveReverseAligned_SSE
0x1800264a0  add     rdi, rbp
0x1800264a3  add     rbx, r14
0x1800264a6  inc     r12d
0x1800264a9  cmp     r12d, esi
0x1800264ac  jb      short loc_180026491
0x1800264ae  jmp     loc_18002656D
0x1800264b3  call    cs:__imp_GetSupportedSSELevel_SSE
0x1800264b9  xor     r12d, r12d
0x1800264bc  cmp     eax, 5
0x1800264bf  jl      short loc_1800264EE
0x1800264c1  test    esi, esi
0x1800264c3  jz      loc_18002656D
0x1800264c9  movsxd  rbp, ebp
0x1800264cc  movsxd  r14, r14d
0x1800264cf  mov     r8d, r15d
0x1800264d2  mov     rdx, rdi
0x1800264d5  mov     rcx, rbx
0x1800264d8  call    cs:__imp_MemCopyAligned_AVX2
0x1800264de  add     rdi, rbp
0x1800264e1  add     rbx, r14
0x1800264e4  inc     r12d
0x1800264e7  cmp     r12d, esi
0x1800264ea  jb      short loc_1800264CF
0x1800264ec  jmp     short loc_18002656D
0x1800264ee  test    esi, esi
0x1800264f0  jz      short loc_18002656D
0x1800264f2  movsxd  rbp, ebp
0x1800264f5  movsxd  r14, r14d
0x1800264f8  mov     r8d, r15d
0x1800264fb  mov     rdx, rdi
0x1800264fe  mov     rcx, rbx
0x180026501  call    cs:__imp_MemCopyAligned_SSE
0x180026507  add     rdi, rbp
0x18002650a  add     rbx, r14
0x18002650d  inc     r12d
0x180026510  cmp     r12d, esi
0x180026513  jb      short loc_1800264F8
0x180026515  jmp     short loc_18002656D
0x180026517  xor     r12d, r12d
0x18002651a  test    r13d, r13d
0x18002651d  jz      short loc_180026547
0x18002651f  test    esi, esi
0x180026521  jz      short loc_18002656D
0x180026523  movsxd  rbp, ebp
0x180026526  movsxd  r14, r14d
0x180026529  mov     r8, r15; Size
0x18002652c  mov     rdx, rdi; Src
0x18002652f  mov     rcx, rbx; void *
0x180026532  call    memmove_0
0x180026537  add     rdi, rbp
0x18002653a  add     rbx, r14
0x18002653d  inc     r12d
0x180026540  cmp     r12d, esi
0x180026543  jb      short loc_180026529
0x180026545  jmp     short loc_18002656D
0x180026547  test    esi, esi
0x180026549  jz      short loc_18002656D
0x18002654b  movsxd  rbp, ebp
0x18002654e  movsxd  r14, r14d
0x180026551  mov     r8, r15; Size
0x180026554  mov     rdx, rdi; Src
0x180026557  mov     rcx, rbx; void *
0x18002655a  call    memcpy_0
0x18002655f  add     rdi, rbp
0x180026562  add     rbx, r14
0x180026565  inc     r12d
0x180026568  cmp     r12d, esi
0x18002656b  jb      short loc_180026551
0x18002656d  mov     al, 1
0x18002656f  jmp     short loc_180026573
0x180026571  xor     al, al
0x180026573  mov     rbx, [rsp+88h+arg_8]
0x18002657b  add     rsp, 50h
0x18002657f  pop     r15
0x180026581  pop     r14
0x180026583  pop     r13
0x180026585  pop     r12
0x180026587  pop     rdi
0x180026588  pop     rsi
0x180026589  pop     rbp
0x18002658a  retn
```
