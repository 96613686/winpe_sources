# QosTbcRandomSpread

- ea: `0x140015a88`
- end: `0x140015cda`
- name: `QosTbcRandomSpread`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400093fc`

## callees

- `0x140014cf0`
- `0x140014ea0`
- `0x140015a88`
- `0x1400161f0`
- `0x140016700`

## pseudocode

```c
char __fastcall QosTbcRandomSpread(int a1, unsigned int a2, _QWORD *a3, unsigned __int64 a4, unsigned __int64 a5)
{
  unsigned int v7; // r14d
  _QWORD *i; // rbx
  char v9; // r12
  unsigned int v10; // ecx
  _QWORD *v11; // rsi
  char v12; // dl
  __int64 v13; // rax
  int v14; // eax
  int v15; // r8d
  char v16; // al
  unsigned int v17; // esi
  __int64 v18; // rcx
  __m128i v19; // xmm0
  __m128i v20; // xmm0
  __int64 j; // r10
  char v22; // al
  __int64 v23; // r9
  __int64 v24; // rdx
  unsigned __int64 v25; // r12
  _QWORD *v26; // rsi
  __int64 v27; // rax
  int v28; // eax
  int v30; // [rsp+30h] [rbp-91h] BYREF
  int v31; // [rsp+34h] [rbp-8Dh] BYREF
  unsigned int v32; // [rsp+38h] [rbp-89h]
  unsigned __int64 v33; // [rsp+40h] [rbp-81h]
  _OWORD v34[8]; // [rsp+50h] [rbp-71h] BYREF

  v32 = a2;
  v33 = a4;
  v7 = QosgBoundaryPeriod / a2;
  if ( QosgBoundaryPeriod / a2 > 0x40 )
    return 0;
  for ( i = (_QWORD *)*a3; i != a3 && i[3] < a4; i = (_QWORD *)*i )
    ;
  v9 = 0;
  v10 = 0;
  v34[0] = _mm_load_si128((const __m128i *)&_xmm);
  v30 = a1;
  v11 = i;
  v34[1] = v34[0];
  v12 = 1;
  v31 = 0;
  v34[2] = v34[0];
  v34[3] = v34[0];
  while ( v11 != a3 )
  {
    if ( v11[3] >= a5 )
    {
      v9 = v12;
      break;
    }
    v13 = *(v11 - 3);
    v11 = (_QWORD *)*v11;
    v14 = QosAssignSlot(
            *(_DWORD *)(*(_QWORD *)(v13 + 8) + 24LL),
            a1,
            64,
            (unsigned int)v34,
            (__int64)&v31,
            (__int64)&v30);
    v12 = v15 - 63;
    v10 = v15 - 63 + v14;
  }
  v16 = v9;
  v17 = v7;
  if ( v10 < v7 )
    v17 = v10;
  else
    v16 = v12;
  if ( !v16 )
    return 0;
  memset(v34, 0, 0x40u);
  v18 = 0;
  do
  {
    v19 = (__m128i)_mm_and_ps(
                     (__m128)_mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v18), 0), (__m128i)_xmm),
                     (__m128)_xmm);
    v20 = _mm_packus_epi16(v19, v19);
    *(_DWORD *)((char *)&v34[4] + v18) = _mm_cvtsi128_si32(_mm_packus_epi16(v20, v20));
    v18 = (unsigned int)(v18 + 4);
  }
  while ( (unsigned int)v18 < 0x40 );
  for ( j = 0; (unsigned int)j < v17; *((_BYTE *)v34 + v24) = 1 )
  {
    QosgRandomValue = (2147483629 * (unsigned __int64)(unsigned int)QosgRandomValue + 2147483587) % 0x7FFFFFFF;
    v22 = *((_BYTE *)&v34[4] + j);
    v23 = (unsigned int)j + QosgRandomValue % (v7 - (unsigned int)j);
    v24 = *((unsigned __int8 *)&v34[4] + v23);
    *((_BYTE *)&v34[4] + j) = v24;
    j = (unsigned int)(j + 1);
    *((_BYTE *)&v34[4] + v23) = v22;
  }
  v30 = a1;
  v31 = QosSelectSlot(0, 0, v17, v34);
  if ( i != a3 )
  {
    v25 = v33;
    do
    {
      v26 = i + 3;
      if ( i[3] >= a5 )
        break;
      v27 = *(i - 3);
      i = (_QWORD *)*i;
      v28 = QosAssignSlot(
              *(_DWORD *)(*(_QWORD *)(v27 + 8) + 24LL),
              a1,
              v7,
              (unsigned int)v34,
              (__int64)&v31,
              (__int64)&v30);
      *v26 = v25 + v32 * v28;
    }
    while ( i != a3 );
  }
  return 1;
}

```

## disassembly

```asm
0x140015a88  mov     [rsp-8+arg_18], rbx
0x140015a8d  push    rbp
0x140015a8e  push    rsi
0x140015a8f  push    rdi
0x140015a90  push    r12
0x140015a92  push    r13
0x140015a94  push    r14
0x140015a96  push    r15
0x140015a98  lea     rbp, [rsp-1Fh]
0x140015a9d  sub     rsp, 0E0h
0x140015aa4  mov     rax, cs:__security_cookie
0x140015aab  xor     rax, rsp
0x140015aae  mov     [rbp+4Fh+var_40], rax
0x140015ab2  mov     eax, cs:QosgBoundaryPeriod
0x140015ab8  mov     rdi, r8
0x140015abb  mov     r8d, edx
0x140015abe  mov     [rsp+110h+var_D8], edx
0x140015ac2  xor     edx, edx
0x140015ac4  mov     [rsp+110h+var_D0], r9
0x140015ac9  div     r8d
0x140015acc  mov     r15d, ecx
0x140015acf  mov     r14d, eax
0x140015ad2  cmp     eax, 40h ; '@'
0x140015ad5  ja      loc_140015CB0
0x140015adb  mov     rbx, [rdi]
0x140015ade  jmp     short loc_140015AE9
0x140015ae0  cmp     [rbx+18h], r9
0x140015ae4  jnb     short loc_140015AEE
0x140015ae6  mov     rbx, [rbx]
0x140015ae9  cmp     rbx, rdi
0x140015aec  jnz     short loc_140015AE0
0x140015aee  movdqa  xmm0, cs:__xmm@01010101010101010101010101010101
0x140015af6  xor     r12b, r12b
0x140015af9  mov     r13, [rbp+4Fh+arg_20]
0x140015afd  xor     ecx, ecx
0x140015aff  movups  [rbp+4Fh+var_C0], xmm0
0x140015b03  mov     [rsp+110h+var_E0], r15d
0x140015b08  mov     rsi, rbx
0x140015b0b  movups  [rbp+4Fh+var_B0], xmm0
0x140015b0f  lea     edx, [rcx+1]
0x140015b12  mov     [rsp+110h+var_DC], ecx
0x140015b16  movups  [rbp+4Fh+var_A0], xmm0
0x140015b1a  movups  [rbp+4Fh+var_90], xmm0
0x140015b1e  cmp     rsi, rdi
0x140015b21  jz      short loc_140015B69
0x140015b23  cmp     [rsi+18h], r13
0x140015b27  jnb     short loc_140015B66
0x140015b29  mov     rax, [rsi-18h]
0x140015b2d  lea     r9, [rbp+4Fh+var_C0]
0x140015b31  mov     rsi, [rsi]
0x140015b34  mov     r8d, 40h ; '@'
0x140015b3a  mov     edx, r15d
0x140015b3d  mov     rcx, [rax+8]
0x140015b41  lea     rax, [rsp+110h+var_E0]
0x140015b46  mov     [rsp+110h+var_E8], rax
0x140015b4b  lea     rax, [rsp+110h+var_DC]
0x140015b50  mov     [rsp+110h+var_F0], rax
0x140015b55  mov     ecx, [rcx+18h]
0x140015b58  call    QosAssignSlot
0x140015b5d  lea     edx, [r8-3Fh]
0x140015b61  lea     ecx, [rdx+rax]
0x140015b64  jmp     short loc_140015B1E
0x140015b66  mov     r12b, dl
0x140015b69  cmp     ecx, r14d
0x140015b6c  movzx   eax, r12b
0x140015b70  mov     esi, r14d
0x140015b73  cmovnb  eax, edx
0x140015b76  cmovb   esi, ecx
0x140015b79  test    al, al
0x140015b7b  jz      loc_140015CB0
0x140015b81  xor     edx, edx; Val
0x140015b83  lea     rcx, [rbp+4Fh+var_C0]; void *
0x140015b87  lea     r8d, [rdx+40h]; Size
0x140015b8b  call    memset
0x140015b90  xor     ecx, ecx
0x140015b92  movd    xmm0, ecx
0x140015b96  pshufd  xmm0, xmm0, 0
0x140015b9b  paddd   xmm0, cs:__xmm@00000003000000020000000100000000
0x140015ba3  andps   xmm0, cs:__xmm@000000ff000000ff000000ff000000ff
0x140015baa  packuswb xmm0, xmm0
0x140015bae  packuswb xmm0, xmm0
0x140015bb2  movd    [rbp+rcx+4Fh+var_80], xmm0
0x140015bb8  add     ecx, 4
0x140015bbb  cmp     ecx, 40h ; '@'
0x140015bbe  jb      short loc_140015B92
0x140015bc0  xor     r10d, r10d
0x140015bc3  test    esi, esi
0x140015bc5  jz      short loc_140015C3D
0x140015bc7  mov     eax, cs:QosgRandomValue
0x140015bcd  imul    r8, rax, 7FFFFFEDh
0x140015bd4  mov     rax, 200000005h
0x140015bde  add     r8, 7FFFFFC3h
0x140015be5  mul     r8
0x140015be8  mov     rcx, r8
0x140015beb  sub     rcx, rdx
0x140015bee  shr     rcx, 1
0x140015bf1  add     rcx, rdx
0x140015bf4  xor     edx, edx
0x140015bf6  shr     rcx, 1Eh
0x140015bfa  imul    rcx, 7FFFFFFFh
0x140015c01  sub     r8, rcx
0x140015c04  mov     ecx, r14d
0x140015c07  sub     ecx, r10d
0x140015c0a  mov     cs:QosgRandomValue, r8d
0x140015c11  mov     eax, r8d
0x140015c14  div     ecx
0x140015c16  mov     al, byte ptr [rbp+r10+4Fh+var_80]
0x140015c1b  add     edx, r10d
0x140015c1e  mov     r9d, edx
0x140015c21  movzx   edx, byte ptr [rbp+rdx+4Fh+var_80]
0x140015c26  mov     byte ptr [rbp+r10+4Fh+var_80], dl
0x140015c2b  inc     r10d
0x140015c2e  mov     byte ptr [rbp+r9+4Fh+var_80], al
0x140015c33  mov     byte ptr [rbp+rdx+4Fh+var_C0], 1
0x140015c38  cmp     r10d, esi
0x140015c3b  jb      short loc_140015BC7
0x140015c3d  lea     r9, [rbp+4Fh+var_C0]
0x140015c41  mov     [rsp+110h+var_E0], r15d
0x140015c46  mov     r8d, esi
0x140015c49  xor     edx, edx
0x140015c4b  xor     ecx, ecx
0x140015c4d  call    QosSelectSlot
0x140015c52  mov     [rsp+110h+var_DC], eax
0x140015c56  cmp     rbx, rdi
0x140015c59  jz      short loc_140015CAC
0x140015c5b  mov     r12, [rsp+110h+var_D0]
0x140015c60  lea     rsi, [rbx+18h]
0x140015c64  cmp     [rsi], r13
0x140015c67  jnb     short loc_140015CAC
0x140015c69  mov     rax, [rbx-18h]
0x140015c6d  lea     r9, [rbp+4Fh+var_C0]
0x140015c71  mov     rbx, [rbx]
0x140015c74  mov     r8d, r14d
0x140015c77  mov     edx, r15d
0x140015c7a  mov     rcx, [rax+8]
0x140015c7e  lea     rax, [rsp+110h+var_E0]
0x140015c83  mov     [rsp+110h+var_E8], rax
0x140015c88  lea     rax, [rsp+110h+var_DC]
0x140015c8d  mov     [rsp+110h+var_F0], rax
0x140015c92  mov     ecx, [rcx+18h]
0x140015c95  call    QosAssignSlot
0x140015c9a  imul    eax, [rsp+110h+var_D8]
0x140015c9f  mov     ecx, eax
0x140015ca1  add     rcx, r12
0x140015ca4  mov     [rsi], rcx
0x140015ca7  cmp     rbx, rdi
0x140015caa  jnz     short loc_140015C60
0x140015cac  mov     al, 1
0x140015cae  jmp     short loc_140015CB2
0x140015cb0  xor     al, al
0x140015cb2  mov     rcx, [rbp+4Fh+var_40]
0x140015cb6  xor     rcx, rsp; StackCookie
0x140015cb9  call    __security_check_cookie
0x140015cbe  mov     rbx, [rsp+110h+arg_18]
0x140015cc6  add     rsp, 0E0h
0x140015ccd  pop     r15
0x140015ccf  pop     r14
0x140015cd1  pop     r13
0x140015cd3  pop     r12
0x140015cd5  pop     rdi
0x140015cd6  pop     rsi
0x140015cd7  pop     rbp
0x140015cd8  retn
```
