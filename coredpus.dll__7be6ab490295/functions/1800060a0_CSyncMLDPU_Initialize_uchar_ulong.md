# CSyncMLDPU::Initialize(uchar *,ulong)

- ea: `0x1800060a0`
- end: `0x180007098`
- name: `?Initialize@CSyncMLDPU@@UEAAJPEAEK@Z`
- size: `4088`
- prototype: `__int64 __fastcall(CSyncMLDPU *this, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800060a0`
- `0x1800107bc`
- `0x1800109b0`
- `0x180010ba4`
- `0x180013d04`
- `0x180014330`
- `0x1800146e4`
- `0x180014c60`
- `0x180015114`
- `0x180015174`
- `0x180015c7b`
- `0x180017aec`
- `0x18001d5dc`
- `0x18001d670`
- `0x18001d7e0`
- `0x18001e32c`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800061fb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000701a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800061fb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000701a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006345`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006345`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800060f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007034`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007034`
- `DMCmnUtils!CopyString` at `0x18000623f`
- `DMCmnUtils!CopyString` at `0x180006264`
- `DMCmnUtils!CopyString` at `0x18000623f`
- `DMCmnUtils!CopyString` at `0x180006264`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000629f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000629f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800064c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006308`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006308`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006710`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006710`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006f34`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180006416`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180006416`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006455`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006455`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006871`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006871`

## string_xrefs

- `0x1800064b7`: `Software\Microsoft\Provisioning\SyncML\RebootRequiredURIs`
- `0x180006291`: `Software\Microsoft\Provisioning\SyncML\NormalReplaceURIs`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::Initialize(CSyncMLDPU *this, unsigned __int8 *a2, int a3)
{
  unsigned __int8 *v4; // r12
  CSyncMLDPU *v5; // rsi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  HLOCAL v7; // r14
  int Instance; // r13d
  LSTATUS v9; // eax
  unsigned __int64 v10; // rax
  size_t v11; // rbx
  HLOCAL v12; // rcx
  DWORD v13; // ecx
  unsigned __int64 v14; // rax
  DWORD v15; // ebx
  __int64 v16; // rcx
  unsigned int v17; // eax
  void *v18; // rdx
  unsigned int v19; // r8d
  HKEY v20; // rcx
  wil *v21; // rcx
  char *v22; // rdi
  char **v23; // rbx
  char **i; // rsi
  unsigned __int64 v25; // rdx
  char *v26; // rax
  const struct std::nothrow_t *v27; // rdx
  char *v28; // rcx
  char *v29; // rax
  const struct std::nothrow_t *v30; // rdx
  char *v31; // rcx
  char **v32; // rbx
  char **v33; // rdi
  unsigned __int64 v34; // rdx
  char *v35; // rax
  const struct std::nothrow_t *v36; // rdx
  char *v37; // rcx
  const struct std::nothrow_t *v38; // rdx
  char **v39; // rcx
  unsigned int v40; // r14d
  __int64 v41; // rdi
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // rax
  _QWORD *v48; // rax
  char *v49; // rsi
  unsigned __int64 v50; // rdi
  void **v51; // r14
  unsigned __int64 v52; // rbx
  size_t v53; // rcx
  void *v54; // rax
  void *v55; // rax
  void *v56; // rcx
  unsigned __int64 v57; // rdi
  void **v58; // r14
  _QWORD *v59; // r12
  unsigned __int64 v60; // rbx
  size_t v61; // rcx
  void *v62; // rax
  void *v63; // rax
  void *v64; // rcx
  HKEY v65; // rdi
  __int64 v66; // rcx
  float v67; // xmm0_4
  unsigned __int64 v68; // rbx
  float v69; // xmm3_4
  float v70; // xmm2_4
  __int64 v71; // rcx
  float v72; // xmm0_4
  unsigned __int64 v73; // rcx
  unsigned __int64 v74; // rax
  unsigned __int64 v75; // rcx
  __int64 v76; // r8
  _QWORD *v77; // rbx
  _QWORD *v78; // rcx
  const wchar_t *v79; // rdi
  unsigned __int64 v80; // r12
  const wchar_t *v81; // rdx
  unsigned __int64 v82; // r14
  const wchar_t *v83; // rcx
  size_t v84; // r8
  int v85; // eax
  size_t v86; // r12
  size_t v87; // r14
  size_t v88; // r8
  int v89; // eax
  _QWORD *v90; // r8
  _QWORD *v91; // r10
  __int64 v92; // rdx
  __int64 v93; // rax
  _QWORD *v94; // r9
  _QWORD *v95; // rbx
  const struct std::nothrow_t *v96; // rdx
  const struct std::nothrow_t *v97; // rdx
  const struct std::nothrow_t *v98; // rdx
  void *v99; // rcx
  const struct std::nothrow_t *v100; // rdx
  void *v101; // rcx
  unsigned int UserDataCount; // [rsp+20h] [rbp-188h]
  unsigned int v104; // [rsp+60h] [rbp-148h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-144h] BYREF
  HLOCAL v106; // [rsp+68h] [rbp-140h]
  HKEY hKey; // [rsp+70h] [rbp-138h] BYREF
  DWORD cValues; // [rsp+78h] [rbp-130h] BYREF
  DWORD cchValueName; // [rsp+7Ch] [rbp-12Ch] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-128h] BYREF
  void *v111[2]; // [rsp+88h] [rbp-120h] BYREF
  __int64 v112; // [rsp+98h] [rbp-110h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A0h] [rbp-108h] BYREF
  DWORD Type; // [rsp+B0h] [rbp-F8h] BYREF
  _QWORD *v115; // [rsp+B8h] [rbp-F0h]
  CSyncMLDPU *v116; // [rsp+C0h] [rbp-E8h]
  __int64 v117; // [rsp+C8h] [rbp-E0h]
  HLOCAL hMem; // [rsp+D0h] [rbp-D8h]
  void *v119; // [rsp+D8h] [rbp-D0h]
  _QWORD *v120; // [rsp+E0h] [rbp-C8h]
  _QWORD *v121; // [rsp+E8h] [rbp-C0h]
  unsigned __int8 *v122; // [rsp+F0h] [rbp-B8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+F8h] [rbp-B0h]
  void *Src[2]; // [rsp+100h] [rbp-A8h] BYREF
  unsigned __int64 v125; // [rsp+110h] [rbp-98h]
  unsigned __int64 v126; // [rsp+118h] [rbp-90h]
  void *v127[2]; // [rsp+120h] [rbp-88h] BYREF
  unsigned __int64 v128; // [rsp+130h] [rbp-78h]
  unsigned __int64 v129; // [rsp+138h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+140h] [rbp-68h] BYREF
  char *v131; // [rsp+150h] [rbp-58h]
  int v132; // [rsp+158h] [rbp-50h]
  int v133; // [rsp+15Ch] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v4 = a2;
  v122 = a2;
  v5 = this;
  v116 = this;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 472);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  lpCriticalSection = v6;
  phkResult = 0;
  v7 = 0;
  v106 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  Type = 0;
  *((_DWORD *)v5 + 88) = *((_DWORD *)v4 + 6);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v131 = byte_180035E73;
    v132 = 34;
    v133 = 1;
    v104 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
  }
  if ( a3 != 40 )
  {
    Instance = -2147024809;
    goto LABEL_211;
  }
  if ( *((_DWORD *)v5 + 6) )
  {
    Instance = -2147023649;
    goto LABEL_211;
  }
  *((_DWORD *)v5 + 63) = *((_DWORD *)v4 + 1);
  Instance = CopyString(*((const unsigned __int16 **)v4 + 1), 0xFFFFFFFF, (unsigned __int16 **)v5 + 41);
  if ( Instance >= 0 )
  {
    Instance = CopyString(*((const unsigned __int16 **)v4 + 2), 0xFFFFFFFF, (unsigned __int16 **)v5 + 43);
    if ( Instance >= 0 )
    {
      v9 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Provisioning\\SyncML\\NormalReplaceURIs",
             0,
             0x20019u,
             &phkResult);
      if ( v9 != 2 )
      {
        if ( v9 )
        {
          if ( v9 <= 0 )
          {
            Instance = v9;
            goto LABEL_211;
          }
          goto LABEL_40;
        }
        v9 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
        if ( v9 )
        {
          if ( v9 <= 0 )
          {
            Instance = v9;
            goto LABEL_211;
          }
          goto LABEL_40;
        }
        if ( cValues )
        {
          v10 = 8LL * cValues;
          if ( v10 <= 0xFFFFFFFF )
          {
            v11 = (unsigned int)v10;
            v12 = LocalAlloc(0, (unsigned int)v10);
            *((_QWORD *)v5 + 37) = v12;
            if ( !v12 )
            {
              Instance = -2147024882;
              goto LABEL_211;
            }
            *((_DWORD *)v5 + 62) = cValues;
            memset_0(v12, 0, v11);
            v13 = cbMaxValueNameLen + 1;
            if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
            {
              cbMaxValueNameLen = -1;
            }
            else
            {
              ++cbMaxValueNameLen;
              v14 = 2LL * v13;
              if ( v14 <= 0xFFFFFFFF )
              {
                v7 = LocalAlloc(0, (unsigned int)v14);
                v106 = v7;
                if ( !v7 )
                {
                  Instance = -2147024882;
                  goto LABEL_211;
                }
                v15 = 0;
                Instance = 0;
                if ( *((_DWORD *)v5 + 62) )
                {
                  while ( 1 )
                  {
                    cchValueName = cbMaxValueNameLen;
                    v9 = RegEnumValueW(phkResult, v15, (LPWSTR)v7, &cchValueName, 0, &Type, 0, 0);
                    Instance = v9;
                    if ( v9 )
                      break;
                    Instance = CoCreateInstance(
                                 &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
                                 0,
                                 1u,
                                 &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
                                 (LPVOID *)(*((_QWORD *)v5 + 37) + 8LL * v15));
                    if ( Instance < 0 )
                      goto LABEL_211;
                    v16 = *(_QWORD *)(*((_QWORD *)v5 + 37) + 8LL * v15);
                    Instance = (*(__int64 (__fastcall **)(__int64, HLOCAL))(*(_QWORD *)v16 + 40LL))(v16, v7);
                    if ( Instance < 0 )
                      goto LABEL_211;
                    if ( ++v15 >= *((_DWORD *)v5 + 62) )
                      goto LABEL_28;
                  }
                  if ( v9 <= 0 )
                    goto LABEL_211;
LABEL_40:
                  Instance = (unsigned __int16)v9 | 0x80070000;
                  goto LABEL_211;
                }
                goto LABEL_28;
              }
            }
          }
          Instance = -2147024362;
          goto LABEL_211;
        }
      }
LABEL_28:
      hKey = 0;
      v17 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Provisioning\\SyncML\\RebootRequiredURIs",
              0,
              0x20019u,
              &hKey);
      if ( v17 )
        wil::details::in1diag3::_Log_Win32(retaddr, v18, v19, (const char *)v17, UserDataCount);
      v20 = hKey;
      if ( hKey )
      {
        try
        {
          *(_OWORD *)v111 = 0;
          v112 = 0;
          ForEachRegValue__lambda_adf4322f45f66e7bf7724f37560fceae_(hKey);
        }
        catch ( ... )
        {
          v104 = wil::ResultFromCaughtException(v21);
          if ( hKey )
            RegCloseKey(hKey);
          Instance = v104;
          v7 = v106;
          goto LABEL_211;
        }
        v22 = (char *)v5 + 448;
        if ( (void **)((char *)v5 + 448) != v111 )
        {
          v23 = *(char ***)v22;
          if ( *(_QWORD *)v22 )
          {
            for ( i = (char **)*((_QWORD *)v5 + 57); v23 != i; v23 += 4 )
            {
              v25 = (unsigned __int64)v23[3];
              if ( v25 > 7 )
              {
                v26 = *v23;
                v27 = (const struct std::nothrow_t *)(2 * v25 + 2);
                if ( (unsigned __int64)v27 < 0x1000 )
                {
                  v28 = *v23;
                }
                else
                {
                  v28 = (char *)*((_QWORD *)v26 - 1);
                  if ( (unsigned __int64)(v26 - v28 - 8) > 0x1F )
                    goto LABEL_49;
                  v27 = (const struct std::nothrow_t *)((char *)v27 + 39);
                }
                operator delete(v28, v27);
              }
              v23[2] = 0;
              v23[3] = (char *)7;
              *(_WORD *)v23 = 0;
            }
            v29 = *(char **)v22;
            v30 = (const struct std::nothrow_t *)((*((_QWORD *)v22 + 2) - *(_QWORD *)v22) & 0xFFFFFFFFFFFFFFE0uLL);
            if ( (unsigned __int64)v30 < 0x1000 )
            {
              v31 = *(char **)v22;
            }
            else
            {
              v31 = (char *)*((_QWORD *)v29 - 1);
              if ( (unsigned __int64)(v29 - v31 - 8) > 0x1F )
LABEL_49:
                __fastfail(5u);
              v30 = (const struct std::nothrow_t *)((char *)v30 + 39);
            }
            operator delete(v31, v30);
            v5 = v116;
          }
          *(void **)v22 = v111[0];
          *((void **)v22 + 1) = v111[1];
          *((_QWORD *)v22 + 2) = v112;
          *(_OWORD *)v111 = 0;
          v112 = 0;
        }
        v32 = (char **)v111[0];
        if ( v111[0] )
        {
          v33 = (char **)v111[1];
          if ( v111[0] != v111[1] )
          {
            do
            {
              v34 = (unsigned __int64)v32[3];
              if ( v34 > 7 )
              {
                v35 = *v32;
                v36 = (const struct std::nothrow_t *)(2 * v34 + 2);
                if ( (unsigned __int64)v36 < 0x1000 )
                {
                  v37 = *v32;
                }
                else
                {
                  v37 = (char *)*((_QWORD *)v35 - 1);
                  if ( (unsigned __int64)(v35 - v37 - 8) > 0x1F )
                    goto LABEL_66;
                  v36 = (const struct std::nothrow_t *)((char *)v36 + 39);
                }
                operator delete(v37, v36);
              }
              v32[2] = 0;
              v32[3] = (char *)7;
              *(_WORD *)v32 = 0;
              v32 += 4;
            }
            while ( v32 != v33 );
            v32 = (char **)v111[0];
          }
          v38 = (const struct std::nothrow_t *)((v112 - (_QWORD)v32) & 0xFFFFFFFFFFFFFFE0uLL);
          if ( (unsigned __int64)v38 < 0x1000 )
          {
            v39 = v32;
          }
          else
          {
            v39 = (char **)*(v32 - 1);
            if ( (unsigned __int64)((char *)v32 - (char *)v39 - 8) > 0x1F )
LABEL_66:
              __fastfail(5u);
            v38 = (const struct std::nothrow_t *)((char *)v38 + 39);
          }
          operator delete(v39, v38);
          *(_OWORD *)v111 = 0;
          v112 = 0;
        }
        v20 = hKey;
      }
      if ( v20 )
        RegCloseKey(v20);
      *((_DWORD *)v5 + 8) = *(_DWORD *)v4;
      v40 = 0;
      v104 = 0;
LABEL_73:
      if ( v40 >= *((_DWORD *)v4 + 7) )
      {
        *((_DWORD *)v5 + 6) = 1;
        v7 = v106;
        goto LABEL_211;
      }
      v41 = *((_QWORD *)v4 + 4);
      if ( !v41 )
      {
        Instance = -2147024809;
        v7 = v106;
        goto LABEL_211;
      }
      v42 = *(_QWORD *)(v41 + 16LL * v40);
      *(_OWORD *)Src = 0;
      v125 = 0;
      v126 = 0;
      v43 = -1;
      do
        ++v43;
      while ( *(_WORD *)(v42 + 2 * v43) );
      std::wstring::_Construct<1,unsigned short const *>(Src);
      v44 = *(_QWORD *)(v41 + 16LL * v40 + 8);
      *(_OWORD *)v127 = 0;
      v128 = 0;
      v129 = 0;
      v45 = -1;
      do
        ++v45;
      while ( *(_WORD *)(v44 + 2 * v45) );
      std::wstring::_Construct<1,unsigned short const *>(v127);
      v47 = *((_QWORD *)v4 + 4);
      if ( !*(_QWORD *)(v47 + 16LL * v40) || !*(_QWORD *)(v47 + 16LL * v40 + 8) )
      {
        v59 = v127[0];
        v95 = Src[0];
        goto LABEL_182;
      }
      hMem = 0;
      hKey = (HKEY)((char *)v5 + 360);
      v117 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v46, Src);
      std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
        (char *)v5 + 360,
        &EventDescriptor,
        Src,
        v117);
      if ( EventDescriptor.Keyword )
      {
        if ( hMem )
          LocalFree(hMem);
        if ( v129 > 7 )
        {
          v98 = (const struct std::nothrow_t *)(2 * v129 + 2);
          if ( (unsigned __int64)v98 >= 0x1000 )
          {
            v99 = (void *)*((_QWORD *)v127[0] - 1);
            if ( (unsigned __int64)((char *)v127[0] - (char *)v99 - 8) <= 0x1F )
            {
              v98 = (const struct std::nothrow_t *)(2 * v129 + 41);
              goto LABEL_200;
            }
LABEL_209:
            __fastfail(5u);
          }
          v99 = v127[0];
LABEL_200:
          operator delete(v99, v98);
        }
        if ( v126 > 7 )
        {
          v100 = (const struct std::nothrow_t *)(2 * v126 + 2);
          if ( (unsigned __int64)v100 < 0x1000 )
          {
            v101 = Src[0];
          }
          else
          {
            v101 = (void *)*((_QWORD *)Src[0] - 1);
            if ( (unsigned __int64)((char *)Src[0] - (char *)v101 - 8) > 0x1F )
              goto LABEL_209;
            v100 = (const struct std::nothrow_t *)(2 * v126 + 41);
          }
          operator delete(v101, v100);
        }
        Instance = -2147024809;
        v7 = v106;
        goto LABEL_211;
      }
      if ( *((_QWORD *)v5 + 47) == 0x333333333333333LL )
        std::_Xlength_error("unordered_map/set too long");
      UserData.Ptr = (ULONGLONG)v5 + 368;
      *(_QWORD *)&UserData.Size = 0;
      v48 = operator new(0x50u);
      v121 = v48;
      *(_QWORD *)&UserData.Size = v48;
      v49 = (char *)(v48 + 2);
      v120 = v48 + 2;
      *((_OWORD *)v48 + 1) = 0;
      v48[4] = 0;
      v48[5] = 0;
      v50 = v125;
      v51 = Src;
      v119 = Src[0];
      if ( v126 > 7 )
        v51 = (void **)Src[0];
      if ( v125 > 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      if ( v125 <= 7 )
      {
        v48[4] = v125;
        v48[5] = 7;
        *(_OWORD *)v49 = *(_OWORD *)v51;
        goto LABEL_108;
      }
      v52 = v125 | 7;
      if ( (v125 | 7) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v52 < 0xA )
          v52 = 10;
        if ( v52 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
        v53 = 2 * (v52 + 1);
        if ( !v53 )
        {
          v54 = 0;
LABEL_107:
          *(_QWORD *)v49 = v54;
          *((_QWORD *)v49 + 2) = v50;
          *((_QWORD *)v49 + 3) = v52;
          memcpy_0(v54, v51, 2 * v50 + 2);
LABEL_108:
          *((_OWORD *)v49 + 2) = 0;
          *((_QWORD *)v49 + 6) = 0;
          *((_QWORD *)v49 + 7) = 0;
          v57 = v128;
          v58 = v127;
          v59 = v127[0];
          v115 = v127[0];
          if ( v129 > 7 )
            v58 = (void **)v127[0];
          if ( v128 > 0x7FFFFFFFFFFFFFFELL )
            std::_Xlen_string();
          if ( v128 <= 7 )
          {
            *((_QWORD *)v49 + 6) = v128;
            *((_QWORD *)v49 + 7) = 7;
            *((_OWORD *)v49 + 2) = *(_OWORD *)v58;
LABEL_128:
            v65 = hKey;
            v66 = *((_QWORD *)hKey + 2) + 1LL;
            if ( v66 < 0 )
              v67 = (float)(v66 & 1 | (unsigned int)((unsigned __int64)v66 >> 1))
                  + (float)(v66 & 1 | (unsigned int)((unsigned __int64)v66 >> 1));
            else
              v67 = (float)(int)v66;
            v68 = *((_QWORD *)hKey + 7);
            v69 = *((float *)hKey + 1);
            if ( (v68 & 0x8000000000000000uLL) != 0LL )
            {
              v71 = *((_QWORD *)hKey + 7) & 1LL | (v68 >> 1);
              v70 = (float)(int)v71 + (float)(int)v71;
            }
            else
            {
              v70 = (float)(int)v68;
            }
            if ( (float)(v67 / v70) <= v69 )
            {
              v78 = *(_QWORD **)&EventDescriptor.Id;
              goto LABEL_173;
            }
            v72 = o_ceilf_0(v67 / v69);
            v73 = 0;
            if ( v72 >= 9.223372e18 )
            {
              v72 = v72 - 9.223372e18;
              if ( v72 < 9.223372e18 )
                v73 = 0x8000000000000000uLL;
            }
            v74 = v73 + (unsigned int)(int)v72;
            v75 = 8;
            if ( v74 > 8 )
              v75 = v74;
            if ( v68 < v75 )
            {
              if ( v68 >= 0x200 || (v68 *= 8LL, v68 < v75) )
                v68 = v75;
            }
            std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
              v65,
              v68);
            v76 = *((_QWORD *)v65 + 3);
            v77 = *(_QWORD **)(v76 + 16 * (*((_QWORD *)v65 + 6) & v117) + 8);
            v78 = (_QWORD *)*((_QWORD *)v65 + 1);
            if ( v77 == v78 )
            {
              *(_QWORD *)&EventDescriptor.Id = *((_QWORD *)v65 + 1);
              EventDescriptor.Keyword = 0;
              goto LABEL_173;
            }
            v120 = *(_QWORD **)(v76 + 16 * (*((_QWORD *)v65 + 6) & v117));
            while ( 1 )
            {
              v79 = (const wchar_t *)(v77 + 2);
              v80 = v77[4];
              v81 = (const wchar_t *)(v77 + 2);
              if ( v77[5] > 7u )
                v81 = *(const wchar_t **)v79;
              v82 = *((_QWORD *)v49 + 2);
              if ( *((_QWORD *)v49 + 3) <= 7u )
                v83 = (const wchar_t *)v49;
              else
                v83 = *(const wchar_t **)v49;
              v84 = *((_QWORD *)v49 + 2);
              if ( v80 < v82 )
                v84 = v77[4];
              v85 = wmemcmp(v83, v81, v84);
              if ( v85 )
              {
                if ( v85 >= 0 )
                {
LABEL_156:
                  v86 = *((_QWORD *)v49 + 2);
                  if ( *((_QWORD *)v49 + 3) > 7u )
                    v49 = *(char **)v49;
                  v87 = v77[4];
                  if ( v77[5] > 7u )
                    v79 = *(const wchar_t **)v79;
                  v88 = v77[4];
                  if ( v86 < v87 )
                    v88 = v86;
                  v89 = wmemcmp(v79, (const wchar_t *)v49, v88);
                  if ( v89 )
                  {
                    if ( v89 >= 0 )
                      goto LABEL_164;
                  }
                  else if ( v87 >= v86 )
                  {
LABEL_164:
                    v78 = (_QWORD *)*v77;
                    goto LABEL_165;
                  }
                  v78 = (_QWORD *)*v77;
                  v77 = 0;
LABEL_165:
                  v59 = v115;
                  v65 = hKey;
                  *(_QWORD *)&EventDescriptor.Id = v78;
                  EventDescriptor.Keyword = (ULONGLONG)v77;
LABEL_173:
                  *(_QWORD *)&UserData.Size = 0;
                  v90 = (_QWORD *)v78[1];
                  ++*((_QWORD *)v65 + 2);
                  v91 = v121;
                  *v121 = v78;
                  v91[1] = v90;
                  *v90 = v91;
                  v78[1] = v91;
                  v92 = *((_QWORD *)v65 + 3);
                  v93 = 2 * (v117 & *((_QWORD *)v65 + 6));
                  v94 = *(_QWORD **)(v92 + 16 * (v117 & *((_QWORD *)v65 + 6)));
                  if ( v94 == *((_QWORD **)v65 + 1) )
                  {
                    *(_QWORD *)(v92 + 16 * (v117 & *((_QWORD *)v65 + 6))) = v91;
                    goto LABEL_178;
                  }
                  if ( v94 == v78 )
                  {
                    *(_QWORD *)(v92 + 16 * (v117 & *((_QWORD *)v65 + 6))) = v91;
                  }
                  else if ( *(_QWORD **)(v92 + 16 * (v117 & *((_QWORD *)v65 + 6)) + 8) == v90 )
                  {
LABEL_178:
                    *(_QWORD *)(v92 + 8 * v93 + 8) = v91;
                  }
                  if ( hMem )
                    LocalFree(hMem);
                  v40 = v104;
                  v5 = v116;
                  v95 = v119;
LABEL_182:
                  if ( v129 <= 7 )
                    goto LABEL_187;
                  v96 = (const struct std::nothrow_t *)(2 * v129 + 2);
                  if ( (unsigned __int64)v96 < 0x1000 )
                    goto LABEL_186;
                  if ( (unsigned __int64)v59 - *(v59 - 1) - 8 > 0x1F )
                    goto LABEL_209;
                  v96 = (const struct std::nothrow_t *)(2 * v129 + 41);
                  v59 = (_QWORD *)*(v59 - 1);
LABEL_186:
                  operator delete(v59, v96);
LABEL_187:
                  if ( v126 <= 7 )
                    goto LABEL_192;
                  v97 = (const struct std::nothrow_t *)(2 * v126 + 2);
                  if ( (unsigned __int64)v97 < 0x1000 )
                    goto LABEL_191;
                  if ( (unsigned __int64)v95 - *(v95 - 1) - 8 > 0x1F )
                    goto LABEL_209;
                  v97 = (const struct std::nothrow_t *)(2 * v126 + 41);
                  v95 = (_QWORD *)*(v95 - 1);
LABEL_191:
                  operator delete(v95, v97);
LABEL_192:
                  v104 = ++v40;
                  v4 = v122;
                  goto LABEL_73;
                }
              }
              else if ( v82 >= v80 )
              {
                goto LABEL_156;
              }
              if ( v77 == v120 )
              {
                v78 = v77;
                v77 = 0;
                goto LABEL_165;
              }
              v77 = (_QWORD *)v77[1];
            }
          }
          v60 = v128 | 7;
          if ( (v128 | 7) <= 0x7FFFFFFFFFFFFFFELL )
          {
            if ( v60 < 0xA )
              v60 = 10;
            if ( v60 + 1 > 0x7FFFFFFFFFFFFFFFLL )
              std::_Throw_bad_array_new_length();
            v61 = 2 * (v60 + 1);
            if ( !v61 )
            {
              v62 = 0;
LABEL_127:
              *((_QWORD *)v49 + 4) = v62;
              *((_QWORD *)v49 + 6) = v57;
              *((_QWORD *)v49 + 7) = v60;
              memcpy_0(v62, v58, 2 * v57 + 2);
              goto LABEL_128;
            }
          }
          else
          {
            v60 = 0x7FFFFFFFFFFFFFFELL;
            v61 = -2;
          }
          if ( v61 < 0x1000 )
          {
            v62 = operator new(v61);
          }
          else
          {
            if ( v61 + 39 < v61 )
              std::_Throw_bad_array_new_length();
            v63 = operator new(v61 + 39);
            v64 = v63;
            if ( !v63 )
              __fastfail(5u);
            v62 = (void *)(((unsigned __int64)v63 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *((_QWORD *)v62 - 1) = v64;
          }
          goto LABEL_127;
        }
      }
      else
      {
        v52 = 0x7FFFFFFFFFFFFFFELL;
        v53 = -2;
      }
      if ( v53 < 0x1000 )
      {
        v54 = operator new(v53);
      }
      else
      {
        if ( v53 + 39 < v53 )
          std::_Throw_bad_array_new_length();
        v55 = operator new(v53 + 39);
        v56 = v55;
        if ( !v55 )
          __fastfail(5u);
        v54 = (void *)(((unsigned __int64)v55 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v54 - 1) = v56;
      }
      goto LABEL_107;
    }
  }
LABEL_211:
  if ( phkResult )
    RegCloseKey(phkResult);
  LocalFree(v7);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v104 = Instance;
    v127[0] = &v104;
    v127[1] = (void *)4;
    UserData.Ptr = 0x50B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    Src[0] = off_18003E050;
    Src[1] = (void *)((unsigned __int16)*off_18003E050 | 0x200000000LL);
    v125 = (unsigned __int64)word_180035E1A;
    v126 = 0x100000017LL;
    LODWORD(v106) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)Src);
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800060a0  mov     [rsp+arg_10], rbx
0x1800060a5  mov     [rsp+arg_18], rsi
0x1800060aa  push    rdi
0x1800060ab  push    r12
0x1800060ad  push    r13
0x1800060af  push    r14
0x1800060b1  push    r15
0x1800060b3  sub     rsp, 180h
0x1800060ba  movaps  [rsp+1A8h+var_38], xmm6
0x1800060c2  mov     rax, cs:__security_cookie
0x1800060c9  xor     rax, rsp
0x1800060cc  mov     [rsp+1A8h+var_48], rax
0x1800060d4  mov     edi, r8d
0x1800060d7  mov     r12, rdx
0x1800060da  mov     [rsp+1A8h+var_B8], rdx
0x1800060e2  mov     rsi, rcx
0x1800060e5  mov     [rsp+1A8h+var_E8], rcx
0x1800060ed  lea     rbx, [rcx+1D8h]
0x1800060f4  mov     rcx, rbx; lpCriticalSection
0x1800060f7  call    cs:__imp_EnterCriticalSection
0x1800060fe  nop     dword ptr [rax+rax+00h]
0x180006103  mov     [rsp+1A8h+lpCriticalSection], rbx
0x18000610b  xor     r15d, r15d
0x18000610e  mov     [rsp+1A8h+phkResult], r15
0x180006116  mov     r14d, r15d
0x180006119  mov     [rsp+1A8h+var_140], r15
0x18000611e  mov     [rsp+1A8h+cValues], r15d
0x180006123  mov     [rsp+1A8h+cbMaxValueNameLen], r15d
0x180006128  mov     [rsp+1A8h+cchValueName], r15d
0x18000612d  mov     [rsp+1A8h+Type], r15d
0x180006135  mov     eax, [r12+18h]
0x18000613a  mov     [rsi+160h], eax
0x180006140  mov     eax, cs:dword_18003E048
0x180006146  cmp     eax, 5
0x180006149  jbe     loc_180006207
0x18000614f  mov     dword ptr [rsp+1A8h+EventDescriptor.Id], 0B000000h
0x18000615a  movzx   eax, cs:word_180035E69
0x180006161  mov     dword ptr [rsp+1A8h+EventDescriptor.Level], eax
0x180006168  mov     [rsp+1A8h+EventDescriptor.Keyword], r15
0x180006170  mov     rax, cs:off_18003E050
0x180006177  mov     [rsp+1A8h+var_68.Ptr], rax
0x18000617f  movzx   eax, word ptr [rax]
0x180006182  mov     [rsp+1A8h+var_68.Size], eax
0x180006189  mov     dword ptr [rsp+1A8h+var_68.0Ch], 2
0x180006194  lea     rax, byte_180035E73
0x18000619b  mov     [rsp+1A8h+var_58], rax
0x1800061a3  mov     [rsp+1A8h+var_50], 22h ; '"'
0x1800061ae  mov     [rsp+1A8h+var_4C], 1
0x1800061b9  lea     rax, _TraceLoggingMetadataEnd
0x1800061c0  lea     rcx, _TraceLoggingMetadata
0x1800061c7  sub     eax, ecx
0x1800061c9  mov     [rsp+1A8h+var_148], eax
0x1800061cd  mov     eax, [rsp+1A8h+var_148]
0x1800061d1  lea     rax, [rsp+1A8h+var_68]
0x1800061d9  mov     [rsp+1A8h+UserData], rax; UserData
0x1800061de  mov     [rsp+1A8h+UserDataCount], 2; UserDataCount
0x1800061e6  xor     r9d, r9d; RelatedActivityId
0x1800061e9  xor     r8d, r8d; ActivityId
0x1800061ec  lea     rdx, [rsp+1A8h+EventDescriptor]; EventDescriptor
0x1800061f4  mov     rcx, cs:RegHandle; RegHandle
0x1800061fb  call    cs:__imp_EventWriteTransfer
0x180006202  nop     dword ptr [rax+rax+00h]
0x180006207  cmp     edi, 28h ; '('
0x18000620a  jnz     loc_180006F13
0x180006210  cmp     [rsi+18h], r15d
0x180006214  jz      short loc_180006221
0x180006216  mov     r13d, 800704DFh
0x18000621c  jmp     loc_180006F19
0x180006221  mov     eax, [r12+4]
0x180006226  mov     [rsi+0FCh], eax
0x18000622c  lea     r8, [rsi+148h]
0x180006233  mov     edi, 0FFFFFFFFh
0x180006238  mov     edx, edi
0x18000623a  mov     rcx, [r12+8]
0x18000623f  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180006246  nop     dword ptr [rax+rax+00h]
0x18000624b  mov     r13d, eax
0x18000624e  test    eax, eax
0x180006250  js      loc_180006F19
0x180006256  lea     r8, [rsi+158h]
0x18000625d  mov     edx, edi
0x18000625f  mov     rcx, [r12+10h]
0x180006264  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000626b  nop     dword ptr [rax+rax+00h]
0x180006270  mov     r13d, eax
0x180006273  test    eax, eax
0x180006275  js      loc_180006F19
0x18000627b  lea     rax, [rsp+1A8h+phkResult]
0x180006283  mov     qword ptr [rsp+1A8h+UserDataCount], rax; phkResult
0x180006288  mov     r9d, 20019h; samDesired
0x18000628e  xor     r8d, r8d; ulOptions
0x180006291  lea     rdx, ?gc_szNormalReplaceKey@@3QBGB; "Software\\Microsoft\\Provisioning\\Sync"...
0x180006298  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000629f  call    cs:__imp_RegOpenKeyExW
0x1800062a6  nop     dword ptr [rax+rax+00h]
0x1800062ab  cmp     eax, 2
0x1800062ae  jz      loc_18000649F
0x1800062b4  test    eax, eax
0x1800062b6  jz      short loc_1800062C6
0x1800062b8  jg      loc_18000657C
0x1800062be  mov     r13d, eax
0x1800062c1  jmp     loc_180006F19
0x1800062c6  mov     [rsp+1A8h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800062cb  mov     [rsp+1A8h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800062d0  mov     [rsp+1A8h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800062d5  lea     rax, [rsp+1A8h+cbMaxValueNameLen]
0x1800062da  mov     [rsp+1A8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800062df  lea     rax, [rsp+1A8h+cValues]
0x1800062e4  mov     [rsp+1A8h+lpcValues], rax; lpcValues
0x1800062e9  mov     [rsp+1A8h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800062ee  mov     [rsp+1A8h+UserData], r15; lpcbMaxSubKeyLen
0x1800062f3  mov     qword ptr [rsp+1A8h+UserDataCount], r15; lpcSubKeys
0x1800062f8  xor     r9d, r9d; lpReserved
0x1800062fb  xor     r8d, r8d; lpcchClass
0x1800062fe  xor     edx, edx; lpClass
0x180006300  mov     rcx, [rsp+1A8h+phkResult]; hKey
0x180006308  call    cs:__imp_RegQueryInfoKeyW
0x18000630f  nop     dword ptr [rax+rax+00h]
0x180006314  test    eax, eax
0x180006316  jz      short loc_180006326
0x180006318  jg      loc_18000657C
0x18000631e  mov     r13d, eax
0x180006321  jmp     loc_180006F19
0x180006326  mov     eax, [rsp+1A8h+cValues]
0x18000632a  test    eax, eax
0x18000632c  jz      loc_18000649F
0x180006332  shl     rax, 3
0x180006336  cmp     rax, rdi
0x180006339  ja      loc_180006590
0x18000633f  mov     ebx, eax
0x180006341  mov     edx, eax; uBytes
0x180006343  xor     ecx, ecx; uFlags
0x180006345  call    cs:__imp_LocalAlloc
0x18000634c  nop     dword ptr [rax+rax+00h]
0x180006351  mov     rcx, rax; void *
0x180006354  mov     [rsi+128h], rax
0x18000635b  test    rax, rax
0x18000635e  jnz     short loc_18000636B
0x180006360  mov     r13d, 8007000Eh
0x180006366  jmp     loc_180006F19
0x18000636b  mov     eax, [rsp+1A8h+cValues]
0x18000636f  mov     [rsi+0F8h], eax
0x180006375  mov     r8, rbx; Size
0x180006378  xor     edx, edx; Val
0x18000637a  call    memset_0
0x18000637f  mov     eax, [rsp+1A8h+cbMaxValueNameLen]
0x180006383  lea     ecx, [rax+1]
0x180006386  cmp     ecx, eax
0x180006388  jb      loc_18000658C
0x18000638e  mov     [rsp+1A8h+cbMaxValueNameLen], ecx
0x180006392  mov     eax, ecx
0x180006394  add     rax, rax
0x180006397  cmp     rax, rdi
0x18000639a  ja      loc_180006590
0x1800063a0  mov     edx, eax; uBytes
0x1800063a2  xor     ecx, ecx; uFlags
0x1800063a4  call    cs:__imp_LocalAlloc
0x1800063ab  nop     dword ptr [rax+rax+00h]
0x1800063b0  mov     r14, rax
0x1800063b3  mov     [rsp+1A8h+var_140], rax
0x1800063b8  test    rax, rax
0x1800063bb  jnz     short loc_1800063C8
0x1800063bd  mov     r13d, 8007000Eh
0x1800063c3  jmp     loc_180006F19
0x1800063c8  mov     ebx, r15d
0x1800063cb  mov     r13d, r15d
0x1800063ce  cmp     [rsi+0F8h], r15d
0x1800063d5  jbe     loc_18000649F
0x1800063db  nop     dword ptr [rax+rax+00h]
0x1800063e0  mov     eax, [rsp+1A8h+cbMaxValueNameLen]
0x1800063e4  mov     [rsp+1A8h+cchValueName], eax
0x1800063e8  mov     [rsp+1A8h+lpcValues], r15; lpcbData
0x1800063ed  mov     [rsp+1A8h+lpcbMaxClassLen], r15; lpData
0x1800063f2  lea     rax, [rsp+1A8h+Type]
0x1800063fa  mov     [rsp+1A8h+UserData], rax; lpType
0x1800063ff  mov     qword ptr [rsp+1A8h+UserDataCount], r15; lpReserved
0x180006404  lea     r9, [rsp+1A8h+cchValueName]; lpcchValueName
0x180006409  mov     r8, r14; lpValueName
0x18000640c  mov     edx, ebx; dwIndex
0x18000640e  mov     rcx, [rsp+1A8h+phkResult]; hKey
0x180006416  call    cs:__imp_RegEnumValueW
0x18000641d  nop     dword ptr [rax+rax+00h]
0x180006422  mov     r13d, eax
0x180006425  test    eax, eax
0x180006427  jnz     loc_180006576
0x18000642d  mov     edi, ebx
0x18000642f  mov     rax, [rsi+128h]
0x180006436  lea     rcx, [rax+rdi*8]
0x18000643a  mov     qword ptr [rsp+1A8h+UserDataCount], rcx; ppv
0x18000643f  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x180006446  xor     edx, edx; pUnkOuter
0x180006448  mov     r8d, 1; dwClsContext
0x18000644e  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x180006455  call    cs:__imp_CoCreateInstance
0x18000645c  nop     dword ptr [rax+rax+00h]
0x180006461  mov     r13d, eax
0x180006464  test    eax, eax
0x180006466  js      loc_180006F19
0x18000646c  mov     rax, [rsi+128h]
0x180006473  mov     rcx, [rax+rdi*8]
0x180006477  mov     rax, [rcx]
0x18000647a  mov     rdx, r14
0x18000647d  mov     rax, [rax+28h]
0x180006481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006486  mov     r13d, eax
0x180006489  test    eax, eax
0x18000648b  js      loc_180006F19
0x180006491  inc     ebx
0x180006493  cmp     ebx, [rsi+0F8h]
0x180006499  jb      loc_1800063E0
0x18000649f  mov     [rsp+1A8h+hKey], r15
0x1800064a4  lea     rax, [rsp+1A8h+hKey]
0x1800064a9  mov     qword ptr [rsp+1A8h+UserDataCount], rax; unsigned int
0x1800064ae  mov     r9d, 20019h; samDesired
0x1800064b4  xor     r8d, r8d; ulOptions
0x1800064b7  lea     rdx, ?gc_szRebootRequiredKey@@3QBGB; "Software\\Microsoft\\Provisioning\\Sync"...
0x1800064be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800064c5  call    cs:__imp_RegOpenKeyExW
0x1800064cc  nop     dword ptr [rax+rax+00h]
0x1800064d1  mov     rcx, [rsp+1A8h]; this
0x1800064d9  test    eax, eax
0x1800064db  jz      short loc_1800064E5
0x1800064dd  mov     r9d, eax; char *
0x1800064e0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800064e5  mov     rcx, [rsp+1A8h+hKey]; hKey
0x1800064ea  test    rcx, rcx
0x1800064ed  jz      loc_18000670B
0x1800064f3  xorps   xmm0, xmm0
0x1800064f6  movdqu  xmmword ptr [rsp+1A8h+var_120], xmm0
0x1800064ff  mov     [rsp+1A8h+var_110], r15
0x180006507  lea     rdx, [rsp+1A8h+var_120]
0x18000650f  call    ForEachRegValue__lambda_adf4322f45f66e7bf7724f37560fceae___; ForEachRegValue__lambda_adf4322f45f66e7bf7724f37560fceae_
0x180006514  lea     rdi, [rsi+1C0h]
0x18000651b  lea     rax, [rsp+1A8h+var_120]
0x180006523  cmp     rdi, rax
0x180006526  jz      loc_180006638
0x18000652c  mov     rbx, [rdi]
0x18000652f  test    rbx, rbx
0x180006532  jz      loc_180006601
0x180006538  mov     rsi, [rdi+8]
0x18000653c  cmp     rbx, rsi
0x18000653f  jz      short loc_1800065BC
0x180006541  mov     rdx, [rbx+18h]
0x180006545  cmp     rdx, 7
0x180006549  jbe     short loc_1800065A3
0x18000654b  mov     rax, [rbx]
0x18000654e  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180006556  cmp     rdx, 1000h
0x18000655d  jb      short loc_18000659B
0x18000655f  mov     rcx, [rax-8]
0x180006563  sub     rax, rcx
0x180006566  sub     rax, 8
0x18000656a  cmp     rax, 1Fh
0x18000656e  ja      short loc_1800065EA
0x180006570  add     rdx, 27h ; '''
0x180006574  jmp     short loc_18000659E
0x180006576  jle     loc_180006F19
0x18000657c  movzx   r13d, ax
0x180006580  or      r13d, 80070000h
0x180006587  jmp     loc_180006F19
0x18000658c  mov     [rsp+1A8h+cbMaxValueNameLen], edi
0x180006590  mov     r13d, 80070216h
0x180006596  jmp     loc_180006F19
0x18000659b  mov     rcx, rax; void *
0x18000659e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800065a3  mov     [rbx+10h], r15
0x1800065a7  mov     qword ptr [rbx+18h], 7
0x1800065af  mov     [rbx], r15w
0x1800065b3  add     rbx, 20h ; ' '
0x1800065b7  cmp     rbx, rsi
0x1800065ba  jnz     short loc_180006541
0x1800065bc  mov     rax, [rdi]
0x1800065bf  mov     rdx, [rdi+10h]
0x1800065c3  sub     rdx, rax
0x1800065c6  and     rdx, 0FFFFFFFFFFFFFFE0h; struct std::nothrow_t *
0x1800065ca  cmp     rdx, 1000h
0x1800065d1  jb      short loc_1800065F1
0x1800065d3  mov     rcx, [rax-8]
0x1800065d7  sub     rax, rcx
0x1800065da  sub     rax, 8
0x1800065de  cmp     rax, 1Fh
0x1800065e2  ja      short loc_1800065EA
0x1800065e4  add     rdx, 27h ; '''
0x1800065e8  jmp     short loc_1800065F4
0x1800065ea  mov     ecx, 5
0x1800065ef  int     29h; Win8: RtlFailFast(ecx)
0x1800065f1  mov     rcx, rax; void *
0x1800065f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800065f9  mov     rsi, [rsp+1A8h+var_E8]
0x180006601  mov     rax, [rsp+1A8h+var_120]
0x180006609  mov     [rdi], rax
0x18000660c  mov     rax, [rsp+1A8h+var_120+8]
0x180006614  mov     [rdi+8], rax
0x180006618  mov     rax, [rsp+1A8h+var_110]
0x180006620  mov     [rdi+10h], rax
0x180006624  xorps   xmm0, xmm0
0x180006627  movdqu  xmmword ptr [rsp+1A8h+var_120], xmm0
0x180006630  mov     [rsp+1A8h+var_110], r15
0x180006638  mov     rbx, [rsp+1A8h+var_120]
0x180006640  test    rbx, rbx
  ... truncated ...
```
