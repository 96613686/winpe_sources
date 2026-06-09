# LookUpTableFlushComplete

- ea: `0x180047148`
- end: `0x1800474b8`
- name: `LookUpTableFlushComplete`
- size: `880`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180046e20`
- `0x180047560`
- `0x1800475c0`
- `0x180047780`

## callees

- `0x180001008`
- `0x180015668`
- `0x18001cef0`
- `0x180046d68`
- `0x180047148`
- `0x180047638`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
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
      if ( (unsigned int)dword_180061150 > 5 && tlgKeywordOn((__int64)&dword_180061150, 0x200000000000LL) )
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
          (__int64)byte_18005A013,
          v4,
          v5,
          (__int64)&v30,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v17,
          (__int64 *)&v29,
          (__int64 *)&v47,
          (__int64)&v28,
          (__int64)&v16,
          (__int64 *)&v45,
          (__int64)&v27,
          (__int64)&v15,
          (__int64 *)&v43,
          (__int64)&v26,
          (__int64)&v14,
          (__int64 *)&v41,
          (__int64)&v25,
          (__int64)&v13,
          (__int64 *)&v39,
          (__int64)&v24,
          (__int64)&v12,
          (__int64 *)&v37,
          (__int64)&v23,
          (__int64)&v11,
          (__int64 *)&v35,
          (__int64)&v22,
          (__int64)&v10,
          (__int64 *)&v33,
          (__int64)&v21,
          (__int64)&v9,
          (__int64 *)&v31,
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
0x180047148  push    rbp
0x18004714a  push    rbx
0x18004714b  push    rsi
0x18004714c  push    rdi
0x18004714d  lea     rbp, [rsp-98h]
0x180047155  sub     rsp, 238h
0x18004715c  mov     rax, cs:__security_cookie
0x180047163  xor     rax, rsp
0x180047166  mov     [rbp+0B0h+var_28], rax
0x18004716d  mov     edx, [rcx+100h]
0x180047173  xor     edi, edi
0x180047175  mov     rbx, rcx
0x180047178  test    edx, edx
0x18004717a  jz      loc_18004749D
0x180047180  call    UpdateInternalStatsOnFlush
0x180047185  lea     esi, [rdi+20h]
0x180047188  cmp     [rcx+110h], rdi
0x18004718f  jz      loc_18004748D
0x180047195  mov     eax, cs:dword_180061150
0x18004719b  cmp     eax, 5
0x18004719e  jbe     loc_180047473
0x1800471a4  mov     rdx, 200000000000h
0x1800471ae  lea     rcx, dword_180061150
0x1800471b5  call    _tlgKeywordOn
0x1800471ba  test    al, al
0x1800471bc  jz      loc_180047473
0x1800471c2  lea     ecx, [rdi+2Ah]
0x1800471c5  mov     [rbp+0B0h+var_130], 4
0x1800471c9  lea     rax, aSummarycount; "SummaryCount"
0x1800471d0  mov     [rbp+0B0h+var_B0], cx
0x1800471d4  mov     [rbp+0B0h+var_C8], rax
0x1800471d8  lea     eax, [rdi+18h]
0x1800471db  mov     [rbp+0B0h+var_C0], ax
0x1800471df  mov     eax, [rbx+134h]
0x1800471e5  mov     [rbp+0B0h+var_118], rax
0x1800471e9  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1800471f0  mov     [rbp+0B0h+var_B8], rax
0x1800471f4  mov     eax, [rbx+130h]
0x1800471fa  mov     [rbp+0B0h+var_110], rax
0x1800471fe  lea     rax, aNumallocationf; "NumAllocationFailures"
0x180047205  mov     [rbp+0B0h+var_A8], rax
0x180047209  mov     eax, [rbx+12Ch]
0x18004720f  mov     [rbp+0B0h+var_108], rax
0x180047213  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18004721a  mov     [rbp+0B0h+var_98], rax
0x18004721e  mov     eax, [rbx+128h]
0x180047224  mov     [rbp+0B0h+var_100], rax
0x180047228  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18004722f  mov     [rbp+0B0h+var_88], rax
0x180047233  mov     eax, [rbx+124h]
0x180047239  mov     [rbp+0B0h+var_F8], rax
0x18004723d  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180047244  mov     [rbp+0B0h+var_78], rax
0x180047248  mov     rax, [rbx+110h]
0x18004724f  mov     [rbp+0B0h+var_F0], rax
0x180047253  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18004725a  mov     [rbp+0B0h+var_68], rax
0x18004725e  lea     eax, [rdi+26h]
0x180047261  mov     [rbp+0B0h+var_60], ax
0x180047265  mov     eax, [rbx+120h]
0x18004726b  mov     [rbp+0B0h+var_E8], rax
0x18004726f  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180047276  mov     [rbp+0B0h+var_58], rax
0x18004727a  mov     rax, [rbx+118h]
0x180047281  mov     [rbp+0B0h+var_E0], rax
0x180047285  lea     rax, aNumflushes; "NumFlushes"
0x18004728c  mov     [rbp+0B0h+var_48], rax
0x180047290  lea     eax, [rdi+14h]
0x180047293  mov     [rbp+0B0h+var_40], ax
0x180047297  mov     rax, [rbx+148h]
0x18004729e  mov     [rbp+0B0h+var_A0], cx
0x1800472a2  mov     [rbp+0B0h+var_90], cx
0x1800472a6  lea     ecx, [rdi+22h]
0x1800472a9  mov     [rbp+0B0h+var_124], 1
0x1800472b0  mov     [rbp+0B0h+var_12F], 4
0x1800472b4  mov     [rbp+0B0h+var_12E], 4
0x1800472b8  mov     [rbp+0B0h+var_12D], 4
0x1800472bc  mov     [rbp+0B0h+var_12C], 4
0x1800472c0  mov     [rbp+0B0h+var_80], cx
0x1800472c4  mov     [rbp+0B0h+var_12B], 4
0x1800472c8  mov     [rbp+0B0h+var_70], cx
0x1800472cc  mov     [rbp+0B0h+var_12A], 4
0x1800472d0  mov     [rbp+0B0h+var_129], 4
0x1800472d4  mov     [rbp+0B0h+var_50], si
0x1800472d8  mov     [rbp+0B0h+var_128], 4
0x1800472dc  mov     rcx, [rax+8]
0x1800472e0  lea     rax, [rbp+0B0h+var_38]
0x1800472e4  mov     [rbp+0B0h+var_D8], rax
0x1800472e8  lea     rax, [rbp+0B0h+var_130]
0x1800472ec  mov     [rsp+250h+var_138], rax
0x1800472f4  lea     rax, [rbp+0B0h+var_124]
0x1800472f8  mov     [rsp+250h+var_140], rax
0x180047300  lea     rax, [rbp+0B0h+var_C8]
0x180047304  movups  xmm0, xmmword ptr [rcx-10h]
0x180047308  mov     [rsp+250h+var_148], rax
0x180047310  lea     rax, [rbp+0B0h+var_12F]
0x180047314  mov     [rsp+250h+var_150], rax
0x18004731c  lea     rax, [rbp+0B0h+var_118]
0x180047320  mov     [rsp+250h+var_158], rax
0x180047328  lea     rax, [rbp+0B0h+var_B8]
0x18004732c  mov     [rsp+250h+var_160], rax
0x180047334  lea     rax, [rbp+0B0h+var_12E]
0x180047338  movdqu  [rbp+0B0h+var_38], xmm0
0x18004733d  mov     [rbp+0B0h+var_127], dil
0x180047341  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x180047348  mov     [rbp+0B0h+var_11C], 12Ch
0x18004734f  mov     [rbp+0B0h+var_D0], 1000000h
0x180047357  mov     [rsp+250h+var_168], rax
0x18004735f  lea     rdx, byte_18005A013
0x180047366  lea     rax, [rbp+0B0h+var_110]
0x18004736a  mov     [rsp+250h+var_170], rax
0x180047372  lea     rax, [rbp+0B0h+var_A8]
0x180047376  mov     [rsp+250h+var_178], rax
0x18004737e  lea     rax, [rbp+0B0h+var_12D]
0x180047382  mov     [rsp+250h+var_180], rax
0x18004738a  lea     rax, [rbp+0B0h+var_108]
0x18004738e  mov     [rsp+250h+var_188], rax
0x180047396  lea     rax, [rbp+0B0h+var_98]
0x18004739a  mov     [rsp+250h+var_190], rax
0x1800473a2  lea     rax, [rbp+0B0h+var_12C]
0x1800473a6  mov     [rsp+250h+var_198], rax
0x1800473ae  lea     rax, [rbp+0B0h+var_100]
0x1800473b2  mov     [rsp+250h+var_1A0], rax
0x1800473ba  lea     rax, [rbp+0B0h+var_88]
0x1800473be  mov     [rsp+250h+var_1A8], rax
0x1800473c6  lea     rax, [rbp+0B0h+var_12B]
0x1800473ca  mov     [rsp+250h+var_1B0], rax
0x1800473d2  lea     rax, [rbp+0B0h+var_F8]
0x1800473d6  mov     [rsp+250h+var_1B8], rax
0x1800473de  lea     rax, [rbp+0B0h+var_78]
0x1800473e2  mov     [rsp+250h+var_1C0], rax
0x1800473ea  lea     rax, [rbp+0B0h+var_12A]
0x1800473ee  mov     [rsp+250h+var_1C8], rax
0x1800473f6  lea     rax, [rbp+0B0h+var_F0]
0x1800473fa  mov     [rsp+250h+var_1D0], rax
0x180047402  lea     rax, [rbp+0B0h+var_68]
0x180047406  mov     [rsp+250h+var_1D8], rax
0x18004740b  lea     rax, [rbp+0B0h+var_129]
0x18004740f  mov     [rsp+250h+var_1E0], rax
0x180047414  lea     rax, [rbp+0B0h+var_E8]
0x180047418  mov     [rsp+250h+var_1E8], rax
0x18004741d  lea     rax, [rbp+0B0h+var_58]
0x180047421  mov     [rsp+250h+var_1F0], rax
0x180047426  lea     rax, [rbp+0B0h+var_128]
0x18004742a  mov     [rsp+250h+var_1F8], rax
0x18004742f  lea     rax, [rbp+0B0h+var_E0]
0x180047433  mov     [rsp+250h+var_200], rax
0x180047438  lea     rax, [rbp+0B0h+var_48]
0x18004743c  mov     [rsp+250h+var_208], rax
0x180047441  lea     rax, [rbp+0B0h+var_D8]
0x180047445  mov     [rsp+250h+var_210], rax
0x18004744a  lea     rax, [rbp+0B0h+var_127]
0x18004744e  mov     [rsp+250h+var_218], rax
0x180047453  lea     rax, [rbp+0B0h+var_120]
0x180047457  mov     [rsp+250h+var_220], rax
0x18004745c  lea     rax, [rbp+0B0h+var_11C]
0x180047460  mov     [rsp+250h+var_228], rax
0x180047465  lea     rax, [rbp+0B0h+var_D0]
0x180047469  mov     [rsp+250h+var_230], rax
0x18004746e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180047473  xorps   xmm0, xmm0
0x180047476  xor     eax, eax
0x180047478  movups  xmmword ptr [rbx+110h], xmm0
0x18004747f  movups  xmmword ptr [rbx+120h], xmm0
0x180047486  mov     [rbx+130h], rax
0x18004748d  mov     edx, edi
0x18004748f  mov     rcx, rbx
0x180047492  call    FlushLookUpTableBucket
0x180047497  inc     edi
0x180047499  cmp     edi, esi
0x18004749b  jb      short loc_18004748D
0x18004749d  mov     rcx, [rbp+0B0h+var_28]
0x1800474a4  xor     rcx, rsp; StackCookie
0x1800474a7  call    __security_check_cookie
0x1800474ac  add     rsp, 238h
0x1800474b3  pop     rdi
0x1800474b4  pop     rsi
0x1800474b5  pop     rbx
0x1800474b6  pop     rbp
0x1800474b7  retn
```
