# LookUpTableFlushComplete

- ea: `0x18001ebcc`
- end: `0x18001efa9`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e850`
- `0x18001f040`
- `0x18001f0a0`
- `0x18001f2d0`

## callees

- `0x1800011dc`
- `0x18001e72c`
- `0x18001ebcc`
- `0x18001f690`

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
      if ( (unsigned int)dword_18002F390 > 5
        && (qword_18002F3A0 & 0x200000000000LL) != 0
        && (qword_18002F3A8 & 0x200000000000LL) == qword_18002F3A8 )
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
          (__int64)&byte_1800290BF,
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
0x18001ebcc  mov     [rsp-8+arg_8], rbx
0x18001ebd1  mov     [rsp-8+arg_10], rsi
0x18001ebd6  push    rbp
0x18001ebd7  push    rdi
0x18001ebd8  push    r14
0x18001ebda  lea     rbp, [rsp-90h]
0x18001ebe2  sub     rsp, 230h
0x18001ebe9  mov     rax, cs:__security_cookie
0x18001ebf0  xor     rax, rsp
0x18001ebf3  mov     [rbp+0A0h+var_18], rax
0x18001ebfa  mov     eax, [rcx+100h]
0x18001ec00  xor     edi, edi
0x18001ec02  mov     rbx, rcx
0x18001ec05  test    eax, eax
0x18001ec07  jz      loc_18001EF82
0x18001ec0d  cmp     [rcx+128h], eax
0x18001ec13  ja      short loc_18001EC1E
0x18001ec15  cmp     [rcx+118h], rdi
0x18001ec1c  jnz     short loc_18001EC24
0x18001ec1e  mov     [rcx+128h], eax
0x18001ec24  cmp     [rcx+124h], eax
0x18001ec2a  jnb     short loc_18001EC32
0x18001ec2c  mov     [rcx+124h], eax
0x18001ec32  mov     esi, 1
0x18001ec37  movq    xmm1, rax
0x18001ec3c  movq    xmm0, rsi
0x18001ec41  lea     r14d, [rsi+1Fh]
0x18001ec45  punpcklqdq xmm1, xmm0
0x18001ec49  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18001ec51  paddq   xmm1, xmm0
0x18001ec55  movdqu  xmmword ptr [rcx+110h], xmm1
0x18001ec5d  cmp     [rcx+110h], rdi
0x18001ec64  jz      loc_18001EF71
0x18001ec6a  mov     eax, cs:dword_18002F390
0x18001ec70  cmp     eax, 5
0x18001ec73  jbe     loc_18001EF57
0x18001ec79  mov     rcx, cs:qword_18002F3A8
0x18001ec80  mov     rdx, 200000000000h
0x18001ec8a  mov     rax, cs:qword_18002F3A0
0x18001ec91  test    rdx, rax
0x18001ec94  jz      loc_18001EF57
0x18001ec9a  mov     rax, rcx
0x18001ec9d  and     rax, rdx
0x18001eca0  cmp     rax, rcx
0x18001eca3  jnz     loc_18001EF57
0x18001eca9  lea     ecx, [rsi+29h]
0x18001ecac  mov     [rbp+0A0h+var_120], 4
0x18001ecb0  lea     rax, aSummarycount; "SummaryCount"
0x18001ecb7  mov     [rbp+0A0h+var_A0], cx
0x18001ecbb  mov     [rbp+0A0h+var_B8], rax
0x18001ecbf  lea     eax, [rsi+17h]
0x18001ecc2  mov     [rbp+0A0h+var_B0], ax
0x18001ecc6  mov     eax, [rbx+134h]
0x18001eccc  mov     [rbp+0A0h+var_108], rax
0x18001ecd0  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18001ecd7  mov     [rbp+0A0h+var_A8], rax
0x18001ecdb  mov     eax, [rbx+130h]
0x18001ece1  mov     [rbp+0A0h+var_100], rax
0x18001ece5  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18001ecec  mov     [rbp+0A0h+var_98], rax
0x18001ecf0  mov     eax, [rbx+12Ch]
0x18001ecf6  mov     [rbp+0A0h+var_F8], rax
0x18001ecfa  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18001ed01  mov     [rbp+0A0h+var_88], rax
0x18001ed05  mov     eax, [rbx+128h]
0x18001ed0b  mov     [rbp+0A0h+var_F0], rax
0x18001ed0f  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18001ed16  mov     [rbp+0A0h+var_78], rax
0x18001ed1a  mov     eax, [rbx+124h]
0x18001ed20  mov     [rbp+0A0h+var_E8], rax
0x18001ed24  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18001ed2b  mov     [rbp+0A0h+var_68], rax
0x18001ed2f  mov     rax, [rbx+110h]
0x18001ed36  mov     [rbp+0A0h+var_E0], rax
0x18001ed3a  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18001ed41  mov     [rbp+0A0h+var_58], rax
0x18001ed45  lea     eax, [rsi+25h]
0x18001ed48  mov     [rbp+0A0h+var_50], ax
0x18001ed4c  mov     eax, [rbx+120h]
0x18001ed52  mov     [rbp+0A0h+var_D8], rax
0x18001ed56  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001ed5d  mov     [rbp+0A0h+var_48], rax
0x18001ed61  mov     rax, [rbx+118h]
0x18001ed68  mov     [rbp+0A0h+var_D0], rax
0x18001ed6c  lea     rax, aNumflushes; "NumFlushes"
0x18001ed73  mov     [rbp+0A0h+var_38], rax
0x18001ed77  lea     eax, [rsi+13h]
0x18001ed7a  mov     [rbp+0A0h+var_30], ax
0x18001ed7e  mov     rax, [rbx+148h]
0x18001ed85  mov     [rbp+0A0h+var_90], cx
0x18001ed89  mov     [rbp+0A0h+var_80], cx
0x18001ed8d  lea     ecx, [rsi+21h]
0x18001ed90  mov     [rbp+0A0h+var_114], esi
0x18001ed93  mov     [rbp+0A0h+var_11F], 4
0x18001ed97  mov     [rbp+0A0h+var_11E], 4
0x18001ed9b  mov     [rbp+0A0h+var_11D], 4
0x18001ed9f  mov     [rbp+0A0h+var_11C], 4
0x18001eda3  mov     [rbp+0A0h+var_70], cx
0x18001eda7  mov     [rbp+0A0h+var_11B], 4
0x18001edab  mov     [rbp+0A0h+var_60], cx
0x18001edaf  mov     [rbp+0A0h+var_11A], 4
0x18001edb3  mov     [rbp+0A0h+var_119], 4
0x18001edb7  mov     [rbp+0A0h+var_40], r14w
0x18001edbc  mov     [rbp+0A0h+var_118], 4
0x18001edc0  mov     rcx, [rax+8]
0x18001edc4  lea     rax, [rbp+0A0h+var_28]
0x18001edc8  mov     [rbp+0A0h+var_C8], rax
0x18001edcc  lea     rax, [rbp+0A0h+var_120]
0x18001edd0  mov     [rsp+240h+var_128], rax
0x18001edd8  lea     rax, [rbp+0A0h+var_114]
0x18001eddc  mov     [rsp+240h+var_130], rax
0x18001ede4  lea     rax, [rbp+0A0h+var_B8]
0x18001ede8  movups  xmm0, xmmword ptr [rcx-10h]
0x18001edec  mov     [rsp+240h+var_138], rax
0x18001edf4  lea     rax, [rbp+0A0h+var_11F]
0x18001edf8  mov     [rsp+240h+var_140], rax
0x18001ee00  lea     rax, [rbp+0A0h+var_108]
0x18001ee04  mov     [rsp+240h+var_148], rax
0x18001ee0c  lea     rax, [rbp+0A0h+var_A8]
0x18001ee10  mov     [rsp+240h+var_150], rax
0x18001ee18  lea     rax, [rbp+0A0h+var_11E]
0x18001ee1c  movdqu  [rbp+0A0h+var_28], xmm0
0x18001ee21  mov     [rbp+0A0h+var_117], dil
0x18001ee25  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x18001ee2c  mov     [rbp+0A0h+var_10C], 12Ch
0x18001ee33  mov     [rbp+0A0h+var_C0], 1000000h
0x18001ee3b  mov     [rsp+240h+var_158], rax
0x18001ee43  lea     rdx, byte_1800290BF
0x18001ee4a  lea     rax, [rbp+0A0h+var_100]
0x18001ee4e  mov     [rsp+240h+var_160], rax
0x18001ee56  lea     rax, [rbp+0A0h+var_98]
0x18001ee5a  mov     [rsp+240h+var_168], rax
0x18001ee62  lea     rax, [rbp+0A0h+var_11D]
0x18001ee66  mov     [rsp+240h+var_170], rax
0x18001ee6e  lea     rax, [rbp+0A0h+var_F8]
0x18001ee72  mov     [rsp+240h+var_178], rax
0x18001ee7a  lea     rax, [rbp+0A0h+var_88]
0x18001ee7e  mov     [rsp+240h+var_180], rax
0x18001ee86  lea     rax, [rbp+0A0h+var_11C]
0x18001ee8a  mov     [rsp+240h+var_188], rax
0x18001ee92  lea     rax, [rbp+0A0h+var_F0]
0x18001ee96  mov     [rsp+240h+var_190], rax
0x18001ee9e  lea     rax, [rbp+0A0h+var_78]
0x18001eea2  mov     [rsp+240h+var_198], rax
0x18001eeaa  lea     rax, [rbp+0A0h+var_11B]
0x18001eeae  mov     [rsp+240h+var_1A0], rax
0x18001eeb6  lea     rax, [rbp+0A0h+var_E8]
0x18001eeba  mov     [rsp+240h+var_1A8], rax
0x18001eec2  lea     rax, [rbp+0A0h+var_68]
0x18001eec6  mov     [rsp+240h+var_1B0], rax
0x18001eece  lea     rax, [rbp+0A0h+var_11A]
0x18001eed2  mov     [rsp+240h+var_1B8], rax
0x18001eeda  lea     rax, [rbp+0A0h+var_E0]
0x18001eede  mov     [rsp+240h+var_1C0], rax
0x18001eee6  lea     rax, [rbp+0A0h+var_58]
0x18001eeea  mov     [rsp+240h+var_1C8], rax
0x18001eeef  lea     rax, [rbp+0A0h+var_119]
0x18001eef3  mov     [rsp+240h+var_1D0], rax
0x18001eef8  lea     rax, [rbp+0A0h+var_D8]
0x18001eefc  mov     [rsp+240h+var_1D8], rax
0x18001ef01  lea     rax, [rbp+0A0h+var_48]
0x18001ef05  mov     [rsp+240h+var_1E0], rax
0x18001ef0a  lea     rax, [rbp+0A0h+var_118]
0x18001ef0e  mov     [rsp+240h+var_1E8], rax
0x18001ef13  lea     rax, [rbp+0A0h+var_D0]
0x18001ef17  mov     [rsp+240h+var_1F0], rax
0x18001ef1c  lea     rax, [rbp+0A0h+var_38]
0x18001ef20  mov     [rsp+240h+var_1F8], rax
0x18001ef25  lea     rax, [rbp+0A0h+var_C8]
0x18001ef29  mov     [rsp+240h+var_200], rax
0x18001ef2e  lea     rax, [rbp+0A0h+var_117]
0x18001ef32  mov     [rsp+240h+var_208], rax
0x18001ef37  lea     rax, [rbp+0A0h+var_110]
0x18001ef3b  mov     [rsp+240h+var_210], rax
0x18001ef40  lea     rax, [rbp+0A0h+var_10C]
0x18001ef44  mov     [rsp+240h+var_218], rax
0x18001ef49  lea     rax, [rbp+0A0h+var_C0]
0x18001ef4d  mov     [rsp+240h+var_220], rax
0x18001ef52  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18001ef57  xorps   xmm0, xmm0
0x18001ef5a  xor     eax, eax
0x18001ef5c  movups  xmmword ptr [rbx+110h], xmm0
0x18001ef63  movups  xmmword ptr [rbx+120h], xmm0
0x18001ef6a  mov     [rbx+130h], rax
0x18001ef71  mov     edx, edi
0x18001ef73  mov     rcx, rbx
0x18001ef76  call    FlushLookUpTableBucket
0x18001ef7b  add     edi, esi
0x18001ef7d  cmp     edi, r14d
0x18001ef80  jb      short loc_18001EF71
0x18001ef82  mov     rcx, [rbp+0A0h+var_18]
0x18001ef89  xor     rcx, rsp; StackCookie
0x18001ef8c  call    __security_check_cookie
0x18001ef91  lea     r11, [rsp+240h+var_10]
0x18001ef99  mov     rbx, [r11+28h]
0x18001ef9d  mov     rsi, [r11+30h]
0x18001efa1  mov     rsp, r11
0x18001efa4  pop     r14
0x18001efa6  pop     rdi
0x18001efa7  pop     rbp
0x18001efa8  retn
```
