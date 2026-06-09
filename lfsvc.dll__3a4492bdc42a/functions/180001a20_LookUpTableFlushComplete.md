# LookUpTableFlushComplete

- ea: `0x180001a20`
- end: `0x180001e0b`
- name: `LookUpTableFlushComplete`
- size: `1003`
- prototype: `__int64 __fastcall(const __m128i *, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800019a0`
- `0x180002470`
- `0x18000ac70`
- `0x18000b104`

## callees

- `0x1800013ac`
- `0x180001a20`
- `0x180004310`
- `0x18000abb0`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned int i; // ebx
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
      if ( (unsigned int)dword_1800120A8 > 5
        && (qword_1800120B8 & 0x200000000000LL) != 0
        && (qword_1800120C0 & 0x200000000000LL) == qword_1800120C0 )
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
        v47 = 32;
        v29 = a1[17].m128i_i64[1];
        v48 = L"NumFlushes";
        v49 = 20;
        v6 = a1[20].m128i_i64[1];
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
        v17 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v30 = &v50;
        v50 = *(_OWORD *)(v7 - 16);
        v18[0] = 0;
        v20 = -1;
        v21 = 300;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (int)&unk_18000EE40,
          1,
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
    for ( i = 0; i < 0x20; ++i )
      result = FlushLookUpTableBucket(a1, i);
  }
  return result;
}

```

## disassembly

```asm
0x180001a20  mov     [rsp-8+arg_10], rdi
0x180001a25  push    rbp
0x180001a26  lea     rbp, [rsp-90h]
0x180001a2e  sub     rsp, 230h
0x180001a35  mov     rax, cs:__security_cookie
0x180001a3c  xor     rax, rsp
0x180001a3f  mov     [rbp+90h+var_8], rax
0x180001a46  mov     eax, [rcx+100h]
0x180001a4c  mov     rdi, rcx
0x180001a4f  test    eax, eax
0x180001a51  jz      loc_180001DEB
0x180001a57  mov     [rsp+230h+arg_8], rbx
0x180001a5f  cmp     [rcx+128h], eax
0x180001a65  ja      short loc_180001A71
0x180001a67  cmp     qword ptr [rcx+118h], 0
0x180001a6f  jnz     short loc_180001A77
0x180001a71  mov     [rcx+128h], eax
0x180001a77  cmp     [rcx+124h], eax
0x180001a7d  jnb     short loc_180001A85
0x180001a7f  mov     [rcx+124h], eax
0x180001a85  mov     r8d, 1
0x180001a8b  movq    xmm1, rax
0x180001a90  movq    xmm0, r8
0x180001a95  punpcklqdq xmm1, xmm0
0x180001a99  movdqu  xmm0, xmmword ptr [rcx+110h]
0x180001aa1  paddq   xmm1, xmm0
0x180001aa5  movdqu  xmmword ptr [rcx+110h], xmm1
0x180001aad  cmp     qword ptr [rcx+110h], 0
0x180001ab5  jz      loc_180001DD0
0x180001abb  mov     eax, cs:dword_1800120A8
0x180001ac1  cmp     eax, 5
0x180001ac4  jbe     loc_180001DB6
0x180001aca  mov     rcx, cs:qword_1800120C0
0x180001ad1  mov     rdx, 200000000000h
0x180001adb  mov     rax, cs:qword_1800120B8
0x180001ae2  test    rdx, rax
0x180001ae5  jz      loc_180001DB6
0x180001aeb  mov     rax, rcx
0x180001aee  and     rax, rdx
0x180001af1  cmp     rax, rcx
0x180001af4  jnz     loc_180001DB6
0x180001afa  mov     ecx, 2Ah ; '*'
0x180001aff  mov     [rbp+90h+var_110], 4
0x180001b03  lea     rax, aSummarycount; "SummaryCount"
0x180001b0a  mov     [rbp+90h+var_90], cx
0x180001b0e  mov     [rbp+90h+var_A8], rax
0x180001b12  mov     eax, 18h
0x180001b17  mov     [rbp+90h+var_A0], ax
0x180001b1b  mov     eax, [rdi+134h]
0x180001b21  mov     [rbp+90h+var_F8], rax
0x180001b25  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x180001b2c  mov     [rbp+90h+var_98], rax
0x180001b30  mov     eax, [rdi+130h]
0x180001b36  mov     [rbp+90h+var_F0], rax
0x180001b3a  lea     rax, aNumallocationf; "NumAllocationFailures"
0x180001b41  mov     [rbp+90h+var_88], rax
0x180001b45  mov     eax, [rdi+12Ch]
0x180001b4b  mov     [rbp+90h+var_E8], rax
0x180001b4f  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x180001b56  mov     [rbp+90h+var_78], rax
0x180001b5a  mov     eax, [rdi+128h]
0x180001b60  mov     [rbp+90h+var_E0], rax
0x180001b64  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180001b6b  mov     [rbp+90h+var_68], rax
0x180001b6f  mov     eax, [rdi+124h]
0x180001b75  mov     [rbp+90h+var_D8], rax
0x180001b79  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180001b80  mov     [rbp+90h+var_58], rax
0x180001b84  mov     rax, [rdi+110h]
0x180001b8b  mov     [rbp+90h+var_D0], rax
0x180001b8f  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180001b96  mov     [rbp+90h+var_48], rax
0x180001b9a  mov     eax, 26h ; '&'
0x180001b9f  mov     [rbp+90h+var_40], ax
0x180001ba3  mov     eax, [rdi+120h]
0x180001ba9  mov     [rbp+90h+var_C8], rax
0x180001bad  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180001bb4  mov     [rbp+90h+var_38], rax
0x180001bb8  mov     eax, 20h ; ' '
0x180001bbd  mov     [rbp+90h+var_30], ax
0x180001bc1  mov     rax, [rdi+118h]
0x180001bc8  mov     [rbp+90h+var_C0], rax
0x180001bcc  lea     rax, aNumflushes; "NumFlushes"
0x180001bd3  mov     [rbp+90h+var_28], rax
0x180001bd7  mov     eax, 14h
0x180001bdc  mov     [rbp+90h+var_20], ax
0x180001be0  mov     rax, [rdi+148h]
0x180001be7  mov     [rbp+90h+var_80], cx
0x180001beb  mov     [rbp+90h+var_70], cx
0x180001bef  mov     ecx, 22h ; '"'
0x180001bf4  mov     [rbp+90h+var_104], r8d
0x180001bf8  mov     [rbp+90h+var_10F], 4
0x180001bfc  mov     [rbp+90h+var_10E], 4
0x180001c00  mov     [rbp+90h+var_10D], 4
0x180001c04  mov     [rbp+90h+var_10C], 4
0x180001c08  mov     [rbp+90h+var_60], cx
0x180001c0c  mov     [rbp+90h+var_10B], 4
0x180001c10  mov     [rbp+90h+var_50], cx
0x180001c14  mov     [rbp+90h+var_10A], 4
0x180001c18  mov     [rbp+90h+var_109], 4
0x180001c1c  mov     [rbp+90h+var_108], 4
0x180001c20  mov     rcx, [rax+8]
0x180001c24  lea     rax, [rbp+90h+var_18]
0x180001c28  mov     [rbp+90h+var_B8], rax
0x180001c2c  lea     rax, [rbp+90h+var_110]
0x180001c30  mov     [rsp+230h+var_118], rax
0x180001c38  lea     rax, [rbp+90h+var_104]
0x180001c3c  mov     [rsp+230h+var_120], rax
0x180001c44  lea     rax, [rbp+90h+var_A8]
0x180001c48  movups  xmm0, xmmword ptr [rcx-10h]
0x180001c4c  mov     [rsp+230h+var_128], rax
0x180001c54  lea     rax, [rbp+90h+var_10F]
0x180001c58  mov     [rsp+230h+var_130], rax
0x180001c60  lea     rax, [rbp+90h+var_F8]
0x180001c64  mov     [rsp+230h+var_138], rax
0x180001c6c  lea     rax, [rbp+90h+var_98]
0x180001c70  mov     [rsp+230h+var_140], rax
0x180001c78  movups  [rbp+90h+var_18], xmm0
0x180001c7c  mov     [rbp+90h+var_107], 0
0x180001c80  mov     [rbp+90h+var_100], 0FFFFFFFFh
0x180001c87  mov     [rbp+90h+var_FC], 12Ch
0x180001c8e  mov     [rbp+90h+var_B0], 1000000h
0x180001c96  lea     rax, [rbp+90h+var_10E]
0x180001c9a  mov     [rsp+230h+var_148], rax
0x180001ca2  lea     rdx, unk_18000EE40
0x180001ca9  lea     rax, [rbp+90h+var_F0]
0x180001cad  mov     [rsp+230h+var_150], rax
0x180001cb5  lea     rax, [rbp+90h+var_88]
0x180001cb9  mov     [rsp+230h+var_158], rax
0x180001cc1  lea     rax, [rbp+90h+var_10D]
0x180001cc5  mov     [rsp+230h+var_160], rax
0x180001ccd  lea     rax, [rbp+90h+var_E8]
0x180001cd1  mov     [rsp+230h+var_168], rax
0x180001cd9  lea     rax, [rbp+90h+var_78]
0x180001cdd  mov     [rsp+230h+var_170], rax
0x180001ce5  lea     rax, [rbp+90h+var_10C]
0x180001ce9  mov     [rsp+230h+var_178], rax
0x180001cf1  lea     rax, [rbp+90h+var_E0]
0x180001cf5  mov     [rsp+230h+var_180], rax
0x180001cfd  lea     rax, [rbp+90h+var_68]
0x180001d01  mov     [rsp+230h+var_188], rax
0x180001d09  lea     rax, [rbp+90h+var_10B]
0x180001d0d  mov     [rsp+230h+var_190], rax
0x180001d15  lea     rax, [rbp+90h+var_D8]
0x180001d19  mov     [rsp+230h+var_198], rax
0x180001d21  lea     rax, [rbp+90h+var_58]
0x180001d25  mov     [rsp+230h+var_1A0], rax
0x180001d2d  lea     rax, [rbp+90h+var_10A]
0x180001d31  mov     [rsp+230h+var_1A8], rax
0x180001d39  lea     rax, [rbp+90h+var_D0]
0x180001d3d  mov     [rsp+230h+var_1B0], rax
0x180001d45  lea     rax, [rbp+90h+var_48]
0x180001d49  mov     [rsp+230h+var_1B8], rax
0x180001d4e  lea     rax, [rbp+90h+var_109]
0x180001d52  mov     [rsp+230h+var_1C0], rax
0x180001d57  lea     rax, [rbp+90h+var_C8]
0x180001d5b  mov     [rsp+230h+var_1C8], rax
0x180001d60  lea     rax, [rbp+90h+var_38]
0x180001d64  mov     [rsp+230h+var_1D0], rax
0x180001d69  lea     rax, [rbp+90h+var_108]
0x180001d6d  mov     [rsp+230h+var_1D8], rax
0x180001d72  lea     rax, [rbp+90h+var_C0]
0x180001d76  mov     [rsp+230h+var_1E0], rax
0x180001d7b  lea     rax, [rbp+90h+var_28]
0x180001d7f  mov     [rsp+230h+var_1E8], rax
0x180001d84  lea     rax, [rbp+90h+var_B8]
0x180001d88  mov     [rsp+230h+var_1F0], rax
0x180001d8d  lea     rax, [rbp+90h+var_107]
0x180001d91  mov     [rsp+230h+var_1F8], rax
0x180001d96  lea     rax, [rbp+90h+var_100]
0x180001d9a  mov     [rsp+230h+var_200], rax
0x180001d9f  lea     rax, [rbp+90h+var_FC]
0x180001da3  mov     [rsp+230h+var_208], rax
0x180001da8  lea     rax, [rbp+90h+var_B0]
0x180001dac  mov     [rsp+230h+var_210], rax
0x180001db1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180001db6  xorps   xmm0, xmm0
0x180001db9  xor     eax, eax
0x180001dbb  movups  xmmword ptr [rdi+110h], xmm0
0x180001dc2  movups  xmmword ptr [rdi+120h], xmm0
0x180001dc9  mov     [rdi+130h], rax
0x180001dd0  xor     ebx, ebx
0x180001dd2  mov     edx, ebx
0x180001dd4  mov     rcx, rdi
0x180001dd7  call    FlushLookUpTableBucket
0x180001ddc  inc     ebx
0x180001dde  cmp     ebx, 20h ; ' '
0x180001de1  jb      short loc_180001DD2
0x180001de3  mov     rbx, [rsp+230h+arg_8]
0x180001deb  mov     rcx, [rbp+90h+var_8]
0x180001df2  xor     rcx, rsp; StackCookie
0x180001df5  call    __security_check_cookie
0x180001dfa  mov     rdi, [rsp+230h+arg_10]
0x180001e02  add     rsp, 230h
0x180001e09  pop     rbp
0x180001e0a  retn
```
