# LookUpTableFlushComplete

- ea: `0x180014d9c`
- end: `0x180015179`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: `__int64 __fastcall(const __m128i *, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b6bc`
- `0x18000df84`
- `0x180014a20`
- `0x180015210`
- `0x180015270`

## callees

- `0x18000187c`
- `0x1800024a0`
- `0x1800148f8`
- `0x180014d9c`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  unsigned int v5; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
  char v9; // [rsp+120h] [rbp-80h] BYREF
  char v10; // [rsp+121h] [rbp-7Fh] BYREF
  char v11; // [rsp+122h] [rbp-7Eh] BYREF
  char v12; // [rsp+123h] [rbp-7Dh] BYREF
  char v13; // [rsp+124h] [rbp-7Ch] BYREF
  char v14; // [rsp+125h] [rbp-7Bh] BYREF
  char v15; // [rsp+126h] [rbp-7Ah] BYREF
  char v16; // [rsp+127h] [rbp-79h] BYREF
  char v17; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v18[3]; // [rsp+129h] [rbp-77h] BYREF
  int v19; // [rsp+12Ch] [rbp-74h] BYREF
  int v20; // [rsp+130h] [rbp-70h] BYREF
  int v21; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v22; // [rsp+138h] [rbp-68h] BYREF
  __int64 v23; // [rsp+140h] [rbp-60h] BYREF
  __int64 v24; // [rsp+148h] [rbp-58h] BYREF
  __int64 v25; // [rsp+150h] [rbp-50h] BYREF
  __int64 v26; // [rsp+158h] [rbp-48h] BYREF
  __int64 v27; // [rsp+160h] [rbp-40h] BYREF
  __int64 v28; // [rsp+168h] [rbp-38h] BYREF
  __int64 v29; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v30; // [rsp+178h] [rbp-28h] BYREF
  __int64 v31; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v32; // [rsp+188h] [rbp-18h] BYREF
  __int16 v33; // [rsp+190h] [rbp-10h]
  const wchar_t *v34; // [rsp+198h] [rbp-8h] BYREF
  __int16 v35; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v36; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v37; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v38; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v39; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v40; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v41; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v42; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v43; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v44; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v45; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v46; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v47; // [rsp+200h] [rbp+60h]
  const wchar_t *v48; // [rsp+208h] [rbp+68h] BYREF
  __int16 v49; // [rsp+210h] [rbp+70h]
  __int128 v50; // [rsp+218h] [rbp+78h] BYREF

  result = a1[16].m128i_u32[0];
  v5 = 0;
  if ( (_DWORD)result )
  {
    if ( a1[18].m128i_i32[2] > (unsigned int)result || !a1[17].m128i_i64[1] )
      a1[18].m128i_i32[2] = result;
    if ( a1[18].m128i_i32[1] < (unsigned int)result )
      a1[18].m128i_i32[1] = result;
    a1[17] = _mm_add_epi64(
               _mm_unpacklo_epi64((__m128i)(unsigned __int64)result, (__m128i)1uLL),
               _mm_loadu_si128(a1 + 17));
    if ( a1[17].m128i_i64[0] )
    {
      if ( (unsigned int)dword_180021128 > 5
        && (qword_180021138 & 0x200000000000LL) != 0
        && (qword_180021140 & 0x200000000000LL) == qword_180021140 )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = a1[19].m128i_u32[1];
        v34 = L"NumLargeEventFailures";
        v23 = a1[19].m128i_u32[0];
        v36 = L"NumAllocationFailures";
        v24 = a1[18].m128i_u32[3];
        v38 = L"NumBucketLimitReached";
        v25 = a1[18].m128i_u32[2];
        v40 = L"MinEntriesFlushed";
        v26 = a1[18].m128i_u32[1];
        v42 = L"MaxEntriesFlushed";
        v27 = a1[17].m128i_i64[0];
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = a1[18].m128i_u32[0];
        v46 = L"MaxEntriesStored";
        v29 = a1[17].m128i_i64[1];
        v48 = L"NumFlushes";
        v49 = 20;
        v7 = a1[20].m128i_i64[1];
        v37 = 42;
        v39 = 42;
        v19 = 1;
        v10 = 4;
        v11 = 4;
        v12 = 4;
        v13 = 4;
        v41 = 34;
        v14 = 4;
        v43 = 34;
        v15 = 4;
        v16 = 4;
        v47 = 32;
        v17 = 4;
        v8 = *(_QWORD *)(v7 + 8);
        v30 = &v50;
        v50 = *(_OWORD *)(v8 - 16);
        v18[0] = 0;
        v20 = -1;
        v21 = 300;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v8,
          (__int64)&dword_18001C844,
          a3,
          a4,
          (__int64)&v31,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)v18,
          (__int64 *)&v30,
          (__int64 *)&v48,
          (__int64)&v29,
          (__int64)&v17,
          (__int64 *)&v46,
          (__int64)&v28,
          (__int64)&v16,
          (__int64 *)&v44,
          (__int64)&v27,
          (__int64)&v15,
          (__int64 *)&v42,
          (__int64)&v26,
          (__int64)&v14,
          (__int64 *)&v40,
          (__int64)&v25,
          (__int64)&v13,
          (__int64 *)&v38,
          (__int64)&v24,
          (__int64)&v12,
          (__int64 *)&v36,
          (__int64)&v23,
          (__int64)&v11,
          (__int64 *)&v34,
          (__int64)&v22,
          (__int64)&v10,
          (__int64 *)&v32,
          (__int64)&v19,
          (__int64)&v9);
      }
      a1[17] = 0;
      a1[18] = 0;
      a1[19].m128i_i64[0] = 0;
    }
    do
      result = FlushLookUpTableBucket(a1, v5++);
    while ( v5 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x180014d9c  mov     [rsp-8+arg_8], rbx
0x180014da1  mov     [rsp-8+arg_10], rsi
0x180014da6  push    rbp
0x180014da7  push    rdi
0x180014da8  push    r14
0x180014daa  lea     rbp, [rsp-90h]
0x180014db2  sub     rsp, 230h
0x180014db9  mov     rax, cs:__security_cookie
0x180014dc0  xor     rax, rsp
0x180014dc3  mov     [rbp+0A0h+var_18], rax
0x180014dca  mov     eax, [rcx+100h]
0x180014dd0  xor     edi, edi
0x180014dd2  mov     rbx, rcx
0x180014dd5  test    eax, eax
0x180014dd7  jz      loc_180015152
0x180014ddd  cmp     [rcx+128h], eax
0x180014de3  ja      short loc_180014DEE
0x180014de5  cmp     [rcx+118h], rdi
0x180014dec  jnz     short loc_180014DF4
0x180014dee  mov     [rcx+128h], eax
0x180014df4  cmp     [rcx+124h], eax
0x180014dfa  jnb     short loc_180014E02
0x180014dfc  mov     [rcx+124h], eax
0x180014e02  mov     esi, 1
0x180014e07  movq    xmm1, rax
0x180014e0c  movq    xmm0, rsi
0x180014e11  lea     r14d, [rsi+1Fh]
0x180014e15  punpcklqdq xmm1, xmm0
0x180014e19  movdqu  xmm0, xmmword ptr [rcx+110h]
0x180014e21  paddq   xmm1, xmm0
0x180014e25  movdqu  xmmword ptr [rcx+110h], xmm1
0x180014e2d  cmp     [rcx+110h], rdi
0x180014e34  jz      loc_180015141
0x180014e3a  mov     eax, cs:dword_180021128
0x180014e40  cmp     eax, 5
0x180014e43  jbe     loc_180015127
0x180014e49  mov     rcx, cs:qword_180021140
0x180014e50  mov     rdx, 200000000000h
0x180014e5a  mov     rax, cs:qword_180021138
0x180014e61  test    rdx, rax
0x180014e64  jz      loc_180015127
0x180014e6a  mov     rax, rcx
0x180014e6d  and     rax, rdx
0x180014e70  cmp     rax, rcx
0x180014e73  jnz     loc_180015127
0x180014e79  lea     ecx, [rsi+29h]
0x180014e7c  mov     [rbp+0A0h+var_120], 4
0x180014e80  lea     rax, aSummarycount; "SummaryCount"
0x180014e87  mov     [rbp+0A0h+var_A0], cx
0x180014e8b  mov     [rbp+0A0h+var_B8], rax
0x180014e8f  lea     eax, [rsi+17h]
0x180014e92  mov     [rbp+0A0h+var_B0], ax
0x180014e96  mov     eax, [rbx+134h]
0x180014e9c  mov     [rbp+0A0h+var_108], rax
0x180014ea0  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x180014ea7  mov     [rbp+0A0h+var_A8], rax
0x180014eab  mov     eax, [rbx+130h]
0x180014eb1  mov     [rbp+0A0h+var_100], rax
0x180014eb5  lea     rax, aNumallocationf; "NumAllocationFailures"
0x180014ebc  mov     [rbp+0A0h+var_98], rax
0x180014ec0  mov     eax, [rbx+12Ch]
0x180014ec6  mov     [rbp+0A0h+var_F8], rax
0x180014eca  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x180014ed1  mov     [rbp+0A0h+var_88], rax
0x180014ed5  mov     eax, [rbx+128h]
0x180014edb  mov     [rbp+0A0h+var_F0], rax
0x180014edf  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180014ee6  mov     [rbp+0A0h+var_78], rax
0x180014eea  mov     eax, [rbx+124h]
0x180014ef0  mov     [rbp+0A0h+var_E8], rax
0x180014ef4  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180014efb  mov     [rbp+0A0h+var_68], rax
0x180014eff  mov     rax, [rbx+110h]
0x180014f06  mov     [rbp+0A0h+var_E0], rax
0x180014f0a  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180014f11  mov     [rbp+0A0h+var_58], rax
0x180014f15  lea     eax, [rsi+25h]
0x180014f18  mov     [rbp+0A0h+var_50], ax
0x180014f1c  mov     eax, [rbx+120h]
0x180014f22  mov     [rbp+0A0h+var_D8], rax
0x180014f26  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180014f2d  mov     [rbp+0A0h+var_48], rax
0x180014f31  mov     rax, [rbx+118h]
0x180014f38  mov     [rbp+0A0h+var_D0], rax
0x180014f3c  lea     rax, aNumflushes; "NumFlushes"
0x180014f43  mov     [rbp+0A0h+var_38], rax
0x180014f47  lea     eax, [rsi+13h]
0x180014f4a  mov     [rbp+0A0h+var_30], ax
0x180014f4e  mov     rax, [rbx+148h]
0x180014f55  mov     [rbp+0A0h+var_90], cx
0x180014f59  mov     [rbp+0A0h+var_80], cx
0x180014f5d  lea     ecx, [rsi+21h]
0x180014f60  mov     [rbp+0A0h+var_114], esi
0x180014f63  mov     [rbp+0A0h+var_11F], 4
0x180014f67  mov     [rbp+0A0h+var_11E], 4
0x180014f6b  mov     [rbp+0A0h+var_11D], 4
0x180014f6f  mov     [rbp+0A0h+var_11C], 4
0x180014f73  mov     [rbp+0A0h+var_70], cx
0x180014f77  mov     [rbp+0A0h+var_11B], 4
0x180014f7b  mov     [rbp+0A0h+var_60], cx
0x180014f7f  mov     [rbp+0A0h+var_11A], 4
0x180014f83  mov     [rbp+0A0h+var_119], 4
0x180014f87  mov     [rbp+0A0h+var_40], r14w
0x180014f8c  mov     [rbp+0A0h+var_118], 4
0x180014f90  mov     rcx, [rax+8]
0x180014f94  lea     rax, [rbp+0A0h+var_28]
0x180014f98  mov     [rbp+0A0h+var_C8], rax
0x180014f9c  lea     rax, [rbp+0A0h+var_120]
0x180014fa0  mov     [rsp+240h+var_128], rax
0x180014fa8  lea     rax, [rbp+0A0h+var_114]
0x180014fac  mov     [rsp+240h+var_130], rax
0x180014fb4  lea     rax, [rbp+0A0h+var_B8]
0x180014fb8  movups  xmm0, xmmword ptr [rcx-10h]
0x180014fbc  mov     [rsp+240h+var_138], rax
0x180014fc4  lea     rax, [rbp+0A0h+var_11F]
0x180014fc8  mov     [rsp+240h+var_140], rax
0x180014fd0  lea     rax, [rbp+0A0h+var_108]
0x180014fd4  mov     [rsp+240h+var_148], rax
0x180014fdc  lea     rax, [rbp+0A0h+var_A8]
0x180014fe0  mov     [rsp+240h+var_150], rax
0x180014fe8  lea     rax, [rbp+0A0h+var_11E]
0x180014fec  movdqu  [rbp+0A0h+var_28], xmm0
0x180014ff1  mov     [rbp+0A0h+var_117], dil
0x180014ff5  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x180014ffc  mov     [rbp+0A0h+var_10C], 12Ch
0x180015003  mov     [rbp+0A0h+var_C0], 1000000h
0x18001500b  mov     [rsp+240h+var_158], rax
0x180015013  lea     rdx, dword_18001C844
0x18001501a  lea     rax, [rbp+0A0h+var_100]
0x18001501e  mov     [rsp+240h+var_160], rax
0x180015026  lea     rax, [rbp+0A0h+var_98]
0x18001502a  mov     [rsp+240h+var_168], rax
0x180015032  lea     rax, [rbp+0A0h+var_11D]
0x180015036  mov     [rsp+240h+var_170], rax
0x18001503e  lea     rax, [rbp+0A0h+var_F8]
0x180015042  mov     [rsp+240h+var_178], rax
0x18001504a  lea     rax, [rbp+0A0h+var_88]
0x18001504e  mov     [rsp+240h+var_180], rax
0x180015056  lea     rax, [rbp+0A0h+var_11C]
0x18001505a  mov     [rsp+240h+var_188], rax
0x180015062  lea     rax, [rbp+0A0h+var_F0]
0x180015066  mov     [rsp+240h+var_190], rax
0x18001506e  lea     rax, [rbp+0A0h+var_78]
0x180015072  mov     [rsp+240h+var_198], rax
0x18001507a  lea     rax, [rbp+0A0h+var_11B]
0x18001507e  mov     [rsp+240h+var_1A0], rax
0x180015086  lea     rax, [rbp+0A0h+var_E8]
0x18001508a  mov     [rsp+240h+var_1A8], rax
0x180015092  lea     rax, [rbp+0A0h+var_68]
0x180015096  mov     [rsp+240h+var_1B0], rax
0x18001509e  lea     rax, [rbp+0A0h+var_11A]
0x1800150a2  mov     [rsp+240h+var_1B8], rax
0x1800150aa  lea     rax, [rbp+0A0h+var_E0]
0x1800150ae  mov     [rsp+240h+var_1C0], rax
0x1800150b6  lea     rax, [rbp+0A0h+var_58]
0x1800150ba  mov     [rsp+240h+var_1C8], rax
0x1800150bf  lea     rax, [rbp+0A0h+var_119]
0x1800150c3  mov     [rsp+240h+var_1D0], rax
0x1800150c8  lea     rax, [rbp+0A0h+var_D8]
0x1800150cc  mov     [rsp+240h+var_1D8], rax
0x1800150d1  lea     rax, [rbp+0A0h+var_48]
0x1800150d5  mov     [rsp+240h+var_1E0], rax
0x1800150da  lea     rax, [rbp+0A0h+var_118]
0x1800150de  mov     [rsp+240h+var_1E8], rax
0x1800150e3  lea     rax, [rbp+0A0h+var_D0]
0x1800150e7  mov     [rsp+240h+var_1F0], rax
0x1800150ec  lea     rax, [rbp+0A0h+var_38]
0x1800150f0  mov     [rsp+240h+var_1F8], rax
0x1800150f5  lea     rax, [rbp+0A0h+var_C8]
0x1800150f9  mov     [rsp+240h+var_200], rax
0x1800150fe  lea     rax, [rbp+0A0h+var_117]
0x180015102  mov     [rsp+240h+var_208], rax
0x180015107  lea     rax, [rbp+0A0h+var_110]
0x18001510b  mov     [rsp+240h+var_210], rax
0x180015110  lea     rax, [rbp+0A0h+var_10C]
0x180015114  mov     [rsp+240h+var_218], rax
0x180015119  lea     rax, [rbp+0A0h+var_C0]
0x18001511d  mov     [rsp+240h+var_220], rax
0x180015122  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180015127  xorps   xmm0, xmm0
0x18001512a  xor     eax, eax
0x18001512c  movups  xmmword ptr [rbx+110h], xmm0
0x180015133  movups  xmmword ptr [rbx+120h], xmm0
0x18001513a  mov     [rbx+130h], rax
0x180015141  mov     edx, edi
0x180015143  mov     rcx, rbx
0x180015146  call    FlushLookUpTableBucket
0x18001514b  add     edi, esi
0x18001514d  cmp     edi, r14d
0x180015150  jb      short loc_180015141
0x180015152  mov     rcx, [rbp+0A0h+var_18]
0x180015159  xor     rcx, rsp; StackCookie
0x18001515c  call    __security_check_cookie
0x180015161  lea     r11, [rsp+240h+var_10]
0x180015169  mov     rbx, [r11+28h]
0x18001516d  mov     rsi, [r11+30h]
0x180015171  mov     rsp, r11
0x180015174  pop     r14
0x180015176  pop     rdi
0x180015177  pop     rbp
0x180015178  retn
```
