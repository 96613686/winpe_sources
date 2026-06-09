# RegistryKey::ReadStringValueWorker<256,HSTRING__ *>(ushort const *,ulong,HSTRING__ * *,bool *)

- ea: `0x1800584a0`
- end: `0x180058e19`
- name: `??$ReadStringValueWorker@$0BAA@PEAUHSTRING__@@@RegistryKey@@AEBAJPEBGKPEAPEAUHSTRING__@@PEA_N@Z`
- size: `2425`
- prototype: `HRESULT __fastcall(RegistryKey *this, const wchar_t *valueName, unsigned int dwFlags, HSTRING__ **value, bool *isExpandable)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058440`
- `0x180058470`
- `0x1801324e0`

## callees

- `0x18003a8bc`
- `0x180041020`
- `0x1800421e0`
- `0x1800436b0`
- `0x1800450a0`
- `0x180058130`
- `0x1800584a0`
- `0x180058e20`
- `0x180058e60`
- `0x18005a880`
- `0x18005a990`
- `0x1800b7fe4`
- `0x1800d141c`
- `0x1800db154`
- `0x1800f5294`
- `0x180106abc`
- `0x180188554`
- `0x1801999b0`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058686`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180058686`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058678`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180058678`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058908`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058908`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058a5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058c61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058c92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058d58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058a5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058c61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058c92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058d58`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180058973`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800589cd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180058973`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800589cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800586fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800586fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058528`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058528`

## string_xrefs

- `0x180058570`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x1800585d6`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x18005872d`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058781`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x1800587a1`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058879`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058a38`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058aa4`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058af8`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058b5a`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058b78`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058c19`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058cc3`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058cec`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058d3c`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058d88`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058db1`: `onecore\com\combase\inc\RegistryKey.hpp`
- `0x180058dcc`: `onecore\com\combase\inc\RegistryKey.hpp`

## pseudocode

```c
__int64 __fastcall RegistryKey::ReadStringValueWorker<256,HSTRING__ *>(
        RegistryKey *this,
        const wchar_t *valueName,
        unsigned int dwFlags,
        HSTRING__ **value,
        bool *isExpandable)
{
  HKEY__ *volatile hkey; // rcx
  LSTATUS v10; // eax
  HRESULT v11; // ebx
  char v12; // si
  bool v14; // zf
  unsigned __int64 v15; // r14
  unsigned int v16; // r15d
  HANDLE ProcessHeap; // rax
  HSTRING_BUFFER__ *v18; // rax
  STRING_OPAQUE *v19; // rbx
  _WORD *v20; // rcx
  char m_ptr; // r15
  LSTATUS ValueW; // eax
  HRESULT v23; // esi
  unsigned int v24; // ebx
  const wchar_t *v25; // r8
  unsigned int v26; // edx
  unsigned int v27; // edx
  __int64 length; // rcx
  HSTRING__ *v29; // rsi
  HSTRING_BUFFER__ *v30; // rbx
  __int64 v31; // rax
  int v32; // edx
  _WORD *v33; // rcx
  _WORD *v34; // r8
  wchar_t *v35; // rbx
  unsigned __int64 v36; // r14
  wchar_t *v37; // rax
  const wchar_t *v38; // rdx
  wchar_t *v39; // rsi
  HRESULT v40; // eax
  unsigned int v41; // r14d
  wchar_t *v42; // r14
  DWORD v43; // eax
  DWORD v44; // r15d
  __int64 v45; // r12
  HRESULT v46; // eax
  wchar_t *v47; // rax
  wchar_t *v48; // rdx
  HRESULT v49; // eax
  unsigned int v50; // ecx
  unsigned int v51; // esi
  HRESULT v52; // eax
  unsigned int v53; // edx
  unsigned int LastErrorMsg; // edi
  unsigned int *lpData; // [rsp+20h] [rbp-E0h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > result; // [rsp+40h] [rbp-C0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (__cdecl*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer,wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t> > > buffer; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int dataSize; // [rsp+50h] [rbp-B0h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > dynamicBuffer; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int dwType; // [rsp+60h] [rbp-A0h] BYREF
  bool *v61; // [rsp+68h] [rbp-98h]
  HSTRING__ **v62; // [rsp+70h] [rbp-90h]
  wchar_t stackBuffer[256]; // [rsp+80h] [rbp-80h] BYREF
  void *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v61 = isExpandable;
  v62 = value;
  LODWORD(dynamicBuffer.m_ptr) = dwFlags;
  *isExpandable = 0;
  dataSize = 512;
  *value = 0;
  hkey = this->_hkey;
  dwType = 0;
  buffer.m_ptr = 0;
  result.m_ptr = 0;
  v10 = RegQueryValueExW(hkey, valueName, 0, &dwType, (LPBYTE)stackBuffer, &dataSize);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 < 0 )
  {
    if ( v11 == -2147024894 )
      goto LABEL_8;
    if ( v11 == -2147024662 )
    {
LABEL_81:
      v12 = 0;
      goto LABEL_9;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      0x6EAu,
      "onecore\\com\\combase\\inc\\RegistryKey.hpp",
      v11,
      "value:%ls",
      valueName);
  }
  if ( v11 == -2147024774 )
    goto LABEL_81;
LABEL_8:
  v12 = 1;
  if ( v11 < 0 )
    return (unsigned int)v11;
LABEL_9:
  if ( dwType == 1 )
  {
    v14 = (dwFlags & 2) == 0;
  }
  else
  {
    if ( dwType != 2 )
    {
      if ( dwType != 7 || (dwFlags & 0x20) == 0 )
        goto LABEL_12;
      goto LABEL_16;
    }
    v14 = (dwFlags & 4) == 0;
  }
  if ( v14 )
  {
LABEL_12:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x81Eu,
      "onecore\\com\\combase\\inc\\RegistryKey.hpp",
      -2147024883,
      "value:%ws",
      valueName);
    return 2147942413LL;
  }
LABEL_16:
  if ( !dataSize || (dataSize & 1) != 0 )
    goto LABEL_12;
  v15 = (dataSize >> 1) - 1;
  if ( dataSize >> 1 == 1 )
  {
    if ( v12 && !stackBuffer[0] && (dwFlags & 0x20) == 0 )
    {
      *value = 0;
      return 0;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x837u,
      "onecore\\com\\combase\\inc\\RegistryKey.hpp",
      -2147024883,
      "value:%ws",
      valueName);
    Windows::Internal::String::~String((Windows::Internal::String *)&result);
    return 2147942413LL;
  }
  if ( dwType != 2 || (dwFlags & 0x10000000) != 0 )
  {
    v16 = 2 * v15;
    if ( 2 * v15 > 0xFFFFFFFF || v16 >= 0xFFFFFFE0 )
    {
      v24 = -2146959343;
      v25 = L"length";
      v26 = 6;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v18 = (HSTRING_BUFFER__ *)HeapAlloc(ProcessHeap, 0, v16 + 32);
      v19 = (STRING_OPAQUE *)v18;
      if ( v18 )
      {
        buffer.m_ptr = v18;
        *((_WORD *)v18 + v15 + 14) = 0;
        *(_DWORD *)v18 = 0;
        *((_QWORD *)v18 + 2) = v18 + 7;
        *((_DWORD *)v18 + 1) = v15;
        *((_DWORD *)v18 + 6) = 1;
        v20 = (_WORD *)*((_QWORD *)v18 + 2);
        *(_DWORD *)v18 = -122574658;
        v20[v15] = 0;
        if ( v12 )
        {
          if ( stackBuffer[v15]
            || (m_ptr = (char)dynamicBuffer.m_ptr, ((__int64)dynamicBuffer.m_ptr & 0x20) != 0)
            && stackBuffer[(unsigned int)(v15 - 1)] )
          {
            v53 = 2170;
            goto LABEL_79;
          }
          memcpy_0(v20, stackBuffer, dataSize);
        }
        else
        {
          m_ptr = (char)dynamicBuffer.m_ptr;
          ValueW = RegGetValueW(this->_hkey, 0, valueName, (DWORD)dynamicBuffer.m_ptr, 0, v20, &dataSize);
          v23 = ValueW;
          if ( ValueW > 0 )
            v23 = (unsigned __int16)ValueW | 0x80070000;
          if ( v23 < 0 )
          {
            if ( v23 != -2147024894 && v23 != -2147024662 )
              wil::details::in1diag3::Log_Hr(retaddr, 0x64Fu, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v23);
            wil::details::in1diag3::Return_Hr(retaddr, 0x885u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v23);
            Windows::Internal::String::~String((Windows::Internal::String *)&result);
            WindowsDeleteStringBuffer((HSTRING_BUFFER)v19);
            return (unsigned int)v23;
          }
        }
        if ( v19->flags != -122574658 || (length = v19->length, v19->stringRef[length]) )
        {
          RoOriginateErrorW(-2147024809, 0xCu, L"bufferHandle");
          wil::details::in1diag3::Return_Hr(retaddr, 0x7Fu, "onecore\\com\\combase\\inc\\RegistryKey.hpp", -2147024809);
          wil::details::in1diag3::Return_Hr(retaddr, 0x887u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", -2147024809);
          Windows::Internal::String::~String((Windows::Internal::String *)&result);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&buffer);
          return 2147942487LL;
        }
        if ( (_DWORD)length )
        {
          v19->flags = WRHF_NONE;
          v29 = (HSTRING__ *)v19;
        }
        else
        {
          v29 = 0;
          STRING_OPAQUE::Release(v19);
        }
        v30 = 0;
        if ( (m_ptr & 0x20) == 0 )
        {
          if ( v29 )
          {
            v31 = *((unsigned int *)v29 + 1);
            if ( (_DWORD)v31 )
            {
              v32 = *(_DWORD *)v29;
              if ( (*(_DWORD *)v29 & 0x10) == 0 )
              {
                v33 = (_WORD *)*((_QWORD *)v29 + 2);
                v34 = &v33[v31];
                while ( 1 )
                {
                  if ( v33 >= v34 )
                  {
                    v32 |= 0x10u;
                    goto LABEL_47;
                  }
                  if ( !*v33 )
                    break;
                  ++v33;
                }
                v32 |= 0x18u;
LABEL_47:
                *(_DWORD *)v29 = v32;
              }
              if ( (v32 & 8) != 0 )
              {
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  0x88Du,
                  "onecore\\com\\combase\\inc\\RegistryKey.hpp",
                  -2147024883,
                  "value:%ws",
                  valueName);
                WindowsDeleteString(v29);
                return 2147942413LL;
              }
            }
          }
        }
        *v61 = dwType == 2;
LABEL_84:
        result.m_ptr = 0;
        *v62 = v29;
        Windows::Internal::String::~String((Windows::Internal::String *)&result);
        if ( v30 )
        {
          WindowsDeleteStringBuffer(v30);
          return 0;
        }
        return 0;
      }
      v26 = 0;
      v24 = -2147024882;
      v25 = 0;
    }
    RoOriginateErrorW(v24, v26, v25);
    wil::details::in1diag3::Return_Hr(retaddr, 0x77u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v24);
    v27 = 2156;
LABEL_31:
    wil::details::in1diag3::Return_Hr(retaddr, v27, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v24);
    Windows::Internal::String::~String((Windows::Internal::String *)&result);
    return v24;
  }
  v35 = 0;
  v36 = v15;
  dynamicBuffer.m_ptr = 0;
  if ( v12 )
  {
    if ( !stackBuffer[v36] )
    {
      v39 = stackBuffer;
      v42 = 0;
      goto LABEL_63;
    }
    v53 = 2120;
LABEL_79:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      v53,
      "onecore\\com\\combase\\inc\\RegistryKey.hpp",
      -2147024883,
      "value:%ws",
      valueName);
    Windows::Internal::String::~String((Windows::Internal::String *)&result);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&buffer);
    return 2147942413LL;
  }
  v37 = (wchar_t *)LocalAlloc(0, v36 * 2 + 2);
  if ( v37 )
  {
    *v37 = 0;
    v37[v36] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &dynamicBuffer,
    v37);
  v35 = dynamicBuffer.m_ptr;
  if ( !dynamicBuffer.m_ptr )
  {
    v24 = -2147024882;
    v27 = 2125;
    goto LABEL_31;
  }
  v39 = dynamicBuffer.m_ptr;
  v40 = RegistryKey::GetValue(this, v38, valueName, dwFlags | 0x10000000, lpData, dynamicBuffer.m_ptr, &dataSize);
  v41 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x855u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v40);
    if ( !v35 )
      goto LABEL_94;
    goto LABEL_93;
  }
  v42 = v35;
LABEL_63:
  v43 = ExpandEnvironmentStringsW(v39, 0, 0);
  v44 = v43;
  if ( v43 )
  {
    v45 = v43 - 1;
    dynamicBuffer.m_ptr = 0;
    v46 = STRING_OPAQUE::Create(0, v43 - 1, (STRING_OPAQUE **)&dynamicBuffer);
    v41 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x77u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v46);
      wil::details::in1diag3::Return_Hr(retaddr, 0x85Fu, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v41);
      if ( !v35 )
        goto LABEL_94;
      goto LABEL_93;
    }
    v47 = dynamicBuffer.m_ptr;
    buffer.m_ptr = (HSTRING_BUFFER__ *)dynamicBuffer.m_ptr;
    *(_DWORD *)dynamicBuffer.m_ptr = -122574658;
    v48 = (wchar_t *)*((_QWORD *)v47 + 2);
    v48[v45] = 0;
    ExpandEnvironmentStringsW(v39, v48, v44);
    result.m_ptr = 0;
    v49 = StringTraits<HSTRING__ *>::Promote(&buffer, &result.m_ptr);
    v51 = v49;
    if ( v49 >= 0 )
    {
      v29 = result.m_ptr;
      LODWORD(dynamicBuffer.m_ptr) = 0;
      v52 = StringTraits<HSTRING__ *>::VerifyNoEmbeddedNulls(v50, result.m_ptr, (int *)&dynamicBuffer);
      v41 = v52;
      if ( v52 >= 0 )
      {
        if ( LODWORD(dynamicBuffer.m_ptr) )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0x866u,
            "onecore\\com\\combase\\inc\\RegistryKey.hpp",
            -2147024883,
            "value:%ws",
            valueName);
          if ( v35 )
            LocalFree(v35);
          Windows::Internal::String::~String((Windows::Internal::String *)&result);
          if ( buffer.m_ptr )
          {
            WindowsDeleteStringBuffer(buffer.m_ptr);
            return 2147942413LL;
          }
          return 2147942413LL;
        }
        *v61 = 1;
        if ( v35 )
          LocalFree(v35);
        v30 = buffer.m_ptr;
        goto LABEL_84;
      }
      wil::details::in1diag3::Return_Hr(retaddr, 0x865u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v52);
      if ( !v35 )
        goto LABEL_94;
LABEL_93:
      LocalFree(v35);
LABEL_94:
      Windows::Internal::String::~String((Windows::Internal::String *)&result);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&buffer);
      return v41;
    }
    wil::details::in1diag3::Return_Hr(retaddr, 0x862u, "onecore\\com\\combase\\inc\\RegistryKey.hpp", v49);
    if ( v35 )
      LocalFree(v35);
    Windows::Internal::String::~String((Windows::Internal::String *)&result);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&buffer);
    return v51;
  }
  else
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     0x85Au,
                     "onecore\\com\\combase\\inc\\RegistryKey.hpp",
                     "ExpandEnvironmentStrings failed, value:%ws",
                     valueName);
    if ( v42 )
      LocalFree(v35);
    Windows::Internal::String::~String((Windows::Internal::String *)&result);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&buffer);
    return LastErrorMsg;
  }
}

```

## disassembly

```asm
0x1800584a0  push    rbp
0x1800584a2  push    rbx
0x1800584a3  push    rdi
0x1800584a4  push    r12
0x1800584a6  push    r13
0x1800584a8  push    r15
0x1800584aa  lea     rbp, [rsp-1A8h]
0x1800584b2  sub     rsp, 2A8h
0x1800584b9  mov     rax, cs:__security_cookie
0x1800584c0  xor     rax, rsp
0x1800584c3  mov     [rbp+1D0h+var_50], rax
0x1800584ca  mov     rax, [rbp+1D0h+arg_20]
0x1800584d1  mov     r15, value
0x1800584d4  mov     [rsp+2D0h+var_268], rax
0x1800584d9  mov     r12d, dwFlags
0x1800584dc  mov     [rsp+2D0h+var_260], value
0x1800584e1  mov     r13, this
0x1800584e4  mov     dword ptr [rsp+2D0h+dynamicBuffer.m_ptr], dwFlags
0x1800584e9  mov     rdi, valueName
0x1800584ec  mov     byte ptr [rax], 0
0x1800584ef  xor     dwFlags, dwFlags; lpReserved
0x1800584f2  xor     eax, eax
0x1800584f4  mov     [rsp+2D0h+dataSize], 200h
0x1800584fc  mov     [value], rax
0x1800584ff  lea     value, [rsp+2D0h+dwType]; lpType
0x180058504  mov     this, [this]; hKey
0x180058507  mov     [rsp+2D0h+dwType], eax
0x18005850b  mov     [rsp+2D0h+buffer.m_ptr], rax
0x180058510  mov     [rsp+2D0h+result.m_ptr], rax
0x180058515  lea     rax, [rsp+2D0h+dataSize]
0x18005851a  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18005851f  lea     rax, [rbp+1D0h+stackBuffer]
0x180058523  mov     [rsp+2D0h+lpData], rax; lpData
0x180058528  call    cs:__imp_RegQueryValueExW
0x18005852e  mov     ebx, eax
0x180058530  test    eax, eax
0x180058532  jle     short loc_18005853D
0x180058534  movzx   ebx, ax
0x180058537  or      ebx, 80070000h
0x18005853d  mov     [rsp+2D0h+var_30], rsi
0x180058545  test    ebx, ebx
0x180058547  jns     short loc_180058589
0x180058549  cmp     ebx, 80070002h
0x18005854f  jz      short loc_180058595
0x180058551  cmp     ebx, 800700EAh
0x180058557  jz      loc_180058B35
0x18005855d  mov     this, [rbp+1D8h]; callerReturnAddress
0x180058564  lea     rax, pcbData; "value:%ls"
0x18005856b  mov     [rsp+2D0h+lpcbData], rdi
0x180058570  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x180058577  mov     r9d, ebx; hr
0x18005857a  mov     [rsp+2D0h+lpData], rax; pcbData
0x18005857f  mov     edx, 6EAh; lineNumber
0x180058584  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058589  cmp     ebx, 8007007Ah
0x18005858f  jz      loc_180058B35
0x180058595  cmp     ebx, 800700EAh
0x18005859b  jz      loc_180058B35
0x1800585a1  mov     sil, 1
0x1800585a4  test    ebx, ebx
0x1800585a6  js      short loc_18005861F
0x1800585a8  mov     eax, [rsp+2D0h+dwType]
0x1800585ac  cmp     eax, 1
0x1800585af  jz      short loc_180058623
0x1800585b1  cmp     eax, 2
0x1800585b4  jz      loc_1800588DB
0x1800585ba  cmp     eax, 7
0x1800585bd  jz      loc_180058ABD
0x1800585c3  mov     this, [rbp+1D8h]; callerReturnAddress
0x1800585ca  lea     rax, aValueWs; "value:%ws"
0x1800585d1  mov     [rsp+2D0h+lpcbData], rdi
0x1800585d6  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x1800585dd  mov     r9d, 8007000Dh; hr
0x1800585e3  mov     [rsp+2D0h+lpData], rax; formatString
0x1800585e8  mov     edx, 81Eh; lineNumber
0x1800585ed  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800585f2  mov     eax, 8007000Dh
0x1800585f7  mov     rsi, [rsp+2D0h+var_30]
0x1800585ff  mov     this, [rbp+1D0h+var_50]
0x180058606  xor     this, rsp; StackCookie
0x180058609  call    __security_check_cookie
0x18005860e  add     rsp, 2A8h
0x180058615  pop     r15
0x180058617  pop     r13
0x180058619  pop     r12
0x18005861b  pop     rdi
0x18005861c  pop     rbx
0x18005861d  pop     rbp
0x18005861e  retn
0x18005861f  mov     eax, ebx
0x180058621  jmp     short loc_1800585F7
0x180058623  test    r12b, 2
0x180058627  jz      short loc_1800585C3
0x180058629  mov     ecx, [rsp+2D0h+dataSize]
0x18005862d  test    ecx, ecx
0x18005862f  jz      short loc_1800585C3
0x180058631  test    cl, 1
0x180058634  jnz     short loc_1800585C3
0x180058636  shr     ecx, 1
0x180058638  mov     [rsp+2D0h+var_38], r14
0x180058640  lea     r14d, [this-1]
0x180058644  test    r14d, r14d
0x180058647  jz      loc_1800588AF
0x18005864d  cmp     eax, 2
0x180058650  jz      loc_1800588E4
0x180058656  lea     r15, [r14+r14]
0x18005865a  mov     ebx, 0FFFFFFFFh
0x18005865f  cmp     r15, rbx
0x180058662  ja      loc_180058762
0x180058668  lea     eax, [r15+20h]
0x18005866c  cmp     eax, 20h ; ' '
0x18005866f  cmovnb  ebx, eax
0x180058672  jb      loc_180058762
0x180058678  call    cs:__imp_GetProcessHeap
0x18005867e  mov     dwFlags, ebx; dwBytes
0x180058681  xor     edx, edx; dwFlags
0x180058683  mov     this, rax; hHeap
0x180058686  call    cs:__imp_HeapAlloc
0x18005868c  mov     rbx, rax
0x18005868f  test    rax, rax
0x180058692  jz      loc_180058C80
0x180058698  xor     ecx, ecx
0x18005869a  mov     [rsp+2D0h+buffer.m_ptr], rbx
0x18005869f  mov     [rax+r14*2+1Ch], cx
0x1800586a5  mov     [rax], ecx
0x1800586a7  lea     this, [rax+1Ch]
0x1800586ab  mov     [rax+10h], this
0x1800586af  mov     [rax+4], r14d
0x1800586b3  mov     dword ptr [rax+18h], 1
0x1800586ba  mov     this, [rax+10h]; void *
0x1800586be  mov     dword ptr [rax], 0F8B1A8BEh
0x1800586c4  xor     eax, eax
0x1800586c6  mov     [this+r15], ax
0x1800586cb  test    sil, sil
0x1800586ce  jnz     loc_180058AD4
0x1800586d4  mov     r15d, dword ptr [rsp+2D0h+dynamicBuffer.m_ptr]
0x1800586d9  lea     rax, [rsp+2D0h+dataSize]
0x1800586de  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800586e3  mov     r9d, r15d; dwFlags
0x1800586e6  mov     [rsp+2D0h+lpcbData], this; pvData
0x1800586eb  mov     r8, rdi; lpValue
0x1800586ee  mov     this, [r13+0]; hkey
0x1800586f2  xor     edx, edx; lpSubKey
0x1800586f4  mov     [rsp+2D0h+lpData], 0; pdwType
0x1800586fd  call    cs:__imp_RegGetValueW
0x180058703  mov     esi, eax
0x180058705  test    eax, eax
0x180058707  jle     short loc_180058712
0x180058709  movzx   esi, ax
0x18005870c  or      esi, 80070000h
0x180058712  test    esi, esi
0x180058714  jns     loc_1800587E6
0x18005871a  cmp     esi, 80070002h
0x180058720  jnz     loc_180058A91
0x180058726  mov     this, [rbp+1D8h]; callerReturnAddress
0x18005872d  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x180058734  mov     r9d, esi; hr
0x180058737  mov     edx, 885h; lineNumber
0x18005873c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058741  lea     this, [rsp+2D0h+result]; this
0x180058746  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005874b  mov     this, rbx; bufferHandle
0x18005874e  call    WindowsDeleteStringBuffer
0x180058753  mov     eax, esi
0x180058755  mov     r14, [rsp+2D0h+var_38]
0x18005875d  jmp     loc_1800585F7
0x180058762  mov     ebx, 80080011h
0x180058767  lea     r8, aLength; "length"
0x18005876e  mov     edx, 6; cchMax
0x180058773  mov     ecx, ebx; error
0x180058775  call    RoOriginateErrorW
0x18005877a  mov     this, [rbp+1D8h]; callerReturnAddress
0x180058781  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x180058788  mov     r9d, ebx; hr
0x18005878b  mov     edx, 77h ; 'w'; lineNumber
0x180058790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058795  mov     edx, 86Ch; lineNumber
0x18005879a  mov     this, [rbp+1D8h]; callerReturnAddress
0x1800587a1  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x1800587a8  mov     r9d, ebx; hr
0x1800587ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800587b0  lea     this, [rsp+2D0h+result]; this
0x1800587b5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800587ba  mov     r14, [rsp+2D0h+var_38]
0x1800587c2  mov     eax, ebx
0x1800587c4  jmp     loc_1800585F7
0x1800587c9  mov     r15d, dword ptr [rsp+2D0h+dynamicBuffer.m_ptr]
0x1800587ce  test    r15b, 20h
0x1800587d2  jnz     loc_180058E04
0x1800587d8  mov     dwFlags, [rsp+2D0h+dataSize]; Size
0x1800587dd  lea     valueName, [rbp+1D0h+stackBuffer]; Src
0x1800587e1  call    memcpy_0
0x1800587e6  cmp     dword ptr [rbx], 0F8B1A8BEh
0x1800587ec  jnz     loc_180058B3D
0x1800587f2  mov     ecx, [rbx+4]
0x1800587f5  mov     rax, [rbx+10h]
0x1800587f9  cmp     word ptr [rax+this*2], 0
0x1800587fe  jnz     loc_180058B3D
0x180058804  test    ecx, ecx
0x180058806  jz      loc_180058C71
0x18005880c  mov     dword ptr [rbx], 0
0x180058812  mov     rsi, rbx
0x180058815  xor     ebx, ebx
0x180058817  test    r15b, 20h
0x18005881b  jnz     loc_180058BB5
0x180058821  test    rsi, rsi
0x180058824  jz      loc_180058BB5
0x18005882a  mov     eax, [rsi+4]
0x18005882d  test    eax, eax
0x18005882f  jz      loc_180058BB5
0x180058835  mov     edx, [rsi]
0x180058837  test    dl, 10h
0x18005883a  jnz     short loc_18005885D
0x18005883c  mov     this, [rsi+10h]
0x180058840  lea     r8, [this+rax*2]
0x180058844  cmp     this, r8
0x180058847  jnb     short loc_180058858
0x180058849  cmp     [this], bx
0x18005884c  jz      loc_180058ACC
0x180058852  add     this, 2
0x180058856  jmp     short loc_180058844
0x180058858  or      edx, 10h
0x18005885b  mov     [rsi], edx
0x18005885d  test    dl, 8
0x180058860  jz      loc_180058BB5
0x180058866  mov     this, [rbp+1D8h]; callerReturnAddress
0x18005886d  lea     rax, aValueWs; "value:%ws"
0x180058874  mov     [rsp+2D0h+lpcbData], rdi
0x180058879  lea     r8, aOnecoreComComb_8; "onecore\\com\\combase\\inc\\RegistryKey"...
0x180058880  mov     r9d, 8007000Dh; hr
0x180058886  mov     [rsp+2D0h+lpData], rax; formatString
0x18005888b  mov     edx, 88Dh; lineNumber
0x180058890  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058895  mov     this, rsi; string
0x180058898  call    WindowsDeleteString
0x18005889d  mov     r14, [rsp+2D0h+var_38]
0x1800588a5  mov     eax, 8007000Dh
0x1800588aa  jmp     loc_1800585F7
0x1800588af  test    sil, sil
0x1800588b2  jz      loc_180058C06
0x1800588b8  cmp     [rbp+1D0h+stackBuffer], 0
0x1800588bd  jnz     loc_180058C06
0x1800588c3  test    r12b, 20h
0x1800588c7  jnz     loc_180058C06
0x1800588cd  mov     qword ptr [r15], 0
0x1800588d4  xor     eax, eax
0x1800588d6  jmp     loc_180058755
0x1800588db  test    r12b, 4
0x1800588df  jmp     loc_180058627
0x1800588e4  bt      r12d, 1Ch
0x1800588e9  jb      loc_180058656
0x1800588ef  xor     ebx, ebx
0x1800588f1  add     r14, r14
0x1800588f4  mov     [rsp+2D0h+dynamicBuffer.m_ptr], rbx
0x1800588f9  test    sil, sil
0x1800588fc  jnz     loc_180058DEE
0x180058902  lea     valueName, [r14+2]; uBytes
0x180058906  xor     ecx, ecx; uFlags
0x180058908  call    cs:__imp_LocalAlloc
0x18005890e  test    rax, rax
0x180058911  jz      short loc_18005891D
0x180058913  xor     ecx, ecx
0x180058915  mov     [rax], cx
0x180058918  mov     [rax+r14], cx
0x18005891d  mov     valueName, rax; ptr
0x180058920  lea     this, [rsp+2D0h+dynamicBuffer]; this
0x180058925  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005892a  mov     rbx, [rsp+2D0h+dynamicBuffer.m_ptr]
0x18005892f  test    rbx, rbx
0x180058932  jz      loc_180058BF7
0x180058938  lea     rax, [rsp+2D0h+dataSize]
0x18005893d  bts     r12d, 1Ch
0x180058942  mov     [rsp+2D0h+pcbData], rax; pszValue
0x180058947  mov     r9d, r12d; pvData
0x18005894a  mov     r8, rdi; dwFlags
0x18005894d  mov     [rsp+2D0h+lpcbData], rbx; pszSubKey
0x180058952  mov     this, r13; this
0x180058955  mov     rsi, rbx
0x180058958  call    ?GetValue@RegistryKey@@QEBAJPEBG0KPEAKPEAX1@Z; RegistryKey::GetValue(ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x18005895d  mov     r14d, eax
0x180058960  test    eax, eax
0x180058962  js      loc_180058CBC
0x180058968  mov     r14, rbx
0x18005896b  xor     dwFlags, dwFlags; nSize
0x18005896e  xor     edx, edx; lpDst
0x180058970  mov     this, rsi; lpSrc
0x180058973  call    cs:__imp_ExpandEnvironmentStringsW
0x180058979  mov     r15d, eax
0x18005897c  test    eax, eax
0x18005897e  jz      loc_180058CDE
0x180058984  lea     r12d, [rax-1]
0x180058988  mov     [rsp+2D0h+dynamicBuffer.m_ptr], 0
0x180058991  mov     edx, r12d; length
0x180058994  lea     r8, [rsp+2D0h+dynamicBuffer]; ppString
0x180058999  xor     ecx, ecx; sourceString
0x18005899b  call    ?Create@STRING_OPAQUE@@SAJPEBGIPEAPEAU1@@Z; STRING_OPAQUE::Create(ushort const *,uint,STRING_OPAQUE * *)
0x1800589a0  mov     r14d, eax
0x1800589a3  test    eax, eax
0x1800589a5  js      loc_180058DAA
0x1800589ab  mov     rax, [rsp+2D0h+dynamicBuffer.m_ptr]
  ... truncated ...
```
