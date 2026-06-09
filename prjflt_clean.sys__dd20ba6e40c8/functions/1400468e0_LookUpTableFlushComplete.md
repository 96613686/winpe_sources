# LookUpTableFlushComplete

- ea: `0x1400468e0`
- end: `0x140046cbe`
- name: `LookUpTableFlushComplete`
- size: `990`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140036f5c`
- `0x140046d60`
- `0x140046df0`
- `0x140046e60`

## callees

- `0x1400010ac`
- `0x14000a9b0`
- `0x14000ba20`
- `0x1400468e0`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, int a3, int a4)
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
    if ( a1[19].m128i_i32[2] > (unsigned int)result || !a1[18].m128i_i64[1] )
      a1[19].m128i_i32[2] = result;
    if ( a1[19].m128i_i32[1] < (unsigned int)result )
      a1[19].m128i_i32[1] = result;
    a1[18] = _mm_add_epi64(
               _mm_unpacklo_epi64((__m128i)(unsigned __int64)result, (__m128i)1uLL),
               _mm_loadu_si128(a1 + 18));
    if ( a1[18].m128i_i64[0] )
    {
      if ( (unsigned int)dword_14001A120 > 5
        && (qword_14001A130 & 0x200000000000LL) != 0
        && (qword_14001A138 & 0x200000000000LL) == qword_14001A138 )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = a1[20].m128i_u32[1];
        v34 = L"NumLargeEventFailures";
        v23 = a1[20].m128i_u32[0];
        v36 = L"NumAllocationFailures";
        v24 = a1[19].m128i_u32[3];
        v38 = L"NumBucketLimitReached";
        v25 = a1[19].m128i_u32[2];
        v40 = L"MinEntriesFlushed";
        v26 = a1[19].m128i_u32[1];
        v42 = L"MaxEntriesFlushed";
        v27 = a1[18].m128i_i64[0];
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = a1[19].m128i_u32[0];
        v46 = L"MaxEntriesStored";
        v29 = a1[18].m128i_i64[1];
        v48 = L"NumFlushes";
        v49 = 20;
        v7 = a1[21].m128i_i64[1];
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
          (unsigned int)&unk_14001718B,
          a3,
          a4,
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
      a1[18] = 0;
      a1[19] = 0;
      a1[20].m128i_i64[0] = 0;
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
0x1400468e0  mov     [rsp-8+arg_8], rbx
0x1400468e5  mov     [rsp-8+arg_10], rsi
0x1400468ea  push    rbp
0x1400468eb  push    rdi
0x1400468ec  push    r14
0x1400468ee  lea     rbp, [rsp-90h]
0x1400468f6  sub     rsp, 230h
0x1400468fd  mov     rax, cs:__security_cookie
0x140046904  xor     rax, rsp
0x140046907  mov     [rbp+0A0h+var_18], rax
0x14004690e  mov     eax, [rcx+100h]
0x140046914  xor     edi, edi
0x140046916  mov     rbx, rcx
0x140046919  test    eax, eax
0x14004691b  jz      loc_140046C96
0x140046921  cmp     [rcx+138h], eax
0x140046927  ja      short loc_140046932
0x140046929  cmp     [rcx+128h], rdi
0x140046930  jnz     short loc_140046938
0x140046932  mov     [rcx+138h], eax
0x140046938  cmp     [rcx+134h], eax
0x14004693e  jnb     short loc_140046946
0x140046940  mov     [rcx+134h], eax
0x140046946  mov     esi, 1
0x14004694b  movq    xmm1, rax
0x140046950  movq    xmm0, rsi
0x140046955  lea     r14d, [rsi+1Fh]
0x140046959  punpcklqdq xmm1, xmm0
0x14004695d  movdqu  xmm0, xmmword ptr [rcx+120h]
0x140046965  paddq   xmm1, xmm0
0x140046969  movdqu  xmmword ptr [rcx+120h], xmm1
0x140046971  cmp     [rcx+120h], rdi
0x140046978  jz      loc_140046C85
0x14004697e  mov     eax, cs:dword_14001A120
0x140046984  cmp     eax, 5
0x140046987  jbe     loc_140046C6B
0x14004698d  mov     rcx, cs:qword_14001A138
0x140046994  mov     rdx, 200000000000h
0x14004699e  mov     rax, cs:qword_14001A130
0x1400469a5  test    rdx, rax
0x1400469a8  jz      loc_140046C6B
0x1400469ae  mov     rax, rcx
0x1400469b1  and     rax, rdx
0x1400469b4  cmp     rax, rcx
0x1400469b7  jnz     loc_140046C6B
0x1400469bd  lea     ecx, [rsi+29h]
0x1400469c0  mov     [rbp+0A0h+var_120], 4
0x1400469c4  lea     rax, aSummarycount; "SummaryCount"
0x1400469cb  mov     [rbp+0A0h+var_A0], cx
0x1400469cf  mov     [rbp+0A0h+var_B8], rax
0x1400469d3  lea     eax, [rsi+17h]
0x1400469d6  mov     [rbp+0A0h+var_B0], ax
0x1400469da  mov     eax, [rbx+144h]
0x1400469e0  mov     [rbp+0A0h+var_108], rax
0x1400469e4  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1400469eb  mov     [rbp+0A0h+var_A8], rax
0x1400469ef  mov     eax, [rbx+140h]
0x1400469f5  mov     [rbp+0A0h+var_100], rax
0x1400469f9  lea     rax, aNumallocationf; "NumAllocationFailures"
0x140046a00  mov     [rbp+0A0h+var_98], rax
0x140046a04  mov     eax, [rbx+13Ch]
0x140046a0a  mov     [rbp+0A0h+var_F8], rax
0x140046a0e  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x140046a15  mov     [rbp+0A0h+var_88], rax
0x140046a19  mov     eax, [rbx+138h]
0x140046a1f  mov     [rbp+0A0h+var_F0], rax
0x140046a23  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x140046a2a  mov     [rbp+0A0h+var_78], rax
0x140046a2e  mov     eax, [rbx+134h]
0x140046a34  mov     [rbp+0A0h+var_E8], rax
0x140046a38  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x140046a3f  mov     [rbp+0A0h+var_68], rax
0x140046a43  mov     rax, [rbx+120h]
0x140046a4a  mov     [rbp+0A0h+var_E0], rax
0x140046a4e  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x140046a55  mov     [rbp+0A0h+var_58], rax
0x140046a59  lea     eax, [rsi+25h]
0x140046a5c  mov     [rbp+0A0h+var_50], ax
0x140046a60  mov     eax, [rbx+130h]
0x140046a66  mov     [rbp+0A0h+var_D8], rax
0x140046a6a  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x140046a71  mov     [rbp+0A0h+var_48], rax
0x140046a75  mov     rax, [rbx+128h]
0x140046a7c  mov     [rbp+0A0h+var_D0], rax
0x140046a80  lea     rax, aNumflushes; "NumFlushes"
0x140046a87  mov     [rbp+0A0h+var_38], rax
0x140046a8b  lea     eax, [rsi+13h]
0x140046a8e  mov     [rbp+0A0h+var_30], ax
0x140046a92  mov     rax, [rbx+158h]
0x140046a99  mov     [rbp+0A0h+var_90], cx
0x140046a9d  mov     [rbp+0A0h+var_80], cx
0x140046aa1  lea     ecx, [rsi+21h]
0x140046aa4  mov     [rbp+0A0h+var_114], esi
0x140046aa7  mov     [rbp+0A0h+var_11F], 4
0x140046aab  mov     [rbp+0A0h+var_11E], 4
0x140046aaf  mov     [rbp+0A0h+var_11D], 4
0x140046ab3  mov     [rbp+0A0h+var_11C], 4
0x140046ab7  mov     [rbp+0A0h+var_70], cx
0x140046abb  mov     [rbp+0A0h+var_11B], 4
0x140046abf  mov     [rbp+0A0h+var_60], cx
0x140046ac3  mov     [rbp+0A0h+var_11A], 4
0x140046ac7  mov     [rbp+0A0h+var_119], 4
0x140046acb  mov     [rbp+0A0h+var_40], r14w
0x140046ad0  mov     [rbp+0A0h+var_118], 4
0x140046ad4  mov     rcx, [rax+8]
0x140046ad8  lea     rax, [rbp+0A0h+var_28]
0x140046adc  mov     [rbp+0A0h+var_C8], rax
0x140046ae0  lea     rax, [rbp+0A0h+var_120]
0x140046ae4  mov     [rsp+240h+var_128], rax
0x140046aec  lea     rax, [rbp+0A0h+var_114]
0x140046af0  mov     [rsp+240h+var_130], rax
0x140046af8  lea     rax, [rbp+0A0h+var_B8]
0x140046afc  movups  xmm0, xmmword ptr [rcx-10h]
0x140046b00  mov     [rsp+240h+var_138], rax
0x140046b08  lea     rax, [rbp+0A0h+var_11F]
0x140046b0c  mov     [rsp+240h+var_140], rax
0x140046b14  lea     rax, [rbp+0A0h+var_108]
0x140046b18  mov     [rsp+240h+var_148], rax
0x140046b20  lea     rax, [rbp+0A0h+var_A8]
0x140046b24  mov     [rsp+240h+var_150], rax
0x140046b2c  lea     rax, [rbp+0A0h+var_11E]
0x140046b30  movdqu  [rbp+0A0h+var_28], xmm0
0x140046b35  mov     [rbp+0A0h+var_117], dil
0x140046b39  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x140046b40  mov     [rbp+0A0h+var_10C], 12Ch
0x140046b47  mov     [rbp+0A0h+var_C0], 1000000h
0x140046b4f  mov     [rsp+240h+var_158], rax
0x140046b57  lea     rdx, unk_14001718B
0x140046b5e  lea     rax, [rbp+0A0h+var_100]
0x140046b62  mov     [rsp+240h+var_160], rax
0x140046b6a  lea     rax, [rbp+0A0h+var_98]
0x140046b6e  mov     [rsp+240h+var_168], rax
0x140046b76  lea     rax, [rbp+0A0h+var_11D]
0x140046b7a  mov     [rsp+240h+var_170], rax
0x140046b82  lea     rax, [rbp+0A0h+var_F8]
0x140046b86  mov     [rsp+240h+var_178], rax
0x140046b8e  lea     rax, [rbp+0A0h+var_88]
0x140046b92  mov     [rsp+240h+var_180], rax
0x140046b9a  lea     rax, [rbp+0A0h+var_11C]
0x140046b9e  mov     [rsp+240h+var_188], rax
0x140046ba6  lea     rax, [rbp+0A0h+var_F0]
0x140046baa  mov     [rsp+240h+var_190], rax
0x140046bb2  lea     rax, [rbp+0A0h+var_78]
0x140046bb6  mov     [rsp+240h+var_198], rax
0x140046bbe  lea     rax, [rbp+0A0h+var_11B]
0x140046bc2  mov     [rsp+240h+var_1A0], rax
0x140046bca  lea     rax, [rbp+0A0h+var_E8]
0x140046bce  mov     [rsp+240h+var_1A8], rax
0x140046bd6  lea     rax, [rbp+0A0h+var_68]
0x140046bda  mov     [rsp+240h+var_1B0], rax
0x140046be2  lea     rax, [rbp+0A0h+var_11A]
0x140046be6  mov     [rsp+240h+var_1B8], rax
0x140046bee  lea     rax, [rbp+0A0h+var_E0]
0x140046bf2  mov     [rsp+240h+var_1C0], rax
0x140046bfa  lea     rax, [rbp+0A0h+var_58]
0x140046bfe  mov     [rsp+240h+var_1C8], rax
0x140046c03  lea     rax, [rbp+0A0h+var_119]
0x140046c07  mov     [rsp+240h+var_1D0], rax
0x140046c0c  lea     rax, [rbp+0A0h+var_D8]
0x140046c10  mov     [rsp+240h+var_1D8], rax
0x140046c15  lea     rax, [rbp+0A0h+var_48]
0x140046c19  mov     [rsp+240h+var_1E0], rax
0x140046c1e  lea     rax, [rbp+0A0h+var_118]
0x140046c22  mov     [rsp+240h+var_1E8], rax
0x140046c27  lea     rax, [rbp+0A0h+var_D0]
0x140046c2b  mov     [rsp+240h+var_1F0], rax
0x140046c30  lea     rax, [rbp+0A0h+var_38]
0x140046c34  mov     [rsp+240h+var_1F8], rax
0x140046c39  lea     rax, [rbp+0A0h+var_C8]
0x140046c3d  mov     [rsp+240h+var_200], rax
0x140046c42  lea     rax, [rbp+0A0h+var_117]
0x140046c46  mov     [rsp+240h+var_208], rax
0x140046c4b  lea     rax, [rbp+0A0h+var_110]
0x140046c4f  mov     [rsp+240h+var_210], rax
0x140046c54  lea     rax, [rbp+0A0h+var_10C]
0x140046c58  mov     [rsp+240h+var_218], rax
0x140046c5d  lea     rax, [rbp+0A0h+var_C0]
0x140046c61  mov     [rsp+240h+var_220], rax
0x140046c66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x140046c6b  xorps   xmm0, xmm0
0x140046c6e  xor     eax, eax
0x140046c70  movups  xmmword ptr [rbx+120h], xmm0
0x140046c77  movups  xmmword ptr [rbx+130h], xmm0
0x140046c7e  mov     [rbx+140h], rax
0x140046c85  mov     edx, edi
0x140046c87  mov     rcx, rbx
0x140046c8a  call    FlushLookUpTableBucket
0x140046c8f  add     edi, esi
0x140046c91  cmp     edi, r14d
0x140046c94  jb      short loc_140046C85
0x140046c96  mov     rcx, [rbp+0A0h+var_18]
0x140046c9d  xor     rcx, rsp; StackCookie
0x140046ca0  call    __security_check_cookie
0x140046ca5  lea     r11, [rsp+240h+var_10]
0x140046cad  mov     rbx, [r11+28h]
0x140046cb1  mov     rsi, [r11+30h]
0x140046cb5  mov     rsp, r11
0x140046cb8  pop     r14
0x140046cba  pop     rdi
0x140046cbb  pop     rbp
0x140046cbc  retn
```
