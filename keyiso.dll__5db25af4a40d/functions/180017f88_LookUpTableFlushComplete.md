# LookUpTableFlushComplete

- ea: `0x180017f88`
- end: `0x18001830a`
- name: `LookUpTableFlushComplete`
- size: `898`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017c60`
- `0x1800183b0`
- `0x180018410`
- `0x1800185ec`

## callees

- `0x180001008`
- `0x180017bdc`
- `0x180017f88`
- `0x180018488`
- `0x180018950`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 result; // rax
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
    if ( *(_QWORD *)(v5 + 272) )
    {
      if ( (unsigned int)dword_180025168 > 5
        && (qword_180025178 & 0x200000000000LL) != 0
        && (qword_180025180 & 0x200000000000LL) == qword_180025180 )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = *(unsigned int *)(a1 + 308);
        v34 = L"NumLargeEventFailures";
        v23 = *(unsigned int *)(a1 + 304);
        v36 = L"NumAllocationFailures";
        v24 = *(unsigned int *)(a1 + 300);
        v38 = L"NumBucketLimitReached";
        v25 = *(unsigned int *)(a1 + 296);
        v40 = L"MinEntriesFlushed";
        v26 = *(unsigned int *)(a1 + 292);
        v42 = L"MaxEntriesFlushed";
        v27 = *(_QWORD *)(a1 + 272);
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = *(unsigned int *)(a1 + 288);
        v46 = L"MaxEntriesStored";
        v29 = *(_QWORD *)(a1 + 280);
        v48 = L"NumFlushes";
        v49 = 20;
        v6 = *(_QWORD *)(a1 + 328);
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
        v7 = *(_QWORD *)(v6 + 8);
        v30 = &v50;
        v50 = *(_OWORD *)(v7 - 16);
        v18[0] = 0;
        v20 = -1;
        v21 = 300;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (__int64)byte_1800212ED,
          v3,
          v4,
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
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    do
      result = FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x180017f88  push    rbp
0x180017f8a  push    rbx
0x180017f8b  push    rsi
0x180017f8c  push    rdi
0x180017f8d  lea     rbp, [rsp-98h]
0x180017f95  sub     rsp, 238h
0x180017f9c  mov     rax, cs:__security_cookie
0x180017fa3  xor     rax, rsp
0x180017fa6  mov     [rbp+0B0h+var_28], rax
0x180017fad  mov     edx, [rcx+100h]
0x180017fb3  xor     edi, edi
0x180017fb5  mov     rbx, rcx
0x180017fb8  test    edx, edx
0x180017fba  jz      loc_1800182EF
0x180017fc0  call    UpdateInternalStatsOnFlush
0x180017fc5  lea     esi, [rdi+20h]
0x180017fc8  cmp     [rcx+110h], rdi
0x180017fcf  jz      loc_1800182DF
0x180017fd5  mov     eax, cs:dword_180025168
0x180017fdb  cmp     eax, 5
0x180017fde  jbe     loc_1800182C5
0x180017fe4  mov     rcx, cs:qword_180025180
0x180017feb  mov     rdx, 200000000000h
0x180017ff5  mov     rax, cs:qword_180025178
0x180017ffc  test    rdx, rax
0x180017fff  jz      loc_1800182C5
0x180018005  mov     rax, rcx
0x180018008  and     rax, rdx
0x18001800b  cmp     rax, rcx
0x18001800e  jnz     loc_1800182C5
0x180018014  lea     ecx, [rdi+2Ah]
0x180018017  mov     [rbp+0B0h+var_130], 4
0x18001801b  lea     rax, aSummarycount; "SummaryCount"
0x180018022  mov     [rbp+0B0h+var_B0], cx
0x180018026  mov     [rbp+0B0h+var_C8], rax
0x18001802a  lea     eax, [rdi+18h]
0x18001802d  mov     [rbp+0B0h+var_C0], ax
0x180018031  mov     eax, [rbx+134h]
0x180018037  mov     [rbp+0B0h+var_118], rax
0x18001803b  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x180018042  mov     [rbp+0B0h+var_B8], rax
0x180018046  mov     eax, [rbx+130h]
0x18001804c  mov     [rbp+0B0h+var_110], rax
0x180018050  lea     rax, aNumallocationf; "NumAllocationFailures"
0x180018057  mov     [rbp+0B0h+var_A8], rax
0x18001805b  mov     eax, [rbx+12Ch]
0x180018061  mov     [rbp+0B0h+var_108], rax
0x180018065  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18001806c  mov     [rbp+0B0h+var_98], rax
0x180018070  mov     eax, [rbx+128h]
0x180018076  mov     [rbp+0B0h+var_100], rax
0x18001807a  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180018081  mov     [rbp+0B0h+var_88], rax
0x180018085  mov     eax, [rbx+124h]
0x18001808b  mov     [rbp+0B0h+var_F8], rax
0x18001808f  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180018096  mov     [rbp+0B0h+var_78], rax
0x18001809a  mov     rax, [rbx+110h]
0x1800180a1  mov     [rbp+0B0h+var_F0], rax
0x1800180a5  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x1800180ac  mov     [rbp+0B0h+var_68], rax
0x1800180b0  lea     eax, [rdi+26h]
0x1800180b3  mov     [rbp+0B0h+var_60], ax
0x1800180b7  mov     eax, [rbx+120h]
0x1800180bd  mov     [rbp+0B0h+var_E8], rax
0x1800180c1  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x1800180c8  mov     [rbp+0B0h+var_58], rax
0x1800180cc  mov     rax, [rbx+118h]
0x1800180d3  mov     [rbp+0B0h+var_E0], rax
0x1800180d7  lea     rax, aNumflushes; "NumFlushes"
0x1800180de  mov     [rbp+0B0h+var_48], rax
0x1800180e2  lea     eax, [rdi+14h]
0x1800180e5  mov     [rbp+0B0h+var_40], ax
0x1800180e9  mov     rax, [rbx+148h]
0x1800180f0  mov     [rbp+0B0h+var_A0], cx
0x1800180f4  mov     [rbp+0B0h+var_90], cx
0x1800180f8  lea     ecx, [rdi+22h]
0x1800180fb  mov     [rbp+0B0h+var_124], 1
0x180018102  mov     [rbp+0B0h+var_12F], 4
0x180018106  mov     [rbp+0B0h+var_12E], 4
0x18001810a  mov     [rbp+0B0h+var_12D], 4
0x18001810e  mov     [rbp+0B0h+var_12C], 4
0x180018112  mov     [rbp+0B0h+var_80], cx
0x180018116  mov     [rbp+0B0h+var_12B], 4
0x18001811a  mov     [rbp+0B0h+var_70], cx
0x18001811e  mov     [rbp+0B0h+var_12A], 4
0x180018122  mov     [rbp+0B0h+var_129], 4
0x180018126  mov     [rbp+0B0h+var_50], si
0x18001812a  mov     [rbp+0B0h+var_128], 4
0x18001812e  mov     rcx, [rax+8]
0x180018132  lea     rax, [rbp+0B0h+var_38]
0x180018136  mov     [rbp+0B0h+var_D8], rax
0x18001813a  lea     rax, [rbp+0B0h+var_130]
0x18001813e  mov     [rsp+250h+var_138], rax
0x180018146  lea     rax, [rbp+0B0h+var_124]
0x18001814a  mov     [rsp+250h+var_140], rax
0x180018152  lea     rax, [rbp+0B0h+var_C8]
0x180018156  movups  xmm0, xmmword ptr [rcx-10h]
0x18001815a  mov     [rsp+250h+var_148], rax
0x180018162  lea     rax, [rbp+0B0h+var_12F]
0x180018166  mov     [rsp+250h+var_150], rax
0x18001816e  lea     rax, [rbp+0B0h+var_118]
0x180018172  mov     [rsp+250h+var_158], rax
0x18001817a  lea     rax, [rbp+0B0h+var_B8]
0x18001817e  mov     [rsp+250h+var_160], rax
0x180018186  lea     rax, [rbp+0B0h+var_12E]
0x18001818a  movdqu  [rbp+0B0h+var_38], xmm0
0x18001818f  mov     [rbp+0B0h+var_127], dil
0x180018193  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x18001819a  mov     [rbp+0B0h+var_11C], 12Ch
0x1800181a1  mov     [rbp+0B0h+var_D0], 1000000h
0x1800181a9  mov     [rsp+250h+var_168], rax
0x1800181b1  lea     rdx, byte_1800212ED
0x1800181b8  lea     rax, [rbp+0B0h+var_110]
0x1800181bc  mov     [rsp+250h+var_170], rax
0x1800181c4  lea     rax, [rbp+0B0h+var_A8]
0x1800181c8  mov     [rsp+250h+var_178], rax
0x1800181d0  lea     rax, [rbp+0B0h+var_12D]
0x1800181d4  mov     [rsp+250h+var_180], rax
0x1800181dc  lea     rax, [rbp+0B0h+var_108]
0x1800181e0  mov     [rsp+250h+var_188], rax
0x1800181e8  lea     rax, [rbp+0B0h+var_98]
0x1800181ec  mov     [rsp+250h+var_190], rax
0x1800181f4  lea     rax, [rbp+0B0h+var_12C]
0x1800181f8  mov     [rsp+250h+var_198], rax
0x180018200  lea     rax, [rbp+0B0h+var_100]
0x180018204  mov     [rsp+250h+var_1A0], rax
0x18001820c  lea     rax, [rbp+0B0h+var_88]
0x180018210  mov     [rsp+250h+var_1A8], rax
0x180018218  lea     rax, [rbp+0B0h+var_12B]
0x18001821c  mov     [rsp+250h+var_1B0], rax
0x180018224  lea     rax, [rbp+0B0h+var_F8]
0x180018228  mov     [rsp+250h+var_1B8], rax
0x180018230  lea     rax, [rbp+0B0h+var_78]
0x180018234  mov     [rsp+250h+var_1C0], rax
0x18001823c  lea     rax, [rbp+0B0h+var_12A]
0x180018240  mov     [rsp+250h+var_1C8], rax
0x180018248  lea     rax, [rbp+0B0h+var_F0]
0x18001824c  mov     [rsp+250h+var_1D0], rax
0x180018254  lea     rax, [rbp+0B0h+var_68]
0x180018258  mov     [rsp+250h+var_1D8], rax
0x18001825d  lea     rax, [rbp+0B0h+var_129]
0x180018261  mov     [rsp+250h+var_1E0], rax
0x180018266  lea     rax, [rbp+0B0h+var_E8]
0x18001826a  mov     [rsp+250h+var_1E8], rax
0x18001826f  lea     rax, [rbp+0B0h+var_58]
0x180018273  mov     [rsp+250h+var_1F0], rax
0x180018278  lea     rax, [rbp+0B0h+var_128]
0x18001827c  mov     [rsp+250h+var_1F8], rax
0x180018281  lea     rax, [rbp+0B0h+var_E0]
0x180018285  mov     [rsp+250h+var_200], rax
0x18001828a  lea     rax, [rbp+0B0h+var_48]
0x18001828e  mov     [rsp+250h+var_208], rax
0x180018293  lea     rax, [rbp+0B0h+var_D8]
0x180018297  mov     [rsp+250h+var_210], rax
0x18001829c  lea     rax, [rbp+0B0h+var_127]
0x1800182a0  mov     [rsp+250h+var_218], rax
0x1800182a5  lea     rax, [rbp+0B0h+var_120]
0x1800182a9  mov     [rsp+250h+var_220], rax
0x1800182ae  lea     rax, [rbp+0B0h+var_11C]
0x1800182b2  mov     [rsp+250h+var_228], rax
0x1800182b7  lea     rax, [rbp+0B0h+var_D0]
0x1800182bb  mov     [rsp+250h+var_230], rax
0x1800182c0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1800182c5  xorps   xmm0, xmm0
0x1800182c8  xor     eax, eax
0x1800182ca  movups  xmmword ptr [rbx+110h], xmm0
0x1800182d1  movups  xmmword ptr [rbx+120h], xmm0
0x1800182d8  mov     [rbx+130h], rax
0x1800182df  mov     edx, edi
0x1800182e1  mov     rcx, rbx
0x1800182e4  call    FlushLookUpTableBucket
0x1800182e9  inc     edi
0x1800182eb  cmp     edi, esi
0x1800182ed  jb      short loc_1800182DF
0x1800182ef  mov     rcx, [rbp+0B0h+var_28]
0x1800182f6  xor     rcx, rsp; StackCookie
0x1800182f9  call    __security_check_cookie
0x1800182fe  add     rsp, 238h
0x180018305  pop     rdi
0x180018306  pop     rsi
0x180018307  pop     rbx
0x180018308  pop     rbp
0x180018309  retn
```
