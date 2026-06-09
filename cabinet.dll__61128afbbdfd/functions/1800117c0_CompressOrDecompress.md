# CompressOrDecompress

- ea: `0x1800117c0`
- end: `0x180011d66`
- name: `CompressOrDecompress`
- size: `1446`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011720`
- `0x180011790`

## callees

- `0x1800117c0`
- `0x180011d6c`
- `0x180011d9c`
- `0x180014dc0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bdb`
- `ntdll!RtlComputeCrc32` at `0x180011a9d`
- `ntdll!RtlComputeCrc32` at `0x180011ab3`
- `ntdll!RtlComputeCrc32` at `0x180011c23`
- `ntdll!RtlComputeCrc32` at `0x180011c35`
- `ntdll!RtlComputeCrc32` at `0x180011a9d`
- `ntdll!RtlComputeCrc32` at `0x180011ab3`
- `ntdll!RtlComputeCrc32` at `0x180011c23`
- `ntdll!RtlComputeCrc32` at `0x180011c35`

## pseudocode

```c
__int64 __fastcall CompressOrDecompress(
        __int64 a1,
        __m128i *a2,
        unsigned __int64 a3,
        char *a4,
        unsigned __int64 a5,
        unsigned __int64 *a6,
        unsigned int a7)
{
  int *v10; // rcx
  DWORD v11; // ebx
  unsigned __int64 v12; // rbx
  int v13; // ecx
  __int64 *v14; // rax
  __int64 v15; // r10
  __int64 (__fastcall *v16)(_QWORD, __int8 *, unsigned __int64, char *, unsigned __int64, unsigned __int64 *); // rax
  __int64 *v18; // rax
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // rcx
  __int64 v21; // r15
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // r10
  unsigned __int64 v25; // r8
  DWORD v26; // eax
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  __m128i v29; // xmm0
  __int64 v30; // xmm1_8
  int v31; // eax
  __int64 v32; // rbx
  ULONG v33; // eax
  unsigned int v34; // r9d
  unsigned __int64 v35; // rsi
  int v36; // r10d
  unsigned __int64 v37; // r15
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // r13
  unsigned __int64 v41; // r8
  DWORD v42; // eax
  ULONG v43; // eax
  UCHAR v44; // al
  __int64 v45; // xmm1_8
  char *v46; // rax
  unsigned __int64 v47; // rcx
  __int64 v48; // r8
  unsigned __int64 v49; // rdx
  unsigned __int64 v50; // r8
  unsigned __int64 v51; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int64 v52; // [rsp+48h] [rbp-59h]
  __int64 v53; // [rsp+50h] [rbp-51h]
  char *v54; // [rsp+58h] [rbp-49h]
  unsigned __int64 v55; // [rsp+60h] [rbp-41h]
  __int64 (__fastcall *v56)(_QWORD, __int8 *, unsigned __int64, char *, unsigned __int64, unsigned __int64 *); // [rsp+68h] [rbp-39h]
  __int64 v57; // [rsp+70h] [rbp-31h]
  UCHAR Buffer[16]; // [rsp+78h] [rbp-29h] BYREF
  __int64 v59; // [rsp+88h] [rbp-19h]

  v59 = 0;
  v54 = a4;
  *(_OWORD *)Buffer = 0;
  v57 = a1;
  v51 = 0;
  v11 = CmpsValidateHandle(a1, a7);
  if ( v11 )
    goto LABEL_62;
  if ( !a7 )
  {
    v12 = a5;
    if ( !a5 && (*v10 & 0x20000000) != 0 )
      goto LABEL_5;
LABEL_8:
    v13 = *v10;
    v14 = &qword_18001D140;
    if ( (v13 & 0x40000000) == 0 )
      v14 = &qword_18001D020;
    v15 = *(_QWORD *)(a1 + 8);
    v16 = (__int64 (__fastcall *)(_QWORD, __int8 *, unsigned __int64, char *, unsigned __int64, unsigned __int64 *))v14[6 * (v13 & 0x9FFFFFFF)];
    v56 = v16;
    if ( (v13 & 0x20000000) != 0 )
    {
      v11 = ((__int64 (__fastcall *)(__int64, __m128i *, unsigned __int64))v16)(v15, a2, a3);
      if ( a6 )
        *a6 = v51;
      if ( v11 )
        goto LABEL_62;
      return 1;
    }
    v18 = &qword_18001D148;
    if ( (v13 & 0x40000000) == 0 )
      v18 = &qword_18001D028;
    ((void (__fastcall *)(__int64))v18[6 * (v13 & 0x9FFFFFFF)])(v15);
    if ( a7 )
    {
      v19 = 0x4000000;
      if ( a3 < 0x4000000 )
        v19 = a3;
LABEL_20:
      v20 = a3 / v19 + 1;
      if ( !(a3 % v19) )
        v20 = a3 / v19;
      v21 = 0;
      v52 = v20;
      v22 = 0;
      v23 = 4 * v20 + 24;
      v55 = v23;
      while ( 1 )
      {
        v53 = v22;
        if ( v22 >= v20 )
          break;
        if ( v12 - v21 <= v23 )
          v24 = 0;
        else
          v24 = v12 - v21 - v23;
        v51 = 0;
        v25 = v19;
        if ( a3 - v22 * v19 < v19 )
          v25 = a3 - v22 * v19;
        v26 = v56(*(_QWORD *)(a1 + 8), &a2->m128i_i8[v22 * v19], v25, &v54[4 * v22 + 28 + v21], v24, &v51);
        v11 = v26;
        if ( v26 == 122 )
        {
          if ( a6 )
            *a6 = CmpsMaxCompressedSize(a1, a3);
          goto LABEL_62;
        }
        if ( v26 == 111 )
        {
          v19 = v51;
          v12 = a5;
          goto LABEL_20;
        }
        v27 = v51;
        v28 = v53;
        v12 = a5;
        *(_DWORD *)&v54[4 * v53 + 24 + v21] = v51;
        v21 += v27;
        v23 = v55;
        v22 = v28 + 1;
        v20 = v52;
      }
      Buffer[7] = *(_BYTE *)a1;
      *(_WORD *)&Buffer[4] = 24;
      Buffer[6] = 0;
      *(_DWORD *)Buffer = -1058713334;
      *(_QWORD *)&Buffer[8] = a3;
      v59 = (unsigned int)v19;
      v43 = RtlComputeCrc32(0, Buffer, 6u);
      v44 = RtlComputeCrc32(v43, &Buffer[7], 0x11u);
      v45 = v59;
      Buffer[6] = v44;
      v46 = v54;
      *(_OWORD *)v54 = *(_OWORD *)Buffer;
      *((_QWORD *)v46 + 2) = v45;
      if ( a6 )
        *a6 = v21 + 4 * (v52 + 6);
      return 1;
    }
    if ( !a3 )
    {
      if ( a6 )
        *a6 = CmpsMaxCompressedSize(a1, v12);
      v11 = 122;
      goto LABEL_62;
    }
    if ( a3 >= 0x1C )
    {
      v29 = *a2;
      v30 = a2[1].m128i_i64[0];
      v31 = _mm_cvtsi128_si32(*a2);
      *(__m128i *)Buffer = *a2;
      v59 = v30;
      if ( v31 == -1058713334 && v29.m128i_i16[2] >= 0x18u )
      {
        v32 = 4;
        v53 = 4;
        if ( a3 >= (unsigned __int64)v29.m128i_u16[2] + 4
          && (v30 & 0xFFFE00000000LL) == 0
          && v29.m128i_i8[7] == *(_BYTE *)a1
          && (unsigned int)v30 <= 0x4000000 )
        {
          v33 = RtlComputeCrc32(0, (PUCHAR)a2, 6u);
          if ( Buffer[6] == (unsigned __int8)RtlComputeCrc32(v33, &a2->m128i_u8[7], *(unsigned __int16 *)&Buffer[4] - 7) )
          {
            v34 = v59;
            if ( (v59 & 0x100000000LL) != 0 )
            {
              v47 = *(unsigned __int16 *)&Buffer[4];
              v35 = 0;
              v36 = 1;
              LODWORD(v52) = 1;
              while ( v47 + 8 <= a3 )
              {
                v48 = *(unsigned int *)((char *)&a2->m128i_u32[1] + v47);
                if ( !*(__int32 *)((char *)a2->m128i_i32 + v47) )
                {
                  if ( (_DWORD)v48 )
                    break;
                  v32 = 8;
                  goto LABEL_72;
                }
                if ( !(_DWORD)v48 )
                  break;
                v49 = v47 + *(unsigned int *)((char *)a2->m128i_u32 + v47);
                if ( v49 < v47 )
                  break;
                if ( v49 + 16 < v49 )
                  break;
                v50 = v35 + v48;
                if ( v50 < v35 )
                  break;
                v47 = v49 + 8;
                v35 = v50;
              }
            }
            else
            {
              v35 = *(unsigned int *)&Buffer[8] + ((unsigned __int64)*(unsigned int *)&Buffer[12] << 32);
              if ( v35 )
              {
                if ( (unsigned int)v59 >= 0x8000 )
                {
                  v36 = 0;
                  LODWORD(v52) = 0;
LABEL_72:
                  v53 = v32;
                  goto LABEL_46;
                }
                if ( v35 == (unsigned int)v59 )
                {
                  v36 = 0;
                  LODWORD(v52) = 0;
LABEL_46:
                  if ( a5 < v35 )
                  {
                    v11 = 122;
                    if ( a6 )
                    {
                      *a6 = -1;
                      if ( v35 != -1 )
                        *a6 = v35;
                    }
                    goto LABEL_62;
                  }
                  v37 = *(unsigned __int16 *)&Buffer[4];
                  v38 = 0;
                  while ( 1 )
                  {
                    v55 = v38;
                    if ( v38 >= v35 )
                      break;
                    v39 = v32 + v37;
                    if ( v32 + v37 > a3 || v39 < v37 || !*(__int32 *)((char *)a2->m128i_i32 + v37) )
                      goto LABEL_65;
                    if ( v36 )
                    {
                      v40 = *(unsigned int *)((char *)&a2->m128i_u32[1] + v37);
                    }
                    else
                    {
                      v40 = v34;
                      if ( v34 > v35 - v38 )
                        v40 = v35 - v38;
                    }
                    v41 = *(unsigned int *)((char *)a2->m128i_u32 + v37);
                    v37 = v41 + v39;
                    if ( v41 + v39 < v39 || v37 > a3 )
                      goto LABEL_65;
                    v42 = v56(*(_QWORD *)(v57 + 8), &a2->m128i_i8[v39], v41, &v54[v38], v40, &v51);
                    v11 = v42;
                    if ( v42 == 605 )
                      goto LABEL_62;
                    if ( v42 == 111 )
                      goto LABEL_65;
                    v34 = v59;
                    v38 = v40 + v55;
                    v32 = v53;
                    v36 = v52;
                  }
                  if ( a6 )
                    *a6 = v35;
                  return 1;
                }
              }
            }
          }
        }
      }
    }
LABEL_65:
    v11 = 605;
    goto LABEL_62;
  }
  if ( a3 )
  {
    v12 = a5;
    goto LABEL_8;
  }
LABEL_5:
  v11 = 87;
LABEL_62:
  SetLastError(v11);
  return 0;
}

```

## disassembly

```asm
0x1800117c0  push    rbp
0x1800117c2  push    rbx
0x1800117c3  push    rsi
0x1800117c4  push    rdi
0x1800117c5  push    r12
0x1800117c7  push    r13
0x1800117c9  push    r14
0x1800117cb  push    r15
0x1800117cd  lea     rbp, [rsp-7]
0x1800117d2  sub     rsp, 0A8h
0x1800117d9  mov     rax, cs:__security_cookie
0x1800117e0  xor     rax, rsp
0x1800117e3  mov     [rbp+3Fh+var_50], rax
0x1800117e7  mov     esi, [rbp+3Fh+arg_30]
0x1800117ea  xor     eax, eax
0x1800117ec  mov     rdi, [rbp+3Fh+arg_28]
0x1800117f0  mov     r12, rdx
0x1800117f3  xorps   xmm0, xmm0
0x1800117f6  mov     [rbp+3Fh+var_58], rax
0x1800117fa  mov     edx, esi
0x1800117fc  mov     [rbp+3Fh+var_88], r9
0x180011800  movups  xmmword ptr [rbp+3Fh+Buffer], xmm0
0x180011804  mov     r14, r8
0x180011807  mov     [rbp+3Fh+var_70], rcx
0x18001180b  mov     r13, rcx
0x18001180e  mov     [rbp+3Fh+var_A0], 0
0x180011816  call    CmpsValidateHandle
0x18001181b  mov     ebx, eax
0x18001181d  test    eax, eax
0x18001181f  jnz     loc_180011BD9
0x180011825  mov     r11d, 20000000h
0x18001182b  test    esi, esi
0x18001182d  jnz     short loc_180011847
0x18001182f  mov     rbx, [rbp+3Fh+arg_20]
0x180011833  test    rbx, rbx
0x180011836  jnz     short loc_180011850
0x180011838  test    [rcx], r11d
0x18001183b  jz      short loc_180011850
0x18001183d  mov     ebx, 57h ; 'W'
0x180011842  jmp     loc_180011BD9
0x180011847  test    r14, r14
0x18001184a  jz      short loc_18001183D
0x18001184c  mov     rbx, [rbp+3Fh+arg_20]
0x180011850  mov     ecx, [rcx]
0x180011852  lea     r10, qword_18001D020
0x180011859  mov     edx, 9FFFFFFFh
0x18001185e  mov     eax, ecx
0x180011860  and     rax, rdx
0x180011863  mov     r8d, ecx
0x180011866  lea     rdx, [rax+rax*2]
0x18001186a  add     rdx, rdx
0x18001186d  lea     rax, qword_18001D140
0x180011874  and     r8d, 40000000h
0x18001187b  cmovz   rax, r10
0x18001187f  mov     r10, [r13+8]
0x180011883  mov     rax, [rax+rdx*8]
0x180011887  mov     [rbp+3Fh+var_78], rax
0x18001188b  test    r11d, ecx
0x18001188e  jz      short loc_1800118E7
0x180011890  lea     rcx, [rbp+3Fh+var_A0]
0x180011894  mov     r8, r14
0x180011897  mov     [rsp+0E0h+var_B8], rcx
0x18001189c  mov     rdx, r12
0x18001189f  mov     rcx, r10
0x1800118a2  mov     [rsp+0E0h+var_C0], rbx
0x1800118a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ac  mov     ebx, eax
0x1800118ae  test    rdi, rdi
0x1800118b1  jz      short loc_1800118BA
0x1800118b3  mov     rax, [rbp+3Fh+var_A0]
0x1800118b7  mov     [rdi], rax
0x1800118ba  test    ebx, ebx
0x1800118bc  jnz     loc_180011BD9
0x1800118c2  mov     eax, 1
0x1800118c7  mov     rcx, [rbp+3Fh+var_50]
0x1800118cb  xor     rcx, rsp; StackCookie
0x1800118ce  call    __security_check_cookie
0x1800118d3  add     rsp, 0A8h
0x1800118da  pop     r15
0x1800118dc  pop     r14
0x1800118de  pop     r13
0x1800118e0  pop     r12
0x1800118e2  pop     rdi
0x1800118e3  pop     rsi
0x1800118e4  pop     rbx
0x1800118e5  pop     rbp
0x1800118e6  retn
0x1800118e7  test    r8d, r8d
0x1800118ea  lea     rcx, qword_18001D028
0x1800118f1  lea     rax, qword_18001D148
0x1800118f8  cmovz   rax, rcx
0x1800118fc  mov     rcx, r10
0x1800118ff  mov     rax, [rax+rdx*8]
0x180011903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011908  test    esi, esi
0x18001190a  jz      loc_1800119F8
0x180011910  mov     esi, 4000000h
0x180011915  cmp     r14, rsi
0x180011918  cmovb   rsi, r14
0x18001191c  xor     edx, edx
0x18001191e  mov     rax, r14
0x180011921  div     rsi
0x180011924  test    rdx, rdx
0x180011927  lea     rcx, [rax+1]
0x18001192b  cmovz   rcx, rax
0x18001192f  xor     r15d, r15d
0x180011932  mov     [rbp+3Fh+var_98], rcx
0x180011936  xor     edx, edx
0x180011938  lea     rax, ds:18h[rcx*4]
0x180011940  mov     [rbp+3Fh+var_80], rax
0x180011944  mov     [rbp+3Fh+var_90], rdx
0x180011948  cmp     rdx, rcx
0x18001194b  jnb     loc_180011BE8
0x180011951  mov     r10, rbx
0x180011954  sub     r10, r15
0x180011957  cmp     r10, rax
0x18001195a  jbe     loc_1800119F0
0x180011960  sub     r10, rax
0x180011963  mov     rcx, rsi
0x180011966  mov     [rbp+3Fh+var_A0], 0
0x18001196e  imul    rcx, rdx
0x180011972  mov     rax, r14
0x180011975  mov     r8, rsi
0x180011978  sub     rax, rcx
0x18001197b  cmp     rax, rsi
0x18001197e  cmovb   r8, rax
0x180011982  mov     rax, [rbp+3Fh+var_88]
0x180011986  add     rax, 1Ch
0x18001198a  lea     r9, [rax+rdx*4]
0x18001198e  lea     rax, [rbp+3Fh+var_A0]
0x180011992  add     r9, r15
0x180011995  mov     [rsp+0E0h+var_B8], rax
0x18001199a  lea     rdx, [rcx+r12]
0x18001199e  mov     rax, [rbp+3Fh+var_78]
0x1800119a2  mov     rcx, [r13+8]
0x1800119a6  mov     [rsp+0E0h+var_C0], r10
0x1800119ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b0  mov     ebx, eax
0x1800119b2  cmp     eax, 7Ah ; 'z'
0x1800119b5  jz      loc_180011BC6
0x1800119bb  cmp     eax, 6Fh ; 'o'
0x1800119be  jz      loc_180011CC2
0x1800119c4  mov     rcx, [rbp+3Fh+var_A0]
0x1800119c8  mov     rdx, [rbp+3Fh+var_90]
0x1800119cc  mov     rax, [rbp+3Fh+var_88]
0x1800119d0  mov     rbx, [rbp+3Fh+arg_20]
0x1800119d4  lea     rax, [rax+rdx*4]
0x1800119d8  mov     [rax+r15+18h], ecx
0x1800119dd  add     r15, rcx
0x1800119e0  mov     rax, [rbp+3Fh+var_80]
0x1800119e4  inc     rdx
0x1800119e7  mov     rcx, [rbp+3Fh+var_98]
0x1800119eb  jmp     loc_180011944
0x1800119f0  xor     r10d, r10d
0x1800119f3  jmp     loc_180011963
0x1800119f8  test    r14, r14
0x1800119fb  jz      loc_180011D37
0x180011a01  cmp     r14, 1Ch
0x180011a05  jb      loc_180011C70
0x180011a0b  movups  xmm0, xmmword ptr [r12]
0x180011a10  movsd   xmm1, qword ptr [r12+10h]
0x180011a17  movd    eax, xmm0
0x180011a1b  movups  xmmword ptr [rbp+3Fh+Buffer], xmm0
0x180011a1f  movsd   [rbp+3Fh+var_58], xmm1
0x180011a24  cmp     eax, 0C0E5510Ah
0x180011a29  jnz     loc_180011C70
0x180011a2f  movq    rcx, xmm0
0x180011a34  mov     edx, 18h
0x180011a39  mov     rax, rcx
0x180011a3c  shr     rax, 20h
0x180011a40  cmp     ax, dx
0x180011a43  jb      loc_180011C70
0x180011a49  lea     ebx, [rdx-14h]
0x180011a4c  movzx   eax, ax
0x180011a4f  add     rax, rbx
0x180011a52  mov     [rbp+3Fh+var_90], rbx
0x180011a56  cmp     r14, rax
0x180011a59  jb      loc_180011C70
0x180011a5f  movq    rdx, xmm1
0x180011a64  mov     rax, rdx
0x180011a67  shr     rax, 20h
0x180011a6b  movzx   eax, ax
0x180011a6e  test    eax, 0FFFFFFFEh
0x180011a73  jnz     loc_180011C70
0x180011a79  shr     rcx, 38h
0x180011a7d  cmp     cl, [r13+0]
0x180011a81  jnz     loc_180011C70
0x180011a87  mov     esi, 4000000h
0x180011a8c  cmp     edx, esi
0x180011a8e  ja      loc_180011C70
0x180011a94  lea     r8d, [rbx+2]; Length
0x180011a98  mov     rdx, r12; Buffer
0x180011a9b  xor     ecx, ecx; InitialCrc
0x180011a9d  call    cs:__imp_RtlComputeCrc32
0x180011aa3  movzx   r8d, word ptr [rbp+3Fh+Buffer+4]
0x180011aa8  lea     rdx, [r12+7]; Buffer
0x180011aad  sub     r8d, 7; Length
0x180011ab1  mov     ecx, eax; InitialCrc
0x180011ab3  call    cs:__imp_RtlComputeCrc32
0x180011ab9  cmp     [rbp+3Fh+Buffer+6], al
0x180011abc  jnz     loc_180011C70
0x180011ac2  test    byte ptr [rbp+3Fh+var_58+4], 1
0x180011ac6  mov     r9d, dword ptr [rbp+3Fh+var_58]
0x180011aca  jnz     loc_180011CD9
0x180011ad0  mov     esi, dword ptr [rbp+3Fh+Buffer+0Ch]
0x180011ad3  mov     eax, dword ptr [rbp+3Fh+Buffer+8]
0x180011ad6  shl     rsi, 20h
0x180011ada  add     rsi, rax
0x180011add  jz      loc_180011C70
0x180011ae3  cmp     r9d, 8000h
0x180011aea  jnb     loc_180011CB2
0x180011af0  cmp     rsi, r9
0x180011af3  jnz     loc_180011C70
0x180011af9  xor     r10d, r10d
0x180011afc  mov     dword ptr [rbp+3Fh+var_98], r10d
0x180011b00  cmp     [rbp+3Fh+arg_20], rsi
0x180011b04  jb      loc_180011C7A
0x180011b0a  movzx   r15d, word ptr [rbp+3Fh+Buffer+4]
0x180011b0f  xor     edx, edx
0x180011b11  mov     [rbp+3Fh+var_80], rdx
0x180011b15  cmp     rdx, rsi
0x180011b18  jnb     loc_180011CA1
0x180011b1e  lea     rcx, [rbx+r15]
0x180011b22  cmp     rcx, r14
0x180011b25  ja      loc_180011C70
0x180011b2b  cmp     rcx, r15
0x180011b2e  jb      loc_180011C70
0x180011b34  cmp     dword ptr [r12+r15], 0
0x180011b39  jz      loc_180011C70
0x180011b3f  test    r10d, r10d
0x180011b42  jnz     loc_180011CCF
0x180011b48  mov     r13d, r9d
0x180011b4b  mov     rax, rsi
0x180011b4e  sub     rax, rdx
0x180011b51  cmp     r13, rax
0x180011b54  cmova   r13, rax
0x180011b58  mov     r8d, [r12+r15]
0x180011b5c  lea     r15, [r8+rcx]
0x180011b60  cmp     r15, rcx
0x180011b63  jb      loc_180011C70
0x180011b69  cmp     r15, r14
0x180011b6c  ja      loc_180011C70
0x180011b72  mov     r9, [rbp+3Fh+var_88]
0x180011b76  lea     rax, [rbp+3Fh+var_A0]
0x180011b7a  mov     [rsp+0E0h+var_B8], rax
0x180011b7f  add     r9, rdx
0x180011b82  mov     rax, [rbp+3Fh+var_70]
0x180011b86  lea     rdx, [r12+rcx]
0x180011b8a  mov     [rsp+0E0h+var_C0], r13
0x180011b8f  mov     rcx, [rax+8]
0x180011b93  mov     rax, [rbp+3Fh+var_78]
0x180011b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b9c  mov     ebx, eax
0x180011b9e  cmp     eax, 25Dh
0x180011ba3  jz      short loc_180011BD9
0x180011ba5  cmp     eax, 6Fh ; 'o'
0x180011ba8  jz      loc_180011C70
0x180011bae  mov     rdx, [rbp+3Fh+var_80]
0x180011bb2  mov     r9d, dword ptr [rbp+3Fh+var_58]
0x180011bb6  add     rdx, r13
0x180011bb9  mov     rbx, [rbp+3Fh+var_90]
0x180011bbd  mov     r10d, dword ptr [rbp+3Fh+var_98]
0x180011bc1  jmp     loc_180011B11
0x180011bc6  test    rdi, rdi
0x180011bc9  jz      short loc_180011BD9
0x180011bcb  mov     rdx, r14
0x180011bce  mov     rcx, r13
0x180011bd1  call    CmpsMaxCompressedSize
0x180011bd6  mov     [rdi], rax
0x180011bd9  mov     ecx, ebx; dwErrCode
0x180011bdb  call    cs:__imp_SetLastError
0x180011be1  xor     eax, eax
0x180011be3  jmp     loc_1800118C7
0x180011be8  mov     al, [r13+0]
0x180011bec  mov     edx, 18h
0x180011bf1  mov     [rbp+3Fh+Buffer+7], al
0x180011bf4  xor     ecx, ecx; InitialCrc
0x180011bf6  mov     word ptr [rbp+3Fh+Buffer+4], dx
0x180011bfa  mov     rax, r14
0x180011bfd  shr     rax, 20h
0x180011c01  mov     dword ptr [rbp+3Fh+Buffer+0Ch], eax
0x180011c04  lea     r8d, [rdx-12h]; Length
0x180011c08  xor     eax, eax
0x180011c0a  mov     [rbp+3Fh+Buffer+6], 0
0x180011c0e  lea     rdx, [rbp+3Fh+Buffer]; Buffer
0x180011c12  mov     dword ptr [rbp+3Fh+var_58+4], eax
0x180011c15  mov     dword ptr [rbp+3Fh+Buffer], 0C0E5510Ah
0x180011c1c  mov     dword ptr [rbp+3Fh+Buffer+8], r14d
0x180011c20  mov     dword ptr [rbp+3Fh+var_58], esi
0x180011c23  call    cs:__imp_RtlComputeCrc32
0x180011c29  mov     r8d, 11h; Length
0x180011c2f  lea     rdx, [rbp+3Fh+Buffer+7]; Buffer
0x180011c33  mov     ecx, eax; InitialCrc
0x180011c35  call    cs:__imp_RtlComputeCrc32
0x180011c3b  movsd   xmm1, [rbp+3Fh+var_58]
0x180011c40  mov     [rbp+3Fh+Buffer+6], al
0x180011c43  mov     rax, [rbp+3Fh+var_88]
0x180011c47  movups  xmm0, xmmword ptr [rbp+3Fh+Buffer]
0x180011c4b  movups  xmmword ptr [rax], xmm0
0x180011c4e  movsd   qword ptr [rax+10h], xmm1
  ... truncated ...
```
