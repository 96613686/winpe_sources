# DafGetProvidersInfo

- ea: `0x18005eee4`
- end: `0x18005f49b`
- name: `DafGetProvidersInfo`
- size: `1463`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, void (__fastcall *)(_QWORD, __int64, __int128 *))`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800272ec`

## callees

- `0x180023ed0`
- `0x18003aa4c`
- `0x18003bc80`
- `0x18003c79c`
- `0x180042bb0`
- `0x180049474`
- `0x180049834`
- `0x18005ee9c`
- `0x18005eee4`
- `0x18007e9cc`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005f084`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005f084`
- `RPCRT4!UuidFromStringW` at `0x18005f118`
- `RPCRT4!UuidFromStringW` at `0x18005f1e6`
- `RPCRT4!UuidFromStringW` at `0x18005f118`
- `RPCRT4!UuidFromStringW` at `0x18005f1e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ef81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005efca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ef81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005efca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005f03d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005f03d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f0ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f1bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f286`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f0ee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f1bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005f286`

## string_xrefs

- `0x18005f192`: `CLSID`
- `0x18005f0bc`: `ProtocolId`
- `0x18005f140`: `failed to convert protocol id guid string, "%ls"`

## pseudocode

```c
__int64 __fastcall DafGetProvidersInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void (__fastcall *a5)(_QWORD, __int64, __int128 *))
{
  HKEY *p_hKey; // rdi
  __int64 v7; // rbx
  __int64 v8; // rsi
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int i; // r15d
  HKEY v12; // r14
  DWORD j; // r12d
  unsigned int v14; // eax
  wchar_t **v15; // rdi
  LSTATUS ValueW; // eax
  unsigned int v17; // eax
  LSTATUS v18; // eax
  unsigned int v19; // eax
  DWORD v20; // edx
  char *v21; // r8
  __int64 v22; // rdx
  unsigned int v23; // esi
  char *v24; // rdi
  char *v26; // rdi
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  const char *lpClass; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v34; // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall *v35)(_QWORD, __int64, __int128 *); // [rsp+60h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+78h] [rbp-88h]
  __int128 *v38; // [rsp+88h] [rbp-78h]
  __int128 Buf2; // [rsp+90h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+A0h] [rbp-60h] BYREF
  UUID Buf1; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-40h] BYREF
  int v43; // [rsp+D0h] [rbp-30h]
  int v44; // [rsp+D4h] [rbp-2Ch]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+E0h] [rbp-20h]
  DWORD v47; // [rsp+E4h] [rbp-1Ch]
  WCHAR *v48; // [rsp+E8h] [rbp-18h]
  __int128 v49; // [rsp+F0h] [rbp-10h]
  int v50; // [rsp+100h] [rbp+0h]
  int v51; // [rsp+104h] [rbp+4h]
  __int64 v52; // [rsp+108h] [rbp+8h]
  int v53; // [rsp+110h] [rbp+10h]
  int v54; // [rsp+114h] [rbp+14h]
  UUID *p_Uuid; // [rsp+118h] [rbp+18h]
  __int128 v56; // [rsp+120h] [rbp+20h]
  int v57; // [rsp+130h] [rbp+30h]
  int v58; // [rsp+134h] [rbp+34h]
  __int64 v59; // [rsp+138h] [rbp+38h]
  int v60; // [rsp+140h] [rbp+40h]
  int v61; // [rsp+144h] [rbp+44h]
  UUID *p_Buf1; // [rsp+148h] [rbp+48h]
  __int128 v63; // [rsp+150h] [rbp+50h]
  int v64; // [rsp+160h] [rbp+60h]
  int v65; // [rsp+164h] [rbp+64h]
  __int64 v66; // [rsp+168h] [rbp+68h]
  int v67; // [rsp+170h] [rbp+70h]
  DWORD v68; // [rsp+174h] [rbp+74h]
  char *v69; // [rsp+178h] [rbp+78h]
  char pvData[2]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 StringUuid[36]; // [rsp+182h] [rbp+82h] BYREF
  __int16 v72; // [rsp+1CAh] [rbp+CAh]
  WCHAR Name[256]; // [rsp+390h] [rbp+290h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5E8h] [rbp+4E8h]

  p_hKey = &hKey;
  v35 = a5;
  v38 = 0;
  v36 = 0;
  v7 = 2;
  v8 = 2;
  v37 = 0;
  do
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(p_hKey++);
    --v8;
  }
  while ( v8 );
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Device Association Framework\\InboxProviders",
         0,
         0x20019u,
         &hKey);
  if ( v9 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\helpers\\provider.cpp",
      (const char *)v9,
      phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v34,
    0);
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Device Association Framework\\Providers",
          0,
          0x20019u,
          &v34);
  if ( v10 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\helpers\\provider.cpp",
      (const char *)v10,
      phkResulta);
  for ( i = 0; i < 2; ++i )
  {
    v12 = *(&hKey + i);
    if ( v12 )
    {
      for ( j = 0; ; ++j )
      {
        cchName = 255;
        v14 = RegEnumKeyExW(v12, j, Name, &cchName, 0, 0, 0, 0);
        if ( v14 == 259 )
          break;
        if ( v14 )
        {
          v23 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x77,
                  (unsigned int)"onecore\\base\\devices\\association\\libs\\helpers\\provider.cpp",
                  (const char *)v14,
                  (unsigned int)"failed to enumerate provider's key",
                  lpClass);
          v24 = (char *)&v35;
          do
          {
            v24 -= 8;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(v24);
            --v7;
          }
          while ( v7 );
          return v23;
        }
        while ( (unsigned int)v8 < 0x15 )
        {
          v15 = &off_180089560[4 * (unsigned int)v8];
          if ( CompareStringOrdinal(Name, -1, *v15, -1, 1) == 2 )
          {
            LODWORD(v8) = 0;
            goto LABEL_18;
          }
          LODWORD(v8) = v8 + 1;
        }
        LODWORD(v8) = 0;
        v15 = 0;
LABEL_18:
        memset_0(pvData, 0, 0x208u);
        pdwType = 0;
        pcbData = 520;
        ValueW = RegGetValueW(v12, Name, L"ProtocolId", 2u, &pdwType, pvData, &pcbData);
        Uuid = 0;
        if ( !ValueW && pdwType == 1 )
        {
          v72 = 0;
          v17 = UuidFromStringW(StringUuid, &Uuid);
          wil::details::in1diag3::Log_IfWin32ErrorMsg(
            retaddr,
            (void *)0x86,
            (unsigned int)"onecore\\base\\devices\\association\\libs\\helpers\\provider.cpp",
            (const char *)v17,
            (unsigned int)"failed to convert protocol id guid string, \"%ls\"",
            pvData);
        }
        Buf2 = 0;
        if ( !memcmp_0(&Uuid, &Buf2, 0x10u) && v15 )
          Uuid = *(UUID *)v15[2];
        pcbData = 520;
        v18 = RegGetValueW(v12, Name, L"CLSID", 2u, &pdwType, pvData, &pcbData);
        Buf1 = 0;
        if ( !v18 && pdwType == 1 )
        {
          v72 = 0;
          v19 = UuidFromStringW(StringUuid, &Buf1);
          wil::details::in1diag3::Log_IfWin32ErrorMsg(
            retaddr,
            (void *)0x96,
            (unsigned int)"onecore\\base\\devices\\association\\libs\\helpers\\provider.cpp",
            (const char *)v19,
            (unsigned int)"failed to convert class id guid string, \"%ls\"",
            pvData);
        }
        Buf2 = 0;
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) && v15 )
          Buf1 = *(UUID *)v15[3];
        pcbData = 520;
        if ( RegGetValueW(v12, Name, 0, 2u, &pdwType, pvData, &pcbData) || pdwType != 1 )
        {
          v20 = 0;
          v21 = 0;
          pcbData = 0;
          if ( v15 )
          {
            v21 = (char *)v15[1];
            v22 = -1;
            do
              ++v22;
            while ( *(_WORD *)&v21[2 * v22] );
            v20 = 2 * v22 + 2;
            pcbData = v20;
          }
        }
        else
        {
          v20 = pcbData;
          v21 = pvData;
        }
        v43 = 2;
        v42 = DEVPKEY_Protocol_ProviderName;
        v68 = v20;
        v69 = v21;
        v47 = 2 * cchName + 2;
        v48 = Name;
        v50 = 4;
        p_Uuid = &Uuid;
        v57 = 5;
        p_Buf1 = &Buf1;
        v64 = 3;
        v49 = DEVPKEY_Protocol_ProtocolId;
        v44 = 0;
        v45 = 0;
        v56 = DEVPKEY_Protocol_ProviderClassId;
        *(_QWORD *)&v37 = Name;
        v67 = v21 != 0 ? 0x12 : 0;
        v38 = &v42;
        v46 = 18;
        v51 = 0;
        v52 = 0;
        v53 = 13;
        v54 = 16;
        v58 = 0;
        v59 = 0;
        v60 = 13;
        v61 = 16;
        v63 = DEVPKEY_Protocol_ProviderFriendlyName;
        v65 = 0;
        v66 = 0;
        LODWORD(v36) = 1;
        DWORD2(v36) = 12;
        DWORD2(v37) = 4;
        v35(0, a4, &v36);
        v36 = 0;
        v38 = 0;
        v37 = 0;
      }
    }
  }
  v26 = (char *)&v35;
  do
  {
    v26 -= 8;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(v26);
    --v7;
  }
  while ( v7 );
  LODWORD(v36) = 0;
  DWORD2(v36) = 1;
  v35(0, a4, &v36);
  return 0;
}

```

## disassembly

```asm
0x18005eee4  push    rbp
0x18005eee6  push    rbx
0x18005eee7  push    rsi
0x18005eee8  push    rdi
0x18005eee9  push    r12
0x18005eeeb  push    r13
0x18005eeed  push    r14
0x18005eeef  push    r15
0x18005eef1  lea     rbp, [rsp-4A8h]
0x18005eef9  sub     rsp, 5A8h
0x18005ef00  mov     rax, cs:__security_cookie
0x18005ef07  xor     rax, rsp
0x18005ef0a  mov     [rbp+4E0h+var_50], rax
0x18005ef11  mov     r14, [rbp+4E0h+arg_20]
0x18005ef18  lea     rdi, [rsp+5E0h+hKey]
0x18005ef1d  xor     eax, eax
0x18005ef1f  mov     [rsp+5E0h+var_580], r14
0x18005ef24  xorps   xmm0, xmm0
0x18005ef27  mov     [rbp+4E0h+var_558], rax
0x18005ef2b  mov     r13, r9
0x18005ef2e  movups  [rsp+5E0h+var_578], xmm0
0x18005ef33  lea     ebx, [rax+2]
0x18005ef36  mov     esi, ebx
0x18005ef38  movups  [rsp+5E0h+var_568], xmm0
0x18005ef3d  mov     rcx, rdi; void *
0x18005ef40  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>(void)
0x18005ef45  add     rdi, 8
0x18005ef49  sub     rsi, 1
0x18005ef4d  jnz     short loc_18005EF3D
0x18005ef4f  xor     edx, edx
0x18005ef51  lea     rcx, [rsp+5E0h+hKey]
0x18005ef56  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005ef5b  lea     rax, [rsp+5E0h+hKey]
0x18005ef60  mov     edi, 20019h
0x18005ef65  mov     r14, 0FFFFFFFF80000002h
0x18005ef6c  mov     [rsp+5E0h+phkResult], rax; unsigned int
0x18005ef71  mov     r9d, edi; samDesired
0x18005ef74  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Device Association"...
0x18005ef7b  mov     rcx, r14; hKey
0x18005ef7e  xor     r8d, r8d; ulOptions
0x18005ef81  call    cs:__imp_RegOpenKeyExW
0x18005ef87  test    eax, eax
0x18005ef89  jz      short loc_18005EFA4
0x18005ef8b  mov     rcx, [rbp+4E8h]; this
0x18005ef92  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\association\\li"...
0x18005ef99  mov     r9d, eax; char *
0x18005ef9c  lea     edx, [rsi+5Fh]; void *
0x18005ef9f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005efa4  xor     edx, edx
0x18005efa6  lea     rcx, [rsp+5E0h+var_588]
0x18005efab  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005efb0  lea     rax, [rsp+5E0h+var_588]
0x18005efb5  mov     r9d, edi; samDesired
0x18005efb8  xor     r8d, r8d; ulOptions
0x18005efbb  mov     [rsp+5E0h+phkResult], rax; unsigned int
0x18005efc0  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Device Association"...
0x18005efc7  mov     rcx, r14; hKey
0x18005efca  call    cs:__imp_RegOpenKeyExW
0x18005efd0  test    eax, eax
0x18005efd2  jz      short loc_18005EFEF
0x18005efd4  mov     rcx, [rbp+4E8h]; this
0x18005efdb  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\association\\li"...
0x18005efe2  mov     r9d, eax; char *
0x18005efe5  mov     edx, 60h ; '`'; void *
0x18005efea  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005efef  mov     r15d, esi
0x18005eff2  cmp     r15d, ebx
0x18005eff5  jnb     loc_18005F43F
0x18005effb  mov     eax, r15d
0x18005effe  mov     r14, [rsp+rax*8+5E0h+hKey]
0x18005f003  test    r14, r14
0x18005f006  jz      loc_18005F3F3
0x18005f00c  mov     r12d, esi
0x18005f00f  mov     [rsp+5E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18005f014  lea     r9, [rsp+5E0h+cchName]; lpcchName
0x18005f019  mov     [rsp+5E0h+lpcchClass], rsi; lpcchClass
0x18005f01e  lea     r8, [rbp+4E0h+Name]; lpName
0x18005f025  mov     [rsp+5E0h+lpClass], rsi; char *
0x18005f02a  mov     edx, r12d; dwIndex
0x18005f02d  mov     rcx, r14; hKey
0x18005f030  mov     [rsp+5E0h+phkResult], rsi; lpReserved
0x18005f035  mov     [rsp+5E0h+cchName], 0FFh
0x18005f03d  call    cs:__imp_RegEnumKeyExW
0x18005f043  cmp     eax, 103h
0x18005f048  jz      loc_18005F3F3
0x18005f04e  test    eax, eax
0x18005f050  jnz     loc_18005F3FB
0x18005f056  cmp     esi, 15h
0x18005f059  jnb     short loc_18005F096
0x18005f05b  lea     rcx, off_180089560; "AspInfra"
0x18005f062  mov     edi, esi
0x18005f064  or      r9d, 0FFFFFFFFh; cchCount2
0x18005f068  shl     rdi, 5
0x18005f06c  add     rdi, rcx
0x18005f06f  mov     dword ptr [rsp+5E0h+phkResult], 1; bIgnoreCase
0x18005f077  or      edx, r9d; cchCount1
0x18005f07a  lea     rcx, [rbp+4E0h+Name]; lpString1
0x18005f081  mov     r8, [rdi]; lpString2
0x18005f084  call    cs:__imp_CompareStringOrdinal
0x18005f08a  cmp     eax, ebx
0x18005f08c  jz      short loc_18005F092
0x18005f08e  inc     esi
0x18005f090  jmp     short loc_18005F056
0x18005f092  xor     esi, esi
0x18005f094  jmp     short loc_18005F09A
0x18005f096  xor     esi, esi
0x18005f098  mov     edi, esi
0x18005f09a  xor     edx, edx; Val
0x18005f09c  lea     rcx, [rbp+4E0h+pvData]; void *
0x18005f0a3  mov     r8d, 208h; Size
0x18005f0a9  call    memset_0
0x18005f0ae  lea     rax, [rsp+5E0h+pcbData]
0x18005f0b3  mov     [rsp+5E0h+pdwType], esi
0x18005f0b7  mov     [rsp+5E0h+lpcchClass], rax; pcbData
0x18005f0bc  lea     r8, aProtocolid; "ProtocolId"
0x18005f0c3  lea     rax, [rbp+4E0h+pvData]
0x18005f0ca  mov     [rsp+5E0h+pcbData], 208h
0x18005f0d2  mov     [rsp+5E0h+lpClass], rax; pvData
0x18005f0d7  lea     rdx, [rbp+4E0h+Name]; lpSubKey
0x18005f0de  lea     rax, [rsp+5E0h+pdwType]
0x18005f0e3  mov     r9d, ebx; dwFlags
0x18005f0e6  mov     rcx, r14; hkey
0x18005f0e9  mov     [rsp+5E0h+phkResult], rax; pdwType
0x18005f0ee  call    cs:__imp_RegGetValueW
0x18005f0f4  xorps   xmm0, xmm0
0x18005f0f7  movups  xmmword ptr [rbp+4E0h+Uuid.Data1], xmm0
0x18005f0fb  test    eax, eax
0x18005f0fd  jnz     short loc_18005F151
0x18005f0ff  cmp     [rsp+5E0h+pdwType], 1
0x18005f104  jnz     short loc_18005F151
0x18005f106  lea     rdx, [rbp+4E0h+Uuid]; Uuid
0x18005f10a  mov     [rbp+4E0h+var_416], si
0x18005f111  lea     rcx, [rbp+4E0h+StringUuid]; StringUuid
0x18005f118  call    cs:__imp_UuidFromStringW
0x18005f11e  mov     rcx, [rbp+4E8h]; this
0x18005f125  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\association\\li"...
0x18005f12c  mov     r9d, eax; char *
0x18005f12f  mov     edx, 86h; void *
0x18005f134  lea     rax, [rbp+4E0h+pvData]
0x18005f13b  mov     [rsp+5E0h+lpClass], rax; char *
0x18005f140  lea     rax, aFailedToConver; "failed to convert protocol id guid stri"...
0x18005f147  mov     [rsp+5E0h+phkResult], rax; unsigned int
0x18005f14c  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18005f151  xorps   xmm0, xmm0
0x18005f154  lea     rdx, [rbp+4E0h+Buf2]; Buf2
0x18005f158  mov     r8d, 10h; Size
0x18005f15e  lea     rcx, [rbp+4E0h+Uuid]; Buf1
0x18005f162  movups  [rbp+4E0h+Buf2], xmm0
0x18005f166  call    memcmp_0
0x18005f16b  test    eax, eax
0x18005f16d  jnz     short loc_18005F180
0x18005f16f  test    rdi, rdi
0x18005f172  jz      short loc_18005F180
0x18005f174  mov     rax, [rdi+10h]
0x18005f178  movups  xmm0, xmmword ptr [rax]
0x18005f17b  movdqu  xmmword ptr [rbp+4E0h+Uuid.Data1], xmm0
0x18005f180  lea     rax, [rsp+5E0h+pcbData]
0x18005f185  mov     [rsp+5E0h+pcbData], 208h
0x18005f18d  mov     [rsp+5E0h+lpcchClass], rax; pcbData
0x18005f192  lea     r8, ValueName; "CLSID"
0x18005f199  lea     rax, [rbp+4E0h+pvData]
0x18005f1a0  mov     r9d, ebx; dwFlags
0x18005f1a3  mov     [rsp+5E0h+lpClass], rax; pvData
0x18005f1a8  lea     rdx, [rbp+4E0h+Name]; lpSubKey
0x18005f1af  lea     rax, [rsp+5E0h+pdwType]
0x18005f1b4  mov     rcx, r14; hkey
0x18005f1b7  mov     [rsp+5E0h+phkResult], rax; pdwType
0x18005f1bc  call    cs:__imp_RegGetValueW
0x18005f1c2  xorps   xmm0, xmm0
0x18005f1c5  movups  xmmword ptr [rbp+4E0h+Buf1.Data1], xmm0
0x18005f1c9  test    eax, eax
0x18005f1cb  jnz     short loc_18005F21F
0x18005f1cd  cmp     [rsp+5E0h+pdwType], 1
0x18005f1d2  jnz     short loc_18005F21F
0x18005f1d4  lea     rdx, [rbp+4E0h+Buf1]; Uuid
0x18005f1d8  mov     [rbp+4E0h+var_416], si
0x18005f1df  lea     rcx, [rbp+4E0h+StringUuid]; StringUuid
0x18005f1e6  call    cs:__imp_UuidFromStringW
0x18005f1ec  mov     rcx, [rbp+4E8h]; this
0x18005f1f3  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\association\\li"...
0x18005f1fa  mov     r9d, eax; char *
0x18005f1fd  mov     edx, 96h; void *
0x18005f202  lea     rax, [rbp+4E0h+pvData]
0x18005f209  mov     [rsp+5E0h+lpClass], rax; char *
0x18005f20e  lea     rax, aFailedToConver_0; "failed to convert class id guid string,"...
0x18005f215  mov     [rsp+5E0h+phkResult], rax; unsigned int
0x18005f21a  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18005f21f  xorps   xmm0, xmm0
0x18005f222  lea     rdx, [rbp+4E0h+Buf2]; Buf2
0x18005f226  mov     r8d, 10h; Size
0x18005f22c  lea     rcx, [rbp+4E0h+Buf1]; Buf1
0x18005f230  movups  [rbp+4E0h+Buf2], xmm0
0x18005f234  call    memcmp_0
0x18005f239  test    eax, eax
0x18005f23b  jnz     short loc_18005F24E
0x18005f23d  test    rdi, rdi
0x18005f240  jz      short loc_18005F24E
0x18005f242  mov     rax, [rdi+18h]
0x18005f246  movups  xmm0, xmmword ptr [rax]
0x18005f249  movdqu  xmmword ptr [rbp+4E0h+Buf1.Data1], xmm0
0x18005f24e  lea     rax, [rsp+5E0h+pcbData]
0x18005f253  mov     [rsp+5E0h+pcbData], 208h
0x18005f25b  mov     [rsp+5E0h+lpcchClass], rax; pcbData
0x18005f260  lea     rdx, [rbp+4E0h+Name]; lpSubKey
0x18005f267  lea     rax, [rbp+4E0h+pvData]
0x18005f26e  mov     r9d, ebx; dwFlags
0x18005f271  mov     [rsp+5E0h+lpClass], rax; pvData
0x18005f276  xor     r8d, r8d; lpValue
0x18005f279  lea     rax, [rsp+5E0h+pdwType]
0x18005f27e  mov     rcx, r14; hkey
0x18005f281  mov     [rsp+5E0h+phkResult], rax; pdwType
0x18005f286  call    cs:__imp_RegGetValueW
0x18005f28c  test    eax, eax
0x18005f28e  jnz     short loc_18005F2A4
0x18005f290  cmp     [rsp+5E0h+pdwType], 1
0x18005f295  jnz     short loc_18005F2A4
0x18005f297  mov     edx, [rsp+5E0h+pcbData]
0x18005f29b  lea     r8, [rbp+4E0h+pvData]
0x18005f2a2  jmp     short loc_18005F2CF
0x18005f2a4  mov     edx, esi
0x18005f2a6  mov     r8, rsi
0x18005f2a9  mov     [rsp+5E0h+pcbData], edx
0x18005f2ad  test    rdi, rdi
0x18005f2b0  jz      short loc_18005F2CF
0x18005f2b2  mov     r8, [rdi+8]
0x18005f2b6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005f2ba  inc     rdx
0x18005f2bd  cmp     [r8+rdx*2], si
0x18005f2c2  jnz     short loc_18005F2BA
0x18005f2c4  lea     edx, ds:2[rdx*2]
0x18005f2cb  mov     [rsp+5E0h+pcbData], edx
0x18005f2cf  mov     eax, cs:dword_18008DD20
0x18005f2d5  mov     edi, 0Dh
0x18005f2da  movups  xmm0, cs:DEVPKEY_Protocol_ProviderName
0x18005f2e1  mov     [rbp+4E0h+var_510], eax
0x18005f2e4  mov     eax, [rsp+5E0h+cchName]
0x18005f2e8  movaps  [rbp+4E0h+var_520], xmm0
0x18005f2ec  movups  xmm0, cs:DEVPKEY_Protocol_ProtocolId
0x18005f2f3  mov     [rbp+4E0h+var_46C], edx
0x18005f2f6  mov     rdx, r13
0x18005f2f9  lea     eax, ds:2[rax*2]
0x18005f300  mov     [rbp+4E0h+var_468], r8
0x18005f304  mov     [rbp+4E0h+var_4FC], eax
0x18005f307  lea     rax, [rbp+4E0h+Name]
0x18005f30e  mov     [rbp+4E0h+var_4F8], rax
0x18005f312  mov     eax, cs:dword_18008DD50
0x18005f318  mov     [rbp+4E0h+var_4E0], eax
0x18005f31b  lea     rax, [rbp+4E0h+Uuid]
0x18005f31f  mov     [rbp+4E0h+var_4C8], rax
0x18005f323  mov     eax, cs:dword_18008DD38
0x18005f329  mov     [rbp+4E0h+var_4B0], eax
0x18005f32c  lea     rax, [rbp+4E0h+Buf1]
0x18005f330  mov     [rbp+4E0h+var_498], rax
0x18005f334  mov     eax, cs:dword_18008F2C8
0x18005f33a  mov     [rbp+4E0h+var_480], eax
0x18005f33d  mov     rax, r8
0x18005f340  neg     rax
0x18005f343  movaps  [rbp+4E0h+var_4F0], xmm0
0x18005f347  movups  xmm0, cs:DEVPKEY_Protocol_ProviderClassId
0x18005f34e  sbb     ecx, ecx
0x18005f350  mov     [rbp+4E0h+var_50C], esi
0x18005f353  and     ecx, 12h
0x18005f356  mov     [rbp+4E0h+var_508], rsi
0x18005f35a  lea     rax, [rbp+4E0h+Name]
0x18005f361  movaps  [rbp+4E0h+var_4C0], xmm0
0x18005f365  movups  xmm0, cs:DEVPKEY_Protocol_ProviderFriendlyName
0x18005f36c  mov     qword ptr [rsp+5E0h+var_568], rax
0x18005f371  lea     r8, [rsp+5E0h+var_578]
0x18005f376  lea     rax, [rbp+4E0h+var_520]
0x18005f37a  mov     [rbp+4E0h+var_470], ecx
0x18005f37d  mov     [rbp+4E0h+var_558], rax
0x18005f381  xor     ecx, ecx
0x18005f383  mov     rax, [rsp+5E0h+var_580]
0x18005f388  mov     [rbp+4E0h+var_500], 12h
0x18005f38f  mov     [rbp+4E0h+var_4DC], esi
0x18005f392  mov     [rbp+4E0h+var_4D8], rsi
0x18005f396  mov     [rbp+4E0h+var_4D0], edi
0x18005f399  mov     [rbp+4E0h+var_4CC], 10h
0x18005f3a0  mov     [rbp+4E0h+var_4AC], esi
0x18005f3a3  mov     [rbp+4E0h+var_4A8], rsi
0x18005f3a7  mov     [rbp+4E0h+var_4A0], edi
0x18005f3aa  mov     [rbp+4E0h+var_49C], 10h
0x18005f3b1  movaps  [rbp+4E0h+var_490], xmm0
0x18005f3b5  mov     [rbp+4E0h+var_47C], esi
0x18005f3b8  mov     [rbp+4E0h+var_478], rsi
0x18005f3bc  mov     dword ptr [rsp+5E0h+var_578], 1
0x18005f3c4  mov     dword ptr [rsp+5E0h+var_578+8], 0Ch
0x18005f3cc  mov     dword ptr [rbp+4E0h+var_568+8], 4
0x18005f3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3d8  xorps   xmm0, xmm0
0x18005f3db  xor     eax, eax
0x18005f3dd  movups  [rsp+5E0h+var_578], xmm0
0x18005f3e2  mov     [rbp+4E0h+var_558], rax
0x18005f3e6  inc     r12d
0x18005f3e9  movups  [rsp+5E0h+var_568], xmm0
0x18005f3ee  jmp     loc_18005F00F
0x18005f3f3  inc     r15d
0x18005f3f6  jmp     loc_18005EFF2
0x18005f3fb  mov     rcx, [rbp+4E8h]; this
0x18005f402  lea     rdx, aFailedToEnumer; "failed to enumerate provider's key"
  ... truncated ...
```
