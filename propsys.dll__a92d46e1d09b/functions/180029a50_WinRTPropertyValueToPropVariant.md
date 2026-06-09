# WinRTPropertyValueToPropVariant

- ea: `0x180029a50`
- end: `0x18002a683`
- name: `WinRTPropertyValueToPropVariant`
- size: `3123`
- prototype: `HRESULT __stdcall(IUnknown *punkPropertyValue, PROPVARIANT *ppropvar)`
- caller_count: `1`
- callee_count: `53`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029a50`

## callees

- `0x180003f94`
- `0x180006b40`
- `0x18000c890`
- `0x1800194d0`
- `0x18001bff8`
- `0x18001c4fc`
- `0x1800231e8`
- `0x180029a50`
- `0x18002a68c`
- `0x18002a770`
- `0x18002a7b8`
- `0x18002ab10`
- `0x180048760`
- `0x1800537f0`
- `0x18005cd3c`
- `0x180069eec`
- `0x18006ed20`
- `0x180088468`
- `0x18008bca8`
- `0x18008bd50`
- `0x18008bdf4`
- `0x18008bf3c`
- `0x18008bfc0`
- `0x18008c064`
- `0x18008c108`
- `0x18008c1ac`
- `0x18008c870`
- `0x18008c8b4`
- `0x18008c904`
- `0x18008c948`
- `0x18008c998`
- `0x18008c9e8`
- `0x18008ca30`
- `0x18008ca80`
- `0x18008cba8`
- `0x18008cbf8`
- `0x18008cc48`
- `0x18008cc8c`
- `0x18008ccdc`
- `0x18008cd20`
- `0x18008cd70`
- `0x18008ce64`
- `0x18008cea8`
- `0x18008cef8`
- `0x18008cf74`
- `0x18008cfb8`
- `0x18008d008`
- `0x18008d04c`
- `0x18008d09c`
- `0x18008d0ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18002a4e6`
- `api-ms-win-core-com-l1-1-0!FreePropVariantArray` at `0x18002a4e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a5dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ba2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a5dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a5a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029b8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002a5a8`

## pseudocode

```c
HRESULT __stdcall WinRTPropertyValueToPropVariant(IUnknown *punkPropertyValue, PROPVARIANT *ppropvar)
{
  int DoubleArray; // edi
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  const unsigned __int16 *StringRawBuffer; // rax
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rax
  unsigned int v20; // ecx
  int UInt16; // eax
  int v22; // eax
  HRESULT inited; // eax
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int Char16Array; // eax
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  void *v35; // rcx
  __int64 v36; // r9
  PROPVARIANT *v37; // rbx
  void *v38; // rcx
  unsigned int v39; // r14d
  ULONG v40; // ecx
  PROPVARIANT *v41; // rax
  unsigned int i; // ebx
  PCWSTR *v43; // rbx
  void *v44; // rcx
  unsigned int v45; // r14d
  ULONG j; // edx
  unsigned int k; // ebx
  RoVariant *v48; // [rsp+20h] [rbp-50h] BYREF
  struct IInspectable *v49; // [rsp+28h] [rbp-48h] BYREF
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  IID clsid; // [rsp+38h] [rbp-38h] BYREF
  RoVariant *v52; // [rsp+48h] [rbp-28h] BYREF
  int v53; // [rsp+50h] [rbp-20h]
  struct Windows::Foundation::DateTime *v54; // [rsp+58h] [rbp-18h] BYREF
  int v55; // [rsp+60h] [rbp-10h] BYREF

  *(_OWORD *)ppropvar = 0;
  ppropvar[2] = 0;
  v52 = 0;
  v53 = 0;
  if ( punkPropertyValue )
  {
    v48 = (RoVariant *)&v52;
    v49 = 0;
    DoubleArray = ((__int64 (__fastcall *)(IUnknown *, GUID *, struct IInspectable **))punkPropertyValue->lpVtbl->QueryInterface)(
                    punkPropertyValue,
                    &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                    &v49);
    RoVariant::Attach((RoVariant *)&v52, v49);
    if ( DoubleArray < 0 )
      goto LABEL_19;
  }
  v4 = 0;
  v55 = 0;
  DoubleArray = v53;
  if ( v53 < 0 )
    goto LABEL_19;
  if ( v53 )
  {
    if ( v53 == 1 || v53 == 3 )
    {
      v4 = 13;
      v55 = 13;
    }
    else
    {
      DoubleArray = (*(__int64 (__fastcall **)(RoVariant *, int *))(*(_QWORD *)v52 + 48LL))(v52, &v55);
      if ( DoubleArray < 0 )
        goto LABEL_19;
      v4 = v55;
    }
  }
  if ( v4 > 1025 )
  {
    if ( v4 > 1032 )
    {
      v30 = v4 - 1033;
      if ( !v30 )
      {
        LODWORD(string) = 0;
        *(_QWORD *)&clsid.Data1 = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        DoubleArray = RoVariant::Accessor::GetDoubleArray(
                        (RoVariant::Accessor *)&v48,
                        (unsigned int *)&string,
                        (double **)&clsid);
        if ( DoubleArray >= 0 )
          DoubleArray = _InitPropVariantFromVector<5,double,double>(
                          *(_QWORD *)&clsid.Data1,
                          (unsigned int)string,
                          ppropvar);
        goto LABEL_160;
      }
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( !v32 )
        {
          LODWORD(string) = 0;
          *(_QWORD *)&clsid.Data1 = 0;
          v48 = v52;
          LODWORD(v49) = v53;
          DoubleArray = RoVariant::Accessor::GetBooleanArray(
                          (RoVariant::Accessor *)&v48,
                          (unsigned int *)&string,
                          (unsigned __int8 **)&clsid);
          if ( DoubleArray < 0 )
            goto LABEL_160;
          inited = _InitPropVariantFromVector<11,unsigned char,short>(
                     *(_QWORD *)&clsid.Data1,
                     (unsigned int)string,
                     ppropvar);
          goto LABEL_82;
        }
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            if ( v34 != 1 )
              goto LABEL_127;
            LODWORD(string) = 0;
            v54 = 0;
            v48 = v52;
            LODWORD(v49) = v53;
            DoubleArray = RoVariant::Accessor::GetDateTimeArray(
                            (RoVariant::Accessor *)&v48,
                            (unsigned int *)&string,
                            &v54);
            if ( DoubleArray >= 0 )
            {
              *(_QWORD *)&clsid.Data1 = 0;
              v48 = 0;
              DoubleArray = ULongLongMult((unsigned int)string, 8u, (unsigned __int64 *)&v48);
              if ( DoubleArray >= 0 )
              {
                DoubleArray = CTCoAllocPolicy::Alloc(v35, 1u, (unsigned __int64)v48, (void **)&clsid);
                v36 = *(_QWORD *)&clsid.Data1;
              }
              v20 = 0;
              if ( DoubleArray >= 0 )
              {
                while ( 1 )
                {
                  if ( v20 >= (unsigned int)string )
                  {
                    DoubleArray = _InitPropVariantFromVector<64,_FILETIME,_FILETIME>(
                                    v36,
                                    (unsigned int)string,
                                    ppropvar);
                    goto LABEL_129;
                  }
                  v19 = *((_QWORD *)v54 + v20);
                  if ( v19 < 0 )
                    break;
                  *(_QWORD *)(v36 + 8LL * v20++) = v19;
                }
                DoubleArray = -2147483637;
              }
LABEL_129:
              CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(&clsid);
            }
            CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(&v54);
            goto LABEL_19;
          }
          LODWORD(string) = 0;
          *(_QWORD *)&clsid.Data1 = 0;
          v48 = v52;
          LODWORD(v49) = v53;
          DoubleArray = RoVariant::Accessor::GetInspectableArray(
                          (RoVariant::Accessor *)&v48,
                          (unsigned int *)&string,
                          (struct IInspectable ***)&clsid);
          if ( DoubleArray >= 0 )
          {
            v37 = 0;
            v54 = 0;
            v48 = 0;
            DoubleArray = ULongLongMult((unsigned int)string, 0x18u, (unsigned __int64 *)&v48);
            if ( DoubleArray >= 0 )
            {
              DoubleArray = CTCoAllocPolicy::Alloc(v38, 1u, (unsigned __int64)v48, (void **)&v54);
              v37 = (PROPVARIANT *)v54;
            }
            if ( DoubleArray >= 0 )
            {
              v39 = 0;
              while ( 1 )
              {
                v40 = (unsigned int)string;
                if ( v39 >= (unsigned int)string )
                  break;
                DoubleArray = WinRTPropertyValueToPropVariant(
                                *(IUnknown **)(*(_QWORD *)&clsid.Data1 + 8LL * v39),
                                &v37[3 * v39]);
                ++v39;
                if ( DoubleArray < 0 )
                {
                  v40 = (unsigned int)string;
                  goto LABEL_140;
                }
              }
              *(_WORD *)ppropvar = 4108;
              *((_DWORD *)ppropvar + 2) = v40;
              v41 = v37;
              v37 = 0;
              v54 = 0;
              ppropvar[2] = v41;
LABEL_140:
              FreePropVariantArray(v40, v37);
            }
            for ( i = 0; i < (unsigned int)string; ++i )
              SafeRelease<IShellFolder2>(*(_QWORD *)&clsid.Data1 + 8LL * i);
            CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(&v54);
          }
        }
        else
        {
          LODWORD(string) = 0;
          *(_QWORD *)&clsid.Data1 = 0;
          v48 = v52;
          LODWORD(v49) = v53;
          DoubleArray = RoVariant::Accessor::GetStringArray(
                          (RoVariant::Accessor *)&v48,
                          (unsigned int *)&string,
                          (HSTRING **)&clsid);
          if ( DoubleArray >= 0 )
          {
            v43 = 0;
            v54 = 0;
            v48 = 0;
            DoubleArray = ULongLongMult((unsigned int)string, 8u, (unsigned __int64 *)&v48);
            if ( DoubleArray >= 0 )
            {
              DoubleArray = CTCoAllocPolicy::Alloc(v44, 1u, (unsigned __int64)v48, (void **)&v54);
              v43 = (PCWSTR *)v54;
            }
            if ( DoubleArray >= 0 )
            {
              v45 = 0;
              for ( j = (unsigned int)string; v45 < (unsigned int)string; j = (unsigned int)string )
              {
                v43[v45] = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)&clsid.Data1 + 8LL * v45), 0);
                ++v45;
              }
              DoubleArray = InitPropVariantFromStringVector(v43, j, ppropvar);
            }
            for ( k = 0; k < (unsigned int)string; ++k )
              WindowsDeleteString(*(HSTRING *)(*(_QWORD *)&clsid.Data1 + 8LL * k));
            CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(&v54);
          }
        }
LABEL_160:
        CCoTaskMemPtr<HSTRING__ *>::~CCoTaskMemPtr<HSTRING__ *>(&clsid);
        goto LABEL_19;
      }
      LODWORD(string) = 0;
      *(_QWORD *)&clsid.Data1 = 0;
      v48 = v52;
      LODWORD(v49) = v53;
      Char16Array = RoVariant::Accessor::GetChar16Array(
                      (RoVariant::Accessor *)&v48,
                      (unsigned int *)&string,
                      (unsigned __int16 **)&clsid);
    }
    else
    {
      if ( v4 == 1032 )
      {
        LODWORD(string) = 0;
        *(_QWORD *)&clsid.Data1 = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        DoubleArray = RoVariant::Accessor::GetSingleArray(
                        (RoVariant::Accessor *)&v48,
                        (unsigned int *)&string,
                        (float **)&clsid);
        if ( DoubleArray >= 0 )
          DoubleArray = _InitPropVariantFromVector<4,float,float>(
                          *(_QWORD *)&clsid.Data1,
                          (unsigned int)string,
                          ppropvar);
        goto LABEL_160;
      }
      v24 = v4 - 1026;
      if ( !v24 )
      {
        LODWORD(string) = 0;
        *(_QWORD *)&clsid.Data1 = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        DoubleArray = RoVariant::Accessor::GetInt16Array(
                        (RoVariant::Accessor *)&v48,
                        (unsigned int *)&string,
                        (__int16 **)&clsid);
        if ( DoubleArray >= 0 )
          DoubleArray = _InitPropVariantFromVector<2,short,short>(
                          *(_QWORD *)&clsid.Data1,
                          (unsigned int)string,
                          ppropvar);
        goto LABEL_160;
      }
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( v28 )
            {
              if ( v28 != 1 )
                goto LABEL_127;
              LODWORD(string) = 0;
              *(_QWORD *)&clsid.Data1 = 0;
              v48 = v52;
              LODWORD(v49) = v53;
              DoubleArray = RoVariant::Accessor::GetUInt64Array(
                              (RoVariant::Accessor *)&v48,
                              (unsigned int *)&string,
                              (unsigned __int64 **)&clsid);
              if ( DoubleArray >= 0 )
                DoubleArray = _InitPropVariantFromVector<21,unsigned __int64,unsigned __int64>(
                                *(_QWORD *)&clsid.Data1,
                                (unsigned int)string,
                                ppropvar);
            }
            else
            {
              LODWORD(string) = 0;
              *(_QWORD *)&clsid.Data1 = 0;
              v48 = v52;
              LODWORD(v49) = v53;
              DoubleArray = RoVariant::Accessor::GetInt64Array(
                              (RoVariant::Accessor *)&v48,
                              (unsigned int *)&string,
                              (__int64 **)&clsid);
              if ( DoubleArray >= 0 )
                DoubleArray = _InitPropVariantFromVector<20,__int64,__int64>(
                                *(_QWORD *)&clsid.Data1,
                                (unsigned int)string,
                                ppropvar);
            }
          }
          else
          {
            LODWORD(string) = 0;
            *(_QWORD *)&clsid.Data1 = 0;
            v48 = v52;
            LODWORD(v49) = v53;
            DoubleArray = RoVariant::Accessor::GetUInt32Array(
                            (RoVariant::Accessor *)&v48,
                            (unsigned int *)&string,
                            (unsigned int **)&clsid);
            if ( DoubleArray >= 0 )
              DoubleArray = _InitPropVariantFromVector<19,unsigned long,unsigned long>(
                              *(_QWORD *)&clsid.Data1,
                              (unsigned int)string,
                              ppropvar);
          }
        }
        else
        {
          LODWORD(string) = 0;
          *(_QWORD *)&clsid.Data1 = 0;
          v48 = v52;
          LODWORD(v49) = v53;
          DoubleArray = RoVariant::Accessor::GetInt32Array(
                          (RoVariant::Accessor *)&v48,
                          (unsigned int *)&string,
                          (int **)&clsid);
          if ( DoubleArray >= 0 )
            DoubleArray = _InitPropVariantFromVector<3,long,long>(
                            *(_QWORD *)&clsid.Data1,
                            (unsigned int)string,
                            ppropvar);
        }
        goto LABEL_160;
      }
      LODWORD(string) = 0;
      *(_QWORD *)&clsid.Data1 = 0;
      v48 = v52;
      LODWORD(v49) = v53;
      Char16Array = RoVariant::Accessor::GetUInt16Array(
                      (RoVariant::Accessor *)&v48,
                      (unsigned int *)&string,
                      (unsigned __int16 **)&clsid);
    }
    DoubleArray = Char16Array;
    if ( Char16Array >= 0 )
      DoubleArray = _InitPropVariantFromVector<18,unsigned short,unsigned short>(
                      *(_QWORD *)&clsid.Data1,
                      (unsigned int)string,
                      ppropvar);
    goto LABEL_160;
  }
  if ( v4 == 1025 )
  {
    LODWORD(string) = 0;
    *(_QWORD *)&clsid.Data1 = 0;
    v48 = v52;
    LODWORD(v49) = v53;
    DoubleArray = RoVariant::Accessor::GetUInt8Array(
                    (RoVariant::Accessor *)&v48,
                    (unsigned int *)&string,
                    (unsigned __int8 **)&clsid);
    if ( DoubleArray >= 0 )
    {
      inited = InitPropVariantFromBuffer(*(const void **)&clsid.Data1, (UINT)string, ppropvar);
LABEL_82:
      DoubleArray = inited;
      goto LABEL_160;
    }
    goto LABEL_160;
  }
  if ( v4 <= 8 )
  {
    if ( v4 == 8 )
    {
      LODWORD(string) = 0;
      v48 = v52;
      LODWORD(v49) = v53;
      DoubleArray = RoVariant::Accessor::GetSingle((RoVariant::Accessor *)&v48, (float *)&string);
      if ( DoubleArray < 0 )
        goto LABEL_19;
      *(_WORD *)ppropvar = 4;
      *((_DWORD *)ppropvar + 2) = (_DWORD)string;
      goto LABEL_35;
    }
    if ( v4 )
    {
      v11 = v4 - 1;
      if ( !v11 )
      {
        LOBYTE(string) = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        DoubleArray = RoVariant::Accessor::GetUInt8((RoVariant::Accessor *)&v48, (unsigned __int8 *)&string);
        if ( DoubleArray < 0 )
          goto LABEL_19;
        *(_WORD *)ppropvar = 17;
        *((_BYTE *)ppropvar + 8) = (_BYTE)string;
        goto LABEL_35;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        LOWORD(string) = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        DoubleArray = RoVariant::Accessor::GetInt16((RoVariant::Accessor *)&v48, (__int16 *)&string);
        if ( DoubleArray < 0 )
          goto LABEL_19;
        *(_WORD *)ppropvar = 2;
LABEL_61:
        *((_WORD *)ppropvar + 4) = (_WORD)string;
        goto LABEL_35;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
        LOWORD(string) = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        UInt16 = RoVariant::Accessor::GetUInt16((RoVariant::Accessor *)&v48, (unsigned __int16 *)&string);
LABEL_57:
        DoubleArray = UInt16;
        if ( UInt16 < 0 )
          goto LABEL_19;
        *(_WORD *)ppropvar = 18;
        goto LABEL_61;
      }
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 != 1 )
              goto LABEL_127;
            v48 = v52;
            LODWORD(v49) = v53;
            *(_QWORD *)&clsid.Data1 = 0;
            DoubleArray = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v48);
            if ( DoubleArray < 0 )
              goto LABEL_19;
            DoubleArray = (*(__int64 (__fastcall **)(RoVariant *, IID *))(*(_QWORD *)v52 + 112LL))(v52, &clsid);
            if ( DoubleArray < 0 )
              goto LABEL_19;
            *(_WORD *)ppropvar = 21;
          }
          else
          {
            v48 = v52;
            LODWORD(v49) = v53;
            *(_QWORD *)&clsid.Data1 = 0;
            DoubleArray = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v48);
            if ( DoubleArray < 0 )
              goto LABEL_19;
            DoubleArray = (*(__int64 (__fastcall **)(RoVariant *, IID *))(*(_QWORD *)v52 + 104LL))(v52, &clsid);
            if ( DoubleArray < 0 )
              goto LABEL_19;
            *(_WORD *)ppropvar = 20;
          }
          ppropvar[1] = *(PROPVARIANT *)&clsid.Data1;
          goto LABEL_35;
        }
        LODWORD(string) = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        DoubleArray = RoVariant::Accessor::GetUInt32((RoVariant::Accessor *)&v48, (unsigned int *)&string);
        if ( DoubleArray < 0 )
          goto LABEL_19;
        *(_WORD *)ppropvar = 19;
      }
      else
      {
        LODWORD(string) = 0;
        v48 = v52;
        LODWORD(v49) = v53;
        DoubleArray = RoVariant::Accessor::GetInt32((RoVariant::Accessor *)&v48, (int *)&string);
        if ( DoubleArray < 0 )
          goto LABEL_19;
        *(_WORD *)ppropvar = 3;
      }
      *((_DWORD *)ppropvar + 2) = (_DWORD)string;
    }
LABEL_35:
    DoubleArray = 0;
    goto LABEL_19;
  }
  v5 = v4 - 9;
  if ( !v5 )
  {
    *(_QWORD *)&clsid.Data1 = 0;
    v48 = v52;
    LODWORD(v49) = v53;
    DoubleArray = RoVariant::Accessor::GetDouble((RoVariant::Accessor *)&v48, (double *)&clsid.Data1);
    if ( DoubleArray < 0 )
      goto LABEL_19;
    *(_WORD *)ppropvar = 5;
    ppropvar[1] = *(PROPVARIANT *)&clsid.Data1;
    goto LABEL_35;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    LOWORD(string) = 0;
    v48 = v52;
    LODWORD(v49) = v53;
    UInt16 = RoVariant::Accessor::GetChar16((RoVariant::Accessor *)&v48, (unsigned __int16 *)&string);
    goto LABEL_57;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    LOBYTE(string) = 0;
    v48 = v52;
    LODWORD(v49) = v53;
    DoubleArray = RoVariant::Accessor::GetBoolean((RoVariant::Accessor *)&v48, (unsigned __int8 *)&string);
    if ( DoubleArray < 0 )
      goto LABEL_19;
    *(_WORD *)ppropvar = 11;
    *((_WORD *)ppropvar + 4) = -((_BYTE)string != 0);
    goto LABEL_35;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    string = 0;
    v48 = v52;
    LODWORD(v49) = v53;
    WindowsDeleteString(0);
    string = 0;
    DoubleArray = RoVariant::Accessor::GetString((RoVariant::Accessor *)&v48, &string);
    if ( DoubleArray >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      DoubleArray = InitPropVariantFromString(StringRawBuffer, (struct tagPROPVARIANT *)ppropvar);
    }
    WindowsDeleteString(string);
    goto LABEL_19;
  }
  v17 = v8 - 1;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( !v18 )
    {
      v48 = v52;
      LODWORD(v49) = v53;
      *(_QWORD *)&clsid.Data1 = 0;
      DoubleArray = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v48);
      if ( DoubleArray >= 0 )
      {
        DoubleArray = (*(__int64 (__fastcall **)(RoVariant *, IID *))(*(_QWORD *)v52 + 168LL))(v52, &clsid);
        if ( DoubleArray >= 0 )
        {
          if ( *(__int64 *)&clsid.Data1 < 0 )
          {
            DoubleArray = -2147483637;
          }
          else
          {
            v54 = *(struct Windows::Foundation::DateTime **)&clsid.Data1;
            DoubleArray = SHConvertTime(&v54, 0, ppropvar + 1, 0);
            if ( DoubleArray >= 0 )
              *(_WORD *)ppropvar = 64;
          }
        }
      }
      goto LABEL_19;
    }
    if ( v18 == 2 )
    {
      clsid = 0;
      v48 = v52;
      LODWORD(v49) = v53;
      DoubleArray = RoVariant::Accessor::GetGuid((RoVariant::Accessor *)&v48, &clsid);
      if ( DoubleArray >= 0 )
        DoubleArray = InitPropVariantFromCLSID(&clsid, ppropvar);
      goto LABEL_19;
    }
LABEL_127:
    DoubleArray = -2147418113;
    goto LABEL_19;
  }
  string = 0;
  v48 = v52;
  LODWORD(v49) = v53;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&string);
  DoubleArray = RoVariant::Accessor::GetInspectable((RoVariant::Accessor *)&v48, (struct IInspectable **)&string);
  if ( DoubleArray >= 0 )
  {
    *(_QWORD *)&clsid.Data1 = 0;
    if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<IPropertyValue>(&string, &clsid) < 0 )
      v22 = InitPropVariantFromUnknown((IUnknown *)string, (struct tagPROPVARIANT *)ppropvar);
    else
      v22 = (*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(**(_QWORD **)&clsid.Data1 + 40LL))(
              *(_QWORD *)&clsid.Data1,
              ppropvar);
    DoubleArray = v22;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&clsid);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&string);
LABEL_19:
  if ( v52 && ((v53 - 3) & 0xFFFFFFFB) == 0 )
    (*(void (**)(void))(*(_QWORD *)v52 + 16LL))();
  return DoubleArray;
}

```

## disassembly

```asm
0x180029a50  mov     [rsp-28h+arg_10], rbx
0x180029a55  push    rbp
0x180029a56  push    rsi
0x180029a57  push    rdi
0x180029a58  push    r14
0x180029a5a  push    r15
0x180029a5c  mov     rbp, rsp
0x180029a5f  sub     rsp, 70h
0x180029a63  mov     rax, cs:__security_cookie
0x180029a6a  xor     rax, rsp
0x180029a6d  mov     [rbp+var_8], rax
0x180029a71  mov     rsi, rdx
0x180029a74  xorps   xmm0, xmm0
0x180029a77  xor     eax, eax
0x180029a79  movups  xmmword ptr [rdx], xmm0
0x180029a7c  mov     [rdx+10h], rax
0x180029a80  xor     r15d, r15d
0x180029a83  mov     [rbp+var_28], r15
0x180029a87  mov     [rbp+var_20], r15d
0x180029a8b  test    rcx, rcx
0x180029a8e  jz      short loc_180029ACA
0x180029a90  lea     rax, [rbp+var_28]
0x180029a94  mov     [rbp+var_50], rax
0x180029a98  mov     [rbp+var_48], r15
0x180029a9c  mov     rax, [rcx]
0x180029a9f  lea     r8, [rbp+var_48]
0x180029aa3  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180029aaa  mov     rax, [rax]
0x180029aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ab2  mov     edi, eax
0x180029ab4  mov     rdx, [rbp+var_48]; struct IInspectable *
0x180029ab8  mov     rcx, [rbp+var_50]; this
0x180029abc  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x180029ac1  nop
0x180029ac2  test    edi, edi
0x180029ac4  js      loc_180029BA9
0x180029aca  mov     ecx, r15d
0x180029acd  mov     [rbp+var_10], ecx
0x180029ad0  mov     edi, [rbp+var_20]
0x180029ad3  test    edi, edi
0x180029ad5  js      loc_180029BA9
0x180029adb  mov     ebx, 2
0x180029ae0  jz      short loc_180029B14
0x180029ae2  sub     edi, 1
0x180029ae5  jz      loc_180029D9D
0x180029aeb  cmp     edi, ebx
0x180029aed  jz      loc_180029D9D
0x180029af3  mov     rcx, [rbp+var_28]
0x180029af7  mov     rax, [rcx]
0x180029afa  lea     rdx, [rbp+var_10]
0x180029afe  mov     rax, [rax+30h]
0x180029b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b07  mov     edi, eax
0x180029b09  test    eax, eax
0x180029b0b  js      loc_180029BA9
0x180029b11  mov     ecx, [rbp+var_10]
0x180029b14  mov     eax, 401h
0x180029b19  cmp     ecx, eax
0x180029b1b  jg      loc_18002A0C1
0x180029b21  jz      loc_18002A064
0x180029b27  cmp     ecx, 8
0x180029b2a  jle     loc_180029BEF
0x180029b30  sub     ecx, 9
0x180029b33  jz      loc_18002A023
0x180029b39  sub     ecx, 1
0x180029b3c  jz      loc_180029E35
0x180029b42  sub     ecx, 1
0x180029b45  jz      loc_180029FE4
0x180029b4b  sub     ecx, 1
0x180029b4e  jnz     loc_180029C8B
0x180029b54  mov     [rbp+string], r15
0x180029b58  mov     rax, [rbp+var_28]
0x180029b5c  mov     [rbp+var_50], rax
0x180029b60  mov     eax, [rbp+var_20]
0x180029b63  mov     dword ptr [rbp+var_48], eax
0x180029b66  xor     ecx, ecx; string
0x180029b68  call    cs:__imp_WindowsDeleteString
0x180029b6e  mov     [rbp+string], r15
0x180029b72  lea     rdx, [rbp+string]; HSTRING *
0x180029b76  lea     rcx, [rbp+var_50]; this
0x180029b7a  call    ?GetString@Accessor@RoVariant@@QEBAJPEAPEAUHSTRING__@@@Z; RoVariant::Accessor::GetString(HSTRING__ * *)
0x180029b7f  mov     edi, eax
0x180029b81  test    eax, eax
0x180029b83  js      short loc_180029B9E
0x180029b85  xor     edx, edx; length
0x180029b87  mov     rcx, [rbp+string]; string
0x180029b8b  call    cs:__imp_WindowsGetStringRawBuffer
0x180029b91  mov     rdx, rsi; struct tagPROPVARIANT *
0x180029b94  mov     rcx, rax; Src
0x180029b97  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180029b9c  mov     edi, eax
0x180029b9e  mov     rcx, [rbp+string]; string
0x180029ba2  call    cs:__imp_WindowsDeleteString
0x180029ba8  nop
0x180029ba9  mov     rcx, [rbp+var_28]
0x180029bad  test    rcx, rcx
0x180029bb0  jnz     short loc_180029BD4
0x180029bb2  mov     eax, edi
0x180029bb4  mov     rcx, [rbp+var_8]
0x180029bb8  xor     rcx, rsp; StackCookie
0x180029bbb  call    __security_check_cookie
0x180029bc0  mov     rbx, [rsp+70h+arg_10]
0x180029bc8  add     rsp, 70h
0x180029bcc  pop     r15
0x180029bce  pop     r14
0x180029bd0  pop     rdi
0x180029bd1  pop     rsi
0x180029bd2  pop     rbp
0x180029bd3  retn
0x180029bd4  mov     eax, [rbp+var_20]
0x180029bd7  add     eax, 0FFFFFFFDh
0x180029bda  test    eax, 0FFFFFFFBh
0x180029bdf  jnz     short loc_180029BB2
0x180029be1  mov     rax, [rcx]
0x180029be4  mov     rax, [rax+10h]
0x180029be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bed  jmp     short loc_180029BB2
0x180029bef  jz      loc_180029ED9
0x180029bf5  test    ecx, ecx
0x180029bf7  jz      loc_180029C83
0x180029bfd  sub     ecx, 1
0x180029c00  jz      loc_180029EA0
0x180029c06  sub     ecx, 1
0x180029c09  jz      loc_180029E66
0x180029c0f  sub     ecx, 1
0x180029c12  jz      loc_180029E13
0x180029c18  sub     ecx, 1
0x180029c1b  jz      loc_180029DDA
0x180029c21  sub     ecx, 1
0x180029c24  jz      loc_180029DAA
0x180029c2a  sub     ecx, 1
0x180029c2d  jnz     loc_180029D20
0x180029c33  mov     rax, [rbp+var_28]
0x180029c37  mov     [rbp+var_50], rax
0x180029c3b  mov     eax, [rbp+var_20]
0x180029c3e  mov     dword ptr [rbp+var_48], eax
0x180029c41  mov     qword ptr [rbp+clsid.Data1], r15
0x180029c45  lea     rcx, [rbp+var_50]; this
0x180029c49  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180029c4e  mov     edi, eax
0x180029c50  test    eax, eax
0x180029c52  js      loc_180029BA9
0x180029c58  mov     rcx, [rbp+var_28]
0x180029c5c  mov     rax, [rcx]
0x180029c5f  lea     rdx, [rbp+clsid]
0x180029c63  mov     rax, [rax+68h]
0x180029c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c6c  mov     edi, eax
0x180029c6e  test    eax, eax
0x180029c70  js      loc_180029BA9
0x180029c76  mov     word ptr [rsi], 14h
0x180029c7b  mov     rax, qword ptr [rbp+clsid.Data1]
0x180029c7f  mov     [rsi+8], rax
0x180029c83  mov     edi, r15d
0x180029c86  jmp     loc_180029BA9
0x180029c8b  sub     ecx, 1
0x180029c8e  jz      loc_180029F6A
0x180029c94  sub     ecx, 1
0x180029c97  jnz     loc_180029F19
0x180029c9d  mov     rax, [rbp+var_28]
0x180029ca1  mov     [rbp+var_50], rax
0x180029ca5  mov     eax, [rbp+var_20]
0x180029ca8  mov     dword ptr [rbp+var_48], eax
0x180029cab  mov     qword ptr [rbp+clsid.Data1], r15
0x180029caf  lea     rcx, [rbp+var_50]; this
0x180029cb3  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180029cb8  mov     edi, eax
0x180029cba  test    eax, eax
0x180029cbc  js      loc_180029BA9
0x180029cc2  mov     rcx, [rbp+var_28]
0x180029cc6  mov     rax, [rcx]
0x180029cc9  lea     rdx, [rbp+clsid]
0x180029ccd  mov     rax, [rax+0A8h]
0x180029cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cd9  mov     edi, eax
0x180029cdb  test    eax, eax
0x180029cdd  js      loc_180029BA9
0x180029ce3  mov     rax, qword ptr [rbp+clsid.Data1]
0x180029ce7  test    rax, rax
0x180029cea  js      loc_180029F60
0x180029cf0  mov     dword ptr [rbp+var_18], eax
0x180029cf3  sar     rax, 20h
0x180029cf7  mov     dword ptr [rbp+var_18+4], eax
0x180029cfa  lea     r8, [rsi+8]
0x180029cfe  xor     r9d, r9d
0x180029d01  xor     edx, edx
0x180029d03  lea     rcx, [rbp+var_18]
0x180029d07  call    ?SHConvertTime@@YAJPEBU_FILETIME@@W4SHTIME_FLAGS@@PEAU1@1@Z; SHConvertTime(_FILETIME const *,SHTIME_FLAGS,_FILETIME *,SHTIME_FLAGS)
0x180029d0c  mov     edi, eax
0x180029d0e  test    eax, eax
0x180029d10  js      loc_180029BA9
0x180029d16  mov     word ptr [rsi], 40h ; '@'
0x180029d1b  jmp     loc_180029BA9
0x180029d20  cmp     ecx, 1
0x180029d23  jnz     loc_18002A407
0x180029d29  mov     rax, [rbp+var_28]
0x180029d2d  mov     [rbp+var_50], rax
0x180029d31  mov     eax, [rbp+var_20]
0x180029d34  mov     dword ptr [rbp+var_48], eax
0x180029d37  mov     qword ptr [rbp+clsid.Data1], r15
0x180029d3b  lea     rcx, [rbp+var_50]; this
0x180029d3f  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180029d44  mov     edi, eax
0x180029d46  test    eax, eax
0x180029d48  js      loc_180029BA9
0x180029d4e  mov     rcx, [rbp+var_28]
0x180029d52  mov     rax, [rcx]
0x180029d55  lea     rdx, [rbp+clsid]
0x180029d59  mov     rax, [rax+70h]
0x180029d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d62  mov     edi, eax
0x180029d64  test    eax, eax
0x180029d66  js      loc_180029BA9
0x180029d6c  mov     word ptr [rsi], 15h
0x180029d71  jmp     loc_180029C7B
0x180029d76  mov     edx, ecx
0x180029d78  mov     rax, [rbp+var_18]
0x180029d7c  mov     rax, [rax+rdx*8]
0x180029d80  test    rax, rax
0x180029d83  js      loc_18002A411
0x180029d89  mov     [r9+rdx*8], eax
0x180029d8d  sar     rax, 20h
0x180029d91  mov     [r9+rdx*8+4], eax
0x180029d96  inc     ecx
0x180029d98  jmp     loc_18002A3ED
0x180029d9d  mov     ecx, 0Dh
0x180029da2  mov     [rbp+var_10], ecx
0x180029da5  jmp     loc_180029B14
0x180029daa  mov     dword ptr [rbp+string], r15d
0x180029dae  mov     rax, [rbp+var_28]
0x180029db2  mov     [rbp+var_50], rax
0x180029db6  mov     eax, [rbp+var_20]
0x180029db9  mov     dword ptr [rbp+var_48], eax
0x180029dbc  lea     rdx, [rbp+string]; unsigned int *
0x180029dc0  lea     rcx, [rbp+var_50]; this
0x180029dc4  call    ?GetUInt32@Accessor@RoVariant@@QEBAJPEAI@Z; RoVariant::Accessor::GetUInt32(uint *)
0x180029dc9  mov     edi, eax
0x180029dcb  test    eax, eax
0x180029dcd  js      loc_180029BA9
0x180029dd3  mov     word ptr [rsi], 13h
0x180029dd8  jmp     short loc_180029E08
0x180029dda  mov     dword ptr [rbp+string], r15d
0x180029dde  mov     rax, [rbp+var_28]
0x180029de2  mov     [rbp+var_50], rax
0x180029de6  mov     eax, [rbp+var_20]
0x180029de9  mov     dword ptr [rbp+var_48], eax
0x180029dec  lea     rdx, [rbp+string]; int *
0x180029df0  lea     rcx, [rbp+var_50]; this
0x180029df4  call    ?GetInt32@Accessor@RoVariant@@QEBAJPEAH@Z; RoVariant::Accessor::GetInt32(int *)
0x180029df9  mov     edi, eax
0x180029dfb  test    eax, eax
0x180029dfd  js      loc_180029BA9
0x180029e03  mov     word ptr [rsi], 3
0x180029e08  mov     eax, dword ptr [rbp+string]
0x180029e0b  mov     [rsi+8], eax
0x180029e0e  jmp     loc_180029C83
0x180029e13  mov     word ptr [rbp+string], r15w
0x180029e18  mov     rax, [rbp+var_28]
0x180029e1c  mov     [rbp+var_50], rax
0x180029e20  mov     eax, [rbp+var_20]
0x180029e23  mov     dword ptr [rbp+var_48], eax
0x180029e26  lea     rdx, [rbp+string]; unsigned __int16 *
0x180029e2a  lea     rcx, [rbp+var_50]; this
0x180029e2e  call    ?GetUInt16@Accessor@RoVariant@@QEBAJPEAG@Z; RoVariant::Accessor::GetUInt16(ushort *)
0x180029e33  jmp     short loc_180029E55
0x180029e35  mov     word ptr [rbp+string], r15w
0x180029e3a  mov     rax, [rbp+var_28]
0x180029e3e  mov     [rbp+var_50], rax
0x180029e42  mov     eax, [rbp+var_20]
0x180029e45  mov     dword ptr [rbp+var_48], eax
0x180029e48  lea     rdx, [rbp+string]; unsigned __int16 *
0x180029e4c  lea     rcx, [rbp+var_50]; this
0x180029e50  call    ?GetChar16@Accessor@RoVariant@@QEBAJPEAG@Z; RoVariant::Accessor::GetChar16(ushort *)
0x180029e55  mov     edi, eax
0x180029e57  test    eax, eax
0x180029e59  js      loc_180029BA9
0x180029e5f  mov     word ptr [rsi], 12h
0x180029e64  jmp     short loc_180029E93
0x180029e66  mov     word ptr [rbp+string], r15w
0x180029e6b  mov     rax, [rbp+var_28]
0x180029e6f  mov     [rbp+var_50], rax
0x180029e73  mov     eax, [rbp+var_20]
0x180029e76  mov     dword ptr [rbp+var_48], eax
0x180029e79  lea     rdx, [rbp+string]; __int16 *
0x180029e7d  lea     rcx, [rbp+var_50]; this
0x180029e81  call    ?GetInt16@Accessor@RoVariant@@QEBAJPEAF@Z; RoVariant::Accessor::GetInt16(short *)
0x180029e86  mov     edi, eax
0x180029e88  test    eax, eax
0x180029e8a  js      loc_180029BA9
0x180029e90  mov     [rsi], bx
0x180029e93  movzx   eax, word ptr [rbp+string]
0x180029e97  mov     [rsi+8], ax
0x180029e9b  jmp     loc_180029C83
0x180029ea0  mov     byte ptr [rbp+string], r15b
0x180029ea4  mov     rax, [rbp+var_28]
0x180029ea8  mov     [rbp+var_50], rax
0x180029eac  mov     eax, [rbp+var_20]
0x180029eaf  mov     dword ptr [rbp+var_48], eax
0x180029eb2  lea     rdx, [rbp+string]; unsigned __int8 *
0x180029eb6  lea     rcx, [rbp+var_50]; this
  ... truncated ...
```
