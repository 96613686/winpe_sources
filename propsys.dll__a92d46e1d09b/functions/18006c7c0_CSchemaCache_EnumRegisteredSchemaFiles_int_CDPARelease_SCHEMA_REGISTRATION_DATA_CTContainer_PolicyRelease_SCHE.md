# CSchemaCache::_EnumRegisteredSchemaFiles(int,CDPARelease<SCHEMA_REGISTRATION_DATA,CTContainer_PolicyRelease<SCHEMA_REGISTRATION_DATA>> *,int *)

- ea: `0x18006c7c0`
- end: `0x18006cbd8`
- name: `?_EnumRegisteredSchemaFiles@CSchemaCache@@AEAAXHPEAV?$CDPARelease@USCHEMA_REGISTRATION_DATA@@V?$CTContainer_PolicyRelease@USCHEMA_REGISTRATION_DATA@@@@@@PEAH@Z`
- size: `1048`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003898`

## callees

- `0x180003434`
- `0x180003b48`
- `0x180003f94`
- `0x180004148`
- `0x18000457c`
- `0x18002f9e0`
- `0x1800423a0`
- `0x1800425c0`
- `0x18006114c`
- `0x180064148`
- `0x180065c04`
- `0x18006c7c0`
- `0x18006e0b8`
- `0x18006ed20`
- `0x18008f504`
- `0x18008f748`
- `0x18008f928`
- `0x18008fd94`
- `0x180091650`
- `0x180092bb0`
- `0x180092f8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c845`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c8f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ca05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c845`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006c8f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006ca05`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006c8a7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006cb63`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006c8a7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18006cb63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cb80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006cb80`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18006c9b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18006c9b0`

## string_xrefs

- `0x18006c914`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x18006c95a`: `onecoreuap\shell\propsys\schemacache.cpp`
- `0x18006ca54`: `onecoreuap\shell\propsys\schemacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSchemaCache::_EnumRegisteredSchemaFiles(CSchemaCache *a1, int a2, HDPA *a3, BOOL *a4)
{
  int v4; // r14d
  LSTATUS v5; // eax
  signed int v6; // edi
  int v7; // r12d
  DWORD v8; // r13d
  unsigned int v9; // r15d
  LSTATUS v10; // eax
  struct IMigrationContext *v11; // rdx
  int v12; // eax
  const WCHAR *v13; // rbx
  BOOL v14; // esi
  const unsigned __int16 *FileNameW; // rax
  LSTATUS v16; // eax
  signed int v17; // esi
  struct CSchemaData **v18; // r14
  BOOL v19; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  void *pFind; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszPath; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h]
  HDPA *v24; // [rsp+58h] [rbp-A8h]
  CSchemaCache *v25; // [rsp+60h] [rbp-A0h]
  BOOL *v26; // [rsp+68h] [rbp-98h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v28; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  HKEY v30; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[336]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  v26 = a4;
  v24 = a3;
  v4 = a2;
  v23 = a2;
  v25 = a1;
  *a4 = 1;
  hKey = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\PropertySystem\\PropertySchema",
         0,
         a2 != 0 ? 264 : 520,
         &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::SchemaCache_EnumRegisteredSchemaFiles((PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles *)v31);
    v7 = 0;
    LODWORD(pFind) = 0;
    cchName = 260;
    v8 = 0;
    LODWORD(v28) = 0;
    if ( !RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0) )
    {
      v9 = v4 != 0 ? 0xFFFFFF00 : 0;
      do
      {
        v28 = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &v28,
          0);
        v10 = RegOpenKeyExW(hKey, Name, 0, v9 + 513, &v28);
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        if ( v6 >= 0 )
        {
          pszPath = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pszPath,
            0);
          v12 = GetAndExpandRegisteredPath(v28, v11, (unsigned __int16 **)&pszPath);
          v6 = v12;
          if ( v12 >= 0 )
          {
            v13 = pszPath;
            v30 = (HKEY)pszPath;
            PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::SchemaPath<unsigned short *>(v31, &v30);
            v14 = 1;
            pFind = 0;
            v6 = SCHEMA_REGISTRATION_DATA::Load(v28, (struct SCHEMA_REGISTRATION_DATA **)&pFind);
            if ( v6 >= 0
              || (FileNameW = PathFindFileNameW(v13),
                  v6 = SCHEMA_REGISTRATION_DATA::Generate(FileNameW, (struct SCHEMA_REGISTRATION_DATA **)&pFind),
                  v6 < 0) )
            {
              v18 = (struct CSchemaData **)pFind;
            }
            else
            {
              v30 = 0;
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &v30,
                0);
              v16 = RegOpenKeyExW(v28, 0, 0, v4 != 0 ? 258 : 514, &v30);
              v17 = v16;
              if ( v16 > 0 )
                v17 = (unsigned __int16)v16 | 0x80070000;
              v18 = (struct CSchemaData **)pFind;
              if ( v17 >= 0 )
                v17 = SCHEMA_REGISTRATION_DATA::Write((SCHEMA_REGISTRATION_DATA *)pFind, v30);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
              v14 = v17 >= 0;
            }
            if ( v6 >= 0 )
            {
              if ( DPA_Search(*v24, v18, 0, CompareSchemaRegistrations, 0, 0) == -1 )
              {
                Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v18 + 20);
                v6 = CSchemaCache::_LoadOrBuildCachedSchema(
                       v25,
                       (const struct SCHEMA_REGISTRATION_DATA *)v18,
                       v13,
                       v14,
                       v18 + 20);
                if ( v6 >= 0 )
                {
                  if ( DPA_InsertPtr(*v24, 0x7FFFFFFF, v18) == -1 )
                  {
                    v6 = -2147024882;
                  }
                  else
                  {
                    v6 = 0;
                    pFind = 0;
                    ++v7;
                  }
                }
              }
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xD1,
                (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
                (const char *)(unsigned int)v6,
                phkResult);
            }
            wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>::~unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>(&pFind);
            v19 = *v26 && v14;
            *v26 = v19;
            v4 = v23;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xB3,
              (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
              (const char *)(unsigned int)v12,
              phkResult);
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPath);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xAE,
            (unsigned int)"onecoreuap\\shell\\propsys\\schemacache.cpp",
            (const char *)(unsigned int)v6,
            phkResult);
        }
        cchName = 260;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v28);
        ++v8;
      }
      while ( !RegEnumKeyExW(hKey, v8, Name, &cchName, 0, 0, 0, 0) );
      LODWORD(pFind) = v7;
      LODWORD(v28) = v8;
    }
    RegCloseKey(hKey);
    PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::EnumeratedSchemas<unsigned int &,unsigned int &>(
      v31,
      &pFind,
      &v28);
    wil::ActivityBase<PropsysTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v31,
      (unsigned int)v6);
    PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::~SchemaCache_EnumRegisteredSchemaFiles((PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles *)v31);
  }
}

```

## disassembly

```asm
0x18006c7c0  mov     [rsp-8+arg_8], rbx
0x18006c7c5  push    rbp
0x18006c7c6  push    rsi
0x18006c7c7  push    rdi
0x18006c7c8  push    r12
0x18006c7ca  push    r13
0x18006c7cc  push    r14
0x18006c7ce  push    r15
0x18006c7d0  lea     rbp, [rsp-300h]
0x18006c7d8  sub     rsp, 400h
0x18006c7df  mov     rax, cs:__security_cookie
0x18006c7e6  xor     rax, rsp
0x18006c7e9  mov     [rbp+330h+var_40], rax
0x18006c7f0  mov     [rsp+430h+var_3C8], r9
0x18006c7f5  mov     [rsp+430h+var_3D8], r8
0x18006c7fa  mov     r14d, edx
0x18006c7fd  mov     [rsp+430h+var_3E0], edx
0x18006c801  mov     [rsp+430h+var_3D0], rcx
0x18006c806  mov     dword ptr [r9], 1
0x18006c80d  xor     ebx, ebx
0x18006c80f  mov     [rsp+430h+hKey], rbx
0x18006c814  mov     eax, edx
0x18006c816  neg     eax
0x18006c818  sbb     r9d, r9d
0x18006c81b  mov     esi, 0FFFFFF00h
0x18006c820  and     r9d, esi
0x18006c823  add     r9d, 208h; samDesired
0x18006c82a  lea     rax, [rsp+430h+hKey]
0x18006c82f  mov     [rsp+430h+phkResult], rax; phkResult
0x18006c834  xor     r8d, r8d; ulOptions
0x18006c837  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006c83e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006c845  call    cs:__imp_RegOpenKeyExW
0x18006c84b  mov     edi, eax
0x18006c84d  test    eax, eax
0x18006c84f  jle     short loc_18006C85A
0x18006c851  movzx   edi, ax
0x18006c854  or      edi, 80070000h
0x18006c85a  test    edi, edi
0x18006c85c  js      loc_18006CBAE
0x18006c862  lea     rcx, [rbp+330h+var_3A0]; this
0x18006c866  call    ??$?0$$V@SchemaCache_EnumRegisteredSchemaFiles@PropsysTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::SchemaCache_EnumRegisteredSchemaFiles(wistd::integral_constant<char,0>)
0x18006c86b  nop
0x18006c86c  mov     r12d, ebx
0x18006c86f  mov     dword ptr [rsp+430h+pFind], ebx
0x18006c873  mov     [rbp+330h+cchName], 104h
0x18006c87a  mov     r13d, ebx
0x18006c87d  mov     dword ptr [rsp+430h+var_3B8], ebx
0x18006c881  mov     [rsp+430h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18006c886  mov     [rsp+430h+lpcchClass], rbx; lpcchClass
0x18006c88b  mov     [rsp+430h+lpClass], rbx; lpClass
0x18006c890  mov     [rsp+430h+phkResult], rbx; lpReserved
0x18006c895  lea     r9, [rbp+330h+cchName]; lpcchName
0x18006c899  lea     r8, [rbp+330h+Name]; lpName
0x18006c8a0  xor     edx, edx; dwIndex
0x18006c8a2  mov     rcx, [rsp+430h+hKey]; hKey
0x18006c8a7  call    cs:__imp_RegEnumKeyExW
0x18006c8ad  test    eax, eax
0x18006c8af  jnz     loc_18006CB7B
0x18006c8b5  mov     eax, r14d
0x18006c8b8  neg     eax
0x18006c8ba  sbb     r15d, r15d
0x18006c8bd  and     r15d, esi
0x18006c8c0  mov     [rsp+430h+var_3B8], rbx
0x18006c8c5  xor     edx, edx
0x18006c8c7  lea     rcx, [rsp+430h+var_3B8]
0x18006c8cc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006c8d1  lea     rax, [rsp+430h+var_3B8]
0x18006c8d6  mov     [rsp+430h+phkResult], rax; int
0x18006c8db  lea     r9d, [r15+201h]; samDesired
0x18006c8e2  xor     r8d, r8d; ulOptions
0x18006c8e5  lea     rdx, [rbp+330h+Name]; lpSubKey
0x18006c8ec  mov     rcx, [rsp+430h+hKey]; hKey
0x18006c8f1  call    cs:__imp_RegOpenKeyExW
0x18006c8f7  mov     edi, eax
0x18006c8f9  test    eax, eax
0x18006c8fb  jle     short loc_18006C906
0x18006c8fd  movzx   edi, ax
0x18006c900  or      edi, 80070000h
0x18006c906  mov     rcx, [rbp+338h]; this
0x18006c90d  test    edi, edi
0x18006c90f  jns     short loc_18006C92A
0x18006c911  mov     r9d, edi; char *
0x18006c914  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x18006c91b  mov     edx, 0AEh; void *
0x18006c920  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c925  jmp     loc_18006CB28
0x18006c92a  mov     [rsp+430h+pszPath], rbx
0x18006c92f  xor     edx, edx
0x18006c931  lea     rcx, [rsp+430h+pszPath]
0x18006c936  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006c93b  lea     r8, [rsp+430h+pszPath]; unsigned __int16 **
0x18006c940  mov     rcx, [rsp+430h+var_3B8]; HKEY
0x18006c945  call    ?GetAndExpandRegisteredPath@@YAJPEAUHKEY__@@PEAUIMigrationContext@@PEAPEAG@Z; GetAndExpandRegisteredPath(HKEY__ *,IMigrationContext *,ushort * *)
0x18006c94a  mov     edi, eax
0x18006c94c  mov     rcx, [rbp+338h]; this
0x18006c953  test    eax, eax
0x18006c955  jns     short loc_18006C970
0x18006c957  mov     r9d, eax; char *
0x18006c95a  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x18006c961  mov     edx, 0B3h; void *
0x18006c966  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c96b  jmp     loc_18006CB1E
0x18006c970  mov     rbx, [rsp+430h+pszPath]
0x18006c975  mov     [rbp+330h+var_3A8], rbx
0x18006c979  lea     rdx, [rbp+330h+var_3A8]
0x18006c97d  lea     rcx, [rbp+330h+var_3A0]
0x18006c981  call    ??$SchemaPath@PEAG@SchemaCache_EnumRegisteredSchemaFiles@PropsysTelemetry@@QEAAX$$QEAPEAG@Z; PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::SchemaPath<ushort *>(ushort * &&)
0x18006c986  mov     esi, 1
0x18006c98b  mov     [rsp+430h+pFind], 0
0x18006c994  lea     rdx, [rsp+430h+pFind]; struct SCHEMA_REGISTRATION_DATA **
0x18006c999  mov     rcx, [rsp+430h+var_3B8]; HKEY
0x18006c99e  call    ?Load@SCHEMA_REGISTRATION_DATA@@SAJPEAUHKEY__@@PEAPEAU1@@Z; SCHEMA_REGISTRATION_DATA::Load(HKEY__ *,SCHEMA_REGISTRATION_DATA * *)
0x18006c9a3  mov     edi, eax
0x18006c9a5  test    eax, eax
0x18006c9a7  jns     loc_18006CA41
0x18006c9ad  mov     rcx, rbx; pszPath
0x18006c9b0  call    cs:__imp_PathFindFileNameW
0x18006c9b6  lea     rdx, [rsp+430h+pFind]; struct SCHEMA_REGISTRATION_DATA **
0x18006c9bb  mov     rcx, rax; unsigned __int16 *
0x18006c9be  call    ?Generate@SCHEMA_REGISTRATION_DATA@@SAJPEBGPEAPEAU1@@Z; SCHEMA_REGISTRATION_DATA::Generate(ushort const *,SCHEMA_REGISTRATION_DATA * *)
0x18006c9c3  mov     edi, eax
0x18006c9c5  test    eax, eax
0x18006c9c7  js      short loc_18006CA41
0x18006c9c9  mov     [rbp+330h+var_3A8], 0
0x18006c9d1  xor     edx, edx
0x18006c9d3  lea     rcx, [rbp+330h+var_3A8]
0x18006c9d7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006c9dc  mov     eax, r14d
0x18006c9df  neg     eax
0x18006c9e1  sbb     r9d, r9d
0x18006c9e4  and     r9d, 0FFFFFF00h
0x18006c9eb  add     r9d, 202h; samDesired
0x18006c9f2  lea     rax, [rbp+330h+var_3A8]
0x18006c9f6  mov     [rsp+430h+phkResult], rax; phkResult
0x18006c9fb  xor     r8d, r8d; ulOptions
0x18006c9fe  xor     edx, edx; lpSubKey
0x18006ca00  mov     rcx, [rsp+430h+var_3B8]; hKey
0x18006ca05  call    cs:__imp_RegOpenKeyExW
0x18006ca0b  mov     esi, eax
0x18006ca0d  test    eax, eax
0x18006ca0f  jle     short loc_18006CA1A
0x18006ca11  movzx   esi, ax
0x18006ca14  or      esi, 80070000h
0x18006ca1a  mov     r14, [rsp+430h+pFind]
0x18006ca1f  test    esi, esi
0x18006ca21  js      short loc_18006CA31
0x18006ca23  mov     rdx, [rbp+330h+var_3A8]; HKEY
0x18006ca27  mov     rcx, r14; this
0x18006ca2a  call    ?Write@SCHEMA_REGISTRATION_DATA@@QEBAJPEAUHKEY__@@@Z; SCHEMA_REGISTRATION_DATA::Write(HKEY__ *)
0x18006ca2f  mov     esi, eax
0x18006ca31  lea     rcx, [rbp+330h+var_3A8]
0x18006ca35  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006ca3a  not     esi
0x18006ca3c  shr     esi, 1Fh
0x18006ca3f  jmp     short loc_18006CA46
0x18006ca41  mov     r14, [rsp+430h+pFind]
0x18006ca46  mov     rcx, [rbp+338h]; this
0x18006ca4d  test    edi, edi
0x18006ca4f  jns     short loc_18006CA6A
0x18006ca51  mov     r9d, edi; char *
0x18006ca54  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\propsys\\schemacache"...
0x18006ca5b  mov     edx, 0D1h; void *
0x18006ca60  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ca65  jmp     loc_18006CAF4
0x18006ca6a  mov     dword ptr [rsp+430h+lpClass], 0; options
0x18006ca72  mov     [rsp+430h+phkResult], 0; lParam
0x18006ca7b  lea     r9, ?CompareSchemaRegistrations@@YAHPEBUSCHEMA_REGISTRATION_DATA@@0PEAX@Z; pfnCompare
0x18006ca82  xor     r8d, r8d; iStart
0x18006ca85  mov     rdx, r14; pFind
0x18006ca88  mov     rax, [rsp+430h+var_3D8]
0x18006ca8d  mov     rcx, [rax]; hdpa
0x18006ca90  call    cs:__imp_DPA_Search
0x18006ca96  cmp     eax, 0FFFFFFFFh
0x18006ca99  jnz     short loc_18006CAF4
0x18006ca9b  lea     rdi, [r14+0A0h]
0x18006caa2  mov     rcx, rdi
0x18006caa5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18006caaa  mov     [rsp+430h+phkResult], rdi; struct CSchemaData **
0x18006caaf  mov     r9d, esi; int
0x18006cab2  mov     r8, rbx; unsigned __int16 *
0x18006cab5  mov     rdx, r14; struct SCHEMA_REGISTRATION_DATA *
0x18006cab8  mov     rcx, [rsp+430h+var_3D0]; this
0x18006cabd  call    ?_LoadOrBuildCachedSchema@CSchemaCache@@AEAAJPEBUSCHEMA_REGISTRATION_DATA@@PEBGHPEAPEAVCSchemaData@@@Z; CSchemaCache::_LoadOrBuildCachedSchema(SCHEMA_REGISTRATION_DATA const *,ushort const *,int,CSchemaData * *)
0x18006cac2  mov     edi, eax
0x18006cac4  test    eax, eax
0x18006cac6  js      short loc_18006CAF4
0x18006cac8  mov     r8, r14; p
0x18006cacb  mov     edx, 7FFFFFFFh; i
0x18006cad0  mov     rax, [rsp+430h+var_3D8]
0x18006cad5  mov     rcx, [rax]; hdpa
0x18006cad8  call    cs:__imp_DPA_InsertPtr
0x18006cade  cmp     eax, 0FFFFFFFFh
0x18006cae1  jz      short loc_18006CAEF
0x18006cae3  xor     edi, edi
0x18006cae5  mov     [rsp+430h+pFind], rdi
0x18006caea  inc     r12d
0x18006caed  jmp     short loc_18006CAF4
0x18006caef  mov     edi, 8007000Eh
0x18006caf4  lea     rcx, [rsp+430h+pFind]
0x18006caf9  call    ??1?$unique_ptr@USCHEMA_REGISTRATION_DATA@@U?$default_delete@USCHEMA_REGISTRATION_DATA@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>::~unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>(void)
0x18006cafe  mov     rbx, [rsp+430h+var_3C8]
0x18006cb03  cmp     dword ptr [rbx], 0
0x18006cb06  jz      short loc_18006CB13
0x18006cb08  test    esi, esi
0x18006cb0a  jz      short loc_18006CB13
0x18006cb0c  mov     eax, 1
0x18006cb11  jmp     short loc_18006CB15
0x18006cb13  xor     eax, eax
0x18006cb15  mov     [rbx], eax
0x18006cb17  mov     r14d, [rsp+430h+var_3E0]
0x18006cb1c  xor     ebx, ebx
0x18006cb1e  lea     rcx, [rsp+430h+pszPath]
0x18006cb23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006cb28  mov     [rbp+330h+cchName], 104h
0x18006cb2f  lea     rcx, [rsp+430h+var_3B8]
0x18006cb34  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006cb39  inc     r13d
0x18006cb3c  mov     [rsp+430h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18006cb41  mov     [rsp+430h+lpcchClass], rbx; lpcchClass
0x18006cb46  mov     [rsp+430h+lpClass], rbx; lpClass
0x18006cb4b  mov     [rsp+430h+phkResult], rbx; lpReserved
0x18006cb50  lea     r9, [rbp+330h+cchName]; lpcchName
0x18006cb54  lea     r8, [rbp+330h+Name]; lpName
0x18006cb5b  mov     edx, r13d; dwIndex
0x18006cb5e  mov     rcx, [rsp+430h+hKey]; hKey
0x18006cb63  call    cs:__imp_RegEnumKeyExW
0x18006cb69  test    eax, eax
0x18006cb6b  jz      loc_18006C8C0
0x18006cb71  mov     dword ptr [rsp+430h+pFind], r12d
0x18006cb76  mov     dword ptr [rsp+430h+var_3B8], r13d
0x18006cb7b  mov     rcx, [rsp+430h+hKey]; hKey
0x18006cb80  call    cs:__imp_RegCloseKey
0x18006cb86  lea     r8, [rsp+430h+var_3B8]
0x18006cb8b  lea     rdx, [rsp+430h+pFind]
0x18006cb90  lea     rcx, [rbp+330h+var_3A0]
0x18006cb94  call    ??$EnumeratedSchemas@AEAIAEAI@SchemaCache_EnumRegisteredSchemaFiles@PropsysTelemetry@@QEAAXAEAI0@Z; PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::EnumeratedSchemas<uint &,uint &>(uint &,uint &)
0x18006cb99  mov     edx, edi
0x18006cb9b  lea     rcx, [rbp+330h+var_3A0]
0x18006cb9f  call    ?Stop@?$ActivityBase@VPropsysTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PropsysTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006cba4  nop
0x18006cba5  lea     rcx, [rbp+330h+var_3A0]; this
0x18006cba9  call    ??1SchemaCache_EnumRegisteredSchemaFiles@PropsysTelemetry@@QEAA@XZ; PropsysTelemetry::SchemaCache_EnumRegisteredSchemaFiles::~SchemaCache_EnumRegisteredSchemaFiles(void)
0x18006cbae  mov     rcx, [rbp+330h+var_40]
0x18006cbb5  xor     rcx, rsp; StackCookie
0x18006cbb8  call    __security_check_cookie
0x18006cbbd  mov     rbx, [rsp+430h+arg_8]
0x18006cbc5  add     rsp, 400h
0x18006cbcc  pop     r15
0x18006cbce  pop     r14
0x18006cbd0  pop     r13
0x18006cbd2  pop     r12
0x18006cbd4  pop     rdi
0x18006cbd5  pop     rsi
0x18006cbd6  pop     rbp
0x18006cbd7  retn
```
