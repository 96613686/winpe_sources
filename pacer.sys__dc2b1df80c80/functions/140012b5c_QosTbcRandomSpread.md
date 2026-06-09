# QosTbcRandomSpread

- ea: `0x140012b5c`
- end: `0x140012dae`
- name: `QosTbcRandomSpread`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000bdf4`

## callees

- `0x14001214c`
- `0x1400122fc`
- `0x140012b5c`
- `0x140013110`
- `0x140013600`

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
0x140012b5c  mov     [rsp-8+arg_18], rbx
0x140012b61  push    rbp
0x140012b62  push    rsi
0x140012b63  push    rdi
0x140012b64  push    r12
0x140012b66  push    r13
0x140012b68  push    r14
0x140012b6a  push    r15
0x140012b6c  lea     rbp, [rsp-1Fh]
0x140012b71  sub     rsp, 0E0h
0x140012b78  mov     rax, cs:__security_cookie
0x140012b7f  xor     rax, rsp
0x140012b82  mov     [rbp+4Fh+var_40], rax
0x140012b86  mov     eax, cs:QosgBoundaryPeriod
0x140012b8c  mov     rdi, r8
0x140012b8f  mov     r8d, edx
0x140012b92  mov     [rsp+110h+var_D8], edx
0x140012b96  xor     edx, edx
0x140012b98  mov     [rsp+110h+var_D0], r9
0x140012b9d  div     r8d
0x140012ba0  mov     r15d, ecx
0x140012ba3  mov     r14d, eax
0x140012ba6  cmp     eax, 40h ; '@'
0x140012ba9  ja      loc_140012D84
0x140012baf  mov     rbx, [rdi]
0x140012bb2  jmp     short loc_140012BBD
0x140012bb4  cmp     [rbx+18h], r9
0x140012bb8  jnb     short loc_140012BC2
0x140012bba  mov     rbx, [rbx]
0x140012bbd  cmp     rbx, rdi
0x140012bc0  jnz     short loc_140012BB4
0x140012bc2  movdqa  xmm0, cs:__xmm@01010101010101010101010101010101
0x140012bca  xor     r12b, r12b
0x140012bcd  mov     r13, [rbp+4Fh+arg_20]
0x140012bd1  xor     ecx, ecx
0x140012bd3  movups  [rbp+4Fh+var_C0], xmm0
0x140012bd7  mov     [rsp+110h+var_E0], r15d
0x140012bdc  mov     rsi, rbx
0x140012bdf  movups  [rbp+4Fh+var_B0], xmm0
0x140012be3  lea     edx, [rcx+1]
0x140012be6  mov     [rsp+110h+var_DC], ecx
0x140012bea  movups  [rbp+4Fh+var_A0], xmm0
0x140012bee  movups  [rbp+4Fh+var_90], xmm0
0x140012bf2  cmp     rsi, rdi
0x140012bf5  jz      short loc_140012C3D
0x140012bf7  cmp     [rsi+18h], r13
0x140012bfb  jnb     short loc_140012C3A
0x140012bfd  mov     rax, [rsi-18h]
0x140012c01  lea     r9, [rbp+4Fh+var_C0]
0x140012c05  mov     rsi, [rsi]
0x140012c08  mov     r8d, 40h ; '@'
0x140012c0e  mov     edx, r15d
0x140012c11  mov     rcx, [rax+8]
0x140012c15  lea     rax, [rsp+110h+var_E0]
0x140012c1a  mov     [rsp+110h+var_E8], rax
0x140012c1f  lea     rax, [rsp+110h+var_DC]
0x140012c24  mov     [rsp+110h+var_F0], rax
0x140012c29  mov     ecx, [rcx+18h]
0x140012c2c  call    QosAssignSlot
0x140012c31  lea     edx, [r8-3Fh]
0x140012c35  lea     ecx, [rdx+rax]
0x140012c38  jmp     short loc_140012BF2
0x140012c3a  mov     r12b, dl
0x140012c3d  cmp     ecx, r14d
0x140012c40  movzx   eax, r12b
0x140012c44  mov     esi, r14d
0x140012c47  cmovnb  eax, edx
0x140012c4a  cmovb   esi, ecx
0x140012c4d  test    al, al
0x140012c4f  jz      loc_140012D84
0x140012c55  xor     edx, edx; Val
0x140012c57  lea     rcx, [rbp+4Fh+var_C0]; void *
0x140012c5b  lea     r8d, [rdx+40h]; Size
0x140012c5f  call    memset
0x140012c64  xor     ecx, ecx
0x140012c66  movd    xmm0, ecx
0x140012c6a  pshufd  xmm0, xmm0, 0
0x140012c6f  paddd   xmm0, cs:__xmm@00000003000000020000000100000000
0x140012c77  andps   xmm0, cs:__xmm@000000ff000000ff000000ff000000ff
0x140012c7e  packuswb xmm0, xmm0
0x140012c82  packuswb xmm0, xmm0
0x140012c86  movd    [rbp+rcx+4Fh+var_80], xmm0
0x140012c8c  add     ecx, 4
0x140012c8f  cmp     ecx, 40h ; '@'
0x140012c92  jb      short loc_140012C66
0x140012c94  xor     r10d, r10d
0x140012c97  test    esi, esi
0x140012c99  jz      short loc_140012D11
0x140012c9b  mov     eax, cs:QosgRandomValue
0x140012ca1  imul    r8, rax, 7FFFFFEDh
0x140012ca8  mov     rax, 200000005h
0x140012cb2  add     r8, 7FFFFFC3h
0x140012cb9  mul     r8
0x140012cbc  mov     rcx, r8
0x140012cbf  sub     rcx, rdx
0x140012cc2  shr     rcx, 1
0x140012cc5  add     rcx, rdx
0x140012cc8  xor     edx, edx
0x140012cca  shr     rcx, 1Eh
0x140012cce  imul    rcx, 7FFFFFFFh
0x140012cd5  sub     r8, rcx
0x140012cd8  mov     ecx, r14d
0x140012cdb  sub     ecx, r10d
0x140012cde  mov     cs:QosgRandomValue, r8d
0x140012ce5  mov     eax, r8d
0x140012ce8  div     ecx
0x140012cea  mov     al, byte ptr [rbp+r10+4Fh+var_80]
0x140012cef  add     edx, r10d
0x140012cf2  mov     r9d, edx
0x140012cf5  movzx   edx, byte ptr [rbp+rdx+4Fh+var_80]
0x140012cfa  mov     byte ptr [rbp+r10+4Fh+var_80], dl
0x140012cff  inc     r10d
0x140012d02  mov     byte ptr [rbp+r9+4Fh+var_80], al
0x140012d07  mov     byte ptr [rbp+rdx+4Fh+var_C0], 1
0x140012d0c  cmp     r10d, esi
0x140012d0f  jb      short loc_140012C9B
0x140012d11  lea     r9, [rbp+4Fh+var_C0]
0x140012d15  mov     [rsp+110h+var_E0], r15d
0x140012d1a  mov     r8d, esi
0x140012d1d  xor     edx, edx
0x140012d1f  xor     ecx, ecx
0x140012d21  call    QosSelectSlot
0x140012d26  mov     [rsp+110h+var_DC], eax
0x140012d2a  cmp     rbx, rdi
0x140012d2d  jz      short loc_140012D80
0x140012d2f  mov     r12, [rsp+110h+var_D0]
0x140012d34  lea     rsi, [rbx+18h]
0x140012d38  cmp     [rsi], r13
0x140012d3b  jnb     short loc_140012D80
0x140012d3d  mov     rax, [rbx-18h]
0x140012d41  lea     r9, [rbp+4Fh+var_C0]
0x140012d45  mov     rbx, [rbx]
0x140012d48  mov     r8d, r14d
0x140012d4b  mov     edx, r15d
0x140012d4e  mov     rcx, [rax+8]
0x140012d52  lea     rax, [rsp+110h+var_E0]
0x140012d57  mov     [rsp+110h+var_E8], rax
0x140012d5c  lea     rax, [rsp+110h+var_DC]
0x140012d61  mov     [rsp+110h+var_F0], rax
0x140012d66  mov     ecx, [rcx+18h]
0x140012d69  call    QosAssignSlot
0x140012d6e  imul    eax, [rsp+110h+var_D8]
0x140012d73  mov     ecx, eax
0x140012d75  add     rcx, r12
0x140012d78  mov     [rsi], rcx
0x140012d7b  cmp     rbx, rdi
0x140012d7e  jnz     short loc_140012D34
0x140012d80  mov     al, 1
0x140012d82  jmp     short loc_140012D86
0x140012d84  xor     al, al
0x140012d86  mov     rcx, [rbp+4Fh+var_40]
0x140012d8a  xor     rcx, rsp; StackCookie
0x140012d8d  call    __security_check_cookie
0x140012d92  mov     rbx, [rsp+110h+arg_18]
0x140012d9a  add     rsp, 0E0h
0x140012da1  pop     r15
0x140012da3  pop     r14
0x140012da5  pop     r13
0x140012da7  pop     r12
0x140012da9  pop     rdi
0x140012daa  pop     rsi
0x140012dab  pop     rbp
0x140012dac  retn
```
