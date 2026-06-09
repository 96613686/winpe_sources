# HuftBuild

- ea: `0x1800078e0`
- end: `0x180007da0`
- name: `HuftBuild`
- size: `1216`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, unsigned int, __int64, unsigned int, __int64, unsigned int, __int64, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007260`
- `0x180009158`

## callees

- `0x1800078e0`
- `0x180014dc0`
- `0x18001562a`

## pseudocode

```c
__int64 __fastcall HuftBuild(
        unsigned int *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        unsigned int a9,
        unsigned int *a10)
{
  unsigned int *v12; // rcx
  unsigned int v13; // edx
  __int64 v14; // rax
  unsigned int v15; // r8d
  unsigned int v16; // r12d
  unsigned int i; // ecx
  signed int v18; // r13d
  unsigned int v19; // edx
  unsigned int v20; // eax
  int v21; // r8d
  int v22; // r8d
  signed int v23; // r15d
  int v24; // eax
  char *v25; // rcx
  char *v26; // r8
  unsigned int j; // edx
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned int v31; // edx
  unsigned int *v32; // r14
  int v33; // esi
  unsigned int v34; // r8d
  int v35; // edi
  unsigned __int64 v36; // r11
  unsigned int v37; // r10d
  unsigned int v38; // r15d
  unsigned int v39; // eax
  unsigned int v40; // r9d
  int v41; // eax
  unsigned int v42; // ecx
  unsigned int k; // eax
  __int64 v44; // rcx
  unsigned int m; // eax
  unsigned int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rbx
  char v49; // di
  unsigned int v50; // edx
  unsigned int v51; // ecx
  unsigned int v52; // eax
  __int64 v53; // r11
  int *v54; // r10
  int v55; // eax
  unsigned int v56; // r11d
  unsigned int v57; // eax
  unsigned int v59; // [rsp+20h] [rbp-E0h]
  int v60; // [rsp+24h] [rbp-DCh]
  __int128 v61; // [rsp+28h] [rbp-D8h]
  unsigned int v62; // [rsp+38h] [rbp-C8h]
  unsigned int v63; // [rsp+3Ch] [rbp-C4h]
  int v66; // [rsp+48h] [rbp-B8h]
  int v68; // [rsp+70h] [rbp-90h] BYREF
  char v69; // [rsp+74h] [rbp-8Ch] BYREF
  _DWORD v70[2]; // [rsp+C0h] [rbp-40h]
  char v71; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v72[16]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v73[288]; // [rsp+190h] [rbp+90h] BYREF

  memset_0(v72, 0, sizeof(v72));
  v61 = 0;
  if ( a2 > 0x120 )
    return 2;
  memset_0(&v68, 0, 0x44u);
  v12 = a1;
  v13 = a2;
  do
  {
    v14 = *v12++;
    ++*(&v68 + v14);
    --v13;
  }
  while ( v13 );
  if ( v68 == a2 )
  {
    *a10 = 0;
    return 0;
  }
  v15 = *a10;
  v16 = 1;
  for ( i = 1; i <= 0x10; ++i )
  {
    if ( *(&v68 + i) )
      break;
  }
  v18 = i;
  if ( v15 < i )
    v15 = i;
  v19 = 16;
  do
  {
    if ( *(&v68 + v19) )
      break;
    --v19;
  }
  while ( v19 );
  v20 = v19;
  if ( v15 <= v19 )
    v20 = v15;
  v21 = 1 << i;
  v59 = v20;
  *a10 = v20;
  while ( i < v19 )
  {
    v22 = v21 - *(&v68 + i);
    if ( v22 < 0 )
      return 2;
    ++i;
    v21 = 2 * v22;
  }
  v66 = v21 - *(&v68 + v19);
  if ( v66 < 0 )
    return 2;
  *(&v68 + v19) = v21;
  v23 = v19;
  v63 = v19;
  v70[1] = 0;
  v24 = 0;
  v25 = &v69;
  v26 = &v71;
  for ( j = v19 - 1; j; --j )
  {
    v24 += *(_DWORD *)v25;
    v25 += 4;
    *(_DWORD *)v26 = v24;
    v26 += 4;
  }
  v28 = 0;
  while ( 1 )
  {
    v29 = *a1;
    if ( (_DWORD)v29 )
    {
      if ( (unsigned int)v29 > 0x10 )
        return 2;
      v30 = (unsigned int)v70[v29];
      if ( (unsigned int)v30 >= 0x120 )
        return 2;
      v73[v30] = v28;
      v70[v29] = v30 + 1;
    }
    if ( ++v28 >= a2 )
      break;
    ++a1;
  }
  v31 = v59;
  v32 = v73;
  v62 = 0;
  v33 = -v59;
  v70[0] = 0;
  v34 = 0;
  v35 = -1;
  v36 = 0;
  v37 = 0;
LABEL_30:
  if ( v18 <= v23 )
  {
    v38 = *(&v68 + v18);
    while ( 1 )
    {
      v39 = v38;
      v40 = v38--;
      if ( !v39 )
      {
        v23 = v63;
        ++v18;
        goto LABEL_30;
      }
      while ( 1 )
      {
        v41 = v31 + v33;
        if ( v18 <= (int)(v31 + v33) )
          break;
        v48 = v35;
        v60 = v35 + 1;
        if ( v35 + 1 >= 16 )
          return 2;
        v49 = v33;
        v50 = (unsigned __int16)v63 - v41;
        v33 = v41;
        if ( v50 > v59 )
          v50 = (unsigned __int16)v59;
        v51 = v18 - v41;
        v52 = 1 << (v18 - v41);
        if ( v52 > v40 )
        {
          v54 = &v68 + v18;
          v55 = v52 - v38 - 1;
          if ( ++v51 < v50 )
          {
            do
            {
              v56 = v54[1];
              ++v54;
              v57 = 2 * v55;
              if ( v57 <= v56 )
                break;
              v55 = v57 - v56;
              ++v51;
            }
            while ( v51 < v50 );
          }
        }
        v37 = 1 << v51;
        v53 = v62;
        v62 += 1 << v51;
        if ( v62 > a9 )
          return 3;
        v36 = a8 + 16 * v53;
        v72[v60] = v36;
        if ( v60 )
        {
          LOBYTE(v61) = v51 + 16;
          v70[v60] = v34;
          BYTE1(v61) = v59;
          *(_DWORD *)((char *)&v61 + 10) = v36 >> 16;
          WORD4(v61) = v36;
          HIWORD(v61) = HIWORD(v36);
          *(_OWORD *)(v72[v48] + 16 * ((unsigned __int64)v34 >> v49)) = v61;
        }
        v31 = v59;
        v35 = v60;
      }
      if ( v32 >= &v73[a2] )
        goto LABEL_61;
      v42 = *v32;
      if ( *v32 < a3 )
      {
        if ( v42 >= 0x100 )
          LOBYTE(v61) = 15;
        else
          LOBYTE(v61) = 16;
        WORD4(v61) = *v32++;
        goto LABEL_39;
      }
      v46 = a7;
      if ( a5 < a7 )
        v46 = a5;
      if ( v42 >= a3 + v46 )
      {
LABEL_61:
        LOBYTE(v61) = 99;
      }
      else
      {
        v47 = 2LL * (v42 - a3);
        ++v32;
        LOBYTE(v61) = *(_BYTE *)(v47 + a6);
        WORD4(v61) = *(_WORD *)(v47 + a4);
      }
LABEL_39:
      for ( k = v34 >> v33; k < v37; *(_OWORD *)(v36 + 16 * v44) = v61 )
      {
        v44 = k;
        k += 1 << (v18 - v33);
        BYTE1(v61) = v18 - v33;
      }
      for ( m = 1 << (v18 - 1); (m & v34) != 0; m >>= 1 )
        v34 ^= m;
      v34 ^= m;
      while ( (v34 & ((1 << v33) - 1)) != v70[v35] )
      {
        if ( --v35 < 0 )
          return 2;
        v33 -= v59;
      }
      v31 = v59;
    }
  }
  if ( !v66 || v23 == 1 )
    return 0;
  return v16;
}

```

## disassembly

```asm
0x1800078e0  mov     [rsp-8+arg_10], rbx
0x1800078e5  push    rbp
0x1800078e6  push    rsi
0x1800078e7  push    rdi
0x1800078e8  push    r12
0x1800078ea  push    r13
0x1800078ec  push    r14
0x1800078ee  push    r15
0x1800078f0  lea     rbp, [rsp-520h]
0x1800078f8  sub     rsp, 620h
0x1800078ff  mov     rax, cs:__security_cookie
0x180007906  xor     rax, rsp
0x180007909  mov     [rbp+550h+var_40], rax
0x180007910  mov     rax, [rbp+550h+arg_38]
0x180007917  mov     esi, edx
0x180007919  mov     rdi, [rbp+550h+arg_48]
0x180007920  mov     rbx, rcx
0x180007923  mov     [rsp+650h+var_60C], r8d
0x180007928  lea     rcx, [rbp+550h+var_540]; void *
0x18000792c  mov     [rsp+650h+var_610], edx
0x180007930  mov     r8d, 80h; Size
0x180007936  xor     edx, edx; Val
0x180007938  mov     [rsp+650h+var_5F0], rax
0x18000793d  mov     [rsp+650h+var_5E8], r9
0x180007942  call    memset_0
0x180007947  xorps   xmm0, xmm0
0x18000794a  movups  [rsp+650h+var_628], xmm0
0x18000794f  cmp     esi, 120h
0x180007955  ja      loc_180007D67
0x18000795b  xor     edx, edx; Val
0x18000795d  lea     rcx, [rsp+650h+var_5E0]; void *
0x180007962  mov     r8d, 44h ; 'D'; Size
0x180007968  call    memset_0
0x18000796d  mov     rcx, rbx
0x180007970  mov     edx, esi
0x180007972  nop     dword ptr [rax+00h]
0x180007976  nop     word ptr [rax+rax+00000000h]
0x180007980  mov     eax, [rcx]
0x180007982  lea     rcx, [rcx+4]
0x180007986  inc     [rsp+rax*4+650h+var_5E0]
0x18000798a  add     edx, 0FFFFFFFFh
0x18000798d  jnz     short loc_180007980
0x18000798f  cmp     [rsp+650h+var_5E0], esi
0x180007993  jz      loc_180007D7F
0x180007999  mov     r8d, [rdi]
0x18000799c  mov     r12d, 1
0x1800079a2  mov     ecx, r12d
0x1800079a5  mov     eax, ecx
0x1800079a7  cmp     [rsp+rax*4+650h+var_5E0], 0
0x1800079ac  jnz     short loc_1800079B5
0x1800079ae  inc     ecx
0x1800079b0  cmp     ecx, 10h
0x1800079b3  jbe     short loc_1800079A5
0x1800079b5  mov     r13d, ecx
0x1800079b8  cmp     r8d, ecx
0x1800079bb  jb      loc_180007D89
0x1800079c1  mov     edx, 10h
0x1800079c6  mov     eax, edx
0x1800079c8  cmp     [rsp+rax*4+650h+var_5E0], 0
0x1800079cd  jnz     short loc_1800079D4
0x1800079cf  add     edx, 0FFFFFFFFh
0x1800079d2  jnz     short loc_1800079C6
0x1800079d4  cmp     r8d, edx
0x1800079d7  mov     eax, edx
0x1800079d9  cmovbe  eax, r8d
0x1800079dd  mov     r8d, r12d
0x1800079e0  shl     r8d, cl
0x1800079e3  mov     [rsp+650h+var_630], eax
0x1800079e7  mov     [rdi], eax
0x1800079e9  cmp     ecx, edx
0x1800079eb  jnb     short loc_180007A01
0x1800079ed  mov     eax, ecx
0x1800079ef  sub     r8d, [rsp+rax*4+650h+var_5E0]
0x1800079f4  js      loc_180007D67
0x1800079fa  inc     ecx
0x1800079fc  add     r8d, r8d
0x1800079ff  jmp     short loc_1800079E9
0x180007a01  mov     eax, edx
0x180007a03  mov     ecx, r8d
0x180007a06  sub     ecx, [rsp+rax*4+650h+var_5E0]
0x180007a0a  mov     [rsp+650h+var_608], ecx
0x180007a0e  js      loc_180007D67
0x180007a14  xor     r9d, r9d
0x180007a17  mov     [rsp+rax*4+650h+var_5E0], r8d
0x180007a1c  mov     r15d, edx
0x180007a1f  mov     [rsp+650h+var_614], edx
0x180007a23  mov     [rbp+550h+var_58C], r9d
0x180007a27  mov     eax, r9d
0x180007a2a  lea     rcx, [rsp+650h+var_5DC]
0x180007a2f  lea     r8, [rbp+550h+var_588]
0x180007a33  add     edx, 0FFFFFFFFh
0x180007a36  jz      short loc_180007A52
0x180007a38  nop     dword ptr [rax+rax+00000000h]
0x180007a40  add     eax, [rcx]
0x180007a42  lea     rcx, [rcx+4]
0x180007a46  mov     [r8], eax
0x180007a49  lea     r8, [r8+4]
0x180007a4d  add     edx, 0FFFFFFFFh
0x180007a50  jnz     short loc_180007A40
0x180007a52  mov     ecx, r9d
0x180007a55  mov     eax, [rbx]
0x180007a57  test    eax, eax
0x180007a59  jz      short loc_180007A89
0x180007a5b  cmp     eax, 10h
0x180007a5e  ja      loc_180007D67
0x180007a64  lea     r8, [rbp+550h+var_590]
0x180007a68  mov     edx, [r8+rax*4]
0x180007a6c  lea     r8, [r8+rax*4]
0x180007a70  cmp     edx, 120h
0x180007a76  jnb     loc_180007D67
0x180007a7c  lea     eax, [rdx+1]
0x180007a7f  mov     [rbp+rdx*4+550h+var_4C0], ecx
0x180007a86  mov     [r8], eax
0x180007a89  inc     ecx
0x180007a8b  cmp     ecx, esi
0x180007a8d  jnb     short loc_180007A95
0x180007a8f  add     rbx, 4
0x180007a93  jmp     short loc_180007A55
0x180007a95  mov     edx, [rsp+650h+var_630]
0x180007a99  lea     r14, [rbp+550h+var_4C0]
0x180007aa0  mov     esi, edx
0x180007aa2  mov     [rsp+650h+var_618], r9d
0x180007aa7  neg     esi
0x180007aa9  mov     [rbp+550h+var_590], r9d
0x180007aad  mov     r8d, r9d
0x180007ab0  mov     edi, 0FFFFFFFFh
0x180007ab5  mov     r11, r9
0x180007ab8  mov     r10d, r9d
0x180007abb  nop     dword ptr [rax+rax+00h]
0x180007ac0  cmp     r13d, r15d
0x180007ac3  jg      loc_180007D30
0x180007ac9  movsxd  rax, r13d
0x180007acc  mov     r15d, [rsp+rax*4+650h+var_5E0]
0x180007ad1  lea     rax, [rsp+rax*4+650h+var_5E0]
0x180007ad6  mov     [rsp+650h+var_5F8], rax
0x180007adb  nop     dword ptr [rax+rax+00h]
0x180007ae0  mov     eax, r15d
0x180007ae3  mov     r9d, r15d
0x180007ae6  dec     r15d
0x180007ae9  test    eax, eax
0x180007aeb  jz      loc_180007CDB
0x180007af1  lea     eax, [rdx+rsi]
0x180007af4  cmp     r13d, eax
0x180007af7  jg      loc_180007BFD
0x180007afd  movzx   eax, r13b
0x180007b01  lea     rcx, [rbp+550h+var_4C0]
0x180007b08  sub     al, sil
0x180007b0b  mov     byte ptr [rsp+650h+var_628+1], al
0x180007b0f  mov     eax, [rsp+650h+var_610]
0x180007b13  lea     rcx, [rcx+rax*4]
0x180007b17  cmp     r14, rcx
0x180007b1a  jnb     loc_180007CE8
0x180007b20  mov     ecx, [r14]
0x180007b23  mov     edx, [rsp+650h+var_60C]
0x180007b27  cmp     ecx, edx
0x180007b29  jnb     loc_180007BB2
0x180007b2f  cmp     ecx, 100h
0x180007b35  jnb     loc_180007D6E
0x180007b3b  mov     byte ptr [rsp+650h+var_628], 10h
0x180007b40  mov     word ptr [rsp+650h+var_628+8], cx
0x180007b45  add     r14, 4
0x180007b49  mov     ecx, r13d
0x180007b4c  mov     edx, r12d
0x180007b4f  sub     ecx, esi
0x180007b51  mov     eax, r8d
0x180007b54  shl     edx, cl
0x180007b56  mov     ecx, esi
0x180007b58  shr     eax, cl
0x180007b5a  cmp     eax, r10d
0x180007b5d  jnb     short loc_180007B75
0x180007b5f  movups  xmm0, [rsp+650h+var_628]
0x180007b64  mov     ecx, eax
0x180007b66  add     eax, edx
0x180007b68  add     rcx, rcx
0x180007b6b  movups  xmmword ptr [r11+rcx*8], xmm0
0x180007b70  cmp     eax, r10d
0x180007b73  jb      short loc_180007B64
0x180007b75  lea     ecx, [r13-1]
0x180007b79  mov     eax, r12d
0x180007b7c  shl     eax, cl
0x180007b7e  test    r8d, eax
0x180007b81  jz      short loc_180007B8D
0x180007b83  xor     r8d, eax
0x180007b86  shr     eax, 1
0x180007b88  test    r8d, eax
0x180007b8b  jnz     short loc_180007B83
0x180007b8d  xor     r8d, eax
0x180007b90  mov     ecx, esi
0x180007b92  movsxd  rax, edi
0x180007b95  mov     edx, r12d
0x180007b98  shl     edx, cl
0x180007b9a  dec     edx
0x180007b9c  and     edx, r8d
0x180007b9f  cmp     edx, [rbp+rax*4+550h+var_590]
0x180007ba3  jnz     loc_180007CC9
0x180007ba9  mov     edx, [rsp+650h+var_630]
0x180007bad  jmp     loc_180007AE0
0x180007bb2  mov     eax, [rbp+550h+arg_30]
0x180007bb8  mov     r9d, [rbp+550h+arg_20]
0x180007bbf  cmp     r9d, eax
0x180007bc2  jb      loc_180007D91
0x180007bc8  add     eax, edx
0x180007bca  cmp     ecx, eax
0x180007bcc  jnb     loc_180007CE8
0x180007bd2  mov     rax, [rbp+550h+arg_28]
0x180007bd9  sub     ecx, edx
0x180007bdb  add     rcx, rcx
0x180007bde  add     r14, 4
0x180007be2  movzx   eax, byte ptr [rcx+rax]
0x180007be6  mov     byte ptr [rsp+650h+var_628], al
0x180007bea  mov     rax, [rsp+650h+var_5E8]
0x180007bef  movzx   eax, word ptr [rcx+rax]
0x180007bf3  mov     word ptr [rsp+650h+var_628+8], ax
0x180007bf8  jmp     loc_180007B49
0x180007bfd  movsxd  rbx, edi
0x180007c00  inc     edi
0x180007c02  mov     [rsp+650h+var_62C], edi
0x180007c06  cmp     edi, 10h
0x180007c09  jge     loc_180007D67
0x180007c0f  movzx   edx, word ptr [rsp+650h+var_614]
0x180007c14  mov     edi, esi
0x180007c16  sub     edx, eax
0x180007c18  mov     esi, eax
0x180007c1a  mov     eax, [rsp+650h+var_630]
0x180007c1e  cmp     edx, eax
0x180007c20  ja      loc_180007CF2
0x180007c26  mov     ecx, r13d
0x180007c29  mov     eax, r12d
0x180007c2c  sub     ecx, esi
0x180007c2e  shl     eax, cl
0x180007c30  cmp     eax, r9d
0x180007c33  ja      loc_180007CFA
0x180007c39  mov     eax, [rsp+650h+var_618]
0x180007c3d  mov     r10d, r12d
0x180007c40  shl     r10d, cl
0x180007c43  mov     r11d, eax
0x180007c46  add     eax, r10d
0x180007c49  mov     [rsp+650h+var_618], eax
0x180007c4d  cmp     eax, [rbp+550h+arg_40]
0x180007c53  ja      loc_180007D99
0x180007c59  movsxd  rdx, [rsp+650h+var_62C]
0x180007c5e  shl     r11, 4
0x180007c62  add     r11, [rsp+650h+var_5F0]
0x180007c67  mov     [rsp+650h+var_600], r11
0x180007c6c  mov     [rbp+rdx*8+550h+var_540], r11
0x180007c71  test    edx, edx
0x180007c73  jz      short loc_180007CBC
0x180007c75  mov     eax, [rsp+650h+var_630]
0x180007c79  add     cl, 10h
0x180007c7c  mov     byte ptr [rsp+650h+var_628], cl
0x180007c80  movzx   ecx, dil
0x180007c84  mov     [rbp+rdx*4+550h+var_590], r8d
0x180007c89  mov     byte ptr [rsp+650h+var_628+1], al
0x180007c8d  mov     eax, dword ptr [rsp+650h+var_600+2]
0x180007c91  mov     dword ptr [rsp+650h+var_628+0Ah], eax
0x180007c95  movzx   eax, word ptr [rsp+650h+var_600+6]
0x180007c9a  mov     edx, r8d
0x180007c9d  shr     rdx, cl
0x180007ca0  mov     rcx, [rbp+rbx*8+550h+var_540]
0x180007ca5  add     rdx, rdx
0x180007ca8  mov     word ptr [rsp+650h+var_628+8], r11w
0x180007cae  mov     word ptr [rsp+650h+var_628+0Eh], ax
0x180007cb3  movups  xmm0, [rsp+650h+var_628]
0x180007cb8  movups  xmmword ptr [rcx+rdx*8], xmm0
0x180007cbc  mov     edx, [rsp+650h+var_630]
0x180007cc0  mov     edi, [rsp+650h+var_62C]
0x180007cc4  jmp     loc_180007AF1
0x180007cc9  sub     edi, r12d
0x180007ccc  js      loc_180007D67
0x180007cd2  sub     esi, [rsp+650h+var_630]
0x180007cd6  jmp     loc_180007B90
0x180007cdb  mov     r15d, [rsp+650h+var_614]
0x180007ce0  inc     r13d
0x180007ce3  jmp     loc_180007AC0
0x180007ce8  mov     byte ptr [rsp+650h+var_628], 63h ; 'c'
0x180007ced  jmp     loc_180007B49
0x180007cf2  movzx   edx, ax
0x180007cf5  jmp     loc_180007C26
0x180007cfa  mov     r10, [rsp+650h+var_5F8]
0x180007cff  sub     eax, r15d
0x180007d02  dec     eax
0x180007d04  inc     ecx
0x180007d06  cmp     ecx, edx
0x180007d08  jnb     loc_180007C39
0x180007d0e  mov     r11d, [r10+4]
0x180007d12  lea     r10, [r10+4]
0x180007d16  add     eax, eax
0x180007d18  cmp     eax, r11d
0x180007d1b  jbe     loc_180007C39
0x180007d21  sub     eax, r11d
0x180007d24  inc     ecx
0x180007d26  cmp     ecx, edx
0x180007d28  jnb     loc_180007C39
0x180007d2e  jmp     short loc_180007D0E
0x180007d30  cmp     [rsp+650h+var_608], 0
0x180007d35  jnz     short loc_180007D78
0x180007d37  xor     r12d, r12d
0x180007d3a  mov     eax, r12d
0x180007d3d  mov     rcx, [rbp+550h+var_40]
0x180007d44  xor     rcx, rsp; StackCookie
  ... truncated ...
```
