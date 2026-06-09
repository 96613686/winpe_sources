# LookUpTableFlushComplete

- ea: `0x18000444c`
- end: `0x180004829`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: `__int64 __fastcall(const __m128i *, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800040d0`
- `0x1800048c0`
- `0x180004920`
- `0x180004b50`

## callees

- `0x180001008`
- `0x180003fac`
- `0x18000444c`
- `0x180004f20`

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
      if ( (unsigned int)dword_18000A040 > 5
        && (qword_18000A050 & 0x200000000000LL) != 0
        && (qword_18000A058 & 0x200000000000LL) == qword_18000A058 )
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
          (__int64)&word_1800082D6,
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
0x18000444c  mov     [rsp-8+arg_8], rbx
0x180004451  mov     [rsp-8+arg_10], rsi
0x180004456  push    rbp
0x180004457  push    rdi
0x180004458  push    r14
0x18000445a  lea     rbp, [rsp-90h]
0x180004462  sub     rsp, 230h
0x180004469  mov     rax, cs:__security_cookie
0x180004470  xor     rax, rsp
0x180004473  mov     [rbp+0A0h+var_18], rax
0x18000447a  mov     eax, [rcx+100h]
0x180004480  xor     edi, edi
0x180004482  mov     rbx, rcx
0x180004485  test    eax, eax
0x180004487  jz      loc_180004802
0x18000448d  cmp     [rcx+128h], eax
0x180004493  ja      short loc_18000449E
0x180004495  cmp     [rcx+118h], rdi
0x18000449c  jnz     short loc_1800044A4
0x18000449e  mov     [rcx+128h], eax
0x1800044a4  cmp     [rcx+124h], eax
0x1800044aa  jnb     short loc_1800044B2
0x1800044ac  mov     [rcx+124h], eax
0x1800044b2  mov     esi, 1
0x1800044b7  movq    xmm1, rax
0x1800044bc  movq    xmm0, rsi
0x1800044c1  lea     r14d, [rsi+1Fh]
0x1800044c5  punpcklqdq xmm1, xmm0
0x1800044c9  movdqu  xmm0, xmmword ptr [rcx+110h]
0x1800044d1  paddq   xmm1, xmm0
0x1800044d5  movdqu  xmmword ptr [rcx+110h], xmm1
0x1800044dd  cmp     [rcx+110h], rdi
0x1800044e4  jz      loc_1800047F1
0x1800044ea  mov     eax, cs:dword_18000A040
0x1800044f0  cmp     eax, 5
0x1800044f3  jbe     loc_1800047D7
0x1800044f9  mov     rcx, cs:qword_18000A058
0x180004500  mov     rdx, 200000000000h
0x18000450a  mov     rax, cs:qword_18000A050
0x180004511  test    rdx, rax
0x180004514  jz      loc_1800047D7
0x18000451a  mov     rax, rcx
0x18000451d  and     rax, rdx
0x180004520  cmp     rax, rcx
0x180004523  jnz     loc_1800047D7
0x180004529  lea     ecx, [rsi+29h]
0x18000452c  mov     [rbp+0A0h+var_120], 4
0x180004530  lea     rax, aSummarycount; "SummaryCount"
0x180004537  mov     [rbp+0A0h+var_A0], cx
0x18000453b  mov     [rbp+0A0h+var_B8], rax
0x18000453f  lea     eax, [rsi+17h]
0x180004542  mov     [rbp+0A0h+var_B0], ax
0x180004546  mov     eax, [rbx+134h]
0x18000454c  mov     [rbp+0A0h+var_108], rax
0x180004550  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x180004557  mov     [rbp+0A0h+var_A8], rax
0x18000455b  mov     eax, [rbx+130h]
0x180004561  mov     [rbp+0A0h+var_100], rax
0x180004565  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18000456c  mov     [rbp+0A0h+var_98], rax
0x180004570  mov     eax, [rbx+12Ch]
0x180004576  mov     [rbp+0A0h+var_F8], rax
0x18000457a  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x180004581  mov     [rbp+0A0h+var_88], rax
0x180004585  mov     eax, [rbx+128h]
0x18000458b  mov     [rbp+0A0h+var_F0], rax
0x18000458f  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180004596  mov     [rbp+0A0h+var_78], rax
0x18000459a  mov     eax, [rbx+124h]
0x1800045a0  mov     [rbp+0A0h+var_E8], rax
0x1800045a4  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x1800045ab  mov     [rbp+0A0h+var_68], rax
0x1800045af  mov     rax, [rbx+110h]
0x1800045b6  mov     [rbp+0A0h+var_E0], rax
0x1800045ba  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x1800045c1  mov     [rbp+0A0h+var_58], rax
0x1800045c5  lea     eax, [rsi+25h]
0x1800045c8  mov     [rbp+0A0h+var_50], ax
0x1800045cc  mov     eax, [rbx+120h]
0x1800045d2  mov     [rbp+0A0h+var_D8], rax
0x1800045d6  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x1800045dd  mov     [rbp+0A0h+var_48], rax
0x1800045e1  mov     rax, [rbx+118h]
0x1800045e8  mov     [rbp+0A0h+var_D0], rax
0x1800045ec  lea     rax, aNumflushes; "NumFlushes"
0x1800045f3  mov     [rbp+0A0h+var_38], rax
0x1800045f7  lea     eax, [rsi+13h]
0x1800045fa  mov     [rbp+0A0h+var_30], ax
0x1800045fe  mov     rax, [rbx+148h]
0x180004605  mov     [rbp+0A0h+var_90], cx
0x180004609  mov     [rbp+0A0h+var_80], cx
0x18000460d  lea     ecx, [rsi+21h]
0x180004610  mov     [rbp+0A0h+var_114], esi
0x180004613  mov     [rbp+0A0h+var_11F], 4
0x180004617  mov     [rbp+0A0h+var_11E], 4
0x18000461b  mov     [rbp+0A0h+var_11D], 4
0x18000461f  mov     [rbp+0A0h+var_11C], 4
0x180004623  mov     [rbp+0A0h+var_70], cx
0x180004627  mov     [rbp+0A0h+var_11B], 4
0x18000462b  mov     [rbp+0A0h+var_60], cx
0x18000462f  mov     [rbp+0A0h+var_11A], 4
0x180004633  mov     [rbp+0A0h+var_119], 4
0x180004637  mov     [rbp+0A0h+var_40], r14w
0x18000463c  mov     [rbp+0A0h+var_118], 4
0x180004640  mov     rcx, [rax+8]
0x180004644  lea     rax, [rbp+0A0h+var_28]
0x180004648  mov     [rbp+0A0h+var_C8], rax
0x18000464c  lea     rax, [rbp+0A0h+var_120]
0x180004650  mov     [rsp+240h+var_128], rax
0x180004658  lea     rax, [rbp+0A0h+var_114]
0x18000465c  mov     [rsp+240h+var_130], rax
0x180004664  lea     rax, [rbp+0A0h+var_B8]
0x180004668  movups  xmm0, xmmword ptr [rcx-10h]
0x18000466c  mov     [rsp+240h+var_138], rax
0x180004674  lea     rax, [rbp+0A0h+var_11F]
0x180004678  mov     [rsp+240h+var_140], rax
0x180004680  lea     rax, [rbp+0A0h+var_108]
0x180004684  mov     [rsp+240h+var_148], rax
0x18000468c  lea     rax, [rbp+0A0h+var_A8]
0x180004690  mov     [rsp+240h+var_150], rax
0x180004698  lea     rax, [rbp+0A0h+var_11E]
0x18000469c  movdqu  [rbp+0A0h+var_28], xmm0
0x1800046a1  mov     [rbp+0A0h+var_117], dil
0x1800046a5  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x1800046ac  mov     [rbp+0A0h+var_10C], 12Ch
0x1800046b3  mov     [rbp+0A0h+var_C0], 1000000h
0x1800046bb  mov     [rsp+240h+var_158], rax
0x1800046c3  lea     rdx, word_1800082D6
0x1800046ca  lea     rax, [rbp+0A0h+var_100]
0x1800046ce  mov     [rsp+240h+var_160], rax
0x1800046d6  lea     rax, [rbp+0A0h+var_98]
0x1800046da  mov     [rsp+240h+var_168], rax
0x1800046e2  lea     rax, [rbp+0A0h+var_11D]
0x1800046e6  mov     [rsp+240h+var_170], rax
0x1800046ee  lea     rax, [rbp+0A0h+var_F8]
0x1800046f2  mov     [rsp+240h+var_178], rax
0x1800046fa  lea     rax, [rbp+0A0h+var_88]
0x1800046fe  mov     [rsp+240h+var_180], rax
0x180004706  lea     rax, [rbp+0A0h+var_11C]
0x18000470a  mov     [rsp+240h+var_188], rax
0x180004712  lea     rax, [rbp+0A0h+var_F0]
0x180004716  mov     [rsp+240h+var_190], rax
0x18000471e  lea     rax, [rbp+0A0h+var_78]
0x180004722  mov     [rsp+240h+var_198], rax
0x18000472a  lea     rax, [rbp+0A0h+var_11B]
0x18000472e  mov     [rsp+240h+var_1A0], rax
0x180004736  lea     rax, [rbp+0A0h+var_E8]
0x18000473a  mov     [rsp+240h+var_1A8], rax
0x180004742  lea     rax, [rbp+0A0h+var_68]
0x180004746  mov     [rsp+240h+var_1B0], rax
0x18000474e  lea     rax, [rbp+0A0h+var_11A]
0x180004752  mov     [rsp+240h+var_1B8], rax
0x18000475a  lea     rax, [rbp+0A0h+var_E0]
0x18000475e  mov     [rsp+240h+var_1C0], rax
0x180004766  lea     rax, [rbp+0A0h+var_58]
0x18000476a  mov     [rsp+240h+var_1C8], rax
0x18000476f  lea     rax, [rbp+0A0h+var_119]
0x180004773  mov     [rsp+240h+var_1D0], rax
0x180004778  lea     rax, [rbp+0A0h+var_D8]
0x18000477c  mov     [rsp+240h+var_1D8], rax
0x180004781  lea     rax, [rbp+0A0h+var_48]
0x180004785  mov     [rsp+240h+var_1E0], rax
0x18000478a  lea     rax, [rbp+0A0h+var_118]
0x18000478e  mov     [rsp+240h+var_1E8], rax
0x180004793  lea     rax, [rbp+0A0h+var_D0]
0x180004797  mov     [rsp+240h+var_1F0], rax
0x18000479c  lea     rax, [rbp+0A0h+var_38]
0x1800047a0  mov     [rsp+240h+var_1F8], rax
0x1800047a5  lea     rax, [rbp+0A0h+var_C8]
0x1800047a9  mov     [rsp+240h+var_200], rax
0x1800047ae  lea     rax, [rbp+0A0h+var_117]
0x1800047b2  mov     [rsp+240h+var_208], rax
0x1800047b7  lea     rax, [rbp+0A0h+var_110]
0x1800047bb  mov     [rsp+240h+var_210], rax
0x1800047c0  lea     rax, [rbp+0A0h+var_10C]
0x1800047c4  mov     [rsp+240h+var_218], rax
0x1800047c9  lea     rax, [rbp+0A0h+var_C0]
0x1800047cd  mov     [rsp+240h+var_220], rax
0x1800047d2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1800047d7  xorps   xmm0, xmm0
0x1800047da  xor     eax, eax
0x1800047dc  movups  xmmword ptr [rbx+110h], xmm0
0x1800047e3  movups  xmmword ptr [rbx+120h], xmm0
0x1800047ea  mov     [rbx+130h], rax
0x1800047f1  mov     edx, edi
0x1800047f3  mov     rcx, rbx
0x1800047f6  call    FlushLookUpTableBucket
0x1800047fb  add     edi, esi
0x1800047fd  cmp     edi, r14d
0x180004800  jb      short loc_1800047F1
0x180004802  mov     rcx, [rbp+0A0h+var_18]
0x180004809  xor     rcx, rsp; StackCookie
0x18000480c  call    __security_check_cookie
0x180004811  lea     r11, [rsp+240h+var_10]
0x180004819  mov     rbx, [r11+28h]
0x18000481d  mov     rsi, [r11+30h]
0x180004821  mov     rsp, r11
0x180004824  pop     r14
0x180004826  pop     rdi
0x180004827  pop     rbp
0x180004828  retn
```
