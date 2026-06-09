# RegistryHelper::TryGetHAADJMutexName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18009ecd4`
- end: `0x18009f1d6`
- name: `?TryGetHAADJMutexName@RegistryHelper@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1282`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009b940`

## callees

- `0x18000468c`
- `0x1800048cc`
- `0x180005ba0`
- `0x180006450`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x18000f368`
- `0x18002dd24`
- `0x1800319ac`
- `0x180044300`
- `0x18008be1c`
- `0x18008c238`
- `0x180095bf8`
- `0x180095d38`
- `0x1800980d4`
- `0x180098250`
- `0x18009ecd4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ef73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ef84`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ef73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18009ef84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f154`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009f01d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009f01d`
- `RPCRT4!RpcStringFreeW` at `0x18009f16b`
- `RPCRT4!RpcStringFreeW` at `0x18009f16b`
- `RPCRT4!UuidToStringW` at `0x18009ee1a`
- `RPCRT4!UuidToStringW` at `0x18009ee1a`

## string_xrefs

- `0x18009ed8e`: `RegistryPath::InitializePersistedStatePath`
- `0x18009ef3a`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18009f05d`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18009ee04`: `CreateGuid`
- `0x18009eddd`: `RegistryPath::CreateKey`
- `0x18009f056`: `RegistryPath::ReadBinaryValue`
- `0x18009f073`: `RegistryPath::ReadBinaryValue`
- `0x18009ef33`: `RegistryPath::SaveBinaryValue`
- `0x18009ef4e`: `RegistryPath::SaveBinaryValue`
- `0x18009f109`: `RegistryPath::DeleteSubTree`
- `0x18009ed98`: `RegistryHelper::TryGetHAADJMutexName`
- `0x18009ee30`: `RegistryHelper::TryGetHAADJMutexName`
- `0x18009ef58`: `RegistryHelper::TryGetHAADJMutexName`
- `0x18009f0e1`: `RegistryHelper::TryGetHAADJMutexName`
- `0x18009f192`: `RegistryHelper::TryGetHAADJMutexName`
- `0x18009ed75`: `CDJConfigRoot`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryHelper::TryGetHAADJMutexName(char **Src)
{
  int v2; // eax
  unsigned __int16 *v3; // rdx
  unsigned int v4; // r8d
  unsigned int v5; // edi
  const wchar_t *v6; // r8
  unsigned int v7; // eax
  int v8; // esi
  __int64 v9; // r14
  __int64 v10; // rdx
  const unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r8
  unsigned __int8 *v13; // r10
  HKEY v14; // rcx
  const unsigned __int16 *v15; // rdx
  unsigned int BinaryValue; // eax
  int v17; // r14d
  const wchar_t *v18; // r8
  ULONGLONG TickCount64; // r12
  const unsigned __int16 *v20; // rsi
  const unsigned __int16 *v21; // r8
  const WCHAR *v22; // rdx
  HKEY v23; // rcx
  unsigned __int8 *v24; // rsi
  __int64 v25; // r14
  __int64 v27; // rax
  const unsigned __int16 *v28; // r8
  __int64 v29; // rax
  const unsigned __int16 *v30; // r8
  __int64 v31; // rax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rax
  const unsigned __int16 *v34; // r8
  unsigned __int8 **v35; // [rsp+20h] [rbp-118h]
  unsigned int v36[2]; // [rsp+40h] [rbp-F8h] BYREF
  void *lpMem; // [rsp+48h] [rbp-F0h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-E8h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-E4h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-E0h] BYREF
  RPC_WSTR StringUuid; // [rsp+60h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-D0h] BYREF
  unsigned __int8 *v43; // [rsp+70h] [rbp-C8h] BYREF
  unsigned __int8 *v44; // [rsp+78h] [rbp-C0h] BYREF
  unsigned __int16 *v45[4]; // [rsp+80h] [rbp-B8h] BYREF
  HKEY hkey[2]; // [rsp+A0h] [rbp-98h]
  __int64 v47; // [rsp+B0h] [rbp-88h]
  __int64 v48; // [rsp+B8h] [rbp-80h]
  const std::bad_alloc *v49; // [rsp+C0h] [rbp-78h] BYREF
  const std::exception *v50; // [rsp+C8h] [rbp-70h] BYREF
  const std::bad_alloc *v51; // [rsp+D0h] [rbp-68h] BYREF
  const std::exception *v52; // [rsp+D8h] [rbp-60h] BYREF
  UUID Uuid; // [rsp+E0h] [rbp-58h] BYREF

  hKey = 0;
  v38 = 0;
  lpMem = 0;
  v39 = 0;
  v40 = 0;
  v36[0] = 0;
  v43 = 0;
  v44 = 0;
  Uuid = GUID_NULL;
  StringUuid = 0;
  memset(v45, 0, sizeof(v45));
  *(_OWORD *)hkey = 0;
  v47 = 0;
  v48 = 0;
  v2 = RegistryPath::InitializePersistedStatePath(
         (RegistryPath *)v45,
         L"CDJConfigRoot",
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CDJ",
         L"HAADJMutex");
  v5 = v2;
  if ( v2 < 0 )
  {
    v6 = L"RegistryPath::InitializePersistedStatePath";
LABEL_3:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistryHelper::TryGetHAADJMutexName",
      v6,
      (unsigned int)v2);
    goto LABEL_58;
  }
  v2 = RegistryPath::CreateKey(
         (RegistryPath *)v45,
         v3,
         v4,
         0xF003Fu,
         (struct _SECURITY_ATTRIBUTES *const)v35,
         &hKey,
         &v38);
  v5 = v2;
  if ( v2 < 0 )
  {
    v6 = L"RegistryPath::CreateKey";
    goto LABEL_3;
  }
  if ( v38 == 1 )
  {
    v2 = CreateGuid(&Uuid);
    v5 = v2;
    if ( v2 < 0 )
    {
      v6 = L"CreateGuid";
      goto LABEL_3;
    }
    v7 = UuidToStringW(&Uuid, &StringUuid);
    v8 = v7;
    if ( v7 )
    {
      Logger::TraceError(
        L"%s: %s failed with RPC_STATUS: 0x%08x.",
        L"RegistryHelper::TryGetHAADJMutexName",
        L"UuidToStringW",
        v7);
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      else
        v5 = v8;
      goto LABEL_58;
    }
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( StringUuid[v10] );
    v2 = EncryptData((unsigned __int8 *)StringUuid, 2 * v10 + 2, &v43, &v39);
    v5 = v2;
    if ( v2 < 0 )
    {
      v6 = L"EncryptData";
      goto LABEL_3;
    }
    if ( !hkey[0] || (unsigned int)IsEmptyString(v45[0]) )
    {
      Logger::TraceError(
        L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
        L"RegistryPath::SaveBinaryValue");
      BinaryValue = 87;
    }
    else
    {
      v12 = (const unsigned __int16 *)v39;
      v13 = v43;
      v14 = hkey[1];
      if ( hkey[1] )
      {
        v15 = 0;
      }
      else
      {
        v15 = RegistryPath::SubPath((RegistryPath *)v45);
        v14 = hkey[0];
      }
      BinaryValue = RegSaveBinaryValue(v14, v15, v12, v11, v13, (unsigned int)v12);
      if ( !BinaryValue )
      {
        try
        {
          std::wstring::_Assign<unsigned short>(Src, L"Global\\", (char *)7);
          do
            ++v9;
          while ( StringUuid[v9] );
          std::wstring::_Append<unsigned short>(Src);
        }
        catch ( const std::bad_alloc *v49 )
        {
          v27 = (*(__int64 (__fastcall **)(const std::bad_alloc *))(*(_QWORD *)v49 + 8LL))(v49);
          v36[0] = -2147024882;
          v28 = &dword_1800D914C;
          if ( v27 )
            v28 = (const unsigned __int16 *)v27;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed. %hs.",
            L"RegistryHelper::TryGetHAADJMutexName",
            v28);
          v5 = v36[0];
          goto LABEL_58;
        }
        catch ( const std::exception *v50 )
        {
          v36[0] = -2147418113;
          v29 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v50 + 8LL))(v50);
          v30 = &dword_1800D914C;
          if ( v29 )
            v30 = (const unsigned __int16 *)v29;
          Logger::TraceError(L"%s: Unhandled std::exception: %hs.", L"RegistryHelper::TryGetHAADJMutexName", v30);
          v5 = v36[0];
          goto LABEL_58;
        }
        catch ( ... )
        {
          v36[0] = -2147418113;
          Logger::TraceError(L"%s: Unhandled exception.", L"RegistryHelper::TryGetHAADJMutexName");
          v5 = -2147418113;
          goto LABEL_58;
        }
        goto LABEL_58;
      }
    }
    v17 = BinaryValue;
    v18 = L"RegistryPath::SaveBinaryValue";
LABEL_26:
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"RegistryHelper::TryGetHAADJMutexName",
      v18,
      BinaryValue);
    if ( v17 > 0 )
      v5 = (unsigned __int16)v17 | 0x80070000;
    else
      v5 = v17;
  }
  else
  {
    TickCount64 = GetTickCount64();
    v20 = v45[0];
    while ( GetTickCount64() - TickCount64 <= 0x1F4 )
    {
      if ( lpMem )
        goto LABEL_43;
      if ( !hkey[0] || (unsigned int)IsEmptyString(v20) )
      {
        Logger::TraceError(
          L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
          L"RegistryPath::ReadBinaryValue");
        BinaryValue = 87;
        v17 = 87;
LABEL_41:
        v18 = L"RegistryPath::ReadBinaryValue";
        goto LABEL_26;
      }
      if ( hkey[1] )
      {
        v22 = 0;
        v23 = hkey[1];
      }
      else
      {
        v22 = RegistryPath::SubPath((RegistryPath *)v45);
        v23 = hkey[0];
      }
      BinaryValue = RegReadBinaryValue(v23, v22, v21, v20, (unsigned __int8 **)&lpMem, v36);
      v17 = BinaryValue;
      if ( BinaryValue )
        goto LABEL_41;
      if ( lpMem )
      {
        v2 = DecryptData((unsigned __int8 *)lpMem, v36[0], &v44, &v40);
        v5 = v2;
        if ( v2 < 0 )
        {
          v6 = L"DecryptData";
          goto LABEL_3;
        }
      }
      else
      {
        Sleep(0xAu);
      }
    }
    if ( lpMem )
    {
LABEL_43:
      if ( v40 )
      {
        if ( (v40 & 1) == 0 )
        {
          v24 = v44;
          if ( !*(_WORD *)&v44[2 * ((unsigned __int64)v40 >> 1) - 2] )
          {
            try
            {
              std::wstring::_Assign<unsigned short>(Src, L"Global\\", (char *)7);
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)&v24[2 * v25] );
              std::wstring::_Append<unsigned short>(Src);
            }
            catch ( const std::bad_alloc *v51 )
            {
              v31 = (*(__int64 (__fastcall **)(const std::bad_alloc *))(*(_QWORD *)v51 + 8LL))(v51);
              v36[0] = -2147024882;
              v32 = &dword_1800D914C;
              if ( v31 )
                v32 = (const unsigned __int16 *)v31;
              Logger::TraceCritical(
                L"%s: Out of memory. Allocation failed. %hs.",
                L"RegistryHelper::TryGetHAADJMutexName",
                v32);
              v5 = v36[0];
              goto LABEL_58;
            }
            catch ( const std::exception *v52 )
            {
              v36[0] = -2147418113;
              v33 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v52 + 8LL))(v52);
              v34 = &dword_1800D914C;
              if ( v33 )
                v34 = (const unsigned __int16 *)v33;
              Logger::TraceError(L"%s: Unhandled std::exception: %hs.", L"RegistryHelper::TryGetHAADJMutexName", v34);
              v5 = v36[0];
              goto LABEL_58;
            }
            catch ( ... )
            {
              v36[0] = -2147418113;
              Logger::TraceError(L"%s: Unhandled exception.", L"RegistryHelper::TryGetHAADJMutexName");
              v5 = v36[0];
              goto LABEL_58;
            }
            goto LABEL_58;
          }
        }
      }
    }
    Logger::TraceWarning(
      (wchar_t *)L"%s: Failed to retrieve mutex name, mutex key status unknown.",
      L"RegistryHelper::TryGetHAADJMutexName");
    v2 = RegistryPath::DeleteSubTree((HKEY *)v45, 0);
    v5 = v2;
    if ( v2 < 0 )
    {
      v6 = L"RegistryPath::DeleteSubTree";
      goto LABEL_3;
    }
    v5 = -2145648498;
  }
LABEL_58:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  SafeFree(lpMem);
  SafeFree(v43);
  SafeFree(v44);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistryHelper::TryGetHAADJMutexName", v5);
  RegistryPath::Reset((RegistryPath *)v45);
  return v5;
}

```

## disassembly

```asm
0x18009ecd4  mov     r11, rsp
0x18009ecd7  push    rbx
0x18009ecd8  push    rsi
0x18009ecd9  push    rdi
0x18009ecda  push    r12
0x18009ecdc  push    r14
0x18009ecde  push    r15
0x18009ece0  sub     rsp, 108h
0x18009ece7  mov     rax, cs:__security_cookie
0x18009ecee  xor     rax, rsp
0x18009ecf1  mov     [rsp+138h+var_48], rax
0x18009ecf9  mov     r15, rcx
0x18009ecfc  xor     ebx, ebx
0x18009ecfe  mov     [rsp+138h+hKey], rbx
0x18009ed03  mov     [rsp+138h+var_E8], ebx
0x18009ed07  mov     [rsp+138h+lpMem], rbx
0x18009ed0c  mov     [rsp+138h+var_E4], ebx
0x18009ed10  mov     [rsp+138h+var_E0], ebx
0x18009ed14  mov     [rsp+138h+var_F8], ebx
0x18009ed18  mov     [rsp+138h+var_C8], rbx
0x18009ed1d  mov     [rsp+138h+var_C0], rbx
0x18009ed22  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18009ed29  movdqu  xmmword ptr [r11-58h], xmm0
0x18009ed2f  mov     [rsp+138h+StringUuid], rbx
0x18009ed34  mov     [r11-0B8h], rbx
0x18009ed3b  mov     [r11-0B0h], rbx
0x18009ed42  mov     [r11-0A8h], rbx
0x18009ed49  mov     [r11-0A0h], rbx
0x18009ed50  xorps   xmm0, xmm0
0x18009ed53  movdqa  xmmword ptr [rsp+138h+hkey], xmm0
0x18009ed5c  mov     [r11-88h], rbx
0x18009ed63  mov     [r11-80h], rbx
0x18009ed67  lea     r9, aHaadjmutex; "HAADJMutex"
0x18009ed6e  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18009ed75  lea     rdx, aCdjconfigroot; "CDJConfigRoot"
0x18009ed7c  lea     rcx, [r11-0B8h]; this
0x18009ed83  call    ?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z; RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)
0x18009ed88  mov     edi, eax
0x18009ed8a  test    eax, eax
0x18009ed8c  jns     short loc_18009EDB0
0x18009ed8e  lea     r8, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x18009ed95  mov     r9d, eax
0x18009ed98  lea     rdx, aRegistryhelper_0; "RegistryHelper::TryGetHAADJMutexName"
0x18009ed9f  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18009eda6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009edab  jmp     loc_18009F14A
0x18009edb0  lea     rax, [rsp+138h+var_E8]
0x18009edb5  mov     [rsp+138h+var_108], rax; unsigned int *
0x18009edba  lea     rax, [rsp+138h+hKey]
0x18009edbf  mov     [rsp+138h+var_110], rax; HKEY *
0x18009edc4  mov     r9d, 0F003Fh; unsigned int
0x18009edca  lea     rcx, [rsp+138h+var_B8]; this
0x18009edd2  call    ?CreateKey@RegistryPath@@QEBAKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z; RegistryPath::CreateKey(ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x18009edd7  mov     edi, eax
0x18009edd9  test    eax, eax
0x18009eddb  jns     short loc_18009EDE6
0x18009eddd  lea     r8, aRegistrypathCr_0; "RegistryPath::CreateKey"
0x18009ede4  jmp     short loc_18009ED95
0x18009ede6  cmp     [rsp+138h+var_E8], 1
0x18009edeb  jnz     loc_18009EF70
0x18009edf1  lea     rcx, [rsp+138h+Uuid]; struct _GUID *
0x18009edf9  call    ?CreateGuid@@YAJPEAU_GUID@@@Z; CreateGuid(_GUID *)
0x18009edfe  mov     edi, eax
0x18009ee00  test    eax, eax
0x18009ee02  jns     short loc_18009EE0D
0x18009ee04  lea     r8, aCreateguid; "CreateGuid"
0x18009ee0b  jmp     short loc_18009ED95
0x18009ee0d  lea     rdx, [rsp+138h+StringUuid]; StringUuid
0x18009ee12  lea     rcx, [rsp+138h+Uuid]; Uuid
0x18009ee1a  call    cs:__imp_UuidToStringW
0x18009ee20  mov     esi, eax
0x18009ee22  test    eax, eax
0x18009ee24  jz      short loc_18009EE48
0x18009ee26  mov     r9d, eax
0x18009ee29  lea     r8, aUuidtostringw_0; "UuidToStringW"
0x18009ee30  lea     rdx, aRegistryhelper_0; "RegistryHelper::TryGetHAADJMutexName"
0x18009ee37  lea     rcx, aSSFailedWithRp; "%s: %s failed with RPC_STATUS: 0x%08x."
0x18009ee3e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009ee43  jmp     loc_18009F139
0x18009ee48  mov     rcx, [rsp+138h+StringUuid]; unsigned __int8 *
0x18009ee4d  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009ee51  mov     rdx, r14
0x18009ee54  inc     rdx
0x18009ee57  cmp     [rcx+rdx*2], bx
0x18009ee5b  jnz     short loc_18009EE54
0x18009ee5d  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18009ee65  lea     r9, [rsp+138h+var_E4]; unsigned int *
0x18009ee6a  lea     r8, [rsp+138h+var_C8]; unsigned __int8 **
0x18009ee6f  call    ?EncryptData@@YAJPEAE_KPEAPEAEPEAK@Z; EncryptData(uchar *,unsigned __int64,uchar * *,ulong *)
0x18009ee74  mov     edi, eax
0x18009ee76  test    eax, eax
0x18009ee78  jns     short loc_18009EE86
0x18009ee7a  lea     r8, aEncryptdata; "EncryptData"
0x18009ee81  jmp     loc_18009ED95
0x18009ee86  cmp     [rsp+138h+hkey], rbx
0x18009ee8e  jz      loc_18009EF33
0x18009ee94  mov     r9, [rsp+138h+var_B8]
0x18009ee9c  mov     rcx, r9; unsigned __int16 *
0x18009ee9f  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18009eea4  test    eax, eax
0x18009eea6  jnz     loc_18009EF33
0x18009eeac  mov     r8d, [rsp+138h+var_E4]
0x18009eeb1  mov     r10, [rsp+138h+var_C8]
0x18009eeb6  mov     rcx, [rsp+138h+hkey+8]
0x18009eebe  test    rcx, rcx
0x18009eec1  jz      short loc_18009EEC7
0x18009eec3  xor     edx, edx
0x18009eec5  jmp     short loc_18009EEDF
0x18009eec7  lea     rcx, [rsp+138h+var_B8]; this
0x18009eecf  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18009eed4  mov     rdx, rax; unsigned __int16 *
0x18009eed7  mov     rcx, [rsp+138h+hkey]; HKEY
0x18009eedf  mov     dword ptr [rsp+138h+var_110], r8d; unsigned int
0x18009eee4  mov     [rsp+138h+var_118], r10; unsigned __int8 *
0x18009eee9  call    ?RegSaveBinaryValue@@YAKPEAUHKEY__@@PEBG11PEAEK@Z; RegSaveBinaryValue(HKEY__ *,ushort const *,ushort const *,ushort const *,uchar *,ulong)
0x18009eeee  test    eax, eax
0x18009eef0  jnz     short loc_18009EF4B
0x18009eef2  lea     r8d, [rax+7]
0x18009eef6  lea     rdx, aGlobal; "Global\\"
0x18009eefd  mov     rcx, r15
0x18009ef00  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009ef05  mov     rdx, [rsp+138h+StringUuid]
0x18009ef0a  inc     r14
0x18009ef0d  cmp     [rdx+r14*2], bx
0x18009ef12  jnz     short loc_18009EF0A
0x18009ef14  mov     r8, r14
0x18009ef17  mov     rcx, r15; Src
0x18009ef1a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18009ef1f  jmp     loc_18009F0D3
0x18009ef24  jmp     loc_18009F0D5
0x18009ef29  jmp     loc_18009F0D5
0x18009ef2e  jmp     loc_18009F0D5
0x18009ef33  lea     rdx, aRegistrypathSa_1; "RegistryPath::SaveBinaryValue"
0x18009ef3a  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18009ef41  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009ef46  mov     eax, 57h ; 'W'
0x18009ef4b  mov     r14d, eax
0x18009ef4e  lea     r8, aRegistrypathSa_1; "RegistryPath::SaveBinaryValue"
0x18009ef55  mov     r9d, eax
0x18009ef58  lea     rdx, aRegistryhelper_0; "RegistryHelper::TryGetHAADJMutexName"
0x18009ef5f  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18009ef66  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009ef6b  jmp     loc_18009F121
0x18009ef70  mov     r14d, ebx
0x18009ef73  call    cs:__imp_GetTickCount64
0x18009ef79  mov     r12, rax
0x18009ef7c  mov     rsi, [rsp+138h+var_B8]
0x18009ef84  call    cs:__imp_GetTickCount64
0x18009ef8a  sub     rax, r12
0x18009ef8d  cmp     rax, 1F4h
0x18009ef93  ja      loc_18009F07F
0x18009ef99  cmp     [rsp+138h+lpMem], rbx
0x18009ef9e  jnz     loc_18009F086
0x18009efa4  cmp     [rsp+138h+hkey], rbx
0x18009efac  jz      loc_18009F056
0x18009efb2  mov     rcx, rsi; unsigned __int16 *
0x18009efb5  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18009efba  test    eax, eax
0x18009efbc  jnz     loc_18009F056
0x18009efc2  cmp     [rsp+138h+hkey+8], rbx
0x18009efca  jz      short loc_18009EFD8
0x18009efcc  xor     edx, edx
0x18009efce  mov     rcx, [rsp+138h+hkey+8]
0x18009efd6  jmp     short loc_18009EFF0
0x18009efd8  lea     rcx, [rsp+138h+var_B8]; this
0x18009efe0  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18009efe5  mov     rdx, rax; lpSubKey
0x18009efe8  mov     rcx, [rsp+138h+hkey]; hkey
0x18009eff0  lea     rax, [rsp+138h+var_F8]
0x18009eff5  mov     [rsp+138h+var_110], rax; unsigned int *
0x18009effa  lea     rax, [rsp+138h+lpMem]
0x18009efff  mov     [rsp+138h+var_118], rax; unsigned __int8 **
0x18009f004  mov     r9, rsi; unsigned __int16 *
0x18009f007  call    ?RegReadBinaryValue@@YAKPEAUHKEY__@@PEBG11PEAPEAEPEAK@Z; RegReadBinaryValue(HKEY__ *,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)
0x18009f00c  mov     r14d, eax
0x18009f00f  test    eax, eax
0x18009f011  jnz     short loc_18009F071
0x18009f013  cmp     [rsp+138h+lpMem], rbx
0x18009f018  jnz     short loc_18009F028
0x18009f01a  lea     ecx, [rax+0Ah]; dwMilliseconds
0x18009f01d  call    cs:__imp_Sleep
0x18009f023  jmp     loc_18009EF84
0x18009f028  mov     edx, [rsp+138h+var_F8]; unsigned __int64
0x18009f02c  lea     r9, [rsp+138h+var_E0]; unsigned int *
0x18009f031  lea     r8, [rsp+138h+var_C0]; unsigned __int8 **
0x18009f036  mov     rcx, [rsp+138h+lpMem]; unsigned __int8 *
0x18009f03b  call    ?DecryptData@@YAJPEAE_KPEAPEAEPEAK@Z; DecryptData(uchar *,unsigned __int64,uchar * *,ulong *)
0x18009f040  mov     edi, eax
0x18009f042  test    eax, eax
0x18009f044  jns     loc_18009EF84
0x18009f04a  lea     r8, aDecryptdata; "DecryptData"
0x18009f051  jmp     loc_18009ED95
0x18009f056  lea     rdx, aRegistrypathRe_0; "RegistryPath::ReadBinaryValue"
0x18009f05d  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18009f064  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009f069  mov     eax, 57h ; 'W'
0x18009f06e  mov     r14d, eax
0x18009f071  mov     esi, ebx
0x18009f073  lea     r8, aRegistrypathRe_0; "RegistryPath::ReadBinaryValue"
0x18009f07a  jmp     loc_18009EF55
0x18009f07f  cmp     [rsp+138h+lpMem], rbx
0x18009f084  jz      short loc_18009F0E1
0x18009f086  mov     eax, [rsp+138h+var_E0]
0x18009f08a  test    eax, eax
0x18009f08c  jz      short loc_18009F0E1
0x18009f08e  test    al, 1
0x18009f090  jnz     short loc_18009F0E1
0x18009f092  shr     rax, 1
0x18009f095  mov     rsi, [rsp+138h+var_C0]
0x18009f09a  cmp     [rsi+rax*2-2], bx
0x18009f09f  jnz     short loc_18009F0E1
0x18009f0a1  mov     r8d, 7
0x18009f0a7  lea     rdx, aGlobal; "Global\\"
0x18009f0ae  mov     rcx, r15
0x18009f0b1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009f0b6  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009f0ba  inc     r14
0x18009f0bd  cmp     [rsi+r14*2], bx
0x18009f0c2  jnz     short loc_18009F0BA
0x18009f0c4  mov     r8, r14
0x18009f0c7  mov     rdx, rsi
0x18009f0ca  mov     rcx, r15; Src
0x18009f0cd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18009f0d2  nop
0x18009f0d3  jmp     short loc_18009F14A
0x18009f0d5  xor     ebx, ebx
0x18009f0d7  mov     edi, [rsp+138h+var_F8]
0x18009f0db  jmp     short loc_18009F14A
0x18009f0dd  jmp     short loc_18009F0D5
0x18009f0df  jmp     short loc_18009F0D5
0x18009f0e1  lea     rdx, aRegistryhelper_0; "RegistryHelper::TryGetHAADJMutexName"
0x18009f0e8  lea     rcx, aSFailedToRetri_0; "%s: Failed to retrieve mutex name, mute"...
0x18009f0ef  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18009f0f4  xor     edx, edx; int
0x18009f0f6  lea     rcx, [rsp+138h+var_B8]; this
0x18009f0fe  call    ?DeleteSubTree@RegistryPath@@QEAAKH@Z; RegistryPath::DeleteSubTree(int)
0x18009f103  mov     edi, eax
0x18009f105  test    eax, eax
0x18009f107  jns     short loc_18009F115
0x18009f109  lea     r8, aRegistrypathDe_0; "RegistryPath::DeleteSubTree"
0x18009f110  jmp     loc_18009ED95
0x18009f115  mov     edi, 801C008Eh
0x18009f11a  test    r14d, r14d
0x18009f11d  jz      short loc_18009F14A
0x18009f11f  mov     esi, ebx
0x18009f121  test    r14d, r14d
0x18009f124  jg      short loc_18009F12B
0x18009f126  mov     edi, r14d
0x18009f129  jmp     short loc_18009F135
0x18009f12b  movzx   edi, r14w
0x18009f12f  or      edi, 80070000h
0x18009f135  test    esi, esi
0x18009f137  jz      short loc_18009F14A
0x18009f139  test    esi, esi
0x18009f13b  jg      short loc_18009F141
0x18009f13d  mov     edi, esi
0x18009f13f  jmp     short loc_18009F14A
0x18009f141  movzx   edi, si
0x18009f144  or      edi, 80070000h
0x18009f14a  mov     rcx, [rsp+138h+hKey]; hKey
0x18009f14f  test    rcx, rcx
0x18009f152  jz      short loc_18009F15F
0x18009f154  call    cs:__imp_RegCloseKey
0x18009f15a  mov     [rsp+138h+hKey], rbx
0x18009f15f  cmp     [rsp+138h+StringUuid], rbx
0x18009f164  jz      short loc_18009F171
0x18009f166  lea     rcx, [rsp+138h+StringUuid]; String
0x18009f16b  call    cs:__imp_RpcStringFreeW
0x18009f171  mov     rcx, [rsp+138h+lpMem]; lpMem
0x18009f176  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009f17b  mov     rcx, [rsp+138h+var_C8]; lpMem
0x18009f180  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009f185  mov     rcx, [rsp+138h+var_C0]; lpMem
0x18009f18a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18009f18f  mov     r8d, edi
0x18009f192  lea     rdx, aRegistryhelper_0; "RegistryHelper::TryGetHAADJMutexName"
0x18009f199  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18009f1a0  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009f1a5  nop
0x18009f1a6  lea     rcx, [rsp+138h+var_B8]; this
0x18009f1ae  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x18009f1b3  mov     eax, edi
0x18009f1b5  mov     rcx, [rsp+138h+var_48]
0x18009f1bd  xor     rcx, rsp; StackCookie
0x18009f1c0  call    __security_check_cookie
0x18009f1c5  add     rsp, 108h
0x18009f1cc  pop     r15
0x18009f1ce  pop     r14
0x18009f1d0  pop     r12
0x18009f1d2  pop     rdi
0x18009f1d3  pop     rsi
0x18009f1d4  pop     rbx
0x18009f1d5  retn
```
