# Spctl_Subsystem_CreatePool_L1(_SP_SPCTL_PARAMS *,void *)

- ea: `0x1800a99c0`
- end: `0x1800aa194`
- name: `?Spctl_Subsystem_CreatePool_L1@@YAKPEAU_SP_SPCTL_PARAMS@@PEAX@Z`
- size: `2004`
- prototype: `unsigned int(struct _SP_SPCTL_PARAMS *, void *)`
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x1800958b8`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180006350`
- `0x180006dd4`
- `0x180007221`
- `0x18000c644`
- `0x18000cd3c`
- `0x180026a6c`
- `0x18002aae0`
- `0x18002ab30`
- `0x18002aba4`
- `0x18002ac20`
- `0x18002d170`
- `0x18002d880`
- `0x180033aac`
- `0x180037890`
- `0x18004658c`
- `0x180047afc`
- `0x18004ba30`
- `0x180069b88`
- `0x18006b4b0`
- `0x1800a99c0`
- `0x1800aef0c`
- `0x1801bbf68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa08e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa116`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa08e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa116`

## string_xrefs

- `0x1800a99f6`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a9ba0`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a9c13`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a9cdf`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a9d90`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a9ea0`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800a9f74`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800aa025`: `Spctl_Subsystem_CreatePool_L1`
- `0x1800aa05b`: `Spctl_Subsystem_CreatePool_L1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spctl_Subsystem_CreatePool_L1(struct _SP_SPCTL_PARAMS *a1, void *a2, int a3, int a4)
{
  struct _SP_POOL_INFO *v6; // rsi
  unsigned int v7; // eax
  unsigned int PoolErrors; // r14d
  __int64 v10; // rdi
  __int64 v11; // r15
  unsigned int v12; // ecx
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  unsigned int v17; // ebx
  __int64 Drives; // rax
  unsigned int v19; // eax
  int v20; // r8d
  int v21; // r9d
  int PoolTemplate; // eax
  int v23; // r8d
  int v24; // r9d
  char v25; // r11
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rax
  unsigned int v30; // ecx
  __int64 v31; // rax
  unsigned int v32; // ecx
  __int64 v33; // rax
  unsigned int v34; // ecx
  __int64 v35; // rdx
  DWORD LastError; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rax
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v45; // rax
  int v46; // r8d
  int v47; // r9d
  int v48; // ecx
  int v49; // [rsp+40h] [rbp-99h] BYREF
  int v50; // [rsp+44h] [rbp-95h] BYREF
  struct _SP_POOL_INFO *v51; // [rsp+48h] [rbp-91h] BYREF
  const char *v52; // [rsp+50h] [rbp-89h] BYREF
  int v53; // [rsp+58h] [rbp-81h]
  struct CSpCluster *v54; // [rsp+60h] [rbp-79h] BYREF
  unsigned int v55; // [rsp+68h] [rbp-71h] BYREF
  HLOCAL v56; // [rsp+70h] [rbp-69h] BYREF
  struct _LIST_ENTRY hMem; // [rsp+78h] [rbp-61h] BYREF
  const char *v58; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v59[16]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v60[40]; // [rsp+A0h] [rbp-39h] BYREF
  struct _GUID Buf1[2]; // [rsp+C8h] [rbp-11h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v49 = 390;
    v51 = (struct _SP_POOL_INFO *)"Spctl_Subsystem_CreatePool_L1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"Spctl_Subsystem_CreatePool_L1",
      (unsigned int)&word_18032656E,
      a3,
      a4,
      (__int64)&v51,
      (__int64)&v49);
  }
  v54 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v54);
  v54 = 0;
  v55 = 0;
  v56 = 0;
  memset_0(v60, 0, 0x48u);
  v6 = 0;
  v51 = 0;
  v7 = *((_DWORD *)a1 + 142);
  if ( v7 < 0x18 )
    goto LABEL_4;
  if ( *((_DWORD *)a1 + 146) < 0x220u )
  {
    **((_DWORD **)a1 + 74) = 544;
LABEL_4:
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v54);
    return 87;
  }
  PoolErrors = 0;
  v10 = *((_QWORD *)a1 + 70);
  v11 = *((_QWORD *)a1 + 72);
  hMem.Blink = &hMem;
  hMem.Flink = &hMem;
  v12 = *(_DWORD *)(v10 + 12);
  if ( v7 < v12 )
    goto LABEL_78;
  if ( *(_DWORD *)(v10 + 16) != 2001 )
    goto LABEL_78;
  if ( v12 < *(_DWORD *)(v10 + 8) )
    goto LABEL_78;
  if ( *(_DWORD *)(v10 + 8) < 0x52u )
    goto LABEL_78;
  v13 = *(unsigned int *)(v10 + 32);
  if ( (unsigned int)v13 < *(_DWORD *)(v10 + 8) )
    goto LABEL_78;
  if ( (unsigned int)v13 > v12 )
    goto LABEL_78;
  if ( (v13 & 3) != 0 )
    goto LABEL_78;
  v14 = v12 - v13;
  if ( v14 < 4 )
    goto LABEL_78;
  v15 = v10 + v13;
  v16 = 16LL * *(unsigned int *)(v10 + v13);
  if ( v16 > 0xFFFFFFFF || (int)v16 + 4 > v14 )
    goto LABEL_78;
  v17 = 0;
  Drives = SuexGetDrives(v59, v15, 0, 0, &hMem, &v55, &v56);
  v52 = *(const char **)Drives;
  v53 = *(_DWORD *)(Drives + 8);
  if ( _mm_cvtsi128_si32((__m128i)(unsigned __int64)v52) < 0 )
  {
    v19 = _status_t::ToSMRC(&v52);
    PoolErrors = v19;
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v49 = v19;
      v50 = 516;
      v51 = (struct _SP_POOL_INFO *)"Spctl_Subsystem_CreatePool_L1";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        dword_18039EB68,
        (unsigned int)&byte_180321E7F,
        v20,
        v21,
        (__int64)&v51,
        (__int64)&v50,
        (__int64)&v49);
    }
    goto LABEL_79;
  }
  PoolTemplate = SuGetPoolTemplate(*(unsigned int *)(v10 + 24), &hMem, &v51);
  v25 = 0;
  if ( !PoolTemplate )
  {
    PoolErrors = GleToSmpReturnCode();
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v50 = PoolErrors;
      v49 = 529;
      v52 = "Spctl_Subsystem_CreatePool_L1";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v26,
        (unsigned int)byte_180329173,
        v27,
        v28,
        (__int64)&v52,
        (__int64)&v49,
        (__int64)&v50);
    }
    v6 = v51;
    goto LABEL_79;
  }
  v29 = *(unsigned int *)(v10 + 36);
  v6 = v51;
  if ( (_DWORD)v29 )
  {
    if ( (unsigned int)v29 < *(_DWORD *)(v10 + 8) )
      goto LABEL_78;
    v30 = *(_DWORD *)(v10 + 12);
    if ( (unsigned int)v29 > v30
      || (v29 & 1) != 0
      || (int)StringCbLengthW((const unsigned __int16 *)(v10 + v29), v30 - (unsigned int)v29, (unsigned __int64 *)&v51) < 0 )
    {
      goto LABEL_78;
    }
    if ( (int)StringCchCopyW(
                (unsigned __int16 *)v6 + 12,
                0x100u,
                (const unsigned __int16 *)(v10 + *(unsigned int *)(v10 + 36))) < 0 )
    {
      PoolErrors = 5;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v50 = 5;
        v49 = 561;
        v52 = "Spctl_Subsystem_CreatePool_L1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          5,
          (unsigned int)word_18031FDDA,
          v23,
          v24,
          (__int64)&v52,
          (__int64)&v49,
          (__int64)&v50);
      }
      goto LABEL_79;
    }
  }
  v31 = *(unsigned int *)(v10 + 40);
  if ( (_DWORD)v31 )
  {
    if ( (unsigned int)v31 < *(_DWORD *)(v10 + 8) )
      goto LABEL_78;
    v32 = *(_DWORD *)(v10 + 12);
    if ( (unsigned int)v31 > v32
      || (v31 & 1) != 0
      || (int)StringCbLengthW((const unsigned __int16 *)(v10 + v31), v32 - (unsigned int)v31, (unsigned __int64 *)&v51) < 0 )
    {
      goto LABEL_78;
    }
    if ( (int)StringCchCopyW(
                (unsigned __int16 *)v6 + 268,
                0x400u,
                (const unsigned __int16 *)(v10 + *(unsigned int *)(v10 + 40))) < 0 )
    {
      PoolErrors = 5;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v50 = 5;
        v49 = 594;
        v52 = "Spctl_Subsystem_CreatePool_L1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          5,
          (unsigned int)byte_1803288BD,
          v23,
          v24,
          (__int64)&v52,
          (__int64)&v49,
          (__int64)&v50);
      }
      goto LABEL_79;
    }
  }
  if ( *(_BYTE *)(v10 + 48) != v25 )
    *((_DWORD *)v6 + 672) = SmpToSpProvisioningType(*(unsigned __int16 *)(v10 + 50));
  if ( *(_DWORD *)(v10 + 8) >= 0x56u && *(_BYTE *)(v10 + 82) != v25 )
    *((_DWORD *)v6 + 676) = SmpToSpMediaType(*(unsigned __int16 *)(v10 + 84));
  if ( *(_BYTE *)(v10 + 60) != v25 )
    *((_DWORD *)v6 + 679) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v10 + 62));
  v33 = *(unsigned int *)(v10 + 44);
  if ( !(_DWORD)v33 )
  {
LABEL_54:
    if ( *(_BYTE *)(v10 + 52) != v25 )
      *((_DWORD *)v6 + 665) = *(_DWORD *)(v10 + 56);
    if ( *(_DWORD *)(v10 + 8) >= 0x68u && *(_BYTE *)(v10 + 88) != v25 )
    {
      if ( *(_QWORD *)(v10 + 96) > 0xFFFFFFFF )
      {
        PoolErrors = 5;
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v50 = 5;
          v49 = 655;
          v52 = "Spctl_Subsystem_CreatePool_L1";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            5,
            (unsigned int)byte_180326F53,
            v23,
            v24,
            (__int64)&v52,
            (__int64)&v49,
            (__int64)&v50);
        }
        goto LABEL_79;
      }
      *((_DWORD *)v6 + 662) = *(_DWORD *)(v10 + 96);
    }
    if ( *(_DWORD *)(v10 + 8) >= 0x78u && *(_BYTE *)(v10 + 104) != v25 )
      *((_QWORD *)v6 + 335) = *(_QWORD *)(v10 + 112);
    if ( *(_BYTE *)(v10 + 64) != v25 )
      *((_QWORD *)v6 + 350) = *(_QWORD *)(v10 + 72);
    if ( *(_BYTE *)(v10 + 80) != v25 && *(_BYTE *)(v10 + 81) == 1 )
      *((_QWORD *)v6 + 350) = -1;
    if ( (unsigned int)SuexCreatePool(
                         v6,
                         &hMem,
                         v55,
                         (unsigned __int16 *const)(v11 + 4),
                         a2,
                         (struct _SUEX_EXTENDEDSTATUS_OBJECT **)&v56) )
    {
      if ( *(_BYTE *)(v10 + 28) )
      {
        SuexParseIdLite((const unsigned __int16 *)(v11 + 4), (struct _SUEX_ID *)v60);
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v54);
        if ( CSpCluster::GetInstance(&v54) == MI_RESULT_OK )
        {
          v40 = CSpCluster::AddPoolToCluster(v54, v59, Buf1);
          v52 = *(const char **)v40;
          v53 = *(_DWORD *)(v40 + 8);
          if ( _mm_cvtsi128_si32((__m128i)(unsigned __int64)v52) < 0 )
          {
            PoolErrors = _status_t::ToSMRC(&v52);
            if ( (unsigned int)dword_18039EB68 > 2 )
            {
              v50 = PoolErrors;
              v49 = 698;
              v52 = "Spctl_Subsystem_CreatePool_L1";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v41,
                (unsigned int)&word_1803231B6,
                v42,
                v43,
                (__int64)&v52,
                (__int64)&v49,
                (__int64)&v50);
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      PoolErrors = _TranslateCreatePoolErrors(LastError);
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v50 = PoolErrors;
        v49 = 684;
        v52 = "Spctl_Subsystem_CreatePool_L1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v37,
          (unsigned int)byte_180329CC9,
          v38,
          v39,
          (__int64)&v52,
          (__int64)&v49,
          (__int64)&v50);
      }
    }
    goto LABEL_79;
  }
  if ( (unsigned int)v33 >= *(_DWORD *)(v10 + 8) )
  {
    v34 = *(_DWORD *)(v10 + 12);
    if ( (unsigned int)v33 <= v34
      && (v33 & 1) == 0
      && (int)StringCbLengthW((const unsigned __int16 *)(v10 + v33), v34 - (unsigned int)v33, (unsigned __int64 *)&v51) >= 0 )
    {
      *((_DWORD *)v6 + 680) = SmpToSpResiliencyType(v10 + *(unsigned int *)(v10 + 44), v35);
      v25 = 0;
      goto LABEL_54;
    }
  }
LABEL_78:
  v17 = 87;
LABEL_79:
  while ( 1 )
  {
    Flink = hMem.Flink;
    if ( hMem.Flink == &hMem )
      break;
    if ( hMem.Flink->Blink != &hMem || (v45 = hMem.Flink->Flink, hMem.Flink->Flink->Blink != hMem.Flink) )
      __fastfail(3u);
    hMem.Flink = hMem.Flink->Flink;
    v45->Blink = &hMem;
    LocalFree(Flink);
  }
  if ( PoolErrors && PoolErrors != 46011 && memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    SuexDeletePool(Buf1, a2);
  _FillMethodResponse(v11, *((unsigned int *)a1 + 146), PoolErrors, v56, *((_QWORD *)a1 + 74));
  if ( v6 )
    LocalFree(v6);
  v48 = (int)v56;
  if ( v56 )
  {
    LocalFree(v56);
    v56 = 0;
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v50 = 733;
    v58 = "Spctl_Subsystem_CreatePool_L1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v48,
      (unsigned int)word_180322CD2,
      v46,
      v47,
      (__int64)&v58,
      (__int64)&v50);
  }
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v54);
  return v17;
}

```

## disassembly

```asm
0x1800a99c0  mov     [rsp-8+arg_10], rbx
0x1800a99c5  push    rbp
0x1800a99c6  push    rsi
0x1800a99c7  push    rdi
0x1800a99c8  push    r12
0x1800a99ca  push    r13
0x1800a99cc  push    r14
0x1800a99ce  push    r15
0x1800a99d0  lea     rbp, [rsp-27h]
0x1800a99d5  sub     rsp, 100h
0x1800a99dc  mov     rax, cs:__security_cookie
0x1800a99e3  xor     rax, rsp
0x1800a99e6  mov     [rbp+57h+var_40], rax
0x1800a99ea  mov     r12, rdx
0x1800a99ed  mov     r13, rcx
0x1800a99f0  mov     eax, cs:dword_18039EB68
0x1800a99f6  lea     rcx, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a99fd  cmp     eax, 5
0x1800a9a00  jbe     short loc_1800A9A2F
0x1800a9a02  mov     [rsp+130h+var_F0], 186h
0x1800a9a0a  mov     [rsp+130h+var_E8], rcx
0x1800a9a0f  lea     rax, [rsp+130h+var_F0]
0x1800a9a14  mov     [rsp+130h+var_108], rax
0x1800a9a19  lea     rax, [rsp+130h+var_E8]
0x1800a9a1e  mov     [rsp+130h+var_110], rax
0x1800a9a23  lea     rdx, word_18032656E
0x1800a9a2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a9a2f  xor     ebx, ebx
0x1800a9a31  mov     [rbp+57h+var_D0], rbx
0x1800a9a35  lea     rcx, [rbp+57h+var_D0]
0x1800a9a39  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800a9a3e  mov     [rbp+57h+var_D0], rbx
0x1800a9a42  mov     [rbp+57h+var_C8], ebx
0x1800a9a45  mov     [rbp+57h+var_C0], rbx
0x1800a9a49  xor     edx, edx; Val
0x1800a9a4b  lea     r8d, [rbx+48h]; Size
0x1800a9a4f  lea     rcx, [rbp+57h+var_90]; void *
0x1800a9a53  call    memset_0
0x1800a9a58  xor     r11d, r11d
0x1800a9a5b  mov     esi, r11d
0x1800a9a5e  mov     [rsp+130h+var_E8], r11
0x1800a9a63  mov     eax, [r13+238h]
0x1800a9a6a  cmp     eax, 18h
0x1800a9a6d  jnb     short loc_1800A9A82
0x1800a9a6f  lea     rcx, [rbp+57h+var_D0]
0x1800a9a73  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800a9a78  mov     eax, 57h ; 'W'
0x1800a9a7d  jmp     loc_1800AA16C
0x1800a9a82  mov     ecx, 220h
0x1800a9a87  cmp     [r13+248h], ecx
0x1800a9a8e  jnb     short loc_1800A9A9B
0x1800a9a90  mov     rax, [r13+250h]
0x1800a9a97  mov     [rax], ecx
0x1800a9a99  jmp     short loc_1800A9A6F
0x1800a9a9b  mov     r14d, r11d
0x1800a9a9e  mov     rdi, [r13+230h]
0x1800a9aa5  mov     r15, [r13+240h]
0x1800a9aac  lea     rcx, [rbp+57h+hMem]
0x1800a9ab0  mov     [rbp+57h+var_B0], rcx
0x1800a9ab4  lea     rcx, [rbp+57h+hMem]
0x1800a9ab8  mov     [rbp+57h+hMem], rcx
0x1800a9abc  mov     ecx, [rdi+0Ch]
0x1800a9abf  cmp     eax, ecx
0x1800a9ac1  jb      loc_1800AA056
0x1800a9ac7  cmp     dword ptr [rdi+10h], 7D1h
0x1800a9ace  jnz     loc_1800AA056
0x1800a9ad4  cmp     ecx, [rdi+8]
0x1800a9ad7  jb      loc_1800AA056
0x1800a9add  cmp     dword ptr [rdi+8], 52h ; 'R'
0x1800a9ae1  jb      loc_1800AA056
0x1800a9ae7  mov     eax, [rdi+20h]
0x1800a9aea  cmp     eax, [rdi+8]
0x1800a9aed  jb      loc_1800AA056
0x1800a9af3  cmp     eax, ecx
0x1800a9af5  ja      loc_1800AA056
0x1800a9afb  test    al, 3
0x1800a9afd  jnz     loc_1800AA056
0x1800a9b03  sub     ecx, eax
0x1800a9b05  cmp     ecx, 4
0x1800a9b08  jb      loc_1800AA056
0x1800a9b0e  lea     rdx, [rdi+rax]
0x1800a9b12  mov     eax, [rdx]
0x1800a9b14  shl     rax, 4
0x1800a9b18  mov     r8d, 0FFFFFFFFh
0x1800a9b1e  cmp     rax, r8
0x1800a9b21  ja      loc_1800AA056
0x1800a9b27  add     eax, 4
0x1800a9b2a  cmp     eax, ecx
0x1800a9b2c  ja      loc_1800AA056
0x1800a9b32  mov     ebx, r11d
0x1800a9b35  lea     rax, [rbp+57h+var_C0]
0x1800a9b39  mov     [rsp+130h+var_100], rax
0x1800a9b3e  lea     rax, [rbp+57h+var_C8]
0x1800a9b42  mov     [rsp+130h+var_108], rax
0x1800a9b47  lea     rax, [rbp+57h+hMem]
0x1800a9b4b  mov     [rsp+130h+var_110], rax
0x1800a9b50  xor     r9d, r9d
0x1800a9b53  xor     r8d, r8d
0x1800a9b56  lea     rcx, [rbp+57h+var_A0]
0x1800a9b5a  call    ?SuexGetDrives@@YA?AV_status_t@@PEAU_SP_IDS@@HKPEAU_LIST_ENTRY@@PEAKPEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; SuexGetDrives(_SP_IDS *,int,ulong,_LIST_ENTRY *,ulong *,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x1800a9b5f  movsd   xmm0, qword ptr [rax]
0x1800a9b63  movsd   [rsp+130h+var_E0], xmm0
0x1800a9b69  mov     eax, [rax+8]
0x1800a9b6c  mov     [rsp+130h+var_D8], eax
0x1800a9b70  movd    eax, xmm0
0x1800a9b74  test    eax, eax
0x1800a9b76  jns     short loc_1800A9BDB
0x1800a9b78  lea     rcx, [rsp+130h+var_E0]
0x1800a9b7d  call    ?ToSMRC@_status_t@@QEAA?AW4SM_RETURN_CODE@@XZ; _status_t::ToSMRC(void)
0x1800a9b82  mov     r14d, eax
0x1800a9b85  mov     ecx, cs:dword_18039EB68
0x1800a9b8b  cmp     ecx, 2
0x1800a9b8e  jbe     loc_1800AA05B
0x1800a9b94  mov     [rsp+130h+var_F0], eax
0x1800a9b98  mov     [rsp+130h+var_EC], 204h
0x1800a9ba0  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a9ba7  mov     [rsp+130h+var_E8], rdi
0x1800a9bac  lea     rax, [rsp+130h+var_F0]
0x1800a9bb1  mov     [rsp+130h+var_100], rax
0x1800a9bb6  lea     rax, [rsp+130h+var_EC]
0x1800a9bbb  mov     [rsp+130h+var_108], rax
0x1800a9bc0  lea     rax, [rsp+130h+var_E8]
0x1800a9bc5  lea     rdx, byte_180321E7F
0x1800a9bcc  mov     [rsp+130h+var_110], rax
0x1800a9bd1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a9bd6  jmp     loc_1800AA062
0x1800a9bdb  lea     r8, [rsp+130h+var_E8]
0x1800a9be0  lea     rdx, [rbp+57h+hMem]
0x1800a9be4  mov     ecx, [rdi+18h]
0x1800a9be7  call    ?SuGetPoolTemplate@@YAHW4_SC_VERSION@@PEAU_LIST_ENTRY@@PEAPEAU_SP_POOL_INFO@@@Z; SuGetPoolTemplate(_SC_VERSION,_LIST_ENTRY *,_SP_POOL_INFO * *)
0x1800a9bec  xor     r11d, r11d
0x1800a9bef  test    eax, eax
0x1800a9bf1  jnz     short loc_1800A9C5D
0x1800a9bf3  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800a9bf8  mov     r14d, eax
0x1800a9bfb  mov     eax, cs:dword_18039EB68
0x1800a9c01  cmp     eax, 2
0x1800a9c04  jbe     short loc_1800A9C53
0x1800a9c06  mov     [rsp+130h+var_EC], r14d
0x1800a9c0b  mov     [rsp+130h+var_F0], 211h
0x1800a9c13  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a9c1a  mov     [rsp+130h+var_E0], rdi
0x1800a9c1f  lea     rax, [rsp+130h+var_EC]
0x1800a9c24  mov     [rsp+130h+var_100], rax
0x1800a9c29  lea     rax, [rsp+130h+var_F0]
0x1800a9c2e  mov     [rsp+130h+var_108], rax
0x1800a9c33  lea     rax, [rsp+130h+var_E0]
0x1800a9c38  mov     [rsp+130h+var_110], rax
0x1800a9c3d  lea     rdx, byte_180329173
0x1800a9c44  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800a9c49  mov     rsi, [rsp+130h+var_E8]
0x1800a9c4e  jmp     loc_1800AA062
0x1800a9c53  mov     rsi, [rsp+130h+var_E8]
0x1800a9c58  jmp     loc_1800AA05B
0x1800a9c5d  mov     eax, [rdi+24h]
0x1800a9c60  mov     rsi, [rsp+130h+var_E8]
0x1800a9c65  test    eax, eax
0x1800a9c67  jz      loc_1800A9D10
0x1800a9c6d  cmp     eax, [rdi+8]
0x1800a9c70  jb      loc_1800AA056
0x1800a9c76  mov     ecx, [rdi+0Ch]
0x1800a9c79  cmp     eax, ecx
0x1800a9c7b  ja      loc_1800AA056
0x1800a9c81  test    al, 1
0x1800a9c83  jnz     loc_1800AA056
0x1800a9c89  sub     ecx, eax
0x1800a9c8b  mov     edx, ecx; unsigned __int64
0x1800a9c8d  lea     rcx, [rdi+rax]; unsigned __int16 *
0x1800a9c91  lea     r8, [rsp+130h+var_E8]; unsigned __int64 *
0x1800a9c96  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a9c9b  test    eax, eax
0x1800a9c9d  js      loc_1800AA056
0x1800a9ca3  mov     r8d, [rdi+24h]
0x1800a9ca7  add     r8, rdi; unsigned __int16 *
0x1800a9caa  lea     rcx, [rsi+18h]; unsigned __int16 *
0x1800a9cae  mov     edx, 100h; unsigned __int64
0x1800a9cb3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a9cb8  test    eax, eax
0x1800a9cba  jns     short loc_1800A9D10
0x1800a9cbc  mov     ecx, 5
0x1800a9cc1  mov     r14d, ecx
0x1800a9cc4  mov     eax, cs:dword_18039EB68
0x1800a9cca  cmp     eax, 2
0x1800a9ccd  jbe     loc_1800AA05B
0x1800a9cd3  mov     [rsp+130h+var_EC], ecx
0x1800a9cd7  mov     [rsp+130h+var_F0], 231h
0x1800a9cdf  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a9ce6  mov     [rsp+130h+var_E0], rdi
0x1800a9ceb  lea     rax, [rsp+130h+var_EC]
0x1800a9cf0  mov     [rsp+130h+var_100], rax
0x1800a9cf5  lea     rax, [rsp+130h+var_F0]
0x1800a9cfa  mov     [rsp+130h+var_108], rax
0x1800a9cff  lea     rax, [rsp+130h+var_E0]
0x1800a9d04  lea     rdx, word_18031FDDA
0x1800a9d0b  jmp     loc_1800A9BCC
0x1800a9d10  mov     eax, [rdi+28h]
0x1800a9d13  test    eax, eax
0x1800a9d15  jz      loc_1800A9DC1
0x1800a9d1b  cmp     eax, [rdi+8]
0x1800a9d1e  jb      loc_1800AA056
0x1800a9d24  mov     ecx, [rdi+0Ch]
0x1800a9d27  cmp     eax, ecx
0x1800a9d29  ja      loc_1800AA056
0x1800a9d2f  test    al, 1
0x1800a9d31  jnz     loc_1800AA056
0x1800a9d37  sub     ecx, eax
0x1800a9d39  mov     edx, ecx; unsigned __int64
0x1800a9d3b  lea     rcx, [rdi+rax]; unsigned __int16 *
0x1800a9d3f  lea     r8, [rsp+130h+var_E8]; unsigned __int64 *
0x1800a9d44  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a9d49  test    eax, eax
0x1800a9d4b  js      loc_1800AA056
0x1800a9d51  mov     r8d, [rdi+28h]
0x1800a9d55  add     r8, rdi; unsigned __int16 *
0x1800a9d58  lea     rcx, [rsi+218h]; unsigned __int16 *
0x1800a9d5f  mov     edx, 400h; unsigned __int64
0x1800a9d64  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800a9d69  test    eax, eax
0x1800a9d6b  jns     short loc_1800A9DC1
0x1800a9d6d  mov     ecx, 5
0x1800a9d72  mov     r14d, ecx
0x1800a9d75  mov     eax, cs:dword_18039EB68
0x1800a9d7b  cmp     eax, 2
0x1800a9d7e  jbe     loc_1800AA05B
0x1800a9d84  mov     [rsp+130h+var_EC], ecx
0x1800a9d88  mov     [rsp+130h+var_F0], 252h
0x1800a9d90  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a9d97  mov     [rsp+130h+var_E0], rdi
0x1800a9d9c  lea     rax, [rsp+130h+var_EC]
0x1800a9da1  mov     [rsp+130h+var_100], rax
0x1800a9da6  lea     rax, [rsp+130h+var_F0]
0x1800a9dab  mov     [rsp+130h+var_108], rax
0x1800a9db0  lea     rax, [rsp+130h+var_E0]
0x1800a9db5  lea     rdx, byte_1803288BD
0x1800a9dbc  jmp     loc_1800A9BCC
0x1800a9dc1  cmp     [rdi+30h], r11b
0x1800a9dc5  jz      short loc_1800A9DD6
0x1800a9dc7  movzx   ecx, word ptr [rdi+32h]
0x1800a9dcb  call    ?SmpToSpProvisioningType@@YA?AW4_SP_PROVISIONING_TYPE@@G@Z; SmpToSpProvisioningType(ushort)
0x1800a9dd0  mov     [rsi+0A80h], eax
0x1800a9dd6  cmp     dword ptr [rdi+8], 56h ; 'V'
0x1800a9dda  jb      short loc_1800A9DF1
0x1800a9ddc  cmp     [rdi+52h], r11b
0x1800a9de0  jz      short loc_1800A9DF1
0x1800a9de2  movzx   ecx, word ptr [rdi+54h]
0x1800a9de6  call    ?SmpToSpMediaType@@YA?AW4_SC_MEDIA_TYPE@@W4MEDIA_TYPE@SM_CONSTANTS@@@Z; SmpToSpMediaType(SM_CONSTANTS::MEDIA_TYPE)
0x1800a9deb  mov     [rsi+0A90h], eax
0x1800a9df1  cmp     [rdi+3Ch], r11b
0x1800a9df5  jz      short loc_1800A9E06
0x1800a9df7  movzx   ecx, word ptr [rdi+3Eh]
0x1800a9dfb  call    ?SmpToSpFaultDomainType@@YA?AW4_SC_FD_TYPE@@G@Z; SmpToSpFaultDomainType(ushort)
0x1800a9e00  mov     [rsi+0A9Ch], eax
0x1800a9e06  mov     eax, [rdi+2Ch]
0x1800a9e09  test    eax, eax
0x1800a9e0b  jz      short loc_1800A9E57
0x1800a9e0d  cmp     eax, [rdi+8]
0x1800a9e10  jb      loc_1800AA056
0x1800a9e16  mov     ecx, [rdi+0Ch]
0x1800a9e19  cmp     eax, ecx
0x1800a9e1b  ja      loc_1800AA056
0x1800a9e21  test    al, 1
0x1800a9e23  jnz     loc_1800AA056
0x1800a9e29  sub     ecx, eax
0x1800a9e2b  mov     edx, ecx; unsigned __int64
0x1800a9e2d  lea     rcx, [rdi+rax]; unsigned __int16 *
0x1800a9e31  lea     r8, [rsp+130h+var_E8]; unsigned __int64 *
0x1800a9e36  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800a9e3b  test    eax, eax
0x1800a9e3d  js      loc_1800AA056
0x1800a9e43  mov     ecx, [rdi+2Ch]
0x1800a9e46  add     rcx, rdi
0x1800a9e49  call    ?SmpToSpResiliencyType@@YA?AW4_SP_RESILIENCY_TYPE@@PEBG@Z; SmpToSpResiliencyType(ushort const *)
0x1800a9e4e  mov     [rsi+0AA0h], eax
0x1800a9e54  xor     r11d, r11d
0x1800a9e57  cmp     [rdi+34h], r11b
0x1800a9e5b  jz      short loc_1800A9E66
0x1800a9e5d  mov     eax, [rdi+38h]
0x1800a9e60  mov     [rsi+0A64h], eax
0x1800a9e66  cmp     dword ptr [rdi+8], 68h ; 'h'
0x1800a9e6a  jb      short loc_1800A9EDA
0x1800a9e6c  cmp     [rdi+58h], r11b
0x1800a9e70  jz      short loc_1800A9EDA
0x1800a9e72  mov     eax, 0FFFFFFFFh
0x1800a9e77  cmp     [rdi+60h], rax
0x1800a9e7b  jbe     short loc_1800A9ED1
0x1800a9e7d  mov     ecx, 5
0x1800a9e82  mov     r14d, ecx
0x1800a9e85  mov     eax, cs:dword_18039EB68
0x1800a9e8b  cmp     eax, 2
0x1800a9e8e  jbe     loc_1800AA05B
0x1800a9e94  mov     [rsp+130h+var_EC], ecx
0x1800a9e98  mov     [rsp+130h+var_F0], 28Fh
0x1800a9ea0  lea     rdi, aSpctlSubsystem_0; "Spctl_Subsystem_CreatePool_L1"
0x1800a9ea7  mov     [rsp+130h+var_E0], rdi
0x1800a9eac  lea     rax, [rsp+130h+var_EC]
0x1800a9eb1  mov     [rsp+130h+var_100], rax
0x1800a9eb6  lea     rax, [rsp+130h+var_F0]
0x1800a9ebb  mov     [rsp+130h+var_108], rax
0x1800a9ec0  lea     rax, [rsp+130h+var_E0]
0x1800a9ec5  lea     rdx, byte_180326F53
  ... truncated ...
```
