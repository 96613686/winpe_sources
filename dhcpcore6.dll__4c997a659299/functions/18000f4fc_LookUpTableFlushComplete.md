# LookUpTableFlushComplete

- ea: `0x18000f4fc`
- end: `0x18000f86d`
- name: `LookUpTableFlushComplete`
- size: `881`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f480`
- `0x18000fb80`
- `0x18002fd50`
- `0x180030280`

## callees

- `0x180001008`
- `0x18000f4fc`
- `0x18001260c`
- `0x180019ad0`
- `0x18002fc88`
- `0x180030128`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rcx
  char v10; // [rsp+120h] [rbp-80h] BYREF
  char v11; // [rsp+121h] [rbp-7Fh] BYREF
  char v12; // [rsp+122h] [rbp-7Eh] BYREF
  char v13; // [rsp+123h] [rbp-7Dh] BYREF
  char v14; // [rsp+124h] [rbp-7Ch] BYREF
  char v15; // [rsp+125h] [rbp-7Bh] BYREF
  char v16; // [rsp+126h] [rbp-7Ah] BYREF
  char v17; // [rsp+127h] [rbp-79h] BYREF
  char v18; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v19[3]; // [rsp+129h] [rbp-77h] BYREF
  int v20; // [rsp+12Ch] [rbp-74h] BYREF
  int v21; // [rsp+130h] [rbp-70h] BYREF
  int v22; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+138h] [rbp-68h] BYREF
  __int64 v24; // [rsp+140h] [rbp-60h] BYREF
  __int64 v25; // [rsp+148h] [rbp-58h] BYREF
  __int64 v26; // [rsp+150h] [rbp-50h] BYREF
  __int64 v27; // [rsp+158h] [rbp-48h] BYREF
  __int64 v28; // [rsp+160h] [rbp-40h] BYREF
  __int64 v29; // [rsp+168h] [rbp-38h] BYREF
  __int64 v30; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v31; // [rsp+178h] [rbp-28h] BYREF
  __int64 v32; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v33; // [rsp+188h] [rbp-18h] BYREF
  __int16 v34; // [rsp+190h] [rbp-10h]
  const wchar_t *v35; // [rsp+198h] [rbp-8h] BYREF
  __int16 v36; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v37; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v38; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v39; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v40; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v41; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v42; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v43; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v44; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v45; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v46; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v47; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v48; // [rsp+200h] [rbp+60h]
  const wchar_t *v49; // [rsp+208h] [rbp+68h] BYREF
  __int16 v50; // [rsp+210h] [rbp+70h]
  __int128 v51; // [rsp+218h] [rbp+78h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v5 + 272) )
    {
      if ( (unsigned int)dword_180042138 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_180042138, 0x200000000000LL, v3, v4) )
      {
        v10 = 4;
        v36 = 42;
        v33 = L"SummaryCount";
        v34 = 24;
        v23 = *(unsigned int *)(a1 + 308);
        v35 = L"NumLargeEventFailures";
        v24 = *(unsigned int *)(a1 + 304);
        v37 = L"NumAllocationFailures";
        v25 = *(unsigned int *)(a1 + 300);
        v39 = L"NumBucketLimitReached";
        v26 = *(unsigned int *)(a1 + 296);
        v41 = L"MinEntriesFlushed";
        v27 = *(unsigned int *)(a1 + 292);
        v43 = L"MaxEntriesFlushed";
        v28 = *(_QWORD *)(a1 + 272);
        v45 = L"TotalEntriesFlushed";
        v46 = 38;
        v29 = *(unsigned int *)(a1 + 288);
        v47 = L"MaxEntriesStored";
        v30 = *(_QWORD *)(a1 + 280);
        v49 = L"NumFlushes";
        v50 = 20;
        v8 = *(_QWORD *)(a1 + 328);
        v38 = 42;
        v40 = 42;
        v20 = 1;
        v11 = 4;
        v12 = 4;
        v13 = 4;
        v14 = 4;
        v42 = 34;
        v15 = 4;
        v44 = 34;
        v16 = 4;
        v17 = 4;
        v48 = 32;
        v18 = 4;
        v9 = *(_QWORD *)(v8 + 8);
        v31 = &v51;
        v51 = *(_OWORD *)(v9 - 16);
        v19[0] = 0;
        v21 = -1;
        v22 = 300;
        v32 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v9,
          (unsigned int)&word_18003C936,
          v6,
          v7,
          (__int64)&v32,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)v19,
          (__int64)&v31,
          (__int64)&v49,
          (__int64)&v30,
          (__int64)&v18,
          (__int64)&v47,
          (__int64)&v29,
          (__int64)&v17,
          (__int64)&v45,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v43,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v41,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v39,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v37,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v35,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v33,
          (__int64)&v20,
          (__int64)&v10);
      }
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    do
      FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
}

```

## disassembly

```asm
0x18000f4fc  push    rbp
0x18000f4fe  push    rbx
0x18000f4ff  push    rsi
0x18000f500  push    rdi
0x18000f501  lea     rbp, [rsp-98h]
0x18000f509  sub     rsp, 238h
0x18000f510  mov     rax, cs:__security_cookie
0x18000f517  xor     rax, rsp
0x18000f51a  mov     [rbp+0B0h+var_28], rax
0x18000f521  mov     edx, [rcx+100h]
0x18000f527  xor     edi, edi
0x18000f529  mov     rbx, rcx
0x18000f52c  test    edx, edx
0x18000f52e  jz      loc_18000F851
0x18000f534  call    UpdateInternalStatsOnFlush
0x18000f539  lea     esi, [rdi+20h]
0x18000f53c  cmp     [rcx+110h], rdi
0x18000f543  jz      loc_18000F841
0x18000f549  mov     eax, cs:dword_180042138
0x18000f54f  cmp     eax, 5
0x18000f552  jbe     loc_18000F827
0x18000f558  mov     rdx, 200000000000h
0x18000f562  lea     rcx, dword_180042138
0x18000f569  call    _tlgKeywordOn
0x18000f56e  test    al, al
0x18000f570  jz      loc_18000F827
0x18000f576  lea     ecx, [rdi+2Ah]
0x18000f579  mov     [rbp+0B0h+var_130], 4
0x18000f57d  lea     rax, aSummarycount; "SummaryCount"
0x18000f584  mov     [rbp+0B0h+var_B0], cx
0x18000f588  mov     [rbp+0B0h+var_C8], rax
0x18000f58c  lea     eax, [rdi+18h]
0x18000f58f  mov     [rbp+0B0h+var_C0], ax
0x18000f593  mov     eax, [rbx+134h]
0x18000f599  mov     [rbp+0B0h+var_118], rax
0x18000f59d  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18000f5a4  mov     [rbp+0B0h+var_B8], rax
0x18000f5a8  mov     eax, [rbx+130h]
0x18000f5ae  mov     [rbp+0B0h+var_110], rax
0x18000f5b2  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18000f5b9  mov     [rbp+0B0h+var_A8], rax
0x18000f5bd  mov     eax, [rbx+12Ch]
0x18000f5c3  mov     [rbp+0B0h+var_108], rax
0x18000f5c7  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18000f5ce  mov     [rbp+0B0h+var_98], rax
0x18000f5d2  mov     eax, [rbx+128h]
0x18000f5d8  mov     [rbp+0B0h+var_100], rax
0x18000f5dc  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18000f5e3  mov     [rbp+0B0h+var_88], rax
0x18000f5e7  mov     eax, [rbx+124h]
0x18000f5ed  mov     [rbp+0B0h+var_F8], rax
0x18000f5f1  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18000f5f8  mov     [rbp+0B0h+var_78], rax
0x18000f5fc  mov     rax, [rbx+110h]
0x18000f603  mov     [rbp+0B0h+var_F0], rax
0x18000f607  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18000f60e  mov     [rbp+0B0h+var_68], rax
0x18000f612  lea     eax, [rdi+26h]
0x18000f615  mov     [rbp+0B0h+var_60], ax
0x18000f619  mov     eax, [rbx+120h]
0x18000f61f  mov     [rbp+0B0h+var_E8], rax
0x18000f623  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18000f62a  mov     [rbp+0B0h+var_58], rax
0x18000f62e  mov     rax, [rbx+118h]
0x18000f635  mov     [rbp+0B0h+var_E0], rax
0x18000f639  lea     rax, aNumflushes; "NumFlushes"
0x18000f640  mov     [rbp+0B0h+var_48], rax
0x18000f644  lea     eax, [rdi+14h]
0x18000f647  mov     [rbp+0B0h+var_40], ax
0x18000f64b  mov     rax, [rbx+148h]
0x18000f652  mov     [rbp+0B0h+var_A0], cx
0x18000f656  mov     [rbp+0B0h+var_90], cx
0x18000f65a  lea     ecx, [rdi+22h]
0x18000f65d  mov     [rbp+0B0h+var_124], 1
0x18000f664  mov     [rbp+0B0h+var_12F], 4
0x18000f668  mov     [rbp+0B0h+var_12E], 4
0x18000f66c  mov     [rbp+0B0h+var_12D], 4
0x18000f670  mov     [rbp+0B0h+var_12C], 4
0x18000f674  mov     [rbp+0B0h+var_80], cx
0x18000f678  mov     [rbp+0B0h+var_12B], 4
0x18000f67c  mov     [rbp+0B0h+var_70], cx
0x18000f680  mov     [rbp+0B0h+var_12A], 4
0x18000f684  mov     [rbp+0B0h+var_129], 4
0x18000f688  mov     [rbp+0B0h+var_50], si
0x18000f68c  mov     [rbp+0B0h+var_128], 4
0x18000f690  mov     rcx, [rax+8]
0x18000f694  lea     rax, [rbp+0B0h+var_38]
0x18000f698  mov     [rbp+0B0h+var_D8], rax
0x18000f69c  lea     rax, [rbp+0B0h+var_130]
0x18000f6a0  mov     [rsp+250h+var_138], rax
0x18000f6a8  lea     rax, [rbp+0B0h+var_124]
0x18000f6ac  mov     [rsp+250h+var_140], rax
0x18000f6b4  lea     rax, [rbp+0B0h+var_C8]
0x18000f6b8  movups  xmm0, xmmword ptr [rcx-10h]
0x18000f6bc  mov     [rsp+250h+var_148], rax
0x18000f6c4  lea     rax, [rbp+0B0h+var_12F]
0x18000f6c8  mov     [rsp+250h+var_150], rax
0x18000f6d0  lea     rax, [rbp+0B0h+var_118]
0x18000f6d4  mov     [rsp+250h+var_158], rax
0x18000f6dc  lea     rax, [rbp+0B0h+var_B8]
0x18000f6e0  mov     [rsp+250h+var_160], rax
0x18000f6e8  lea     rax, [rbp+0B0h+var_12E]
0x18000f6ec  movdqu  [rbp+0B0h+var_38], xmm0
0x18000f6f1  mov     [rbp+0B0h+var_127], dil
0x18000f6f5  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x18000f6fc  mov     [rbp+0B0h+var_11C], 12Ch
0x18000f703  mov     [rbp+0B0h+var_D0], 1000000h
0x18000f70b  mov     [rsp+250h+var_168], rax
0x18000f713  lea     rdx, word_18003C936
0x18000f71a  lea     rax, [rbp+0B0h+var_110]
0x18000f71e  mov     [rsp+250h+var_170], rax
0x18000f726  lea     rax, [rbp+0B0h+var_A8]
0x18000f72a  mov     [rsp+250h+var_178], rax
0x18000f732  lea     rax, [rbp+0B0h+var_12D]
0x18000f736  mov     [rsp+250h+var_180], rax
0x18000f73e  lea     rax, [rbp+0B0h+var_108]
0x18000f742  mov     [rsp+250h+var_188], rax
0x18000f74a  lea     rax, [rbp+0B0h+var_98]
0x18000f74e  mov     [rsp+250h+var_190], rax
0x18000f756  lea     rax, [rbp+0B0h+var_12C]
0x18000f75a  mov     [rsp+250h+var_198], rax
0x18000f762  lea     rax, [rbp+0B0h+var_100]
0x18000f766  mov     [rsp+250h+var_1A0], rax
0x18000f76e  lea     rax, [rbp+0B0h+var_88]
0x18000f772  mov     [rsp+250h+var_1A8], rax
0x18000f77a  lea     rax, [rbp+0B0h+var_12B]
0x18000f77e  mov     [rsp+250h+var_1B0], rax
0x18000f786  lea     rax, [rbp+0B0h+var_F8]
0x18000f78a  mov     [rsp+250h+var_1B8], rax
0x18000f792  lea     rax, [rbp+0B0h+var_78]
0x18000f796  mov     [rsp+250h+var_1C0], rax
0x18000f79e  lea     rax, [rbp+0B0h+var_12A]
0x18000f7a2  mov     [rsp+250h+var_1C8], rax
0x18000f7aa  lea     rax, [rbp+0B0h+var_F0]
0x18000f7ae  mov     [rsp+250h+var_1D0], rax
0x18000f7b6  lea     rax, [rbp+0B0h+var_68]
0x18000f7ba  mov     [rsp+250h+var_1D8], rax
0x18000f7bf  lea     rax, [rbp+0B0h+var_129]
0x18000f7c3  mov     [rsp+250h+var_1E0], rax
0x18000f7c8  lea     rax, [rbp+0B0h+var_E8]
0x18000f7cc  mov     [rsp+250h+var_1E8], rax
0x18000f7d1  lea     rax, [rbp+0B0h+var_58]
0x18000f7d5  mov     [rsp+250h+var_1F0], rax
0x18000f7da  lea     rax, [rbp+0B0h+var_128]
0x18000f7de  mov     [rsp+250h+var_1F8], rax
0x18000f7e3  lea     rax, [rbp+0B0h+var_E0]
0x18000f7e7  mov     [rsp+250h+var_200], rax
0x18000f7ec  lea     rax, [rbp+0B0h+var_48]
0x18000f7f0  mov     [rsp+250h+var_208], rax
0x18000f7f5  lea     rax, [rbp+0B0h+var_D8]
0x18000f7f9  mov     [rsp+250h+var_210], rax
0x18000f7fe  lea     rax, [rbp+0B0h+var_127]
0x18000f802  mov     [rsp+250h+var_218], rax
0x18000f807  lea     rax, [rbp+0B0h+var_120]
0x18000f80b  mov     [rsp+250h+var_220], rax
0x18000f810  lea     rax, [rbp+0B0h+var_11C]
0x18000f814  mov     [rsp+250h+var_228], rax
0x18000f819  lea     rax, [rbp+0B0h+var_D0]
0x18000f81d  mov     [rsp+250h+var_230], rax
0x18000f822  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18000f827  xorps   xmm0, xmm0
0x18000f82a  xor     eax, eax
0x18000f82c  movups  xmmword ptr [rbx+110h], xmm0
0x18000f833  movups  xmmword ptr [rbx+120h], xmm0
0x18000f83a  mov     [rbx+130h], rax
0x18000f841  mov     edx, edi
0x18000f843  mov     rcx, rbx
0x18000f846  call    FlushLookUpTableBucket
0x18000f84b  inc     edi
0x18000f84d  cmp     edi, esi
0x18000f84f  jb      short loc_18000F841
0x18000f851  mov     rcx, [rbp+0B0h+var_28]
0x18000f858  xor     rcx, rsp; StackCookie
0x18000f85b  call    __security_check_cookie
0x18000f860  add     rsp, 238h
0x18000f867  pop     rdi
0x18000f868  pop     rsi
0x18000f869  pop     rbx
0x18000f86a  pop     rbp
0x18000f86b  retn
```
