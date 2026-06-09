# PmEnumerateVolumes(CPmEnumerationFilter *,CRefMap<ushort const *,CPmVolume *> &)

- ea: `0x18011ce80`
- end: `0x18011d7dc`
- name: `?PmEnumerateVolumes@@YAHPEAVCPmEnumerationFilter@@AEAV?$CRefMap@PEBGPEAVCPmVolume@@@@@Z`
- size: `2396`
- prototype: `__int64 __fastcall(CPmEnumerationFilter *this)`
- caller_count: `8`
- callee_count: `19`
- tags: `file_ops, reparse_path`

## callers

- `0x18010e42c`
- `0x1801118e8`
- `0x180144b50`
- `0x180168d50`
- `0x180170fb0`
- `0x180173e60`
- `0x180185e20`
- `0x1801863e0`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x180001740`
- `0x180003c80`
- `0x180006290`
- `0x1800062e0`
- `0x180006330`
- `0x180006cf4`
- `0x18000c704`
- `0x18000cd18`
- `0x1800117a0`
- `0x18001d380`
- `0x18004bca8`
- `0x18011943c`
- `0x18011ce80`
- `0x18011dfa0`
- `0x180127118`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011cf74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d0fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d53a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011cf74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d0fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d53a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d695`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011d27b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011d300`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011d62a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011d27b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011d300`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011d62a`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18011d37d`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18011d37d`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18011d26f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18011d26f`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18011d771`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18011d771`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18011d530`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x18011d530`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18011d2a7`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18011d2a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PmEnumerateVolumes(CPmEnumerationFilter *this, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // ebx
  unsigned int v7; // r14d
  unsigned __int16 *v8; // rsi
  int v9; // ecx
  __int64 FirstVolumeW; // r13
  DWORD v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  char *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  const unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // r8
  DWORD v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  DWORD LastError; // eax
  char *v31; // rdx
  __int64 v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // eax
  DWORD v38; // eax
  __int64 v39; // r8
  __int64 v40; // r9
  char *v41; // rdx
  DWORD v42; // ecx
  __int64 v43; // rcx
  __int64 v44; // r8
  __int64 v45; // r9
  __int16 *v46; // rdx
  DWORD v47; // eax
  const MI_Char *v49; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  const char *v51; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v54[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR szVolumeName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v52 = (unsigned __int16 *)"PmEnumerateVolumes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&word_180345556,
      a3,
      a4,
      &v52);
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
          if ( (unsigned int)dword_180397B68 <= 3 )
            goto LABEL_94;
          LODWORD(v49) = 122;
          v31 = byte_1803459BB;
        }
        else
        {
          if ( (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_94;
          LODWORD(v49) = LastError;
          v31 = (char *)qword_180343118;
        }
      }
      else
      {
        if ( (unsigned int)dword_180397B68 <= 4 )
          goto LABEL_94;
        LODWORD(v49) = 0;
        v31 = &byte_180344D47;
      }
      v51 = "PmEnumerateVolumes";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        LastError,
        (__int64)v31,
        v16,
        v17,
        &v51);
      goto LABEL_94;
    }
    while ( 1 )
    {
      if ( GetLastError() == 18 )
        goto LABEL_37;
      v53 = 0;
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
      v53 = 0;
      if ( (unsigned int)PmGetVolume(v8) )
      {
        v32 = v53;
        if ( (unsigned int)dword_180397B68 > 4 )
        {
          v33 = *(_QWORD *)(v53 + 8);
          v51 = (const char *)(v33 + 14);
          v54[0] = v33 + 1080;
          v50 = SubsystemTypeToName(*(unsigned int *)(v53 + 24));
          v49 = L"MSFT_Volume";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
            v34,
            (__int64)&byte_180344AEF,
            v35,
            v36,
            &v49,
            &v50,
            v54,
            &v51);
        }
        if ( !CSpCluster::IsClusterNode() || *(_DWORD *)(v32 + 24) == *((_DWORD *)this + 3) )
        {
          v37 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 8LL))(
                  a2,
                  *(_QWORD *)(v32 + 16),
                  v32);
          v6 = v37;
          if ( v37 < 0 )
          {
            v42 = (unsigned __int16)v37;
            if ( (v37 & 0x1FFF0000) != 0x70000 )
              v42 = v37;
            SetLastError(v42);
            if ( (unsigned int)dword_180397B68 > 2 )
            {
              LODWORD(v49) = 1674;
              v46 = &word_180344726;
              goto LABEL_84;
            }
LABEL_85:
            CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
            goto LABEL_94;
          }
        }
        v6 = 0;
      }
      else
      {
        v38 = GetLastError();
        if ( v38 )
        {
          if ( v38 != 122 )
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_65;
            LODWORD(v50) = v38;
            v41 = byte_180343541;
LABEL_76:
            v51 = "PmEnumerateVolumes";
            LODWORD(v49) = 1681;
LABEL_77:
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v38,
              (__int64)v41,
              v39,
              v40,
              &v51);
            goto LABEL_65;
          }
          if ( (unsigned int)dword_180397B68 > 3 )
          {
            LODWORD(v50) = 122;
            v41 = byte_1803463C5;
            goto LABEL_76;
          }
        }
        else if ( (unsigned int)dword_180397B68 > 4 )
        {
          LODWORD(v49) = 0;
          LODWORD(v50) = 1681;
          v51 = "PmEnumerateVolumes";
          v41 = (char *)&dword_180343EAC;
          goto LABEL_77;
        }
      }
LABEL_65:
      SmFreeString(&v52);
      v8 = (unsigned __int16 *)operator new[](0x208u);
      v52 = v8;
      if ( !FindNextVolumeW((HANDLE)FirstVolumeW, v8, 0x104u) && GetLastError() != 18 )
      {
        v47 = GetLastError();
        v43 = v47;
        if ( v47 )
        {
          if ( v47 == 122 )
          {
            if ( (unsigned int)dword_180397B68 > 3 )
            {
              LODWORD(v50) = 122;
              LODWORD(v49) = 1697;
              v51 = "PmEnumerateVolumes";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v47,
                (__int64)byte_180346793,
                v44,
                v45,
                &v51);
            }
          }
          else if ( (unsigned int)dword_180397B68 > 2 )
          {
            LODWORD(v50) = v47;
            LODWORD(v49) = 1697;
            v51 = "PmEnumerateVolumes";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v47,
              (__int64)&byte_180345BD7,
              v44,
              v45,
              &v51);
          }
        }
        else if ( (unsigned int)dword_180397B68 > 4 )
        {
          LODWORD(v49) = 1697;
          v46 = &word_180341B96;
LABEL_84:
          v51 = "PmEnumerateVolumes";
          LODWORD(v50) = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v43,
            (__int64)v46,
            v44,
            v45,
            &v51);
        }
        goto LABEL_85;
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
      v14 = v11;
      if ( v11 )
      {
        if ( v11 != 122 )
        {
          if ( (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_16;
          LODWORD(v49) = v11;
          v15 = byte_180341B33;
          goto LABEL_13;
        }
        if ( (unsigned int)dword_180397B68 > 3 )
        {
          LODWORD(v49) = 122;
          v15 = &byte_180342077;
          goto LABEL_13;
        }
      }
      else if ( (unsigned int)dword_180397B68 > 4 )
      {
        LODWORD(v49) = 1554;
        v15 = byte_180345923;
LABEL_13:
        v52 = (unsigned __int16 *)"PmEnumerateVolumes";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (__int64)v15,
          v12,
          v13,
          &v52);
      }
LABEL_16:
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
      goto LABEL_98;
    }
    if ( (unsigned int)dword_180397B68 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 1024) )
    {
      v52 = (unsigned __int16 *)(*(_QWORD *)(v50 + 8) + 164LL);
      if ( CPmEnumerationFilter::ToObjectId(this) )
        v21 = CPmEnumerationFilter::ToObjectId(this);
      else
        v21 = L"Unknown";
      v49 = v21;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v18,
        (__int64)byte_180345E11,
        v19,
        v20,
        &v49,
        &v52);
    }
    v22 = (const unsigned __int16 *)(*(_QWORD *)(v50 + 8) + 164LL);
    if ( *v22 )
    {
      StringCchCatW(szVolumePathName, 0x104u, v22);
      StringCchCatW(szVolumePathName, 0x104u, L"\\");
      if ( !(unsigned int)PmGetVolume(szVolumePathName) )
      {
        v23 = GetLastError();
        v14 = v23;
        if ( v23 )
        {
          if ( v23 == 122 )
          {
            if ( (unsigned int)dword_180397B68 <= 3 )
              goto LABEL_16;
            LODWORD(v49) = 122;
            v15 = (char *)&dword_1803428B4;
          }
          else
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_16;
            LODWORD(v49) = v23;
            v15 = (char *)qword_1803436B0;
          }
        }
        else
        {
          if ( (unsigned int)dword_180397B68 <= 4 )
            goto LABEL_16;
          LODWORD(v49) = 0;
          v15 = byte_180346521;
        }
        goto LABEL_13;
      }
      v24 = v53;
      if ( (unsigned int)dword_180397B68 > 4 )
      {
        v25 = *(_QWORD *)(v53 + 8);
        v52 = (unsigned __int16 *)(v25 + 14);
        v49 = (const MI_Char *)(v25 + 1080);
        v54[0] = SubsystemTypeToName(*(unsigned int *)(v53 + 24));
        v51 = (const char *)L"MSFT_Volume";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
          v26,
          (__int64)word_1803454D2,
          v27,
          v28,
          &v51,
          v54,
          &v49,
          &v52);
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a2 + 8LL))(a2, *(_QWORD *)(v24 + 8) + 1080LL, v24);
    }
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v53);
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
LABEL_37:
    v7 = 1;
LABEL_94:
    if ( v8 )
      operator delete(v8);
    if ( FirstVolumeW != -1 )
      FindVolumeClose((HANDLE)FirstVolumeW);
    goto LABEL_98;
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
      goto LABEL_98;
    }
    if ( *((_DWORD *)this + 3) == *(_DWORD *)(v50 + 24) )
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)a2 + 8LL))(a2, *(_QWORD *)(v50 + 16), v50);
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v50);
    goto LABEL_37;
  }
  SetLastError(0x57u);
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    LODWORD(v49) = 87;
    v51 = "PmEnumerateVolumes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v29,
      (__int64)&word_180344E6E,
      v16,
      v17,
      &v51);
  }
LABEL_98:
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v50) = 1712;
    v51 = "PmEnumerateVolumes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)dword_180397B68,
      (__int64)qword_180343D48,
      v16,
      v17,
      &v51);
  }
  return v7;
}

```

## disassembly

```asm
0x18011ce80  mov     [rsp-8+arg_10], rbx
0x18011ce85  push    rbp
0x18011ce86  push    rsi
0x18011ce87  push    rdi
0x18011ce88  push    r12
0x18011ce8a  push    r13
0x18011ce8c  push    r14
0x18011ce8e  push    r15
0x18011ce90  lea     rbp, [rsp-3C0h]
0x18011ce98  sub     rsp, 4C0h
0x18011ce9f  mov     rax, cs:__security_cookie
0x18011cea6  xor     rax, rsp
0x18011cea9  mov     [rbp+3F0h+var_40], rax
0x18011ceb0  mov     r15, rdx
0x18011ceb3  mov     rdi, rcx
0x18011ceb6  mov     eax, cs:dword_180397B68
0x18011cebc  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x18011cec3  cmp     eax, 5
0x18011cec6  jbe     short loc_18011CEF5
0x18011cec8  mov     [rsp+4F0h+var_4A0], 5FDh
0x18011ced0  mov     [rsp+4F0h+var_480], r12
0x18011ced5  lea     rax, [rsp+4F0h+var_4A0]
0x18011ceda  mov     [rsp+4F0h+var_4C8], rax
0x18011cedf  lea     rax, [rsp+4F0h+var_480]
0x18011cee4  mov     [rsp+4F0h+var_4D0], rax
0x18011cee9  lea     rdx, word_180345556
0x18011cef0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18011cef5  xor     ebx, ebx
0x18011cef7  mov     r14d, ebx
0x18011cefa  mov     esi, ebx
0x18011cefc  mov     [rsp+4F0h+var_480], rbx
0x18011cf01  cmp     [rdi+10h], ebx
0x18011cf04  jz      loc_18011D355
0x18011cf0a  mov     ecx, [rdi+8]
0x18011cf0d  lea     eax, [rcx-1]
0x18011cf10  cmp     eax, 1
0x18011cf13  jbe     loc_18011D355
0x18011cf19  or      r13, 0FFFFFFFFFFFFFFFFh
0x18011cf1d  cmp     ecx, 11h
0x18011cf20  jnz     loc_18011D245
0x18011cf26  mov     [rsp+4F0h+var_490], rbx
0x18011cf2b  lea     rcx, [rsp+4F0h+var_490]
0x18011cf30  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011cf35  mov     [rsp+4F0h+var_490], rbx
0x18011cf3a  mov     [rsp+4F0h+var_478], rbx
0x18011cf3f  lea     rcx, [rsp+4F0h+var_478]
0x18011cf44  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011cf49  mov     [rsp+4F0h+var_478], rbx
0x18011cf4e  xor     edx, edx; Val
0x18011cf50  mov     r8d, 208h; Size
0x18011cf56  lea     rcx, [rbp+3F0h+szVolumePathName]; void *
0x18011cf5a  call    memset_0
0x18011cf5f  lea     rdx, [rsp+4F0h+var_490]
0x18011cf64  mov     rcx, [rdi]; unsigned __int16 *
0x18011cf67  call    ?PmGetPartition@@YAHPEBGAEAV?$CSmRefPtr@VCPmPartition@@X@@@Z; PmGetPartition(ushort const *,CSmRefPtr<CPmPartition,void> &)
0x18011cf6c  test    eax, eax
0x18011cf6e  jnz     loc_18011D034
0x18011cf74  call    cs:__imp_GetLastError
0x18011cf7a  mov     ecx, eax
0x18011cf7c  test    eax, eax
0x18011cf7e  mov     eax, cs:dword_180397B68
0x18011cf84  jnz     short loc_18011CFB3
0x18011cf86  cmp     eax, 4
0x18011cf89  jbe     loc_18011D013
0x18011cf8f  mov     [rsp+4F0h+var_4A0], ebx
0x18011cf93  mov     dword ptr [rsp+4F0h+var_498], 612h
0x18011cf9b  lea     rax, [rsp+4F0h+var_4A0]
0x18011cfa0  mov     [rsp+4F0h+var_4C0], rax
0x18011cfa5  lea     rax, [rsp+4F0h+var_498]
0x18011cfaa  lea     rdx, byte_180345923
0x18011cfb1  jmp     short loc_18011CFDF
0x18011cfb3  cmp     ecx, 7Ah ; 'z'
0x18011cfb6  jnz     short loc_18011D001
0x18011cfb8  cmp     eax, 3
0x18011cfbb  jbe     short loc_18011D013
0x18011cfbd  mov     dword ptr [rsp+4F0h+var_498], ecx
0x18011cfc1  lea     rdx, byte_180342077
0x18011cfc8  mov     [rsp+4F0h+var_4A0], 612h
0x18011cfd0  lea     rax, [rsp+4F0h+var_498]
0x18011cfd5  mov     [rsp+4F0h+var_4C0], rax
0x18011cfda  lea     rax, [rsp+4F0h+var_4A0]
0x18011cfdf  mov     [rsp+4F0h+var_4C8], rax
0x18011cfe4  lea     rax, [rsp+4F0h+var_480]
0x18011cfe9  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x18011cff0  mov     [rsp+4F0h+var_4D0], rax
0x18011cff5  mov     [rsp+4F0h+var_480], r12
0x18011cffa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18011cfff  jmp     short loc_18011D01A
0x18011d001  cmp     eax, 2
0x18011d004  jbe     short loc_18011D013
0x18011d006  mov     dword ptr [rsp+4F0h+var_498], ecx
0x18011d00a  lea     rdx, byte_180341B33
0x18011d011  jmp     short loc_18011CFC8
0x18011d013  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x18011d01a  lea     rcx, [rsp+4F0h+var_478]
0x18011d01f  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011d024  nop
0x18011d025  lea     rcx, [rsp+4F0h+var_490]
0x18011d02a  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011d02f  jmp     loc_18011D777
0x18011d034  mov     eax, cs:dword_180397B68
0x18011d03a  cmp     eax, 4
0x18011d03d  jbe     short loc_18011D0AC
0x18011d03f  mov     edx, 400h
0x18011d044  lea     rcx, dword_180397B68
0x18011d04b  call    _tlgKeywordOn
0x18011d050  test    al, al
0x18011d052  jz      short loc_18011D0AC
0x18011d054  mov     rax, [rsp+4F0h+var_490]
0x18011d059  mov     rdx, [rax+8]
0x18011d05d  add     rdx, 0A4h
0x18011d064  mov     [rsp+4F0h+var_480], rdx
0x18011d069  mov     rcx, rdi; this
0x18011d06c  call    ?ToObjectId@CPmEnumerationFilter@@QEAAPEBGXZ; CPmEnumerationFilter::ToObjectId(void)
0x18011d071  test    rax, rax
0x18011d074  jz      short loc_18011D080
0x18011d076  mov     rcx, rdi; this
0x18011d079  call    ?ToObjectId@CPmEnumerationFilter@@QEAAPEBGXZ; CPmEnumerationFilter::ToObjectId(void)
0x18011d07e  jmp     short loc_18011D087
0x18011d080  lea     rax, aUnknown; "Unknown"
0x18011d087  mov     [rsp+4F0h+var_498], rax
0x18011d08c  lea     rax, [rsp+4F0h+var_480]
0x18011d091  mov     [rsp+4F0h+var_4C8], rax
0x18011d096  lea     rax, [rsp+4F0h+var_498]
0x18011d09b  mov     [rsp+4F0h+var_4D0], rax
0x18011d0a0  lea     rdx, byte_180345E11
0x18011d0a7  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18011d0ac  mov     rax, [rsp+4F0h+var_490]
0x18011d0b1  mov     r8, [rax+8]
0x18011d0b5  add     r8, 0A4h; unsigned __int16 *
0x18011d0bc  cmp     [r8], bx
0x18011d0c0  jz      loc_18011D21E
0x18011d0c6  mov     edx, 104h; unsigned __int64
0x18011d0cb  lea     rcx, [rbp+3F0h+szVolumePathName]; unsigned __int16 *
0x18011d0cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18011d0d4  lea     r8, SubBlock; "\\"
0x18011d0db  mov     edx, 104h; unsigned __int64
0x18011d0e0  lea     rcx, [rbp+3F0h+szVolumePathName]; unsigned __int16 *
0x18011d0e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18011d0e9  lea     rdx, [rsp+4F0h+var_478]
0x18011d0ee  lea     rcx, [rbp+3F0h+szVolumePathName]; unsigned __int16 *
0x18011d0f2  call    ?PmGetVolume@@YAHPEBGAEAV?$CSmRefPtr@VCPmVolume@@X@@@Z; PmGetVolume(ushort const *,CSmRefPtr<CPmVolume,void> &)
0x18011d0f7  test    eax, eax
0x18011d0f9  jnz     short loc_18011D175
0x18011d0fb  call    cs:__imp_GetLastError
0x18011d101  mov     ecx, eax
0x18011d103  test    eax, eax
0x18011d105  mov     eax, cs:dword_180397B68
0x18011d10b  jnz     short loc_18011D12E
0x18011d10d  cmp     eax, 4
0x18011d110  jbe     loc_18011D013
0x18011d116  mov     dword ptr [rsp+4F0h+var_498], ebx
0x18011d11a  mov     [rsp+4F0h+var_4A0], 629h
0x18011d122  lea     rdx, byte_180346521
0x18011d129  jmp     loc_18011CFD0
0x18011d12e  cmp     ecx, 7Ah ; 'z'
0x18011d131  jnz     short loc_18011D154
0x18011d133  cmp     eax, 3
0x18011d136  jbe     loc_18011D013
0x18011d13c  mov     dword ptr [rsp+4F0h+var_498], ecx
0x18011d140  mov     [rsp+4F0h+var_4A0], 629h
0x18011d148  lea     rdx, dword_1803428B4
0x18011d14f  jmp     loc_18011CFD0
0x18011d154  cmp     eax, 2
0x18011d157  jbe     loc_18011D013
0x18011d15d  mov     dword ptr [rsp+4F0h+var_498], ecx
0x18011d161  mov     [rsp+4F0h+var_4A0], 629h
0x18011d169  lea     rdx, qword_1803436B0
0x18011d170  jmp     loc_18011CFD0
0x18011d175  mov     eax, cs:dword_180397B68
0x18011d17b  mov     rbx, [rsp+4F0h+var_478]
0x18011d180  cmp     eax, 4
0x18011d183  jbe     short loc_18011D200
0x18011d185  mov     rax, [rbx+8]
0x18011d189  movzx   ecx, word ptr [rax+0Ch]
0x18011d18d  mov     word ptr [rsp+4F0h+var_4A0], cx
0x18011d192  mov     rcx, [rbx+8]
0x18011d196  lea     rax, [rcx+0Eh]
0x18011d19a  mov     [rsp+4F0h+var_480], rax
0x18011d19f  lea     rax, [rcx+438h]
0x18011d1a6  mov     [rsp+4F0h+var_498], rax
0x18011d1ab  mov     ecx, [rbx+18h]
0x18011d1ae  call    ?SubsystemTypeToName@@YAPEBGW4WSP_SUBSYSTEM_TYPE@@@Z; SubsystemTypeToName(WSP_SUBSYSTEM_TYPE)
0x18011d1b3  mov     [rbp+3F0h+var_470], rax
0x18011d1b7  lea     rax, aMsftVolume; "MSFT_Volume"
0x18011d1be  mov     [rsp+4F0h+var_488], rax
0x18011d1c3  lea     rax, [rsp+4F0h+var_4A0]
0x18011d1c8  mov     [rsp+4F0h+var_4B0], rax
0x18011d1cd  lea     rax, [rsp+4F0h+var_480]
0x18011d1d2  mov     [rsp+4F0h+var_4B8], rax
0x18011d1d7  lea     rax, [rsp+4F0h+var_498]
0x18011d1dc  mov     [rsp+4F0h+var_4C0], rax
0x18011d1e1  lea     rax, [rbp+3F0h+var_470]
0x18011d1e5  mov     [rsp+4F0h+var_4C8], rax
0x18011d1ea  lea     rax, [rsp+4F0h+var_488]
0x18011d1ef  mov     [rsp+4F0h+var_4D0], rax
0x18011d1f4  lea     rdx, word_1803454D2
0x18011d1fb  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &)
0x18011d200  mov     rax, [r15]
0x18011d203  mov     rdx, [rbx+8]
0x18011d207  add     rdx, 438h
0x18011d20e  mov     r8, rbx
0x18011d211  mov     rcx, r15
0x18011d214  mov     rax, [rax+8]
0x18011d218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d21d  nop
0x18011d21e  lea     rcx, [rsp+4F0h+var_478]
0x18011d223  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011d228  nop
0x18011d229  lea     rcx, [rsp+4F0h+var_490]
0x18011d22e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011d233  lea     r12, aPmenumeratevol; "PmEnumerateVolumes"
0x18011d23a  mov     r14d, 1
0x18011d240  jmp     loc_18011D75B
0x18011d245  cmp     ecx, 12h
0x18011d248  jnz     loc_18011D2F9
0x18011d24e  mov     [rsp+4F0h+var_490], rbx
0x18011d253  lea     rcx, [rsp+4F0h+var_490]
0x18011d258  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011d25d  mov     [rsp+4F0h+var_490], rbx
0x18011d262  mov     r8d, 104h; cchBufferLength
0x18011d268  lea     rdx, [rbp+3F0h+szVolumePathName]; lpszVolumePathName
0x18011d26c  mov     rcx, [rdi]; lpszFileName
0x18011d26f  call    cs:__imp_GetVolumePathNameW
0x18011d275  test    eax, eax
0x18011d277  jnz     short loc_18011D296
0x18011d279  xor     ecx, ecx; dwErrCode
0x18011d27b  call    cs:__imp_SetLastError
0x18011d281  mov     r14d, 1
0x18011d287  lea     rcx, [rsp+4F0h+var_490]
0x18011d28c  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011d291  jmp     loc_18011D777
0x18011d296  mov     r8d, 104h; cchBufferLength
0x18011d29c  lea     rdx, [rbp+3F0h+szVolumeName]; lpszVolumeName
0x18011d2a3  lea     rcx, [rbp+3F0h+szVolumePathName]; lpszVolumeMountPoint
0x18011d2a7  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18011d2ad  test    eax, eax
0x18011d2af  jz      short loc_18011D279
0x18011d2b1  lea     rdx, [rsp+4F0h+var_490]
0x18011d2b6  lea     rcx, [rbp+3F0h+szVolumeName]; unsigned __int16 *
0x18011d2bd  call    ?PmGetVolume@@YAHPEBGAEAV?$CSmRefPtr@VCPmVolume@@X@@@Z; PmGetVolume(ushort const *,CSmRefPtr<CPmVolume,void> &)
0x18011d2c2  test    eax, eax
0x18011d2c4  jz      short loc_18011D279
0x18011d2c6  mov     rdx, [rsp+4F0h+var_490]
0x18011d2cb  mov     eax, [rdx+18h]
0x18011d2ce  cmp     [rdi+0Ch], eax
0x18011d2d1  jnz     short loc_18011D2EA
0x18011d2d3  mov     rax, [r15]
0x18011d2d6  mov     r8, rdx
0x18011d2d9  mov     rdx, [rdx+10h]
0x18011d2dd  mov     rcx, r15
0x18011d2e0  mov     rax, [rax+8]
0x18011d2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d2e9  nop
0x18011d2ea  lea     rcx, [rsp+4F0h+var_490]
0x18011d2ef  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18011d2f4  jmp     loc_18011D23A
0x18011d2f9  mov     ebx, 57h ; 'W'
0x18011d2fe  mov     ecx, ebx; dwErrCode
0x18011d300  call    cs:__imp_SetLastError
0x18011d306  mov     eax, cs:dword_180397B68
0x18011d30c  cmp     eax, 2
0x18011d30f  jbe     loc_18011D777
0x18011d315  mov     dword ptr [rsp+4F0h+var_498], ebx
0x18011d319  mov     [rsp+4F0h+var_4A0], 65Dh
0x18011d321  mov     [rsp+4F0h+var_488], r12
0x18011d326  lea     rax, [rsp+4F0h+var_498]
0x18011d32b  mov     [rsp+4F0h+var_4C0], rax
0x18011d330  lea     rax, [rsp+4F0h+var_4A0]
0x18011d335  mov     [rsp+4F0h+var_4C8], rax
0x18011d33a  lea     rax, [rsp+4F0h+var_488]
0x18011d33f  mov     [rsp+4F0h+var_4D0], rax
0x18011d344  lea     rdx, word_180344E6E
0x18011d34b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18011d350  jmp     loc_18011D777
0x18011d355  lea     rcx, [rsp+4F0h+var_480]; unsigned __int16 **
0x18011d35a  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x18011d35f  mov     r12d, 208h
0x18011d365  mov     ecx, r12d; unsigned __int64
0x18011d368  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18011d36d  mov     rsi, rax
0x18011d370  mov     [rsp+4F0h+var_480], rax
0x18011d375  mov     edx, 104h; cchBufferLength
0x18011d37a  mov     rcx, rax; lpszVolumeName
0x18011d37d  call    cs:__imp_FindFirstVolumeW
0x18011d383  mov     r13, rax
0x18011d386  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011d38a  jnz     loc_18011D553
0x18011d390  call    cs:__imp_GetLastError
0x18011d396  mov     ecx, eax
0x18011d398  test    eax, eax
0x18011d39a  mov     eax, cs:dword_180397B68
0x18011d3a0  jnz     short loc_18011D3B8
0x18011d3a2  cmp     eax, 4
0x18011d3a5  jbe     loc_18011D754
0x18011d3ab  mov     dword ptr [rsp+4F0h+var_498], ebx
0x18011d3af  lea     rdx, byte_180344D47
0x18011d3b6  jmp     short loc_18011D3E7
0x18011d3b8  cmp     ecx, 7Ah ; 'z'
0x18011d3bb  jnz     short loc_18011D3D3
  ... truncated ...
```
