# PmEnumerateVolumes(CPmEnumerationFilter *,CRefMap<ushort const *,CPmVolume *> &)

- ea: `0x180120af0`
- end: `0x1801214af`
- name: `?PmEnumerateVolumes@@YAHPEAVCPmEnumerationFilter@@AEAV?$CRefMap@PEBGPEAVCPmVolume@@@@@Z`
- size: `2495`
- prototype: `__int64 __fastcall(CPmEnumerationFilter *this)`
- caller_count: `8`
- callee_count: `19`
- tags: `file_ops, reparse_path`

## callers

- `0x180112000`
- `0x180115518`
- `0x1801490f0`
- `0x18016cef8`
- `0x180175228`
- `0x180178140`
- `0x18018a470`
- `0x18018aa4c`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180001764`
- `0x180003cb8`
- `0x180006350`
- `0x1800063a0`
- `0x1800063f0`
- `0x180006dd4`
- `0x18000c644`
- `0x18000cc78`
- `0x180011a30`
- `0x18001da6c`
- `0x18004d408`
- `0x18011cfac`
- `0x180120af0`
- `0x180121c7c`
- `0x18012aecc`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012102e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801211e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012121d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012135b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120d75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012102e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801211e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180121203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012121d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012135b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180120f01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180120f92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801212ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180120f01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180120f92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801212ea`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180121015`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180121015`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180120eef`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180120eef`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18012143d`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18012143d`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1801211d4`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1801211d4`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180120f33`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180120f33`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PmEnumerateVolumes(CPmEnumerationFilter *this, __int64 a2, int a3, int a4)
{
  int v6; // ebx
  unsigned int v7; // r14d
  unsigned __int16 *v8; // rsi
  int v9; // ecx
  __int64 FirstVolumeW; // r13
  DWORD v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const MI_Char **v14; // rax
  char *v15; // rdx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  const unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // r8
  __int64 v23; // rbx
  __int64 v24; // rcx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  DWORD LastError; // ecx
  char *v30; // rdx
  __int64 v31; // rbx
  __int64 v32; // rcx
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  int v36; // eax
  DWORD v37; // ecx
  int v38; // r8d
  int v39; // r9d
  __int16 *v40; // rdx
  DWORD v41; // ecx
  DWORD v42; // ecx
  int v43; // r8d
  int v44; // r9d
  int *v45; // rdx
  const MI_Char **v47; // [rsp+30h] [rbp-D0h]
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  const MI_Char *v49; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  const char *v51; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v54[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szVolumeName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v48 = 1533;
    v52 = (unsigned __int16 *)"PmEnumerateVolumes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&word_18034C4DE,
      a3,
      a4,
      (__int64)&v52,
      (__int64)&v48);
  }
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v52 = 0;
  if ( !*((_DWORD *)this + 4) || (v9 = *((_DWORD *)this + 2), (unsigned int)(v9 - 1) <= 1) )
  {
    SmFreeString(&v52);
    v8 = (unsigned __int16 *)operator new[](0x208u);
    v52 = v8;
    FirstVolumeW = (__int64)FindFirstVolumeW(v8, 0x104u);
    if ( FirstVolumeW == -1 )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError == 122 )
        {
          if ( (unsigned int)dword_18039EB68 <= 3 )
            goto LABEL_95;
          LODWORD(v49) = 122;
          v30 = byte_18034C8AB;
        }
        else
        {
          if ( (unsigned int)dword_18039EB68 <= 2 )
            goto LABEL_95;
          LODWORD(v49) = LastError;
          v30 = byte_18034A161;
        }
      }
      else
      {
        if ( (unsigned int)dword_18039EB68 <= 4 )
          goto LABEL_95;
        LODWORD(v49) = 0;
        v30 = &byte_18034BDC7;
      }
      v48 = 1648;
      v51 = "PmEnumerateVolumes";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        LastError,
        (_DWORD)v30,
        v16,
        v17,
        (__int64)&v51,
        (__int64)&v48,
        (__int64)&v49);
      goto LABEL_95;
    }
    while ( 1 )
    {
      if ( GetLastError() == 18 )
        goto LABEL_39;
      v53 = 0;
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
      v53 = 0;
      if ( (unsigned int)PmGetVolume(v8) )
      {
        v31 = v53;
        if ( (unsigned int)dword_18039EB68 > 4 )
        {
          LOWORD(v48) = *(_WORD *)(*(_QWORD *)(v53 + 8) + 12LL);
          v32 = *(_QWORD *)(v53 + 8);
          v51 = (const char *)(v32 + 14);
          v54[0] = v32 + 1080;
          v50 = SubsystemTypeToName(*(unsigned int *)(v53 + 24));
          v49 = L"MSFT_Volume";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
            v33,
            (unsigned int)byte_18034B9D3,
            v34,
            v35,
            (__int64)&v49,
            (__int64)&v50,
            (__int64)v54,
            (__int64)&v51,
            (__int64)&v48);
        }
        if ( !CSpCluster::IsClusterNode() || *(_DWORD *)(v31 + 24) == *((_DWORD *)this + 3) )
        {
          v36 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 8LL))(
                  a2,
                  *(_QWORD *)(v31 + 16),
                  v31);
          v6 = v36;
          if ( v36 < 0 )
          {
            v41 = (unsigned __int16)v36;
            if ( (v36 & 0x1FFF0000) != 0x70000 )
              v41 = v36;
            SetLastError(v41);
            if ( (unsigned int)dword_18039EB68 > 2 )
            {
              LODWORD(v49) = 1674;
              v45 = &dword_18034B74C;
              goto LABEL_85;
            }
LABEL_86:
            CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
            goto LABEL_95;
          }
        }
        v6 = 0;
      }
      else
      {
        v37 = GetLastError();
        if ( v37 )
        {
          if ( v37 != 122 )
          {
            if ( (unsigned int)dword_18039EB68 <= 2 )
              goto LABEL_67;
            LODWORD(v50) = v37;
            v40 = (__int16 *)&byte_18034A56F;
            goto LABEL_78;
          }
          if ( (unsigned int)dword_18039EB68 > 3 )
          {
            LODWORD(v50) = 122;
            v40 = word_18034D2B2;
LABEL_78:
            v51 = "PmEnumerateVolumes";
            LODWORD(v49) = 1681;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v37,
              (_DWORD)v40,
              v38,
              v39,
              (__int64)&v51,
              (__int64)&v49,
              (__int64)&v50);
          }
        }
        else if ( (unsigned int)dword_18039EB68 > 4 )
        {
          LODWORD(v49) = 0;
          LODWORD(v50) = 1681;
          v51 = "PmEnumerateVolumes";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            0,
            (unsigned int)byte_18034AE2B,
            v38,
            v39,
            (__int64)&v51,
            (__int64)&v50,
            (__int64)&v49);
        }
      }
LABEL_67:
      SmFreeString(&v52);
      v8 = (unsigned __int16 *)operator new[](0x208u);
      v52 = v8;
      if ( !FindNextVolumeW((HANDLE)FirstVolumeW, v8, 0x104u) && GetLastError() != 18 )
      {
        v42 = GetLastError();
        if ( v42 )
        {
          if ( v42 == 122 )
          {
            if ( (unsigned int)dword_18039EB68 > 3 )
            {
              LODWORD(v50) = 122;
              LODWORD(v49) = 1697;
              v51 = "PmEnumerateVolumes";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                122,
                (unsigned int)byte_18034D66B,
                v43,
                v44,
                (__int64)&v51,
                (__int64)&v49,
                (__int64)&v50);
            }
          }
          else if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v50) = v42;
            LODWORD(v49) = 1697;
            v51 = "PmEnumerateVolumes";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v42,
              (unsigned int)byte_18034CB69,
              v43,
              v44,
              (__int64)&v51,
              (__int64)&v49,
              (__int64)&v50);
          }
        }
        else if ( (unsigned int)dword_18039EB68 > 4 )
        {
          LODWORD(v49) = 1697;
          v45 = (int *)byte_180348B15;
LABEL_85:
          v51 = "PmEnumerateVolumes";
          LODWORD(v50) = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v42,
            (_DWORD)v45,
            v43,
            v44,
            (__int64)&v51,
            (__int64)&v49,
            (__int64)&v50);
        }
        goto LABEL_86;
      }
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
    }
  }
  FirstVolumeW = -1;
  if ( v9 == 17 )
  {
    v50 = 0;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
    v50 = 0;
    v53 = 0;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
    v53 = 0;
    memset_0(szVolumePathName, 0, 0x208u);
    if ( !(unsigned int)PmGetPartition(*(unsigned __int16 **)this) )
    {
      v11 = GetLastError();
      if ( !v11 )
      {
        if ( (unsigned int)dword_18039EB68 > 4 )
        {
          v48 = 0;
          LODWORD(v49) = 1554;
          v47 = (const MI_Char **)&v48;
          v14 = &v49;
          v15 = byte_18034C919;
LABEL_15:
          v52 = (unsigned __int16 *)"PmEnumerateVolumes";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v11,
            (_DWORD)v15,
            v12,
            v13,
            (__int64)&v52,
            (__int64)v14,
            (__int64)v47);
        }
LABEL_18:
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
        goto LABEL_99;
      }
      if ( v11 == 122 )
      {
        if ( (unsigned int)dword_18039EB68 <= 3 )
          goto LABEL_18;
        LODWORD(v49) = 122;
        v15 = byte_180349003;
      }
      else
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_18;
        LODWORD(v49) = v11;
        v15 = byte_180348B4D;
      }
      v48 = 1554;
LABEL_14:
      v47 = &v49;
      v14 = (const MI_Char **)&v48;
      goto LABEL_15;
    }
    if ( (unsigned int)dword_18039EB68 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 1024) )
    {
      v52 = (unsigned __int16 *)(*(_QWORD *)(v50 + 8) + 164LL);
      if ( CPmEnumerationFilter::ToObjectId(this) )
        v21 = CPmEnumerationFilter::ToObjectId(this);
      else
        v21 = L"Unknown";
      v49 = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v18,
        (unsigned int)&dword_18034CDFC,
        v19,
        v20,
        (__int64)&v49,
        (__int64)&v52);
    }
    v22 = (const unsigned __int16 *)(*(_QWORD *)(v50 + 8) + 164LL);
    if ( *v22 )
    {
      StringCchCatW(szVolumePathName, 0x104u, v22);
      StringCchCatW(szVolumePathName, 0x104u, L"\\");
      if ( !(unsigned int)PmGetVolume(szVolumePathName) )
      {
        v11 = GetLastError();
        if ( v11 )
        {
          if ( v11 == 122 )
          {
            if ( (unsigned int)dword_18039EB68 <= 3 )
              goto LABEL_18;
            LODWORD(v49) = 122;
            v48 = 1577;
            v15 = (char *)&dword_18034983C;
          }
          else
          {
            if ( (unsigned int)dword_18039EB68 <= 2 )
              goto LABEL_18;
            LODWORD(v49) = v11;
            v48 = 1577;
            v15 = (char *)word_18034A5D2;
          }
        }
        else
        {
          if ( (unsigned int)dword_18039EB68 <= 4 )
            goto LABEL_18;
          LODWORD(v49) = 0;
          v48 = 1577;
          v15 = byte_18034D4A9;
        }
        goto LABEL_14;
      }
      v23 = v53;
      if ( (unsigned int)dword_18039EB68 > 4 )
      {
        LOWORD(v48) = *(_WORD *)(*(_QWORD *)(v53 + 8) + 12LL);
        v24 = *(_QWORD *)(v53 + 8);
        v52 = (unsigned __int16 *)(v24 + 14);
        v49 = (const MI_Char *)(v24 + 1080);
        v54[0] = SubsystemTypeToName(*(unsigned int *)(v53 + 24));
        v51 = (const char *)L"MSFT_Volume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
          v25,
          (unsigned int)&byte_18034C317,
          v26,
          v27,
          (__int64)&v51,
          (__int64)v54,
          (__int64)&v49,
          (__int64)&v52,
          (__int64)&v48);
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a2 + 8LL))(a2, *(_QWORD *)(v23 + 8) + 1080LL, v23);
    }
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
LABEL_39:
    v7 = 1;
LABEL_95:
    if ( v8 )
      operator delete(v8);
    if ( FirstVolumeW != -1 )
      FindVolumeClose((HANDLE)FirstVolumeW);
    goto LABEL_99;
  }
  if ( v9 == 18 )
  {
    v50 = 0;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
    v50 = 0;
    if ( !GetVolumePathNameW(*(LPCWSTR *)this, szVolumePathName, 0x104u)
      || !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u)
      || !(unsigned int)PmGetVolume(szVolumeName) )
    {
      SetLastError(0);
      v7 = 1;
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
      goto LABEL_99;
    }
    if ( *((_DWORD *)this + 3) == *(_DWORD *)(v50 + 24) )
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 8LL))(a2, *(_QWORD *)(v50 + 16), v50);
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
    goto LABEL_39;
  }
  SetLastError(0x57u);
  if ( (unsigned int)dword_18039EB68 > 2 )
  {
    LODWORD(v49) = 87;
    v48 = 1629;
    v51 = "PmEnumerateVolumes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v28,
      (unsigned int)&byte_18034BCFF,
      v16,
      v17,
      (__int64)&v51,
      (__int64)&v48,
      (__int64)&v49);
  }
LABEL_99:
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v50) = 1712;
    v51 = "PmEnumerateVolumes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_18039EB68,
      (unsigned int)byte_18034ACDB,
      v16,
      v17,
      (__int64)&v51,
      (__int64)&v50);
  }
  return v7;
}

```

## disassembly

```asm
0x180120af0  mov     [rsp-8+arg_10], rbx
0x180120af5  push    rbp
0x180120af6  push    rsi
0x180120af7  push    rdi
0x180120af8  push    r12
0x180120afa  push    r13
0x180120afc  push    r14
0x180120afe  push    r15
0x180120b00  lea     rbp, [rsp-3C0h]
0x180120b08  sub     rsp, 4C0h
0x180120b0f  mov     rax, cs:__security_cookie
0x180120b16  xor     rax, rsp
0x180120b19  mov     [rbp+3F0h+var_40], rax
0x180120b20  mov     r15, rdx
0x180120b23  mov     rdi, rcx
0x180120b26  mov     eax, cs:dword_18039EB68
0x180120b2c  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x180120b33  cmp     eax, 5
0x180120b36  jbe     short loc_180120B65
0x180120b38  mov     [rsp+4F0h+var_4A0], 5FDh
0x180120b40  mov     [rsp+4F0h+var_480], r12
0x180120b45  lea     rax, [rsp+4F0h+var_4A0]
0x180120b4a  mov     [rsp+4F0h+var_4C8], rax
0x180120b4f  lea     rax, [rsp+4F0h+var_480]
0x180120b54  mov     [rsp+4F0h+var_4D0], rax
0x180120b59  lea     rdx, word_18034C4DE
0x180120b60  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180120b65  xor     ebx, ebx
0x180120b67  mov     r14d, ebx
0x180120b6a  mov     esi, ebx
0x180120b6c  mov     [rsp+4F0h+var_480], rbx
0x180120b71  cmp     [rdi+10h], ebx
0x180120b74  jz      loc_180120FED
0x180120b7a  mov     ecx, [rdi+8]
0x180120b7d  lea     eax, [rcx-1]
0x180120b80  cmp     eax, 1
0x180120b83  jbe     loc_180120FED
0x180120b89  or      r13, 0FFFFFFFFFFFFFFFFh
0x180120b8d  cmp     ecx, 11h
0x180120b90  jnz     loc_180120EC5
0x180120b96  mov     [rsp+4F0h+var_490], rbx
0x180120b9b  lea     rcx, [rsp+4F0h+var_490]
0x180120ba0  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120ba5  mov     [rsp+4F0h+var_490], rbx
0x180120baa  mov     [rsp+4F0h+var_478], rbx
0x180120baf  lea     rcx, [rsp+4F0h+var_478]
0x180120bb4  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120bb9  mov     [rsp+4F0h+var_478], rbx
0x180120bbe  xor     edx, edx; Val
0x180120bc0  mov     r8d, 208h; Size
0x180120bc6  lea     rcx, [rbp+3F0h+szVolumePathName]; void *
0x180120bca  call    memset_0
0x180120bcf  lea     rdx, [rsp+4F0h+var_490]
0x180120bd4  mov     rcx, [rdi]; unsigned __int16 *
0x180120bd7  call    ?PmGetPartition@@YAHPEBGAEAV?$CSmRefPtr@VCPmPartition@@X@@@Z; PmGetPartition(ushort const *,CSmRefPtr<CPmPartition,void> &)
0x180120bdc  test    eax, eax
0x180120bde  jnz     loc_180120CAA
0x180120be4  call    cs:__imp_GetLastError
0x180120beb  nop     dword ptr [rax+rax+00h]
0x180120bf0  mov     ecx, eax
0x180120bf2  test    eax, eax
0x180120bf4  mov     eax, cs:dword_18039EB68
0x180120bfa  jnz     short loc_180120C29
0x180120bfc  cmp     eax, 4
0x180120bff  jbe     loc_180120C89
0x180120c05  mov     [rsp+4F0h+var_4A0], ebx
0x180120c09  mov     dword ptr [rsp+4F0h+var_498], 612h
0x180120c11  lea     rax, [rsp+4F0h+var_4A0]
0x180120c16  mov     [rsp+4F0h+var_4C0], rax
0x180120c1b  lea     rax, [rsp+4F0h+var_498]
0x180120c20  lea     rdx, byte_18034C919
0x180120c27  jmp     short loc_180120C55
0x180120c29  cmp     ecx, 7Ah ; 'z'
0x180120c2c  jnz     short loc_180120C77
0x180120c2e  cmp     eax, 3
0x180120c31  jbe     short loc_180120C89
0x180120c33  mov     dword ptr [rsp+4F0h+var_498], ecx
0x180120c37  lea     rdx, byte_180349003
0x180120c3e  mov     [rsp+4F0h+var_4A0], 612h
0x180120c46  lea     rax, [rsp+4F0h+var_498]
0x180120c4b  mov     [rsp+4F0h+var_4C0], rax
0x180120c50  lea     rax, [rsp+4F0h+var_4A0]
0x180120c55  mov     [rsp+4F0h+var_4C8], rax
0x180120c5a  lea     rax, [rsp+4F0h+var_480]
0x180120c5f  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x180120c66  mov     [rsp+4F0h+var_4D0], rax
0x180120c6b  mov     [rsp+4F0h+var_480], r12
0x180120c70  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180120c75  jmp     short loc_180120C90
0x180120c77  cmp     eax, 2
0x180120c7a  jbe     short loc_180120C89
0x180120c7c  mov     dword ptr [rsp+4F0h+var_498], ecx
0x180120c80  lea     rdx, byte_180348B4D
0x180120c87  jmp     short loc_180120C3E
0x180120c89  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x180120c90  lea     rcx, [rsp+4F0h+var_478]
0x180120c95  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120c9a  nop
0x180120c9b  lea     rcx, [rsp+4F0h+var_490]
0x180120ca0  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120ca5  jmp     loc_180121449
0x180120caa  mov     eax, cs:dword_18039EB68
0x180120cb0  cmp     eax, 4
0x180120cb3  jbe     short loc_180120D22
0x180120cb5  mov     edx, 400h
0x180120cba  lea     rcx, dword_18039EB68
0x180120cc1  call    _tlgKeywordOn
0x180120cc6  test    al, al
0x180120cc8  jz      short loc_180120D22
0x180120cca  mov     rax, [rsp+4F0h+var_490]
0x180120ccf  mov     rdx, [rax+8]
0x180120cd3  add     rdx, 0A4h
0x180120cda  mov     [rsp+4F0h+var_480], rdx
0x180120cdf  mov     rcx, rdi; this
0x180120ce2  call    ?ToObjectId@CPmEnumerationFilter@@QEAAPEBGXZ; CPmEnumerationFilter::ToObjectId(void)
0x180120ce7  test    rax, rax
0x180120cea  jz      short loc_180120CF6
0x180120cec  mov     rcx, rdi; this
0x180120cef  call    ?ToObjectId@CPmEnumerationFilter@@QEAAPEBGXZ; CPmEnumerationFilter::ToObjectId(void)
0x180120cf4  jmp     short loc_180120CFD
0x180120cf6  lea     rax, aUnknown; "Unknown"
0x180120cfd  mov     [rsp+4F0h+var_498], rax
0x180120d02  lea     rax, [rsp+4F0h+var_480]
0x180120d07  mov     [rsp+4F0h+var_4C8], rax
0x180120d0c  lea     rax, [rsp+4F0h+var_498]
0x180120d11  mov     [rsp+4F0h+var_4D0], rax
0x180120d16  lea     rdx, dword_18034CDFC
0x180120d1d  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180120d22  mov     rax, [rsp+4F0h+var_490]
0x180120d27  mov     r8, [rax+8]
0x180120d2b  add     r8, 0A4h; unsigned __int16 *
0x180120d32  cmp     [r8], bx
0x180120d36  jz      loc_180120E9E
0x180120d3c  mov     edx, 104h; unsigned __int64
0x180120d41  lea     rcx, [rbp+3F0h+szVolumePathName]; unsigned __int16 *
0x180120d45  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180120d4a  lea     r8, SubBlock; "\\"
0x180120d51  mov     edx, 104h; unsigned __int64
0x180120d56  lea     rcx, [rbp+3F0h+szVolumePathName]; unsigned __int16 *
0x180120d5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180120d5f  lea     rdx, [rsp+4F0h+var_478]
0x180120d64  lea     rcx, [rbp+3F0h+szVolumePathName]; unsigned __int16 *
0x180120d68  call    ?PmGetVolume@@YAHPEBGAEAV?$CSmRefPtr@VCPmVolume@@X@@@Z; PmGetVolume(ushort const *,CSmRefPtr<CPmVolume,void> &)
0x180120d6d  test    eax, eax
0x180120d6f  jnz     loc_180120DF5
0x180120d75  call    cs:__imp_GetLastError
0x180120d7c  nop     dword ptr [rax+rax+00h]
0x180120d81  mov     ecx, eax
0x180120d83  test    eax, eax
0x180120d85  mov     eax, cs:dword_18039EB68
0x180120d8b  jnz     short loc_180120DAE
0x180120d8d  cmp     eax, 4
0x180120d90  jbe     loc_180120C89
0x180120d96  mov     dword ptr [rsp+4F0h+var_498], ebx
0x180120d9a  mov     [rsp+4F0h+var_4A0], 629h
0x180120da2  lea     rdx, byte_18034D4A9
0x180120da9  jmp     loc_180120C46
0x180120dae  cmp     ecx, 7Ah ; 'z'
0x180120db1  jnz     short loc_180120DD4
0x180120db3  cmp     eax, 3
0x180120db6  jbe     loc_180120C89
0x180120dbc  mov     dword ptr [rsp+4F0h+var_498], ecx
0x180120dc0  mov     [rsp+4F0h+var_4A0], 629h
0x180120dc8  lea     rdx, dword_18034983C
0x180120dcf  jmp     loc_180120C46
0x180120dd4  cmp     eax, 2
0x180120dd7  jbe     loc_180120C89
0x180120ddd  mov     dword ptr [rsp+4F0h+var_498], ecx
0x180120de1  mov     [rsp+4F0h+var_4A0], 629h
0x180120de9  lea     rdx, word_18034A5D2
0x180120df0  jmp     loc_180120C46
0x180120df5  mov     eax, cs:dword_18039EB68
0x180120dfb  mov     rbx, [rsp+4F0h+var_478]
0x180120e00  cmp     eax, 4
0x180120e03  jbe     short loc_180120E80
0x180120e05  mov     rax, [rbx+8]
0x180120e09  movzx   ecx, word ptr [rax+0Ch]
0x180120e0d  mov     word ptr [rsp+4F0h+var_4A0], cx
0x180120e12  mov     rcx, [rbx+8]
0x180120e16  lea     rax, [rcx+0Eh]
0x180120e1a  mov     [rsp+4F0h+var_480], rax
0x180120e1f  lea     rax, [rcx+438h]
0x180120e26  mov     [rsp+4F0h+var_498], rax
0x180120e2b  mov     ecx, [rbx+18h]
0x180120e2e  call    ?SubsystemTypeToName@@YAPEBGW4WSP_SUBSYSTEM_TYPE@@@Z; SubsystemTypeToName(WSP_SUBSYSTEM_TYPE)
0x180120e33  mov     [rbp+3F0h+var_470], rax
0x180120e37  lea     rax, aMsftVolume; "MSFT_Volume"
0x180120e3e  mov     [rsp+4F0h+var_488], rax
0x180120e43  lea     rax, [rsp+4F0h+var_4A0]
0x180120e48  mov     [rsp+4F0h+var_4B0], rax
0x180120e4d  lea     rax, [rsp+4F0h+var_480]
0x180120e52  mov     [rsp+4F0h+var_4B8], rax
0x180120e57  lea     rax, [rsp+4F0h+var_498]
0x180120e5c  mov     [rsp+4F0h+var_4C0], rax
0x180120e61  lea     rax, [rbp+3F0h+var_470]
0x180120e65  mov     [rsp+4F0h+var_4C8], rax
0x180120e6a  lea     rax, [rsp+4F0h+var_488]
0x180120e6f  mov     [rsp+4F0h+var_4D0], rax
0x180120e74  lea     rdx, byte_18034C317
0x180120e7b  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &)
0x180120e80  mov     rax, [r15]
0x180120e83  mov     rdx, [rbx+8]
0x180120e87  add     rdx, 438h
0x180120e8e  mov     r8, rbx
0x180120e91  mov     rcx, r15
0x180120e94  mov     rax, [rax+8]
0x180120e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120e9d  nop
0x180120e9e  lea     rcx, [rsp+4F0h+var_478]
0x180120ea3  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120ea8  nop
0x180120ea9  lea     rcx, [rsp+4F0h+var_490]
0x180120eae  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120eb3  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x180120eba  mov     r14d, 1
0x180120ec0  jmp     loc_180121427
0x180120ec5  cmp     ecx, 12h
0x180120ec8  jnz     loc_180120F8B
0x180120ece  mov     [rsp+4F0h+var_490], rbx
0x180120ed3  lea     rcx, [rsp+4F0h+var_490]
0x180120ed8  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120edd  mov     [rsp+4F0h+var_490], rbx
0x180120ee2  mov     r8d, 104h; cchBufferLength
0x180120ee8  lea     rdx, [rbp+3F0h+szVolumePathName]; lpszVolumePathName
0x180120eec  mov     rcx, [rdi]; lpszFileName
0x180120eef  call    cs:__imp_GetVolumePathNameW
0x180120ef6  nop     dword ptr [rax+rax+00h]
0x180120efb  test    eax, eax
0x180120efd  jnz     short loc_180120F22
0x180120eff  xor     ecx, ecx; dwErrCode
0x180120f01  call    cs:__imp_SetLastError
0x180120f08  nop     dword ptr [rax+rax+00h]
0x180120f0d  mov     r14d, 1
0x180120f13  lea     rcx, [rsp+4F0h+var_490]
0x180120f18  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120f1d  jmp     loc_180121449
0x180120f22  mov     r8d, 104h; cchBufferLength
0x180120f28  lea     rdx, [rbp+3F0h+szVolumeName]; lpszVolumeName
0x180120f2f  lea     rcx, [rbp+3F0h+szVolumePathName]; lpszVolumeMountPoint
0x180120f33  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180120f3a  nop     dword ptr [rax+rax+00h]
0x180120f3f  test    eax, eax
0x180120f41  jz      short loc_180120EFF
0x180120f43  lea     rdx, [rsp+4F0h+var_490]
0x180120f48  lea     rcx, [rbp+3F0h+szVolumeName]; unsigned __int16 *
0x180120f4f  call    ?PmGetVolume@@YAHPEBGAEAV?$CSmRefPtr@VCPmVolume@@X@@@Z; PmGetVolume(ushort const *,CSmRefPtr<CPmVolume,void> &)
0x180120f54  test    eax, eax
0x180120f56  jz      short loc_180120EFF
0x180120f58  mov     rdx, [rsp+4F0h+var_490]
0x180120f5d  mov     eax, [rdx+18h]
0x180120f60  cmp     [rdi+0Ch], eax
0x180120f63  jnz     short loc_180120F7C
0x180120f65  mov     rax, [r15]
0x180120f68  mov     r8, rdx
0x180120f6b  mov     rdx, [rdx+10h]
0x180120f6f  mov     rcx, r15
0x180120f72  mov     rax, [rax+8]
0x180120f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120f7b  nop
0x180120f7c  lea     rcx, [rsp+4F0h+var_490]
0x180120f81  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180120f86  jmp     loc_180120EBA
0x180120f8b  mov     ebx, 57h ; 'W'
0x180120f90  mov     ecx, ebx; dwErrCode
0x180120f92  call    cs:__imp_SetLastError
0x180120f99  nop     dword ptr [rax+rax+00h]
0x180120f9e  mov     eax, cs:dword_18039EB68
0x180120fa4  cmp     eax, 2
0x180120fa7  jbe     loc_180121449
0x180120fad  mov     dword ptr [rsp+4F0h+var_498], ebx
0x180120fb1  mov     [rsp+4F0h+var_4A0], 65Dh
0x180120fb9  mov     [rsp+4F0h+var_488], r12
0x180120fbe  lea     rax, [rsp+4F0h+var_498]
0x180120fc3  mov     [rsp+4F0h+var_4C0], rax
0x180120fc8  lea     rax, [rsp+4F0h+var_4A0]
0x180120fcd  mov     [rsp+4F0h+var_4C8], rax
0x180120fd2  lea     rax, [rsp+4F0h+var_488]
0x180120fd7  mov     [rsp+4F0h+var_4D0], rax
0x180120fdc  lea     rdx, byte_18034BCFF
0x180120fe3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180120fe8  jmp     loc_180121449
0x180120fed  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 **
0x180120ff2  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x180120ff7  mov     r12d, 208h
0x180120ffd  mov     ecx, r12d; unsigned __int64
0x180121000  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180121005  mov     rsi, rax
0x180121008  mov     [rsp+4F0h+var_480], rax
0x18012100d  mov     edx, 104h; cchBufferLength
0x180121012  mov     rcx, rax; lpszVolumeName
0x180121015  call    cs:__imp_FindFirstVolumeW
0x18012101c  nop     dword ptr [rax+rax+00h]
0x180121021  mov     r13, rax
0x180121024  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180121028  jnz     loc_180121203
0x18012102e  call    cs:__imp_GetLastError
0x180121035  nop     dword ptr [rax+rax+00h]
0x18012103a  mov     ecx, eax
0x18012103c  test    eax, eax
0x18012103e  mov     eax, cs:dword_18039EB68
  ... truncated ...
```
