# PolicyManager::BuildMergedPassportCspPolicy

- ea: `0x18001ee80`
- end: `0x18002000c`
- name: `PolicyManager::BuildMergedPassportCspPolicy`
- size: `4492`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180020320`

## callees

- `0x1800105c0`
- `0x18001ee80`
- `0x180024014`
- `0x18002cb1c`
- `0x18002cbf8`
- `0x18002d16c`
- `0x18002dff0`
- `0x18002e02c`
- `0x18002e850`
- `0x18002f7db`
- `0x18002f7e7`
- `0x18003e370`
- `0x180043ff0`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ffcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fff2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001efd4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f109`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f330`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fc1c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fcc8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001feb9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001efd4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f109`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001f330`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fc1c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001fcc8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001feb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f052`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f052`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eef0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eef0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f27d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f27d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyManager::BuildMergedPassportCspPolicy(__int64 a1, _OWORD *a2)
{
  _OWORD *v2; // rdi
  int v3; // ebx
  unsigned int v5; // ebx
  DWORD v6; // eax
  size_t v7; // rbx
  _QWORD *v8; // rax
  void *v9; // rax
  void *v10; // rcx
  char *v11; // rdi
  LSTATUS v12; // eax
  unsigned __int64 v13; // rdx
  void *v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // rbx
  __int64 v17; // rsi
  _QWORD *v18; // rdi
  unsigned __int64 v19; // r14
  ULONGLONG v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rsi
  void *v25; // rax
  unsigned __int64 v26; // rdx
  void *v27; // rax
  size_t v28; // rbx
  unsigned __int64 v29; // rbx
  size_t v30; // rbx
  unsigned __int64 v31; // r14
  size_t v32; // rcx
  void *v33; // rax
  char *v34; // rsi
  size_t v35; // rbx
  void **v36; // rbx
  void *v37; // r11
  const __m128i *v38; // r8
  unsigned __int64 v39; // rdx
  const __m128i *v40; // r9
  __int64 v41; // rax
  unsigned __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  _BYTE *v45; // rcx
  void **v46; // rdx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  unsigned __int64 v50; // rdx
  void *v51; // rcx
  void **v52; // rax
  int v53; // eax
  ULONG Size; // ecx
  int v55; // ecx
  int v56; // r9d
  int v57; // r8d
  int v58; // edx
  int v59; // eax
  unsigned int v60; // r11d
  int v61; // r9d
  int v62; // r8d
  int v63; // edx
  int v64; // eax
  unsigned __int64 v65; // rdx
  void *v66; // rcx
  unsigned __int64 v67; // rdx
  void *v68; // rax
  unsigned __int64 v69; // rdx
  void *v70; // rcx
  unsigned __int64 v71; // rdx
  void *v72; // rax
  unsigned __int64 v73; // rdx
  void *Ptr; // rax
  signed int v75; // eax
  int v76; // edx
  unsigned int v77; // r8d
  signed int v78; // eax
  int v79; // edx
  unsigned int v80; // r8d
  signed int LastError; // eax
  int v82; // edx
  unsigned int v83; // r8d
  signed int v84; // eax
  int v85; // edx
  unsigned int v86; // r8d
  signed int v87; // eax
  int v88; // edx
  unsigned int v89; // r8d
  signed int v90; // eax
  int v91; // edx
  unsigned int v92; // r8d
  unsigned int v93; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v94; // [rsp+64h] [rbp-9Ch]
  __int64 v95; // [rsp+68h] [rbp-98h] BYREF
  void **v96; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+80h] [rbp-80h] BYREF
  void **v99; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  DWORD dwIndex; // [rsp+94h] [rbp-6Ch]
  DWORD cSubKeys; // [rsp+98h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR v103; // [rsp+A0h] [rbp-60h] BYREF
  int v104; // [rsp+B0h] [rbp-50h]
  __int128 v105; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v106[44]; // [rsp+C8h] [rbp-38h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD *v108; // [rsp+108h] [rbp+8h]
  void *v109[2]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v110; // [rsp+120h] [rbp+20h]
  unsigned __int64 v111; // [rsp+128h] [rbp+28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+130h] [rbp+30h] BYREF
  char *v113; // [rsp+140h] [rbp+40h]
  int v114; // [rsp+148h] [rbp+48h]
  int v115; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v116; // [rsp+150h] [rbp+50h]
  __int64 v117; // [rsp+158h] [rbp+58h]
  struct _EVENT_DATA_DESCRIPTOR v118; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v119[12]; // [rsp+170h] [rbp+70h]
  _BYTE v120[20]; // [rsp+17Ch] [rbp+7Ch]
  __int64 v121; // [rsp+190h] [rbp+90h]
  __int64 v122; // [rsp+198h] [rbp+98h]

  v2 = a2;
  v108 = a2;
  *(_QWORD *)&EventDescriptor.Id = a1;
  v96 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork", 0, 0x20019u, &hKey);
  if ( v3 == 2 )
  {
    v96 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(&v96) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v82, v83);
      __debugbreak();
    }
    return 2147942402LL;
  }
  if ( v3 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v95) = v3;
      v116 = &v95;
      v117 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v113 = byte_180061CA5;
      v114 = 28;
      v115 = 1;
      HIDWORD(v95) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v96 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(&v96) )
    {
      v84 = GetLastError();
      if ( v84 > 0 )
        v84 = (unsigned __int16)v84 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v84, v85, v86);
LABEL_252:
      std::_Throw_bad_array_new_length();
    }
    return (unsigned int)v3;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v3 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v95) = v3;
      v116 = &v95;
      v117 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v113 = byte_180061C81;
      v114 = 24;
      v115 = 1;
      HIDWORD(v95) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v96 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(&v96) )
    {
      v78 = GetLastError();
      if ( v78 > 0 )
        v78 = (unsigned __int16)v78 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v78, v79, v80);
      __debugbreak();
    }
    return (unsigned int)v3;
  }
  ++cbMaxSubKeyLen;
  v5 = 0;
  v94 = 0;
  LOBYTE(v105) = 0;
  DWORD1(v105) = 1;
  *((_QWORD *)&v105 + 1) = 1;
  v106[0] = 0;
  *(_QWORD *)&v106[4] = 0x7F00000008LL;
  *(_OWORD *)&v106[12] = 0;
  *(_DWORD *)&v106[28] = 2;
  *(_QWORD *)&v106[32] = 1;
  *(_DWORD *)&v106[40] = 0;
  NgcPolicy::NgcPolicy::Initialize(&v105);
  v6 = 0;
  dwIndex = 0;
  if ( !cSubKeys )
  {
LABEL_231:
    if ( (unsigned int)dword_18006E000 > 4 )
    {
      v93 = v5;
      LODWORD(v99) = 0;
      v121 = (__int64)&v93;
      v122 = 4;
      *(_QWORD *)&v120[4] = &v99;
      *(_QWORD *)&v120[12] = 4;
      *(_DWORD *)&v103.Id = 184549376;
      *(_DWORD *)&v103.Level = 4;
      v103.Keyword = 0;
      v118.Ptr = (ULONGLONG)off_18006E008;
      v118.Size = *(unsigned __int16 *)off_18006E008;
      v118.Reserved = 2;
      *(_QWORD *)v119 = byte_180061BB9;
      *(_DWORD *)&v119[8] = 50;
      *(_DWORD *)v120 = 1;
      LODWORD(v95) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v103, 0, 0, 4u, &v118);
    }
    if ( v5 )
    {
      *v2 = v105;
      v2[1] = *(_OWORD *)v106;
      v2[2] = *(_OWORD *)&v106[16];
      *(_OWORD *)((char *)v2 + 44) = *(_OWORD *)&v106[28];
      v96 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
      if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(&v96) )
      {
        v75 = GetLastError();
        if ( v75 > 0 )
          v75 = (unsigned __int16)v75 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v75, v76, v77);
        __debugbreak();
      }
      return 0;
    }
    else
    {
      v96 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
      if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(&v96) )
      {
        v90 = GetLastError();
        if ( v90 > 0 )
          v90 = (unsigned __int16)v90 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v90, v91, v92);
        JUMPOUT(0x18002000BLL);
      }
      return 2148073489LL;
    }
  }
  v104 = HIDWORD(v105);
  v95 = *(_QWORD *)((char *)&v105 + 4);
  while ( 1 )
  {
    UserData = 0;
    v113 = 0;
    if ( cbMaxSubKeyLen )
    {
      v7 = 2LL * cbMaxSubKeyLen;
      if ( v7 )
      {
        if ( v7 < 0x1000 )
        {
          v8 = operator new(v7);
        }
        else
        {
          if ( v7 + 39 < v7 )
            goto LABEL_252;
          v9 = operator new(v7 + 39);
          v10 = v9;
          if ( !v9 )
            goto LABEL_226;
          v8 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v8 - 1) = v10;
        }
      }
      else
      {
        v8 = 0;
      }
      UserData.Ptr = (ULONGLONG)v8;
      v11 = (char *)v8 + v7;
      v113 = (char *)v8 + v7;
      memset_0(v8, 0, v7);
      *(_QWORD *)&UserData.Size = v11;
      v6 = dwIndex;
    }
    else
    {
      v11 = *(char **)&UserData.Size;
    }
    cchName = (__int64)&v11[-UserData.Ptr] >> 1;
    v12 = RegEnumKeyExW(hKey, v6, (LPWSTR)UserData.Ptr, &cchName, 0, 0, 0, 0);
    if ( v12 == 259 )
    {
      if ( UserData.Ptr )
      {
        v73 = 2 * ((__int64)&v113[-UserData.Ptr] >> 1);
        if ( v73 < 0x1000 )
        {
          Ptr = (void *)UserData.Ptr;
        }
        else
        {
          Ptr = *(void **)(UserData.Ptr - 8);
          if ( UserData.Ptr - (unsigned __int64)Ptr - 8 > 0x1F )
            goto LABEL_226;
          v73 += 39LL;
        }
        operator delete(Ptr, v73);
        UserData = 0;
        v113 = 0;
      }
      v5 = v94;
LABEL_230:
      v2 = v108;
      goto LABEL_231;
    }
    if ( v12 )
    {
      if ( (unsigned int)dword_18006E000 > 3 )
      {
        LODWORD(v99) = v12;
        *(_QWORD *)&v120[4] = &v99;
        *(_QWORD *)&v120[12] = 4;
        *(_DWORD *)&v103.Id = 184549376;
        *(_DWORD *)&v103.Level = 3;
        v103.Keyword = 0;
        v118.Ptr = (ULONGLONG)off_18006E008;
        v118.Size = *(unsigned __int16 *)off_18006E008;
        v118.Reserved = 2;
        *(_QWORD *)v119 = byte_180061C59;
        *(_DWORD *)&v119[8] = 28;
        *(_DWORD *)v120 = 1;
        v93 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &v103, 0, 0, 3u, &v118);
      }
      if ( UserData.Ptr )
      {
        v13 = 2 * ((__int64)&v113[-UserData.Ptr] >> 1);
        if ( v13 < 0x1000 )
        {
          operator delete((void *)UserData.Ptr, v13);
        }
        else
        {
          v14 = *(void **)(UserData.Ptr - 8);
          if ( UserData.Ptr - (unsigned __int64)v14 - 8 > 0x1F )
            goto LABEL_226;
          operator delete(v14, v13 + 39);
        }
      }
      goto LABEL_107;
    }
    v15 = cchName + 1;
    cchName = v15;
    v16 = (unsigned int)v15;
    v17 = *(_QWORD *)&UserData.Size;
    v18 = (_QWORD *)UserData.Ptr;
    v19 = (__int64)(*(_QWORD *)&UserData.Size - UserData.Ptr) >> 1;
    if ( (unsigned int)v15 < v19 )
    {
      v20 = UserData.Ptr + 2 * v15;
LABEL_65:
      *(_QWORD *)&UserData.Size = v20;
      goto LABEL_66;
    }
    if ( (unsigned int)v15 > v19 )
    {
      v21 = (__int64)&v113[-UserData.Ptr] >> 1;
      if ( (unsigned int)v15 <= v21 )
      {
        v28 = 2 * ((unsigned int)v15 - v19);
        memset_0(*(void **)&UserData.Size, 0, v28);
        v20 = v28 + v17;
        v18 = (_QWORD *)UserData.Ptr;
        goto LABEL_65;
      }
      v22 = v21 >> 1;
      if ( v21 > 0x7FFFFFFFFFFFFFFFLL - (v21 >> 1) )
        goto LABEL_256;
      v23 = v22 + v21;
      if ( v22 + v21 < v16 )
        v23 = v16;
      if ( v23 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_256;
      v24 = 2 * v23;
      if ( 2 * v23 )
      {
        if ( v24 < 0x1000 )
        {
          v18 = operator new(2 * v23);
        }
        else
        {
          if ( v24 + 39 < v24 )
            goto LABEL_256;
          v25 = operator new(v24 + 39);
          if ( !v25 )
            goto LABEL_210;
          v18 = (_QWORD *)(((unsigned __int64)v25 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v18 - 1) = v25;
        }
      }
      else
      {
        v18 = 0;
      }
      memset_0((char *)v18 + 2 * v19, 0, 2 * (v16 - v19));
      memmove_0(v18, (const void *)UserData.Ptr, *(_QWORD *)&UserData.Size - UserData.Ptr);
      if ( UserData.Ptr )
      {
        v26 = 2 * ((__int64)&v113[-UserData.Ptr] >> 1);
        if ( v26 < 0x1000 )
        {
          v27 = (void *)UserData.Ptr;
        }
        else
        {
          v27 = *(void **)(UserData.Ptr - 8);
          if ( UserData.Ptr - (unsigned __int64)v27 - 8 > 0x1F )
            goto LABEL_210;
          v26 += 39LL;
        }
        operator delete(v27, v26);
      }
      UserData.Ptr = (ULONGLONG)v18;
      *(_QWORD *)&UserData.Size = (char *)v18 + 2 * v16;
      v113 = (char *)v18 + v24;
    }
LABEL_66:
    *(_OWORD *)v109 = 0;
    v110 = 0;
    v111 = 0;
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v18 + v29) );
    if ( v29 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    if ( v29 > 7 )
    {
      v31 = v29 | 7;
      if ( (v29 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v31 < 0xA )
          v31 = 10;
        if ( v31 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          goto LABEL_256;
        v32 = 2 * (v31 + 1);
        if ( !v32 )
        {
          v34 = 0;
LABEL_83:
          v109[0] = v34;
          v110 = v29;
          v111 = v31;
          v35 = 2 * v29;
          memcpy_0(v34, v18, v35);
          *(_WORD *)&v34[v35] = 0;
          v18 = (_QWORD *)UserData.Ptr;
          goto LABEL_84;
        }
      }
      else
      {
        v31 = 0x7FFFFFFFFFFFFFFELL;
        v32 = -2;
      }
      if ( v32 < 0x1000 )
      {
        v34 = (char *)operator new(v32);
      }
      else
      {
        if ( v32 + 39 < v32 )
          goto LABEL_256;
        v33 = operator new(v32 + 39);
        if ( !v33 )
          goto LABEL_210;
        v34 = (char *)(((unsigned __int64)v33 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v34 - 1) = v33;
      }
      goto LABEL_83;
    }
    v110 = v29;
    v111 = 7;
    v30 = 2 * v29;
    memcpy_0(v109, v18, v30);
    *(_WORD *)((char *)v109 + v30) = 0;
LABEL_84:
    v36 = v109;
    v37 = v109[0];
    if ( v111 > 7 )
      v36 = (void **)v109[0];
    if ( v110 != 10 )
      goto LABEL_113;
    v38 = (const __m128i *)L"Biometrics";
    v39 = 0;
    v40 = (const __m128i *)v36;
    while ( 1 )
    {
      LOWORD(v41) = _mm_movemask_epi8(_mm_cmpeq_epi16(_mm_loadu_si128(v38), _mm_loadu_si128(v40)));
      if ( (_WORD)v41 != 0xFFFF )
        break;
      v39 += 8LL;
      ++v40;
      ++v38;
      if ( v39 + 8 > v110 )
      {
        v42 = v39 + 4;
        if ( v39 + 4 > v110 )
        {
          v42 = v39;
        }
        else if ( v40->m128i_i64[0] != v38->m128i_i64[0] )
        {
          _BitScanForward64((unsigned __int64 *)&v41, v40->m128i_i64[0] ^ v38->m128i_i64[0]);
          goto LABEL_112;
        }
        if ( v42 < v110 )
        {
          while ( *((_WORD *)v36 + v42) == aBiometrics[v42] )
          {
            if ( ++v42 >= v110 )
              goto LABEL_97;
          }
          goto LABEL_113;
        }
LABEL_97:
        if ( v111 <= 7 )
          goto LABEL_102;
        v43 = 2 * v111 + 2;
        if ( v43 < 0x1000 )
          goto LABEL_101;
        if ( (unsigned __int64)v109[0] - *((_QWORD *)v109[0] - 1) - 8 <= 0x1F )
        {
          v43 = 2 * v111 + 41;
          v37 = (void *)*((_QWORD *)v109[0] - 1);
LABEL_101:
          operator delete(v37, v43);
          v18 = (_QWORD *)UserData.Ptr;
LABEL_102:
          v110 = 0;
          v111 = 7;
          LOWORD(v109[0]) = 0;
          if ( v18 )
          {
            v44 = 2 * ((v113 - (char *)v18) >> 1);
            if ( v44 >= 0x1000 )
            {
              v45 = (_BYTE *)*(v18 - 1);
              if ( (unsigned __int64)((char *)v18 - v45 - 8) <= 0x1F )
              {
                v44 += 39LL;
                goto LABEL_106;
              }
LABEL_226:
              __fastfail(5u);
            }
            v45 = v18;
LABEL_106:
            operator delete(v45, v44);
          }
          goto LABEL_107;
        }
LABEL_210:
        __fastfail(5u);
      }
    }
    _BitScanForward((unsigned int *)&v41, ~(unsigned __int16)v41);
LABEL_112:
    v93 = v41;
LABEL_113:
    LOBYTE(v118.Ptr) = 0;
    HIDWORD(v118.Ptr) = 1;
    *(_QWORD *)&v118.Size = 1;
    v119[0] = 0;
    *(_DWORD *)&v119[4] = 8;
    *(_DWORD *)&v119[8] = 127;
    *(_OWORD *)v120 = 0;
    *(_DWORD *)&v120[16] = 2;
    v121 = 1;
    LODWORD(v122) = 0;
    v46 = v109;
    if ( v111 > 7 )
      v46 = (void **)v109[0];
    v47 = PolicyManager::ReadPassportCspPolicy(*(_QWORD *)&EventDescriptor.Id, v46, &v118);
    if ( v47 >= 0 )
      break;
    if ( v111 > 7 )
    {
      v50 = 2 * v111 + 2;
      v51 = v109[0];
      if ( v50 >= 0x1000 )
      {
        if ( (unsigned __int64)v109[0] - *((_QWORD *)v109[0] - 1) - 8 > 0x1F )
          goto LABEL_210;
        v50 = 2 * v111 + 41;
        v51 = (void *)*((_QWORD *)v109[0] - 1);
      }
      operator delete(v51, v50);
    }
    v110 = 0;
    v111 = 7;
    LOWORD(v109[0]) = 0;
    v45 = (_BYTE *)UserData.Ptr;
    if ( UserData.Ptr )
    {
      v44 = 2 * ((__int64)&v113[-UserData.Ptr] >> 1);
      if ( v44 >= 0x1000 )
      {
        if ( UserData.Ptr - *(_QWORD *)(UserData.Ptr - 8) - 8 > 0x1F )
          goto LABEL_226;
        v44 += 39LL;
        v45 = *(_BYTE **)(UserData.Ptr - 8);
      }
      goto LABEL_106;
    }
LABEL_107:
    v5 = v94;
LABEL_108:
    v6 = dwIndex + 1;
    dwIndex = v6;
    if ( v6 >= cSubKeys )
      goto LABEL_230;
  }
  if ( (unsigned int)dword_18006E000 > 4 )
  {
    v52 = v109;
    if ( v111 > 7 )
      v52 = (void **)v109[0];
    v99 = v52;
    v93 = v47;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v47,
      (unsigned int)byte_180061C15,
      v48,
      v49,
      (__int64)&v93,
      (__int64)&v99);
  }
  if ( (_BYTE)v105 && LOBYTE(v118.Ptr) )
  {
    v53 = v104;
    if ( v118.Reserved == 1 )
      v53 = 1;
    v104 = v53;
    HIDWORD(v105) = v53;
    Size = HIDWORD(v95);
    if ( (int)v118.Size < SHIDWORD(v95) )
      Size = v118.Size;
    HIDWORD(v95) = Size;
    DWORD2(v105) = Size;
    v55 = v95;
    if ( !HIDWORD(v118.Ptr) )
      v55 = 0;
    LODWORD(v95) = v55;
    DWORD1(v105) = v55;
    if ( *(_DWORD *)&v119[4] > *(_DWORD *)&v106[4] )
      goto LABEL_189;
    if ( *(_DWORD *)&v119[4] >= *(_DWORD *)&v106[4] )
    {
      switch ( *(_DWORD *)&v120[8] )
      {
        case 0:
          goto LABEL_145;
        case 1:
          v56 = 2;
          break;
        case 2:
          v56 = 1;
          break;
        default:
LABEL_145:
          v56 = 0;
          break;
      }
      switch ( *(_DWORD *)&v120[4] )
      {
        case 0:
          goto LABEL_151;
        case 1:
          v57 = 2;
          break;
        case 2:
          v57 = 1;
          break;
        default:
LABEL_151:
          v57 = 0;
          break;
      }
      switch ( *(_DWORD *)v120 )
      {
        case 0:
          goto LABEL_157;
        case 1:
          v58 = 2;
          break;
        case 2:
          v58 = 1;
          break;
        default:
LABEL_157:
          v58 = 0;
          break;
      }
      switch ( *(_DWORD *)&v120[12] )
      {
        case 0:
          goto LABEL_163;
        case 1:
          v59 = 2;
          break;
        case 2:
          v59 = 1;
          break;
        default:
LABEL_163:
          v59 = 0;
          break;
      }
      v60 = v56 + v57 + v58 + ((_DWORD)v121 == 0) + v59;
      switch ( *(_DWORD *)&v106[20] )
      {
        case 0:
          goto LABEL_169;
        case 1:
          v61 = 2;
          break;
        case 2:
          v61 = 1;
          break;
        default:
LABEL_169:
          v61 = 0;
          break;
      }
      switch ( *(_DWORD *)&v106[16] )
      {
        case 0:
          goto LABEL_175;
        case 1:
          v62 = 2;
          break;
        case 2:
          v62 = 1;
          break;
        default:
LABEL_175:
          v62 = 0;
          break;
      }
      switch ( *(_DWORD *)&v106[12] )
      {
        case 0:
          goto LABEL_181;
        case 1:
          v63 = 2;
          break;
        case 2:
          v63 = 1;
          break;
        default:
LABEL_181:
          v63 = 0;
          break;
      }
      switch ( *(_DWORD *)&v106[24] )
      {
        case 0:
          goto LABEL_187;
        case 1:
          v64 = 2;
          break;
        case 2:
          v64 = 1;
          break;
        default:
LABEL_187:
          v64 = 0;
          break;
      }
      if ( v60 > v61 + v62 + v63 + (unsigned int)(*(_DWORD *)&v106[32] == 0) + v64 )
      {
LABEL_189:
        v106[0] = v119[0];
        *(_WORD *)&v106[1] = *(_WORD *)&v119[1];
        v106[3] = v119[3];
        *(_QWORD *)&v106[4] = *(_QWORD *)&v119[4];
        *(_OWORD *)&v106[12] = *(_OWORD *)v120;
        *(_QWORD *)&v106[28] = __PAIR64__(v121, *(unsigned int *)&v120[16]);
        *(_QWORD *)&v106[36] = __PAIR64__(v122, HIDWORD(v121));
      }
    }
    if ( v111 > 7 )
    {
      v65 = 2 * v111 + 2;
      v66 = v109[0];
      if ( v65 >= 0x1000 )
      {
        if ( (unsigned __int64)v109[0] - *((_QWORD *)v109[0] - 1) - 8 > 0x1F )
          goto LABEL_210;
        v65 = 2 * v111 + 41;
        v66 = (void *)*((_QWORD *)v109[0] - 1);
      }
      operator delete(v66, v65);
    }
    v5 = ++v94;
    v110 = 0;
    v111 = 7;
    LOWORD(v109[0]) = 0;
    if ( UserData.Ptr )
    {
      v67 = 2 * ((__int64)&v113[-UserData.Ptr] >> 1);
      if ( v67 < 0x1000 )
      {
        v68 = (void *)UserData.Ptr;
      }
      else
      {
        v68 = *(void **)(UserData.Ptr - 8);
        if ( UserData.Ptr - (unsigned __int64)v68 - 8 > 0x1F )
          goto LABEL_226;
        v67 += 39LL;
      }
      operator delete(v68, v67);
    }
    goto LABEL_108;
  }
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    v93 = -2147467260;
    *(_QWORD *)&v120[4] = &v93;
    *(_QWORD *)&v120[12] = 4;
    *(_DWORD *)&v103.Id = 184549376;
    *(_DWORD *)&v103.Level = 2;
    v103.Keyword = 0;
    v118.Ptr = (ULONGLONG)off_18006E008;
    v118.Size = *(unsigned __int16 *)off_18006E008;
    v118.Reserved = 2;
    *(_QWORD *)v119 = &unk_180063A38;
    *(_DWORD *)&v119[8] = 42;
    *(_DWORD *)v120 = 1;
    LODWORD(v99) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v103, 0, 0, 3u, &v118);
  }
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    v93 = -2147467260;
    *(_QWORD *)&v120[4] = &v93;
    *(_QWORD *)&v120[12] = 4;
    *(_DWORD *)&v103.Id = 184549376;
    *(_DWORD *)&v103.Level = 2;
    v103.Keyword = 0;
    v118.Ptr = (ULONGLONG)off_18006E008;
    v118.Size = *(unsigned __int16 *)off_18006E008;
    v118.Reserved = 2;
    *(_QWORD *)v119 = &byte_180061BF7;
    *(_DWORD *)&v119[8] = 29;
    *(_DWORD *)v120 = 1;
    LODWORD(v99) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v103, 0, 0, 3u, &v118);
  }
  if ( v111 > 7 )
  {
    v69 = 2 * v111 + 2;
    if ( v69 < 0x1000 )
    {
      v70 = v109[0];
    }
    else
    {
      v70 = (void *)*((_QWORD *)v109[0] - 1);
      if ( (unsigned __int64)((char *)v109[0] - (char *)v70 - 8) > 0x1F )
        goto LABEL_210;
      v69 = 2 * v111 + 41;
    }
    operator delete(v70, v69);
  }
  v110 = 0;
  v111 = 7;
  LOWORD(v109[0]) = 0;
  if ( UserData.Ptr )
  {
    v71 = 2 * ((__int64)&v113[-UserData.Ptr] >> 1);
    if ( v71 < 0x1000 )
    {
      v72 = (void *)UserData.Ptr;
    }
    else
    {
      v72 = *(void **)(UserData.Ptr - 8);
      if ( UserData.Ptr - (unsigned __int64)v72 - 8 > 0x1F )
        goto LABEL_226;
      v71 += 39LL;
    }
    operator delete(v72, v71);
    UserData = 0;
    v113 = 0;
  }
  v96 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  if ( hKey && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(&v96) )
  {
    v87 = GetLastError();
    if ( v87 > 0 )
      v87 = (unsigned __int16)v87 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v87, v88, v89);
LABEL_256:
    std::_Throw_bad_array_new_length();
  }
  return 2147500036LL;
}

```

## disassembly

```asm
0x18001ee80  mov     [rsp-8+arg_10], rbx
0x18001ee85  push    rbp
0x18001ee86  push    rsi
0x18001ee87  push    rdi
0x18001ee88  push    r12
0x18001ee8a  push    r13
0x18001ee8c  push    r14
0x18001ee8e  push    r15
0x18001ee90  lea     rbp, [rsp-0B0h]
0x18001ee98  sub     rsp, 1B0h
0x18001ee9f  mov     rax, cs:__security_cookie
0x18001eea6  xor     rax, rsp
0x18001eea9  mov     [rbp+0E0h+var_40], rax
0x18001eeb0  mov     rdi, rdx
0x18001eeb3  mov     [rbp+0E0h+var_D8], rdx
0x18001eeb7  mov     qword ptr [rbp+0E0h+EventDescriptor.Id], rcx
0x18001eebb  lea     rsi, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18001eec2  mov     [rsp+1E0h+var_170], rsi
0x18001eec7  xor     r14d, r14d
0x18001eeca  mov     [rsp+1E0h+hKey], r14
0x18001eecf  lea     rax, [rsp+1E0h+hKey]
0x18001eed4  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18001eed9  mov     r9d, 20019h; samDesired
0x18001eedf  xor     r8d, r8d; ulOptions
0x18001eee2  lea     rdx, Src; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x18001eee9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001eef0  call    cs:__imp_RegOpenKeyExW
0x18001eef6  mov     ebx, eax
0x18001eef8  cmp     eax, 2
0x18001eefb  jnz     short loc_18001EF25
0x18001eefd  mov     [rsp+1E0h+var_170], rsi
0x18001ef02  cmp     [rsp+1E0h+hKey], r14
0x18001ef07  jz      short loc_18001EF1B
0x18001ef09  lea     rcx, [rsp+1E0h+var_170]
0x18001ef0e  call    ?InternalClose@?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(void)
0x18001ef13  test    al, al
0x18001ef15  jz      loc_18001FF92
0x18001ef1b  mov     eax, 80070002h
0x18001ef20  jmp     loc_18001FF34
0x18001ef25  test    ebx, ebx
0x18001ef27  jz      loc_18001F00D
0x18001ef2d  mov     eax, cs:dword_18006E000
0x18001ef33  cmp     eax, 2
0x18001ef36  jbe     loc_18001EFDA
0x18001ef3c  mov     dword ptr [rsp+1E0h+var_178], ebx
0x18001ef40  lea     rax, [rsp+1E0h+var_178]
0x18001ef45  mov     [rbp+0E0h+var_90], rax
0x18001ef49  mov     [rbp+0E0h+var_88], 4
0x18001ef51  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x18001ef58  movzx   eax, cs:word_180061C9B
0x18001ef5f  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x18001ef62  mov     [rbp+0E0h+EventDescriptor.Keyword], r14
0x18001ef66  mov     rax, cs:off_18006E008
0x18001ef6d  mov     [rbp+0E0h+var_B0.Ptr], rax
0x18001ef71  movzx   eax, word ptr [rax]
0x18001ef74  mov     [rbp+0E0h+var_B0.Size], eax
0x18001ef77  mov     dword ptr [rbp+0E0h+var_B0.0Ch], 2
0x18001ef7e  lea     rax, byte_180061CA5
0x18001ef85  mov     [rbp+0E0h+var_A0], rax
0x18001ef89  mov     [rbp+0E0h+var_98], 1Ch
0x18001ef90  mov     r13d, 1
0x18001ef96  mov     [rbp+0E0h+var_94], r13d
0x18001ef9a  lea     rax, _TraceLoggingMetadataEnd
0x18001efa1  lea     rdi, _TraceLoggingMetadata
0x18001efa8  sub     eax, edi
0x18001efaa  mov     dword ptr [rsp+1E0h+var_178+4], eax
0x18001efae  mov     eax, dword ptr [rsp+1E0h+var_178+4]
0x18001efb2  lea     rax, [rbp+0E0h+var_B0]
0x18001efb6  mov     [rsp+1E0h+UserData], rax; UserData
0x18001efbb  mov     dword ptr [rsp+1E0h+phkResult], 3; UserDataCount
0x18001efc3  xor     r9d, r9d; RelatedActivityId
0x18001efc6  xor     r8d, r8d; ActivityId
0x18001efc9  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x18001efcd  mov     rcx, cs:RegHandle; RegHandle
0x18001efd4  call    cs:__imp_EventWriteTransfer
0x18001efda  test    ebx, ebx
0x18001efdc  jle     short loc_18001EFE7
0x18001efde  movzx   ebx, bx
0x18001efe1  or      ebx, 80070000h
0x18001efe7  mov     [rsp+1E0h+var_170], rsi
0x18001efec  cmp     [rsp+1E0h+hKey], 0
0x18001eff2  jz      short loc_18001F006
0x18001eff4  lea     rcx, [rsp+1E0h+var_170]
0x18001eff9  call    ?InternalClose@?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(void)
0x18001effe  test    al, al
0x18001f000  jz      loc_18001FFAC
0x18001f006  mov     eax, ebx
0x18001f008  jmp     loc_18001FF34
0x18001f00d  mov     [rbp+0E0h+cSubKeys], r14d
0x18001f011  mov     [rbp+0E0h+cbMaxSubKeyLen], r14d
0x18001f015  mov     [rsp+1E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18001f01a  mov     [rsp+1E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18001f01f  mov     [rsp+1E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18001f024  mov     [rsp+1E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18001f029  mov     [rsp+1E0h+lpcValues], r14; lpcValues
0x18001f02e  mov     [rsp+1E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18001f033  lea     rax, [rbp+0E0h+cbMaxSubKeyLen]
0x18001f037  mov     [rsp+1E0h+UserData], rax; lpcbMaxSubKeyLen
0x18001f03c  lea     rax, [rbp+0E0h+cSubKeys]
0x18001f040  mov     [rsp+1E0h+phkResult], rax; lpcSubKeys
0x18001f045  xor     r9d, r9d; lpReserved
0x18001f048  xor     r8d, r8d; lpcchClass
0x18001f04b  xor     edx, edx; lpClass
0x18001f04d  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001f052  call    cs:__imp_RegQueryInfoKeyW
0x18001f058  mov     ebx, eax
0x18001f05a  test    eax, eax
0x18001f05c  jz      loc_18001F144
0x18001f062  mov     eax, cs:dword_18006E000
0x18001f068  cmp     eax, 2
0x18001f06b  jbe     loc_18001F10F
0x18001f071  mov     dword ptr [rsp+1E0h+var_178], ebx
0x18001f075  lea     rax, [rsp+1E0h+var_178]
0x18001f07a  mov     [rbp+0E0h+var_90], rax
0x18001f07e  mov     [rbp+0E0h+var_88], 4
0x18001f086  mov     dword ptr [rbp+0E0h+EventDescriptor.Id], 0B000000h
0x18001f08d  movzx   eax, cs:word_180061C77
0x18001f094  mov     dword ptr [rbp+0E0h+EventDescriptor.Level], eax
0x18001f097  mov     [rbp+0E0h+EventDescriptor.Keyword], r14
0x18001f09b  mov     rax, cs:off_18006E008
0x18001f0a2  mov     [rbp+0E0h+var_B0.Ptr], rax
0x18001f0a6  movzx   eax, word ptr [rax]
0x18001f0a9  mov     [rbp+0E0h+var_B0.Size], eax
0x18001f0ac  mov     dword ptr [rbp+0E0h+var_B0.0Ch], 2
0x18001f0b3  lea     rax, byte_180061C81
0x18001f0ba  mov     [rbp+0E0h+var_A0], rax
0x18001f0be  mov     [rbp+0E0h+var_98], 18h
0x18001f0c5  mov     r13d, 1
0x18001f0cb  mov     [rbp+0E0h+var_94], r13d
0x18001f0cf  lea     rax, _TraceLoggingMetadataEnd
0x18001f0d6  lea     rdi, _TraceLoggingMetadata
0x18001f0dd  sub     eax, edi
0x18001f0df  mov     dword ptr [rsp+1E0h+var_178+4], eax
0x18001f0e3  mov     eax, dword ptr [rsp+1E0h+var_178+4]
0x18001f0e7  lea     rax, [rbp+0E0h+var_B0]
0x18001f0eb  mov     [rsp+1E0h+UserData], rax; UserData
0x18001f0f0  mov     dword ptr [rsp+1E0h+phkResult], 3; UserDataCount
0x18001f0f8  xor     r9d, r9d; RelatedActivityId
0x18001f0fb  xor     r8d, r8d; ActivityId
0x18001f0fe  lea     rdx, [rbp+0E0h+EventDescriptor]; EventDescriptor
0x18001f102  mov     rcx, cs:RegHandle; RegHandle
0x18001f109  call    cs:__imp_EventWriteTransfer
0x18001f10f  test    ebx, ebx
0x18001f111  jle     short loc_18001F11C
0x18001f113  movzx   ebx, bx
0x18001f116  or      ebx, 80070000h
0x18001f11c  mov     [rsp+1E0h+var_170], rsi
0x18001f121  cmp     [rsp+1E0h+hKey], 0
0x18001f127  jz      loc_18001F006
0x18001f12d  lea     rcx, [rsp+1E0h+var_170]
0x18001f132  call    ?InternalClose@?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::InternalClose(void)
0x18001f137  test    al, al
0x18001f139  jz      loc_18001FF78
0x18001f13f  jmp     loc_18001F006
0x18001f144  mov     r15d, r14d
0x18001f147  inc     [rbp+0E0h+cbMaxSubKeyLen]
0x18001f14a  mov     ebx, r14d
0x18001f14d  mov     [rsp+1E0h+var_17C], ebx
0x18001f151  mov     byte ptr [rbp+0E0h+var_128], bl
0x18001f154  mov     r13d, 1
0x18001f15a  mov     dword ptr [rbp+0E0h+var_128+4], r13d
0x18001f15e  mov     qword ptr [rbp+0E0h+var_128+8], r13
0x18001f162  mov     [rbp+0E0h+var_118], bl
0x18001f165  mov     dword ptr [rbp+0E0h+var_118+4], 8
0x18001f16c  mov     dword ptr [rbp+0E0h+var_118+8], 7Fh
0x18001f173  xorps   xmm0, xmm0
0x18001f176  movdqu  xmmword ptr [rbp+0E0h+var_118+0Ch], xmm0
0x18001f17b  mov     dword ptr [rbp+0E0h+var_FC], 2
0x18001f182  mov     qword ptr [rbp+0E0h+var_FC+4], r13
0x18001f186  mov     dword ptr [rbp+0E0h+var_FC+0Ch], r14d
0x18001f18a  lea     rcx, [rbp+0E0h+var_128]
0x18001f18e  call    ?Initialize@NgcPolicy@1@QEAAJW4_NGC_BIOMETRICS_POLICY@@W4_NGC_SMART_CARD_POLICY@@W4_NGC_HARDWARE_POLICY@@@Z; NgcPolicy::NgcPolicy::Initialize(_NGC_BIOMETRICS_POLICY,_NGC_SMART_CARD_POLICY,_NGC_HARDWARE_POLICY)
0x18001f193  mov     eax, r14d
0x18001f196  mov     [rbp+0E0h+dwIndex], eax
0x18001f199  lea     r12, _TraceLoggingMetadataEnd
0x18001f1a0  lea     rsi, _TraceLoggingMetadata
0x18001f1a7  cmp     [rbp+0E0h+cSubKeys], r14d
0x18001f1ab  jbe     loc_18001FE04
0x18001f1b1  mov     ecx, dword ptr [rbp+0E0h+var_128+0Ch]
0x18001f1b4  mov     [rbp+0E0h+var_130], ecx
0x18001f1b7  mov     ecx, dword ptr [rbp+0E0h+var_128+8]
0x18001f1ba  mov     dword ptr [rsp+1E0h+var_178+4], ecx
0x18001f1be  mov     edx, dword ptr [rbp+0E0h+var_128+4]
0x18001f1c1  mov     dword ptr [rsp+1E0h+var_178], edx
0x18001f1c5  nop     word ptr [rax+rax+00000000h]
0x18001f1d0  mov     ebx, [rbp+0E0h+cbMaxSubKeyLen]
0x18001f1d3  xorps   xmm0, xmm0
0x18001f1d6  movdqu  xmmword ptr [rbp+0E0h+var_B0.Ptr], xmm0
0x18001f1db  mov     [rbp+0E0h+var_A0], r14
0x18001f1df  test    rbx, rbx
0x18001f1e2  jz      short loc_18001F24D
0x18001f1e4  add     rbx, rbx
0x18001f1e7  jnz     short loc_18001F1EE
0x18001f1e9  mov     rax, r14
0x18001f1ec  jmp     short loc_18001F22B
0x18001f1ee  cmp     rbx, 1000h
0x18001f1f5  jb      short loc_18001F223
0x18001f1f7  lea     rcx, [rbx+27h]; Size
0x18001f1fb  cmp     rcx, rbx
0x18001f1fe  jbe     loc_18001FFC6
0x18001f204  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f209  mov     rcx, rax
0x18001f20c  test    rax, rax
0x18001f20f  jz      loc_18001FDDE
0x18001f215  add     rax, 27h ; '''
0x18001f219  and     rax, 0FFFFFFFFFFFFFFE0h
0x18001f21d  mov     [rax-8], rcx
0x18001f221  jmp     short loc_18001F22B
0x18001f223  mov     rcx, rbx; Size
0x18001f226  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f22b  mov     [rbp+0E0h+var_B0.Ptr], rax
0x18001f22f  lea     rdi, [rax+rbx]
0x18001f233  mov     [rbp+0E0h+var_A0], rdi
0x18001f237  mov     r8, rbx; Size
0x18001f23a  xor     edx, edx; Val
0x18001f23c  mov     rcx, rax; void *
0x18001f23f  call    memset_0
0x18001f244  mov     qword ptr [rbp+0E0h+var_B0.Size], rdi
0x18001f248  mov     eax, [rbp+0E0h+dwIndex]
0x18001f24b  jmp     short loc_18001F251
0x18001f24d  mov     rdi, qword ptr [rbp+0E0h+var_B0.Size]
0x18001f251  mov     r8, [rbp+0E0h+var_B0.Ptr]; lpName
0x18001f255  sub     rdi, r8
0x18001f258  sar     rdi, 1
0x18001f25b  mov     [rbp+0E0h+cchName], edi
0x18001f25e  mov     [rsp+1E0h+lpcValues], r14; lpftLastWriteTime
0x18001f263  mov     [rsp+1E0h+lpcbMaxClassLen], r14; lpcchClass
0x18001f268  mov     [rsp+1E0h+UserData], r14; lpClass
0x18001f26d  mov     [rsp+1E0h+phkResult], r14; lpReserved
0x18001f272  lea     r9, [rbp+0E0h+cchName]; lpcchName
0x18001f276  mov     edx, eax; dwIndex
0x18001f278  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001f27d  call    cs:__imp_RegEnumKeyExW
0x18001f283  cmp     eax, 103h
0x18001f288  jz      loc_18001FDA7
0x18001f28e  test    eax, eax
0x18001f290  jz      loc_18001F38E
0x18001f296  mov     ecx, cs:dword_18006E000
0x18001f29c  cmp     ecx, 3
0x18001f29f  jbe     loc_18001F337
0x18001f2a5  mov     dword ptr [rbp+0E0h+var_158], eax
0x18001f2a8  lea     rax, [rbp+0E0h+var_158]
0x18001f2ac  mov     qword ptr [rbp+0E0h+var_64+4], rax
0x18001f2b3  mov     qword ptr [rbp+0E0h+var_64+0Ch], 4
0x18001f2be  mov     dword ptr [rbp+0E0h+var_140.Id], 0B000000h
0x18001f2c5  movzx   eax, cs:word_180061C4F
0x18001f2cc  mov     dword ptr [rbp+0E0h+var_140.Level], eax
0x18001f2cf  mov     [rbp+0E0h+var_140.Keyword], r14
0x18001f2d3  mov     rax, cs:off_18006E008
0x18001f2da  mov     [rbp+0E0h+var_80.Ptr], rax
0x18001f2de  movzx   eax, word ptr [rax]
0x18001f2e1  mov     [rbp+0E0h+var_80.Size], eax
0x18001f2e4  mov     dword ptr [rbp+0E0h+var_80.0Ch], 2
0x18001f2eb  lea     rax, byte_180061C59
0x18001f2f2  mov     qword ptr [rbp+0E0h+var_70], rax
0x18001f2f6  mov     dword ptr [rbp+0E0h+var_70+8], 1Ch
0x18001f2fd  mov     dword ptr [rbp+0E0h+var_64], r13d
0x18001f301  mov     rax, r12
0x18001f304  sub     eax, esi
0x18001f306  mov     [rsp+1E0h+var_180], eax
0x18001f30a  mov     eax, [rsp+1E0h+var_180]
0x18001f30e  lea     rax, [rbp+0E0h+var_80]
0x18001f312  mov     [rsp+1E0h+UserData], rax; UserData
0x18001f317  mov     dword ptr [rsp+1E0h+phkResult], 3; UserDataCount
0x18001f31f  xor     r9d, r9d; RelatedActivityId
0x18001f322  xor     r8d, r8d; ActivityId
0x18001f325  lea     rdx, [rbp+0E0h+var_140]; EventDescriptor
0x18001f329  mov     rcx, cs:RegHandle; RegHandle
0x18001f330  call    cs:__imp_EventWriteTransfer
0x18001f336  nop
0x18001f337  mov     rcx, [rbp+0E0h+var_B0.Ptr]; void *
0x18001f33b  test    rcx, rcx
0x18001f33e  jz      loc_18001F74E
0x18001f344  mov     rax, [rbp+0E0h+var_A0]
0x18001f348  sub     rax, rcx
0x18001f34b  sar     rax, 1
0x18001f34e  lea     rdx, [rax+rax]; unsigned __int64
0x18001f352  cmp     rdx, 1000h
0x18001f359  jb      short loc_18001F381
0x18001f35b  mov     rax, [rcx-8]
0x18001f35f  sub     rcx, rax
0x18001f362  sub     rcx, 8
0x18001f366  cmp     rcx, 1Fh
0x18001f36a  ja      loc_18001FDDE
0x18001f370  add     rdx, 27h ; '''; unsigned __int64
0x18001f374  mov     rcx, rax; void *
0x18001f377  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f37c  jmp     loc_18001F74E
0x18001f381  mov     rax, rcx
0x18001f384  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f389  jmp     loc_18001F74E
0x18001f38e  mov     eax, [rbp+0E0h+cchName]
0x18001f391  inc     eax
0x18001f393  mov     [rbp+0E0h+cchName], eax
0x18001f396  mov     ebx, eax
0x18001f398  mov     rsi, qword ptr [rbp+0E0h+var_B0.Size]
0x18001f39c  mov     r14, rsi
0x18001f39f  mov     rdi, [rbp+0E0h+var_B0.Ptr]
0x18001f3a3  sub     r14, rdi
0x18001f3a6  sar     r14, 1
  ... truncated ...
```
