# LdrpResGetResourceDirectory

- ea: `0x1800ad130`
- end: `0x1800ad6ba`
- name: `LdrpResGetResourceDirectory`
- size: `1418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800ab4f0`

## callees

- `0x18001f070`
- `0x18006f0d0`
- `0x1800ad130`
- `0x1800ae518`
- `0x18016f030`

## string_xrefs

- `0x1800ad199`: `LdrpResGetResourceDirectory Exit`
- `0x1800ad184`: `LdrpResGetResourceDirectory Enter`

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
0x1800ad130  mov     r11, rsp
0x1800ad133  mov     [r11+10h], rbx
0x1800ad137  mov     [r11+18h], rsi
0x1800ad13b  mov     [r11+20h], r9
0x1800ad13f  push    rdi
0x1800ad140  push    r12
0x1800ad142  push    r13
0x1800ad144  push    r14
0x1800ad146  push    r15
0x1800ad148  sub     rsp, 150h
0x1800ad14f  mov     r14, r9
0x1800ad152  mov     edi, r8d
0x1800ad155  mov     r15, rdx
0x1800ad158  mov     rbx, rcx
0x1800ad15b  xor     eax, eax
0x1800ad15d  mov     [rsp+178h+var_140], rax
0x1800ad162  mov     [r11+8], rax
0x1800ad166  xor     edx, edx; Val
0x1800ad168  mov     r8d, 0F0h; Size
0x1800ad16e  lea     rcx, [rsp+178h+var_118]; void *
0x1800ad173  call    memset$thunk$772440563353939046
0x1800ad178  mov     r13b, 1
0x1800ad17b  mov     [rsp+178h+var_138], 440042h
0x1800ad184  lea     rax, aLdrpresgetreso_0; "LdrpResGetResourceDirectory Enter"
0x1800ad18b  mov     [rsp+178h+var_130], rax
0x1800ad190  mov     [rsp+178h+var_128], 420040h
0x1800ad199  lea     rax, aLdrpresgetreso_1; "LdrpResGetResourceDirectory Exit"
0x1800ad1a0  mov     [rsp+178h+var_120], rax
0x1800ad1a5  mov     rax, gs:60h
0x1800ad1ae  mov     rcx, [rax+90h]
0x1800ad1b5  test    rcx, rcx
0x1800ad1b8  jnz     loc_1800AD5F0
0x1800ad1be  mov     esi, 7FFE0385h
0x1800ad1c3  mov     ecx, esi
0x1800ad1c5  test    [rcx], r13b
0x1800ad1c8  jnz     loc_1800AD645
0x1800ad1ce  test    rbx, rbx
0x1800ad1d1  jz      loc_1800AD63B
0x1800ad1d7  test    r14, r14
0x1800ad1da  jz      loc_1800AD63B
0x1800ad1e0  mov     r12, [rsp+178h+arg_20]
0x1800ad1e8  test    r12, r12
0x1800ad1eb  jz      loc_1800AD63B
0x1800ad1f1  mov     rax, rbx
0x1800ad1f4  and     eax, 1
0x1800ad1f7  test    bl, 2
0x1800ad1fa  jnz     loc_1800AD5D9
0x1800ad200  movzx   r14d, r13b
0x1800ad204  test    rax, rax
0x1800ad207  jnz     loc_1800AD5D9
0x1800ad20d  and     edi, 1000h
0x1800ad213  mov     ecx, 0
0x1800ad218  setz    cl
0x1800ad21b  lea     r9, [rsp+178h+arg_0]
0x1800ad223  mov     r8, r15
0x1800ad226  mov     rdx, rbx
0x1800ad229  call    RtlImageNtHeaderEx
0x1800ad22e  test    eax, eax
0x1800ad230  js      loc_1800AD5AF
0x1800ad236  mov     r9, [rsp+178h+arg_0]
0x1800ad23e  movzx   eax, word ptr [r9+18h]
0x1800ad243  mov     ecx, 10Bh
0x1800ad248  cmp     ax, cx
0x1800ad24b  jnz     loc_1800AD469
0x1800ad251  movups  xmm0, xmmword ptr [r9+18h]
0x1800ad256  movups  [rsp+178h+var_118], xmm0
0x1800ad25b  movups  xmm1, xmmword ptr [r9+28h]
0x1800ad260  movups  [rsp+178h+var_108], xmm1
0x1800ad265  movups  xmm0, xmmword ptr [r9+38h]
0x1800ad26a  movups  [rsp+178h+var_F8], xmm0
0x1800ad272  movups  xmm0, xmmword ptr [r9+58h]
0x1800ad277  movups  [rsp+178h+var_D8], xmm0
0x1800ad27f  movups  xmm2, xmmword ptr [r9+68h]
0x1800ad284  movaps  [rsp+178h+var_C8], xmm2
0x1800ad28c  movups  xmm0, xmmword ptr [r9+78h]
0x1800ad291  movups  [rsp+178h+var_B8], xmm0
0x1800ad299  movups  xmm1, xmmword ptr [r9+0B8h]
0x1800ad2a1  movups  [rsp+178h+var_78], xmm1
0x1800ad2a9  movups  xmm1, xmmword ptr [r9+0D8h]
0x1800ad2b1  movups  [rsp+178h+var_58], xmm1
0x1800ad2b9  movups  xmm0, xmmword ptr [r9+0A8h]
0x1800ad2c1  movups  [rsp+178h+var_88], xmm0
0x1800ad2c9  movups  xmm0, xmmword ptr [r9+0C8h]
0x1800ad2d1  movups  [rsp+178h+var_68], xmm0
0x1800ad2d9  psrldq  xmm2, 0Ch
0x1800ad2de  movups  xmm0, xmmword ptr [r9+0E8h]
0x1800ad2e6  movups  xmm4, xmmword ptr [r9+98h]
0x1800ad2ee  movups  xmm3, xmmword ptr [r9+88h]
0x1800ad2f6  movups  xmm5, xmmword ptr [r9+48h]
0x1800ad2fb  movd    eax, xmm2
0x1800ad2ff  movups  [rsp+178h+var_48], xmm0
0x1800ad307  movaps  [rsp+178h+var_98], xmm4
0x1800ad30f  movaps  [rsp+178h+var_A8], xmm3
0x1800ad317  movaps  [rsp+178h+var_E8], xmm5
0x1800ad31f  cmp     eax, 2
0x1800ad322  jbe     loc_1800AD443
0x1800ad328  movd    edx, xmm4
0x1800ad32c  movd    eax, xmm3
0x1800ad330  test    r13b, r13b
0x1800ad333  cmovnz  edx, eax
0x1800ad336  test    edx, edx
0x1800ad338  jz      loc_1800AD41D
0x1800ad33e  test    r14b, r14b
0x1800ad341  jz      short loc_1800AD3AE
0x1800ad343  add     rdx, rbx
0x1800ad346  cmp     rdx, rbx
0x1800ad349  jnb     short loc_1800AD3A4
0x1800ad34b  mov     ebx, 0C000007Bh
0x1800ad350  mov     [rsp+178h+var_158], ebx
0x1800ad354  mov     edi, 7FFE0384h
0x1800ad359  jmp     loc_1800AD58F
0x1800ad35e  mov     rax, rbx
0x1800ad361  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800ad365  add     rax, r15
0x1800ad368  cmp     r14, rax
0x1800ad36b  ja      loc_1800AD430
0x1800ad371  mov     r10d, [r8+0Ch]
0x1800ad375  cmp     edx, r10d
0x1800ad378  jb      loc_1800AD411
0x1800ad37e  mov     r11d, [r8+10h]
0x1800ad382  lea     eax, [r10+r11]
0x1800ad386  cmp     edx, eax
0x1800ad388  jnb     loc_1800AD411
0x1800ad38e  test    r11d, r11d
0x1800ad391  jz      loc_1800AD456
0x1800ad397  mov     eax, [r8+14h]
0x1800ad39b  sub     rax, r10
0x1800ad39e  add     rax, rbx
0x1800ad3a1  add     rdx, rax
0x1800ad3a4  mov     [rsp+178h+var_140], rdx
0x1800ad3a9  jmp     loc_1800AD51C
0x1800ad3ae  psrldq  xmm5, 0Ch
0x1800ad3b3  movd    eax, xmm5
0x1800ad3b7  cmp     edx, eax
0x1800ad3b9  jb      short loc_1800AD343
0x1800ad3bb  xor     r13d, r13d
0x1800ad3be  test    edi, edi
0x1800ad3c0  setnz   r13b
0x1800ad3c4  mov     dword ptr [rsp+178h+arg_0], r13d
0x1800ad3cc  mov     [rsp+178h+var_154], 0
0x1800ad3d4  mov     [rsp+178h+var_148], 0
0x1800ad3dd  movzx   r8d, word ptr [r9+14h]
0x1800ad3e2  add     r8, 18h
0x1800ad3e6  add     r8, r9
0x1800ad3e9  mov     [rsp+178h+var_148], r8
0x1800ad3ee  jz      short loc_1800AD430
0x1800ad3f0  xor     ecx, ecx
0x1800ad3f2  mov     [rsp+178h+var_154], ecx
0x1800ad3f6  movzx   eax, word ptr [r9+6]
0x1800ad3fb  cmp     ecx, eax
0x1800ad3fd  jge     short loc_1800AD430
0x1800ad3ff  lea     r14, [r8+28h]
0x1800ad403  test    r13b, r13b
0x1800ad406  jnz     loc_1800AD35E
0x1800ad40c  jmp     loc_1800AD371
0x1800ad411  mov     r8, r14
0x1800ad414  mov     [rsp+178h+var_148], r14
0x1800ad419  inc     ecx
0x1800ad41b  jmp     short loc_1800AD3F2
0x1800ad41d  mov     ebx, 0C0000089h
0x1800ad422  mov     [rsp+178h+var_158], ebx
0x1800ad426  mov     edi, 7FFE0384h
0x1800ad42b  jmp     loc_1800AD58F
0x1800ad430  mov     ebx, 0C000007Bh
0x1800ad435  mov     [rsp+178h+var_158], ebx
0x1800ad439  mov     edi, 7FFE0384h
0x1800ad43e  jmp     loc_1800AD58F
0x1800ad443  mov     ebx, 0C0000089h
0x1800ad448  mov     [rsp+178h+var_158], ebx
0x1800ad44c  mov     edi, 7FFE0384h
0x1800ad451  jmp     loc_1800AD58F
0x1800ad456  mov     ebx, 0C0000089h
0x1800ad45b  mov     [rsp+178h+var_158], ebx
0x1800ad45f  mov     edi, 7FFE0384h
0x1800ad464  jmp     loc_1800AD58F
0x1800ad469  mov     ecx, 20Bh
0x1800ad46e  cmp     ax, cx
0x1800ad471  jnz     loc_1800AD4F7
0x1800ad477  movups  xmm0, xmmword ptr [r9+18h]
0x1800ad47c  movups  [rsp+178h+var_118], xmm0
0x1800ad481  movups  xmm1, xmmword ptr [r9+28h]
0x1800ad486  movups  [rsp+178h+var_108], xmm1
0x1800ad48b  movups  xmm0, xmmword ptr [r9+38h]
0x1800ad490  movups  [rsp+178h+var_F8], xmm0
0x1800ad498  movups  xmm0, xmmword ptr [r9+58h]
0x1800ad49d  movups  [rsp+178h+var_D8], xmm0
0x1800ad4a5  movups  xmm1, xmmword ptr [r9+68h]
0x1800ad4aa  movups  [rsp+178h+var_C8], xmm1
0x1800ad4b2  movups  xmm2, xmmword ptr [r9+78h]
0x1800ad4b7  movaps  [rsp+178h+var_B8], xmm2
0x1800ad4bf  movups  xmm1, xmmword ptr [r9+0B8h]
0x1800ad4c7  movups  [rsp+178h+var_78], xmm1
0x1800ad4cf  movups  xmm1, xmmword ptr [r9+0D8h]
0x1800ad4d7  movups  [rsp+178h+var_58], xmm1
0x1800ad4df  movups  xmm1, xmmword ptr [r9+0F8h]
0x1800ad4e7  movups  [rsp+178h+var_38], xmm1
0x1800ad4ef  xor     r13b, r13b
0x1800ad4f2  jmp     loc_1800AD2B9
0x1800ad4f7  mov     ebx, 0C000007Bh
0x1800ad4fc  mov     [rsp+178h+var_158], ebx
0x1800ad500  mov     edi, 7FFE0384h
0x1800ad505  jmp     loc_1800AD58F
0x1800ad50a  mov     ebx, eax
0x1800ad50c  mov     [rsp+178h+var_158], eax
0x1800ad510  mov     esi, 7FFE0385h
0x1800ad515  mov     edi, 7FFE0384h
0x1800ad51a  jmp     short loc_1800AD58F
0x1800ad51c  test    rdx, rdx
0x1800ad51f  jz      loc_1800AD6A9
0x1800ad525  test    edi, edi
0x1800ad527  jz      short loc_1800AD579
0x1800ad529  cmp     rdx, rbx
0x1800ad52c  jbe     loc_1800AD5E9
0x1800ad532  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800ad536  lea     r8, [rbx+r15]
0x1800ad53a  lea     rax, [rdx+10h]
0x1800ad53e  cmp     rax, r8
0x1800ad541  ja      loc_1800AD5E9
0x1800ad547  movzx   eax, word ptr [rdx+0Ch]
0x1800ad54b  mov     [rsp+178h+var_150], ax
0x1800ad550  movzx   ecx, word ptr [rdx+0Eh]
0x1800ad554  mov     [rsp+178h+var_14C], cx
0x1800ad559  jmp     short loc_1800AD569
0x1800ad55b  mov     ebx, eax
0x1800ad55d  mov     esi, 7FFE0385h
0x1800ad562  mov     edi, 7FFE0384h
0x1800ad567  jmp     short loc_1800AD58F
0x1800ad569  test    ax, ax
0x1800ad56c  jz      short loc_1800AD5CD
0x1800ad56e  add     ecx, eax
0x1800ad570  lea     rcx, [rdx+rcx*8]
0x1800ad574  cmp     rcx, r8
0x1800ad577  ja      short loc_1800AD5E9
0x1800ad579  mov     rax, [rsp+178h+arg_18]
0x1800ad581  mov     [rax], rdx
0x1800ad584  mov     [r12], r9
0x1800ad588  xor     ebx, ebx
0x1800ad58a  mov     edi, 7FFE0384h
0x1800ad58f  mov     rax, gs:60h
0x1800ad598  mov     rcx, [rax+90h]
0x1800ad59f  test    rcx, rcx
0x1800ad5a2  jnz     short loc_1800AD61A
0x1800ad5a4  test    byte ptr [rsi], 1
0x1800ad5a7  jnz     loc_1800AD677
0x1800ad5ad  mov     eax, ebx
0x1800ad5af  lea     r11, [rsp+178h+var_28]
0x1800ad5b7  mov     rbx, [r11+38h]
0x1800ad5bb  mov     rsi, [r11+40h]
0x1800ad5bf  mov     rsp, r11
0x1800ad5c2  pop     r15
0x1800ad5c4  pop     r14
0x1800ad5c6  pop     r13
0x1800ad5c8  pop     r12
0x1800ad5ca  pop     rdi
0x1800ad5cb  retn
0x1800ad5cd  test    cx, cx
0x1800ad5d0  jnz     short loc_1800AD56E
0x1800ad5d2  mov     ebx, 0C000008Ah
0x1800ad5d7  jmp     short loc_1800AD58A
0x1800ad5d9  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1800ad5dd  movzx   r14d, al
0x1800ad5e1  xor     r14b, r13b
0x1800ad5e4  jmp     loc_1800AD20D
0x1800ad5e9  mov     ebx, 0C000007Bh
0x1800ad5ee  jmp     short loc_1800AD58A
0x1800ad5f0  cmp     dword ptr [rcx], 0
0x1800ad5f3  jz      loc_1800AD1BE
0x1800ad5f9  mov     rax, gs:60h
0x1800ad602  mov     rcx, [rax+90h]
0x1800ad609  add     rcx, 22Bh
0x1800ad610  mov     esi, 7FFE0385h
0x1800ad615  jmp     loc_1800AD1C5
0x1800ad61a  cmp     dword ptr [rcx], 0
0x1800ad61d  jz      short loc_1800AD5A4
0x1800ad61f  mov     rax, gs:60h
0x1800ad628  mov     rsi, [rax+90h]
0x1800ad62f  add     rsi, 22Bh
0x1800ad636  jmp     loc_1800AD5A4
0x1800ad63b  mov     eax, 0C000000Dh
0x1800ad640  jmp     loc_1800AD5AF
0x1800ad645  call    RtlGetCurrentServiceSessionId
0x1800ad64a  test    eax, eax
0x1800ad64c  jz      short loc_1800AD6B3
0x1800ad64e  mov     rax, gs:60h
0x1800ad657  mov     rcx, [rax+90h]
0x1800ad65e  add     rcx, 22Ah
0x1800ad665  movzx   edx, byte ptr [rcx]
0x1800ad668  lea     rcx, [rsp+178h+var_138]
0x1800ad66d  call    LdrpTraceLoadMUIDll
0x1800ad672  jmp     loc_1800AD1CE
0x1800ad677  call    RtlGetCurrentServiceSessionId
0x1800ad67c  test    eax, eax
0x1800ad67e  jz      short loc_1800AD697
0x1800ad680  mov     rax, gs:60h
0x1800ad689  mov     rdi, [rax+90h]
0x1800ad690  add     rdi, 22Ah
0x1800ad697  movzx   edx, byte ptr [rdi]
0x1800ad69a  lea     rcx, [rsp+178h+var_128]
0x1800ad69f  call    LdrpTraceLoadMUIDll
0x1800ad6a4  jmp     loc_1800AD5AD
  ... truncated ...
```
