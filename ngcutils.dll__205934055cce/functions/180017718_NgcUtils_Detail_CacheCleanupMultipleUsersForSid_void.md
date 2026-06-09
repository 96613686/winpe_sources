# NgcUtils::Detail::CacheCleanupMultipleUsersForSid(void)

- ea: `0x180017718`
- end: `0x180017f00`
- name: `?CacheCleanupMultipleUsersForSid@Detail@NgcUtils@@YAJXZ`
- size: `2024`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800185d0`

## callees

- `0x180003080`
- `0x180003568`
- `0x18000a594`
- `0x18000a5b4`
- `0x18000ce74`
- `0x18001354c`
- `0x180013dc8`
- `0x1800146ec`
- `0x180014e34`
- `0x180015c4c`
- `0x180015ca4`
- `0x180015e18`
- `0x180016528`
- `0x180016904`
- `0x180016a84`
- `0x180016b24`
- `0x180017718`
- `0x1800183f8`
- `0x18001aeb4`
- `0x18001b090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001779c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017cf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ed5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001779c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017cf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017ed5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017a11`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017d55`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017a11`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180017d55`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800179ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800179ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017bac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017be5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017caa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017ebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017bac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017be5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017caa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017cd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017e84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017ebb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017a29`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017a29`

## string_xrefs

- `0x180017780`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180017c16`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180017c45`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180017e2a`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180017e60`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall NgcUtils::Detail::CacheCleanupMultipleUsersForSid(NgcUtils::Detail *this)
{
  int v1; // r15d
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v3; // ebx
  _QWORD *v5; // rax
  HLOCAL v6; // rbx
  int v7; // r14d
  int v8; // eax
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  const WCHAR *v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // r13d
  int v17; // edi
  const WCHAR *v18; // r8
  int v19; // esi
  int v20; // r12d
  const WCHAR *v21; // rdx
  unsigned int ValueW; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  const WCHAR *v27; // rcx
  const char *v28; // r9
  int v29; // edx
  int v30; // ecx
  __int128 *v31; // rax
  LPCWSTR *v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  LPCWSTR *v37; // rax
  __int128 *v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdx
  unsigned int LastError; // edi
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 *v60; // rsi
  __int64 *i; // rdi
  void **v62; // r14
  void *v63; // rcx
  const wchar_t *v64; // r15
  int v65; // eax
  unsigned int v66; // r12d
  const WCHAR *v67; // rcx
  __int64 v68; // r8
  const char *v69; // r9
  __int64 *v70; // rcx
  int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  unsigned __int16 **pdwType; // [rsp+20h] [rbp-E0h]
  HKEY *pdwTypea; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  int v78; // [rsp+4Ch] [rbp-B4h]
  __int128 v79; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  FILETIME FileTime1; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime2; // [rsp+78h] [rbp-88h] BYREF
  HKEY v84; // [rsp+80h] [rbp-80h] BYREF
  int v85; // [rsp+88h] [rbp-78h]
  _BYTE v86[24]; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v88; // [rsp+B8h] [rbp-48h]
  FILETIME v89; // [rsp+BCh] [rbp-44h]
  _BYTE v90[24]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v91[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v92; // [rsp+F0h] [rbp-10h]
  _QWORD v93[2]; // [rsp+F8h] [rbp-8h] BYREF
  int v94; // [rsp+108h] [rbp+8h]
  __int128 v95; // [rsp+110h] [rbp+10h] BYREF
  __int64 v96; // [rsp+120h] [rbp+20h]
  unsigned __int64 v97; // [rsp+128h] [rbp+28h]
  LPCWSTR v98[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v99; // [rsp+148h] [rbp+48h]
  LPCWSTR v100[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v101; // [rsp+160h] [rbp+60h]
  LPCWSTR StringSid[4]; // [rsp+170h] [rbp+70h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v104[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v105; // [rsp+1C0h] [rbp+C0h]
  _BYTE v106[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v107[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  HKEY hkey; // [rsp+210h] [rbp+110h] BYREF
  int v109; // [rsp+218h] [rbp+118h]
  _BYTE v110[12]; // [rsp+21Ch] [rbp+11Ch]
  _DWORD v111[2]; // [rsp+228h] [rbp+128h] BYREF
  const wchar_t *v112; // [rsp+230h] [rbp+130h]
  int v113; // [rsp+238h] [rbp+138h]
  int v114; // [rsp+23Ch] [rbp+13Ch]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v1 = 0;
  v78 = 0;
  hMem = 0;
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (const unsigned __int16 *)&hMem,
                                        pdwType);
  v3 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v79 = 0;
    v5 = operator new(0x50u);
    *v5 = v5;
    v5[1] = v5;
    *(_QWORD *)&v79 = v5;
    v6 = hMem;
    NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v84, HKEY_LOCAL_MACHINE, (LPCWSTR)hMem);
    v93[0] = v84;
    v93[1] = v86;
    v7 = 0;
    v94 = 0;
    v8 = v85;
    v78 = v85;
    while ( v7 != v8 )
    {
      NgcUtils::RegKeyIterator::Iterator::operator*(v93, StringSid);
      v9 = (void *)std::operator+<unsigned short>(v104, StringSid);
      v10 = std::wstring::append(v9, L"UserNames");
      *(_OWORD *)v100 = 0;
      v101 = 0;
      *(_OWORD *)v100 = *(_OWORD *)v10;
      v101 = *(_OWORD *)(v10 + 16);
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 7;
      *(_WORD *)v10 = 0;
      v1 |= 1u;
      std::wstring::~wstring(v104, v11, v12);
      v13 = (const WCHAR *)v100;
      if ( *((_QWORD *)&v101 + 1) > 7u )
        v13 = v100[0];
      NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey, v84, v13);
      v16 = v88;
      if ( v88 >= 2 )
      {
        v95 = 0;
        v96 = 0;
        v97 = 7;
        LOWORD(v95) = 0;
        FileTime2 = v89;
        v104[0] = hKey;
        v104[1] = v90;
        v17 = 0;
        v105 = 0;
        while ( v17 != v16 )
        {
          NgcUtils::RegKeyIterator::Iterator::operator*(v104, v98);
          v18 = (const WCHAR *)v98;
          if ( v99 > 7 )
            v18 = v98[0];
          NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey, hKey, v18);
          v91[0] = hkey;
          v91[1] = v111;
          v19 = 0;
          v92 = 0;
          v20 = v109;
          while ( 1 )
          {
            if ( v19 == v20 )
              goto LABEL_44;
            NgcUtils::RegKeyIterator::Iterator::operator*(v91, lpSubKey);
            pvData = 0;
            pcbData = 4;
            v21 = (const WCHAR *)lpSubKey;
            if ( lpSubKey[3] > (LPCWSTR)7 )
              v21 = lpSubKey[0];
            ValueW = RegGetValueW(hkey, v21, L"UserEntered", 0x10u, 0, &pvData, &pcbData);
            if ( ValueW )
            {
              LastError = wil::details::in1diag3::Return_Win32(
                            retaddr,
                            (void *)0x636,
                            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                            (const char *)ValueW,
                            (unsigned int)pdwTypea);
LABEL_54:
              std::wstring::~wstring(lpSubKey, v49, v51);
              std::vector<unsigned short>::~vector<unsigned short>(v111);
              if ( hkey )
                RegCloseKey(hkey);
              std::wstring::~wstring(v98, v52, v53);
              std::wstring::~wstring(&v95, v54, v55);
              std::vector<unsigned short>::~vector<unsigned short>(v90);
              if ( hKey )
                RegCloseKey(hKey);
              std::wstring::~wstring(v100, v56, v57);
              std::wstring::~wstring(StringSid, v58, v59);
              goto LABEL_59;
            }
            if ( pvData )
              break;
            FileTime1 = *(FILETIME *)v110;
            if ( v96 )
            {
              Sid = 0;
              v27 = (const WCHAR *)StringSid;
              if ( StringSid[3] > (LPCWSTR)7 )
                v27 = StringSid[0];
              if ( !ConvertStringSidToSidW(v27, &Sid) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x64D,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v28);
                if ( Sid )
                  LocalFree(Sid);
                goto LABEL_54;
              }
              if ( CompareFileTime(&FileTime1, &FileTime2) == 1 )
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
                {
                  v31 = &v95;
                  if ( v97 > 7 )
                    v31 = (__int128 *)v95;
                  v32 = v98;
                  if ( v99 > 7 )
                    LODWORD(v32) = v98[0];
                  McTemplateU0kzz_EventWriteTransfer(v30, v29, (_DWORD)Sid, (_DWORD)v32, (__int64)v31);
                }
                std::wstring::wstring(v106, StringSid);
                std::wstring::wstring(v107, &v95);
                v1 |= 2u;
                std::list<std::pair<std::wstring,std::wstring>>::push_back(&v79, v106);
                std::wstring::~wstring(v107, v33, v34);
                std::wstring::~wstring(v106, v35, v36);
                std::wstring::operator=(&v95, v98);
                FileTime2 = FileTime1;
              }
              else
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
                {
                  v37 = v98;
                  if ( v99 > 7 )
                    v37 = (LPCWSTR *)v98[0];
                  v38 = &v95;
                  if ( v97 > 7 )
                    LODWORD(v38) = v95;
                  McTemplateU0kzz_EventWriteTransfer(v30, v29, (_DWORD)Sid, (_DWORD)v38, (__int64)v37);
                }
                std::wstring::wstring(v106, StringSid);
                std::wstring::wstring(v107, v98);
                v1 |= 4u;
                std::list<std::pair<std::wstring,std::wstring>>::push_back(&v79, v106);
                std::wstring::~wstring(v107, v39, v40);
                std::wstring::~wstring(v106, v41, v42);
              }
              if ( Sid )
                LocalFree(Sid);
            }
            else
            {
              std::wstring::operator=(&v95, v98);
              FileTime2 = FileTime1;
            }
            std::wstring::~wstring(lpSubKey, v25, v26);
            v92 = ++v19;
          }
          std::wstring::~wstring(lpSubKey, v23, v24);
LABEL_44:
          std::vector<unsigned short>::~vector<unsigned short>(v111);
          if ( hkey )
            RegCloseKey(hkey);
          std::wstring::~wstring(v98, v43, v44);
          v105 = ++v17;
        }
        std::wstring::~wstring(&v95, v14, v15);
      }
      std::vector<unsigned short>::~vector<unsigned short>(v90);
      if ( hKey )
        RegCloseKey(hKey);
      std::wstring::~wstring(v100, v45, v46);
      std::wstring::~wstring(StringSid, v47, v48);
      v94 = ++v7;
      v8 = v78;
    }
    v60 = (__int64 *)v79;
    for ( i = *(__int64 **)v79; ; i = (__int64 *)*i )
    {
      if ( i == v60 )
      {
        std::vector<unsigned short>::~vector<unsigned short>(v86);
        if ( v84 )
          RegCloseKey(v84);
        std::list<std::pair<std::wstring,std::wstring>>::~list<std::pair<std::wstring,std::wstring>>(&v79);
        if ( v6 )
          LocalFree(v6);
        return 0;
      }
      v62 = (void **)(i + 2);
      if ( (unsigned __int64)i[5] <= 7 )
        v63 = i + 2;
      else
        v63 = *v62;
      v64 = (const wchar_t *)(i + 6);
      v65 = NgcUtils::Detail::CacheRemoveUser(v63, (LPCWSTR)i + 24);
      v66 = v65;
      if ( v65 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x670,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
          (const char *)(unsigned int)v65,
          (int)pdwTypea);
        std::vector<unsigned short>::~vector<unsigned short>(v86);
        if ( v84 )
          RegCloseKey(v84);
        std::list<std::pair<std::wstring,std::wstring>>::~list<std::pair<std::wstring,std::wstring>>(&v79);
        if ( v6 )
          LocalFree(v6);
        return v66;
      }
      Sid = 0;
      v67 = (unsigned __int64)i[5] <= 7 ? (const WCHAR *)(i + 2) : (const WCHAR *)*v62;
      if ( !ConvertStringSidToSidW(v67, &Sid) )
        break;
      if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
      {
        if ( (unsigned __int64)i[9] > 7 )
          v64 = *(const wchar_t **)v64;
        v70 = (__int64 *)Sid;
        if ( Sid )
        {
          v71 = 4 * *((unsigned __int8 *)Sid + 1) + 8;
        }
        else
        {
          v70 = &qword_180064FA0;
          v71 = 8;
        }
        *(_QWORD *)&v110[4] = v70;
        v111[0] = v71;
        v111[1] = 0;
        if ( v64 )
        {
          v72 = -1;
          do
            ++v72;
          while ( v64[v72] );
          v73 = 2 * v72 + 2;
        }
        else
        {
          v64 = L"NULL";
          v73 = 10;
        }
        v112 = v64;
        v113 = v73;
        v114 = 0;
        pdwTypea = &hkey;
        McGenEventWrite_EventWriteTransfer(v70, EVENT_HFB_USERNAMESIDCACHE_REMOVED_STALEUSERNAME, v68, 3);
      }
      if ( Sid )
        LocalFree(Sid);
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x675,
                  (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                  v69);
    if ( Sid )
      LocalFree(Sid);
LABEL_59:
    std::vector<unsigned short>::~vector<unsigned short>(v86);
    if ( v84 )
      RegCloseKey(v84);
    std::list<std::pair<std::wstring,std::wstring>>::~list<std::pair<std::wstring,std::wstring>>(&v79);
    if ( v6 )
      LocalFree(v6);
    return LastError;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x618,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      (int)pdwTypea);
    if ( hMem )
      LocalFree(hMem);
    return v3;
  }
}

```

## disassembly

```asm
0x180017718  push    rbp
0x18001771a  push    rbx
0x18001771b  push    rsi
0x18001771c  push    rdi
0x18001771d  push    r12
0x18001771f  push    r13
0x180017721  push    r14
0x180017723  push    r15
0x180017725  lea     rbp, [rsp-158h]
0x18001772d  sub     rsp, 258h
0x180017734  mov     rax, cs:__security_cookie
0x18001773b  xor     rax, rsp
0x18001773e  mov     [rbp+190h+var_50], rax
0x180017745  xor     r12d, r12d
0x180017748  mov     r15d, r12d
0x18001774b  mov     [rsp+290h+var_244], r12d
0x180017750  mov     [rsp+290h+hMem], r12
0x180017755  lea     r9, [rsp+290h+hMem]; unsigned __int16 *
0x18001775a  xor     r8d, r8d; unsigned __int16 *
0x18001775d  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017764  lea     rcx, aNgccredprov; "NgcCredprov"
0x18001776b  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180017770  mov     ebx, eax
0x180017772  test    eax, eax
0x180017774  jns     short loc_1800177A9
0x180017776  mov     rcx, [rbp+198h]; this
0x18001777d  mov     r9d, eax; char *
0x180017780  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180017787  mov     edx, 618h; void *
0x18001778c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017791  nop
0x180017792  mov     rcx, [rsp+290h+hMem]; hMem
0x180017797  test    rcx, rcx
0x18001779a  jz      short loc_1800177A2
0x18001779c  call    cs:__imp_LocalFree
0x1800177a2  mov     eax, ebx
0x1800177a4  jmp     loc_180017EDD
0x1800177a9  xorps   xmm0, xmm0
0x1800177ac  movdqu  [rsp+290h+var_240], xmm0
0x1800177b2  mov     ecx, 50h ; 'P'; Size
0x1800177b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800177bc  mov     [rax], rax
0x1800177bf  mov     [rax+8], rax
0x1800177c3  mov     qword ptr [rsp+290h+var_240], rax
0x1800177c8  mov     rbx, [rsp+290h+hMem]
0x1800177cd  mov     r8, rbx; lpSubKey
0x1800177d0  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800177d7  lea     rcx, [rbp+190h+var_210]; this
0x1800177db  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x1800177e0  nop
0x1800177e1  mov     rax, [rbp+190h+var_210]
0x1800177e5  mov     [rbp+190h+var_198], rax
0x1800177e9  lea     rax, [rbp+190h+var_1F8]
0x1800177ed  mov     [rbp+190h+var_190], rax
0x1800177f1  mov     r14d, r12d
0x1800177f4  mov     [rbp+190h+var_188], r12d
0x1800177f8  mov     eax, [rbp+190h+var_208]
0x1800177fb  mov     [rsp+290h+var_244], eax
0x1800177ff  cmp     r14d, eax
0x180017802  jz      loc_180017CFE
0x180017808  lea     rdx, [rbp+190h+StringSid]
0x18001780c  lea     rcx, [rbp+190h+var_198]
0x180017810  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x180017815  nop
0x180017816  lea     rdx, [rbp+190h+StringSid]
0x18001781a  lea     rcx, [rbp+190h+var_E0]
0x180017821  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180017826  nop
0x180017827  lea     rdx, aUsernames; "UserNames"
0x18001782e  mov     rcx, rax; Src
0x180017831  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180017836  xorps   xmm0, xmm0
0x180017839  movups  xmmword ptr [rbp+190h+var_140], xmm0
0x18001783d  xorps   xmm1, xmm1
0x180017840  movdqu  [rbp+190h+var_130], xmm1
0x180017845  movups  xmm0, xmmword ptr [rax]
0x180017848  movups  xmmword ptr [rbp+190h+var_140], xmm0
0x18001784c  movups  xmm1, xmmword ptr [rax+10h]
0x180017850  movups  [rbp+190h+var_130], xmm1
0x180017854  mov     [rax+10h], r12
0x180017858  mov     qword ptr [rax+18h], 7
0x180017860  mov     [rax], r12w
0x180017864  or      r15d, 1
0x180017868  lea     rcx, [rbp+190h+var_E0]
0x18001786f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017874  lea     r8, [rbp+190h+var_140]
0x180017878  cmp     qword ptr [rbp+190h+var_130+8], 7
0x18001787d  cmova   r8, [rbp+190h+var_140]; lpSubKey
0x180017882  mov     rdx, [rbp+190h+var_210]; hKey
0x180017886  lea     rcx, [rbp+190h+hKey]; this
0x18001788a  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18001788f  nop
0x180017890  mov     r13d, [rbp+190h+var_1D8]
0x180017894  cmp     r13d, 2
0x180017898  jb      loc_180017BD3
0x18001789e  xorps   xmm0, xmm0
0x1800178a1  movups  [rbp+190h+var_180], xmm0
0x1800178a5  mov     [rbp+190h+var_170], r12
0x1800178a9  mov     [rbp+190h+var_168], 7
0x1800178b1  mov     word ptr [rbp+190h+var_180], r12w
0x1800178b6  mov     rax, [rbp+190h+var_1D4]
0x1800178ba  mov     qword ptr [rsp+290h+FileTime2.dwLowDateTime], rax
0x1800178bf  mov     rax, [rbp+190h+hKey]
0x1800178c3  mov     [rbp+190h+var_E0], rax
0x1800178ca  lea     rax, [rbp+190h+var_1C8]
0x1800178ce  mov     [rbp+190h+var_D8], rax
0x1800178d5  mov     edi, r12d
0x1800178d8  mov     [rbp+190h+var_D0], r12d
0x1800178df  cmp     edi, r13d
0x1800178e2  jz      loc_180017BC9
0x1800178e8  lea     rdx, [rbp+190h+var_160]
0x1800178ec  lea     rcx, [rbp+190h+var_E0]
0x1800178f3  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x1800178f8  nop
0x1800178f9  lea     r8, [rbp+190h+var_160]
0x1800178fd  cmp     [rbp+190h+var_148], 7
0x180017902  cmova   r8, [rbp+190h+var_160]; lpSubKey
0x180017907  mov     rdx, [rbp+190h+hKey]; hKey
0x18001790b  lea     rcx, [rbp+190h+hkey]; this
0x180017912  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x180017917  nop
0x180017918  mov     rax, [rbp+190h+hkey]
0x18001791f  mov     [rbp+190h+var_1B0], rax
0x180017923  lea     rax, [rbp+190h+var_68]
0x18001792a  mov     [rbp+190h+var_1A8], rax
0x18001792e  mov     esi, r12d
0x180017931  mov     [rbp+190h+var_1A0], r12d
0x180017935  mov     r12d, [rbp+190h+var_78]
0x18001793c  cmp     esi, r12d
0x18001793f  jz      loc_180017B91
0x180017945  lea     rdx, [rbp+190h+lpSubKey]
0x18001794c  lea     rcx, [rbp+190h+var_1B0]
0x180017950  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x180017955  nop
0x180017956  mov     [rsp+290h+var_248], 0
0x18001795e  mov     [rsp+290h+var_230], 4
0x180017966  lea     rdx, [rbp+190h+lpSubKey]
0x18001796d  cmp     [rbp+190h+var_E8], 7
0x180017975  cmova   rdx, [rbp+190h+lpSubKey]; lpSubKey
0x18001797d  lea     rax, [rsp+290h+var_230]
0x180017982  mov     [rsp+290h+pcbData], rax; pcbData
0x180017987  lea     rax, [rsp+290h+var_248]
0x18001798c  mov     [rsp+290h+pvData], rax; pvData
0x180017991  mov     [rsp+290h+pdwType], 0; unsigned int
0x18001799a  mov     r9d, 10h; dwFlags
0x1800179a0  lea     r8, aUserentered; "UserEntered"
0x1800179a7  mov     rcx, [rbp+190h+hkey]; hkey
0x1800179ae  call    cs:__imp_RegGetValueW
0x1800179b4  xor     ecx, ecx
0x1800179b6  test    eax, eax
0x1800179b8  jnz     loc_180017C3B
0x1800179be  cmp     [rsp+290h+var_248], ecx
0x1800179c2  jnz     loc_180017B84
0x1800179c8  mov     rax, qword ptr [rbp+190h+var_74]
0x1800179cf  mov     qword ptr [rsp+290h+FileTime1.dwLowDateTime], rax
0x1800179d4  cmp     [rbp+190h+var_170], rcx
0x1800179d8  jnz     short loc_1800179F6
0x1800179da  lea     rdx, [rbp+190h+var_160]
0x1800179de  lea     rcx, [rbp+190h+var_180]
0x1800179e2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800179e7  mov     rax, qword ptr [rsp+290h+FileTime1.dwLowDateTime]
0x1800179ec  mov     qword ptr [rsp+290h+FileTime2.dwLowDateTime], rax
0x1800179f1  jmp     loc_180017B6E
0x1800179f6  mov     [rsp+290h+Sid], rcx
0x1800179fb  lea     rcx, [rbp+190h+StringSid]
0x1800179ff  cmp     [rbp+190h+var_108], 7
0x180017a07  cmova   rcx, [rbp+190h+StringSid]; StringSid
0x180017a0c  lea     rdx, [rsp+290h+Sid]; Sid
0x180017a11  call    cs:__imp_ConvertStringSidToSidW
0x180017a17  test    eax, eax
0x180017a19  jz      loc_180017C0F
0x180017a1f  lea     rdx, [rsp+290h+FileTime2]; lpFileTime2
0x180017a24  lea     rcx, [rsp+290h+FileTime1]; lpFileTime1
0x180017a29  call    cs:__imp_CompareFileTime
0x180017a2f  cmp     eax, 1
0x180017a32  jnz     loc_180017AD8
0x180017a38  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x180017a3f  jz      short loc_180017A6C
0x180017a41  lea     rax, [rbp+190h+var_180]
0x180017a45  cmp     [rbp+190h+var_168], 7
0x180017a4a  cmova   rax, qword ptr [rbp+190h+var_180]
0x180017a4f  lea     r9, [rbp+190h+var_160]
0x180017a53  cmp     [rbp+190h+var_148], 7
0x180017a58  cmova   r9, [rbp+190h+var_160]
0x180017a5d  mov     [rsp+290h+pdwType], rax
0x180017a62  mov     r8, [rsp+290h+Sid]
0x180017a67  call    McTemplateU0kzz_EventWriteTransfer
0x180017a6c  lea     rdx, [rbp+190h+StringSid]
0x180017a70  lea     rcx, [rbp+190h+var_C0]
0x180017a77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017a7c  nop
0x180017a7d  lea     rdx, [rbp+190h+var_180]
0x180017a81  lea     rcx, [rbp+190h+var_A0]
0x180017a88  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017a8d  nop
0x180017a8e  or      r15d, 2
0x180017a92  lea     rdx, [rbp+190h+var_C0]
0x180017a99  lea     rcx, [rsp+290h+var_240]
0x180017a9e  call    ?push_back@?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::list<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x180017aa3  nop
0x180017aa4  lea     rcx, [rbp+190h+var_A0]
0x180017aab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017ab0  lea     rcx, [rbp+190h+var_C0]
0x180017ab7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017abc  lea     rdx, [rbp+190h+var_160]
0x180017ac0  lea     rcx, [rbp+190h+var_180]
0x180017ac4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180017ac9  mov     rax, qword ptr [rsp+290h+FileTime1.dwLowDateTime]
0x180017ace  mov     qword ptr [rsp+290h+FileTime2.dwLowDateTime], rax
0x180017ad3  jmp     loc_180017B5D
0x180017ad8  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x180017adf  jz      short loc_180017B0C
0x180017ae1  lea     rax, [rbp+190h+var_160]
0x180017ae5  cmp     [rbp+190h+var_148], 7
0x180017aea  cmova   rax, [rbp+190h+var_160]
0x180017aef  lea     r9, [rbp+190h+var_180]
0x180017af3  cmp     [rbp+190h+var_168], 7
0x180017af8  cmova   r9, qword ptr [rbp+190h+var_180]
0x180017afd  mov     [rsp+290h+pdwType], rax
0x180017b02  mov     r8, [rsp+290h+Sid]
0x180017b07  call    McTemplateU0kzz_EventWriteTransfer
0x180017b0c  lea     rdx, [rbp+190h+StringSid]
0x180017b10  lea     rcx, [rbp+190h+var_C0]
0x180017b17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017b1c  nop
0x180017b1d  lea     rdx, [rbp+190h+var_160]
0x180017b21  lea     rcx, [rbp+190h+var_A0]
0x180017b28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017b2d  nop
0x180017b2e  or      r15d, 4
0x180017b32  lea     rdx, [rbp+190h+var_C0]
0x180017b39  lea     rcx, [rsp+290h+var_240]
0x180017b3e  call    ?push_back@?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::list<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x180017b43  nop
0x180017b44  lea     rcx, [rbp+190h+var_A0]
0x180017b4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017b50  lea     rcx, [rbp+190h+var_C0]
0x180017b57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017b5c  nop
0x180017b5d  mov     rcx, [rsp+290h+Sid]; hMem
0x180017b62  test    rcx, rcx
0x180017b65  jz      short loc_180017B6E
0x180017b67  call    cs:__imp_LocalFree
0x180017b6d  nop
0x180017b6e  lea     rcx, [rbp+190h+lpSubKey]
0x180017b75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017b7a  inc     esi
0x180017b7c  mov     [rbp+190h+var_1A0], esi
0x180017b7f  jmp     loc_18001793C
0x180017b84  lea     rcx, [rbp+190h+lpSubKey]
0x180017b8b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017b90  nop
0x180017b91  lea     rcx, [rbp+190h+var_68]
0x180017b98  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180017b9d  mov     rcx, [rbp+190h+hkey]; hKey
0x180017ba4  xor     r12d, r12d
0x180017ba7  test    rcx, rcx
0x180017baa  jz      short loc_180017BB3
0x180017bac  call    cs:__imp_RegCloseKey
0x180017bb2  nop
0x180017bb3  lea     rcx, [rbp+190h+var_160]
0x180017bb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017bbc  inc     edi
0x180017bbe  mov     [rbp+190h+var_D0], edi
0x180017bc4  jmp     loc_1800178DF
0x180017bc9  lea     rcx, [rbp+190h+var_180]
0x180017bcd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017bd2  nop
0x180017bd3  lea     rcx, [rbp+190h+var_1C8]
0x180017bd7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180017bdc  mov     rcx, [rbp+190h+hKey]; hKey
0x180017be0  test    rcx, rcx
0x180017be3  jz      short loc_180017BEC
0x180017be5  call    cs:__imp_RegCloseKey
0x180017beb  nop
0x180017bec  lea     rcx, [rbp+190h+var_140]
0x180017bf0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017bf5  nop
0x180017bf6  lea     rcx, [rbp+190h+StringSid]
0x180017bfa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017bff  inc     r14d
0x180017c02  mov     [rbp+190h+var_188], r14d
0x180017c06  mov     eax, [rsp+290h+var_244]
0x180017c0a  jmp     loc_1800177FF
0x180017c0f  mov     rcx, [rbp+198h]; this
0x180017c16  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180017c1d  mov     edx, 64Dh; void *
0x180017c22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017c27  mov     edi, eax
0x180017c29  mov     rcx, [rsp+290h+Sid]; hMem
0x180017c2e  test    rcx, rcx
0x180017c31  jz      short loc_180017C58
0x180017c33  call    cs:__imp_LocalFree
0x180017c39  jmp     short loc_180017C58
0x180017c3b  mov     rcx, [rbp+198h]; this
0x180017c42  mov     r9d, eax; char *
0x180017c45  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180017c4c  mov     edx, 636h; void *
0x180017c51  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017c56  mov     edi, eax
  ... truncated ...
```
