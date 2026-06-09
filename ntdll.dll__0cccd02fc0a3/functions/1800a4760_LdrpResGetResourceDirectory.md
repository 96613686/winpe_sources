# LdrpResGetResourceDirectory

- ea: `0x1800a4760`
- end: `0x1800a4cea`
- name: `LdrpResGetResourceDirectory`
- size: `1418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800a2b20`

## callees

- `0x18001f070`
- `0x1800526f0`
- `0x1800a4760`
- `0x1800a5b48`
- `0x18016f030`

## string_xrefs

- `0x1800a47c9`: `LdrpResGetResourceDirectory Exit`
- `0x1800a47b4`: `LdrpResGetResourceDirectory Enter`

## pseudocode

```c
__int64 __fastcall LdrpResGetResourceDirectory(
        unsigned __int64 a1,
        __int64 a2,
        __int16 a3,
        unsigned __int64 *a4,
        _QWORD *a5)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  char v12; // r13
  _DWORD *SharedData; // rcx
  __int64 v14; // rsi
  __int64 v15; // rcx
  _QWORD *v16; // r12
  char v17; // al
  char v18; // r14
  int v19; // edi
  __int64 result; // rax
  unsigned __int64 v21; // rdx
  unsigned int *v22; // r8
  __int64 v23; // r9
  __int16 v24; // ax
  __m128i v25; // xmm2
  __m128i v26; // xmm4
  __m128i v27; // xmm3
  __m128i v28; // xmm5
  unsigned int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rdi
  __int64 v32; // r10
  unsigned int v33; // r11d
  int i; // ecx
  int v35; // eax
  int v36; // ecx
  _DWORD *v37; // rcx
  __int64 v38; // rcx
  _QWORD v39[2]; // [rsp+40h] [rbp-138h] BYREF
  _QWORD v40[2]; // [rsp+50h] [rbp-128h] BYREF
  __int128 v41; // [rsp+60h] [rbp-118h] BYREF
  __int128 v42; // [rsp+70h] [rbp-108h]
  __int128 v43; // [rsp+80h] [rbp-F8h]
  __m128i v44; // [rsp+90h] [rbp-E8h]
  __int128 v45; // [rsp+A0h] [rbp-D8h]
  __m128i v46; // [rsp+B0h] [rbp-C8h]
  __m128i v47; // [rsp+C0h] [rbp-B8h]
  __m128i v48; // [rsp+D0h] [rbp-A8h]
  __m128i v49; // [rsp+E0h] [rbp-98h]
  __int128 v50; // [rsp+F0h] [rbp-88h]
  __int128 v51; // [rsp+100h] [rbp-78h]
  __int128 v52; // [rsp+110h] [rbp-68h]
  __int128 v53; // [rsp+120h] [rbp-58h]
  __int128 v54; // [rsp+130h] [rbp-48h]
  __int128 v55; // [rsp+140h] [rbp-38h]
  __int64 v56; // [rsp+180h] [rbp+8h] BYREF
  unsigned __int64 *v57; // [rsp+198h] [rbp+20h]

  v57 = a4;
  v56 = 0;
  memset_thunk_772440563353939046(&v41, 0, 0xF0u);
  v12 = 1;
  v39[0] = 4456514;
  v39[1] = L"LdrpResGetResourceDirectory Enter";
  v40[0] = 4325440;
  v40[1] = L"LdrpResGetResourceDirectory Exit";
  SharedData = NtCurrentPeb()->SharedData;
  if ( SharedData && *SharedData )
  {
    v15 = (__int64)NtCurrentPeb()->SharedData + 555;
    v14 = 2147353477;
  }
  else
  {
    v14 = 2147353477;
    v15 = 2147353477;
  }
  if ( (*(_BYTE *)v15 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v15, v9, v10, v11) )
      v38 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v38 = 2147353476;
    LdrpTraceLoadMUIDll(v39, *(unsigned __int8 *)v38);
  }
  if ( !a1 )
    return 3221225485LL;
  if ( !a4 )
    return 3221225485LL;
  v16 = a5;
  if ( !a5 )
    return 3221225485LL;
  v17 = a1 & 1;
  if ( (a1 & 2) != 0 || (v18 = 1, (a1 & 1) != 0) )
  {
    a1 &= 0xFFFFFFFFFFFFFFFCuLL;
    v18 = v17 ^ 1;
  }
  v19 = a3 & 0x1000;
  result = RtlImageNtHeaderEx(v19 == 0, a1, a2, &v56);
  if ( (int)result >= 0 )
  {
    v23 = v56;
    v24 = *(_WORD *)(v56 + 24);
    if ( v24 == 267 )
    {
      v41 = *(_OWORD *)(v56 + 24);
      v42 = *(_OWORD *)(v56 + 40);
      v43 = *(_OWORD *)(v56 + 56);
      v45 = *(_OWORD *)(v56 + 88);
      v25 = *(__m128i *)(v56 + 104);
      v46 = v25;
      v47 = *(__m128i *)(v56 + 120);
      v51 = *(_OWORD *)(v56 + 184);
      v53 = *(_OWORD *)(v56 + 216);
    }
    else
    {
      if ( v24 != 523 )
      {
        v30 = -1073741701;
        v31 = 2147353476;
        goto LABEL_47;
      }
      v41 = *(_OWORD *)(v56 + 24);
      v42 = *(_OWORD *)(v56 + 40);
      v43 = *(_OWORD *)(v56 + 56);
      v45 = *(_OWORD *)(v56 + 88);
      v46 = *(__m128i *)(v56 + 104);
      v25 = *(__m128i *)(v56 + 120);
      v47 = v25;
      v51 = *(_OWORD *)(v56 + 184);
      v53 = *(_OWORD *)(v56 + 216);
      v55 = *(_OWORD *)(v56 + 248);
      v12 = 0;
    }
    v50 = *(_OWORD *)(v56 + 168);
    v52 = *(_OWORD *)(v56 + 200);
    v26 = *(__m128i *)(v56 + 152);
    v27 = *(__m128i *)(v56 + 136);
    v28 = *(__m128i *)(v56 + 72);
    v54 = *(_OWORD *)(v56 + 232);
    v49 = v26;
    v48 = v27;
    v44 = v28;
    if ( (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(v25, 12)) <= 2 )
    {
      v30 = -1073741687;
      v31 = 2147353476;
      goto LABEL_47;
    }
    v21 = (unsigned int)_mm_cvtsi128_si32(v26);
    v29 = _mm_cvtsi128_si32(v27);
    if ( v12 )
      v21 = v29;
    if ( !(_DWORD)v21 )
    {
      v30 = -1073741687;
      v31 = 2147353476;
      goto LABEL_47;
    }
    if ( !v18 && (unsigned int)v21 >= _mm_cvtsi128_si32(_mm_srli_si128(v28, 12)) )
    {
      LODWORD(v56) = v19 != 0;
      v22 = (unsigned int *)(v23 + *(unsigned __int16 *)(v23 + 20) + 24LL);
      if ( v22 )
      {
        for ( i = 0;
              i < *(unsigned __int16 *)(v23 + 6)
           && (!v19 || (unsigned __int64)(v22 + 10) <= a2 + (a1 & 0xFFFFFFFFFFFFFFFCuLL));
              ++i )
        {
          v32 = v22[3];
          if ( (unsigned int)v21 >= (unsigned int)v32 )
          {
            v33 = v22[4];
            if ( (unsigned int)v21 < (unsigned int)v32 + v33 )
            {
              if ( v33 )
              {
                v21 += a1 + v22[5] - v32;
                goto LABEL_39;
              }
              v30 = -1073741687;
              v31 = 2147353476;
              goto LABEL_47;
            }
          }
          v22 += 10;
        }
      }
      v30 = -1073741701;
      v31 = 2147353476;
      goto LABEL_47;
    }
    v21 += a1;
    if ( v21 < a1 )
    {
      v30 = -1073741701;
      v31 = 2147353476;
      goto LABEL_47;
    }
LABEL_39:
    if ( !v21 )
    {
      v30 = -1073741687;
      goto LABEL_46;
    }
    if ( !v19 )
      goto LABEL_45;
    if ( v21 > a1 )
    {
      v22 = (unsigned int *)((a1 & 0xFFFFFFFFFFFFFFFCuLL) + a2);
      if ( v21 + 16 <= (unsigned __int64)v22 )
      {
        v35 = *(unsigned __int16 *)(v21 + 12);
        v36 = *(unsigned __int16 *)(v21 + 14);
        if ( !__PAIR32__(v36, v35) )
        {
          v30 = -1073741686;
          goto LABEL_46;
        }
        if ( v21 + 8LL * (unsigned int)(v35 + v36) <= (unsigned __int64)v22 )
        {
LABEL_45:
          *v57 = v21;
          *v16 = v23;
          v30 = 0;
LABEL_46:
          v31 = 2147353476;
LABEL_47:
          v37 = NtCurrentPeb()->SharedData;
          if ( v37 && *v37 )
            v14 = (__int64)NtCurrentPeb()->SharedData + 555;
          if ( (*(_BYTE *)v14 & 1) != 0 )
          {
            if ( (unsigned int)RtlGetCurrentServiceSessionId(v37, v21, v22, v23) )
              v31 = (__int64)NtCurrentPeb()->SharedData + 554;
            LdrpTraceLoadMUIDll(v40, *(unsigned __int8 *)v31);
          }
          return v30;
        }
      }
    }
    v30 = -1073741701;
    goto LABEL_46;
  }
  return result;
}

```

## disassembly

```asm
0x1800a4760  mov     r11, rsp
0x1800a4763  mov     [r11+10h], rbx
0x1800a4767  mov     [r11+18h], rsi
0x1800a476b  mov     [r11+20h], r9
0x1800a476f  push    rdi
0x1800a4770  push    r12
0x1800a4772  push    r13
0x1800a4774  push    r14
0x1800a4776  push    r15
0x1800a4778  sub     rsp, 150h
0x1800a477f  mov     r14, r9
0x1800a4782  mov     edi, r8d
0x1800a4785  mov     r15, rdx
0x1800a4788  mov     rbx, rcx
0x1800a478b  xor     eax, eax
0x1800a478d  mov     [rsp+178h+var_140], rax
0x1800a4792  mov     [r11+8], rax
0x1800a4796  xor     edx, edx; Val
0x1800a4798  mov     r8d, 0F0h; Size
0x1800a479e  lea     rcx, [rsp+178h+var_118]; void *
0x1800a47a3  call    memset$thunk$772440563353939046
0x1800a47a8  mov     r13b, 1
0x1800a47ab  mov     [rsp+178h+var_138], 440042h
0x1800a47b4  lea     rax, aLdrpresgetreso_0; "LdrpResGetResourceDirectory Enter"
0x1800a47bb  mov     [rsp+178h+var_130], rax
0x1800a47c0  mov     [rsp+178h+var_128], 420040h
0x1800a47c9  lea     rax, aLdrpresgetreso_1; "LdrpResGetResourceDirectory Exit"
0x1800a47d0  mov     [rsp+178h+var_120], rax
0x1800a47d5  mov     rax, gs:60h
0x1800a47de  mov     rcx, [rax+90h]
0x1800a47e5  test    rcx, rcx
0x1800a47e8  jnz     loc_1800A4C20
0x1800a47ee  mov     esi, 7FFE0385h
0x1800a47f3  mov     ecx, esi
0x1800a47f5  test    [rcx], r13b
0x1800a47f8  jnz     loc_1800A4C75
0x1800a47fe  test    rbx, rbx
0x1800a4801  jz      loc_1800A4C6B
0x1800a4807  test    r14, r14
0x1800a480a  jz      loc_1800A4C6B
0x1800a4810  mov     r12, [rsp+178h+arg_20]
0x1800a4818  test    r12, r12
0x1800a481b  jz      loc_1800A4C6B
0x1800a4821  mov     rax, rbx
0x1800a4824  and     eax, 1
0x1800a4827  test    bl, 2
0x1800a482a  jnz     loc_1800A4C09
0x1800a4830  movzx   r14d, r13b
0x1800a4834  test    rax, rax
0x1800a4837  jnz     loc_1800A4C09
0x1800a483d  and     edi, 1000h
0x1800a4843  mov     ecx, 0
0x1800a4848  setz    cl
0x1800a484b  lea     r9, [rsp+178h+arg_0]
0x1800a4853  mov     r8, r15
0x1800a4856  mov     rdx, rbx
0x1800a4859  call    RtlImageNtHeaderEx
0x1800a485e  test    eax, eax
0x1800a4860  js      loc_1800A4BDF
0x1800a4866  mov     r9, [rsp+178h+arg_0]
0x1800a486e  movzx   eax, word ptr [r9+18h]
0x1800a4873  mov     ecx, 10Bh
0x1800a4878  cmp     ax, cx
0x1800a487b  jnz     loc_1800A4A99
0x1800a4881  movups  xmm0, xmmword ptr [r9+18h]
0x1800a4886  movups  [rsp+178h+var_118], xmm0
0x1800a488b  movups  xmm1, xmmword ptr [r9+28h]
0x1800a4890  movups  [rsp+178h+var_108], xmm1
0x1800a4895  movups  xmm0, xmmword ptr [r9+38h]
0x1800a489a  movups  [rsp+178h+var_F8], xmm0
0x1800a48a2  movups  xmm0, xmmword ptr [r9+58h]
0x1800a48a7  movups  [rsp+178h+var_D8], xmm0
0x1800a48af  movups  xmm2, xmmword ptr [r9+68h]
0x1800a48b4  movaps  [rsp+178h+var_C8], xmm2
0x1800a48bc  movups  xmm0, xmmword ptr [r9+78h]
0x1800a48c1  movups  [rsp+178h+var_B8], xmm0
0x1800a48c9  movups  xmm1, xmmword ptr [r9+0B8h]
0x1800a48d1  movups  [rsp+178h+var_78], xmm1
0x1800a48d9  movups  xmm1, xmmword ptr [r9+0D8h]
0x1800a48e1  movups  [rsp+178h+var_58], xmm1
0x1800a48e9  movups  xmm0, xmmword ptr [r9+0A8h]
0x1800a48f1  movups  [rsp+178h+var_88], xmm0
0x1800a48f9  movups  xmm0, xmmword ptr [r9+0C8h]
0x1800a4901  movups  [rsp+178h+var_68], xmm0
0x1800a4909  psrldq  xmm2, 0Ch
0x1800a490e  movups  xmm0, xmmword ptr [r9+0E8h]
0x1800a4916  movups  xmm4, xmmword ptr [r9+98h]
0x1800a491e  movups  xmm3, xmmword ptr [r9+88h]
0x1800a4926  movups  xmm5, xmmword ptr [r9+48h]
0x1800a492b  movd    eax, xmm2
0x1800a492f  movups  [rsp+178h+var_48], xmm0
0x1800a4937  movaps  [rsp+178h+var_98], xmm4
0x1800a493f  movaps  [rsp+178h+var_A8], xmm3
0x1800a4947  movaps  [rsp+178h+var_E8], xmm5
0x1800a494f  cmp     eax, 2
0x1800a4952  jbe     loc_1800A4A73
0x1800a4958  movd    edx, xmm4
0x1800a495c  movd    eax, xmm3
0x1800a4960  test    r13b, r13b
0x1800a4963  cmovnz  edx, eax
0x1800a4966  test    edx, edx
0x1800a4968  jz      loc_1800A4A4D
0x1800a496e  test    r14b, r14b
0x1800a4971  jz      short loc_1800A49DE
0x1800a4973  add     rdx, rbx
0x1800a4976  cmp     rdx, rbx
0x1800a4979  jnb     short loc_1800A49D4
0x1800a497b  mov     ebx, 0C000007Bh
0x1800a4980  mov     [rsp+178h+var_158], ebx
0x1800a4984  mov     edi, 7FFE0384h
0x1800a4989  jmp     loc_1800A4BBF
0x1800a498e  mov     rax, rbx
0x1800a4991  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800a4995  add     rax, r15
0x1800a4998  cmp     r14, rax
0x1800a499b  ja      loc_1800A4A60
0x1800a49a1  mov     r10d, [r8+0Ch]
0x1800a49a5  cmp     edx, r10d
0x1800a49a8  jb      loc_1800A4A41
0x1800a49ae  mov     r11d, [r8+10h]
0x1800a49b2  lea     eax, [r10+r11]
0x1800a49b6  cmp     edx, eax
0x1800a49b8  jnb     loc_1800A4A41
0x1800a49be  test    r11d, r11d
0x1800a49c1  jz      loc_1800A4A86
0x1800a49c7  mov     eax, [r8+14h]
0x1800a49cb  sub     rax, r10
0x1800a49ce  add     rax, rbx
0x1800a49d1  add     rdx, rax
0x1800a49d4  mov     [rsp+178h+var_140], rdx
0x1800a49d9  jmp     loc_1800A4B4C
0x1800a49de  psrldq  xmm5, 0Ch
0x1800a49e3  movd    eax, xmm5
0x1800a49e7  cmp     edx, eax
0x1800a49e9  jb      short loc_1800A4973
0x1800a49eb  xor     r13d, r13d
0x1800a49ee  test    edi, edi
0x1800a49f0  setnz   r13b
0x1800a49f4  mov     dword ptr [rsp+178h+arg_0], r13d
0x1800a49fc  mov     [rsp+178h+var_154], 0
0x1800a4a04  mov     [rsp+178h+var_148], 0
0x1800a4a0d  movzx   r8d, word ptr [r9+14h]
0x1800a4a12  add     r8, 18h
0x1800a4a16  add     r8, r9
0x1800a4a19  mov     [rsp+178h+var_148], r8
0x1800a4a1e  jz      short loc_1800A4A60
0x1800a4a20  xor     ecx, ecx
0x1800a4a22  mov     [rsp+178h+var_154], ecx
0x1800a4a26  movzx   eax, word ptr [r9+6]
0x1800a4a2b  cmp     ecx, eax
0x1800a4a2d  jge     short loc_1800A4A60
0x1800a4a2f  lea     r14, [r8+28h]
0x1800a4a33  test    r13b, r13b
0x1800a4a36  jnz     loc_1800A498E
0x1800a4a3c  jmp     loc_1800A49A1
0x1800a4a41  mov     r8, r14
0x1800a4a44  mov     [rsp+178h+var_148], r14
0x1800a4a49  inc     ecx
0x1800a4a4b  jmp     short loc_1800A4A22
0x1800a4a4d  mov     ebx, 0C0000089h
0x1800a4a52  mov     [rsp+178h+var_158], ebx
0x1800a4a56  mov     edi, 7FFE0384h
0x1800a4a5b  jmp     loc_1800A4BBF
0x1800a4a60  mov     ebx, 0C000007Bh
0x1800a4a65  mov     [rsp+178h+var_158], ebx
0x1800a4a69  mov     edi, 7FFE0384h
0x1800a4a6e  jmp     loc_1800A4BBF
0x1800a4a73  mov     ebx, 0C0000089h
0x1800a4a78  mov     [rsp+178h+var_158], ebx
0x1800a4a7c  mov     edi, 7FFE0384h
0x1800a4a81  jmp     loc_1800A4BBF
0x1800a4a86  mov     ebx, 0C0000089h
0x1800a4a8b  mov     [rsp+178h+var_158], ebx
0x1800a4a8f  mov     edi, 7FFE0384h
0x1800a4a94  jmp     loc_1800A4BBF
0x1800a4a99  mov     ecx, 20Bh
0x1800a4a9e  cmp     ax, cx
0x1800a4aa1  jnz     loc_1800A4B27
0x1800a4aa7  movups  xmm0, xmmword ptr [r9+18h]
0x1800a4aac  movups  [rsp+178h+var_118], xmm0
0x1800a4ab1  movups  xmm1, xmmword ptr [r9+28h]
0x1800a4ab6  movups  [rsp+178h+var_108], xmm1
0x1800a4abb  movups  xmm0, xmmword ptr [r9+38h]
0x1800a4ac0  movups  [rsp+178h+var_F8], xmm0
0x1800a4ac8  movups  xmm0, xmmword ptr [r9+58h]
0x1800a4acd  movups  [rsp+178h+var_D8], xmm0
0x1800a4ad5  movups  xmm1, xmmword ptr [r9+68h]
0x1800a4ada  movups  [rsp+178h+var_C8], xmm1
0x1800a4ae2  movups  xmm2, xmmword ptr [r9+78h]
0x1800a4ae7  movaps  [rsp+178h+var_B8], xmm2
0x1800a4aef  movups  xmm1, xmmword ptr [r9+0B8h]
0x1800a4af7  movups  [rsp+178h+var_78], xmm1
0x1800a4aff  movups  xmm1, xmmword ptr [r9+0D8h]
0x1800a4b07  movups  [rsp+178h+var_58], xmm1
0x1800a4b0f  movups  xmm1, xmmword ptr [r9+0F8h]
0x1800a4b17  movups  [rsp+178h+var_38], xmm1
0x1800a4b1f  xor     r13b, r13b
0x1800a4b22  jmp     loc_1800A48E9
0x1800a4b27  mov     ebx, 0C000007Bh
0x1800a4b2c  mov     [rsp+178h+var_158], ebx
0x1800a4b30  mov     edi, 7FFE0384h
0x1800a4b35  jmp     loc_1800A4BBF
0x1800a4b3a  mov     ebx, eax
0x1800a4b3c  mov     [rsp+178h+var_158], eax
0x1800a4b40  mov     esi, 7FFE0385h
0x1800a4b45  mov     edi, 7FFE0384h
0x1800a4b4a  jmp     short loc_1800A4BBF
0x1800a4b4c  test    rdx, rdx
0x1800a4b4f  jz      loc_1800A4CD9
0x1800a4b55  test    edi, edi
0x1800a4b57  jz      short loc_1800A4BA9
0x1800a4b59  cmp     rdx, rbx
0x1800a4b5c  jbe     loc_1800A4C19
0x1800a4b62  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800a4b66  lea     r8, [rbx+r15]
0x1800a4b6a  lea     rax, [rdx+10h]
0x1800a4b6e  cmp     rax, r8
0x1800a4b71  ja      loc_1800A4C19
0x1800a4b77  movzx   eax, word ptr [rdx+0Ch]
0x1800a4b7b  mov     [rsp+178h+var_150], ax
0x1800a4b80  movzx   ecx, word ptr [rdx+0Eh]
0x1800a4b84  mov     [rsp+178h+var_14C], cx
0x1800a4b89  jmp     short loc_1800A4B99
0x1800a4b8b  mov     ebx, eax
0x1800a4b8d  mov     esi, 7FFE0385h
0x1800a4b92  mov     edi, 7FFE0384h
0x1800a4b97  jmp     short loc_1800A4BBF
0x1800a4b99  test    ax, ax
0x1800a4b9c  jz      short loc_1800A4BFD
0x1800a4b9e  add     ecx, eax
0x1800a4ba0  lea     rcx, [rdx+rcx*8]
0x1800a4ba4  cmp     rcx, r8
0x1800a4ba7  ja      short loc_1800A4C19
0x1800a4ba9  mov     rax, [rsp+178h+arg_18]
0x1800a4bb1  mov     [rax], rdx
0x1800a4bb4  mov     [r12], r9
0x1800a4bb8  xor     ebx, ebx
0x1800a4bba  mov     edi, 7FFE0384h
0x1800a4bbf  mov     rax, gs:60h
0x1800a4bc8  mov     rcx, [rax+90h]
0x1800a4bcf  test    rcx, rcx
0x1800a4bd2  jnz     short loc_1800A4C4A
0x1800a4bd4  test    byte ptr [rsi], 1
0x1800a4bd7  jnz     loc_1800A4CA7
0x1800a4bdd  mov     eax, ebx
0x1800a4bdf  lea     r11, [rsp+178h+var_28]
0x1800a4be7  mov     rbx, [r11+38h]
0x1800a4beb  mov     rsi, [r11+40h]
0x1800a4bef  mov     rsp, r11
0x1800a4bf2  pop     r15
0x1800a4bf4  pop     r14
0x1800a4bf6  pop     r13
0x1800a4bf8  pop     r12
0x1800a4bfa  pop     rdi
0x1800a4bfb  retn
0x1800a4bfd  test    cx, cx
0x1800a4c00  jnz     short loc_1800A4B9E
0x1800a4c02  mov     ebx, 0C000008Ah
0x1800a4c07  jmp     short loc_1800A4BBA
0x1800a4c09  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800a4c0d  movzx   r14d, al
0x1800a4c11  xor     r14b, r13b
0x1800a4c14  jmp     loc_1800A483D
0x1800a4c19  mov     ebx, 0C000007Bh
0x1800a4c1e  jmp     short loc_1800A4BBA
0x1800a4c20  cmp     dword ptr [rcx], 0
0x1800a4c23  jz      loc_1800A47EE
0x1800a4c29  mov     rax, gs:60h
0x1800a4c32  mov     rcx, [rax+90h]
0x1800a4c39  add     rcx, 22Bh
0x1800a4c40  mov     esi, 7FFE0385h
0x1800a4c45  jmp     loc_1800A47F5
0x1800a4c4a  cmp     dword ptr [rcx], 0
0x1800a4c4d  jz      short loc_1800A4BD4
0x1800a4c4f  mov     rax, gs:60h
0x1800a4c58  mov     rsi, [rax+90h]
0x1800a4c5f  add     rsi, 22Bh
0x1800a4c66  jmp     loc_1800A4BD4
0x1800a4c6b  mov     eax, 0C000000Dh
0x1800a4c70  jmp     loc_1800A4BDF
0x1800a4c75  call    RtlGetCurrentServiceSessionId
0x1800a4c7a  test    eax, eax
0x1800a4c7c  jz      short loc_1800A4CE3
0x1800a4c7e  mov     rax, gs:60h
0x1800a4c87  mov     rcx, [rax+90h]
0x1800a4c8e  add     rcx, 22Ah
0x1800a4c95  movzx   edx, byte ptr [rcx]
0x1800a4c98  lea     rcx, [rsp+178h+var_138]
0x1800a4c9d  call    LdrpTraceLoadMUIDll
0x1800a4ca2  jmp     loc_1800A47FE
0x1800a4ca7  call    RtlGetCurrentServiceSessionId
0x1800a4cac  test    eax, eax
0x1800a4cae  jz      short loc_1800A4CC7
0x1800a4cb0  mov     rax, gs:60h
0x1800a4cb9  mov     rdi, [rax+90h]
0x1800a4cc0  add     rdi, 22Ah
0x1800a4cc7  movzx   edx, byte ptr [rdi]
0x1800a4cca  lea     rcx, [rsp+178h+var_128]
0x1800a4ccf  call    LdrpTraceLoadMUIDll
0x1800a4cd4  jmp     loc_1800A4BDD
  ... truncated ...
```
