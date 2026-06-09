# CUMRDPConnection::GetPropertyAudioEnumDllName(__PROPERTY_VALUE *)

- ea: `0x18001f528`
- end: `0x18001ff09`
- name: `?GetPropertyAudioEnumDllName@CUMRDPConnection@@IEAAJPEAU__PROPERTY_VALUE@@@Z`
- size: `2529`
- prototype: `__int64 __fastcall(CUMRDPConnection *this, struct __PROPERTY_VALUE *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180021bd0`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x18000e420`
- `0x180012200`
- `0x18001569c`
- `0x1800173e4`
- `0x18001f528`
- `0x18002e4e0`
- `0x180033da0`
- `0x1800446bc`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f7d2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f800`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f819`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f832`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f7d2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f800`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f819`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f832`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fb43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fb43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fedd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fedd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fa67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fa67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fe1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fe1a`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001f58f`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18001f58f`

## string_xrefs

- `0x18001f604`: `GetPropertyAudioEnumDllName`
- `0x18001f6ae`: `GetPropertyAudioEnumDllName`
- `0x18001f763`: `GetPropertyAudioEnumDllName`
- `0x18001f88b`: `GetPropertyAudioEnumDllName`
- `0x18001f93a`: `GetPropertyAudioEnumDllName`
- `0x18001f9e6`: `GetPropertyAudioEnumDllName`
- `0x18001fab8`: `GetPropertyAudioEnumDllName`
- `0x18001fb94`: `GetPropertyAudioEnumDllName`
- `0x18001fc35`: `GetPropertyAudioEnumDllName`
- `0x18001fce7`: `GetPropertyAudioEnumDllName`
- `0x18001fd97`: `GetPropertyAudioEnumDllName`
- `0x18001fe5b`: `GetPropertyAudioEnumDllName`
- `0x18001fc9c`: `rdpendp.dll`
- `0x18001fccc`: `StringCbCopy`
- `0x18001f870`: `StringCchCopy`
- `0x18001fa9d`: `RegOpenKeyEx`
- `0x18001fb37`: `AudioEnumeratorDll`

## pseudocode

```c
__int64 __fastcall CUMRDPConnection::GetPropertyAudioEnumDllName(
        CUMRDPConnection *this,
        struct __PROPERTY_VALUE *a2,
        __int64 a3)
{
  char *v4; // rcx
  bool v6; // zf
  __int64 v7; // rbx
  __int64 v8; // rdx
  int v9; // ecx
  __int64 v10; // r8
  int v11; // r9d
  signed int v12; // ebx
  int v13; // r9d
  int v14; // ecx
  int v15; // r9d
  int v16; // ecx
  int v17; // r9d
  int v18; // ecx
  int v19; // r9d
  LSTATUS v20; // eax
  int v21; // ecx
  int v22; // r9d
  LSTATUS v23; // eax
  int v24; // ecx
  int v25; // r9d
  int v26; // ecx
  int v27; // r9d
  int v28; // ecx
  int v29; // r9d
  int v30; // ecx
  HLOCAL v31; // rax
  int v32; // ecx
  int v33; // r9d
  unsigned __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  char *v36; // [rsp+58h] [rbp-A8h] BYREF
  const char *v37; // [rsp+60h] [rbp-A0h] BYREF
  const char *v38; // [rsp+68h] [rbp-98h] BYREF
  const char *v39; // [rsp+70h] [rbp-90h] BYREF
  const char *v40; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v45[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 Data[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  cbData = 520;
  v4 = (char *)this + 152;
  hKey = 0;
  Type = 0;
  v35 = 0;
  v43 = 0;
  v6 = *((_DWORD *)v4 + 2) == 0;
  v36 = v4;
  if ( !v6 )
    PAL_System_CritSecEnter(*(_QWORD *)v4, a2, a3);
  if ( *((_QWORD *)this + 36) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v43, a2, a3);
    v7 = *((_QWORD *)this + 36);
    v43 = v7;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v43);
  }
  else
  {
    v7 = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v36);
  if ( !a2 )
  {
    v12 = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v36) = 4289;
      v37 = "pProperty is NULL";
      LODWORD(v35) = -2147024809;
      v38 = "GetPropertyAudioEnumDllName";
      v39 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v40 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)byte_1801953FD,
        v10,
        v11,
        (__int64)&v40,
        (__int64)&v35,
        (__int64)&v39,
        (__int64)&v36,
        (__int64)&v38,
        (__int64)&v37);
    }
    goto LABEL_55;
  }
  if ( !v7 )
  {
    v12 = -2147019873;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v35) = 4294;
      v40 = "m_spListener is NULL";
      LODWORD(v36) = -2147019873;
      v39 = "GetPropertyAudioEnumDllName";
      v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v37 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)&dword_1801953AC,
        v10,
        v11,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v38,
        (__int64)&v35,
        (__int64)&v39,
        (__int64)&v40);
    }
    goto LABEL_55;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64))(*(_QWORD *)v7 + 32LL))(v7, v45, 32);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v35) = 4298;
      v40 = "m_spListener->GetListenerName";
      LODWORD(v36) = v12;
      v39 = "GetPropertyAudioEnumDllName";
      v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v37 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)byte_18019535B,
        v10,
        v13,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v38,
        (__int64)&v35,
        (__int64)&v39,
        (__int64)&v40);
    }
    goto LABEL_55;
  }
  if ( (unsigned int)_o__wcsicmp(v45, L"7A78855482A04FA781DC")
    && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
     || (unsigned int)_o__wcsicmp(v45, L"D8D584DCE21F4BD4B923"))
    && (unsigned int)_o__wcsicmp(v45, L"31C5CE94259D4006A9E4")
    && (unsigned int)_o__wcsicmp(v45, L"41C5CE94259D4006A9E4") )
  {
    v12 = StringCchCopyW(SubKey, 0x104u, L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations");
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v35) = 4321;
        v40 = "StringCchCopy";
        LODWORD(v36) = v12;
        v39 = "GetPropertyAudioEnumDllName";
        v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v37 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v14,
          (unsigned int)byte_1801952B9,
          v10,
          v15,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v39,
          (__int64)&v40);
      }
      goto LABEL_55;
    }
    v12 = StringCchCatW(SubKey, 0x104u, L"\\");
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v35) = 4324;
        v40 = "StringCchCat 1";
        LODWORD(v36) = v12;
        v39 = "GetPropertyAudioEnumDllName";
        v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v37 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v16,
          (unsigned int)qword_180195268,
          v10,
          v17,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v39,
          (__int64)&v40);
      }
      goto LABEL_55;
    }
    v12 = StringCchCatW(SubKey, 0x104u, v45);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v35) = 4327;
        v40 = "StringCchCat 2";
        LODWORD(v36) = v12;
        v39 = "GetPropertyAudioEnumDllName";
        v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v37 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v18,
          (unsigned int)&byte_180195217,
          v10,
          v19,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v39,
          (__int64)&v40);
      }
      goto LABEL_55;
    }
    v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
    v12 = v20;
    if ( v20 )
    {
      if ( v20 > 0 )
        v12 = (unsigned __int16)v20 | 0x80070000;
      if ( v12 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v35) = 4340;
          v40 = "RegOpenKeyEx";
          LODWORD(v36) = v12;
          v39 = "GetPropertyAudioEnumDllName";
          v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          v37 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v21,
            (unsigned int)&word_1801951C6,
            v10,
            v22,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v38,
            (__int64)&v35,
            (__int64)&v39,
            (__int64)&v40);
        }
        goto LABEL_55;
      }
    }
    v23 = RegQueryValueExW(hKey, L"AudioEnumeratorDll", 0, &Type, (LPBYTE)Data, &cbData);
    v12 = v23;
    if ( v23 )
    {
      if ( v23 > 0 )
        v12 = (unsigned __int16)v23 | 0x80070000;
      if ( v12 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v35) = 4352;
          v40 = "RegQueryValueEx";
          LODWORD(v36) = v12;
          v39 = "GetPropertyAudioEnumDllName";
          v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          v37 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v24,
            (unsigned int)byte_180195175,
            v10,
            v25,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v38,
            (__int64)&v35,
            (__int64)&v39,
            (__int64)&v40);
        }
        goto LABEL_55;
      }
    }
    if ( Type != 1 )
    {
      v12 = -2147023728;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v35) = 4357;
        v40 = "Invalid returned type be RegQueryValueEx";
        LODWORD(v36) = -2147023728;
        v39 = "GetPropertyAudioEnumDllName";
        v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v37 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v24,
          (unsigned int)&dword_180195124,
          v10,
          v25,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v39,
          (__int64)&v40);
      }
      goto LABEL_55;
    }
    goto LABEL_48;
  }
  v12 = StringCbCopyW(Data, cbData, L"rdpendp.dll");
  if ( v12 >= 0 )
  {
LABEL_48:
    v12 = StringCchLengthW(Data, 0x104u, &v35);
    if ( v12 >= 0 )
    {
      v30 = v35;
      *(_WORD *)a2 = 2;
      *((_DWORD *)a2 + 2) = v30 + 1;
      cbData = 2 * v30 + 2;
      v31 = LocalAlloc(0x40u, cbData);
      *((_QWORD *)a2 + 2) = v31;
      if ( v31 )
      {
        memcpy_0(v31, Data, cbData);
        v12 = 0;
      }
      else
      {
        v12 = -2147024882;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v35) = 4372;
          v40 = "LocalAlloc";
          LODWORD(v36) = -2147024882;
          v39 = "GetPropertyAudioEnumDllName";
          v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          v37 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v32,
            (unsigned int)word_180195082,
            v10,
            v33,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v38,
            (__int64)&v35,
            (__int64)&v39,
            (__int64)&v40);
        }
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v35) = 4363;
      v40 = "StringCchLength";
      LODWORD(v36) = v12;
      v39 = "GetPropertyAudioEnumDllName";
      v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v37 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v28,
        (unsigned int)byte_1801950D3,
        v10,
        v29,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v38,
        (__int64)&v35,
        (__int64)&v39,
        (__int64)&v40);
    }
    goto LABEL_55;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    LODWORD(v35) = 4313;
    v40 = "StringCbCopy";
    LODWORD(v36) = v12;
    v39 = "GetPropertyAudioEnumDllName";
    v38 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
    v37 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v26,
      (unsigned int)word_18019530A,
      v10,
      v27,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v38,
      (__int64)&v35,
      (__int64)&v39,
      (__int64)&v40);
  }
LABEL_55:
  if ( hKey )
    RegCloseKey(hKey);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v43, v8, v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001f528  push    rbp
0x18001f52a  push    rbx
0x18001f52b  push    rsi
0x18001f52c  push    rdi
0x18001f52d  lea     rbp, [rsp-418h]
0x18001f535  sub     rsp, 518h
0x18001f53c  mov     rax, cs:__security_cookie
0x18001f543  xor     rax, rsp
0x18001f546  mov     [rbp+430h+var_30], rax
0x18001f54d  mov     rbx, rcx
0x18001f550  mov     [rbp+430h+cbData], 208h
0x18001f557  add     rcx, 98h
0x18001f55e  mov     [rbp+430h+hKey], 0
0x18001f566  mov     [rbp+430h+Type], 0
0x18001f56d  mov     rsi, rdx
0x18001f570  mov     [rsp+530h+var_4E0], 0
0x18001f579  mov     [rbp+430h+var_4A8], 0
0x18001f581  cmp     dword ptr [rcx+8], 0
0x18001f585  mov     [rsp+530h+var_4D8], rcx
0x18001f58a  jz      short loc_18001F595
0x18001f58c  mov     rcx, [rcx]
0x18001f58f  call    cs:__imp_PAL_System_CritSecEnter
0x18001f595  cmp     qword ptr [rbx+120h], 0
0x18001f59d  jnz     short loc_18001F5A3
0x18001f59f  xor     ebx, ebx
0x18001f5a1  jmp     short loc_18001F5C0
0x18001f5a3  lea     rcx, [rbp+430h+var_4A8]
0x18001f5a7  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18001f5ac  mov     rbx, [rbx+120h]
0x18001f5b3  lea     rcx, [rbp+430h+var_4A8]
0x18001f5b7  mov     [rbp+430h+var_4A8], rbx
0x18001f5bb  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18001f5c0  lea     rcx, [rsp+530h+var_4D8]; this
0x18001f5c5  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18001f5ca  test    rsi, rsi
0x18001f5cd  jnz     loc_18001F672
0x18001f5d3  mov     eax, cs:dword_1801B76C8
0x18001f5d9  lea     edi, [rsi+2]
0x18001f5dc  mov     ebx, 80070057h
0x18001f5e1  cmp     eax, edi
0x18001f5e3  jbe     loc_18001FED4
0x18001f5e9  lea     rax, aPpropertyIsNul; "pProperty is NULL"
0x18001f5f0  mov     dword ptr [rsp+530h+var_4D8], 10C1h
0x18001f5f8  mov     [rsp+530h+var_4D0], rax
0x18001f5fd  lea     rdx, byte_1801953FD
0x18001f604  lea     rax, aGetpropertyaud; "GetPropertyAudioEnumDllName"
0x18001f60b  mov     dword ptr [rsp+530h+var_4E0], ebx
0x18001f60f  mov     [rsp+530h+var_4C8], rax
0x18001f614  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f61b  mov     [rsp+530h+var_4C0], rax
0x18001f620  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f627  mov     [rsp+530h+var_4B8], rax
0x18001f62c  lea     rax, [rsp+530h+var_4D0]
0x18001f631  mov     [rsp+530h+var_4E8], rax
0x18001f636  lea     rax, [rsp+530h+var_4C8]
0x18001f63b  mov     [rsp+530h+var_4F0], rax
0x18001f640  lea     rax, [rsp+530h+var_4D8]
0x18001f645  mov     [rsp+530h+var_4F8], rax
0x18001f64a  lea     rax, [rsp+530h+var_4C0]
0x18001f64f  mov     [rsp+530h+var_500], rax
0x18001f654  lea     rax, [rsp+530h+var_4E0]
0x18001f659  mov     [rsp+530h+lpcbData], rax
0x18001f65e  lea     rax, [rsp+530h+var_4B8]
0x18001f663  mov     [rsp+530h+phkResult], rax
0x18001f668  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001f66d  jmp     loc_18001FED4
0x18001f672  test    rbx, rbx
0x18001f675  jnz     loc_18001F712
0x18001f67b  mov     eax, cs:dword_1801B76C8
0x18001f681  mov     edi, 2
0x18001f686  mov     ebx, 8007139Fh
0x18001f68b  cmp     eax, edi
0x18001f68d  jbe     loc_18001FED4
0x18001f693  lea     rax, aMSplistenerIsN; "m_spListener is NULL"
0x18001f69a  mov     dword ptr [rsp+530h+var_4E0], 10C6h
0x18001f6a2  mov     [rsp+530h+var_4B8], rax
0x18001f6a7  lea     rdx, dword_1801953AC
0x18001f6ae  lea     rax, aGetpropertyaud; "GetPropertyAudioEnumDllName"
0x18001f6b5  mov     dword ptr [rsp+530h+var_4D8], ebx
0x18001f6b9  mov     [rsp+530h+var_4C0], rax
0x18001f6be  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f6c5  mov     [rsp+530h+var_4C8], rax
0x18001f6ca  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f6d1  mov     [rsp+530h+var_4D0], rax
0x18001f6d6  lea     rax, [rsp+530h+var_4B8]
0x18001f6db  mov     [rsp+530h+var_4E8], rax
0x18001f6e0  lea     rax, [rsp+530h+var_4C0]
0x18001f6e5  mov     [rsp+530h+var_4F0], rax
0x18001f6ea  lea     rax, [rsp+530h+var_4E0]
0x18001f6ef  mov     [rsp+530h+var_4F8], rax
0x18001f6f4  lea     rax, [rsp+530h+var_4C8]
0x18001f6f9  mov     [rsp+530h+var_500], rax
0x18001f6fe  lea     rax, [rsp+530h+var_4D8]
0x18001f703  mov     [rsp+530h+lpcbData], rax
0x18001f708  lea     rax, [rsp+530h+var_4D0]
0x18001f70d  jmp     loc_18001F663
0x18001f712  mov     rax, [rbx]
0x18001f715  lea     rdx, [rbp+430h+var_490]
0x18001f719  mov     r8d, 20h ; ' '
0x18001f71f  mov     rcx, rbx
0x18001f722  mov     rax, [rax+20h]
0x18001f726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f72b  mov     ebx, eax
0x18001f72d  test    eax, eax
0x18001f72f  jns     loc_18001F7C7
0x18001f735  mov     ecx, cs:dword_1801B76C8
0x18001f73b  mov     edi, 2
0x18001f740  cmp     ecx, edi
0x18001f742  jbe     loc_18001FED4
0x18001f748  lea     rax, aMSplistenerGet; "m_spListener->GetListenerName"
0x18001f74f  mov     dword ptr [rsp+530h+var_4E0], 10CAh
0x18001f757  mov     [rsp+530h+var_4B8], rax
0x18001f75c  lea     rdx, byte_18019535B
0x18001f763  lea     rax, aGetpropertyaud; "GetPropertyAudioEnumDllName"
0x18001f76a  mov     dword ptr [rsp+530h+var_4D8], ebx
0x18001f76e  mov     [rsp+530h+var_4C0], rax
0x18001f773  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f77a  mov     [rsp+530h+var_4C8], rax
0x18001f77f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f786  mov     [rsp+530h+var_4D0], rax
0x18001f78b  lea     rax, [rsp+530h+var_4B8]
0x18001f790  mov     [rsp+530h+var_4E8], rax
0x18001f795  lea     rax, [rsp+530h+var_4C0]
0x18001f79a  mov     [rsp+530h+var_4F0], rax
0x18001f79f  lea     rax, [rsp+530h+var_4E0]
0x18001f7a4  mov     [rsp+530h+var_4F8], rax
0x18001f7a9  lea     rax, [rsp+530h+var_4C8]
0x18001f7ae  mov     [rsp+530h+var_500], rax
0x18001f7b3  lea     rax, [rsp+530h+var_4D8]
0x18001f7b8  mov     [rsp+530h+lpcbData], rax
0x18001f7bd  lea     rax, [rsp+530h+var_4D0]
0x18001f7c2  jmp     loc_18001F663
0x18001f7c7  lea     rdx, a7a78855482a04f; "7A78855482A04FA781DC"
0x18001f7ce  lea     rcx, [rbp+430h+var_490]
0x18001f7d2  call    cs:__imp__o__wcsicmp
0x18001f7d8  mov     edi, 104h
0x18001f7dd  test    eax, eax
0x18001f7df  jz      loc_18001FC99
0x18001f7e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18001f7ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18001f7f1  test    al, al
0x18001f7f3  jz      short loc_18001F80E
0x18001f7f5  lea     rdx, aD8d584dce21f4b; "D8D584DCE21F4BD4B923"
0x18001f7fc  lea     rcx, [rbp+430h+var_490]
0x18001f800  call    cs:__imp__o__wcsicmp
0x18001f806  test    eax, eax
0x18001f808  jz      loc_18001FC99
0x18001f80e  lea     rdx, a31c5ce94259d40; "31C5CE94259D4006A9E4"
0x18001f815  lea     rcx, [rbp+430h+var_490]
0x18001f819  call    cs:__imp__o__wcsicmp
0x18001f81f  test    eax, eax
0x18001f821  jz      loc_18001FC99
0x18001f827  lea     rdx, a41c5ce94259d40; "41C5CE94259D4006A9E4"
0x18001f82e  lea     rcx, [rbp+430h+var_490]
0x18001f832  call    cs:__imp__o__wcsicmp
0x18001f838  test    eax, eax
0x18001f83a  jz      loc_18001FC99
0x18001f840  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x18001f847  mov     rdx, rdi; unsigned __int64
0x18001f84a  lea     rcx, [rbp+430h+SubKey]; unsigned __int16 *
0x18001f84e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f853  mov     ebx, eax
0x18001f855  test    eax, eax
0x18001f857  jns     loc_18001F8EF
0x18001f85d  mov     eax, cs:dword_1801B76C8
0x18001f863  mov     edi, 2
0x18001f868  cmp     eax, edi
0x18001f86a  jbe     loc_18001FED4
0x18001f870  lea     rax, aStringcchcopy; "StringCchCopy"
0x18001f877  mov     dword ptr [rsp+530h+var_4E0], 10E1h
0x18001f87f  mov     [rsp+530h+var_4B8], rax
0x18001f884  lea     rdx, byte_1801952B9
0x18001f88b  lea     rax, aGetpropertyaud; "GetPropertyAudioEnumDllName"
0x18001f892  mov     dword ptr [rsp+530h+var_4D8], ebx
0x18001f896  mov     [rsp+530h+var_4C0], rax
0x18001f89b  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f8a2  mov     [rsp+530h+var_4C8], rax
0x18001f8a7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f8ae  mov     [rsp+530h+var_4D0], rax
0x18001f8b3  lea     rax, [rsp+530h+var_4B8]
0x18001f8b8  mov     [rsp+530h+var_4E8], rax
0x18001f8bd  lea     rax, [rsp+530h+var_4C0]
0x18001f8c2  mov     [rsp+530h+var_4F0], rax
0x18001f8c7  lea     rax, [rsp+530h+var_4E0]
0x18001f8cc  mov     [rsp+530h+var_4F8], rax
0x18001f8d1  lea     rax, [rsp+530h+var_4C8]
0x18001f8d6  mov     [rsp+530h+var_500], rax
0x18001f8db  lea     rax, [rsp+530h+var_4D8]
0x18001f8e0  mov     [rsp+530h+lpcbData], rax
0x18001f8e5  lea     rax, [rsp+530h+var_4D0]
0x18001f8ea  jmp     loc_18001F663
0x18001f8ef  lea     r8, asc_180158700; "\\"
0x18001f8f6  mov     rdx, rdi; unsigned __int64
0x18001f8f9  lea     rcx, [rbp+430h+SubKey]; unsigned __int16 *
0x18001f8fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f902  mov     ebx, eax
0x18001f904  test    eax, eax
0x18001f906  jns     loc_18001F99E
0x18001f90c  mov     eax, cs:dword_1801B76C8
0x18001f912  mov     edi, 2
0x18001f917  cmp     eax, edi
0x18001f919  jbe     loc_18001FED4
0x18001f91f  lea     rax, aStringcchcat1; "StringCchCat 1"
0x18001f926  mov     dword ptr [rsp+530h+var_4E0], 10E4h
0x18001f92e  mov     [rsp+530h+var_4B8], rax
0x18001f933  lea     rdx, qword_180195268
0x18001f93a  lea     rax, aGetpropertyaud; "GetPropertyAudioEnumDllName"
0x18001f941  mov     dword ptr [rsp+530h+var_4D8], ebx
0x18001f945  mov     [rsp+530h+var_4C0], rax
0x18001f94a  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f951  mov     [rsp+530h+var_4C8], rax
0x18001f956  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001f95d  mov     [rsp+530h+var_4D0], rax
0x18001f962  lea     rax, [rsp+530h+var_4B8]
0x18001f967  mov     [rsp+530h+var_4E8], rax
0x18001f96c  lea     rax, [rsp+530h+var_4C0]
0x18001f971  mov     [rsp+530h+var_4F0], rax
0x18001f976  lea     rax, [rsp+530h+var_4E0]
0x18001f97b  mov     [rsp+530h+var_4F8], rax
0x18001f980  lea     rax, [rsp+530h+var_4C8]
0x18001f985  mov     [rsp+530h+var_500], rax
0x18001f98a  lea     rax, [rsp+530h+var_4D8]
0x18001f98f  mov     [rsp+530h+lpcbData], rax
0x18001f994  lea     rax, [rsp+530h+var_4D0]
0x18001f999  jmp     loc_18001F663
0x18001f99e  lea     r8, [rbp+430h+var_490]; unsigned __int16 *
0x18001f9a2  mov     rdx, rdi; unsigned __int64
0x18001f9a5  lea     rcx, [rbp+430h+SubKey]; unsigned __int16 *
0x18001f9a9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f9ae  mov     ebx, eax
0x18001f9b0  test    eax, eax
0x18001f9b2  jns     loc_18001FA4A
0x18001f9b8  mov     eax, cs:dword_1801B76C8
0x18001f9be  mov     edi, 2
0x18001f9c3  cmp     eax, edi
0x18001f9c5  jbe     loc_18001FED4
0x18001f9cb  lea     rax, aStringcchcat2; "StringCchCat 2"
0x18001f9d2  mov     dword ptr [rsp+530h+var_4E0], 10E7h
0x18001f9da  mov     [rsp+530h+var_4B8], rax
0x18001f9df  lea     rdx, byte_180195217
0x18001f9e6  lea     rax, aGetpropertyaud; "GetPropertyAudioEnumDllName"
0x18001f9ed  mov     dword ptr [rsp+530h+var_4D8], ebx
0x18001f9f1  mov     [rsp+530h+var_4C0], rax
0x18001f9f6  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001f9fd  mov     [rsp+530h+var_4C8], rax
0x18001fa02  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001fa09  mov     [rsp+530h+var_4D0], rax
0x18001fa0e  lea     rax, [rsp+530h+var_4B8]
0x18001fa13  mov     [rsp+530h+var_4E8], rax
0x18001fa18  lea     rax, [rsp+530h+var_4C0]
0x18001fa1d  mov     [rsp+530h+var_4F0], rax
0x18001fa22  lea     rax, [rsp+530h+var_4E0]
0x18001fa27  mov     [rsp+530h+var_4F8], rax
0x18001fa2c  lea     rax, [rsp+530h+var_4C8]
0x18001fa31  mov     [rsp+530h+var_500], rax
0x18001fa36  lea     rax, [rsp+530h+var_4D8]
0x18001fa3b  mov     [rsp+530h+lpcbData], rax
0x18001fa40  lea     rax, [rsp+530h+var_4D0]
0x18001fa45  jmp     loc_18001F663
0x18001fa4a  lea     rax, [rbp+430h+hKey]
0x18001fa4e  mov     r9d, 20019h; samDesired
0x18001fa54  xor     r8d, r8d; ulOptions
0x18001fa57  mov     [rsp+530h+phkResult], rax; phkResult
0x18001fa5c  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x18001fa60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fa67  call    cs:__imp_RegOpenKeyExW
0x18001fa6d  mov     ebx, eax
0x18001fa6f  test    eax, eax
0x18001fa71  jz      loc_18001FB1C
0x18001fa77  jle     short loc_18001FA82
0x18001fa79  movzx   ebx, ax
0x18001fa7c  or      ebx, 80070000h
0x18001fa82  test    ebx, ebx
0x18001fa84  jns     loc_18001FB1C
0x18001fa8a  mov     eax, cs:dword_1801B76C8
0x18001fa90  mov     edi, 2
0x18001fa95  cmp     eax, edi
0x18001fa97  jbe     loc_18001FED4
0x18001fa9d  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x18001faa4  mov     dword ptr [rsp+530h+var_4E0], 10F4h
0x18001faac  mov     [rsp+530h+var_4B8], rax
0x18001fab1  lea     rdx, word_1801951C6
0x18001fab8  lea     rax, aGetpropertyaud; "GetPropertyAudioEnumDllName"
0x18001fabf  mov     dword ptr [rsp+530h+var_4D8], ebx
0x18001fac3  mov     [rsp+530h+var_4C0], rax
0x18001fac8  lea     rax, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18001facf  mov     [rsp+530h+var_4C8], rax
0x18001fad4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001fadb  mov     [rsp+530h+var_4D0], rax
0x18001fae0  lea     rax, [rsp+530h+var_4B8]
0x18001fae5  mov     [rsp+530h+var_4E8], rax
0x18001faea  lea     rax, [rsp+530h+var_4C0]
0x18001faef  mov     [rsp+530h+var_4F0], rax
0x18001faf4  lea     rax, [rsp+530h+var_4E0]
0x18001faf9  mov     [rsp+530h+var_4F8], rax
0x18001fafe  lea     rax, [rsp+530h+var_4C8]
0x18001fb03  mov     [rsp+530h+var_500], rax
0x18001fb08  lea     rax, [rsp+530h+var_4D8]
0x18001fb0d  mov     [rsp+530h+lpcbData], rax
0x18001fb12  lea     rax, [rsp+530h+var_4D0]
  ... truncated ...
```
