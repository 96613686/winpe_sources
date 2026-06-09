# FIconFileFromClass(_GUID const &,ushort *,uint,uint *,bool)

- ea: `0x18009ab88`
- end: `0x18009af03`
- name: `?FIconFileFromClass@@YAHAEBU_GUID@@PEAGIPEAI_N@Z`
- size: `891`
- prototype: `int __fastcall(const _GUID *rclsid, wchar_t *pszEXE, unsigned int cch, unsigned int *lpIndex, bool rclsid)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009af0c`
- `0x18009bf30`

## callees

- `0x18000f358`
- `0x18000fc2c`
- `0x18001a630`
- `0x18002fcd8`
- `0x180033bb0`
- `0x18003a394`
- `0x180046460`
- `0x180049dd4`
- `0x180049edc`
- `0x18009aa88`
- `0x18009ab88`
- `0x18009b984`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ad0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ae16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ad0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ae16`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009ad31`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009ae36`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009aec9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009ad31`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009ae36`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009aec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009aeb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009aeb1`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009acb7`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18009acb7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009ad5c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18009ad5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009acde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ad99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ae54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ae68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009acde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ad99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ae54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ae68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ac3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ac3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ac7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ac7a`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009ac96`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009ac96`

## string_xrefs

- `0x18009acfc`: `Protocol\StdFileEditing\Server`
- `0x18009ad6e`: `CLSID\`

## pseudocode

```c
__int64 __fastcall FIconFileFromClass(const _GUID *rclsid, wchar_t *pszEXE, DWORD cch, unsigned int *lpIndex)
{
  wchar_t *v6; // r12
  wchar_t *v8; // rdi
  WCHAR *v9; // r14
  __int64 v10; // rax
  unsigned int NameAndIndex; // ebx
  ULONG (__stdcall *AddRef)(IUnknown *); // r12
  PCWSTR StringRawBuffer; // rax
  wchar_t *v14; // rsi
  int v15; // ebx
  int v16; // ebx
  DWORD v17; // eax
  unsigned int v18; // r10d
  int v19; // ebx
  DWORD v20; // eax
  DWORD v21; // ebx
  DWORD v23; // eax
  wchar_t *pszClass; // [rsp+30h] [rbp-B1h] BYREF
  HKEY__ *hKey; // [rsp+38h] [rbp-A9h] BYREF
  wchar_t *lpBuffer; // [rsp+40h] [rbp-A1h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > packagedComDefaultIcon; // [rsp+48h] [rbp-99h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+50h] [rbp-91h] BYREF
  wchar_t *v29; // [rsp+58h] [rbp-89h]
  wchar_t szKey[64]; // [rsp+60h] [rbp-81h] BYREF

  v6 = pszEXE;
  v29 = pszEXE;
  v8 = 0;
  v9 = 0;
  lpBuffer = 0;
  oleClassInfo.m_ptr = 0;
  packagedComDefaultIcon.m_ptr = 0;
  hKey = 0;
  v10 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&rclsid->Data1 )
    v10 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v10 )
    goto LABEL_4;
  oleClassInfo.m_ptr = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         rclsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) >= 0 )
  {
    AddRef = oleClassInfo.m_ptr->lpVtbl[1].AddRef;
    packagedComDefaultIcon.m_ptr = 0;
    if ( ((int (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))AddRef)(
           oleClassInfo.m_ptr,
           &packagedComDefaultIcon) < 0 )
    {
      NameAndIndex = 0;
      goto LABEL_27;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(packagedComDefaultIcon.m_ptr, 0);
    v6 = v29;
    v14 = (wchar_t *)StringRawBuffer;
LABEL_21:
    v20 = ExpandEnvironmentStringsW(v14, 0, 0);
    v21 = v20;
    if ( v20 )
    {
      v9 = (WCHAR *)CoTaskMemAlloc(2LL * v20);
      v23 = ExpandEnvironmentStringsW(v14, v9, v21);
      if ( v23 )
      {
        if ( v23 <= v21 )
        {
          NameAndIndex = ExtractNameAndIndex(v21, v9, v6, cch, lpIndex);
          goto $ErrRtn_1;
        }
      }
    }
    goto LABEL_22;
  }
  pszClass = 0;
  if ( !CoIsOle1Class(rclsid) )
  {
    StringFromCLSID(rclsid, &pszClass);
    StringCchCopyW(szKey, 0x40u, L"CLSID\\");
    StringCchCatW(szKey, v18, pszClass);
    CoTaskMemFree(pszClass);
    if ( !OpenClassesRootKeyExW(szKey, 0x2000000u, &hKey) )
    {
      v19 = RegReadDefValue(hKey, Com::Catalog::Constants::DefaultIcon, &lpBuffer);
      if ( v19 )
      {
        v19 = RegReadDefValue(hKey, Com::Catalog::Constants::LocalServer32, &lpBuffer);
        if ( v19 )
          v19 = RegReadDefValue(hKey, L"LocalServer", &lpBuffer);
      }
      RegCloseKey(hKey);
      v8 = lpBuffer;
      if ( !v19 )
      {
        v14 = lpBuffer;
        goto LABEL_21;
      }
LABEL_22:
      NameAndIndex = 0;
      goto $ErrRtn_1;
    }
LABEL_4:
    NameAndIndex = 0;
    goto LABEL_27;
  }
  ProgIDFromCLSID(rclsid, &pszClass);
  v15 = OpenClassesRootKeyExW(pszClass, 0x2000000u, &hKey);
  CoTaskMemFree(pszClass);
  if ( v15 )
    goto LABEL_4;
  v16 = RegReadDefValue(hKey, L"Protocol\\StdFileEditing\\Server", &lpBuffer);
  RegCloseKey(hKey);
  v8 = lpBuffer;
  if ( v16 )
    goto LABEL_22;
  v17 = ExpandEnvironmentStringsW(lpBuffer, v6, cch);
  if ( !v17 || v17 > cch )
    goto LABEL_22;
  *lpIndex = 0;
  NameAndIndex = 1;
$ErrRtn_1:
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v9 )
    CoTaskMemFree(v9);
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&packagedComDefaultIcon);
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
  return NameAndIndex;
}

```

## disassembly

```asm
0x18009ab88  push    rbp
0x18009ab8a  push    rbx
0x18009ab8b  push    rsi
0x18009ab8c  push    rdi
0x18009ab8d  push    r12
0x18009ab8f  push    r13
0x18009ab91  push    r14
0x18009ab93  push    r15
0x18009ab95  lea     rbp, [rsp-17h]
0x18009ab9a  sub     rsp, 0F8h
0x18009aba1  mov     rax, cs:__security_cookie
0x18009aba8  xor     rax, rsp
0x18009abab  mov     [rbp+4Fh+var_50], rax
0x18009abaf  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18009abb6  xor     esi, esi
0x18009abb8  mov     r13, lpIndex
0x18009abbb  mov     r15d, cch
0x18009abbe  mov     r12, pszEXE
0x18009abc1  mov     [rsp+130h+var_D8], pszEXE
0x18009abc6  mov     rbx, rclsid
0x18009abc9  mov     edi, esi
0x18009abcb  mov     r14d, esi
0x18009abce  mov     [rsp+130h+lpBuffer], rsi
0x18009abd3  mov     [rsp+130h+oleClassInfo.m_ptr], rsi
0x18009abd8  mov     [rsp+130h+packagedComDefaultIcon.m_ptr], rsi
0x18009abdd  mov     [rsp+130h+hKey], rsi
0x18009abe2  sub     rax, [rclsid]
0x18009abe5  jnz     short loc_18009ABF2
0x18009abe7  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18009abee  sub     rax, [rclsid+8]
0x18009abf2  test    rax, rax
0x18009abf5  jnz     short loc_18009ABFE
0x18009abf7  mov     ebx, esi
0x18009abf9  jmp     loc_18009AE74
0x18009abfe  lea     lpIndex, [rsp+130h+oleClassInfo]; ppv
0x18009ac03  mov     [rsp+130h+oleClassInfo.m_ptr], rsi
0x18009ac08  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18009ac0f  xor     edx, edx; pComCatalog
0x18009ac11  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18009ac16  test    eax, eax
0x18009ac18  js      short loc_18009AC93
0x18009ac1a  mov     rbx, [rsp+130h+oleClassInfo.m_ptr]
0x18009ac1f  mov     rsi, [rsp+130h+packagedComDefaultIcon.m_ptr]
0x18009ac24  mov     rax, [rbx]
0x18009ac27  mov     r12, [rax+20h]
0x18009ac2b  test    rsi, rsi
0x18009ac2e  jz      short loc_18009AC53
0x18009ac30  lea     rclsid, [rsp+130h+pszClass]; this
0x18009ac35  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18009ac3a  mov     rclsid, rsi; string
0x18009ac3d  call    cs:__imp_WindowsDeleteString
0x18009ac44  nop     dword ptr [rax+rax+00h]
0x18009ac49  lea     rclsid, [rsp+130h+pszClass]; this
0x18009ac4e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18009ac53  and     [rsp+130h+packagedComDefaultIcon.m_ptr], rdi
0x18009ac58  lea     pszEXE, [rsp+130h+packagedComDefaultIcon]
0x18009ac5d  mov     rclsid, rbx
0x18009ac60  mov     rax, r12
0x18009ac63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac68  test    eax, eax
0x18009ac6a  jns     short loc_18009AC73
0x18009ac6c  xor     ebx, ebx
0x18009ac6e  jmp     loc_18009AE74
0x18009ac73  mov     rclsid, [rsp+130h+packagedComDefaultIcon.m_ptr]; string
0x18009ac78  xor     edx, edx; length
0x18009ac7a  call    cs:__imp_WindowsGetStringRawBuffer
0x18009ac81  nop     dword ptr [rax+rax+00h]
0x18009ac86  mov     r12, [rsp+130h+var_D8]
0x18009ac8b  mov     rsi, rax
0x18009ac8e  jmp     loc_18009AE2E
0x18009ac93  mov     rclsid, rbx; rclsid
0x18009ac96  call    cs:__imp_CoIsOle1Class
0x18009ac9d  nop     dword ptr [rax+rax+00h]
0x18009aca2  mov     [rsp+130h+pszClass], rsi
0x18009aca7  lea     pszEXE, [rsp+130h+pszClass]; lplpsz
0x18009acac  mov     rclsid, rbx; rclsid
0x18009acaf  test    eax, eax
0x18009acb1  jz      loc_18009AD5C
0x18009acb7  call    cs:__imp_ProgIDFromCLSID
0x18009acbe  nop     dword ptr [rax+rax+00h]
0x18009acc3  mov     rclsid, [rsp+130h+pszClass]; pszSubKey
0x18009acc8  lea     r8, [rsp+130h+hKey]; phkResult
0x18009accd  mov     edx, 2000000h; samDesired
0x18009acd2  call    OpenClassesRootKeyExW
0x18009acd7  mov     rclsid, [rsp+130h+pszClass]; pv
0x18009acdc  mov     ebx, eax
0x18009acde  call    cs:__imp_CoTaskMemFree
0x18009ace5  nop     dword ptr [rax+rax+00h]
0x18009acea  test    ebx, ebx
0x18009acec  jnz     loc_18009ABF7
0x18009acf2  mov     rclsid, [rsp+130h+hKey]; hKey
0x18009acf7  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x18009acfc  lea     pszEXE, aProtocolStdfil_0; "Protocol\\StdFileEditing\\Server"
0x18009ad03  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x18009ad08  mov     rclsid, [rsp+130h+hKey]; hKey
0x18009ad0d  mov     ebx, eax
0x18009ad0f  call    cs:__imp_RegCloseKey
0x18009ad16  nop     dword ptr [rax+rax+00h]
0x18009ad1b  mov     rdi, [rsp+130h+lpBuffer]
0x18009ad20  test    ebx, ebx
0x18009ad22  jnz     loc_18009AE4A
0x18009ad28  mov     cch, r15d; nSize
0x18009ad2b  mov     pszEXE, r12; lpDst
0x18009ad2e  mov     rclsid, rdi; lpSrc
0x18009ad31  call    cs:__imp_ExpandEnvironmentStringsW
0x18009ad38  nop     dword ptr [rax+rax+00h]
0x18009ad3d  test    eax, eax
0x18009ad3f  jz      loc_18009AE4A
0x18009ad45  cmp     eax, r15d
0x18009ad48  ja      loc_18009AE4A
0x18009ad4e  mov     [r13+0], esi
0x18009ad52  mov     ebx, 1
0x18009ad57  jmp     $ErrRtn_1
0x18009ad5c  call    cs:__imp_StringFromCLSID
0x18009ad63  nop     dword ptr [rax+rax+00h]
0x18009ad68  mov     r10d, 40h ; '@'
0x18009ad6e  lea     r8, aClsid_0; "CLSID\\"
0x18009ad75  mov     edx, r10d; cchDest
0x18009ad78  lea     rclsid, [rsp+130h+szKey]; pszDest
0x18009ad7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009ad82  mov     r8, [rsp+130h+pszClass]; pszSrc
0x18009ad87  lea     rclsid, [rsp+130h+szKey]; pszDest
0x18009ad8c  mov     edx, r10d; cchDest
0x18009ad8f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009ad94  mov     rclsid, [rsp+130h+pszClass]; pv
0x18009ad99  call    cs:__imp_CoTaskMemFree
0x18009ada0  nop     dword ptr [rax+rax+00h]
0x18009ada5  lea     r8, [rsp+130h+hKey]; phkResult
0x18009adaa  mov     edx, 2000000h; samDesired
0x18009adaf  lea     rclsid, [rsp+130h+szKey]; pszSubKey
0x18009adb4  call    OpenClassesRootKeyExW
0x18009adb9  test    eax, eax
0x18009adbb  jnz     loc_18009ABF7
0x18009adc1  mov     rclsid, [rsp+130h+hKey]; hKey
0x18009adc6  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x18009adcb  lea     pszEXE, ?DefaultIcon@Constants@Catalog@Com@@3QBGB; pszKey
0x18009add2  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x18009add7  mov     ebx, eax
0x18009add9  test    eax, eax
0x18009addb  jz      short loc_18009AE11
0x18009addd  mov     rclsid, [rsp+130h+hKey]; hKey
0x18009ade2  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x18009ade7  lea     pszEXE, ?LocalServer32@Constants@Catalog@Com@@3QBGB; pszKey
0x18009adee  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x18009adf3  mov     ebx, eax
0x18009adf5  test    eax, eax
0x18009adf7  jz      short loc_18009AE11
0x18009adf9  mov     rclsid, [rsp+130h+hKey]; hKey
0x18009adfe  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x18009ae03  lea     pszEXE, aLocalserver; "LocalServer"
0x18009ae0a  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x18009ae0f  mov     ebx, eax
0x18009ae11  mov     rclsid, [rsp+130h+hKey]; hKey
0x18009ae16  call    cs:__imp_RegCloseKey
0x18009ae1d  nop     dword ptr [rax+rax+00h]
0x18009ae22  mov     rdi, [rsp+130h+lpBuffer]
0x18009ae27  test    ebx, ebx
0x18009ae29  jnz     short loc_18009AE4A
0x18009ae2b  mov     rsi, rdi
0x18009ae2e  xor     cch, cch; nSize
0x18009ae31  xor     edx, edx; lpDst
0x18009ae33  mov     rclsid, rsi; lpSrc
0x18009ae36  call    cs:__imp_ExpandEnvironmentStringsW
0x18009ae3d  nop     dword ptr [rax+rax+00h]
0x18009ae42  mov     ebx, eax
0x18009ae44  test    eax, eax
0x18009ae46  jnz     short loc_18009AEAB
0x18009ae48  xor     esi, esi
0x18009ae4a  mov     ebx, esi
0x18009ae4c  test    rdi, rdi
0x18009ae4f  jz      short loc_18009AE60
0x18009ae51  mov     rclsid, rdi; pv
0x18009ae54  call    cs:__imp_CoTaskMemFree
0x18009ae5b  nop     dword ptr [rax+rax+00h]
0x18009ae60  test    r14, r14
0x18009ae63  jz      short loc_18009AE74
0x18009ae65  mov     rclsid, r14; pv
0x18009ae68  call    cs:__imp_CoTaskMemFree
0x18009ae6f  nop     dword ptr [rax+rax+00h]
0x18009ae74  lea     rclsid, [rsp+130h+packagedComDefaultIcon]; this
0x18009ae79  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18009ae7e  lea     rclsid, [rsp+130h+oleClassInfo]; this
0x18009ae83  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009ae88  mov     eax, ebx
0x18009ae8a  mov     rclsid, [rbp+4Fh+var_50]
0x18009ae8e  xor     rclsid, rsp; StackCookie
0x18009ae91  call    __security_check_cookie
0x18009ae96  add     rsp, 0F8h
0x18009ae9d  pop     r15
0x18009ae9f  pop     r14
0x18009aea1  pop     r13
0x18009aea3  pop     r12
0x18009aea5  pop     rdi
0x18009aea6  pop     rsi
0x18009aea7  pop     rbx
0x18009aea8  pop     rbp
0x18009aea9  retn
0x18009aeab  mov     rclsid, rbx
0x18009aeae  add     rclsid, rclsid; cb
0x18009aeb1  call    cs:__imp_CoTaskMemAlloc
0x18009aeb8  nop     dword ptr [rax+rax+00h]
0x18009aebd  mov     cch, ebx; nSize
0x18009aec0  mov     rclsid, rsi; lpSrc
0x18009aec3  mov     pszEXE, rax; lpDst
0x18009aec6  mov     r14, rax
0x18009aec9  call    cs:__imp_ExpandEnvironmentStringsW
0x18009aed0  nop     dword ptr [rax+rax+00h]
0x18009aed5  xor     esi, esi
0x18009aed7  test    eax, eax
0x18009aed9  jz      loc_18009AE4A
0x18009aedf  cmp     eax, ebx
0x18009aee1  ja      loc_18009AE4A
0x18009aee7  mov     r9d, r15d; cchEXE
0x18009aeea  mov     [rsp+130h+pIndex], r13; pIndex
0x18009aeef  mov     r8, r12; pszEXE
0x18009aef2  mov     pszEXE, r14; pszInfo
0x18009aef5  mov     ecx, ebx; dw
0x18009aef7  call    ?ExtractNameAndIndex@@YAHKPEAG0IPEAI@Z; ExtractNameAndIndex(ulong,ushort *,ushort *,uint,uint *)
0x18009aefc  mov     ebx, eax
0x18009aefe  jmp     $ErrRtn_1
```
