# LdrpLogEtwDllSearchResults

- ea: `0x1800c3088`
- end: `0x1800c3585`
- name: `LdrpLogEtwDllSearchResults`
- size: `1277`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x1800c25c0`

## callees

- `0x1800165d0`
- `0x18001861c`
- `0x18001b984`
- `0x18001d490`
- `0x18006f0d0`
- `0x18007b960`
- `0x1800c3088`
- `0x1800c3700`
- `0x18011f24c`
- `0x18015f690`
- `0x180162810`

## pseudocode

```c
__int64 __fastcall LdrpLogEtwDllSearchResults(int a1, __int64 a2)
{
  __m128i v4; // xmm6
  void *ProcessHeap; // rcx
  __int64 result; // rax
  __int64 v7; // rbx
  int v8; // edi
  char *v9; // rcx
  int UnicodeStringFromPathElement; // eax
  __int64 v11; // rcx
  int v12; // r15d
  int v13; // eax
  __int64 v14; // rcx
  int v15; // r12d
  int v16; // esi
  unsigned __int64 v17; // xmm0_8
  unsigned __int64 v18; // rdx
  _WORD *v19; // r11
  __int64 v20; // r12
  _WORD *v21; // r10
  __int64 v22; // rcx
  int v23; // edx
  __int64 v24; // r8
  _WORD *v25; // rax
  int v26; // r9d
  _WORD *v27; // rcx
  int v28; // eax
  unsigned int v29; // r14d
  unsigned int v30; // ebx
  unsigned __int64 v31; // rax
  _WORD *v32; // r15
  int v33; // r10d
  unsigned __int64 v34; // r8
  _WORD *v35; // r9
  __int64 v36; // rcx
  _WORD *v37; // rax
  int v38; // r11d
  _WORD *v39; // rcx
  int v40; // eax
  unsigned int v41; // ecx
  unsigned int v42; // r13d
  unsigned int v43; // ebx
  _WORD *v44; // r14
  int v45; // r10d
  unsigned __int64 v46; // r8
  _WORD *v47; // r9
  __int64 v48; // rcx
  _WORD *v49; // rax
  int v50; // r11d
  _WORD *v51; // rcx
  int v52; // eax
  unsigned int v53; // ecx
  unsigned int v54; // esi
  unsigned int v55; // ebx
  _WORD *v56; // r9
  int v57; // r10d
  unsigned __int64 v58; // r8
  _WORD *v59; // rax
  int v60; // r11d
  _WORD *v61; // rcx
  int v62; // eax
  unsigned int v63; // ebx
  __int64 v64; // rax
  int v65; // [rsp+28h] [rbp-E0h] BYREF
  int v66; // [rsp+2Ch] [rbp-DCh]
  int v67; // [rsp+30h] [rbp-D8h]
  __int128 v68; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v69; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v70; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v71; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v72; // [rsp+78h] [rbp-90h]
  _BYTE v73[3200]; // [rsp+88h] [rbp-80h] BYREF

  v65 = 0;
  v4 = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v68 = 0;
  v70 = 0;
  v69 = 0;
  result = RtlAllocateHeap_0(ProcessHeap, 0, 584);
  v7 = result;
  if ( result )
  {
    *(_WORD *)(result + 6) = 5332;
    *(_DWORD *)(result + 32) = *(_DWORD *)(a2 + 32);
    *(_DWORD *)(result + 36) = *(_DWORD *)(*(_QWORD *)(a2 + 16) + 24LL);
    *(_DWORD *)(result + 40) = a1;
    *(_DWORD *)(result + 44) = *(_DWORD *)(a2 + 36);
    LdrpEventAddUnicodeString(a2, result + 48, 532, &v65);
    v8 = v65;
    v9 = (unsigned int)RtlGetCurrentServiceSessionId() ? (char *)NtCurrentPeb()->SharedData + 554 : (char *)2147353476;
    NtTraceEvent((unsigned __int8)*v9, 1026, (unsigned int)(v8 + 16), v7);
    result = RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v7);
    if ( (a1 & 0x100) != 0 )
    {
      v71 = 0;
      result = RtlGetCurrentDirectory_U(3192, v73);
      if ( (_DWORD)result )
      {
        if ( (unsigned __int8)RtlCreateUnicodeString(&v71, v73) )
          v4 = v71;
        UnicodeStringFromPathElement = LdrpMakeUnicodeStringFromPathElement(*(_QWORD *)(a2 + 16), 1, &v68);
        v11 = *(_QWORD *)(a2 + 16);
        v65 = UnicodeStringFromPathElement;
        v12 = UnicodeStringFromPathElement;
        v13 = LdrpMakeUnicodeStringFromPathElement(v11, 0, &v70);
        v14 = *(_QWORD *)(a2 + 16);
        v66 = v13;
        v15 = v13;
        v67 = LdrpMakeUnicodeStringFromPathElement(v14, 5, &v69);
        v16 = v67;
        result = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, 3232);
        v72 = result;
        v17 = _mm_srli_si128(v4, 8).m128i_u64[0];
        v18 = v17;
        v71.m128i_i64[0] = v17;
        if ( result )
        {
          *(_WORD *)(result + 6) = 5333;
          v19 = (_WORD *)(result + 36);
          *(_DWORD *)(result + 32) = a1;
          v20 = 2147483646;
          if ( (unsigned __int16)_mm_cvtsi128_si32(v4) )
          {
            v21 = (_WORD *)v17;
            v22 = 2147483646;
            v23 = 2;
            v24 = 1596;
            v25 = (_WORD *)(result + 36);
            v26 = 0;
            do
            {
              if ( !v22 )
                break;
              if ( !*v21 )
                break;
              *v25++ = *v21++;
              --v22;
              ++v26;
              --v24;
            }
            while ( v24 );
            v27 = v25 - 1;
            if ( v24 )
              v27 = v25;
            v28 = v26 - 1;
            if ( v24 )
              v28 = v26;
            *v27 = 0;
            v29 = 2 * v28 + 2;
          }
          else
          {
            v23 = 2;
            *v19 = 0;
            v29 = 2;
          }
          v30 = 3192 - v29;
          v31 = (unsigned __int64)v29 >> 1;
          v32 = &v19[v31];
          if ( (_WORD)v68 )
          {
            v33 = 0;
            v34 = (unsigned __int64)v30 >> 1;
            if ( v34 )
            {
              v35 = (_WORD *)*((_QWORD *)&v68 + 1);
              v36 = 2147483646;
              v37 = &v19[v31];
              v38 = 0;
              do
              {
                if ( !v36 )
                  break;
                if ( !*v35 )
                  break;
                *v37++ = *v35++;
                --v36;
                ++v38;
                --v34;
              }
              while ( v34 );
              v39 = v37 - 1;
              if ( v34 )
                v39 = v37;
              v40 = v38 - 1;
              if ( v34 )
                v40 = v38;
              v33 = (v30 >> 1) - v40;
              *v39 = 0;
            }
            v41 = v30 + 2 * (1 - v33);
          }
          else if ( v30 < 2 )
          {
            v41 = 0;
          }
          else
          {
            v41 = 2;
            *v32 = 0;
          }
          v42 = v41 + v29;
          v43 = v30 - v41;
          v44 = &v32[(unsigned __int64)v41 >> 1];
          if ( (_WORD)v70 )
          {
            v45 = 0;
            v46 = (unsigned __int64)v43 >> 1;
            if ( v46 )
            {
              v47 = (_WORD *)*((_QWORD *)&v70 + 1);
              v48 = 2147483646;
              v49 = v44;
              v50 = 0;
              do
              {
                if ( !v48 )
                  break;
                if ( !*v47 )
                  break;
                *v49++ = *v47++;
                --v48;
                ++v50;
                --v46;
              }
              while ( v46 );
              v51 = v49 - 1;
              if ( v46 )
                v51 = v49;
              v52 = v50 - 1;
              if ( v46 )
                v52 = v50;
              v45 = (v43 >> 1) - v52;
              *v51 = 0;
            }
            v53 = v43 + 2 * (1 - v45);
          }
          else if ( v43 < 2 )
          {
            v53 = 0;
          }
          else
          {
            v53 = 2;
            *v44 = 0;
          }
          v54 = v53 + v42;
          v55 = v43 - v53;
          v56 = &v44[(unsigned __int64)v53 >> 1];
          if ( (_WORD)v69 )
          {
            v57 = 0;
            v58 = (unsigned __int64)v55 >> 1;
            if ( v58 )
            {
              v59 = (_WORD *)*((_QWORD *)&v69 + 1);
              v60 = 0;
              do
              {
                if ( !v20 )
                  break;
                if ( !*v59 )
                  break;
                *v56++ = *v59++;
                --v20;
                ++v60;
                --v58;
              }
              while ( v58 );
              v61 = v56 - 1;
              v62 = v60 - 1;
              if ( v58 )
              {
                v61 = v56;
                v62 = v60;
              }
              v57 = (v55 >> 1) - v62;
              *v61 = 0;
            }
            v23 = v55 + 2 * (1 - v57);
          }
          else if ( v55 < 2 )
          {
            v23 = 0;
          }
          else
          {
            *v56 = 0;
          }
          v63 = v54 + v23;
          if ( (unsigned int)RtlGetCurrentServiceSessionId() )
            v64 = (__int64)NtCurrentPeb()->SharedData + 554;
          else
            v64 = 2147353476;
          NtTraceEvent(*(unsigned __int8 *)v64, 1026, v63 + 4, v72);
          result = RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v72);
          v18 = v71.m128i_i64[0];
          v12 = v65;
          v15 = v66;
          v16 = v67;
        }
        if ( v18 )
          result = RtlpSysVolFree(v18);
        if ( v12 >= 0 && *((_QWORD *)&v68 + 1) )
          result = RtlpSysVolFree(*((_QWORD *)&v68 + 1));
        if ( v16 >= 0 && *((_QWORD *)&v69 + 1) )
          result = RtlpSysVolFree(*((_QWORD *)&v69 + 1));
        if ( v15 >= 0 )
        {
          if ( *((_QWORD *)&v70 + 1) )
            return RtlpSysVolFree(*((_QWORD *)&v70 + 1));
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c3088  mov     rax, rsp
0x1800c308b  push    rbp
0x1800c308c  push    rbx
0x1800c308d  push    rsi
0x1800c308e  push    rdi
0x1800c308f  push    r12
0x1800c3091  push    r13
0x1800c3093  push    r14
0x1800c3095  push    r15
0x1800c3097  lea     rbp, [rax-0C68h]
0x1800c309e  sub     rsp, 0D28h
0x1800c30a5  movaps  xmmword ptr [rax-58h], xmm6
0x1800c30a9  mov     rax, cs:__security_cookie
0x1800c30b0  xor     rax, rsp
0x1800c30b3  mov     [rbp+0C60h+var_60], rax
0x1800c30ba  mov     r14d, ecx
0x1800c30bd  xorps   xmm0, xmm0
0x1800c30c0  mov     rcx, gs:60h
0x1800c30c9  mov     rsi, rdx
0x1800c30cc  xorps   xmm1, xmm1
0x1800c30cf  xor     r13d, r13d
0x1800c30d2  xor     edx, edx
0x1800c30d4  mov     [rsp+0D60h+var_D40], r13d
0x1800c30d9  mov     r8d, 248h
0x1800c30df  xorps   xmm6, xmm6
0x1800c30e2  mov     rcx, [rcx+30h]
0x1800c30e6  movups  [rsp+0D60h+var_D38+8], xmm0
0x1800c30eb  movups  [rsp+0D60h+var_D18+8], xmm0
0x1800c30f0  movups  [rsp+0D60h+var_D28+8], xmm1
0x1800c30f5  call    RtlAllocateHeap_0
0x1800c30fa  mov     rbx, rax
0x1800c30fd  test    rax, rax
0x1800c3100  jz      loc_1800C34F1
0x1800c3106  mov     word ptr [rax+6], 14D4h
0x1800c310c  lea     r9, [rsp+0D60h+var_D40]
0x1800c3111  mov     ecx, [rsi+20h]
0x1800c3114  mov     r8d, 214h
0x1800c311a  mov     [rax+20h], ecx
0x1800c311d  mov     rcx, [rsi+10h]
0x1800c3121  mov     edx, [rcx+18h]
0x1800c3124  mov     [rax+24h], edx
0x1800c3127  lea     rdx, [rax+30h]
0x1800c312b  mov     [rax+28h], r14d
0x1800c312f  mov     ecx, [rsi+24h]
0x1800c3132  mov     [rax+2Ch], ecx
0x1800c3135  mov     rcx, rsi
0x1800c3138  call    LdrpEventAddUnicodeString
0x1800c313d  mov     edi, [rsp+0D60h+var_D40]
0x1800c3141  call    RtlGetCurrentServiceSessionId
0x1800c3146  test    eax, eax
0x1800c3148  jz      loc_1800C351D
0x1800c314e  mov     rax, gs:60h
0x1800c3157  mov     rcx, [rax+90h]
0x1800c315e  add     rcx, 22Ah
0x1800c3165  movzx   ecx, byte ptr [rcx]
0x1800c3168  lea     r8d, [rdi+10h]
0x1800c316c  mov     r9, rbx
0x1800c316f  mov     edx, 402h
0x1800c3174  call    NtTraceEvent
0x1800c3179  mov     rcx, gs:60h
0x1800c3182  mov     r8, rbx
0x1800c3185  xor     edx, edx
0x1800c3187  mov     rcx, [rcx+30h]
0x1800c318b  call    RtlFreeHeap_0
0x1800c3190  bt      r14d, 8
0x1800c3195  jnb     loc_1800C34F1
0x1800c319b  xorps   xmm0, xmm0
0x1800c319e  lea     rdx, [rbp+0C60h+var_CE0]
0x1800c31a2  mov     ebx, 0C78h
0x1800c31a7  mov     ecx, ebx
0x1800c31a9  movups  [rsp+0D60h+var_D08+8], xmm0
0x1800c31ae  call    RtlGetCurrentDirectory_U
0x1800c31b3  test    eax, eax
0x1800c31b5  jz      loc_1800C34F1
0x1800c31bb  lea     rdx, [rbp+0C60h+var_CE0]
0x1800c31bf  lea     rcx, [rsp+0D60h+var_D08+8]
0x1800c31c4  call    RtlCreateUnicodeString
0x1800c31c9  test    al, al
0x1800c31cb  jz      short loc_1800C31D2
0x1800c31cd  movaps  xmm6, [rsp+0D60h+var_D08+8]
0x1800c31d2  mov     rcx, [rsi+10h]
0x1800c31d6  lea     r8, [rsp+0D60h+var_D38+8]
0x1800c31db  mov     edi, 1
0x1800c31e0  mov     edx, edi
0x1800c31e2  call    LdrpMakeUnicodeStringFromPathElement
0x1800c31e7  mov     rcx, [rsi+10h]
0x1800c31eb  lea     r8, [rsp+0D60h+var_D18+8]
0x1800c31f0  xor     edx, edx
0x1800c31f2  mov     [rsp+0D60h+var_D40], eax
0x1800c31f6  mov     r15d, eax
0x1800c31f9  call    LdrpMakeUnicodeStringFromPathElement
0x1800c31fe  mov     rcx, [rsi+10h]
0x1800c3202  lea     r8, [rsp+0D60h+var_D28+8]
0x1800c3207  lea     edx, [rdi+4]
0x1800c320a  mov     [rsp+0D60h+var_D3C], eax
0x1800c320e  mov     r12d, eax
0x1800c3211  call    LdrpMakeUnicodeStringFromPathElement
0x1800c3216  mov     rcx, gs:60h
0x1800c321f  xor     edx, edx
0x1800c3221  mov     r8d, 0CA0h
0x1800c3227  mov     dword ptr [rsp+0D60h+var_D38], eax
0x1800c322b  mov     esi, eax
0x1800c322d  mov     rcx, [rcx+30h]
0x1800c3231  call    RtlAllocateHeap_0
0x1800c3236  mov     [rsp+0D60h+var_CF0], rax
0x1800c323b  movdqa  xmm0, xmm6
0x1800c323f  psrldq  xmm0, 8
0x1800c3244  movq    rdx, xmm0
0x1800c3249  mov     qword ptr [rsp+0D60h+var_D08+8], rdx
0x1800c324e  test    rax, rax
0x1800c3251  jz      loc_1800C34A3
0x1800c3257  mov     word ptr [rax+6], 14D5h
0x1800c325d  lea     r11, [rax+24h]
0x1800c3261  mov     [rax+20h], r14d
0x1800c3265  mov     r12d, 7FFFFFFEh
0x1800c326b  movd    eax, xmm6
0x1800c326f  test    ax, ax
0x1800c3272  jz      loc_1800C356A
0x1800c3278  mov     r10, rdx
0x1800c327b  mov     ecx, r12d
0x1800c327e  lea     edx, [rdi+1]
0x1800c3281  mov     r8d, 63Ch
0x1800c3287  mov     rax, r11
0x1800c328a  mov     r9, r13
0x1800c328d  test    rcx, rcx
0x1800c3290  jz      short loc_1800C32AF
0x1800c3292  movzx   esi, word ptr [r10]
0x1800c3296  test    si, si
0x1800c3299  jz      short loc_1800C32AF
0x1800c329b  mov     [rax], si
0x1800c329e  add     r10, rdx
0x1800c32a1  add     rax, rdx
0x1800c32a4  sub     rcx, rdi
0x1800c32a7  add     r9, rdi
0x1800c32aa  sub     r8, rdi
0x1800c32ad  jnz     short loc_1800C328D
0x1800c32af  lea     rcx, [rax-2]
0x1800c32b3  test    r8, r8
0x1800c32b6  cmovnz  rcx, rax
0x1800c32ba  lea     eax, [r9-1]
0x1800c32be  cmovnz  eax, r9d
0x1800c32c2  mov     [rcx], r13w
0x1800c32c6  lea     r14d, ds:2[rax*2]
0x1800c32ce  mov     eax, r14d
0x1800c32d1  sub     ebx, r14d
0x1800c32d4  shr     rax, 1
0x1800c32d7  lea     r15, [r11+rax*2]
0x1800c32db  cmp     word ptr [rsp+0D60h+var_D38+8], r13w
0x1800c32e1  jz      loc_1800C3527
0x1800c32e7  mov     r8d, ebx
0x1800c32ea  mov     r10, r13
0x1800c32ed  shr     r8, 1
0x1800c32f0  jz      short loc_1800C333F
0x1800c32f2  mov     r9, qword ptr [rsp+0D60h+var_D28]
0x1800c32f7  mov     r10, r8
0x1800c32fa  mov     rcx, r12
0x1800c32fd  mov     rax, r15
0x1800c3300  mov     r11, r13
0x1800c3303  test    rcx, rcx
0x1800c3306  jz      short loc_1800C3325
0x1800c3308  movzx   esi, word ptr [r9]
0x1800c330c  test    si, si
0x1800c330f  jz      short loc_1800C3325
0x1800c3311  mov     [rax], si
0x1800c3314  add     r9, rdx
0x1800c3317  add     rax, rdx
0x1800c331a  sub     rcx, rdi
0x1800c331d  add     r11, rdi
0x1800c3320  sub     r8, rdi
0x1800c3323  jnz     short loc_1800C3303
0x1800c3325  test    r8, r8
0x1800c3328  lea     rcx, [rax-2]
0x1800c332c  cmovnz  rcx, rax
0x1800c3330  lea     rax, [r11-1]
0x1800c3334  cmovnz  rax, r11
0x1800c3338  sub     r10, rax
0x1800c333b  mov     [rcx], r13w
0x1800c333f  mov     eax, edi
0x1800c3341  sub     eax, r10d
0x1800c3344  lea     ecx, [rbx+rax*2]
0x1800c3347  mov     eax, ecx
0x1800c3349  lea     r13d, [rcx+r14]
0x1800c334d  shr     rax, 1
0x1800c3350  sub     ebx, ecx
0x1800c3352  lea     r14, [r15+rax*2]
0x1800c3356  xor     r15d, r15d
0x1800c3359  cmp     word ptr [rsp+0D60h+var_D18+8], r15w
0x1800c335f  jz      loc_1800C353E
0x1800c3365  mov     r8d, ebx
0x1800c3368  mov     r10d, r15d
0x1800c336b  shr     r8, 1
0x1800c336e  jz      short loc_1800C33BD
0x1800c3370  mov     r9, qword ptr [rsp+0D60h+var_D08]
0x1800c3375  mov     r10, r8
0x1800c3378  mov     rcx, r12
0x1800c337b  mov     rax, r14
0x1800c337e  mov     r11d, r15d
0x1800c3381  test    rcx, rcx
0x1800c3384  jz      short loc_1800C33A3
0x1800c3386  movzx   esi, word ptr [r9]
0x1800c338a  test    si, si
0x1800c338d  jz      short loc_1800C33A3
0x1800c338f  mov     [rax], si
0x1800c3392  add     r9, rdx
0x1800c3395  add     rax, rdx
0x1800c3398  sub     rcx, rdi
0x1800c339b  add     r11, rdi
0x1800c339e  sub     r8, rdi
0x1800c33a1  jnz     short loc_1800C3381
0x1800c33a3  test    r8, r8
0x1800c33a6  lea     rcx, [rax-2]
0x1800c33aa  cmovnz  rcx, rax
0x1800c33ae  lea     rax, [r11-1]
0x1800c33b2  cmovnz  rax, r11
0x1800c33b6  sub     r10, rax
0x1800c33b9  mov     [rcx], r15w
0x1800c33bd  mov     eax, edi
0x1800c33bf  sub     eax, r10d
0x1800c33c2  lea     ecx, [rbx+rax*2]
0x1800c33c5  mov     eax, ecx
0x1800c33c7  lea     esi, [rcx+r13]
0x1800c33cb  shr     rax, 1
0x1800c33ce  sub     ebx, ecx
0x1800c33d0  xor     r13d, r13d
0x1800c33d3  lea     r9, [r14+rax*2]
0x1800c33d7  cmp     word ptr [rsp+0D60h+var_D28+8], r13w
0x1800c33dd  jz      loc_1800C3555
0x1800c33e3  mov     r8d, ebx
0x1800c33e6  mov     r10d, r13d
0x1800c33e9  shr     r8, 1
0x1800c33ec  jz      short loc_1800C3435
0x1800c33ee  mov     rax, qword ptr [rsp+0D60h+var_D18]
0x1800c33f3  mov     r10, r8
0x1800c33f6  mov     r11d, r13d
0x1800c33f9  test    r12, r12
0x1800c33fc  jz      short loc_1800C341B
0x1800c33fe  movzx   ecx, word ptr [rax]
0x1800c3401  test    cx, cx
0x1800c3404  jz      short loc_1800C341B
0x1800c3406  mov     [r9], cx
0x1800c340a  add     rax, rdx
0x1800c340d  add     r9, rdx
0x1800c3410  sub     r12, rdi
0x1800c3413  add     r11, rdi
0x1800c3416  sub     r8, rdi
0x1800c3419  jnz     short loc_1800C33F9
0x1800c341b  test    r8, r8
0x1800c341e  lea     rcx, [r9-2]
0x1800c3422  lea     rax, [r11-1]
0x1800c3426  cmovnz  rcx, r9
0x1800c342a  cmovnz  rax, r11
0x1800c342e  sub     r10, rax
0x1800c3431  mov     [rcx], r13w
0x1800c3435  sub     edi, r10d
0x1800c3438  lea     edx, [rbx+rdi*2]
0x1800c343b  lea     ebx, [rsi+rdx]
0x1800c343e  call    RtlGetCurrentServiceSessionId
0x1800c3443  test    eax, eax
0x1800c3445  jz      loc_1800C357B
0x1800c344b  mov     rax, gs:60h
0x1800c3454  mov     rax, [rax+90h]
0x1800c345b  add     rax, 22Ah
0x1800c3461  movzx   ecx, byte ptr [rax]
0x1800c3464  lea     r8d, [rbx+4]
0x1800c3468  mov     r9, [rsp+0D60h+var_CF0]
0x1800c346d  mov     edx, 402h
0x1800c3472  call    NtTraceEvent
0x1800c3477  mov     rcx, gs:60h
0x1800c3480  xor     edx, edx
0x1800c3482  mov     r8, [rsp+0D60h+var_CF0]
0x1800c3487  mov     rcx, [rcx+30h]
0x1800c348b  call    RtlFreeHeap_0
0x1800c3490  mov     rdx, qword ptr [rsp+0D60h+var_D08+8]
0x1800c3495  mov     r15d, [rsp+0D60h+var_D40]
0x1800c349a  mov     r12d, [rsp+0D60h+var_D3C]
0x1800c349f  mov     esi, dword ptr [rsp+0D60h+var_D38]
0x1800c34a3  test    rdx, rdx
0x1800c34a6  jz      short loc_1800C34B0
0x1800c34a8  mov     rcx, rdx
0x1800c34ab  call    RtlpSysVolFree
0x1800c34b0  test    r15d, r15d
0x1800c34b3  js      short loc_1800C34C6
0x1800c34b5  cmp     qword ptr [rsp+0D60h+var_D28], r13
0x1800c34ba  jz      short loc_1800C34C6
0x1800c34bc  mov     rcx, qword ptr [rsp+0D60h+var_D28]
0x1800c34c1  call    RtlpSysVolFree
0x1800c34c6  test    esi, esi
0x1800c34c8  js      short loc_1800C34DB
0x1800c34ca  cmp     qword ptr [rsp+0D60h+var_D18], r13
0x1800c34cf  jz      short loc_1800C34DB
0x1800c34d1  mov     rcx, qword ptr [rsp+0D60h+var_D18]
0x1800c34d6  call    RtlpSysVolFree
0x1800c34db  test    r12d, r12d
0x1800c34de  js      short loc_1800C34F1
0x1800c34e0  cmp     qword ptr [rsp+0D60h+var_D08], r13
0x1800c34e5  jz      short loc_1800C34F1
0x1800c34e7  mov     rcx, qword ptr [rsp+0D60h+var_D08]
0x1800c34ec  call    RtlpSysVolFree
0x1800c34f1  mov     rcx, [rbp+0C60h+var_60]
0x1800c34f8  xor     rcx, rsp; StackCookie
  ... truncated ...
```
