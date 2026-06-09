# LdrpLogEtwDllSearchResults

- ea: `0x1800beda8`
- end: `0x1800bf2a5`
- name: `LdrpLogEtwDllSearchResults`
- size: `1277`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x1800be2e0`

## callees

- `0x1800165d0`
- `0x18001861c`
- `0x18001b984`
- `0x18001d490`
- `0x1800526f0`
- `0x18005ef80`
- `0x1800beda8`
- `0x1800bf420`
- `0x18011e75c`
- `0x18015ee80`
- `0x180162000`

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
0x1800beda8  mov     rax, rsp
0x1800bedab  push    rbp
0x1800bedac  push    rbx
0x1800bedad  push    rsi
0x1800bedae  push    rdi
0x1800bedaf  push    r12
0x1800bedb1  push    r13
0x1800bedb3  push    r14
0x1800bedb5  push    r15
0x1800bedb7  lea     rbp, [rax-0C68h]
0x1800bedbe  sub     rsp, 0D28h
0x1800bedc5  movaps  xmmword ptr [rax-58h], xmm6
0x1800bedc9  mov     rax, cs:__security_cookie
0x1800bedd0  xor     rax, rsp
0x1800bedd3  mov     [rbp+0C60h+var_60], rax
0x1800bedda  mov     r14d, ecx
0x1800beddd  xorps   xmm0, xmm0
0x1800bede0  mov     rcx, gs:60h
0x1800bede9  mov     rsi, rdx
0x1800bedec  xorps   xmm1, xmm1
0x1800bedef  xor     r13d, r13d
0x1800bedf2  xor     edx, edx
0x1800bedf4  mov     [rsp+0D60h+var_D40], r13d
0x1800bedf9  mov     r8d, 248h
0x1800bedff  xorps   xmm6, xmm6
0x1800bee02  mov     rcx, [rcx+30h]
0x1800bee06  movups  [rsp+0D60h+var_D38+8], xmm0
0x1800bee0b  movups  [rsp+0D60h+var_D18+8], xmm0
0x1800bee10  movups  [rsp+0D60h+var_D28+8], xmm1
0x1800bee15  call    RtlAllocateHeap_0
0x1800bee1a  mov     rbx, rax
0x1800bee1d  test    rax, rax
0x1800bee20  jz      loc_1800BF211
0x1800bee26  mov     word ptr [rax+6], 14D4h
0x1800bee2c  lea     r9, [rsp+0D60h+var_D40]
0x1800bee31  mov     ecx, [rsi+20h]
0x1800bee34  mov     r8d, 214h
0x1800bee3a  mov     [rax+20h], ecx
0x1800bee3d  mov     rcx, [rsi+10h]
0x1800bee41  mov     edx, [rcx+18h]
0x1800bee44  mov     [rax+24h], edx
0x1800bee47  lea     rdx, [rax+30h]
0x1800bee4b  mov     [rax+28h], r14d
0x1800bee4f  mov     ecx, [rsi+24h]
0x1800bee52  mov     [rax+2Ch], ecx
0x1800bee55  mov     rcx, rsi
0x1800bee58  call    LdrpEventAddUnicodeString
0x1800bee5d  mov     edi, [rsp+0D60h+var_D40]
0x1800bee61  call    RtlGetCurrentServiceSessionId
0x1800bee66  test    eax, eax
0x1800bee68  jz      loc_1800BF23D
0x1800bee6e  mov     rax, gs:60h
0x1800bee77  mov     rcx, [rax+90h]
0x1800bee7e  add     rcx, 22Ah
0x1800bee85  movzx   ecx, byte ptr [rcx]
0x1800bee88  lea     r8d, [rdi+10h]
0x1800bee8c  mov     r9, rbx
0x1800bee8f  mov     edx, 402h
0x1800bee94  call    NtTraceEvent
0x1800bee99  mov     rcx, gs:60h
0x1800beea2  mov     r8, rbx
0x1800beea5  xor     edx, edx
0x1800beea7  mov     rcx, [rcx+30h]
0x1800beeab  call    RtlFreeHeap_0
0x1800beeb0  bt      r14d, 8
0x1800beeb5  jnb     loc_1800BF211
0x1800beebb  xorps   xmm0, xmm0
0x1800beebe  lea     rdx, [rbp+0C60h+var_CE0]
0x1800beec2  mov     ebx, 0C78h
0x1800beec7  mov     ecx, ebx
0x1800beec9  movups  [rsp+0D60h+var_D08+8], xmm0
0x1800beece  call    RtlGetCurrentDirectory_U
0x1800beed3  test    eax, eax
0x1800beed5  jz      loc_1800BF211
0x1800beedb  lea     rdx, [rbp+0C60h+var_CE0]
0x1800beedf  lea     rcx, [rsp+0D60h+var_D08+8]
0x1800beee4  call    RtlCreateUnicodeString
0x1800beee9  test    al, al
0x1800beeeb  jz      short loc_1800BEEF2
0x1800beeed  movaps  xmm6, [rsp+0D60h+var_D08+8]
0x1800beef2  mov     rcx, [rsi+10h]
0x1800beef6  lea     r8, [rsp+0D60h+var_D38+8]
0x1800beefb  mov     edi, 1
0x1800bef00  mov     edx, edi
0x1800bef02  call    LdrpMakeUnicodeStringFromPathElement
0x1800bef07  mov     rcx, [rsi+10h]
0x1800bef0b  lea     r8, [rsp+0D60h+var_D18+8]
0x1800bef10  xor     edx, edx
0x1800bef12  mov     [rsp+0D60h+var_D40], eax
0x1800bef16  mov     r15d, eax
0x1800bef19  call    LdrpMakeUnicodeStringFromPathElement
0x1800bef1e  mov     rcx, [rsi+10h]
0x1800bef22  lea     r8, [rsp+0D60h+var_D28+8]
0x1800bef27  lea     edx, [rdi+4]
0x1800bef2a  mov     [rsp+0D60h+var_D3C], eax
0x1800bef2e  mov     r12d, eax
0x1800bef31  call    LdrpMakeUnicodeStringFromPathElement
0x1800bef36  mov     rcx, gs:60h
0x1800bef3f  xor     edx, edx
0x1800bef41  mov     r8d, 0CA0h
0x1800bef47  mov     dword ptr [rsp+0D60h+var_D38], eax
0x1800bef4b  mov     esi, eax
0x1800bef4d  mov     rcx, [rcx+30h]
0x1800bef51  call    RtlAllocateHeap_0
0x1800bef56  mov     [rsp+0D60h+var_CF0], rax
0x1800bef5b  movdqa  xmm0, xmm6
0x1800bef5f  psrldq  xmm0, 8
0x1800bef64  movq    rdx, xmm0
0x1800bef69  mov     qword ptr [rsp+0D60h+var_D08+8], rdx
0x1800bef6e  test    rax, rax
0x1800bef71  jz      loc_1800BF1C3
0x1800bef77  mov     word ptr [rax+6], 14D5h
0x1800bef7d  lea     r11, [rax+24h]
0x1800bef81  mov     [rax+20h], r14d
0x1800bef85  mov     r12d, 7FFFFFFEh
0x1800bef8b  movd    eax, xmm6
0x1800bef8f  test    ax, ax
0x1800bef92  jz      loc_1800BF28A
0x1800bef98  mov     r10, rdx
0x1800bef9b  mov     ecx, r12d
0x1800bef9e  lea     edx, [rdi+1]
0x1800befa1  mov     r8d, 63Ch
0x1800befa7  mov     rax, r11
0x1800befaa  mov     r9, r13
0x1800befad  test    rcx, rcx
0x1800befb0  jz      short loc_1800BEFCF
0x1800befb2  movzx   esi, word ptr [r10]
0x1800befb6  test    si, si
0x1800befb9  jz      short loc_1800BEFCF
0x1800befbb  mov     [rax], si
0x1800befbe  add     r10, rdx
0x1800befc1  add     rax, rdx
0x1800befc4  sub     rcx, rdi
0x1800befc7  add     r9, rdi
0x1800befca  sub     r8, rdi
0x1800befcd  jnz     short loc_1800BEFAD
0x1800befcf  lea     rcx, [rax-2]
0x1800befd3  test    r8, r8
0x1800befd6  cmovnz  rcx, rax
0x1800befda  lea     eax, [r9-1]
0x1800befde  cmovnz  eax, r9d
0x1800befe2  mov     [rcx], r13w
0x1800befe6  lea     r14d, ds:2[rax*2]
0x1800befee  mov     eax, r14d
0x1800beff1  sub     ebx, r14d
0x1800beff4  shr     rax, 1
0x1800beff7  lea     r15, [r11+rax*2]
0x1800beffb  cmp     word ptr [rsp+0D60h+var_D38+8], r13w
0x1800bf001  jz      loc_1800BF247
0x1800bf007  mov     r8d, ebx
0x1800bf00a  mov     r10, r13
0x1800bf00d  shr     r8, 1
0x1800bf010  jz      short loc_1800BF05F
0x1800bf012  mov     r9, qword ptr [rsp+0D60h+var_D28]
0x1800bf017  mov     r10, r8
0x1800bf01a  mov     rcx, r12
0x1800bf01d  mov     rax, r15
0x1800bf020  mov     r11, r13
0x1800bf023  test    rcx, rcx
0x1800bf026  jz      short loc_1800BF045
0x1800bf028  movzx   esi, word ptr [r9]
0x1800bf02c  test    si, si
0x1800bf02f  jz      short loc_1800BF045
0x1800bf031  mov     [rax], si
0x1800bf034  add     r9, rdx
0x1800bf037  add     rax, rdx
0x1800bf03a  sub     rcx, rdi
0x1800bf03d  add     r11, rdi
0x1800bf040  sub     r8, rdi
0x1800bf043  jnz     short loc_1800BF023
0x1800bf045  test    r8, r8
0x1800bf048  lea     rcx, [rax-2]
0x1800bf04c  cmovnz  rcx, rax
0x1800bf050  lea     rax, [r11-1]
0x1800bf054  cmovnz  rax, r11
0x1800bf058  sub     r10, rax
0x1800bf05b  mov     [rcx], r13w
0x1800bf05f  mov     eax, edi
0x1800bf061  sub     eax, r10d
0x1800bf064  lea     ecx, [rbx+rax*2]
0x1800bf067  mov     eax, ecx
0x1800bf069  lea     r13d, [rcx+r14]
0x1800bf06d  shr     rax, 1
0x1800bf070  sub     ebx, ecx
0x1800bf072  lea     r14, [r15+rax*2]
0x1800bf076  xor     r15d, r15d
0x1800bf079  cmp     word ptr [rsp+0D60h+var_D18+8], r15w
0x1800bf07f  jz      loc_1800BF25E
0x1800bf085  mov     r8d, ebx
0x1800bf088  mov     r10d, r15d
0x1800bf08b  shr     r8, 1
0x1800bf08e  jz      short loc_1800BF0DD
0x1800bf090  mov     r9, qword ptr [rsp+0D60h+var_D08]
0x1800bf095  mov     r10, r8
0x1800bf098  mov     rcx, r12
0x1800bf09b  mov     rax, r14
0x1800bf09e  mov     r11d, r15d
0x1800bf0a1  test    rcx, rcx
0x1800bf0a4  jz      short loc_1800BF0C3
0x1800bf0a6  movzx   esi, word ptr [r9]
0x1800bf0aa  test    si, si
0x1800bf0ad  jz      short loc_1800BF0C3
0x1800bf0af  mov     [rax], si
0x1800bf0b2  add     r9, rdx
0x1800bf0b5  add     rax, rdx
0x1800bf0b8  sub     rcx, rdi
0x1800bf0bb  add     r11, rdi
0x1800bf0be  sub     r8, rdi
0x1800bf0c1  jnz     short loc_1800BF0A1
0x1800bf0c3  test    r8, r8
0x1800bf0c6  lea     rcx, [rax-2]
0x1800bf0ca  cmovnz  rcx, rax
0x1800bf0ce  lea     rax, [r11-1]
0x1800bf0d2  cmovnz  rax, r11
0x1800bf0d6  sub     r10, rax
0x1800bf0d9  mov     [rcx], r15w
0x1800bf0dd  mov     eax, edi
0x1800bf0df  sub     eax, r10d
0x1800bf0e2  lea     ecx, [rbx+rax*2]
0x1800bf0e5  mov     eax, ecx
0x1800bf0e7  lea     esi, [rcx+r13]
0x1800bf0eb  shr     rax, 1
0x1800bf0ee  sub     ebx, ecx
0x1800bf0f0  xor     r13d, r13d
0x1800bf0f3  lea     r9, [r14+rax*2]
0x1800bf0f7  cmp     word ptr [rsp+0D60h+var_D28+8], r13w
0x1800bf0fd  jz      loc_1800BF275
0x1800bf103  mov     r8d, ebx
0x1800bf106  mov     r10d, r13d
0x1800bf109  shr     r8, 1
0x1800bf10c  jz      short loc_1800BF155
0x1800bf10e  mov     rax, qword ptr [rsp+0D60h+var_D18]
0x1800bf113  mov     r10, r8
0x1800bf116  mov     r11d, r13d
0x1800bf119  test    r12, r12
0x1800bf11c  jz      short loc_1800BF13B
0x1800bf11e  movzx   ecx, word ptr [rax]
0x1800bf121  test    cx, cx
0x1800bf124  jz      short loc_1800BF13B
0x1800bf126  mov     [r9], cx
0x1800bf12a  add     rax, rdx
0x1800bf12d  add     r9, rdx
0x1800bf130  sub     r12, rdi
0x1800bf133  add     r11, rdi
0x1800bf136  sub     r8, rdi
0x1800bf139  jnz     short loc_1800BF119
0x1800bf13b  test    r8, r8
0x1800bf13e  lea     rcx, [r9-2]
0x1800bf142  lea     rax, [r11-1]
0x1800bf146  cmovnz  rcx, r9
0x1800bf14a  cmovnz  rax, r11
0x1800bf14e  sub     r10, rax
0x1800bf151  mov     [rcx], r13w
0x1800bf155  sub     edi, r10d
0x1800bf158  lea     edx, [rbx+rdi*2]
0x1800bf15b  lea     ebx, [rsi+rdx]
0x1800bf15e  call    RtlGetCurrentServiceSessionId
0x1800bf163  test    eax, eax
0x1800bf165  jz      loc_1800BF29B
0x1800bf16b  mov     rax, gs:60h
0x1800bf174  mov     rax, [rax+90h]
0x1800bf17b  add     rax, 22Ah
0x1800bf181  movzx   ecx, byte ptr [rax]
0x1800bf184  lea     r8d, [rbx+4]
0x1800bf188  mov     r9, [rsp+0D60h+var_CF0]
0x1800bf18d  mov     edx, 402h
0x1800bf192  call    NtTraceEvent
0x1800bf197  mov     rcx, gs:60h
0x1800bf1a0  xor     edx, edx
0x1800bf1a2  mov     r8, [rsp+0D60h+var_CF0]
0x1800bf1a7  mov     rcx, [rcx+30h]
0x1800bf1ab  call    RtlFreeHeap_0
0x1800bf1b0  mov     rdx, qword ptr [rsp+0D60h+var_D08+8]
0x1800bf1b5  mov     r15d, [rsp+0D60h+var_D40]
0x1800bf1ba  mov     r12d, [rsp+0D60h+var_D3C]
0x1800bf1bf  mov     esi, dword ptr [rsp+0D60h+var_D38]
0x1800bf1c3  test    rdx, rdx
0x1800bf1c6  jz      short loc_1800BF1D0
0x1800bf1c8  mov     rcx, rdx
0x1800bf1cb  call    RtlpSysVolFree
0x1800bf1d0  test    r15d, r15d
0x1800bf1d3  js      short loc_1800BF1E6
0x1800bf1d5  cmp     qword ptr [rsp+0D60h+var_D28], r13
0x1800bf1da  jz      short loc_1800BF1E6
0x1800bf1dc  mov     rcx, qword ptr [rsp+0D60h+var_D28]
0x1800bf1e1  call    RtlpSysVolFree
0x1800bf1e6  test    esi, esi
0x1800bf1e8  js      short loc_1800BF1FB
0x1800bf1ea  cmp     qword ptr [rsp+0D60h+var_D18], r13
0x1800bf1ef  jz      short loc_1800BF1FB
0x1800bf1f1  mov     rcx, qword ptr [rsp+0D60h+var_D18]
0x1800bf1f6  call    RtlpSysVolFree
0x1800bf1fb  test    r12d, r12d
0x1800bf1fe  js      short loc_1800BF211
0x1800bf200  cmp     qword ptr [rsp+0D60h+var_D08], r13
0x1800bf205  jz      short loc_1800BF211
0x1800bf207  mov     rcx, qword ptr [rsp+0D60h+var_D08]
0x1800bf20c  call    RtlpSysVolFree
0x1800bf211  mov     rcx, [rbp+0C60h+var_60]
0x1800bf218  xor     rcx, rsp; StackCookie
  ... truncated ...
```
