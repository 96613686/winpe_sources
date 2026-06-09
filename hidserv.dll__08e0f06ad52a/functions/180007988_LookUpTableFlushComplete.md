# LookUpTableFlushComplete

- ea: `0x180007988`
- end: `0x180007d65`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: `__int64 __fastcall(const __m128i *, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007620`
- `0x180007e00`
- `0x180007e60`
- `0x180008090`

## callees

- `0x180001008`
- `0x1800074f0`
- `0x180007988`
- `0x180008450`

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
      if ( (unsigned int)dword_18000D040 > 5
        && (qword_18000D050 & 0x200000000000LL) != 0
        && (qword_18000D058 & 0x200000000000LL) == qword_18000D058 )
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
          (__int64)byte_18000AE61,
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
      result = FlushLookUpTableBucket((__int64)a1, v5++);
    while ( v5 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x180007988  mov     [rsp-8+arg_8], rbx
0x18000798d  mov     [rsp-8+arg_10], rsi
0x180007992  push    rbp
0x180007993  push    rdi
0x180007994  push    r14
0x180007996  lea     rbp, [rsp-90h]
0x18000799e  sub     rsp, 230h
0x1800079a5  mov     rax, cs:__security_cookie
0x1800079ac  xor     rax, rsp
0x1800079af  mov     [rbp+0A0h+var_18], rax
0x1800079b6  mov     eax, [rcx+100h]
0x1800079bc  xor     edi, edi
0x1800079be  mov     rbx, rcx
0x1800079c1  test    eax, eax
0x1800079c3  jz      loc_180007D3E
0x1800079c9  cmp     [rcx+128h], eax
0x1800079cf  ja      short loc_1800079DA
0x1800079d1  cmp     [rcx+118h], rdi
0x1800079d8  jnz     short loc_1800079E0
0x1800079da  mov     [rcx+128h], eax
0x1800079e0  cmp     [rcx+124h], eax
0x1800079e6  jnb     short loc_1800079EE
0x1800079e8  mov     [rcx+124h], eax
0x1800079ee  mov     esi, 1
0x1800079f3  movq    xmm1, rax
0x1800079f8  movq    xmm0, rsi
0x1800079fd  lea     r14d, [rsi+1Fh]
0x180007a01  punpcklqdq xmm1, xmm0
0x180007a05  movdqu  xmm0, xmmword ptr [rcx+110h]
0x180007a0d  paddq   xmm1, xmm0
0x180007a11  movdqu  xmmword ptr [rcx+110h], xmm1
0x180007a19  cmp     [rcx+110h], rdi
0x180007a20  jz      loc_180007D2D
0x180007a26  mov     eax, cs:dword_18000D040
0x180007a2c  cmp     eax, 5
0x180007a2f  jbe     loc_180007D13
0x180007a35  mov     rcx, cs:qword_18000D058
0x180007a3c  mov     rdx, 200000000000h
0x180007a46  mov     rax, cs:qword_18000D050
0x180007a4d  test    rdx, rax
0x180007a50  jz      loc_180007D13
0x180007a56  mov     rax, rcx
0x180007a59  and     rax, rdx
0x180007a5c  cmp     rax, rcx
0x180007a5f  jnz     loc_180007D13
0x180007a65  lea     ecx, [rsi+29h]
0x180007a68  mov     [rbp+0A0h+var_120], 4
0x180007a6c  lea     rax, aSummarycount; "SummaryCount"
0x180007a73  mov     [rbp+0A0h+var_A0], cx
0x180007a77  mov     [rbp+0A0h+var_B8], rax
0x180007a7b  lea     eax, [rsi+17h]
0x180007a7e  mov     [rbp+0A0h+var_B0], ax
0x180007a82  mov     eax, [rbx+134h]
0x180007a88  mov     [rbp+0A0h+var_108], rax
0x180007a8c  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x180007a93  mov     [rbp+0A0h+var_A8], rax
0x180007a97  mov     eax, [rbx+130h]
0x180007a9d  mov     [rbp+0A0h+var_100], rax
0x180007aa1  lea     rax, aNumallocationf; "NumAllocationFailures"
0x180007aa8  mov     [rbp+0A0h+var_98], rax
0x180007aac  mov     eax, [rbx+12Ch]
0x180007ab2  mov     [rbp+0A0h+var_F8], rax
0x180007ab6  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x180007abd  mov     [rbp+0A0h+var_88], rax
0x180007ac1  mov     eax, [rbx+128h]
0x180007ac7  mov     [rbp+0A0h+var_F0], rax
0x180007acb  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180007ad2  mov     [rbp+0A0h+var_78], rax
0x180007ad6  mov     eax, [rbx+124h]
0x180007adc  mov     [rbp+0A0h+var_E8], rax
0x180007ae0  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180007ae7  mov     [rbp+0A0h+var_68], rax
0x180007aeb  mov     rax, [rbx+110h]
0x180007af2  mov     [rbp+0A0h+var_E0], rax
0x180007af6  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180007afd  mov     [rbp+0A0h+var_58], rax
0x180007b01  lea     eax, [rsi+25h]
0x180007b04  mov     [rbp+0A0h+var_50], ax
0x180007b08  mov     eax, [rbx+120h]
0x180007b0e  mov     [rbp+0A0h+var_D8], rax
0x180007b12  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180007b19  mov     [rbp+0A0h+var_48], rax
0x180007b1d  mov     rax, [rbx+118h]
0x180007b24  mov     [rbp+0A0h+var_D0], rax
0x180007b28  lea     rax, aNumflushes; "NumFlushes"
0x180007b2f  mov     [rbp+0A0h+var_38], rax
0x180007b33  lea     eax, [rsi+13h]
0x180007b36  mov     [rbp+0A0h+var_30], ax
0x180007b3a  mov     rax, [rbx+148h]
0x180007b41  mov     [rbp+0A0h+var_90], cx
0x180007b45  mov     [rbp+0A0h+var_80], cx
0x180007b49  lea     ecx, [rsi+21h]
0x180007b4c  mov     [rbp+0A0h+var_114], esi
0x180007b4f  mov     [rbp+0A0h+var_11F], 4
0x180007b53  mov     [rbp+0A0h+var_11E], 4
0x180007b57  mov     [rbp+0A0h+var_11D], 4
0x180007b5b  mov     [rbp+0A0h+var_11C], 4
0x180007b5f  mov     [rbp+0A0h+var_70], cx
0x180007b63  mov     [rbp+0A0h+var_11B], 4
0x180007b67  mov     [rbp+0A0h+var_60], cx
0x180007b6b  mov     [rbp+0A0h+var_11A], 4
0x180007b6f  mov     [rbp+0A0h+var_119], 4
0x180007b73  mov     [rbp+0A0h+var_40], r14w
0x180007b78  mov     [rbp+0A0h+var_118], 4
0x180007b7c  mov     rcx, [rax+8]
0x180007b80  lea     rax, [rbp+0A0h+var_28]
0x180007b84  mov     [rbp+0A0h+var_C8], rax
0x180007b88  lea     rax, [rbp+0A0h+var_120]
0x180007b8c  mov     [rsp+240h+var_128], rax
0x180007b94  lea     rax, [rbp+0A0h+var_114]
0x180007b98  mov     [rsp+240h+var_130], rax
0x180007ba0  lea     rax, [rbp+0A0h+var_B8]
0x180007ba4  movups  xmm0, xmmword ptr [rcx-10h]
0x180007ba8  mov     [rsp+240h+var_138], rax
0x180007bb0  lea     rax, [rbp+0A0h+var_11F]
0x180007bb4  mov     [rsp+240h+var_140], rax
0x180007bbc  lea     rax, [rbp+0A0h+var_108]
0x180007bc0  mov     [rsp+240h+var_148], rax
0x180007bc8  lea     rax, [rbp+0A0h+var_A8]
0x180007bcc  mov     [rsp+240h+var_150], rax
0x180007bd4  lea     rax, [rbp+0A0h+var_11E]
0x180007bd8  movdqu  [rbp+0A0h+var_28], xmm0
0x180007bdd  mov     [rbp+0A0h+var_117], dil
0x180007be1  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x180007be8  mov     [rbp+0A0h+var_10C], 12Ch
0x180007bef  mov     [rbp+0A0h+var_C0], 1000000h
0x180007bf7  mov     [rsp+240h+var_158], rax
0x180007bff  lea     rdx, byte_18000AE61
0x180007c06  lea     rax, [rbp+0A0h+var_100]
0x180007c0a  mov     [rsp+240h+var_160], rax
0x180007c12  lea     rax, [rbp+0A0h+var_98]
0x180007c16  mov     [rsp+240h+var_168], rax
0x180007c1e  lea     rax, [rbp+0A0h+var_11D]
0x180007c22  mov     [rsp+240h+var_170], rax
0x180007c2a  lea     rax, [rbp+0A0h+var_F8]
0x180007c2e  mov     [rsp+240h+var_178], rax
0x180007c36  lea     rax, [rbp+0A0h+var_88]
0x180007c3a  mov     [rsp+240h+var_180], rax
0x180007c42  lea     rax, [rbp+0A0h+var_11C]
0x180007c46  mov     [rsp+240h+var_188], rax
0x180007c4e  lea     rax, [rbp+0A0h+var_F0]
0x180007c52  mov     [rsp+240h+var_190], rax
0x180007c5a  lea     rax, [rbp+0A0h+var_78]
0x180007c5e  mov     [rsp+240h+var_198], rax
0x180007c66  lea     rax, [rbp+0A0h+var_11B]
0x180007c6a  mov     [rsp+240h+var_1A0], rax
0x180007c72  lea     rax, [rbp+0A0h+var_E8]
0x180007c76  mov     [rsp+240h+var_1A8], rax
0x180007c7e  lea     rax, [rbp+0A0h+var_68]
0x180007c82  mov     [rsp+240h+var_1B0], rax
0x180007c8a  lea     rax, [rbp+0A0h+var_11A]
0x180007c8e  mov     [rsp+240h+var_1B8], rax
0x180007c96  lea     rax, [rbp+0A0h+var_E0]
0x180007c9a  mov     [rsp+240h+var_1C0], rax
0x180007ca2  lea     rax, [rbp+0A0h+var_58]
0x180007ca6  mov     [rsp+240h+var_1C8], rax
0x180007cab  lea     rax, [rbp+0A0h+var_119]
0x180007caf  mov     [rsp+240h+var_1D0], rax
0x180007cb4  lea     rax, [rbp+0A0h+var_D8]
0x180007cb8  mov     [rsp+240h+var_1D8], rax
0x180007cbd  lea     rax, [rbp+0A0h+var_48]
0x180007cc1  mov     [rsp+240h+var_1E0], rax
0x180007cc6  lea     rax, [rbp+0A0h+var_118]
0x180007cca  mov     [rsp+240h+var_1E8], rax
0x180007ccf  lea     rax, [rbp+0A0h+var_D0]
0x180007cd3  mov     [rsp+240h+var_1F0], rax
0x180007cd8  lea     rax, [rbp+0A0h+var_38]
0x180007cdc  mov     [rsp+240h+var_1F8], rax
0x180007ce1  lea     rax, [rbp+0A0h+var_C8]
0x180007ce5  mov     [rsp+240h+var_200], rax
0x180007cea  lea     rax, [rbp+0A0h+var_117]
0x180007cee  mov     [rsp+240h+var_208], rax
0x180007cf3  lea     rax, [rbp+0A0h+var_110]
0x180007cf7  mov     [rsp+240h+var_210], rax
0x180007cfc  lea     rax, [rbp+0A0h+var_10C]
0x180007d00  mov     [rsp+240h+var_218], rax
0x180007d05  lea     rax, [rbp+0A0h+var_C0]
0x180007d09  mov     [rsp+240h+var_220], rax
0x180007d0e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180007d13  xorps   xmm0, xmm0
0x180007d16  xor     eax, eax
0x180007d18  movups  xmmword ptr [rbx+110h], xmm0
0x180007d1f  movups  xmmword ptr [rbx+120h], xmm0
0x180007d26  mov     [rbx+130h], rax
0x180007d2d  mov     edx, edi
0x180007d2f  mov     rcx, rbx
0x180007d32  call    FlushLookUpTableBucket
0x180007d37  add     edi, esi
0x180007d39  cmp     edi, r14d
0x180007d3c  jb      short loc_180007D2D
0x180007d3e  mov     rcx, [rbp+0A0h+var_18]
0x180007d45  xor     rcx, rsp; StackCookie
0x180007d48  call    __security_check_cookie
0x180007d4d  lea     r11, [rsp+240h+var_10]
0x180007d55  mov     rbx, [r11+28h]
0x180007d59  mov     rsi, [r11+30h]
0x180007d5d  mov     rsp, r11
0x180007d60  pop     r14
0x180007d62  pop     rdi
0x180007d63  pop     rbp
0x180007d64  retn
```
