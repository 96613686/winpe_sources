# LookUpTableFlushComplete

- ea: `0x180018a08`
- end: `0x180018d78`
- name: `LookUpTableFlushComplete`
- size: `880`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018870`
- `0x1800188c0`
- `0x180018938`
- `0x1800194f0`

## callees

- `0x180001044`
- `0x180001068`
- `0x180018a08`
- `0x18001a104`
- `0x18001e098`
- `0x18001f1b0`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // rcx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rax
  __int64 v7; // rcx
  char v8; // [rsp+120h] [rbp-80h] BYREF
  char v9; // [rsp+121h] [rbp-7Fh] BYREF
  char v10; // [rsp+122h] [rbp-7Eh] BYREF
  char v11; // [rsp+123h] [rbp-7Dh] BYREF
  char v12; // [rsp+124h] [rbp-7Ch] BYREF
  char v13; // [rsp+125h] [rbp-7Bh] BYREF
  char v14; // [rsp+126h] [rbp-7Ah] BYREF
  char v15; // [rsp+127h] [rbp-79h] BYREF
  char v16; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v17[3]; // [rsp+129h] [rbp-77h] BYREF
  int v18; // [rsp+12Ch] [rbp-74h] BYREF
  int v19; // [rsp+130h] [rbp-70h] BYREF
  int v20; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v21; // [rsp+138h] [rbp-68h] BYREF
  __int64 v22; // [rsp+140h] [rbp-60h] BYREF
  __int64 v23; // [rsp+148h] [rbp-58h] BYREF
  __int64 v24; // [rsp+150h] [rbp-50h] BYREF
  __int64 v25; // [rsp+158h] [rbp-48h] BYREF
  __int64 v26; // [rsp+160h] [rbp-40h] BYREF
  __int64 v27; // [rsp+168h] [rbp-38h] BYREF
  __int64 v28; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v29; // [rsp+178h] [rbp-28h] BYREF
  __int64 v30; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v31; // [rsp+188h] [rbp-18h] BYREF
  __int16 v32; // [rsp+190h] [rbp-10h]
  const wchar_t *v33; // [rsp+198h] [rbp-8h] BYREF
  __int16 v34; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v35; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v36; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v37; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v38; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v39; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v40; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v41; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v42; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v43; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v44; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v45; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v46; // [rsp+200h] [rbp+60h]
  const wchar_t *v47; // [rsp+208h] [rbp+68h] BYREF
  __int16 v48; // [rsp+210h] [rbp+70h]
  __int128 v49; // [rsp+218h] [rbp+78h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v3 + 272) )
    {
      if ( (unsigned int)dword_18002A0D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18002A0D0, 0x200000000000LL) )
      {
        v8 = 4;
        v34 = 42;
        v31 = L"SummaryCount";
        v32 = 24;
        v21 = *(unsigned int *)(a1 + 308);
        v33 = L"NumLargeEventFailures";
        v22 = *(unsigned int *)(a1 + 304);
        v35 = L"NumAllocationFailures";
        v23 = *(unsigned int *)(a1 + 300);
        v37 = L"NumBucketLimitReached";
        v24 = *(unsigned int *)(a1 + 296);
        v39 = L"MinEntriesFlushed";
        v25 = *(unsigned int *)(a1 + 292);
        v41 = L"MaxEntriesFlushed";
        v26 = *(_QWORD *)(a1 + 272);
        v43 = L"TotalEntriesFlushed";
        v44 = 38;
        v27 = *(unsigned int *)(a1 + 288);
        v45 = L"MaxEntriesStored";
        v28 = *(_QWORD *)(a1 + 280);
        v47 = L"NumFlushes";
        v48 = 20;
        v6 = *(_QWORD *)(a1 + 328);
        v36 = 42;
        v38 = 42;
        v18 = 1;
        v9 = 4;
        v10 = 4;
        v11 = 4;
        v12 = 4;
        v40 = 34;
        v13 = 4;
        v42 = 34;
        v14 = 4;
        v15 = 4;
        v46 = 32;
        v16 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v29 = &v49;
        v49 = *(_OWORD *)(v7 - 16);
        v17[0] = 0;
        v19 = -1;
        v20 = 300;
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (unsigned int)byte_1800245DB,
          v4,
          v5,
          (__int64)&v30,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v17,
          (__int64)&v29,
          (__int64)&v47,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v45,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v43,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v41,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v39,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v37,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v35,
          (__int64)&v22,
          (__int64)&v10,
          (__int64)&v33,
          (__int64)&v21,
          (__int64)&v9,
          (__int64)&v31,
          (__int64)&v18,
          (__int64)&v8);
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
0x180018a08  push    rbp
0x180018a0a  push    rbx
0x180018a0b  push    rsi
0x180018a0c  push    rdi
0x180018a0d  lea     rbp, [rsp-98h]
0x180018a15  sub     rsp, 238h
0x180018a1c  mov     rax, cs:__security_cookie
0x180018a23  xor     rax, rsp
0x180018a26  mov     [rbp+0B0h+var_28], rax
0x180018a2d  mov     edx, [rcx+100h]
0x180018a33  xor     edi, edi
0x180018a35  mov     rbx, rcx
0x180018a38  test    edx, edx
0x180018a3a  jz      loc_180018D5D
0x180018a40  call    UpdateInternalStatsOnFlush
0x180018a45  lea     esi, [rdi+20h]
0x180018a48  cmp     [rcx+110h], rdi
0x180018a4f  jz      loc_180018D4D
0x180018a55  mov     eax, cs:dword_18002A0D0
0x180018a5b  cmp     eax, 5
0x180018a5e  jbe     loc_180018D33
0x180018a64  mov     rdx, 200000000000h
0x180018a6e  lea     rcx, dword_18002A0D0
0x180018a75  call    _tlgKeywordOn
0x180018a7a  test    al, al
0x180018a7c  jz      loc_180018D33
0x180018a82  lea     ecx, [rdi+2Ah]
0x180018a85  mov     [rbp+0B0h+var_130], 4
0x180018a89  lea     rax, aSummarycount; "SummaryCount"
0x180018a90  mov     [rbp+0B0h+var_B0], cx
0x180018a94  mov     [rbp+0B0h+var_C8], rax
0x180018a98  lea     eax, [rdi+18h]
0x180018a9b  mov     [rbp+0B0h+var_C0], ax
0x180018a9f  mov     eax, [rbx+134h]
0x180018aa5  mov     [rbp+0B0h+var_118], rax
0x180018aa9  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x180018ab0  mov     [rbp+0B0h+var_B8], rax
0x180018ab4  mov     eax, [rbx+130h]
0x180018aba  mov     [rbp+0B0h+var_110], rax
0x180018abe  lea     rax, aNumallocationf; "NumAllocationFailures"
0x180018ac5  mov     [rbp+0B0h+var_A8], rax
0x180018ac9  mov     eax, [rbx+12Ch]
0x180018acf  mov     [rbp+0B0h+var_108], rax
0x180018ad3  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x180018ada  mov     [rbp+0B0h+var_98], rax
0x180018ade  mov     eax, [rbx+128h]
0x180018ae4  mov     [rbp+0B0h+var_100], rax
0x180018ae8  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180018aef  mov     [rbp+0B0h+var_88], rax
0x180018af3  mov     eax, [rbx+124h]
0x180018af9  mov     [rbp+0B0h+var_F8], rax
0x180018afd  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180018b04  mov     [rbp+0B0h+var_78], rax
0x180018b08  mov     rax, [rbx+110h]
0x180018b0f  mov     [rbp+0B0h+var_F0], rax
0x180018b13  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180018b1a  mov     [rbp+0B0h+var_68], rax
0x180018b1e  lea     eax, [rdi+26h]
0x180018b21  mov     [rbp+0B0h+var_60], ax
0x180018b25  mov     eax, [rbx+120h]
0x180018b2b  mov     [rbp+0B0h+var_E8], rax
0x180018b2f  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180018b36  mov     [rbp+0B0h+var_58], rax
0x180018b3a  mov     rax, [rbx+118h]
0x180018b41  mov     [rbp+0B0h+var_E0], rax
0x180018b45  lea     rax, aNumflushes; "NumFlushes"
0x180018b4c  mov     [rbp+0B0h+var_48], rax
0x180018b50  lea     eax, [rdi+14h]
0x180018b53  mov     [rbp+0B0h+var_40], ax
0x180018b57  mov     rax, [rbx+148h]
0x180018b5e  mov     [rbp+0B0h+var_A0], cx
0x180018b62  mov     [rbp+0B0h+var_90], cx
0x180018b66  lea     ecx, [rdi+22h]
0x180018b69  mov     [rbp+0B0h+var_124], 1
0x180018b70  mov     [rbp+0B0h+var_12F], 4
0x180018b74  mov     [rbp+0B0h+var_12E], 4
0x180018b78  mov     [rbp+0B0h+var_12D], 4
0x180018b7c  mov     [rbp+0B0h+var_12C], 4
0x180018b80  mov     [rbp+0B0h+var_80], cx
0x180018b84  mov     [rbp+0B0h+var_12B], 4
0x180018b88  mov     [rbp+0B0h+var_70], cx
0x180018b8c  mov     [rbp+0B0h+var_12A], 4
0x180018b90  mov     [rbp+0B0h+var_129], 4
0x180018b94  mov     [rbp+0B0h+var_50], si
0x180018b98  mov     [rbp+0B0h+var_128], 4
0x180018b9c  mov     rcx, [rax+8]
0x180018ba0  lea     rax, [rbp+0B0h+var_38]
0x180018ba4  mov     [rbp+0B0h+var_D8], rax
0x180018ba8  lea     rax, [rbp+0B0h+var_130]
0x180018bac  mov     [rsp+250h+var_138], rax
0x180018bb4  lea     rax, [rbp+0B0h+var_124]
0x180018bb8  mov     [rsp+250h+var_140], rax
0x180018bc0  lea     rax, [rbp+0B0h+var_C8]
0x180018bc4  movups  xmm0, xmmword ptr [rcx-10h]
0x180018bc8  mov     [rsp+250h+var_148], rax
0x180018bd0  lea     rax, [rbp+0B0h+var_12F]
0x180018bd4  mov     [rsp+250h+var_150], rax
0x180018bdc  lea     rax, [rbp+0B0h+var_118]
0x180018be0  mov     [rsp+250h+var_158], rax
0x180018be8  lea     rax, [rbp+0B0h+var_B8]
0x180018bec  mov     [rsp+250h+var_160], rax
0x180018bf4  lea     rax, [rbp+0B0h+var_12E]
0x180018bf8  movdqu  [rbp+0B0h+var_38], xmm0
0x180018bfd  mov     [rbp+0B0h+var_127], dil
0x180018c01  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x180018c08  mov     [rbp+0B0h+var_11C], 12Ch
0x180018c0f  mov     [rbp+0B0h+var_D0], 1000000h
0x180018c17  mov     [rsp+250h+var_168], rax
0x180018c1f  lea     rdx, byte_1800245DB
0x180018c26  lea     rax, [rbp+0B0h+var_110]
0x180018c2a  mov     [rsp+250h+var_170], rax
0x180018c32  lea     rax, [rbp+0B0h+var_A8]
0x180018c36  mov     [rsp+250h+var_178], rax
0x180018c3e  lea     rax, [rbp+0B0h+var_12D]
0x180018c42  mov     [rsp+250h+var_180], rax
0x180018c4a  lea     rax, [rbp+0B0h+var_108]
0x180018c4e  mov     [rsp+250h+var_188], rax
0x180018c56  lea     rax, [rbp+0B0h+var_98]
0x180018c5a  mov     [rsp+250h+var_190], rax
0x180018c62  lea     rax, [rbp+0B0h+var_12C]
0x180018c66  mov     [rsp+250h+var_198], rax
0x180018c6e  lea     rax, [rbp+0B0h+var_100]
0x180018c72  mov     [rsp+250h+var_1A0], rax
0x180018c7a  lea     rax, [rbp+0B0h+var_88]
0x180018c7e  mov     [rsp+250h+var_1A8], rax
0x180018c86  lea     rax, [rbp+0B0h+var_12B]
0x180018c8a  mov     [rsp+250h+var_1B0], rax
0x180018c92  lea     rax, [rbp+0B0h+var_F8]
0x180018c96  mov     [rsp+250h+var_1B8], rax
0x180018c9e  lea     rax, [rbp+0B0h+var_78]
0x180018ca2  mov     [rsp+250h+var_1C0], rax
0x180018caa  lea     rax, [rbp+0B0h+var_12A]
0x180018cae  mov     [rsp+250h+var_1C8], rax
0x180018cb6  lea     rax, [rbp+0B0h+var_F0]
0x180018cba  mov     [rsp+250h+var_1D0], rax
0x180018cc2  lea     rax, [rbp+0B0h+var_68]
0x180018cc6  mov     [rsp+250h+var_1D8], rax
0x180018ccb  lea     rax, [rbp+0B0h+var_129]
0x180018ccf  mov     [rsp+250h+var_1E0], rax
0x180018cd4  lea     rax, [rbp+0B0h+var_E8]
0x180018cd8  mov     [rsp+250h+var_1E8], rax
0x180018cdd  lea     rax, [rbp+0B0h+var_58]
0x180018ce1  mov     [rsp+250h+var_1F0], rax
0x180018ce6  lea     rax, [rbp+0B0h+var_128]
0x180018cea  mov     [rsp+250h+var_1F8], rax
0x180018cef  lea     rax, [rbp+0B0h+var_E0]
0x180018cf3  mov     [rsp+250h+var_200], rax
0x180018cf8  lea     rax, [rbp+0B0h+var_48]
0x180018cfc  mov     [rsp+250h+var_208], rax
0x180018d01  lea     rax, [rbp+0B0h+var_D8]
0x180018d05  mov     [rsp+250h+var_210], rax
0x180018d0a  lea     rax, [rbp+0B0h+var_127]
0x180018d0e  mov     [rsp+250h+var_218], rax
0x180018d13  lea     rax, [rbp+0B0h+var_120]
0x180018d17  mov     [rsp+250h+var_220], rax
0x180018d1c  lea     rax, [rbp+0B0h+var_11C]
0x180018d20  mov     [rsp+250h+var_228], rax
0x180018d25  lea     rax, [rbp+0B0h+var_D0]
0x180018d29  mov     [rsp+250h+var_230], rax
0x180018d2e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180018d33  xorps   xmm0, xmm0
0x180018d36  xor     eax, eax
0x180018d38  movups  xmmword ptr [rbx+110h], xmm0
0x180018d3f  movups  xmmword ptr [rbx+120h], xmm0
0x180018d46  mov     [rbx+130h], rax
0x180018d4d  mov     edx, edi
0x180018d4f  mov     rcx, rbx
0x180018d52  call    FlushLookUpTableBucket
0x180018d57  inc     edi
0x180018d59  cmp     edi, esi
0x180018d5b  jb      short loc_180018D4D
0x180018d5d  mov     rcx, [rbp+0B0h+var_28]
0x180018d64  xor     rcx, rsp; StackCookie
0x180018d67  call    __security_check_cookie
0x180018d6c  add     rsp, 238h
0x180018d73  pop     rdi
0x180018d74  pop     rsi
0x180018d75  pop     rbx
0x180018d76  pop     rbp
0x180018d77  retn
```
