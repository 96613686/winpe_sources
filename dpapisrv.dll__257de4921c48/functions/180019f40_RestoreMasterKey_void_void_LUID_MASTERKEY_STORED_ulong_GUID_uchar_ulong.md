# RestoreMasterKey(void *,void *,_LUID *,MASTERKEY_STORED *,ulong,_GUID *,uchar * *,ulong *)

- ea: `0x180019f40`
- end: `0x18001aaa5`
- name: `?RestoreMasterKey@@YAKPEAX0PEAU_LUID@@PEAUMASTERKEY_STORED@@KPEAU_GUID@@PEAPEAEPEAK@Z`
- size: `2917`
- prototype: `__int64 __fastcall(_DWORD *, void *, struct _LUID *, struct MASTERKEY_STORED *, unsigned int, struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e9c0`

## callees

- `0x180001184`
- `0x18000128c`
- `0x1800063c0`
- `0x180006510`
- `0x1800065b0`
- `0x180007f10`
- `0x18000a5d0`
- `0x18000abf0`
- `0x18000ad44`
- `0x18000b680`
- `0x18000c4a0`
- `0x180011014`
- `0x180011604`
- `0x180012544`
- `0x180013a18`
- `0x180013ac0`
- `0x18001467c`
- `0x18001866c`
- `0x180019f40`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x1800261e8`
- `0x18002677c`
- `0x18003b41c`
- `0x18003c62c`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a28a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a28a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa69`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a11e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a2a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a93c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a11e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a2a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a93c`
- `ntdll!RtlNtStatusToDosError` at `0x18001a2da`
- `ntdll!RtlNtStatusToDosError` at `0x18001a303`
- `ntdll!RtlNtStatusToDosError` at `0x18001a2da`
- `ntdll!RtlNtStatusToDosError` at `0x18001a303`

## string_xrefs

- `0x18001a163`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18001a180`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18001a315`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall RestoreMasterKey(
        _DWORD *a1,
        void *a2,
        struct _LUID *a3,
        struct MASTERKEY_STORED *a4,
        unsigned int a5,
        struct _GUID *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  void *v9; // rbx
  _BYTE *v11; // r13
  _DWORD *v12; // r9
  __int64 v13; // rax
  unsigned int v14; // esi
  SIZE_T v15; // rbx
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rdi
  unsigned int v18; // ebx
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // r12d
  NTSTATUS v23; // esi
  __int64 v24; // r9
  unsigned __int8 *v25; // rax
  ULONG v26; // eax
  __m128i *v27; // rax
  __m128i v28; // xmm0
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r9
  BOOL v32; // eax
  __int64 v33; // r9
  __int64 v34; // r9
  unsigned int v35; // eax
  __int64 v36; // r9
  unsigned int v37; // eax
  ULONG v38; // r14d
  __int64 v39; // r9
  __int64 v40; // rdi
  ULONG v41; // edx
  unsigned __int8 *v42; // rax
  __int64 v43; // r9
  unsigned __int8 *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  unsigned __int8 *v47; // rax
  UCHAR *v48; // rax
  __int64 v49; // rdx
  _BYTE *v50; // rax
  _BYTE *v51; // rcx
  __int64 v52; // rax
  void *(*v54)(unsigned __int64); // [rsp+20h] [rbp-E0h]
  ULONG cbInput; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v56; // [rsp+64h] [rbp-9Ch] BYREF
  bool v57; // [rsp+68h] [rbp-98h] BYREF
  bool v58; // [rsp+69h] [rbp-97h] BYREF
  unsigned int uBytes[3]; // [rsp+6Ch] [rbp-94h] BYREF
  BOOL v60; // [rsp+78h] [rbp-88h]
  HLOCAL v61; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v62; // [rsp+88h] [rbp-78h]
  unsigned int v63; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 *v64; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v65; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v66; // [rsp+9Ch] [rbp-64h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 **v68; // [rsp+A8h] [rbp-58h]
  unsigned int *v69; // [rsp+B0h] [rbp-50h]
  unsigned int v70; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v71; // [rsp+C0h] [rbp-40h] BYREF
  int v72; // [rsp+D0h] [rbp-30h] BYREF
  char v73; // [rsp+D4h] [rbp-2Ch]
  _BYTE v74[16]; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v75[10]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v76[32]; // [rsp+110h] [rbp+10h] BYREF
  bool *v77; // [rsp+130h] [rbp+30h]
  __int64 v78; // [rsp+138h] [rbp+38h]
  bool *v79; // [rsp+140h] [rbp+40h]
  __int64 v80; // [rsp+148h] [rbp+48h]
  unsigned __int8 v81[32]; // [rsp+150h] [rbp+50h] BYREF
  UCHAR v82[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int8 v83[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  _WORD Src[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  *(_QWORD *)&uBytes[1] = a3;
  v9 = a2;
  *(_QWORD *)&v71.Data1 = a2;
  v68 = a7;
  v69 = a8;
  v66 = 64;
  v65 = 0;
  v11 = 0;
  hMem = 0;
  cbInput = 0;
  v61 = 0;
  v56 = 0;
  v60 = 0;
  v64 = 0;
  uBytes[0] = 0;
  if ( a1 )
  {
    v63 = a1[13];
    v62 = a1[14];
  }
  else
  {
    v63 = 26128;
    v62 = 32782;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_S(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      108,
      WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      (char *)a4 + 16);
  v72 = 0;
  v73 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v72);
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    v57 = *((_QWORD *)a4 + 17) != 0;
    v58 = *((_QWORD *)a4 + 19) != 0;
    if ( v73 && (v75[0] || v75[1] || v75[2] || v75[3]) )
      v12 = v75;
    else
      LODWORD(v12) = 0;
    v79 = &v57;
    v80 = 1;
    v77 = &v58;
    v78 = 1;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_18004C260,
      (unsigned int)&byte_18004503F,
      (unsigned int)v74,
      (_DWORD)v12,
      4,
      (__int64)v76);
  }
  if ( !v9 )
  {
    v21 = CPSGetUserName(a1, &v64, uBytes);
    v18 = v21;
    if ( !v21 )
    {
      v17 = v64;
      v14 = uBytes[0];
LABEL_29:
      v64 = 0;
      uBytes[0] = 0;
      v22 = (*((_DWORD *)a4 + 24) >> 2) & 1;
      v23 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, _QWORD, _DWORD, unsigned __int16 **, unsigned int *))g_pDPAPILsasrvIfTable
             + 17))(
              *(_QWORD *)&uBytes[1],
              v22,
              v17,
              2 * v14,
              *((_QWORD *)a4 + 13),
              *((_DWORD *)a4 + 25),
              &v64,
              uBytes);
      if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
      {
        v70 = v22;
        uBytes[1] = v23;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)&dword_18004C260,
          (int)byte_180044E4D,
          (int)v74,
          v24,
          (__int64)&uBytes[1],
          (__int64)&v70);
      }
      LocalFree(v17);
      if ( v23 >= 0 )
      {
        v25 = (unsigned __int8 *)LocalAlloc(0, uBytes[0]);
        *v68 = v25;
        if ( v25 )
        {
          memcpy_0(v25, v64, uBytes[0]);
          *v69 = uBytes[0];
        }
        else
        {
          v18 = RtlNtStatusToDosError(-1073741801);
        }
        (*((void (__fastcall **)(unsigned __int16 *))g_pDPAPILsasrvIfTable + 3))(v64);
        goto LABEL_112;
      }
      v26 = RtlNtStatusToDosError(v23);
      DebugTraceError(v26, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 6470);
      goto LABEL_38;
    }
    v19 = 6408;
    v20 = v21;
LABEL_24:
    DebugTraceError(v20, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v19);
LABEL_38:
    v9 = *(void **)&v71.Data1;
    goto LABEL_39;
  }
  if ( (unsigned int)GetTextualSid(v9, Src, 261) )
  {
    v13 = -1;
    do
      ++v13;
    while ( Src[v13] );
    v14 = v13 + 1;
    v15 = 2LL * (unsigned int)(v13 + 1);
    v16 = (unsigned __int16 *)LocalAlloc(0, v15);
    v17 = v16;
    if ( v16 )
    {
      memcpy_0(v16, Src, v15);
      v17[v14 - 1] = 0;
      v18 = 0;
      goto LABEL_29;
    }
    v19 = 6386;
    v20 = 8;
    goto LABEL_24;
  }
  DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 6392);
LABEL_39:
  v27 = (__m128i *)*((_QWORD *)a4 + 17);
  if ( !v27 )
    goto LABEL_62;
  v28 = 0;
  memset(&v75[4], 0, 20);
  if ( *((_DWORD *)a4 + 32) >= 0x14u )
  {
    v28 = *v27;
    *(__m128i *)&v75[4] = *v27;
    v75[8] = v27[1].m128i_i32[0];
  }
  if ( _mm_cvtsi128_si32(v28) != 3
    || *(_QWORD *)&a6->Data1 == *(_QWORD *)&v75[5] && *(_QWORD *)a6->Data4 == *(_QWORD *)&v75[7] )
  {
    goto LABEL_62;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 111, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  if ( !(unsigned int)GetMasterKeyUserEncryptionKey(
                        a1,
                        (struct _GUID *)&v75[5],
                        v9,
                        (*((_DWORD *)a4 + 24) >> 2) & 1,
                        v81,
                        &v65) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 116, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
    {
      uBytes[1] = -1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_18004C260,
        (int)byte_180044CCB,
        (int)v74,
        v31,
        (__int64)&uBytes[1]);
    }
    goto LABEL_62;
  }
  v71 = *(struct _GUID *)&v75[5];
  v18 = DecryptMasterKeyFromStorage(a4, 0, v63, v62, v81, 0x14u, 0, v68, v69, &v71, a1);
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    uBytes[1] = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_18004C260,
      (int)word_180044C4A,
      (int)v74,
      v29,
      (__int64)&uBytes[1]);
  }
  if ( !v18 )
    goto LABEL_112;
  v30 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 115, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
LABEL_62:
    v30 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)a4 + 19) )
  {
    if ( (_UNKNOWN *)v30 != &WPP_GLOBAL_Control && (*(_BYTE *)(v30 + 28) & 8) != 0 )
      WPP_SF_(*(_QWORD *)(v30 + 16), 117, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    UpdateGlobals(v30);
    if ( dword_18004CCB0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 118, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
      v18 = 1058;
    }
    else
    {
      v18 = CPSImpersonateClient(a1);
      if ( !v18 )
      {
        v18 = BackupRestoreData(
                a1,
                a4,
                *((unsigned __int8 **)a4 + 19),
                *((_DWORD *)a4 + 36),
                (unsigned __int8 **)&v61,
                &v56,
                0);
        if ( v18 )
        {
          v35 = LocalBackupRestoreData(
                  a1,
                  a4,
                  *((unsigned __int8 **)a4 + 19),
                  *((_DWORD *)a4 + 36),
                  (unsigned __int8 **)&v61,
                  &v56,
                  (struct _GUID *)&stru_1800430D8);
          v18 = v35;
          if ( v35 )
            DebugTraceError(v35, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 6621);
        }
        CPSRevertToSelf(a1);
        v32 = v18 == 0;
LABEL_73:
        v60 = v32;
        if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
        {
          uBytes[1] = v18;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (int)&dword_18004C260,
            (int)&dword_180044D7C,
            (int)v74,
            v33,
            (__int64)&uBytes[1]);
        }
        if ( !v18 )
          goto LABEL_77;
LABEL_94:
        v34 = 6665;
        goto LABEL_95;
      }
    }
    v32 = v60;
    goto LABEL_73;
  }
  if ( (_UNKNOWN *)v30 != &WPP_GLOBAL_Control && (*(_BYTE *)(v30 + 28) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(v30 + 16), 119, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  v18 = QueryMasterKeyFromStorage(a4, 2u, (unsigned __int8 **)&v61, &v56);
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    uBytes[1] = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_18004C260,
      (int)&byte_180044C77,
      (int)v74,
      v36,
      (__int64)&uBytes[1]);
  }
  if ( v18 )
  {
    DebugTraceError(v18, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 6659);
    goto LABEL_94;
  }
LABEL_77:
  if ( v56 < 4 )
  {
LABEL_112:
    v38 = cbInput;
    goto LABEL_113;
  }
  if ( !*(_DWORD *)v61 )
  {
    v42 = (unsigned __int8 *)LocalAlloc(0, v56 - 4LL);
    *v68 = v42;
    if ( v42 )
    {
      memcpy_0(v42, (char *)v61 + 4, v56 - 4LL);
      *v69 = v56 - 4;
    }
    else
    {
      v18 = 8;
    }
    goto LABEL_112;
  }
  if ( !(unsigned int)GetLocalKeyUserEncryptionKey(a1, a4, v83, &v66, &v65) )
  {
    v18 = -2146893821;
    v34 = 6692;
LABEL_95:
    DebugTraceError(v18, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v34);
    goto LABEL_112;
  }
  v71 = GUID_NULL;
  v37 = DecryptMasterKeyFromStorage(a4, 1u, v63, v62, v83, v66, 0, (unsigned __int8 **)&hMem, &cbInput, &v71, a1);
  v18 = v37;
  if ( v37 )
  {
    DebugTraceError(v37, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 6715);
    v11 = hMem;
    goto LABEL_112;
  }
  if ( v56 >= 0x20 && *(_DWORD *)v61 == 2 && *((_DWORD *)v61 + 6) == 32782 )
  {
    v38 = cbInput;
    v11 = hMem;
    if ( !(unsigned int)FMyPrimitiveSHA512((PUCHAR)hMem, cbInput, v82) )
    {
      v39 = 6739;
LABEL_103:
      v18 = 13;
      DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v39);
LABEL_113:
      v40 = 64;
      goto LABEL_114;
    }
    v40 = 64;
    v41 = 64;
  }
  else
  {
    v38 = cbInput;
    v11 = hMem;
    if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)hMem, cbInput, v82) )
    {
      v39 = 6749;
      goto LABEL_103;
    }
    v41 = 20;
    v40 = 64;
  }
  v18 = DecryptMasterKeyToMemoryEx(v82, v41, (unsigned __int8 *)v61, v56, v54, v68, v69, 0, 0, 0);
LABEL_114:
  v72 = 2;
  if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
  {
    uBytes[1] = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_18004C260,
      (int)&byte_180044C9F,
      (int)v74,
      v43,
      (__int64)&uBytes[1]);
  }
  v44 = v81;
  v45 = 20;
  do
  {
    *v44++ = 0;
    --v45;
  }
  while ( v45 );
  v46 = 64;
  v47 = v83;
  do
  {
    *v47++ = 0;
    --v46;
  }
  while ( v46 );
  v48 = v82;
  do
  {
    *v48++ = 0;
    --v40;
  }
  while ( v40 );
  if ( v11 )
  {
    v49 = v38;
    v50 = v11;
    if ( v38 )
    {
      do
      {
        *v50++ = 0;
        --v49;
      }
      while ( v49 );
    }
    LocalFree(v11);
  }
  if ( v60 )
  {
    v51 = v61;
    if ( v61 )
    {
      v52 = v56;
      if ( v56 )
      {
        do
        {
          *v51++ = 0;
          --v52;
        }
        while ( v52 );
        v51 = v61;
      }
      LocalFree(v51);
    }
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v72);
  return v18;
}

```

## disassembly

```asm
0x180019f40  push    rbp
0x180019f42  push    rbx
0x180019f43  push    rsi
0x180019f44  push    rdi
0x180019f45  push    r12
0x180019f47  push    r13
0x180019f49  push    r14
0x180019f4b  push    r15
0x180019f4d  lea     rbp, [rsp-318h]
0x180019f55  sub     rsp, 418h
0x180019f5c  mov     rax, cs:__security_cookie
0x180019f63  xor     rax, rsp
0x180019f66  mov     [rbp+350h+var_50], rax
0x180019f6d  mov     r14, r9
0x180019f70  mov     qword ptr [rsp+450h+uBytes+4], r8
0x180019f75  mov     rbx, rdx
0x180019f78  mov     qword ptr [rbp+350h+var_390.Data1], rdx
0x180019f7c  mov     r15, rcx
0x180019f7f  mov     rax, [rbp+350h+arg_30]
0x180019f86  mov     [rbp+350h+var_3A8], rax
0x180019f8a  mov     rax, [rbp+350h+arg_38]
0x180019f91  mov     [rbp+350h+var_3A0], rax
0x180019f95  mov     [rbp+350h+var_3B4], 40h ; '@'
0x180019f9c  xor     edi, edi
0x180019f9e  mov     [rbp+350h+var_3B8], edi
0x180019fa1  mov     r13d, edi
0x180019fa4  mov     [rbp+350h+hMem], rdi
0x180019fa8  mov     [rsp+450h+cbInput], edi
0x180019fac  mov     [rbp+350h+var_3D0], rdi
0x180019fb0  mov     [rsp+450h+var_3EC], edi
0x180019fb4  mov     [rsp+450h+var_3D8], edi
0x180019fb8  mov     [rbp+350h+var_3C0], rdi
0x180019fbc  mov     dword ptr [rsp+450h+uBytes], edi
0x180019fc0  test    rcx, rcx
0x180019fc3  jz      short loc_180019FD3
0x180019fc5  mov     eax, [rcx+34h]
0x180019fc8  mov     [rbp+350h+var_3C4], eax
0x180019fcb  mov     eax, [rcx+38h]
0x180019fce  mov     [rbp+350h+var_3C8], eax
0x180019fd1  jmp     short loc_180019FE1
0x180019fd3  mov     [rbp+350h+var_3C4], 6610h
0x180019fda  mov     [rbp+350h+var_3C8], 800Eh
0x180019fe1  lea     rax, WPP_GLOBAL_Control
0x180019fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fef  cmp     rcx, rax
0x180019ff2  jz      short loc_18001A013
0x180019ff4  test    byte ptr [rcx+1Ch], 8
0x180019ff8  jz      short loc_18001A013
0x180019ffa  add     r9, 10h
0x180019ffe  mov     edx, 6Ch ; 'l'
0x18001a003  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18001a00a  mov     rcx, [rcx+10h]
0x18001a00e  call    WPP_SF_S
0x18001a013  mov     [rbp+350h+var_380], edi
0x18001a016  mov     [rbp+350h+var_37C], dil
0x18001a01a  lea     rcx, [rbp+350h+var_380]
0x18001a01e  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hDpapiTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hDpapiTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18001a023  mov     eax, cs:dword_18004C260
0x18001a029  cmp     eax, 5
0x18001a02c  jbe     loc_18001A0D5
0x18001a032  mov     rdx, 400000000000h
0x18001a03c  lea     rcx, dword_18004C260
0x18001a043  call    _tlgKeywordOn
0x18001a048  test    al, al
0x18001a04a  jz      loc_18001A0D5
0x18001a050  cmp     [r14+88h], rdi
0x18001a057  setnz   [rsp+450h+var_3E8]
0x18001a05c  cmp     [r14+98h], rdi
0x18001a063  setnz   [rsp+450h+var_3E7]
0x18001a068  cmp     [rbp+350h+var_37C], dil
0x18001a06c  jz      short loc_18001A088
0x18001a06e  cmp     [rbp+350h+var_368], edi
0x18001a071  jnz     short loc_18001A082
0x18001a073  cmp     [rbp+350h+var_364], edi
0x18001a076  jnz     short loc_18001A082
0x18001a078  cmp     [rbp+350h+var_360], edi
0x18001a07b  jnz     short loc_18001A082
0x18001a07d  cmp     [rbp+350h+var_35C], edi
0x18001a080  jz      short loc_18001A088
0x18001a082  lea     r9, [rbp+350h+var_368]
0x18001a086  jmp     short loc_18001A08B
0x18001a088  mov     r9, rdi
0x18001a08b  lea     rax, [rsp+450h+var_3E8]
0x18001a090  mov     [rbp+350h+var_310], rax
0x18001a094  mov     [rbp+350h+var_308], 1
0x18001a09c  lea     rax, [rsp+450h+var_3E7]
0x18001a0a1  mov     [rbp+350h+var_320], rax
0x18001a0a5  mov     [rbp+350h+var_318], 1
0x18001a0ad  lea     rax, [rbp+350h+var_340]
0x18001a0b1  mov     [rsp+450h+var_428], rax
0x18001a0b6  mov     dword ptr [rsp+450h+var_430], 4
0x18001a0be  lea     r8, [rbp+350h+var_378]
0x18001a0c2  lea     rdx, byte_18004503F
0x18001a0c9  lea     rcx, dword_18004C260
0x18001a0d0  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18001a0d5  mov     r12d, 14h
0x18001a0db  test    rbx, rbx
0x18001a0de  jz      loc_18001A1A3
0x18001a0e4  mov     r8d, 105h
0x18001a0ea  lea     rdx, [rbp+350h+Src]
0x18001a0f1  mov     rcx, rbx
0x18001a0f4  call    GetTextualSid
0x18001a0f9  test    eax, eax
0x18001a0fb  jz      short loc_18001A17A
0x18001a0fd  lea     rcx, [rbp+350h+Src]
0x18001a104  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a108  inc     rax
0x18001a10b  cmp     [rcx+rax*2], di
0x18001a10f  jnz     short loc_18001A108
0x18001a111  lea     esi, [rax+1]
0x18001a114  mov     ebx, esi
0x18001a116  add     rbx, rbx
0x18001a119  mov     rdx, rbx; uBytes
0x18001a11c  xor     ecx, ecx; uFlags
0x18001a11e  call    cs:__imp_LocalAlloc
0x18001a125  nop     dword ptr [rax+rax+00h]
0x18001a12a  mov     rdi, rax
0x18001a12d  test    rax, rax
0x18001a130  jz      short loc_18001A151
0x18001a132  mov     r8, rbx; Size
0x18001a135  lea     rdx, [rbp+350h+Src]; Src
0x18001a13c  mov     rcx, rax; void *
0x18001a13f  call    memcpy_0
0x18001a144  lea     ecx, [rsi-1]
0x18001a147  xor     eax, eax
0x18001a149  mov     [rdi+rcx*2], ax
0x18001a14d  xor     ebx, ebx
0x18001a14f  jmp     short loc_18001A1CC
0x18001a151  mov     r9d, 18F2h
0x18001a157  mov     ecx, 8
0x18001a15c  lea     rsi, aDwlasterror; "dwLastError"
0x18001a163  lea     rdi, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001a16a  mov     rdx, rsi
0x18001a16d  mov     r8, rdi
0x18001a170  call    DebugTraceError
0x18001a175  jmp     loc_18001A336
0x18001a17a  mov     r9d, 18F8h
0x18001a180  lea     rdi, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001a187  mov     r8, rdi
0x18001a18a  lea     rsi, aDwlasterror; "dwLastError"
0x18001a191  mov     rdx, rsi
0x18001a194  mov     ecx, 57h ; 'W'
0x18001a199  call    DebugTraceError
0x18001a19e  jmp     loc_18001A33A
0x18001a1a3  lea     r8, [rsp+450h+uBytes]; unsigned int *
0x18001a1a8  lea     rdx, [rbp+350h+var_3C0]; unsigned __int16 **
0x18001a1ac  mov     rcx, r15; void *
0x18001a1af  call    ?CPSGetUserName@@YAKPEAXPEAPEAGPEAK@Z; CPSGetUserName(void *,ushort * *,ulong *)
0x18001a1b4  mov     ebx, eax
0x18001a1b6  test    eax, eax
0x18001a1b8  jz      short loc_18001A1C4
0x18001a1ba  mov     r9d, 1908h
0x18001a1c0  mov     ecx, eax
0x18001a1c2  jmp     short loc_18001A15C
0x18001a1c4  mov     rdi, [rbp+350h+var_3C0]
0x18001a1c8  mov     esi, dword ptr [rsp+450h+uBytes]
0x18001a1cc  mov     [rbp+350h+var_3C0], 0
0x18001a1d4  mov     dword ptr [rsp+450h+uBytes], 0
0x18001a1dc  mov     r12d, [r14+60h]
0x18001a1e0  shr     r12d, 2
0x18001a1e4  and     r12d, 1
0x18001a1e8  lea     r9d, [rsi+rsi]
0x18001a1ec  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x18001a1f3  lea     rcx, [rsp+450h+uBytes]
0x18001a1f8  mov     [rsp+450h+var_418], rcx
0x18001a1fd  lea     rcx, [rbp+350h+var_3C0]
0x18001a201  mov     [rsp+450h+var_420], rcx
0x18001a206  mov     edx, [r14+64h]
0x18001a20a  mov     dword ptr [rsp+450h+var_428], edx
0x18001a20e  mov     rdx, [r14+68h]
0x18001a212  mov     [rsp+450h+var_430], rdx
0x18001a217  mov     r8, rdi
0x18001a21a  mov     edx, r12d
0x18001a21d  mov     rcx, qword ptr [rsp+450h+uBytes+4]
0x18001a222  mov     rax, [rax+88h]
0x18001a229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a22e  mov     esi, eax
0x18001a230  mov     ecx, cs:dword_18004C260
0x18001a236  cmp     ecx, 5
0x18001a239  jbe     short loc_18001A287
0x18001a23b  mov     rdx, 400000000000h
0x18001a245  lea     rcx, dword_18004C260
0x18001a24c  call    _tlgKeywordOn
0x18001a251  test    al, al
0x18001a253  jz      short loc_18001A287
0x18001a255  mov     [rbp+350h+var_398], r12d
0x18001a259  mov     dword ptr [rsp+450h+uBytes+4], esi
0x18001a25d  lea     rax, [rbp+350h+var_398]
0x18001a261  mov     [rsp+450h+var_428], rax
0x18001a266  lea     rax, [rsp+450h+uBytes+4]
0x18001a26b  mov     [rsp+450h+var_430], rax
0x18001a270  lea     r8, [rbp+350h+var_378]
0x18001a274  lea     rdx, byte_180044E4D
0x18001a27b  lea     rcx, dword_18004C260
0x18001a282  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a287  mov     rcx, rdi; hMem
0x18001a28a  call    cs:__imp_LocalFree
0x18001a291  nop     dword ptr [rax+rax+00h]
0x18001a296  test    esi, esi
0x18001a298  js      short loc_18001A301
0x18001a29a  mov     edx, dword ptr [rsp+450h+uBytes]; uBytes
0x18001a29e  xor     ecx, ecx; uFlags
0x18001a2a0  call    cs:__imp_LocalAlloc
0x18001a2a7  nop     dword ptr [rax+rax+00h]
0x18001a2ac  mov     rcx, [rbp+350h+var_3A8]
0x18001a2b0  mov     [rcx], rax
0x18001a2b3  test    rax, rax
0x18001a2b6  jz      short loc_18001A2D5
0x18001a2b8  mov     r8d, dword ptr [rsp+450h+uBytes]; Size
0x18001a2bd  mov     rdx, [rbp+350h+var_3C0]; Src
0x18001a2c1  mov     rcx, rax; void *
0x18001a2c4  call    memcpy_0
0x18001a2c9  mov     eax, dword ptr [rsp+450h+uBytes]
0x18001a2cd  mov     rcx, [rbp+350h+var_3A0]
0x18001a2d1  mov     [rcx], eax
0x18001a2d3  jmp     short loc_18001A2E8
0x18001a2d5  mov     ecx, 0C0000017h; Status
0x18001a2da  call    cs:__imp_RtlNtStatusToDosError
0x18001a2e1  nop     dword ptr [rax+rax+00h]
0x18001a2e6  mov     ebx, eax
0x18001a2e8  mov     rax, cs:?g_pDPAPILsasrvIfTable@@3PEAU_LSA_IF_LSASRV_FUNCTION_TABLE@@EA; _LSA_IF_LSASRV_FUNCTION_TABLE * g_pDPAPILsasrvIfTable
0x18001a2ef  mov     rcx, [rbp+350h+var_3C0]
0x18001a2f3  mov     rax, [rax+18h]
0x18001a2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2fc  jmp     loc_18001A97F
0x18001a301  mov     ecx, esi; Status
0x18001a303  call    cs:__imp_RtlNtStatusToDosError
0x18001a30a  nop     dword ptr [rax+rax+00h]
0x18001a30f  mov     r9d, 1946h
0x18001a315  lea     rdi, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001a31c  mov     r8, rdi
0x18001a31f  lea     rsi, aDwlasterror; "dwLastError"
0x18001a326  mov     rdx, rsi
0x18001a329  mov     ecx, eax
0x18001a32b  call    DebugTraceError
0x18001a330  mov     r12d, 14h
0x18001a336  mov     rbx, qword ptr [rbp+350h+var_390.Data1]
0x18001a33a  mov     rax, [r14+88h]
0x18001a341  test    rax, rax
0x18001a344  jz      loc_18001A559
0x18001a34a  xorps   xmm0, xmm0
0x18001a34d  xor     ecx, ecx
0x18001a34f  movups  xmmword ptr [rbp+350h+var_358.Data1], xmm0
0x18001a353  mov     [rbp+350h+var_348], ecx
0x18001a356  cmp     [r14+80h], r12d
0x18001a35d  jb      short loc_18001A36C
0x18001a35f  movups  xmm0, xmmword ptr [rax]
0x18001a362  movups  xmmword ptr [rbp+350h+var_358.Data1], xmm0
0x18001a366  mov     eax, [rax+10h]
0x18001a369  mov     [rbp+350h+var_348], eax
0x18001a36c  movd    eax, xmm0
0x18001a370  cmp     eax, 3
0x18001a373  jnz     loc_18001A559
0x18001a379  mov     rcx, [rbp+350h+arg_28]
0x18001a380  mov     rax, [rcx]
0x18001a383  cmp     rax, qword ptr [rbp+350h+var_358.Data2]
0x18001a387  jnz     short loc_18001A397
0x18001a389  mov     rax, [rcx+8]
0x18001a38d  cmp     rax, qword ptr [rbp+350h+var_358.Data4+4]
0x18001a391  jz      loc_18001A559
0x18001a397  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a39e  lea     rax, WPP_GLOBAL_Control
0x18001a3a5  cmp     rcx, rax
0x18001a3a8  jz      short loc_18001A3C5
0x18001a3aa  test    byte ptr [rcx+1Ch], 8
0x18001a3ae  jz      short loc_18001A3C5
0x18001a3b0  mov     edx, 6Fh ; 'o'
0x18001a3b5  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18001a3bc  mov     rcx, [rcx+10h]
0x18001a3c0  call    WPP_SF_
0x18001a3c5  mov     r9d, [r14+60h]
0x18001a3c9  shr     r9d, 2
0x18001a3cd  and     r9d, 1; unsigned int
0x18001a3d1  lea     rax, [rbp+350h+var_3B8]
0x18001a3d5  mov     [rsp+450h+var_428], rax; unsigned int *
0x18001a3da  lea     rax, [rbp+350h+var_300]
0x18001a3de  mov     [rsp+450h+var_430], rax; unsigned __int8 *
0x18001a3e3  mov     r8, rbx; void *
0x18001a3e6  lea     rdx, [rbp+350h+var_358.Data2]; struct _GUID *
0x18001a3ea  mov     rcx, r15; void *
0x18001a3ed  call    ?GetMasterKeyUserEncryptionKey@@YAHPEAXPEAU_GUID@@0KQEAEPEAK@Z; GetMasterKeyUserEncryptionKey(void *,_GUID *,void *,ulong,uchar * const,ulong *)
0x18001a3f2  test    eax, eax
0x18001a3f4  jz      loc_18001A4DB
0x18001a3fa  movups  xmm0, xmmword ptr [rbp+350h+var_358.Data2]
0x18001a3fe  movdqu  xmmword ptr [rbp+350h+var_390.Data1], xmm0
0x18001a403  mov     [rsp+450h+var_400], r15; void *
0x18001a408  lea     rax, [rbp+350h+var_390]
0x18001a40c  mov     [rsp+450h+var_408], rax; struct _GUID
0x18001a411  mov     rax, [rbp+350h+var_3A0]
0x18001a415  mov     [rsp+450h+var_410], rax; unsigned int *
0x18001a41a  mov     rax, [rbp+350h+var_3A8]
0x18001a41e  mov     [rsp+450h+var_418], rax; unsigned __int8 **
0x18001a423  mov     [rsp+450h+var_420], 0; int *
0x18001a42c  mov     dword ptr [rsp+450h+var_428], r12d; unsigned int
0x18001a431  lea     rax, [rbp+350h+var_300]
0x18001a435  mov     [rsp+450h+var_430], rax; unsigned __int8 *
0x18001a43a  mov     r9d, [rbp+350h+var_3C8]; unsigned int
0x18001a43e  mov     r8d, [rbp+350h+var_3C4]; unsigned int
0x18001a442  xor     edx, edx; unsigned int
0x18001a444  mov     rcx, r14; struct MASTERKEY_STORED *
  ... truncated ...
```
