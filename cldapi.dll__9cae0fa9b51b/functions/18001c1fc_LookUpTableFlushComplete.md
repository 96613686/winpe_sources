# LookUpTableFlushComplete

- ea: `0x18001c1fc`
- end: `0x18001c5da`
- name: `LookUpTableFlushComplete`
- size: `990`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001be60`
- `0x18001c680`
- `0x18001c6f0`
- `0x18001c920`

## callees

- `0x180001144`
- `0x180001aa0`
- `0x18001bd94`
- `0x18001c1fc`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, int a3, int a4)
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
      if ( (unsigned int)dword_18002A730 > 5
        && (qword_18002A740 & 0x200000000000LL) != 0
        && (qword_18002A748 & 0x200000000000LL) == qword_18002A748 )
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
          (unsigned int)&word_180026C2E,
          a3,
          a4,
          (__int64)&v31,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)v18,
          (__int64)&v30,
          (__int64)&v48,
          (__int64)&v29,
          (__int64)&v17,
          (__int64)&v46,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v44,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v42,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v40,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v38,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v36,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v34,
          (__int64)&v22,
          (__int64)&v10,
          (__int64)&v32,
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
0x18001c1fc  mov     [rsp-8+arg_8], rbx
0x18001c201  mov     [rsp-8+arg_10], rsi
0x18001c206  push    rbp
0x18001c207  push    rdi
0x18001c208  push    r14
0x18001c20a  lea     rbp, [rsp-90h]
0x18001c212  sub     rsp, 230h
0x18001c219  mov     rax, cs:__security_cookie
0x18001c220  xor     rax, rsp
0x18001c223  mov     [rbp+0A0h+var_18], rax
0x18001c22a  mov     eax, [rcx+100h]
0x18001c230  xor     edi, edi
0x18001c232  mov     rbx, rcx
0x18001c235  test    eax, eax
0x18001c237  jz      loc_18001C5B2
0x18001c23d  cmp     [rcx+128h], eax
0x18001c243  ja      short loc_18001C24E
0x18001c245  cmp     [rcx+118h], rdi
0x18001c24c  jnz     short loc_18001C254
0x18001c24e  mov     [rcx+128h], eax
0x18001c254  cmp     [rcx+124h], eax
0x18001c25a  jnb     short loc_18001C262
0x18001c25c  mov     [rcx+124h], eax
0x18001c262  mov     esi, 1
0x18001c267  movq    xmm1, rax
0x18001c26c  movq    xmm0, rsi
0x18001c271  lea     r14d, [rsi+1Fh]
0x18001c275  punpcklqdq xmm1, xmm0
0x18001c279  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18001c281  paddq   xmm1, xmm0
0x18001c285  movdqu  xmmword ptr [rcx+110h], xmm1
0x18001c28d  cmp     [rcx+110h], rdi
0x18001c294  jz      loc_18001C5A1
0x18001c29a  mov     eax, cs:dword_18002A730
0x18001c2a0  cmp     eax, 5
0x18001c2a3  jbe     loc_18001C587
0x18001c2a9  mov     rcx, cs:qword_18002A748
0x18001c2b0  mov     rdx, 200000000000h
0x18001c2ba  mov     rax, cs:qword_18002A740
0x18001c2c1  test    rdx, rax
0x18001c2c4  jz      loc_18001C587
0x18001c2ca  mov     rax, rcx
0x18001c2cd  and     rax, rdx
0x18001c2d0  cmp     rax, rcx
0x18001c2d3  jnz     loc_18001C587
0x18001c2d9  lea     ecx, [rsi+29h]
0x18001c2dc  mov     [rbp+0A0h+var_120], 4
0x18001c2e0  lea     rax, aSummarycount; "SummaryCount"
0x18001c2e7  mov     [rbp+0A0h+var_A0], cx
0x18001c2eb  mov     [rbp+0A0h+var_B8], rax
0x18001c2ef  lea     eax, [rsi+17h]
0x18001c2f2  mov     [rbp+0A0h+var_B0], ax
0x18001c2f6  mov     eax, [rbx+134h]
0x18001c2fc  mov     [rbp+0A0h+var_108], rax
0x18001c300  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18001c307  mov     [rbp+0A0h+var_A8], rax
0x18001c30b  mov     eax, [rbx+130h]
0x18001c311  mov     [rbp+0A0h+var_100], rax
0x18001c315  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18001c31c  mov     [rbp+0A0h+var_98], rax
0x18001c320  mov     eax, [rbx+12Ch]
0x18001c326  mov     [rbp+0A0h+var_F8], rax
0x18001c32a  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18001c331  mov     [rbp+0A0h+var_88], rax
0x18001c335  mov     eax, [rbx+128h]
0x18001c33b  mov     [rbp+0A0h+var_F0], rax
0x18001c33f  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18001c346  mov     [rbp+0A0h+var_78], rax
0x18001c34a  mov     eax, [rbx+124h]
0x18001c350  mov     [rbp+0A0h+var_E8], rax
0x18001c354  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18001c35b  mov     [rbp+0A0h+var_68], rax
0x18001c35f  mov     rax, [rbx+110h]
0x18001c366  mov     [rbp+0A0h+var_E0], rax
0x18001c36a  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18001c371  mov     [rbp+0A0h+var_58], rax
0x18001c375  lea     eax, [rsi+25h]
0x18001c378  mov     [rbp+0A0h+var_50], ax
0x18001c37c  mov     eax, [rbx+120h]
0x18001c382  mov     [rbp+0A0h+var_D8], rax
0x18001c386  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001c38d  mov     [rbp+0A0h+var_48], rax
0x18001c391  mov     rax, [rbx+118h]
0x18001c398  mov     [rbp+0A0h+var_D0], rax
0x18001c39c  lea     rax, aNumflushes; "NumFlushes"
0x18001c3a3  mov     [rbp+0A0h+var_38], rax
0x18001c3a7  lea     eax, [rsi+13h]
0x18001c3aa  mov     [rbp+0A0h+var_30], ax
0x18001c3ae  mov     rax, [rbx+148h]
0x18001c3b5  mov     [rbp+0A0h+var_90], cx
0x18001c3b9  mov     [rbp+0A0h+var_80], cx
0x18001c3bd  lea     ecx, [rsi+21h]
0x18001c3c0  mov     [rbp+0A0h+var_114], esi
0x18001c3c3  mov     [rbp+0A0h+var_11F], 4
0x18001c3c7  mov     [rbp+0A0h+var_11E], 4
0x18001c3cb  mov     [rbp+0A0h+var_11D], 4
0x18001c3cf  mov     [rbp+0A0h+var_11C], 4
0x18001c3d3  mov     [rbp+0A0h+var_70], cx
0x18001c3d7  mov     [rbp+0A0h+var_11B], 4
0x18001c3db  mov     [rbp+0A0h+var_60], cx
0x18001c3df  mov     [rbp+0A0h+var_11A], 4
0x18001c3e3  mov     [rbp+0A0h+var_119], 4
0x18001c3e7  mov     [rbp+0A0h+var_40], r14w
0x18001c3ec  mov     [rbp+0A0h+var_118], 4
0x18001c3f0  mov     rcx, [rax+8]
0x18001c3f4  lea     rax, [rbp+0A0h+var_28]
0x18001c3f8  mov     [rbp+0A0h+var_C8], rax
0x18001c3fc  lea     rax, [rbp+0A0h+var_120]
0x18001c400  mov     [rsp+240h+var_128], rax
0x18001c408  lea     rax, [rbp+0A0h+var_114]
0x18001c40c  mov     [rsp+240h+var_130], rax
0x18001c414  lea     rax, [rbp+0A0h+var_B8]
0x18001c418  movups  xmm0, xmmword ptr [rcx-10h]
0x18001c41c  mov     [rsp+240h+var_138], rax
0x18001c424  lea     rax, [rbp+0A0h+var_11F]
0x18001c428  mov     [rsp+240h+var_140], rax
0x18001c430  lea     rax, [rbp+0A0h+var_108]
0x18001c434  mov     [rsp+240h+var_148], rax
0x18001c43c  lea     rax, [rbp+0A0h+var_A8]
0x18001c440  mov     [rsp+240h+var_150], rax
0x18001c448  lea     rax, [rbp+0A0h+var_11E]
0x18001c44c  movdqu  [rbp+0A0h+var_28], xmm0
0x18001c451  mov     [rbp+0A0h+var_117], dil
0x18001c455  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x18001c45c  mov     [rbp+0A0h+var_10C], 12Ch
0x18001c463  mov     [rbp+0A0h+var_C0], 1000000h
0x18001c46b  mov     [rsp+240h+var_158], rax
0x18001c473  lea     rdx, word_180026C2E
0x18001c47a  lea     rax, [rbp+0A0h+var_100]
0x18001c47e  mov     [rsp+240h+var_160], rax
0x18001c486  lea     rax, [rbp+0A0h+var_98]
0x18001c48a  mov     [rsp+240h+var_168], rax
0x18001c492  lea     rax, [rbp+0A0h+var_11D]
0x18001c496  mov     [rsp+240h+var_170], rax
0x18001c49e  lea     rax, [rbp+0A0h+var_F8]
0x18001c4a2  mov     [rsp+240h+var_178], rax
0x18001c4aa  lea     rax, [rbp+0A0h+var_88]
0x18001c4ae  mov     [rsp+240h+var_180], rax
0x18001c4b6  lea     rax, [rbp+0A0h+var_11C]
0x18001c4ba  mov     [rsp+240h+var_188], rax
0x18001c4c2  lea     rax, [rbp+0A0h+var_F0]
0x18001c4c6  mov     [rsp+240h+var_190], rax
0x18001c4ce  lea     rax, [rbp+0A0h+var_78]
0x18001c4d2  mov     [rsp+240h+var_198], rax
0x18001c4da  lea     rax, [rbp+0A0h+var_11B]
0x18001c4de  mov     [rsp+240h+var_1A0], rax
0x18001c4e6  lea     rax, [rbp+0A0h+var_E8]
0x18001c4ea  mov     [rsp+240h+var_1A8], rax
0x18001c4f2  lea     rax, [rbp+0A0h+var_68]
0x18001c4f6  mov     [rsp+240h+var_1B0], rax
0x18001c4fe  lea     rax, [rbp+0A0h+var_11A]
0x18001c502  mov     [rsp+240h+var_1B8], rax
0x18001c50a  lea     rax, [rbp+0A0h+var_E0]
0x18001c50e  mov     [rsp+240h+var_1C0], rax
0x18001c516  lea     rax, [rbp+0A0h+var_58]
0x18001c51a  mov     [rsp+240h+var_1C8], rax
0x18001c51f  lea     rax, [rbp+0A0h+var_119]
0x18001c523  mov     [rsp+240h+var_1D0], rax
0x18001c528  lea     rax, [rbp+0A0h+var_D8]
0x18001c52c  mov     [rsp+240h+var_1D8], rax
0x18001c531  lea     rax, [rbp+0A0h+var_48]
0x18001c535  mov     [rsp+240h+var_1E0], rax
0x18001c53a  lea     rax, [rbp+0A0h+var_118]
0x18001c53e  mov     [rsp+240h+var_1E8], rax
0x18001c543  lea     rax, [rbp+0A0h+var_D0]
0x18001c547  mov     [rsp+240h+var_1F0], rax
0x18001c54c  lea     rax, [rbp+0A0h+var_38]
0x18001c550  mov     [rsp+240h+var_1F8], rax
0x18001c555  lea     rax, [rbp+0A0h+var_C8]
0x18001c559  mov     [rsp+240h+var_200], rax
0x18001c55e  lea     rax, [rbp+0A0h+var_117]
0x18001c562  mov     [rsp+240h+var_208], rax
0x18001c567  lea     rax, [rbp+0A0h+var_110]
0x18001c56b  mov     [rsp+240h+var_210], rax
0x18001c570  lea     rax, [rbp+0A0h+var_10C]
0x18001c574  mov     [rsp+240h+var_218], rax
0x18001c579  lea     rax, [rbp+0A0h+var_C0]
0x18001c57d  mov     [rsp+240h+var_220], rax
0x18001c582  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18001c587  xorps   xmm0, xmm0
0x18001c58a  xor     eax, eax
0x18001c58c  movups  xmmword ptr [rbx+110h], xmm0
0x18001c593  movups  xmmword ptr [rbx+120h], xmm0
0x18001c59a  mov     [rbx+130h], rax
0x18001c5a1  mov     edx, edi
0x18001c5a3  mov     rcx, rbx
0x18001c5a6  call    FlushLookUpTableBucket
0x18001c5ab  add     edi, esi
0x18001c5ad  cmp     edi, r14d
0x18001c5b0  jb      short loc_18001C5A1
0x18001c5b2  mov     rcx, [rbp+0A0h+var_18]
0x18001c5b9  xor     rcx, rsp; StackCookie
0x18001c5bc  call    __security_check_cookie
0x18001c5c1  lea     r11, [rsp+240h+var_10]
0x18001c5c9  mov     rbx, [r11+28h]
0x18001c5cd  mov     rsi, [r11+30h]
0x18001c5d1  mov     rsp, r11
0x18001c5d4  pop     r14
0x18001c5d6  pop     rdi
0x18001c5d7  pop     rbp
0x18001c5d8  retn
```
