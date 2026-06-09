# NsippProbeAndAllocateParameters

- ea: `0x1400043d0`
- end: `0x140004c41`
- name: `NsippProbeAndAllocateParameters`
- size: `2161`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x140001010`
- `0x140001880`
- `0x140002280`
- `0x140002850`
- `0x140002eb0`
- `0x1400033c0`
- `0x140003af0`
- `0x140003e20`
- `0x140005c3c`
- `0x1400060e8`

## callees

- `0x1400043d0`
- `0x140004c50`
- `0x140004ca0`
- `0x1400056e8`
- `0x140006560`

## import_xrefs

- `ntoskrnl!ExRaiseAccessViolation` at `0x1400046c8`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400046c8`
- `ntoskrnl!ProbeForRead` at `0x140004720`
- `ntoskrnl!ProbeForRead` at `0x140004720`
- `ntoskrnl!ExAllocatePool2` at `0x14000485a`
- `ntoskrnl!ExAllocatePool2` at `0x14000485a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004bff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004bff`

## pseudocode

```c
__int64 __fastcall NsippProbeAndAllocateParameters(
        const void *a1,
        unsigned int a2,
        __int64 a3,
        __m128i *a4,
        __int64 a5,
        __m128i *a6,
        __int64 a7,
        __m128i *a8,
        unsigned __int8 a9,
        unsigned int a10,
        char a11,
        __m128i *a12,
        _QWORD *a13,
        _QWORD *a14,
        unsigned int *a15,
        __int64 *a16,
        __m128i *a17,
        __int64 *a18,
        __m128i *a19,
        __int64 *a20,
        __int64 *a21,
        __int64 *a22,
        __int64 *a23,
        char **a24,
        _QWORD *a25)
{
  char *v25; // r15
  unsigned __int64 v26; // r12
  volatile void *v27; // rcx
  __m128i v28; // xmm9
  unsigned int v29; // r13d
  __m128i v30; // xmm6
  __m128i v31; // xmm7
  __m128i v32; // xmm8
  __m128i v33; // xmm0
  __m128i v34; // xmm10
  __m128i v35; // xmm11
  unsigned int v36; // ecx
  __int64 v37; // r8
  __int64 v38; // r8
  unsigned int v39; // ecx
  __int64 v40; // r8
  unsigned int v41; // ecx
  __int64 v42; // r8
  __int64 v43; // r8
  unsigned int v44; // ecx
  int v45; // edi
  unsigned int v46; // r14d
  __int64 v47; // rdi
  __int64 v48; // r8
  unsigned __int64 v49; // rax
  char *Pool2; // rax
  char *v51; // r14
  void *v52; // rcx
  __int64 v53; // rdx
  unsigned int v55; // [rsp+30h] [rbp-1A8h]
  __int64 v56; // [rsp+30h] [rbp-1A8h]
  __int64 v57; // [rsp+40h] [rbp-198h]
  __int64 v58; // [rsp+40h] [rbp-198h]
  __int64 v59; // [rsp+40h] [rbp-198h]
  __int64 v60; // [rsp+40h] [rbp-198h]
  void *Src; // [rsp+50h] [rbp-188h]
  void *Srca; // [rsp+50h] [rbp-188h]
  void *v63; // [rsp+60h] [rbp-178h]
  void *v64; // [rsp+68h] [rbp-170h]
  size_t Size; // [rsp+90h] [rbp-148h]
  void *v66; // [rsp+D0h] [rbp-108h]
  __int64 v67; // [rsp+D8h] [rbp-100h]
  __int64 v68; // [rsp+E0h] [rbp-F8h]
  __int64 v69; // [rsp+E8h] [rbp-F0h]
  __int64 v70; // [rsp+F0h] [rbp-E8h]
  __int64 v71; // [rsp+F8h] [rbp-E0h]
  __m128i v72; // [rsp+118h] [rbp-C0h]

  if ( a25 )
  {
    v25 = 0;
    *a25 = 0;
    v26 = (a2 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( a3 )
    {
      v27 = *(volatile void **)(a3 + 8);
      Src = (void *)v27;
    }
    else
    {
      v27 = 0;
      Src = 0;
    }
    if ( a4 )
      v28 = *a4;
    else
      v28 = 0;
    if ( a5 )
    {
      v64 = *(void **)(a5 + 8);
      v29 = *(_DWORD *)(a5 + 16);
      v27 = Src;
    }
    else
    {
      v64 = 0;
      v29 = 0;
    }
    if ( a6 )
    {
      v30 = *a6;
      v31 = a6[1];
      v32 = a6[2];
      v33 = *a6;
    }
    else
    {
      v31 = 0;
      v32 = 0;
      if ( a7 )
      {
        v72 = 0;
        v63 = *(void **)a7;
        v72.m128i_i64[0] = *(_QWORD *)a7;
        v55 = *(_DWORD *)(a7 + 8);
        v72.m128i_i32[2] = v55;
        v30 = v72;
LABEL_11:
        if ( a8 )
        {
          v34 = *a8;
          v35 = (__m128i)a8[1].m128i_u64[0];
        }
        else
        {
          v34 = 0;
          v35 = 0u;
        }
        if ( !v27 )
          ExRaiseAccessViolation();
        if ( a9 )
          ProbeForRead(v27, 0x18u, 1u);
        v36 = _mm_cvtsi128_si32(_mm_srli_si128(v28, 8));
        if ( a10 * (unsigned __int64)v36 > 0xFFFFFFFF )
        {
          v45 = -1073741811;
        }
        else
        {
          Size = a10 * v36;
          v57 = v26 + 24 + NsippProbeForWrite(v28.m128i_i64[0], Size, a3, a9);
          if ( a10 * (unsigned __int64)v29 > 0xFFFFFFFF )
          {
            v45 = -1073741811;
          }
          else
          {
            v58 = v57 + NsippProbeForWrite(v64, a10 * v29, v37, a9);
            v39 = _mm_cvtsi128_si32(_mm_srli_si128(v31, 8));
            if ( a10 * (unsigned __int64)v39 > 0xFFFFFFFF )
            {
              v45 = -1073741811;
            }
            else
            {
              v59 = v58 + NsippProbeForWrite(v31.m128i_i64[0], a10 * v39, v38, a9);
              v41 = _mm_cvtsi128_si32(_mm_srli_si128(v32, 8));
              if ( a10 * (unsigned __int64)v41 > 0xFFFFFFFF )
              {
                v45 = -1073741811;
              }
              else
              {
                v60 = v59 + NsippProbeForWrite(v32.m128i_i64[0], a10 * v41, v40, a9);
                if ( a10 * (unsigned __int64)v55 > 0xFFFFFFFF )
                {
                  v45 = -1073741811;
                }
                else
                {
                  v56 = v60 + NsippProbeForWrite(v63, a10 * v55, v42, a9);
                  v44 = _mm_cvtsi128_si32(v35);
                  if ( a10 * (unsigned __int64)v44 > 0xFFFFFFFF )
                  {
                    v45 = -1073741811;
                  }
                  else
                  {
                    v46 = a10 * v44;
                    v47 = NsippProbeForWrite(v34.m128i_i64[0], a10 * v44, v43, a9) + v56;
                    v66 = (void *)_mm_srli_si128(v34, 8).m128i_u64[0];
                    v49 = v47 + NsippProbeForWrite(v66, v46, v48, a9);
                    if ( v49 > 0xFFFFFFFF )
                    {
                      v45 = -1073741811;
                      goto LABEL_82;
                    }
                    Pool2 = (char *)ExAllocatePool2(65, (unsigned int)v49, 1735414606);
                    v25 = Pool2;
                    if ( !Pool2 )
                    {
                      v45 = -1073741670;
                      goto LABEL_82;
                    }
                    if ( a1 && a2 )
                    {
                      RtlCopyVolatileMemory(Pool2, a1, a2);
                      v51 = &v25[v26];
                    }
                    else
                    {
                      v51 = Pool2;
                    }
                    if ( a9 )
                      RtlCopyFromUser(v51, Src, 0x18u);
                    else
                      RtlCopyVolatileMemory(v51, Src, 0x18u);
                    Srca = v51 + 24;
                    if ( v28.m128i_i64[0] && (_DWORD)Size )
                    {
                      v52 = v51 + 24;
                      if ( a9 )
                        RtlCopyFromUser(v52, (void *)v28.m128i_i64[0], Size);
                      else
                        RtlCopyVolatileMemory(v52, (const void *)v28.m128i_i64[0], Size);
                    }
                    else
                    {
                      Srca = 0;
                    }
                    v67 = NsippCopyMemory(v64, a9);
                    v68 = NsippCopyMemory((void *)v31.m128i_i64[0], a9);
                    v69 = NsippCopyMemory((void *)v32.m128i_i64[0], a9);
                    v70 = NsippCopyMemory(v63, a9);
                    v71 = NsippCopyMemory((void *)v34.m128i_i64[0], a9);
                    v53 = NsippCopyMemory(v66, a9);
                    if ( a15 )
                      *a15 = v29;
                    v45 = 0;
                    if ( a14 )
                      *a14 = v64;
                    if ( a17 )
                    {
                      *a17 = v30;
                      a17[1] = v31;
                      a17[2] = v32;
                    }
                    if ( a12 )
                      *a12 = v28;
                    if ( a19 )
                    {
                      *a19 = v34;
                      a19[1].m128i_i64[0] = v35.m128i_i64[0];
                    }
                    if ( a13 )
                      *a13 = Srca;
                    if ( a24 )
                      *a24 = v51;
                    if ( a16 )
                      *a16 = v67;
                    if ( a22 )
                      *a22 = v68;
                    if ( a23 )
                      *a23 = v69;
                    if ( a18 )
                      *a18 = v70;
                    if ( a20 )
                      *a20 = v71;
                    if ( a21 )
                      *a21 = v53;
                  }
                }
              }
            }
          }
        }
        if ( v45 >= 0 )
        {
LABEL_79:
          *a25 = v25;
          return (unsigned int)v45;
        }
LABEL_82:
        if ( v25 )
        {
          ExFreePoolWithTag(v25, 0);
          v25 = 0;
        }
        goto LABEL_79;
      }
      v30 = 0;
      v33 = 0;
    }
    v63 = (void *)v30.m128i_i64[0];
    v55 = _mm_cvtsi128_si32(_mm_srli_si128(v33, 8));
    goto LABEL_11;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400043d0  mov     rax, rsp
0x1400043d3  mov     [rax+18h], rbx
0x1400043d7  mov     [rax+20h], rsi
0x1400043db  mov     [rax+10h], edx
0x1400043de  mov     [rax+8], rcx
0x1400043e2  push    rdi
0x1400043e3  push    r12
0x1400043e5  push    r13
0x1400043e7  push    r14
0x1400043e9  push    r15
0x1400043eb  sub     rsp, 1B0h
0x1400043f2  movaps  xmmword ptr [rax-38h], xmm6
0x1400043f6  movaps  xmmword ptr [rax-48h], xmm7
0x1400043fa  movaps  xmmword ptr [rax-58h], xmm8
0x1400043ff  movaps  xmmword ptr [rax-68h], xmm9
0x140004404  movaps  xmmword ptr [rax-78h], xmm10
0x140004409  movaps  xmmword ptr [rax-88h], xmm11
0x140004411  xor     ebx, ebx
0x140004413  mov     [rax-158h], rbx
0x14000441a  mov     [rsp+1D8h+var_160], rbx
0x14000441f  mov     [rsp+1D8h+var_180], ebx
0x140004423  mov     rax, [rsp+1D8h+arg_C0]
0x14000442b  test    rax, rax
0x14000442e  jz      loc_140004BE2
0x140004434  mov     r15d, ebx
0x140004437  mov     [rax], rbx
0x14000443a  mov     r12d, edx
0x14000443d  add     r12, 7
0x140004441  and     r12, 0FFFFFFFFFFFFFFF8h
0x140004445  mov     [rsp+1D8h+var_190], r12
0x14000444a  test    r8, r8
0x14000444d  jz      loc_14000473F
0x140004453  mov     rcx, [r8+8]; Address
0x140004457  mov     [rsp+1D8h+Src], rcx
0x14000445c  mov     [rsp+1D8h+var_158], rcx
0x140004464  test    r9, r9
0x140004467  jz      loc_14000474C
0x14000446d  movups  xmm9, xmmword ptr [r9]
0x140004471  mov     rax, [rsp+1D8h+arg_20]
0x140004479  test    rax, rax
0x14000447c  jnz     loc_1400046F4
0x140004482  mov     [rsp+1D8h+var_170], rbx
0x140004487  mov     [rsp+1D8h+var_160], rbx
0x14000448c  mov     r13d, ebx
0x14000448f  mov     [rsp+1D8h+var_180], ebx
0x140004493  mov     rax, [rsp+1D8h+arg_28]
0x14000449b  test    rax, rax
0x14000449e  jz      loc_1400046D5
0x1400044a4  movups  xmm6, xmmword ptr [rax]
0x1400044a7  movups  xmm7, xmmword ptr [rax+10h]
0x1400044ab  movups  xmm8, xmmword ptr [rax+20h]
0x1400044b0  movdqa  xmm0, xmm6
0x1400044b4  psrldq  xmm0, 8
0x1400044b9  movsd   [rsp+1D8h+var_178], xmm6
0x1400044bf  movd    dword ptr [rsp+1D8h+var_1A8], xmm0
0x1400044c5  mov     rax, [rsp+1D8h+arg_38]
0x1400044cd  test    rax, rax
0x1400044d0  jnz     loc_140004788
0x1400044d6  xorps   xmm10, xmm10
0x1400044da  movq    xmm11, rax
0x1400044df  test    rcx, rcx
0x1400044e2  jz      loc_1400046C8
0x1400044e8  movzx   esi, [rsp+1D8h+arg_40]
0x1400044f0  test    sil, sil
0x1400044f3  jnz     loc_140004715
0x1400044f9  lea     rax, [r12+18h]
0x1400044fe  mov     [rsp+1D8h+var_190], rax
0x140004503  mov     edi, [rsp+1D8h+arg_48]
0x14000450a  mov     r14d, edi
0x14000450d  movdqa  xmm0, xmm9
0x140004512  psrldq  xmm0, 8
0x140004517  movd    ecx, xmm0
0x14000451b  mov     eax, ecx
0x14000451d  imul    rax, rdi
0x140004521  mov     edx, 0FFFFFFFFh
0x140004526  cmp     rax, rdx
0x140004529  ja      loc_1400046BA
0x14000452f  imul    ecx, edi
0x140004532  mov     eax, ecx
0x140004534  mov     [rsp+1D8h+Size], rax
0x14000453c  movzx   r9d, sil
0x140004540  mov     edx, ecx
0x140004542  movsd   [rsp+1D8h+var_150], xmm9
0x14000454c  movq    rcx, xmm9
0x140004551  call    NsippProbeForWrite
0x140004556  lea     rcx, [r12+18h]
0x14000455b  add     rax, rcx
0x14000455e  mov     [rsp+1D8h+var_198], rax
0x140004563  mov     [rsp+1D8h+var_190], rax
0x140004568  mov     eax, r13d
0x14000456b  imul    rax, r14
0x14000456f  mov     ecx, 0FFFFFFFFh
0x140004574  cmp     rax, rcx
0x140004577  ja      loc_140004797
0x14000457d  mov     eax, r13d
0x140004580  imul    eax, edi
0x140004583  mov     [rsp+1D8h+var_140], rax
0x14000458b  mov     edx, eax
0x14000458d  movzx   r9d, sil
0x140004591  mov     rcx, [rsp+1D8h+var_170]
0x140004596  call    NsippProbeForWrite
0x14000459b  add     rax, [rsp+1D8h+var_198]
0x1400045a0  mov     [rsp+1D8h+var_198], rax
0x1400045a5  mov     [rsp+1D8h+var_190], rax
0x1400045aa  movdqa  xmm0, xmm7
0x1400045ae  psrldq  xmm0, 8
0x1400045b3  movd    ecx, xmm0
0x1400045b7  mov     eax, ecx
0x1400045b9  imul    rax, r14
0x1400045bd  mov     edx, 0FFFFFFFFh
0x1400045c2  cmp     rax, rdx
0x1400045c5  ja      loc_140004731
0x1400045cb  imul    ecx, edi
0x1400045ce  mov     eax, ecx
0x1400045d0  mov     [rsp+1D8h+var_138], rax
0x1400045d8  mov     edx, ecx
0x1400045da  movzx   r9d, sil
0x1400045de  movsd   [rsp+1D8h+var_130], xmm7
0x1400045e7  movq    rcx, xmm7
0x1400045ec  call    NsippProbeForWrite
0x1400045f1  add     rax, [rsp+1D8h+var_198]
0x1400045f6  mov     [rsp+1D8h+var_198], rax
0x1400045fb  mov     [rsp+1D8h+var_190], rax
0x140004600  movdqa  xmm0, xmm8
0x140004605  psrldq  xmm0, 8
0x14000460a  movd    ecx, xmm0
0x14000460e  mov     eax, ecx
0x140004610  imul    rax, r14
0x140004614  mov     edx, 0FFFFFFFFh
0x140004619  cmp     rax, rdx
0x14000461c  ja      loc_1400047A5
0x140004622  imul    ecx, edi
0x140004625  mov     eax, ecx
0x140004627  mov     [rsp+1D8h+var_128], rax
0x14000462f  mov     edx, ecx
0x140004631  movzx   r9d, sil
0x140004635  movsd   [rsp+1D8h+var_120], xmm8
0x14000463f  movq    rcx, xmm8
0x140004644  call    NsippProbeForWrite
0x140004649  add     rax, [rsp+1D8h+var_198]
0x14000464e  mov     [rsp+1D8h+var_198], rax
0x140004653  mov     [rsp+1D8h+var_190], rax
0x140004658  mov     ecx, dword ptr [rsp+1D8h+var_1A8]
0x14000465c  mov     eax, ecx
0x14000465e  imul    rax, r14
0x140004662  mov     edx, 0FFFFFFFFh
0x140004667  cmp     rax, rdx
0x14000466a  ja      loc_1400047B3
0x140004670  imul    ecx, edi
0x140004673  mov     eax, ecx
0x140004675  mov     [rsp+1D8h+var_118], rax
0x14000467d  mov     edx, ecx
0x14000467f  movzx   r9d, sil
0x140004683  mov     rcx, [rsp+1D8h+var_178]
0x140004688  call    NsippProbeForWrite
0x14000468d  add     rax, [rsp+1D8h+var_198]
0x140004692  mov     [rsp+1D8h+var_1A8], rax
0x140004697  mov     [rsp+1D8h+var_190], rax
0x14000469c  movd    ecx, xmm11
0x1400046a1  mov     eax, ecx
0x1400046a3  imul    rax, r14
0x1400046a7  mov     edx, 0FFFFFFFFh
0x1400046ac  cmp     rax, rdx
0x1400046af  ja      loc_1400047C1
0x1400046b5  jmp     loc_1400047CF
0x1400046ba  mov     edi, 0C000000Dh
0x1400046bf  mov     [rsp+1D8h+var_1A0], edi
0x1400046c3  jmp     loc_140004B4B
0x1400046c8  call    cs:__imp_ExRaiseAccessViolation
0x1400046cf  nop     dword ptr [rax+rax+00h]
0x1400046d4  int     3; Trap to Debugger
0x1400046d5  mov     rax, [rsp+1D8h+arg_30]
0x1400046dd  xorps   xmm7, xmm7
0x1400046e0  xorps   xmm8, xmm8
0x1400046e4  test    rax, rax
0x1400046e7  jnz     short loc_140004755
0x1400046e9  xorps   xmm6, xmm6
0x1400046ec  xorps   xmm0, xmm0
0x1400046ef  jmp     loc_1400044B4
0x1400046f4  mov     rcx, [rax+8]
0x1400046f8  mov     [rsp+1D8h+var_170], rcx
0x1400046fd  mov     [rsp+1D8h+var_160], rcx
0x140004702  mov     r13d, [rax+10h]
0x140004706  mov     [rsp+1D8h+var_180], r13d
0x14000470b  mov     rcx, [rsp+1D8h+Src]
0x140004710  jmp     loc_140004493
0x140004715  mov     edx, 18h; Length
0x14000471a  mov     r8d, 1; Alignment
0x140004720  call    cs:__imp_ProbeForRead
0x140004727  nop     dword ptr [rax+rax+00h]
0x14000472c  jmp     loc_1400044F9
0x140004731  mov     edi, 0C000000Dh
0x140004736  mov     [rsp+1D8h+var_1A0], edi
0x14000473a  jmp     loc_140004B4B
0x14000473f  mov     rcx, rbx
0x140004742  mov     [rsp+1D8h+Src], rbx
0x140004747  jmp     loc_14000445C
0x14000474c  xorps   xmm9, xmm9
0x140004750  jmp     loc_140004471
0x140004755  movups  [rsp+1D8h+var_C0], xmm7
0x14000475d  mov     rdx, [rax]
0x140004760  mov     [rsp+1D8h+var_178], rdx
0x140004765  mov     qword ptr [rsp+1D8h+var_C0], rdx
0x14000476d  mov     eax, [rax+8]
0x140004770  mov     dword ptr [rsp+1D8h+var_1A8], eax
0x140004774  mov     dword ptr [rsp+1D8h+var_C0+8], eax
0x14000477b  movups  xmm6, [rsp+1D8h+var_C0]
0x140004783  jmp     loc_1400044C5
0x140004788  movups  xmm10, xmmword ptr [rax]
0x14000478c  movsd   xmm11, qword ptr [rax+10h]
0x140004792  jmp     loc_1400044DF
0x140004797  mov     edi, 0C000000Dh
0x14000479c  mov     [rsp+1D8h+var_1A0], edi
0x1400047a0  jmp     loc_140004B4B
0x1400047a5  mov     edi, 0C000000Dh
0x1400047aa  mov     [rsp+1D8h+var_1A0], edi
0x1400047ae  jmp     loc_140004B4B
0x1400047b3  mov     edi, 0C000000Dh
0x1400047b8  mov     [rsp+1D8h+var_1A0], edi
0x1400047bc  jmp     loc_140004B4B
0x1400047c1  mov     edi, 0C000000Dh
0x1400047c6  mov     [rsp+1D8h+var_1A0], edi
0x1400047ca  jmp     loc_140004B4B
0x1400047cf  imul    ecx, edi
0x1400047d2  mov     r14d, ecx
0x1400047d5  mov     [rsp+1D8h+var_198], r14
0x1400047da  movzx   r9d, sil
0x1400047de  mov     edx, ecx
0x1400047e0  movsd   [rsp+1D8h+var_110], xmm10
0x1400047ea  movq    rcx, xmm10
0x1400047ef  call    NsippProbeForWrite
0x1400047f4  mov     rdi, [rsp+1D8h+var_1A8]
0x1400047f9  add     rdi, rax
0x1400047fc  mov     [rsp+1D8h+var_190], rdi
0x140004801  movzx   r9d, sil
0x140004805  mov     edx, r14d
0x140004808  movdqa  xmm0, xmm10
0x14000480d  psrldq  xmm0, 8
0x140004812  movq    [rsp+1D8h+var_108], xmm0
0x14000481b  movq    rcx, xmm0
0x140004820  call    NsippProbeForWrite
0x140004825  add     rax, rdi
0x140004828  mov     [rsp+1D8h+var_190], rax
0x14000482d  jmp     short loc_14000483F
0x14000482f  mov     edi, eax
0x140004831  mov     [rsp+1D8h+var_1A0], eax
0x140004835  xor     ebx, ebx
0x140004837  mov     r15d, ebx
0x14000483a  jmp     loc_140004B4B
0x14000483f  mov     ecx, 0FFFFFFFFh
0x140004844  cmp     rax, rcx
0x140004847  ja      loc_140004BEC
0x14000484d  mov     edx, eax
0x14000484f  mov     ecx, 41h ; 'A'
0x140004854  mov     r8d, 6770534Eh
0x14000485a  call    cs:__imp_ExAllocatePool2
0x140004861  nop     dword ptr [rax+rax+00h]
0x140004866  mov     r15, rax
0x140004869  mov     [rsp+1D8h+var_168], rax
0x14000486e  test    rax, rax
0x140004871  jz      loc_140004C13
0x140004877  mov     [rsp+1D8h+var_1A8], rax
0x14000487c  mov     rdx, [rsp+1D8h+arg_0]; Src
0x140004884  test    rdx, rdx
0x140004887  jnz     loc_140004913
0x14000488d  mov     r14, r15
0x140004890  mov     r8d, 18h; Size
0x140004896  mov     rdx, [rsp+1D8h+Src]; Src
0x14000489b  mov     rcx, r14; void *
0x14000489e  test    sil, sil
0x1400048a1  jnz     short loc_140004905
0x1400048a3  call    RtlCopyVolatileMemory
0x1400048a8  lea     rdi, [r14+18h]
0x1400048ac  mov     [rsp+1D8h+Src], rdi
0x1400048b1  mov     [rsp+1D8h+var_1A8], rdi
0x1400048b6  mov     [rsp+1D8h+var_D8], r14
0x1400048be  mov     rdx, [rsp+1D8h+var_150]; Src
0x1400048c6  test    rdx, rdx
0x1400048c9  jnz     short loc_1400048D5
0x1400048cb  mov     rdi, rbx
0x1400048ce  mov     [rsp+1D8h+Src], rbx
0x1400048d3  jmp     short loc_14000493B
0x1400048d5  mov     r12, [rsp+1D8h+Size]
0x1400048dd  test    r12d, r12d
0x1400048e0  jz      short loc_1400048CB
0x1400048e2  mov     r8, r12; Size
0x1400048e5  mov     rcx, rdi; void *
0x1400048e8  test    sil, sil
0x1400048eb  jnz     short loc_14000490C
0x1400048ed  call    RtlCopyVolatileMemory
0x1400048f2  lea     rax, [r12+7]
0x1400048f7  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400048fb  add     rax, rdi
0x1400048fe  mov     [rsp+1D8h+var_1A8], rax
0x140004903  jmp     short loc_14000493B
0x140004905  call    RtlCopyFromUser
0x14000490a  jmp     short loc_1400048A8
0x14000490c  call    RtlCopyFromUser
0x140004911  jmp     short loc_1400048F2
0x140004913  mov     eax, dword ptr [rsp+1D8h+arg_8]
  ... truncated ...
```
