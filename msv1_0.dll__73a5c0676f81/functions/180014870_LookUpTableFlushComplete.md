# LookUpTableFlushComplete

- ea: `0x180014870`
- end: `0x180014dab`
- name: `LookUpTableFlushComplete`
- size: `1339`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800147f0`
- `0x18001efd0`
- `0x18001f5c0`
- `0x18005c0a0`

## callees

- `0x1800020fc`
- `0x180014870`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014cbe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014cbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014d52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014d52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014d44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014d44`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014d37`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014d37`

## pseudocode

```c
int __fastcall LookUpTableFlushComplete(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned __int64 v4; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 i; // r15
  __int64 v9; // rdi
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 *v15; // rcx
  REGHANDLE j; // r14
  PEVENT_DATA_DESCRIPTOR *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  PEVENT_DATA_DESCRIPTOR v20; // rbx
  HANDLE ProcessHeap; // rax
  char v23; // [rsp+128h] [rbp-80h] BYREF
  char v24; // [rsp+129h] [rbp-7Fh] BYREF
  char v25; // [rsp+12Ah] [rbp-7Eh] BYREF
  char v26; // [rsp+12Bh] [rbp-7Dh] BYREF
  char v27; // [rsp+12Ch] [rbp-7Ch] BYREF
  char v28; // [rsp+12Dh] [rbp-7Bh] BYREF
  char v29; // [rsp+12Eh] [rbp-7Ah] BYREF
  char v30; // [rsp+12Fh] [rbp-79h] BYREF
  char v31; // [rsp+130h] [rbp-78h] BYREF
  char v32[3]; // [rsp+131h] [rbp-77h] BYREF
  int v33; // [rsp+134h] [rbp-74h] BYREF
  int v34; // [rsp+138h] [rbp-70h] BYREF
  int v35; // [rsp+13Ch] [rbp-6Ch] BYREF
  __int64 v36; // [rsp+140h] [rbp-68h] BYREF
  __int64 v37; // [rsp+148h] [rbp-60h] BYREF
  __int64 v38; // [rsp+150h] [rbp-58h] BYREF
  __int64 v39; // [rsp+158h] [rbp-50h] BYREF
  __int64 v40; // [rsp+160h] [rbp-48h] BYREF
  __int64 v41; // [rsp+168h] [rbp-40h] BYREF
  __int64 v42; // [rsp+170h] [rbp-38h] BYREF
  __int64 v43; // [rsp+178h] [rbp-30h] BYREF
  __int128 *v44; // [rsp+180h] [rbp-28h] BYREF
  __int64 v45; // [rsp+188h] [rbp-20h] BYREF
  const wchar_t *v46; // [rsp+190h] [rbp-18h] BYREF
  __int16 v47; // [rsp+198h] [rbp-10h]
  const wchar_t *v48; // [rsp+1A0h] [rbp-8h] BYREF
  __int16 v49; // [rsp+1A8h] [rbp+0h]
  const wchar_t *v50; // [rsp+1B0h] [rbp+8h] BYREF
  __int16 v51; // [rsp+1B8h] [rbp+10h]
  const wchar_t *v52; // [rsp+1C0h] [rbp+18h] BYREF
  __int16 v53; // [rsp+1C8h] [rbp+20h]
  const wchar_t *v54; // [rsp+1D0h] [rbp+28h] BYREF
  __int16 v55; // [rsp+1D8h] [rbp+30h]
  const wchar_t *v56; // [rsp+1E0h] [rbp+38h] BYREF
  __int16 v57; // [rsp+1E8h] [rbp+40h]
  const wchar_t *v58; // [rsp+1F0h] [rbp+48h] BYREF
  __int16 v59; // [rsp+1F8h] [rbp+50h]
  const wchar_t *v60; // [rsp+200h] [rbp+58h] BYREF
  __int16 v61; // [rsp+208h] [rbp+60h]
  const wchar_t *v62; // [rsp+210h] [rbp+68h] BYREF
  __int16 v63; // [rsp+218h] [rbp+70h]
  __int128 v64; // [rsp+220h] [rbp+78h] BYREF

  v4 = *(unsigned int *)(a1 + 256);
  if ( (_DWORD)v4 )
  {
    if ( *(_DWORD *)(a1 + 296) > (unsigned int)v4 || !*(_QWORD *)(a1 + 280) )
      *(_DWORD *)(a1 + 296) = v4;
    if ( *(_DWORD *)(a1 + 292) < (unsigned int)v4 )
      *(_DWORD *)(a1 + 292) = v4;
    *(__m128i *)(a1 + 272) = _mm_add_epi64(
                               _mm_unpacklo_epi64((__m128i)v4, (__m128i)1uLL),
                               _mm_loadu_si128((const __m128i *)(a1 + 272)));
    if ( *(_QWORD *)(a1 + 272) )
    {
      if ( (unsigned int)dword_1800862B8 > 5
        && (qword_1800862C8 & 0x200000000000LL) != 0
        && (qword_1800862D0 & 0x200000000000LL) == qword_1800862D0 )
      {
        v23 = 4;
        v49 = 42;
        v46 = L"SummaryCount";
        v47 = 24;
        v45 = *(unsigned int *)(a1 + 308);
        v48 = L"NumLargeEventFailures";
        v37 = *(unsigned int *)(a1 + 304);
        v50 = L"NumAllocationFailures";
        v38 = *(unsigned int *)(a1 + 300);
        v52 = L"NumBucketLimitReached";
        v39 = *(unsigned int *)(a1 + 296);
        v54 = L"MinEntriesFlushed";
        v40 = *(unsigned int *)(a1 + 292);
        v56 = L"MaxEntriesFlushed";
        v41 = *(_QWORD *)(a1 + 272);
        v58 = L"TotalEntriesFlushed";
        v59 = 38;
        v42 = *(unsigned int *)(a1 + 288);
        v60 = L"MaxEntriesStored";
        v61 = 32;
        v43 = *(_QWORD *)(a1 + 280);
        v62 = L"NumFlushes";
        v63 = 20;
        v6 = *(_QWORD *)(a1 + 328);
        v51 = 42;
        v53 = 42;
        v33 = 1;
        v24 = 4;
        v25 = 4;
        v26 = 4;
        v27 = 4;
        v55 = 34;
        v28 = 4;
        v57 = 34;
        v29 = 4;
        v30 = 4;
        v31 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v44 = &v64;
        v64 = *(_OWORD *)(v7 - 16);
        v32[0] = 0;
        v34 = -1;
        v35 = 300;
        v36 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (unsigned int)byte_18007B199,
          1,
          a4,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)v32,
          (__int64)&v44,
          (__int64)&v62,
          (__int64)&v43,
          (__int64)&v31,
          (__int64)&v60,
          (__int64)&v42,
          (__int64)&v30,
          (__int64)&v58,
          (__int64)&v41,
          (__int64)&v29,
          (__int64)&v56,
          (__int64)&v40,
          (__int64)&v28,
          (__int64)&v54,
          (__int64)&v39,
          (__int64)&v27,
          (__int64)&v52,
          (__int64)&v38,
          (__int64)&v26,
          (__int64)&v50,
          (__int64)&v37,
          (__int64)&v25,
          (__int64)&v48,
          (__int64)&v45,
          (__int64)&v24,
          (__int64)&v46,
          (__int64)&v33,
          (__int64)&v23);
      }
      LODWORD(v4) = 0;
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    for ( i = 0; i != 32; ++i )
    {
      if ( *(_QWORD *)(a1 + 8 * i) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
        v9 = *(_QWORD *)(a1 + 8 * i);
        v10 = 0;
        *(_QWORD *)(a1 + 8 * i) = 0;
        v36 = v9;
        if ( v9 )
        {
          v11 = &v36;
          v12 = v9;
          do
          {
            v13 = *(_QWORD *)(v12 + 32);
            *(_QWORD *)(v12 + 32) = 0;
            v11 = (__int64 *)(*v11 + 24);
            v14 = *v11;
            if ( *v11 )
            {
              do
              {
                v15 = (__int64 *)(v14 + 32);
                v14 = *(_QWORD *)(v14 + 32);
              }
              while ( v14 );
            }
            else
            {
              v15 = v11;
            }
            *v15 = v13;
            ++v10;
            v12 = *v11;
          }
          while ( *v11 );
        }
        *(_DWORD *)(a1 + 256) -= v10;
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 264));
        v4 = *(_QWORD *)(a1 + 328);
        for ( j = *(_QWORD *)(v4 + 32); v9; LODWORD(v4) = HeapFree(ProcessHeap, 0, v20) )
        {
          v17 = (PEVENT_DATA_DESCRIPTOR *)(v9 + 16);
          v18 = 2;
          if ( (unsigned int)*(unsigned __int8 *)(v9 + 45) + 2 > 2 )
          {
            do
            {
              v19 = v18++;
              (*v17)[v19].Reserved1 = 0;
            }
            while ( v18 < *(unsigned __int8 *)(v9 + 45) + 2 );
          }
          EventWriteTransfer(j, (PCEVENT_DESCRIPTOR)v9, 0, 0, *(unsigned __int8 *)(v9 + 44), *v17);
          v9 = *(_QWORD *)(v9 + 24);
          v20 = *v17;
          ProcessHeap = GetProcessHeap();
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180014870  mov     r11, rsp
0x180014873  push    rbp
0x180014874  push    rsi
0x180014875  lea     rbp, [r11-0B8h]
0x18001487c  sub     rsp, 248h
0x180014883  mov     rax, cs:__security_cookie
0x18001488a  xor     rax, rsp
0x18001488d  mov     [rbp+0B0h+var_28], rax
0x180014894  mov     eax, [rcx+100h]
0x18001489a  mov     rsi, rcx
0x18001489d  test    eax, eax
0x18001489f  jz      loc_180014D92
0x1800148a5  mov     [r11+10h], rbx
0x1800148a9  mov     [r11+18h], rdi
0x1800148ad  mov     [r11-18h], r12
0x1800148b1  mov     [r11-20h], r14
0x1800148b5  mov     [r11-28h], r15
0x1800148b9  cmp     [rcx+128h], eax
0x1800148bf  ja      short loc_1800148CB
0x1800148c1  cmp     qword ptr [rcx+118h], 0
0x1800148c9  jnz     short loc_1800148D1
0x1800148cb  mov     [rcx+128h], eax
0x1800148d1  cmp     [rcx+124h], eax
0x1800148d7  jnb     short loc_1800148DF
0x1800148d9  mov     [rcx+124h], eax
0x1800148df  mov     r8d, 1
0x1800148e5  movq    xmm1, rax
0x1800148ea  movq    xmm0, r8
0x1800148ef  punpcklqdq xmm1, xmm0
0x1800148f3  movdqu  xmm0, xmmword ptr [rcx+110h]
0x1800148fb  paddq   xmm1, xmm0
0x1800148ff  movdqu  xmmword ptr [rcx+110h], xmm1
0x180014907  cmp     qword ptr [rcx+110h], 0
0x18001490f  jz      loc_180014C2A
0x180014915  mov     eax, cs:dword_1800862B8
0x18001491b  cmp     eax, 5
0x18001491e  jbe     loc_180014C10
0x180014924  mov     rcx, cs:qword_1800862D0
0x18001492b  mov     rdx, 200000000000h
0x180014935  mov     rax, cs:qword_1800862C8
0x18001493c  test    rdx, rax
0x18001493f  jz      loc_180014C10
0x180014945  mov     rax, rcx
0x180014948  and     rax, rdx
0x18001494b  cmp     rax, rcx
0x18001494e  jnz     loc_180014C10
0x180014954  mov     ecx, 2Ah ; '*'
0x180014959  mov     [rbp+0B0h+var_130], 4
0x18001495d  lea     rax, aSummarycount; "SummaryCount"
0x180014964  mov     [rbp+0B0h+var_B0], cx
0x180014968  mov     [rbp+0B0h+var_C8], rax
0x18001496c  mov     eax, 18h
0x180014971  mov     [rbp+0B0h+var_C0], ax
0x180014975  mov     eax, [rsi+134h]
0x18001497b  mov     [rbp+0B0h+var_D0], rax
0x18001497f  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x180014986  mov     [rbp+0B0h+var_B8], rax
0x18001498a  mov     eax, [rsi+130h]
0x180014990  mov     [rbp+0B0h+var_110], rax
0x180014994  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18001499b  mov     [rbp+0B0h+var_A8], rax
0x18001499f  mov     eax, [rsi+12Ch]
0x1800149a5  mov     [rbp+0B0h+var_108], rax
0x1800149a9  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x1800149b0  mov     [rbp+0B0h+var_98], rax
0x1800149b4  mov     eax, [rsi+128h]
0x1800149ba  mov     [rbp+0B0h+var_100], rax
0x1800149be  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x1800149c5  mov     [rbp+0B0h+var_88], rax
0x1800149c9  mov     eax, [rsi+124h]
0x1800149cf  mov     [rbp+0B0h+var_F8], rax
0x1800149d3  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x1800149da  mov     [rbp+0B0h+var_78], rax
0x1800149de  mov     rax, [rsi+110h]
0x1800149e5  mov     [rbp+0B0h+var_F0], rax
0x1800149e9  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x1800149f0  mov     [rbp+0B0h+var_68], rax
0x1800149f4  mov     eax, 26h ; '&'
0x1800149f9  mov     [rbp+0B0h+var_60], ax
0x1800149fd  mov     eax, [rsi+120h]
0x180014a03  mov     [rbp+0B0h+var_E8], rax
0x180014a07  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180014a0e  mov     [rbp+0B0h+var_58], rax
0x180014a12  mov     eax, 20h ; ' '
0x180014a17  mov     [rbp+0B0h+var_50], ax
0x180014a1b  mov     rax, [rsi+118h]
0x180014a22  mov     [rbp+0B0h+var_E0], rax
0x180014a26  lea     rax, aNumflushes; "NumFlushes"
0x180014a2d  mov     [rbp+0B0h+var_48], rax
0x180014a31  mov     eax, 14h
0x180014a36  mov     [rbp+0B0h+var_40], ax
0x180014a3a  mov     rax, [rsi+148h]
0x180014a41  mov     [rbp+0B0h+var_A0], cx
0x180014a45  mov     [rbp+0B0h+var_90], cx
0x180014a49  mov     ecx, 22h ; '"'
0x180014a4e  mov     [rbp+0B0h+var_124], r8d
0x180014a52  mov     [rbp+0B0h+var_12F], 4
0x180014a56  mov     [rbp+0B0h+var_12E], 4
0x180014a5a  mov     [rbp+0B0h+var_12D], 4
0x180014a5e  mov     [rbp+0B0h+var_12C], 4
0x180014a62  mov     [rbp+0B0h+var_80], cx
0x180014a66  mov     [rbp+0B0h+var_12B], 4
0x180014a6a  mov     [rbp+0B0h+var_70], cx
0x180014a6e  mov     [rbp+0B0h+var_12A], 4
0x180014a72  mov     [rbp+0B0h+var_129], 4
0x180014a76  mov     [rbp+0B0h+var_128], 4
0x180014a7a  mov     rcx, [rax+8]
0x180014a7e  lea     rax, [rbp+0B0h+var_38]
0x180014a82  mov     [rbp+0B0h+var_D8], rax
0x180014a86  lea     rax, [rbp+0B0h+var_130]
0x180014a8a  mov     [rsp+118h], rax
0x180014a92  lea     rax, [rbp+0B0h+var_124]
0x180014a96  mov     [rsp+250h+var_140], rax
0x180014a9e  lea     rax, [rbp+0B0h+var_C8]
0x180014aa2  movups  xmm0, xmmword ptr [rcx-10h]
0x180014aa6  mov     [rsp+250h+var_148], rax
0x180014aae  lea     rax, [rbp+0B0h+var_12F]
0x180014ab2  mov     [rsp+250h+var_150], rax
0x180014aba  lea     rax, [rbp+0B0h+var_D0]
0x180014abe  mov     [rsp+250h+var_158], rax
0x180014ac6  lea     rax, [rbp+0B0h+var_B8]
0x180014aca  mov     [rsp+250h+var_160], rax
0x180014ad2  movups  [rbp+0B0h+var_38], xmm0
0x180014ad6  mov     [rbp+0B0h+var_127], 0
0x180014ada  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x180014ae1  mov     [rbp+0B0h+var_11C], 12Ch
0x180014ae8  mov     [rbp+0B0h+var_118], 1000000h
0x180014af0  lea     rax, [rbp+0B0h+var_12E]
0x180014af4  mov     [rsp+250h+var_168], rax
0x180014afc  lea     rdx, byte_18007B199
0x180014b03  lea     rax, [rbp+0B0h+var_110]
0x180014b07  mov     [rsp+250h+var_170], rax
0x180014b0f  lea     rax, [rbp+0B0h+var_A8]
0x180014b13  mov     [rsp+250h+var_178], rax
0x180014b1b  lea     rax, [rbp+0B0h+var_12D]
0x180014b1f  mov     [rsp+250h+var_180], rax
0x180014b27  lea     rax, [rbp+0B0h+var_108]
0x180014b2b  mov     [rsp+250h+var_188], rax
0x180014b33  lea     rax, [rbp+0B0h+var_98]
0x180014b37  mov     [rsp+250h+var_190], rax
0x180014b3f  lea     rax, [rbp+0B0h+var_12C]
0x180014b43  mov     [rsp+250h+var_198], rax
0x180014b4b  lea     rax, [rbp+0B0h+var_100]
0x180014b4f  mov     [rsp+250h+var_1A0], rax
0x180014b57  lea     rax, [rbp+0B0h+var_88]
0x180014b5b  mov     [rsp+250h+var_1A8], rax
0x180014b63  lea     rax, [rbp+0B0h+var_12B]
0x180014b67  mov     [rsp+250h+var_1B0], rax
0x180014b6f  lea     rax, [rbp+0B0h+var_F8]
0x180014b73  mov     [rsp+250h+var_1B8], rax
0x180014b7b  lea     rax, [rbp+0B0h+var_78]
0x180014b7f  mov     [rsp+250h+var_1C0], rax
0x180014b87  lea     rax, [rbp+0B0h+var_12A]
0x180014b8b  mov     [rsp+250h+var_1C8], rax
0x180014b93  lea     rax, [rbp+0B0h+var_F0]
0x180014b97  mov     [rsp+250h+var_1D0], rax
0x180014b9f  lea     rax, [rbp+0B0h+var_68]
0x180014ba3  mov     [rsp+250h+var_1D8], rax
0x180014ba8  lea     rax, [rbp+0B0h+var_129]
0x180014bac  mov     [rsp+250h+var_1E0], rax
0x180014bb1  lea     rax, [rbp+0B0h+var_E8]
0x180014bb5  mov     [rsp+250h+var_1E8], rax
0x180014bba  lea     rax, [rbp+0B0h+var_58]
0x180014bbe  mov     [rsp+250h+var_1F0], rax
0x180014bc3  lea     rax, [rbp+0B0h+var_128]
0x180014bc7  mov     [rsp+250h+var_1F8], rax
0x180014bcc  lea     rax, [rbp+0B0h+var_E0]
0x180014bd0  mov     [rsp+250h+var_200], rax
0x180014bd5  lea     rax, [rbp+0B0h+var_48]
0x180014bd9  mov     [rsp+250h+var_208], rax
0x180014bde  lea     rax, [rbp+0B0h+var_D8]
0x180014be2  mov     [rsp+250h+var_210], rax
0x180014be7  lea     rax, [rbp+0B0h+var_127]
0x180014beb  mov     [rsp+250h+var_218], rax
0x180014bf0  lea     rax, [rbp+0B0h+var_120]
0x180014bf4  mov     [rsp+250h+var_220], rax
0x180014bf9  lea     rax, [rbp+0B0h+var_11C]
0x180014bfd  mov     [rsp+250h+UserData], rax
0x180014c02  lea     rax, [rbp+0B0h+var_118]
0x180014c06  mov     qword ptr [rsp+250h+UserDataCount], rax
0x180014c0b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180014c10  xorps   xmm0, xmm0
0x180014c13  xor     eax, eax
0x180014c15  movups  xmmword ptr [rsi+110h], xmm0
0x180014c1c  movups  xmmword ptr [rsi+120h], xmm0
0x180014c23  mov     [rsi+130h], rax
0x180014c2a  xor     r12d, r12d
0x180014c2d  mov     r15d, r12d
0x180014c30  cmp     [rsi+r15*8], r12
0x180014c34  jz      loc_180014D5D
0x180014c3a  lea     rcx, [rsi+108h]; SRWLock
0x180014c41  call    cs:__imp_AcquireSRWLockExclusive
0x180014c47  mov     rdi, [rsi+r15*8]
0x180014c4b  mov     r8d, r12d
0x180014c4e  mov     [rsi+r15*8], r12
0x180014c52  mov     [rbp+0B0h+var_118], rdi
0x180014c56  test    rdi, rdi
0x180014c59  jz      short loc_180014CB0
0x180014c5b  lea     rdx, [rbp+0B0h+var_118]
0x180014c5f  mov     rax, rdi
0x180014c62  nop     dword ptr [rax+00h]
0x180014c66  nop     word ptr [rax+rax+00000000h]
0x180014c70  mov     r9, [rax+20h]
0x180014c74  mov     [rax+20h], r12
0x180014c78  mov     rdx, [rdx]
0x180014c7b  add     rdx, 18h
0x180014c7f  mov     rax, [rdx]
0x180014c82  test    rax, rax
0x180014c85  jz      short loc_180014C9F
0x180014c87  nop     word ptr [rax+rax+00000000h]
0x180014c90  lea     rcx, [rax+20h]
0x180014c94  mov     rax, [rax+20h]
0x180014c98  test    rax, rax
0x180014c9b  jnz     short loc_180014C90
0x180014c9d  jmp     short loc_180014CA2
0x180014c9f  mov     rcx, rdx
0x180014ca2  mov     [rcx], r9
0x180014ca5  inc     r8d
0x180014ca8  mov     rax, [rdx]
0x180014cab  test    rax, rax
0x180014cae  jnz     short loc_180014C70
0x180014cb0  sub     [rsi+100h], r8d
0x180014cb7  lea     rcx, [rsi+108h]; SRWLock
0x180014cbe  call    cs:__imp_ReleaseSRWLockExclusive
0x180014cc4  mov     rax, [rsi+148h]
0x180014ccb  mov     r14, [rax+20h]
0x180014ccf  test    rdi, rdi
0x180014cd2  jz      loc_180014D5D
0x180014cd8  nop     dword ptr [rax+rax+00000000h]
0x180014ce0  movzx   ecx, byte ptr [rdi+2Dh]
0x180014ce4  lea     rbx, [rdi+10h]
0x180014ce8  mov     eax, 2
0x180014ced  add     ecx, eax
0x180014cef  cmp     ecx, eax
0x180014cf1  jbe     short loc_180014D1B
0x180014cf3  nop     dword ptr [rax+00h]
0x180014cf7  nop     word ptr [rax+rax+00000000h]
0x180014d00  mov     rcx, [rbx]
0x180014d03  movsxd  rdx, eax
0x180014d06  inc     eax
0x180014d08  add     rdx, rdx
0x180014d0b  mov     [rcx+rdx*8+0Dh], r12b
0x180014d10  movzx   ecx, byte ptr [rdi+2Dh]
0x180014d14  add     ecx, 2
0x180014d17  cmp     eax, ecx
0x180014d19  jl      short loc_180014D00
0x180014d1b  movzx   ecx, byte ptr [rdi+2Ch]
0x180014d1f  xor     r9d, r9d; RelatedActivityId
0x180014d22  mov     rax, [rbx]
0x180014d25  xor     r8d, r8d; ActivityId
0x180014d28  mov     [rsp+250h+UserData], rax; UserData
0x180014d2d  mov     rdx, rdi; EventDescriptor
0x180014d30  mov     [rsp+250h+UserDataCount], ecx; UserDataCount
0x180014d34  mov     rcx, r14; RegHandle
0x180014d37  call    cs:__imp_EventWriteTransfer
0x180014d3d  mov     rdi, [rdi+18h]
0x180014d41  mov     rbx, [rbx]
0x180014d44  call    cs:__imp_GetProcessHeap
0x180014d4a  mov     r8, rbx; lpMem
0x180014d4d  xor     edx, edx; dwFlags
0x180014d4f  mov     rcx, rax; hHeap
0x180014d52  call    cs:__imp_HeapFree
0x180014d58  test    rdi, rdi
0x180014d5b  jnz     short loc_180014CE0
0x180014d5d  inc     r15
0x180014d60  cmp     r15, 20h ; ' '
0x180014d64  jnz     loc_180014C30
0x180014d6a  mov     r15, [rsp+250h+var_20]
0x180014d72  mov     r14, [rsp+250h+var_18]
0x180014d7a  mov     r12, [rsp+240h]
0x180014d82  mov     rdi, [rsp+250h+arg_10]
0x180014d8a  mov     rbx, [rsp+250h+arg_8]
0x180014d92  mov     rcx, [rbp+0B0h+var_28]
0x180014d99  xor     rcx, rsp; StackCookie
0x180014d9c  call    __security_check_cookie
0x180014da1  add     rsp, 248h
0x180014da8  pop     rsi
0x180014da9  pop     rbp
0x180014daa  retn
```
