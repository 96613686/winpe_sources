# CFLACSource::ParseStreamMetadata(void)

- ea: `0x18002513c`
- end: `0x180025bdf`
- name: `?ParseStreamMetadata@CFLACSource@@AEAAJXZ`
- size: `2723`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002471c`

## callees

- `0x1800018e4`
- `0x1800018f0`
- `0x180016b0c`
- `0x180016e48`
- `0x180020398`
- `0x180020484`
- `0x1800212c8`
- `0x1800234fc`
- `0x1800243c8`
- `0x180024b54`
- `0x18002513c`
- `0x180025cc0`
- `0x180026540`
- `0x180027b80`
- `0x180027ba8`
- `0x180027df0`
- `0x180034a04`
- `0x1800377c4`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002560a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002564e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800252f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002560a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002564e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002528a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800253ba`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002540e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025558`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800255ab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002569f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800256ee`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002528a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800253ba`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002540e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025558`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800255ab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002569f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800256ee`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180025489`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180025489`
- `MFPlat!MFCreateMemoryBuffer` at `0x180025a37`
- `MFPlat!MFCreateMemoryBuffer` at `0x180025a37`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFLACSource::ParseStreamMetadata(CFLACSource *this)
{
  unsigned int v2; // eax
  unsigned __int8 *v3; // rcx
  unsigned int i; // edx
  unsigned __int8 *v5; // rax
  const void *v6; // r14
  unsigned int v7; // esi
  unsigned int v8; // edi
  char v9; // r8
  unsigned int v10; // esi
  int *v11; // rdx
  char *v12; // rcx
  __int64 v13; // rdi
  const CHAR *v14; // r13
  int v15; // r15d
  WCHAR *lpWideCharStr; // r12
  unsigned int v17; // eax
  signed int LastError; // eax
  unsigned int v19; // r14d
  unsigned int v20; // r12d
  unsigned int v21; // edx
  LPCCH v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // r13d
  __int64 v25; // r14
  int v26; // eax
  int cchWideChar; // r14d
  WCHAR *v28; // rax
  WCHAR *v29; // rdi
  unsigned int v30; // eax
  __int64 v31; // r15
  __int64 v32; // rdi
  unsigned int v33; // r12d
  int v34; // r15d
  const char *v35; // r14
  int v36; // eax
  int v37; // r13d
  WCHAR *v38; // rax
  WCHAR *v39; // r12
  unsigned int v40; // eax
  signed int v41; // eax
  signed int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // r13d
  WCHAR *v46; // rax
  unsigned int v47; // eax
  int Blob; // eax
  HRESULT v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rdx
  unsigned int v52; // edx
  __int64 v53; // rdx
  int v54; // eax
  DWORD v55; // eax
  size_t v56; // rdi
  unsigned int v58; // [rsp+30h] [rbp-49h] BYREF
  void *v59; // [rsp+38h] [rbp-41h] BYREF
  PROPVARIANT pvar; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v61; // [rsp+58h] [rbp-21h]
  int v62; // [rsp+5Ch] [rbp-1Dh]
  LPCCH lpMultiByteStr; // [rsp+60h] [rbp-19h]
  const void *v64; // [rsp+68h] [rbp-11h]
  _QWORD v65[12]; // [rsp+70h] [rbp-9h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v67; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v68; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v69; // [rsp+F8h] [rbp+7Fh]

  v67 = 0;
  v65[2] = this;
  v65[3] = &v67;
  v2 = *((_DWORD *)this + 86);
  v3 = (unsigned __int8 *)(*((_QWORD *)this + 41) + v2);
  for ( i = *((_DWORD *)this + 87) - v2; ; --i )
  {
    v59 = v3;
    if ( i <= 4 || *(_DWORD *)v3 == 1130450022 )
      break;
    ++v3;
  }
  v5 = v3;
  if ( i >= 4 )
  {
    v3 += 4;
    v59 = v3;
  }
  v6 = v5 + 4;
  if ( i < 4 )
    v6 = 0;
  v64 = v6;
  v7 = i - 4;
  if ( i < 4 )
    v7 = i;
  if ( v7 <= 4 )
  {
LABEL_97:
    if ( v6 )
    {
      v68 = 0;
      ppBuffer = 0;
      v49 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 39) + 48LL))(
              *((_QWORD *)this + 39),
              &v68);
      v67 = v49;
      if ( v49 < 0 )
      {
        if ( g_wppLevels )
        {
          v50 = 202;
LABEL_129:
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v50,
            &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids,
            this,
            v49);
          goto LABEL_130;
        }
        goto LABEL_130;
      }
      v55 = (_DWORD)v59 - (_DWORD)v6;
      v56 = (unsigned int)((_DWORD)v59 - (_DWORD)v6);
      *((_QWORD *)this + 37) = v68 - v7 - v56;
      v49 = MFCreateMemoryBuffer(v55, &ppBuffer);
      v67 = v49;
      if ( v49 < 0 )
      {
        if ( g_wppLevels )
        {
          v50 = 203;
          goto LABEL_129;
        }
LABEL_130:
        ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppBuffer);
        goto LABEL_140;
      }
      v49 = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, _QWORD, _QWORD))ppBuffer->lpVtbl->Lock)(
              ppBuffer,
              &v59,
              0,
              0);
      v67 = v49;
      if ( v49 < 0 )
      {
        if ( g_wppLevels )
        {
          v50 = 204;
          goto LABEL_129;
        }
        goto LABEL_130;
      }
      memcpy_0(v59, v6, v56);
      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      v49 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(
              ppBuffer,
              (unsigned int)v56);
      v67 = v49;
      if ( v49 < 0 )
      {
        if ( g_wppLevels )
        {
          v50 = 205;
          goto LABEL_129;
        }
        goto LABEL_130;
      }
      v49 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaBuffer *))(**((_QWORD **)this + 34) + 336LL))(
              *((_QWORD *)this + 34),
              ppBuffer);
      v67 = v49;
      if ( v49 < 0 )
      {
        if ( g_wppLevels )
        {
          v50 = 206;
          goto LABEL_129;
        }
        goto LABEL_130;
      }
      ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppBuffer);
    }
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)this + 14) + 232LL))((char *)this + 112)
      && (*((_BYTE *)this + 390) & 1) != 0 )
    {
      v54 = CFLACSource::ResetStart(this);
      v67 = v54;
      if ( v54 < 0 && g_wppLevels )
      {
        v53 = 208;
        goto LABEL_116;
      }
    }
    else
    {
      if ( byte_18006E80D )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 207, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
      v67 = -1072875792;
    }
LABEL_140:
    if ( v67 != -1072863856 )
      goto LABEL_141;
    return v67;
  }
LABEL_12:
  v8 = v3[3] | ((v3[2] | (v3[1] << 8)) << 8);
  v69 = v8;
  if ( v8 > v7 )
  {
    v52 = *((_DWORD *)this + 72);
    if ( v52 + *((_DWORD *)this + 87) - *((_DWORD *)this + 86) > 0x400000 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 195, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
      v67 = -1072875792;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_141;
      v51 = 196;
LABEL_110:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v51,
        &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids,
        this,
        -1072875792);
      goto LABEL_140;
    }
    v67 = CBuffReader::Reserve((CFLACSource *)((char *)this + 328), v52);
    if ( (v67 & 0x80000000) == 0 )
    {
      v67 = -1072863856;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        return v67;
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids,
        this,
        -1072863856);
      goto LABEL_140;
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v53 = 197;
      v54 = v67;
LABEL_116:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v53, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v54);
      goto LABEL_140;
    }
    goto LABEL_140;
  }
  v9 = *v3;
  LOBYTE(ppBuffer) = v9;
  v10 = v7 - 4;
  v11 = (int *)(v3 + 4);
  v12 = (char *)v11;
  v59 = v11;
  if ( (v9 & 0x7F) != 4 )
    goto LABEL_91;
  if ( v10 <= 4 )
    goto LABEL_90;
  v13 = (unsigned int)*v11;
  if ( v10 - 4 <= (unsigned int)v13 )
    goto LABEL_89;
  v14 = (const CHAR *)(v11 + 1);
  if ( (unsigned int)v13 >= 0x7FFF )
  {
    v15 = 0x7FFF;
  }
  else
  {
    if ( !(_DWORD)v13 )
      goto LABEL_29;
    v15 = *v11;
  }
  lpWideCharStr = (WCHAR *)operator new[](saturated_mul((unsigned int)(v13 + 1), 2u));
  v17 = MultiByteToWideChar(0xFDE9u, 0, v14, v15, lpWideCharStr, v15 + 1);
  if ( lpWideCharStr && v17 )
  {
    lpWideCharStr[v17] = 0;
    *(_QWORD *)&pvar.vt = 31;
    *(_OWORD *)&pvar.decVal.Lo32 = (unsigned __int64)lpWideCharStr;
    (*(void (__fastcall **)(_QWORD, const PROPERTYKEY *, PROPVARIANT *))(**((_QWORD **)this + 51) + 48LL))(
      *((_QWORD *)this + 51),
      &PKEY_Software_ProductName,
      &pvar);
LABEL_28:
    operator delete(lpWideCharStr);
    goto LABEL_29;
  }
  if ( lpWideCharStr )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFLACTagTelemetry::PopulateError((CFLACSource *)((char *)this + 456), LastError);
    goto LABEL_28;
  }
  CFLACTagTelemetry::PopulateError((CFLACSource *)((char *)this + 456), -2147024882);
LABEL_29:
  v19 = v10 - 4 - v13;
  if ( v19 <= 4 )
    goto LABEL_89;
  v20 = *(_DWORD *)&v14[v13];
  v21 = v19 - 4;
  v22 = &v14[v13 + 4];
  v23 = 0;
  v62 = 0;
  if ( !v20 )
    goto LABEL_89;
  while ( 1 )
  {
    if ( !v21 )
      goto LABEL_89;
    if ( v21 <= 4 )
    {
      v21 = 0;
      goto LABEL_88;
    }
    v24 = *(_DWORD *)v22;
    v21 -= 4;
    v61 = v21;
    if ( v24 > v21 )
      break;
    v22 += 4;
    lpMultiByteStr = v22;
    if ( !v24 )
      goto LABEL_88;
    v25 = 0;
    while ( v22[v25] != 61 )
    {
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= v24 )
      {
LABEL_38:
        v26 = MultiByteToWideChar(0xFDE9u, 0, v22, v24, 0, 0);
        if ( v26 )
        {
          cchWideChar = v26 + 1;
          v28 = (WCHAR *)operator new[](saturated_mul((unsigned int)(v26 + 1), 2u));
          v29 = v28;
          if ( v28 )
          {
            v30 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, v24, v28, cchWideChar);
            if ( v30 && dword_18006E1D8 )
            {
              v65[0] = v29;
              v65[1] = v30;
              (**((void (__fastcall ***)(char *, _QWORD, _QWORD *))this + 57))((char *)this + 456, 0, v65);
            }
            operator delete(v29);
          }
          else
          {
            CFLACTagTelemetry::PopulateError((CFLACSource *)((char *)this + 456), -2147024882);
          }
        }
        goto LABEL_55;
      }
    }
    v31 = 0;
    v61 = v21;
    lpMultiByteStr = v22;
    v58 = v24;
    LODWORD(v68) = v20;
    while ( 1 )
    {
      v32 = 6 * v31;
      if ( *((_QWORD *)&krgPKeyFLACMap + 6 * v31 + 2) )
        break;
LABEL_48:
      v31 = (unsigned int)(v31 + 1);
      if ( (unsigned int)v31 >= 0x17 )
        goto LABEL_38;
    }
    if ( CompareStringA(0x7Fu, 1u, *((PCNZCH *)&krgPKeyFLACMap + 6 * v31), -1, v22, v25) != 2 )
    {
      v22 = lpMultiByteStr;
      goto LABEL_48;
    }
    v33 = v24 - v25 - 1;
    v34 = 0x7FFF;
    if ( v33 < 0x7FFF )
      v34 = v24 - v25 - 1;
    if ( !v34 )
    {
      memset(&pvar, 0, sizeof(pvar));
      pvar.vt = 1;
      (*(void (__fastcall **)(_QWORD, _QWORD, PROPVARIANT *))(**((_QWORD **)this + 51) + 48LL))(
        *((_QWORD *)this + 51),
        *((_QWORD *)&krgPKeyFLACMap + v32 + 2),
        &pvar);
      goto LABEL_54;
    }
    v35 = &lpMultiByteStr[(unsigned int)v25 + 1];
    if ( !*((_QWORD *)&krgPKeyFLACMap + v32 + 5) )
    {
      v43 = *(_WORD *)(&krgPKeyFLACMap + v32 + 3) & 0xEFFF;
      if ( v43 != 31 )
      {
        if ( v43 == 19 )
        {
          v58 = 0;
          if ( (int)CFLACSource::ParseNumberFromCharacterArray(this, v35, v33, &v58) >= 0 )
          {
            memset(&pvar, 0, sizeof(pvar));
            pvar.vt = 19;
            pvar.lVal = v58;
            CFLACSource::AddValueToPropertyStore(
              this,
              *((_WORD *)&krgPKeyFLACMap + 4 * v32 + 12),
              &pvar,
              *((const struct _tagpropertykey **)&krgPKeyFLACMap + v32 + 2));
          }
        }
        else
        {
          if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 2u )
            WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 27));
          memset(&pvar, 0, sizeof(pvar));
          Blob = CMFPropVariant::CreateBlob((CMFPropVariant *)&pvar, v35, v33);
          if ( Blob < 0 )
            CFLACTagTelemetry::PopulateError((CFLACSource *)((char *)this + 456), Blob);
          else
            CFLACSource::AddValueToPropertyStore(
              this,
              *((_WORD *)&krgPKeyFLACMap + 4 * v32 + 12),
              &pvar,
              *((const struct _tagpropertykey **)&krgPKeyFLACMap + v32 + 2));
          CMFPropVariant::Clear(&pvar);
        }
        goto LABEL_54;
      }
      v44 = MultiByteToWideChar(0xFDE9u, 0, v35, v34, 0, 0);
      if ( !v44 )
      {
LABEL_69:
        v42 = GetLastError();
        if ( v42 > 0 )
          v42 = (unsigned __int16)v42 | 0x80070000;
        CFLACTagTelemetry::PopulateError((CFLACSource *)((char *)this + 456), v42);
        goto LABEL_54;
      }
      v45 = v44 + 1;
      v46 = (WCHAR *)operator new[](saturated_mul((unsigned int)(v44 + 1), 2u));
      v39 = v46;
      if ( v46 )
      {
        v47 = MultiByteToWideChar(0xFDE9u, 0, v35, v34, v46, v45);
        if ( v47 )
        {
          v39[v47] = 0;
          *(_QWORD *)&pvar.vt = 31;
          *(_OWORD *)&pvar.decVal.Lo32 = (unsigned __int64)v39;
          CFLACSource::AddValueToPropertyStore(
            this,
            *((_WORD *)&krgPKeyFLACMap + 4 * v32 + 12),
            &pvar,
            *((const struct _tagpropertykey **)&krgPKeyFLACMap + v32 + 2));
          goto LABEL_66;
        }
        goto LABEL_63;
      }
LABEL_68:
      CFLACTagTelemetry::PopulateError((CFLACSource *)((char *)this + 456), -2147024882);
      goto LABEL_67;
    }
    v36 = MultiByteToWideChar(0xFDE9u, 0, v35, v34, 0, 0);
    if ( !v36 )
      goto LABEL_69;
    v37 = v36 + 1;
    v38 = (WCHAR *)operator new[](saturated_mul((unsigned int)(v36 + 1), 2u));
    v39 = v38;
    if ( !v38 )
      goto LABEL_68;
    v40 = MultiByteToWideChar(0xFDE9u, 0, v35, v34, v38, v37);
    if ( v40 )
    {
      memset(&pvar, 0, sizeof(pvar));
      v39[v40] = 0;
      if ( (*((int (__fastcall **)(WCHAR *, PROPVARIANT *))&krgPKeyFLACMap + v32 + 5))(v39, &pvar) >= 0 )
        CFLACSource::AddValueToPropertyStore(
          this,
          *((_WORD *)&krgPKeyFLACMap + 4 * v32 + 12),
          &pvar,
          *((const struct _tagpropertykey **)&krgPKeyFLACMap + v32 + 2));
      CMFPropVariant::Clear(&pvar);
      goto LABEL_66;
    }
LABEL_63:
    v41 = GetLastError();
    if ( v41 > 0 )
      v41 = (unsigned __int16)v41 | 0x80070000;
    CFLACTagTelemetry::PopulateError((CFLACSource *)((char *)this + 456), v41);
LABEL_66:
    operator delete(v39);
LABEL_67:
    v24 = v58;
LABEL_54:
    v20 = v68;
LABEL_55:
    v21 = v61 - v24;
    v22 = &lpMultiByteStr[v24];
    v23 = v62;
LABEL_88:
    v62 = ++v23;
    if ( v23 >= v20 )
    {
LABEL_89:
      v8 = v69;
LABEL_90:
      *((_BYTE *)this + 390) |= 4u;
      CFLACSourceTelemetry::MetadataTypeSet((CFLACSource *)((char *)this + 424), *((_BYTE *)this + 390));
      v12 = (char *)v59;
      v9 = (char)ppBuffer;
LABEL_91:
      if ( v8 >= v10 )
      {
        v3 = (unsigned __int8 *)&v12[v10];
        v7 = 0;
      }
      else
      {
        v3 = (unsigned __int8 *)&v12[v8];
        v7 = v10 - v8;
      }
      v59 = v3;
      if ( v9 < 0 || v7 <= 4 )
      {
        v6 = v64;
        goto LABEL_97;
      }
      goto LABEL_12;
    }
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 199, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids);
  v67 = -1072875792;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v51 = 200;
    goto LABEL_110;
  }
LABEL_141:
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 14) + 192LL))((char *)this + 112);
  return v67;
}

```

## disassembly

```asm
0x18002513c  push    rbp
0x18002513e  push    rbx
0x18002513f  push    rsi
0x180025140  push    rdi
0x180025141  push    r12
0x180025143  push    r13
0x180025145  push    r14
0x180025147  push    r15
0x180025149  lea     rbp, [rsp-1Fh]
0x18002514e  sub     rsp, 98h
0x180025155  mov     rbx, rcx
0x180025158  mov     [rbp+57h+arg_8], 0
0x18002515f  mov     [rbp+57h+var_50], rcx
0x180025163  lea     rax, [rbp+57h+arg_8]
0x180025167  mov     [rbp+57h+var_48], rax
0x18002516b  lea     r8, [rcx+148h]
0x180025172  mov     eax, [r8+10h]
0x180025176  mov     ecx, eax
0x180025178  add     rcx, [r8]
0x18002517b  mov     edx, [rbx+15Ch]
0x180025181  sub     edx, eax
0x180025183  mov     r15d, 1
0x180025189  jmp     short loc_180025198
0x18002518b  cmp     dword ptr [rcx], 43614C66h
0x180025191  jz      short loc_1800251A1
0x180025193  dec     edx
0x180025195  add     rcx, r15
0x180025198  cmp     edx, 4
0x18002519b  mov     [rbp+57h+var_98], rcx
0x18002519f  ja      short loc_18002518B
0x1800251a1  mov     rax, rcx
0x1800251a4  cmp     edx, 4
0x1800251a7  jb      short loc_1800251B1
0x1800251a9  add     rcx, 4
0x1800251ad  mov     [rbp+57h+var_98], rcx
0x1800251b1  lea     r14, [rax+4]
0x1800251b5  xor     eax, eax
0x1800251b7  cmp     edx, 4
0x1800251ba  cmovb   r14, rax
0x1800251be  mov     [rbp+57h+var_68], r14
0x1800251c2  lea     esi, [rdx-4]
0x1800251c5  cmovb   esi, edx
0x1800251c8  cmp     esi, 4
0x1800251cb  jbe     loc_1800258A7
0x1800251d1  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800251d5  lea     r10, ?krgPKeyFLACMap@@3QBUPKEY_TO_FLAC_MAP@@B; PKEY_TO_FLAC_MAP const near * const krgPKeyFLACMap
0x1800251dc  movzx   edi, byte ptr [rcx+1]
0x1800251e0  shl     edi, 8
0x1800251e3  movzx   eax, byte ptr [rcx+2]
0x1800251e7  or      edi, eax
0x1800251e9  shl     edi, 8
0x1800251ec  movzx   eax, byte ptr [rcx+3]
0x1800251f0  or      edi, eax
0x1800251f2  mov     [rbp+57h+arg_18], edi
0x1800251f5  cmp     edi, esi
0x1800251f7  ja      loc_18002593E
0x1800251fd  mov     r8b, [rcx]
0x180025200  mov     byte ptr [rbp+57h+ppBuffer], r8b
0x180025204  add     esi, 0FFFFFFFCh
0x180025207  lea     rdx, [rcx+4]
0x18002520b  mov     rcx, rdx
0x18002520e  mov     [rbp+57h+var_98], rdx
0x180025212  mov     al, r8b
0x180025215  and     al, 7Fh
0x180025217  cmp     al, 4
0x180025219  jnz     loc_18002587D
0x18002521f  cmp     esi, 4
0x180025222  jbe     loc_180025851
0x180025228  mov     edi, [rdx]
0x18002522a  lea     r14d, [rsi-4]
0x18002522e  cmp     r14d, edi
0x180025231  jbe     loc_18002584E
0x180025237  lea     r13, [rdx+4]
0x18002523b  cmp     edi, 7FFFh
0x180025241  jnb     short loc_180025250
0x180025243  test    edi, edi
0x180025245  jz      loc_180025328
0x18002524b  mov     r15d, edi
0x18002524e  jmp     short loc_180025256
0x180025250  mov     r15d, 7FFFh
0x180025256  lea     ecx, [rdi+1]
0x180025259  mov     eax, 2
0x18002525e  mul     rcx
0x180025261  cmovb   rax, r9
0x180025265  mov     rcx, rax; unsigned __int64
0x180025268  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002526d  mov     r12, rax
0x180025270  lea     ecx, [r15+1]
0x180025274  mov     [rsp+0D0h+cchWideChar], ecx; cchWideChar
0x180025278  mov     [rsp+0D0h+lpWideCharStr], rax; lpWideCharStr
0x18002527d  mov     r9d, r15d; cbMultiByte
0x180025280  mov     r8, r13; lpMultiByteStr
0x180025283  xor     edx, edx; dwFlags
0x180025285  mov     ecx, 0FDE9h; CodePage
0x18002528a  call    cs:__imp_MultiByteToWideChar
0x180025290  test    r12, r12
0x180025293  jz      short loc_1800252DA
0x180025295  test    eax, eax
0x180025297  jz      short loc_1800252DA
0x180025299  mov     ecx, eax
0x18002529b  xor     eax, eax
0x18002529d  mov     [r12+rcx*2], ax
0x1800252a2  xorps   xmm0, xmm0
0x1800252a5  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800252a9  mov     qword ptr [rbp+57h+pvar+10h], rax
0x1800252ad  mov     eax, 1Fh
0x1800252b2  mov     word ptr [rbp+57h+pvar], ax
0x1800252b6  mov     qword ptr [rbp+57h+pvar+8], r12
0x1800252ba  mov     rcx, [rbx+198h]
0x1800252c1  mov     rax, [rcx]
0x1800252c4  lea     r8, [rbp+57h+pvar]
0x1800252c8  lea     rdx, PKEY_Software_ProductName
0x1800252cf  mov     rax, [rax+30h]
0x1800252d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252d8  jmp     short loc_180025311
0x1800252da  lea     r15, [rbx+1C8h]
0x1800252e1  test    r12, r12
0x1800252e4  jnz     short loc_1800252F5
0x1800252e6  mov     edx, 8007000Eh; int
0x1800252eb  mov     rcx, r15; this
0x1800252ee  call    ?PopulateError@CFLACTagTelemetry@@QEAAXJ@Z; CFLACTagTelemetry::PopulateError(long)
0x1800252f3  jmp     short loc_180025319
0x1800252f5  call    cs:__imp_GetLastError
0x1800252fb  test    eax, eax
0x1800252fd  jle     short loc_180025307
0x1800252ff  movzx   eax, ax
0x180025302  or      eax, 80070000h
0x180025307  mov     edx, eax; int
0x180025309  mov     rcx, r15; this
0x18002530c  call    ?PopulateError@CFLACTagTelemetry@@QEAAXJ@Z; CFLACTagTelemetry::PopulateError(long)
0x180025311  mov     rcx, r12; Block
0x180025314  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025319  or      r9, 0FFFFFFFFFFFFFFFFh; cchCount1
0x18002531d  lea     r10, ?krgPKeyFLACMap@@3QBUPKEY_TO_FLAC_MAP@@B; PKEY_TO_FLAC_MAP const near * const krgPKeyFLACMap
0x180025324  lea     r15d, [r9+2]
0x180025328  sub     r14d, edi
0x18002532b  cmp     r14d, 4
0x18002532f  jbe     loc_18002584E
0x180025335  mov     r12d, [rdi+r13]
0x180025339  lea     edx, [r14-4]
0x18002533d  lea     rcx, [rdi+4]
0x180025341  add     rcx, r13
0x180025344  xor     eax, eax
0x180025346  mov     [rbp+57h+var_74], eax
0x180025349  test    r12d, r12d
0x18002534c  jz      loc_18002584E
0x180025352  test    edx, edx
0x180025354  jz      loc_18002584E
0x18002535a  cmp     edx, 4
0x18002535d  jbe     loc_18002582F
0x180025363  mov     r13d, [rcx]
0x180025366  add     edx, 0FFFFFFFCh
0x180025369  mov     [rbp+57h+var_78], edx
0x18002536c  cmp     r13d, edx
0x18002536f  ja      loc_1800258F9
0x180025375  add     rcx, 4
0x180025379  mov     [rbp+57h+lpMultiByteStr], rcx
0x18002537d  test    r13d, r13d
0x180025380  jz      loc_180025831
0x180025386  xor     r14d, r14d
0x180025389  cmp     byte ptr [r14+rcx], 3Dh ; '='
0x18002538e  jz      loc_180025452
0x180025394  add     r14d, r15d
0x180025397  cmp     r14d, r13d
0x18002539a  jb      short loc_180025389
0x18002539c  mov     [rsp+0D0h+cchWideChar], 0; cchWideChar
0x1800253a4  mov     [rsp+0D0h+lpWideCharStr], 0; lpWideCharStr
0x1800253ad  mov     r9d, r13d; cbMultiByte
0x1800253b0  mov     r8, rcx; lpMultiByteStr
0x1800253b3  xor     edx, edx; dwFlags
0x1800253b5  mov     ecx, 0FDE9h; CodePage
0x1800253ba  call    cs:__imp_MultiByteToWideChar
0x1800253c0  test    eax, eax
0x1800253c2  jz      loc_18002550C
0x1800253c8  lea     r14d, [rax+1]
0x1800253cc  mov     ecx, r14d
0x1800253cf  mov     eax, 2
0x1800253d4  mul     rcx
0x1800253d7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800253de  cmovb   rax, rcx
0x1800253e2  mov     rcx, rax; unsigned __int64
0x1800253e5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800253ea  mov     rdi, rax
0x1800253ed  test    rax, rax
0x1800253f0  jz      loc_180025819
0x1800253f6  mov     [rsp+0D0h+cchWideChar], r14d; cchWideChar
0x1800253fb  mov     [rsp+0D0h+lpWideCharStr], rax; lpWideCharStr
0x180025400  mov     r9d, r13d; cbMultiByte
0x180025403  mov     r8, [rbp+57h+lpMultiByteStr]; lpMultiByteStr
0x180025407  xor     edx, edx; dwFlags
0x180025409  mov     ecx, 0FDE9h; CodePage
0x18002540e  call    cs:__imp_MultiByteToWideChar
0x180025414  test    eax, eax
0x180025416  jz      short loc_180025445
0x180025418  mov     ecx, cs:dword_18006E1D8
0x18002541e  test    ecx, ecx
0x180025420  jz      short loc_180025445
0x180025422  lea     rcx, [rbx+1C8h]
0x180025429  xor     edx, edx
0x18002542b  mov     [rbp+57h+var_58], rdx
0x18002542f  mov     [rbp+57h+var_60], rdi
0x180025433  mov     dword ptr [rbp+57h+var_58], eax
0x180025436  mov     rax, [rcx]
0x180025439  lea     r8, [rbp+57h+var_60]
0x18002543d  mov     rax, [rax]
0x180025440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025445  mov     rcx, rdi; Block
0x180025448  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002544d  jmp     loc_18002550C
0x180025452  xor     r15d, r15d
0x180025455  mov     [rbp+57h+var_78], edx
0x180025458  mov     [rbp+57h+lpMultiByteStr], rcx
0x18002545c  mov     [rbp+57h+var_A0], r13d
0x180025460  mov     dword ptr [rbp+57h+arg_10], r12d
0x180025464  lea     rdi, [r15+r15*2]
0x180025468  add     rdi, rdi
0x18002546b  cmp     qword ptr [r10+rdi*8+10h], 0
0x180025471  jz      short loc_18002549F
0x180025473  mov     [rsp+0D0h+cchWideChar], r14d; cchCount2
0x180025478  mov     [rsp+0D0h+lpWideCharStr], rcx; lpString2
0x18002547d  mov     r8, [r10+rdi*8]; lpString1
0x180025481  mov     edx, 1; dwCmpFlags
0x180025486  lea     ecx, [rdx+7Eh]; Locale
0x180025489  call    cs:__imp_CompareStringA
0x18002548f  cmp     eax, 2
0x180025492  jz      short loc_1800254B2
0x180025494  mov     rcx, [rbp+57h+lpMultiByteStr]
0x180025498  lea     r10, ?krgPKeyFLACMap@@3QBUPKEY_TO_FLAC_MAP@@B; PKEY_TO_FLAC_MAP const near * const krgPKeyFLACMap
0x18002549f  inc     r15d
0x1800254a2  cmp     r15d, 17h
0x1800254a6  jnb     loc_18002539C
0x1800254ac  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800254b0  jmp     short loc_180025464
0x1800254b2  mov     r12d, r13d
0x1800254b5  sub     r12d, r14d
0x1800254b8  dec     r12d
0x1800254bb  mov     eax, 7FFFh
0x1800254c0  mov     r15d, eax
0x1800254c3  cmp     r12d, eax
0x1800254c6  cmovb   r15d, r12d
0x1800254ca  xor     ecx, ecx
0x1800254cc  lea     rdx, ?krgPKeyFLACMap@@3QBUPKEY_TO_FLAC_MAP@@B; PKEY_TO_FLAC_MAP const near * const krgPKeyFLACMap
0x1800254d3  test    r15d, r15d
0x1800254d6  jnz     short loc_18002552A
0x1800254d8  xorps   xmm0, xmm0
0x1800254db  xor     eax, eax
0x1800254dd  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800254e1  mov     qword ptr [rbp+57h+pvar+10h], rax
0x1800254e5  lea     eax, [rcx+1]
0x1800254e8  mov     word ptr [rbp+57h+pvar], ax
0x1800254ec  mov     rcx, [rbx+198h]
0x1800254f3  mov     rax, [rcx]
0x1800254f6  lea     r8, [rbp+57h+pvar]
0x1800254fa  mov     rdx, [rdx+rdi*8+10h]
0x1800254ff  mov     rax, [rax+30h]
0x180025503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025508  mov     r12d, dword ptr [rbp+57h+arg_10]
0x18002550c  mov     edx, [rbp+57h+var_78]
0x18002550f  sub     edx, r13d
0x180025512  mov     eax, r13d
0x180025515  mov     rcx, [rbp+57h+lpMultiByteStr]
0x180025519  add     rcx, rax
0x18002551c  mov     eax, [rbp+57h+var_74]
0x18002551f  mov     r15d, 1
0x180025525  jmp     loc_180025831
0x18002552a  mov     eax, r14d
0x18002552d  mov     r14, [rbp+57h+lpMultiByteStr]
0x180025531  inc     r14
0x180025534  add     r14, rax
0x180025537  cmp     [rdx+rdi*8+28h], rcx
0x18002553c  jz      loc_180025673
0x180025542  mov     [rsp+0D0h+cchWideChar], ecx; cchWideChar
0x180025546  mov     [rsp+0D0h+lpWideCharStr], rcx; lpWideCharStr
0x18002554b  mov     r9d, r15d; cbMultiByte
0x18002554e  mov     r8, r14; lpMultiByteStr
0x180025551  xor     edx, edx; dwFlags
0x180025553  mov     ecx, 0FDE9h; CodePage
0x180025558  call    cs:__imp_MultiByteToWideChar
0x18002555e  test    eax, eax
0x180025560  jz      loc_18002564E
0x180025566  lea     r13d, [rax+1]
0x18002556a  mov     ecx, r13d
0x18002556d  mov     eax, 2
0x180025572  mul     rcx
0x180025575  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002557c  cmovb   rax, rcx
0x180025580  mov     rcx, rax; unsigned __int64
0x180025583  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025588  mov     r12, rax
0x18002558b  test    rax, rax
0x18002558e  jz      loc_18002563B
0x180025594  mov     [rsp+0D0h+cchWideChar], r13d; cchWideChar
0x180025599  mov     [rsp+0D0h+lpWideCharStr], rax; lpWideCharStr
0x18002559e  mov     r9d, r15d; cbMultiByte
0x1800255a1  mov     r8, r14; lpMultiByteStr
0x1800255a4  xor     edx, edx; dwFlags
0x1800255a6  mov     ecx, 0FDE9h; CodePage
0x1800255ab  call    cs:__imp_MultiByteToWideChar
0x1800255b1  test    eax, eax
0x1800255b3  jz      short loc_18002560A
  ... truncated ...
```
