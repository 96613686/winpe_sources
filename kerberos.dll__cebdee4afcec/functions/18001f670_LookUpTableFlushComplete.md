# LookUpTableFlushComplete

- ea: `0x18001f670`
- end: `0x18001fbab`
- name: `LookUpTableFlushComplete`
- size: `1339`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f508`
- `0x18001f5f0`
- `0x18002ab80`
- `0x1800685e0`

## callees

- `0x180001008`
- `0x18001f670`
- `0x180070680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fabe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fabe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fa41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fa41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fb44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fb52`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fb37`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fb37`

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
      if ( (unsigned int)dword_1801402A8 > 5
        && (qword_1801402B8 & 0x200000000000LL) != 0
        && (qword_1801402C0 & 0x200000000000LL) == qword_1801402C0 )
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
          (unsigned int)&dword_18012CC54,
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
0x18001f670  mov     r11, rsp
0x18001f673  push    rbp
0x18001f674  push    rsi
0x18001f675  lea     rbp, [r11-0B8h]
0x18001f67c  sub     rsp, 248h
0x18001f683  mov     rax, cs:__security_cookie
0x18001f68a  xor     rax, rsp
0x18001f68d  mov     [rbp+0B0h+var_28], rax
0x18001f694  mov     eax, [rcx+100h]
0x18001f69a  mov     rsi, rcx
0x18001f69d  test    eax, eax
0x18001f69f  jz      loc_18001FB92
0x18001f6a5  mov     [r11+10h], rbx
0x18001f6a9  mov     [r11+18h], rdi
0x18001f6ad  mov     [r11-18h], r12
0x18001f6b1  mov     [r11-20h], r14
0x18001f6b5  mov     [r11-28h], r15
0x18001f6b9  cmp     [rcx+128h], eax
0x18001f6bf  ja      short loc_18001F6CB
0x18001f6c1  cmp     qword ptr [rcx+118h], 0
0x18001f6c9  jnz     short loc_18001F6D1
0x18001f6cb  mov     [rcx+128h], eax
0x18001f6d1  cmp     [rcx+124h], eax
0x18001f6d7  jnb     short loc_18001F6DF
0x18001f6d9  mov     [rcx+124h], eax
0x18001f6df  mov     r8d, 1
0x18001f6e5  movq    xmm1, rax
0x18001f6ea  movq    xmm0, r8
0x18001f6ef  punpcklqdq xmm1, xmm0
0x18001f6f3  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18001f6fb  paddq   xmm1, xmm0
0x18001f6ff  movdqu  xmmword ptr [rcx+110h], xmm1
0x18001f707  cmp     qword ptr [rcx+110h], 0
0x18001f70f  jz      loc_18001FA2A
0x18001f715  mov     eax, cs:dword_1801402A8
0x18001f71b  cmp     eax, 5
0x18001f71e  jbe     loc_18001FA10
0x18001f724  mov     rcx, cs:qword_1801402C0
0x18001f72b  mov     rdx, 200000000000h
0x18001f735  mov     rax, cs:qword_1801402B8
0x18001f73c  test    rdx, rax
0x18001f73f  jz      loc_18001FA10
0x18001f745  mov     rax, rcx
0x18001f748  and     rax, rdx
0x18001f74b  cmp     rax, rcx
0x18001f74e  jnz     loc_18001FA10
0x18001f754  mov     ecx, 2Ah ; '*'
0x18001f759  mov     [rbp+0B0h+var_130], 4
0x18001f75d  lea     rax, aSummarycount; "SummaryCount"
0x18001f764  mov     [rbp+0B0h+var_B0], cx
0x18001f768  mov     [rbp+0B0h+var_C8], rax
0x18001f76c  mov     eax, 18h
0x18001f771  mov     [rbp+0B0h+var_C0], ax
0x18001f775  mov     eax, [rsi+134h]
0x18001f77b  mov     [rbp+0B0h+var_D0], rax
0x18001f77f  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18001f786  mov     [rbp+0B0h+var_B8], rax
0x18001f78a  mov     eax, [rsi+130h]
0x18001f790  mov     [rbp+0B0h+var_110], rax
0x18001f794  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18001f79b  mov     [rbp+0B0h+var_A8], rax
0x18001f79f  mov     eax, [rsi+12Ch]
0x18001f7a5  mov     [rbp+0B0h+var_108], rax
0x18001f7a9  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18001f7b0  mov     [rbp+0B0h+var_98], rax
0x18001f7b4  mov     eax, [rsi+128h]
0x18001f7ba  mov     [rbp+0B0h+var_100], rax
0x18001f7be  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18001f7c5  mov     [rbp+0B0h+var_88], rax
0x18001f7c9  mov     eax, [rsi+124h]
0x18001f7cf  mov     [rbp+0B0h+var_F8], rax
0x18001f7d3  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18001f7da  mov     [rbp+0B0h+var_78], rax
0x18001f7de  mov     rax, [rsi+110h]
0x18001f7e5  mov     [rbp+0B0h+var_F0], rax
0x18001f7e9  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18001f7f0  mov     [rbp+0B0h+var_68], rax
0x18001f7f4  mov     eax, 26h ; '&'
0x18001f7f9  mov     [rbp+0B0h+var_60], ax
0x18001f7fd  mov     eax, [rsi+120h]
0x18001f803  mov     [rbp+0B0h+var_E8], rax
0x18001f807  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001f80e  mov     [rbp+0B0h+var_58], rax
0x18001f812  mov     eax, 20h ; ' '
0x18001f817  mov     [rbp+0B0h+var_50], ax
0x18001f81b  mov     rax, [rsi+118h]
0x18001f822  mov     [rbp+0B0h+var_E0], rax
0x18001f826  lea     rax, aNumflushes; "NumFlushes"
0x18001f82d  mov     [rbp+0B0h+var_48], rax
0x18001f831  mov     eax, 14h
0x18001f836  mov     [rbp+0B0h+var_40], ax
0x18001f83a  mov     rax, [rsi+148h]
0x18001f841  mov     [rbp+0B0h+var_A0], cx
0x18001f845  mov     [rbp+0B0h+var_90], cx
0x18001f849  mov     ecx, 22h ; '"'
0x18001f84e  mov     [rbp+0B0h+var_124], r8d
0x18001f852  mov     [rbp+0B0h+var_12F], 4
0x18001f856  mov     [rbp+0B0h+var_12E], 4
0x18001f85a  mov     [rbp+0B0h+var_12D], 4
0x18001f85e  mov     [rbp+0B0h+var_12C], 4
0x18001f862  mov     [rbp+0B0h+var_80], cx
0x18001f866  mov     [rbp+0B0h+var_12B], 4
0x18001f86a  mov     [rbp+0B0h+var_70], cx
0x18001f86e  mov     [rbp+0B0h+var_12A], 4
0x18001f872  mov     [rbp+0B0h+var_129], 4
0x18001f876  mov     [rbp+0B0h+var_128], 4
0x18001f87a  mov     rcx, [rax+8]
0x18001f87e  lea     rax, [rbp+0B0h+var_38]
0x18001f882  mov     [rbp+0B0h+var_D8], rax
0x18001f886  lea     rax, [rbp+0B0h+var_130]
0x18001f88a  mov     [rsp+118h], rax
0x18001f892  lea     rax, [rbp+0B0h+var_124]
0x18001f896  mov     [rsp+250h+var_140], rax
0x18001f89e  lea     rax, [rbp+0B0h+var_C8]
0x18001f8a2  movups  xmm0, xmmword ptr [rcx-10h]
0x18001f8a6  mov     [rsp+250h+var_148], rax
0x18001f8ae  lea     rax, [rbp+0B0h+var_12F]
0x18001f8b2  mov     [rsp+250h+var_150], rax
0x18001f8ba  lea     rax, [rbp+0B0h+var_D0]
0x18001f8be  mov     [rsp+250h+var_158], rax
0x18001f8c6  lea     rax, [rbp+0B0h+var_B8]
0x18001f8ca  mov     [rsp+250h+var_160], rax
0x18001f8d2  movups  [rbp+0B0h+var_38], xmm0
0x18001f8d6  mov     [rbp+0B0h+var_127], 0
0x18001f8da  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x18001f8e1  mov     [rbp+0B0h+var_11C], 12Ch
0x18001f8e8  mov     [rbp+0B0h+var_118], 1000000h
0x18001f8f0  lea     rax, [rbp+0B0h+var_12E]
0x18001f8f4  mov     [rsp+250h+var_168], rax
0x18001f8fc  lea     rdx, dword_18012CC54
0x18001f903  lea     rax, [rbp+0B0h+var_110]
0x18001f907  mov     [rsp+250h+var_170], rax
0x18001f90f  lea     rax, [rbp+0B0h+var_A8]
0x18001f913  mov     [rsp+250h+var_178], rax
0x18001f91b  lea     rax, [rbp+0B0h+var_12D]
0x18001f91f  mov     [rsp+250h+var_180], rax
0x18001f927  lea     rax, [rbp+0B0h+var_108]
0x18001f92b  mov     [rsp+250h+var_188], rax
0x18001f933  lea     rax, [rbp+0B0h+var_98]
0x18001f937  mov     [rsp+250h+var_190], rax
0x18001f93f  lea     rax, [rbp+0B0h+var_12C]
0x18001f943  mov     [rsp+250h+var_198], rax
0x18001f94b  lea     rax, [rbp+0B0h+var_100]
0x18001f94f  mov     [rsp+250h+var_1A0], rax
0x18001f957  lea     rax, [rbp+0B0h+var_88]
0x18001f95b  mov     [rsp+250h+var_1A8], rax
0x18001f963  lea     rax, [rbp+0B0h+var_12B]
0x18001f967  mov     [rsp+250h+var_1B0], rax
0x18001f96f  lea     rax, [rbp+0B0h+var_F8]
0x18001f973  mov     [rsp+250h+var_1B8], rax
0x18001f97b  lea     rax, [rbp+0B0h+var_78]
0x18001f97f  mov     [rsp+250h+var_1C0], rax
0x18001f987  lea     rax, [rbp+0B0h+var_12A]
0x18001f98b  mov     [rsp+250h+var_1C8], rax
0x18001f993  lea     rax, [rbp+0B0h+var_F0]
0x18001f997  mov     [rsp+250h+var_1D0], rax
0x18001f99f  lea     rax, [rbp+0B0h+var_68]
0x18001f9a3  mov     [rsp+250h+var_1D8], rax
0x18001f9a8  lea     rax, [rbp+0B0h+var_129]
0x18001f9ac  mov     [rsp+250h+var_1E0], rax
0x18001f9b1  lea     rax, [rbp+0B0h+var_E8]
0x18001f9b5  mov     [rsp+250h+var_1E8], rax
0x18001f9ba  lea     rax, [rbp+0B0h+var_58]
0x18001f9be  mov     [rsp+250h+var_1F0], rax
0x18001f9c3  lea     rax, [rbp+0B0h+var_128]
0x18001f9c7  mov     [rsp+250h+var_1F8], rax
0x18001f9cc  lea     rax, [rbp+0B0h+var_E0]
0x18001f9d0  mov     [rsp+250h+var_200], rax
0x18001f9d5  lea     rax, [rbp+0B0h+var_48]
0x18001f9d9  mov     [rsp+250h+var_208], rax
0x18001f9de  lea     rax, [rbp+0B0h+var_D8]
0x18001f9e2  mov     [rsp+250h+var_210], rax
0x18001f9e7  lea     rax, [rbp+0B0h+var_127]
0x18001f9eb  mov     [rsp+250h+var_218], rax
0x18001f9f0  lea     rax, [rbp+0B0h+var_120]
0x18001f9f4  mov     [rsp+250h+var_220], rax
0x18001f9f9  lea     rax, [rbp+0B0h+var_11C]
0x18001f9fd  mov     [rsp+250h+UserData], rax
0x18001fa02  lea     rax, [rbp+0B0h+var_118]
0x18001fa06  mov     qword ptr [rsp+250h+UserDataCount], rax
0x18001fa0b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18001fa10  xorps   xmm0, xmm0
0x18001fa13  xor     eax, eax
0x18001fa15  movups  xmmword ptr [rsi+110h], xmm0
0x18001fa1c  movups  xmmword ptr [rsi+120h], xmm0
0x18001fa23  mov     [rsi+130h], rax
0x18001fa2a  xor     r12d, r12d
0x18001fa2d  mov     r15d, r12d
0x18001fa30  cmp     [rsi+r15*8], r12
0x18001fa34  jz      loc_18001FB5D
0x18001fa3a  lea     rcx, [rsi+108h]; SRWLock
0x18001fa41  call    cs:__imp_AcquireSRWLockExclusive
0x18001fa47  mov     rdi, [rsi+r15*8]
0x18001fa4b  mov     r8d, r12d
0x18001fa4e  mov     [rsi+r15*8], r12
0x18001fa52  mov     [rbp+0B0h+var_118], rdi
0x18001fa56  test    rdi, rdi
0x18001fa59  jz      short loc_18001FAB0
0x18001fa5b  lea     rdx, [rbp+0B0h+var_118]
0x18001fa5f  mov     rax, rdi
0x18001fa62  nop     dword ptr [rax+00h]
0x18001fa66  nop     word ptr [rax+rax+00000000h]
0x18001fa70  mov     r9, [rax+20h]
0x18001fa74  mov     [rax+20h], r12
0x18001fa78  mov     rdx, [rdx]
0x18001fa7b  add     rdx, 18h
0x18001fa7f  mov     rax, [rdx]
0x18001fa82  test    rax, rax
0x18001fa85  jz      short loc_18001FA9F
0x18001fa87  nop     word ptr [rax+rax+00000000h]
0x18001fa90  lea     rcx, [rax+20h]
0x18001fa94  mov     rax, [rax+20h]
0x18001fa98  test    rax, rax
0x18001fa9b  jnz     short loc_18001FA90
0x18001fa9d  jmp     short loc_18001FAA2
0x18001fa9f  mov     rcx, rdx
0x18001faa2  mov     [rcx], r9
0x18001faa5  inc     r8d
0x18001faa8  mov     rax, [rdx]
0x18001faab  test    rax, rax
0x18001faae  jnz     short loc_18001FA70
0x18001fab0  sub     [rsi+100h], r8d
0x18001fab7  lea     rcx, [rsi+108h]; SRWLock
0x18001fabe  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fac4  mov     rax, [rsi+148h]
0x18001facb  mov     r14, [rax+20h]
0x18001facf  test    rdi, rdi
0x18001fad2  jz      loc_18001FB5D
0x18001fad8  nop     dword ptr [rax+rax+00000000h]
0x18001fae0  movzx   ecx, byte ptr [rdi+2Dh]
0x18001fae4  lea     rbx, [rdi+10h]
0x18001fae8  mov     eax, 2
0x18001faed  add     ecx, eax
0x18001faef  cmp     ecx, eax
0x18001faf1  jbe     short loc_18001FB1B
0x18001faf3  nop     dword ptr [rax+00h]
0x18001faf7  nop     word ptr [rax+rax+00000000h]
0x18001fb00  mov     rcx, [rbx]
0x18001fb03  movsxd  rdx, eax
0x18001fb06  inc     eax
0x18001fb08  add     rdx, rdx
0x18001fb0b  mov     [rcx+rdx*8+0Dh], r12b
0x18001fb10  movzx   ecx, byte ptr [rdi+2Dh]
0x18001fb14  add     ecx, 2
0x18001fb17  cmp     eax, ecx
0x18001fb19  jl      short loc_18001FB00
0x18001fb1b  movzx   ecx, byte ptr [rdi+2Ch]
0x18001fb1f  xor     r9d, r9d; RelatedActivityId
0x18001fb22  mov     rax, [rbx]
0x18001fb25  xor     r8d, r8d; ActivityId
0x18001fb28  mov     [rsp+250h+UserData], rax; UserData
0x18001fb2d  mov     rdx, rdi; EventDescriptor
0x18001fb30  mov     [rsp+250h+UserDataCount], ecx; UserDataCount
0x18001fb34  mov     rcx, r14; RegHandle
0x18001fb37  call    cs:__imp_EventWriteTransfer
0x18001fb3d  mov     rdi, [rdi+18h]
0x18001fb41  mov     rbx, [rbx]
0x18001fb44  call    cs:__imp_GetProcessHeap
0x18001fb4a  mov     r8, rbx; lpMem
0x18001fb4d  xor     edx, edx; dwFlags
0x18001fb4f  mov     rcx, rax; hHeap
0x18001fb52  call    cs:__imp_HeapFree
0x18001fb58  test    rdi, rdi
0x18001fb5b  jnz     short loc_18001FAE0
0x18001fb5d  inc     r15
0x18001fb60  cmp     r15, 20h ; ' '
0x18001fb64  jnz     loc_18001FA30
0x18001fb6a  mov     r15, [rsp+250h+var_20]
0x18001fb72  mov     r14, [rsp+250h+var_18]
0x18001fb7a  mov     r12, [rsp+240h]
0x18001fb82  mov     rdi, [rsp+250h+arg_10]
0x18001fb8a  mov     rbx, [rsp+250h+arg_8]
0x18001fb92  mov     rcx, [rbp+0B0h+var_28]
0x18001fb99  xor     rcx, rsp; StackCookie
0x18001fb9c  call    __security_check_cookie
0x18001fba1  add     rsp, 248h
0x18001fba8  pop     rsi
0x18001fba9  pop     rbp
0x18001fbaa  retn
```
