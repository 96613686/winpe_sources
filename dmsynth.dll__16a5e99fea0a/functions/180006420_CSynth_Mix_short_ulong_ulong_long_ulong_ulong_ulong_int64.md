# CSynth::Mix(short * *,ulong *,ulong *,long *,ulong,ulong,ulong,__int64)

- ea: `0x180006420`
- end: `0x180006a52`
- name: `?Mix@CSynth@@QEAAXPEAPEAFPEAK1PEAJKKK_J@Z`
- size: `1586`
- prototype: `void(CSynth *__hidden this, __int16 **, unsigned int *, unsigned int *, int *, unsigned int, unsigned int, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180012da0`
- `0x180013070`

## callees

- `0x180002120`
- `0x180002580`
- `0x1800035e0`
- `0x180004120`
- `0x180004c90`
- `0x180006420`
- `0x18000c710`
- `0x18000d220`
- `0x18000e3b0`
- `0x180011ee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000644c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000644c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a4b`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800069f1`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800069f1`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180006966`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180006966`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000694d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000694d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800068fa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800068fa`

## pseudocode

```c
void __fastcall CSynth::Mix(
        CSynth *this,
        __int16 **a2,
        unsigned int *a3,
        unsigned int *a4,
        int *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        LARGE_INTEGER PerformanceCount)
{
  unsigned int TheCurrentTime; // eax
  int v14; // edx
  __int64 QuadPart; // r14
  _QWORD *v16; // rcx
  __int64 i; // rbp
  int v18; // ebx
  _QWORD *v19; // rcx
  __int64 *v20; // rcx
  bool v21; // zf
  int v22; // eax
  __int64 *v23; // r8
  __int64 *v24; // rcx
  int v25; // eax
  bool v26; // cc
  __int64 v27; // r11
  char v28; // bl
  unsigned int v29; // r8d
  __int16 *v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 j; // rdi
  CVoice *v34; // rbx
  __int64 v35; // rdx
  CVoice *v36; // rdi
  CVoice *v37; // rdx
  CVoice *v38; // r8
  CVoice *v39; // rax
  CVoice *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  int v43; // eax
  int v44; // eax
  unsigned int k; // ebx
  __int64 v46; // r9
  __int16 *v47; // rdx
  __int16 *v48; // r8
  unsigned int v49; // r10d
  char v50; // r15
  int v51; // edx
  unsigned int v52; // ecx
  __int16 *m; // r11
  __int16 *v54; // r8
  int v55; // eax
  int v56; // eax
  int PerformanceFrequency; // r8d
  __int64 v58; // rax
  __int64 v59; // r9
  __int64 v60; // r10
  __int64 v61; // r8
  _QWORD *v62; // rcx
  unsigned int v63; // r8d
  int v64; // eax
  __int64 v65; // rdx
  int v66; // ecx
  unsigned int v67; // eax
  int v68; // ecx
  __int64 v69; // xmm1_8
  __int64 v70; // [rsp+20h] [rbp-58h]
  unsigned int v71; // [rsp+A0h] [rbp+28h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  *((_QWORD *)this + 2) = a4;
  *((_QWORD *)this + 3) = a5;
  *((_QWORD *)this + 1) = a3;
  *((_DWORD *)this + 8) = a6;
  TheCurrentTime = GetTheCurrentTime();
  v14 = 0;
  QuadPart = PerformanceCount.QuadPart;
  v16 = (_QWORD *)*((_QWORD *)this + 7);
  v71 = TheCurrentTime;
  for ( i = PerformanceCount.QuadPart + a8; v16; ++v14 )
    v16 = (_QWORD *)*v16;
  v18 = *((__int16 *)this + 37) - v14;
  if ( v18 > 0 )
  {
    while ( 1 )
    {
      v19 = (_QWORD *)*((_QWORD *)this + 6);
      if ( !v19 )
        break;
      --v18;
      *((_QWORD *)this + 6) = *v19;
      *v19 = 0;
      *v19 = *((_QWORD *)this + 7);
      *((_QWORD *)this + 7) = v19;
      if ( v18 <= 0 )
        goto LABEL_27;
    }
    v20 = (__int64 *)*((_QWORD *)this + 8);
    if ( !v20 )
      goto LABEL_108;
    do
    {
      v21 = *((_DWORD *)v20 + 138) == 0;
      v22 = v18 - 1;
      v20 = (__int64 *)*v20;
      if ( v21 )
        v22 = v18;
      v18 = v22;
    }
    while ( v20 );
    if ( v22 > 0 )
    {
LABEL_108:
      do
      {
        v23 = (__int64 *)*((_QWORD *)this + 8);
        if ( !v23 )
          break;
        v24 = (__int64 *)*v23;
        if ( *v23 )
        {
          do
          {
            if ( !*((_DWORD *)v24 + 138) )
            {
              if ( *((_DWORD *)v23 + 138) )
                goto LABEL_23;
              if ( *((_DWORD *)v24 + 145) <= *((_DWORD *)v23 + 145) )
              {
                v25 = *((_DWORD *)v23 + 137);
                if ( *((_DWORD *)v24 + 137) )
                {
                  if ( !v25 )
                    goto LABEL_24;
                  v26 = v23[65] <= v24[65];
                }
                else
                {
                  if ( v25 )
                    goto LABEL_23;
                  v26 = *((_DWORD *)v23 + 139) <= *((_DWORD *)v24 + 139);
                }
                if ( !v26 )
LABEL_23:
                  v23 = v24;
              }
            }
LABEL_24:
            v24 = (__int64 *)*v24;
          }
          while ( v24 );
        }
        if ( *((_DWORD *)v23 + 138) )
          break;
        CVoice::QuickStopVoice((CVoice *)v23, i);
        ++*((_DWORD *)this + 24);
        --v18;
      }
      while ( v18 > 0 );
    }
  }
LABEL_27:
  v27 = 0;
  if ( a6 )
  {
    v28 = a7 & 1;
    do
    {
      if ( (a7 & 1) != 0 && (_DWORD)v27 )
        break;
      v29 = a8 << v28;
      if ( a8 << v28 )
      {
        v30 = a2[v27];
        v31 = 0;
        if ( v29 < 4 )
          goto LABEL_109;
        if ( v29 < 0x20 )
          goto LABEL_110;
        do
        {
          *(__m128i *)&v30[v31] = _mm_slli_epi16(_mm_loadu_si128((const __m128i *)&v30[v31]), 1u);
          *(__m128i *)&v30[(unsigned int)(v31 + 8)] = _mm_slli_epi16(
                                                        _mm_loadu_si128((const __m128i *)&v30[(unsigned int)(v31 + 8)]),
                                                        1u);
          *(__m128i *)&v30[(unsigned int)(v31 + 16)] = _mm_slli_epi16(
                                                         _mm_loadu_si128((const __m128i *)&v30[(unsigned int)(v31 + 16)]),
                                                         1u);
          v32 = (unsigned int)(v31 + 24);
          v31 = (unsigned int)(v31 + 32);
          *(__m128i *)&v30[v32] = _mm_slli_epi16(_mm_loadu_si128((const __m128i *)&v30[v32]), 1u);
        }
        while ( (unsigned int)v31 < (v29 & 0xFFFFFFE0) );
        if ( (v29 & 0x1F) >= 4 )
        {
LABEL_110:
          do
          {
            *(_QWORD *)&v30[v31] = _mm_slli_epi16(_mm_loadl_epi64((const __m128i *)&v30[v31]), 1u).m128i_u64[0];
            v31 = (unsigned int)(v31 + 4);
          }
          while ( (unsigned int)v31 < (v29 & 0xFFFFFFFC) );
        }
        if ( (unsigned int)v31 < v29 )
        {
LABEL_109:
          do
          {
            v30[v31] *= 2;
            v31 = (unsigned int)(v31 + 1);
          }
          while ( (unsigned int)v31 < v29 );
        }
      }
      v27 = (unsigned int)(v27 + 1);
    }
    while ( (unsigned int)v27 < a6 );
  }
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 260); j = (unsigned int)(j + 1) )
  {
    CControlLogic::QueueNotes(*(CControlLogic **)(*((_QWORD *)this + 129) + 8 * j), QuadPart, i);
    CControlLogic::QueueWaves(*(CControlLogic **)(*((_QWORD *)this + 129) + 8 * j), i);
  }
  v34 = (CVoice *)*((_QWORD *)this + 8);
  if ( v34 )
  {
    do
    {
      v35 = *((_QWORD *)v34 + 67);
      if ( v35 && v35 < i )
        CVoice::StopVoice(v34, v35);
      v36 = *(CVoice **)v34;
      CVoice::Mix(v34, a2, a7, a8, QuadPart, i);
      if ( !*((_DWORD *)v34 + 136) )
      {
        v37 = (CVoice *)*((_QWORD *)this + 8);
        if ( v34 == v37 )
        {
          v37 = *(CVoice **)v37;
        }
        else
        {
          v38 = 0;
          v39 = (CVoice *)*((_QWORD *)this + 8);
          if ( v37 )
          {
            while ( 1 )
            {
              v40 = *(CVoice **)v39;
              if ( v39 == v34 )
                break;
              v38 = v39;
              v39 = *(CVoice **)v39;
              if ( !v40 )
                goto LABEL_54;
            }
            *(_QWORD *)v38 = v40;
            *(_QWORD *)v39 = 0;
          }
        }
LABEL_54:
        *((_QWORD *)this + 8) = v37;
        *(_QWORD *)v34 = *((_QWORD *)this + 6);
        *((_QWORD *)this + 6) = v34;
        v41 = *((_QWORD *)this + 10);
        v42 = *((_QWORD *)v34 + 65);
        v43 = *((_DWORD *)v34 + 132);
        if ( v42 >= v41 )
          v44 = v43 - v42;
        else
          v44 = v43 - v41;
        *((_DWORD *)this + 23) += v44;
      }
      v34 = v36;
    }
    while ( v36 );
  }
  for ( k = 0; k < *((_DWORD *)this + 260); ++k )
    CControlLogic::ClearMIDI(*(CControlLogic **)(*((_QWORD *)this + 129) + 8LL * k), i);
  if ( *((_DWORD *)this + 34) )
  {
    v46 = *((_QWORD *)this + 19);
    if ( v46 )
    {
      if ( *((_QWORD *)this + 18) && (a7 & 2) == 0 )
      {
        v47 = *a2;
        v70 = *((_QWORD *)this + 18);
        v48 = *a2;
        if ( (a7 & 1) != 0 )
          SVerbStereoToStereoShort(a8, (_DWORD)v47, (_DWORD)v48, v46, v70);
        else
          SVerbMonoToMonoShort(a8, (_DWORD)v47, (_DWORD)v48, v46, v70);
      }
    }
  }
  v49 = 0;
  if ( a6 )
  {
    v50 = a7 & 1;
    do
    {
      if ( (a7 & 1) != 0 && v49 )
        break;
      v51 = *((_DWORD *)this + 27);
      v52 = 0;
      for ( m = a2[v49]; v52 < a8 << v50; ++v52 )
      {
        v54 = &m[v52];
        v55 = 2 * *v54;
        if ( v55 >= -32767 )
        {
          if ( v55 > 0x7FFF )
            v55 = 0x7FFF;
        }
        else
        {
          v55 = -32767;
        }
        *v54 = v55;
        if ( v55 <= v51 )
        {
          if ( v55 < 0 )
          {
            v56 = -v55;
            if ( v56 > v51 )
              v51 = v56;
          }
        }
        else
        {
          v51 = v55;
        }
      }
      ++v49;
      *((_DWORD *)this + 27) = v51;
    }
    while ( v49 < a6 );
  }
  if ( i > *((_QWORD *)this + 5) )
    *((_QWORD *)this + 5) = i;
  if ( dword_18001E5B8 )
  {
    dword_18001E5B8 = 0;
    PerformanceFrequency = QueryPerformanceFrequency(&Frequency);
    dword_18002011C = PerformanceFrequency;
    Frequency.QuadPart /= 1000LL;
  }
  else
  {
    PerformanceFrequency = dword_18002011C;
  }
  if ( PerformanceFrequency )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v58 = PerformanceCount.QuadPart / Frequency.QuadPart;
  }
  else
  {
    LODWORD(v58) = timeGetTime();
  }
  *((_DWORD *)this + 22) += v58 - v71;
  v59 = *((_QWORD *)this + 10);
  v60 = *((unsigned int *)this + 52);
  v61 = *((_QWORD *)this + 5);
  if ( v59 + v60 <= v61 )
  {
    v62 = (_QWORD *)*((_QWORD *)this + 8);
    v63 = v61 - v59;
    if ( v62 )
    {
      v64 = *((_DWORD *)this + 23);
      do
      {
        v65 = v62[65];
        if ( v65 >= v59 )
          v64 = *((_DWORD *)this + 10) + v64 - v65;
        else
          v64 += v63;
        *((_DWORD *)this + 23) = v64;
        v62 = (_QWORD *)*v62;
      }
      while ( v62 );
    }
    v66 = 1;
    if ( !v63 )
      v63 = 1;
    if ( *((_DWORD *)this + 23) )
      v66 = *((_DWORD *)this + 23);
    else
      *((_DWORD *)this + 23) = 1;
    v67 = v66 + (v63 >> 1);
    v68 = *((_DWORD *)this + 22);
    *((_DWORD *)this + 25) = v67 / v63;
    *((_DWORD *)this + 26) = MulDiv(v68, v60, v63);
    v69 = *((_QWORD *)this + 13);
    *((_OWORD *)this + 7) = *(_OWORD *)((char *)this + 88);
    *((_QWORD *)this + 16) = v69;
    *(_OWORD *)((char *)this + 88) = 0;
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 10) = *((_QWORD *)this + 5);
  }
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
}

```

## disassembly

```asm
0x180006420  push    rbx
0x180006422  push    rbp
0x180006423  push    rsi
0x180006424  push    rdi
0x180006425  push    r12
0x180006427  push    r13
0x180006429  push    r14
0x18000642b  push    r15
0x18000642d  sub     rsp, 38h
0x180006431  mov     r15d, [rsp+78h+arg_30]
0x180006439  mov     rsi, rcx
0x18000643c  add     rcx, 418h; lpCriticalSection
0x180006443  mov     rdi, r9
0x180006446  mov     rbx, r8
0x180006449  mov     r13, rdx
0x18000644c  call    cs:__imp_EnterCriticalSection
0x180006452  mov     rax, [rsp+78h+arg_20]
0x18000645a  mov     [rsi+10h], rdi
0x18000645e  mov     edi, [rsp+78h+arg_28]
0x180006465  mov     [rsi+18h], rax
0x180006469  mov     [rsi+8], rbx
0x18000646d  mov     [rsi+20h], edi
0x180006470  call    ?GetTheCurrentTime@@YAKXZ; GetTheCurrentTime(void)
0x180006475  mov     r12d, [rsp+78h+arg_38]
0x18000647d  xor     edx, edx
0x18000647f  mov     r14, qword ptr [rsp+78h+PerformanceCount]
0x180006487  mov     rcx, [rsi+38h]
0x18000648b  mov     dword ptr [rsp+78h+arg_20], eax
0x180006492  lea     rbp, [r14+r12]
0x180006496  test    rcx, rcx
0x180006499  jz      short loc_1800064AA
0x18000649b  nop     dword ptr [rax+rax+00h]
0x1800064a0  mov     rcx, [rcx]
0x1800064a3  inc     edx
0x1800064a5  test    rcx, rcx
0x1800064a8  jnz     short loc_1800064A0
0x1800064aa  movsx   ebx, word ptr [rsi+4Ah]
0x1800064ae  sub     ebx, edx
0x1800064b0  test    ebx, ebx
0x1800064b2  jle     loc_1800065BB
0x1800064b8  nop     dword ptr [rax+rax+00000000h]
0x1800064c0  mov     rcx, [rsi+30h]
0x1800064c4  test    rcx, rcx
0x1800064c7  jz      short loc_1800064ED
0x1800064c9  mov     rax, [rcx]
0x1800064cc  dec     ebx
0x1800064ce  mov     [rsi+30h], rax
0x1800064d2  mov     qword ptr [rcx], 0
0x1800064d9  mov     rax, [rsi+38h]
0x1800064dd  mov     [rcx], rax
0x1800064e0  mov     [rsi+38h], rcx
0x1800064e4  test    ebx, ebx
0x1800064e6  jg      short loc_1800064C0
0x1800064e8  jmp     loc_1800065BB
0x1800064ed  mov     rcx, [rsi+40h]
0x1800064f1  test    rcx, rcx
0x1800064f4  jz      short loc_180006520
0x1800064f6  nop     word ptr [rax+rax+00000000h]
0x180006500  cmp     dword ptr [rcx+228h], 0
0x180006507  lea     eax, [rbx-1]
0x18000650a  mov     rcx, [rcx]
0x18000650d  cmovz   eax, ebx
0x180006510  mov     ebx, eax
0x180006512  test    rcx, rcx
0x180006515  jnz     short loc_180006500
0x180006517  test    eax, eax
0x180006519  jle     loc_1800065BB
0x18000651f  nop
0x180006520  mov     r8, [rsi+40h]
0x180006524  test    r8, r8
0x180006527  jz      loc_1800065BB
0x18000652d  mov     rcx, [r8]
0x180006530  test    rcx, rcx
0x180006533  jz      short loc_180006599
0x180006535  cmp     dword ptr [rcx+228h], 0
0x18000653c  jnz     short loc_180006591
0x18000653e  cmp     dword ptr [r8+228h], 0
0x180006546  jnz     short loc_18000658E
0x180006548  mov     eax, [r8+244h]
0x18000654f  cmp     [rcx+244h], eax
0x180006555  ja      short loc_180006591
0x180006557  cmp     dword ptr [rcx+224h], 0
0x18000655e  mov     eax, [r8+224h]
0x180006565  jz      short loc_18000657B
0x180006567  test    eax, eax
0x180006569  jz      short loc_180006591
0x18000656b  mov     rax, [rcx+208h]
0x180006572  cmp     [r8+208h], rax
0x180006579  jmp     short loc_18000658C
0x18000657b  test    eax, eax
0x18000657d  jnz     short loc_18000658E
0x18000657f  mov     eax, [rcx+22Ch]
0x180006585  cmp     [r8+22Ch], eax
0x18000658c  jle     short loc_180006591
0x18000658e  mov     r8, rcx
0x180006591  mov     rcx, [rcx]
0x180006594  test    rcx, rcx
0x180006597  jnz     short loc_180006535
0x180006599  cmp     dword ptr [r8+228h], 0
0x1800065a1  jnz     short loc_1800065BB
0x1800065a3  mov     rdx, rbp; __int64
0x1800065a6  mov     rcx, r8; this
0x1800065a9  call    ?QuickStopVoice@CVoice@@QEAAX_J@Z; CVoice::QuickStopVoice(__int64)
0x1800065ae  inc     dword ptr [rsi+60h]
0x1800065b1  dec     ebx
0x1800065b3  test    ebx, ebx
0x1800065b5  jg      loc_180006520
0x1800065bb  xor     r11d, r11d
0x1800065be  test    edi, edi
0x1800065c0  jz      loc_1800066A9
0x1800065c6  mov     ebx, r15d
0x1800065c9  and     ebx, 1
0x1800065cc  nop     dword ptr [rax+00h]
0x1800065d0  test    ebx, ebx
0x1800065d2  jz      short loc_1800065DD
0x1800065d4  test    r11d, r11d
0x1800065d7  jnz     loc_1800066A9
0x1800065dd  mov     ecx, ebx
0x1800065df  mov     r8d, r12d
0x1800065e2  shl     r8d, cl
0x1800065e5  test    r8d, r8d
0x1800065e8  jz      loc_18000669D
0x1800065ee  mov     r9, [r13+r11*8+0]
0x1800065f3  xor     edx, edx
0x1800065f5  cmp     r8d, 4
0x1800065f9  jb      loc_180006691
0x1800065ff  cmp     r8d, 20h ; ' '
0x180006603  jb      short loc_18000666E
0x180006605  mov     r10d, r8d
0x180006608  and     r10d, 0FFFFFFE0h
0x18000660c  nop     dword ptr [rax+00h]
0x180006610  movdqu  xmm0, xmmword ptr [r9+rdx*2]
0x180006616  lea     eax, [rdx+8]
0x180006619  psllw   xmm0, 1
0x18000661e  movdqu  xmmword ptr [r9+rdx*2], xmm0
0x180006624  movdqu  xmm0, xmmword ptr [r9+rax*2]
0x18000662a  psllw   xmm0, 1
0x18000662f  movdqu  xmmword ptr [r9+rax*2], xmm0
0x180006635  lea     eax, [rdx+10h]
0x180006638  movdqu  xmm0, xmmword ptr [r9+rax*2]
0x18000663e  psllw   xmm0, 1
0x180006643  movdqu  xmmword ptr [r9+rax*2], xmm0
0x180006649  lea     eax, [rdx+18h]
0x18000664c  add     edx, 20h ; ' '
0x18000664f  movdqu  xmm0, xmmword ptr [r9+rax*2]
0x180006655  psllw   xmm0, 1
0x18000665a  movdqu  xmmword ptr [r9+rax*2], xmm0
0x180006660  cmp     edx, r10d
0x180006663  jb      short loc_180006610
0x180006665  mov     eax, r8d
0x180006668  and     al, 1Fh
0x18000666a  cmp     al, 4
0x18000666c  jb      short loc_18000668C
0x18000666e  mov     ecx, r8d
0x180006671  and     ecx, 0FFFFFFFCh
0x180006674  movq    xmm0, qword ptr [r9+rdx*2]
0x18000667a  psllw   xmm0, 1
0x18000667f  movq    qword ptr [r9+rdx*2], xmm0
0x180006685  add     edx, 4
0x180006688  cmp     edx, ecx
0x18000668a  jb      short loc_180006674
0x18000668c  cmp     edx, r8d
0x18000668f  jnb     short loc_18000669D
0x180006691  shl     word ptr [r9+rdx*2], 1
0x180006696  inc     edx
0x180006698  cmp     edx, r8d
0x18000669b  jb      short loc_180006691
0x18000669d  inc     r11d
0x1800066a0  cmp     r11d, edi
0x1800066a3  jb      loc_1800065D0
0x1800066a9  xor     edi, edi
0x1800066ab  cmp     [rsi+410h], edi
0x1800066b1  jbe     short loc_1800066FB
0x1800066b3  nop     dword ptr [rax+00h]
0x1800066b7  nop     word ptr [rax+rax+00000000h]
0x1800066c0  mov     rcx, [rsi+408h]
0x1800066c7  lea     rbx, ds:0[rdi*8]
0x1800066cf  mov     r8, rbp; __int64
0x1800066d2  mov     rdx, r14; __int64
0x1800066d5  mov     rcx, [rcx+rbx]; this
0x1800066d9  call    ?QueueNotes@CControlLogic@@QEAAX_J0@Z; CControlLogic::QueueNotes(__int64,__int64)
0x1800066de  mov     rcx, [rsi+408h]
0x1800066e5  mov     rdx, rbp; __int64
0x1800066e8  mov     rcx, [rcx+rbx]; this
0x1800066ec  call    ?QueueWaves@CControlLogic@@QEAAX_J@Z; CControlLogic::QueueWaves(__int64)
0x1800066f1  inc     edi
0x1800066f3  cmp     edi, [rsi+410h]
0x1800066f9  jb      short loc_1800066C0
0x1800066fb  mov     rbx, [rsi+40h]
0x1800066ff  test    rbx, rbx
0x180006702  jz      loc_1800067CF
0x180006708  nop     dword ptr [rax+rax+00000000h]
0x180006710  mov     rdx, [rbx+218h]; __int64
0x180006717  test    rdx, rdx
0x18000671a  jz      short loc_180006729
0x18000671c  cmp     rdx, rbp
0x18000671f  jge     short loc_180006729
0x180006721  mov     rcx, rbx; this
0x180006724  call    ?StopVoice@CVoice@@QEAAX_J@Z; CVoice::StopVoice(__int64)
0x180006729  mov     rdi, [rbx]
0x18000672c  mov     r9d, r12d; unsigned int
0x18000672f  mov     [rsp+78h+var_50], rbp; __int64
0x180006734  mov     r8d, r15d; unsigned int
0x180006737  mov     rdx, r13; __int16 **
0x18000673a  mov     [rsp+78h+var_58], r14; __int64
0x18000673f  mov     rcx, rbx; this
0x180006742  call    ?Mix@CVoice@@QEAAKPEAPEAFKK_J1@Z; CVoice::Mix(short * *,ulong,ulong,__int64,__int64)
0x180006747  cmp     dword ptr [rbx+220h], 0
0x18000674e  jnz     short loc_1800067C3
0x180006750  mov     rdx, [rsi+40h]
0x180006754  cmp     rbx, rdx
0x180006757  jnz     short loc_18000675E
0x180006759  mov     rdx, [rdx]
0x18000675c  jmp     short loc_18000678F
0x18000675e  xor     r8d, r8d
0x180006761  mov     rax, rdx
0x180006764  test    rdx, rdx
0x180006767  jz      short loc_18000678F
0x180006769  nop     dword ptr [rax+00000000h]
0x180006770  mov     rcx, [rax]
0x180006773  cmp     rax, rbx
0x180006776  jz      short loc_180006785
0x180006778  mov     r8, rax
0x18000677b  mov     rax, rcx
0x18000677e  test    rcx, rcx
0x180006781  jnz     short loc_180006770
0x180006783  jmp     short loc_18000678F
0x180006785  mov     [r8], rcx
0x180006788  mov     qword ptr [rax], 0
0x18000678f  mov     [rsi+40h], rdx
0x180006793  mov     rax, [rsi+30h]
0x180006797  mov     [rbx], rax
0x18000679a  mov     [rsi+30h], rbx
0x18000679e  mov     rdx, [rsi+50h]
0x1800067a2  mov     r8, [rbx+208h]
0x1800067a9  mov     ecx, [rsi+5Ch]
0x1800067ac  mov     eax, [rbx+210h]
0x1800067b2  cmp     r8, rdx
0x1800067b5  jge     short loc_1800067BB
0x1800067b7  sub     eax, edx
0x1800067b9  jmp     short loc_1800067BE
0x1800067bb  sub     eax, r8d
0x1800067be  add     eax, ecx
0x1800067c0  mov     [rsi+5Ch], eax
0x1800067c3  mov     rbx, rdi
0x1800067c6  test    rdi, rdi
0x1800067c9  jnz     loc_180006710
0x1800067cf  xor     r14d, r14d
0x1800067d2  mov     ebx, r14d
0x1800067d5  cmp     [rsi+410h], r14d
0x1800067dc  jbe     short loc_1800067FF
0x1800067de  xchg    ax, ax
0x1800067e0  mov     rcx, [rsi+408h]
0x1800067e7  mov     rdx, rbp; __int64
0x1800067ea  mov     eax, ebx
0x1800067ec  mov     rcx, [rcx+rax*8]; this
0x1800067f0  call    ?ClearMIDI@CControlLogic@@QEAAX_J@Z; CControlLogic::ClearMIDI(__int64)
0x1800067f5  inc     ebx
0x1800067f7  cmp     ebx, [rsi+410h]
0x1800067fd  jb      short loc_1800067E0
0x1800067ff  cmp     [rsi+88h], r14d
0x180006806  jz      short loc_180006847
0x180006808  mov     r9, [rsi+98h]
0x18000680f  test    r9, r9
0x180006812  jz      short loc_180006847
0x180006814  mov     rax, [rsi+90h]
0x18000681b  test    rax, rax
0x18000681e  jz      short loc_180006847
0x180006820  test    r15b, 2
0x180006824  jnz     short loc_180006847
0x180006826  mov     rdx, [r13+0]
0x18000682a  mov     ecx, r12d
0x18000682d  mov     [rsp+78h+var_58], rax
0x180006832  mov     r8, rdx
0x180006835  test    r15b, 1
0x180006839  jz      short loc_180006842
0x18000683b  call    SVerbStereoToStereoShort
0x180006840  jmp     short loc_180006847
0x180006842  call    SVerbMonoToMonoShort
0x180006847  mov     ebx, [rsp+78h+arg_28]
0x18000684e  mov     r10d, r14d
0x180006851  test    ebx, ebx
0x180006853  jz      loc_1800068D9
0x180006859  and     r15d, 1
0x18000685d  mov     edi, 7FFFh
0x180006862  test    r15d, r15d
0x180006865  jz      short loc_18000686C
0x180006867  test    r10d, r10d
0x18000686a  jnz     short loc_1800068D9
0x18000686c  mov     edx, [rsi+6Ch]
0x18000686f  mov     ecx, r15d
0x180006872  mov     eax, r10d
0x180006875  mov     r9d, r12d
0x180006878  shl     r9d, cl
0x18000687b  mov     ecx, r14d
0x18000687e  mov     r11, [r13+rax*8+0]
0x180006883  test    r9d, r9d
0x180006886  jz      short loc_1800068CE
0x180006888  nop     dword ptr [rax+rax+00000000h]
0x180006890  mov     eax, ecx
  ... truncated ...
```
