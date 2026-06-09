# LookUpTableFlushComplete

- ea: `0x18003cb80`
- end: `0x18003cef1`
- name: `LookUpTableFlushComplete`
- size: `881`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180037f4c`
- `0x18003cf60`
- `0x18003cff0`
- `0x18003d060`

## callees

- `0x180001008`
- `0x180019664`
- `0x180027468`
- `0x180027ba0`
- `0x18003cb80`
- `0x18003d0dc`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // r8
  __int64 v4; // rcx
  int v5; // r8d
  int v6; // r9d
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

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v4 + 288) )
    {
      if ( (unsigned int)dword_180031388 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180031388, 0x200000000000LL, v3) )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = *(unsigned int *)(a1 + 324);
        v34 = L"NumLargeEventFailures";
        v23 = *(unsigned int *)(a1 + 320);
        v36 = L"NumAllocationFailures";
        v24 = *(unsigned int *)(a1 + 316);
        v38 = L"NumBucketLimitReached";
        v25 = *(unsigned int *)(a1 + 312);
        v40 = L"MinEntriesFlushed";
        v26 = *(unsigned int *)(a1 + 308);
        v42 = L"MaxEntriesFlushed";
        v27 = *(_QWORD *)(a1 + 288);
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = *(unsigned int *)(a1 + 304);
        v46 = L"MaxEntriesStored";
        v29 = *(_QWORD *)(a1 + 296);
        v48 = L"NumFlushes";
        v49 = 20;
        v7 = *(_QWORD *)(a1 + 344);
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
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v8,
          (unsigned int)byte_18002D693,
          v5,
          v6,
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
      *(_OWORD *)(a1 + 288) = 0;
      *(_OWORD *)(a1 + 304) = 0;
      *(_QWORD *)(a1 + 320) = 0;
    }
    do
      FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
}

```

## disassembly

```asm
0x18003cb80  push    rbp
0x18003cb82  push    rbx
0x18003cb83  push    rsi
0x18003cb84  push    rdi
0x18003cb85  lea     rbp, [rsp-98h]
0x18003cb8d  sub     rsp, 238h
0x18003cb94  mov     rax, cs:__security_cookie
0x18003cb9b  xor     rax, rsp
0x18003cb9e  mov     [rbp+0B0h+var_28], rax
0x18003cba5  mov     edx, [rcx+100h]
0x18003cbab  xor     edi, edi
0x18003cbad  mov     rbx, rcx
0x18003cbb0  test    edx, edx
0x18003cbb2  jz      loc_18003CED5
0x18003cbb8  call    UpdateInternalStatsOnFlush
0x18003cbbd  lea     esi, [rdi+20h]
0x18003cbc0  cmp     [rcx+120h], rdi
0x18003cbc7  jz      loc_18003CEC5
0x18003cbcd  mov     eax, cs:dword_180031388
0x18003cbd3  cmp     eax, 5
0x18003cbd6  jbe     loc_18003CEAB
0x18003cbdc  mov     rdx, 200000000000h
0x18003cbe6  lea     rcx, dword_180031388
0x18003cbed  call    _tlgKeywordOn
0x18003cbf2  test    al, al
0x18003cbf4  jz      loc_18003CEAB
0x18003cbfa  lea     ecx, [rdi+2Ah]
0x18003cbfd  mov     [rbp+0B0h+var_130], 4
0x18003cc01  lea     rax, aSummarycount; "SummaryCount"
0x18003cc08  mov     [rbp+0B0h+var_B0], cx
0x18003cc0c  mov     [rbp+0B0h+var_C8], rax
0x18003cc10  lea     eax, [rdi+18h]
0x18003cc13  mov     [rbp+0B0h+var_C0], ax
0x18003cc17  mov     eax, [rbx+144h]
0x18003cc1d  mov     [rbp+0B0h+var_118], rax
0x18003cc21  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18003cc28  mov     [rbp+0B0h+var_B8], rax
0x18003cc2c  mov     eax, [rbx+140h]
0x18003cc32  mov     [rbp+0B0h+var_110], rax
0x18003cc36  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18003cc3d  mov     [rbp+0B0h+var_A8], rax
0x18003cc41  mov     eax, [rbx+13Ch]
0x18003cc47  mov     [rbp+0B0h+var_108], rax
0x18003cc4b  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18003cc52  mov     [rbp+0B0h+var_98], rax
0x18003cc56  mov     eax, [rbx+138h]
0x18003cc5c  mov     [rbp+0B0h+var_100], rax
0x18003cc60  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18003cc67  mov     [rbp+0B0h+var_88], rax
0x18003cc6b  mov     eax, [rbx+134h]
0x18003cc71  mov     [rbp+0B0h+var_F8], rax
0x18003cc75  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18003cc7c  mov     [rbp+0B0h+var_78], rax
0x18003cc80  mov     rax, [rbx+120h]
0x18003cc87  mov     [rbp+0B0h+var_F0], rax
0x18003cc8b  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18003cc92  mov     [rbp+0B0h+var_68], rax
0x18003cc96  lea     eax, [rdi+26h]
0x18003cc99  mov     [rbp+0B0h+var_60], ax
0x18003cc9d  mov     eax, [rbx+130h]
0x18003cca3  mov     [rbp+0B0h+var_E8], rax
0x18003cca7  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18003ccae  mov     [rbp+0B0h+var_58], rax
0x18003ccb2  mov     rax, [rbx+128h]
0x18003ccb9  mov     [rbp+0B0h+var_E0], rax
0x18003ccbd  lea     rax, aNumflushes; "NumFlushes"
0x18003ccc4  mov     [rbp+0B0h+var_48], rax
0x18003ccc8  lea     eax, [rdi+14h]
0x18003cccb  mov     [rbp+0B0h+var_40], ax
0x18003cccf  mov     rax, [rbx+158h]
0x18003ccd6  mov     [rbp+0B0h+var_A0], cx
0x18003ccda  mov     [rbp+0B0h+var_90], cx
0x18003ccde  lea     ecx, [rdi+22h]
0x18003cce1  mov     [rbp+0B0h+var_124], 1
0x18003cce8  mov     [rbp+0B0h+var_12F], 4
0x18003ccec  mov     [rbp+0B0h+var_12E], 4
0x18003ccf0  mov     [rbp+0B0h+var_12D], 4
0x18003ccf4  mov     [rbp+0B0h+var_12C], 4
0x18003ccf8  mov     [rbp+0B0h+var_80], cx
0x18003ccfc  mov     [rbp+0B0h+var_12B], 4
0x18003cd00  mov     [rbp+0B0h+var_70], cx
0x18003cd04  mov     [rbp+0B0h+var_12A], 4
0x18003cd08  mov     [rbp+0B0h+var_129], 4
0x18003cd0c  mov     [rbp+0B0h+var_50], si
0x18003cd10  mov     [rbp+0B0h+var_128], 4
0x18003cd14  mov     rcx, [rax+8]
0x18003cd18  lea     rax, [rbp+0B0h+var_38]
0x18003cd1c  mov     [rbp+0B0h+var_D8], rax
0x18003cd20  lea     rax, [rbp+0B0h+var_130]
0x18003cd24  mov     [rsp+250h+var_138], rax
0x18003cd2c  lea     rax, [rbp+0B0h+var_124]
0x18003cd30  mov     [rsp+250h+var_140], rax
0x18003cd38  lea     rax, [rbp+0B0h+var_C8]
0x18003cd3c  movups  xmm0, xmmword ptr [rcx-10h]
0x18003cd40  mov     [rsp+250h+var_148], rax
0x18003cd48  lea     rax, [rbp+0B0h+var_12F]
0x18003cd4c  mov     [rsp+250h+var_150], rax
0x18003cd54  lea     rax, [rbp+0B0h+var_118]
0x18003cd58  mov     [rsp+250h+var_158], rax
0x18003cd60  lea     rax, [rbp+0B0h+var_B8]
0x18003cd64  mov     [rsp+250h+var_160], rax
0x18003cd6c  lea     rax, [rbp+0B0h+var_12E]
0x18003cd70  movdqu  [rbp+0B0h+var_38], xmm0
0x18003cd75  mov     [rbp+0B0h+var_127], dil
0x18003cd79  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x18003cd80  mov     [rbp+0B0h+var_11C], 12Ch
0x18003cd87  mov     [rbp+0B0h+var_D0], 1000000h
0x18003cd8f  mov     [rsp+250h+var_168], rax
0x18003cd97  lea     rdx, byte_18002D693
0x18003cd9e  lea     rax, [rbp+0B0h+var_110]
0x18003cda2  mov     [rsp+250h+var_170], rax
0x18003cdaa  lea     rax, [rbp+0B0h+var_A8]
0x18003cdae  mov     [rsp+250h+var_178], rax
0x18003cdb6  lea     rax, [rbp+0B0h+var_12D]
0x18003cdba  mov     [rsp+250h+var_180], rax
0x18003cdc2  lea     rax, [rbp+0B0h+var_108]
0x18003cdc6  mov     [rsp+250h+var_188], rax
0x18003cdce  lea     rax, [rbp+0B0h+var_98]
0x18003cdd2  mov     [rsp+250h+var_190], rax
0x18003cdda  lea     rax, [rbp+0B0h+var_12C]
0x18003cdde  mov     [rsp+250h+var_198], rax
0x18003cde6  lea     rax, [rbp+0B0h+var_100]
0x18003cdea  mov     [rsp+250h+var_1A0], rax
0x18003cdf2  lea     rax, [rbp+0B0h+var_88]
0x18003cdf6  mov     [rsp+250h+var_1A8], rax
0x18003cdfe  lea     rax, [rbp+0B0h+var_12B]
0x18003ce02  mov     [rsp+250h+var_1B0], rax
0x18003ce0a  lea     rax, [rbp+0B0h+var_F8]
0x18003ce0e  mov     [rsp+250h+var_1B8], rax
0x18003ce16  lea     rax, [rbp+0B0h+var_78]
0x18003ce1a  mov     [rsp+250h+var_1C0], rax
0x18003ce22  lea     rax, [rbp+0B0h+var_12A]
0x18003ce26  mov     [rsp+250h+var_1C8], rax
0x18003ce2e  lea     rax, [rbp+0B0h+var_F0]
0x18003ce32  mov     [rsp+250h+var_1D0], rax
0x18003ce3a  lea     rax, [rbp+0B0h+var_68]
0x18003ce3e  mov     [rsp+250h+var_1D8], rax
0x18003ce43  lea     rax, [rbp+0B0h+var_129]
0x18003ce47  mov     [rsp+250h+var_1E0], rax
0x18003ce4c  lea     rax, [rbp+0B0h+var_E8]
0x18003ce50  mov     [rsp+250h+var_1E8], rax
0x18003ce55  lea     rax, [rbp+0B0h+var_58]
0x18003ce59  mov     [rsp+250h+var_1F0], rax
0x18003ce5e  lea     rax, [rbp+0B0h+var_128]
0x18003ce62  mov     [rsp+250h+var_1F8], rax
0x18003ce67  lea     rax, [rbp+0B0h+var_E0]
0x18003ce6b  mov     [rsp+250h+var_200], rax
0x18003ce70  lea     rax, [rbp+0B0h+var_48]
0x18003ce74  mov     [rsp+250h+var_208], rax
0x18003ce79  lea     rax, [rbp+0B0h+var_D8]
0x18003ce7d  mov     [rsp+250h+var_210], rax
0x18003ce82  lea     rax, [rbp+0B0h+var_127]
0x18003ce86  mov     [rsp+250h+var_218], rax
0x18003ce8b  lea     rax, [rbp+0B0h+var_120]
0x18003ce8f  mov     [rsp+250h+var_220], rax
0x18003ce94  lea     rax, [rbp+0B0h+var_11C]
0x18003ce98  mov     [rsp+250h+var_228], rax
0x18003ce9d  lea     rax, [rbp+0B0h+var_D0]
0x18003cea1  mov     [rsp+250h+var_230], rax
0x18003cea6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18003ceab  xorps   xmm0, xmm0
0x18003ceae  xor     eax, eax
0x18003ceb0  movups  xmmword ptr [rbx+120h], xmm0
0x18003ceb7  movups  xmmword ptr [rbx+130h], xmm0
0x18003cebe  mov     [rbx+140h], rax
0x18003cec5  mov     edx, edi
0x18003cec7  mov     rcx, rbx
0x18003ceca  call    FlushLookUpTableBucket
0x18003cecf  inc     edi
0x18003ced1  cmp     edi, esi
0x18003ced3  jb      short loc_18003CEC5
0x18003ced5  mov     rcx, [rbp+0B0h+var_28]
0x18003cedc  xor     rcx, rsp; StackCookie
0x18003cedf  call    __security_check_cookie
0x18003cee4  add     rsp, 238h
0x18003ceeb  pop     rdi
0x18003ceec  pop     rsi
0x18003ceed  pop     rbx
0x18003ceee  pop     rbp
0x18003ceef  retn
```
