# FIconFileFromClass(_GUID const &,ushort *,uint,uint *,bool)

- ea: `0x180099274`
- end: `0x18009957e`
- name: `?FIconFileFromClass@@YAHAEBU_GUID@@PEAGIPEAI_N@Z`
- size: `778`
- prototype: `int __fastcall(const _GUID *rclsid, wchar_t *pszEXE, unsigned int cch, unsigned int *lpIndex, bool rclsid)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180099584`
- `0x180099e50`

## callees

- `0x18001248c`
- `0x18001a3c8`
- `0x18001b0e4`
- `0x18001b810`
- `0x180036488`
- `0x180052390`
- `0x180055f30`
- `0x1800560c4`
- `0x180099194`
- `0x180099274`
- `0x180099a20`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800993d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800994c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800993d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800994c0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800993ed`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800994da`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800994fd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800993ed`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800994da`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800994fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800994eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800994eb`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180099389`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180099389`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180099412`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180099412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800993aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009952e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009953c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800993aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180099449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009952e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009953c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009954c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180099321`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009954c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099358`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009936e`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18009936e`

## string_xrefs

- `0x1800993be`: `Protocol\StdFileEditing\Server`
- `0x18009941e`: `CLSID\`

## pseudocode

```c
__int64 __fastcall FIconFileFromClass(const _GUID *rclsid, wchar_t *pszEXE, DWORD cch, unsigned int *lpIndex)
{
  wchar_t *v4; // rdi
  WCHAR *v7; // r12
  __int64 v9; // rax
  unsigned int NameAndIndex; // ebx
  void *v11; // rsi
  ULONG (__stdcall *AddRef)(IUnknown *); // r12
  PCWSTR StringRawBuffer; // rax
  wchar_t *v14; // r14
  int v15; // ebx
  int v16; // ebx
  DWORD v17; // eax
  unsigned int v18; // r10d
  int v19; // ebx
  DWORD v20; // eax
  DWORD v21; // ebx
  DWORD v22; // eax
  wchar_t *pszClass; // [rsp+30h] [rbp-B1h] BYREF
  HKEY__ *hKey; // [rsp+38h] [rbp-A9h] BYREF
  wchar_t *lpBuffer; // [rsp+40h] [rbp-A1h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > packagedComDefaultIcon; // [rsp+48h] [rbp-99h] BYREF
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+50h] [rbp-91h] BYREF
  wchar_t *v29; // [rsp+58h] [rbp-89h]
  wchar_t szKey[64]; // [rsp+60h] [rbp-81h] BYREF

  v4 = 0;
  v7 = pszEXE;
  v29 = pszEXE;
  lpBuffer = 0;
  oleClassInfo.m_ptr = 0;
  packagedComDefaultIcon.m_ptr = 0;
  hKey = 0;
  v9 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)&rclsid->Data1 )
    v9 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v9 )
  {
    NameAndIndex = 0;
    goto LABEL_32;
  }
  v11 = 0;
  if ( GetClassInfoWithInprocOrLocalServer(
         rclsid,
         0,
         &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
         (void **)&oleClassInfo.m_ptr) < 0 )
  {
    pszClass = 0;
    if ( CoIsOle1Class(rclsid) )
    {
      ProgIDFromCLSID(rclsid, &pszClass);
      v15 = OpenClassesRootKeyExW(pszClass, 0x2000000u, &hKey);
      CoTaskMemFree(pszClass);
      if ( v15 )
        goto LABEL_7;
      v16 = RegReadDefValue(hKey, L"Protocol\\StdFileEditing\\Server", &lpBuffer);
      RegCloseKey(hKey);
      v4 = lpBuffer;
      if ( !v16 )
      {
        v17 = ExpandEnvironmentStringsW(lpBuffer, v7, cch);
        if ( v17 )
        {
          if ( v17 <= cch )
          {
            *lpIndex = 0;
            NameAndIndex = 1;
$ErrRtn_1:
            if ( v4 )
              CoTaskMemFree(v4);
            if ( v11 )
              CoTaskMemFree(v11);
            goto LABEL_30;
          }
        }
      }
LABEL_25:
      NameAndIndex = 0;
      goto $ErrRtn_1;
    }
    StringFromCLSID(rclsid, &pszClass);
    StringCchCopyW(szKey, 0x40u, L"CLSID\\");
    StringCchCatW(szKey, v18, pszClass);
    CoTaskMemFree(pszClass);
    if ( OpenClassesRootKeyExW(szKey, 0x2000000u, &hKey) )
      goto LABEL_7;
    v19 = RegReadDefValue(hKey, Com::Catalog::Constants::DefaultIcon, &lpBuffer);
    if ( v19 )
    {
      v19 = RegReadDefValue(hKey, Com::Catalog::Constants::LocalServer32, &lpBuffer);
      if ( v19 )
        v19 = RegReadDefValue(hKey, L"LocalServer", &lpBuffer);
    }
    RegCloseKey(hKey);
    v4 = lpBuffer;
    if ( v19 )
      goto LABEL_25;
    v14 = lpBuffer;
LABEL_21:
    v20 = ExpandEnvironmentStringsW(v14, 0, 0);
    v21 = v20;
    if ( v20 )
    {
      v11 = CoTaskMemAlloc(2LL * v20);
      v22 = ExpandEnvironmentStringsW(v14, (LPWSTR)v11, v21);
      if ( v22 )
      {
        if ( v22 <= v21 )
        {
          NameAndIndex = ExtractNameAndIndex(v21, (wchar_t *)v11, v7, cch, lpIndex);
          goto $ErrRtn_1;
        }
      }
    }
    goto LABEL_25;
  }
  AddRef = oleClassInfo.m_ptr->lpVtbl[1].AddRef;
  packagedComDefaultIcon.m_ptr = 0;
  if ( ((int (__fastcall *)(IOleClassInfo *, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > *))AddRef)(
         oleClassInfo.m_ptr,
         &packagedComDefaultIcon) >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(packagedComDefaultIcon.m_ptr, 0);
    v7 = v29;
    v14 = (wchar_t *)StringRawBuffer;
    goto LABEL_21;
  }
LABEL_7:
  NameAndIndex = 0;
LABEL_30:
  if ( packagedComDefaultIcon.m_ptr )
    WindowsDeleteString(packagedComDefaultIcon.m_ptr);
LABEL_32:
  wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
  return NameAndIndex;
}

```

## disassembly

```asm
0x180099274  push    rbp
0x180099276  push    rbx
0x180099277  push    rsi
0x180099278  push    rdi
0x180099279  push    r12
0x18009927b  push    r13
0x18009927d  push    r14
0x18009927f  push    r15
0x180099281  lea     rbp, [rsp-17h]
0x180099286  sub     rsp, 0F8h
0x18009928d  mov     rax, cs:__security_cookie
0x180099294  xor     rax, rsp
0x180099297  mov     [rbp+4Fh+var_50], rax
0x18009929b  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1800992a2  xor     edi, edi
0x1800992a4  mov     r13, lpIndex
0x1800992a7  mov     r15d, cch
0x1800992aa  mov     r12, pszEXE
0x1800992ad  mov     [rsp+130h+var_D8], pszEXE
0x1800992b2  mov     rbx, rclsid
0x1800992b5  mov     [rsp+130h+lpBuffer], rdi
0x1800992ba  mov     [rsp+130h+oleClassInfo.m_ptr], rdi
0x1800992bf  mov     [rsp+130h+packagedComDefaultIcon.m_ptr], rdi
0x1800992c4  mov     [rsp+130h+hKey], rdi
0x1800992c9  sub     rax, [rclsid]
0x1800992cc  jnz     short loc_1800992D9
0x1800992ce  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1800992d5  sub     rax, [rclsid+8]
0x1800992d9  test    rax, rax
0x1800992dc  jnz     short loc_1800992E5
0x1800992de  xor     ebx, ebx
0x1800992e0  jmp     loc_180099552
0x1800992e5  lea     lpIndex, [rsp+130h+oleClassInfo]; ppv
0x1800992ea  xor     edx, edx; pComCatalog
0x1800992ec  lea     r8, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x1800992f3  xor     esi, esi
0x1800992f5  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x1800992fa  test    eax, eax
0x1800992fc  js      short loc_18009936B
0x1800992fe  mov     r14, [rsp+130h+oleClassInfo.m_ptr]
0x180099303  mov     rbx, [rsp+130h+packagedComDefaultIcon.m_ptr]
0x180099308  mov     rax, [r14]
0x18009930b  mov     r12, [rax+20h]
0x18009930f  test    rbx, rbx
0x180099312  jz      short loc_180099331
0x180099314  lea     rclsid, [rsp+130h+pszClass]; this
0x180099319  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18009931e  mov     rclsid, rbx; string
0x180099321  call    cs:__imp_WindowsDeleteString
0x180099327  lea     rclsid, [rsp+130h+pszClass]; this
0x18009932c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180099331  lea     pszEXE, [rsp+130h+packagedComDefaultIcon]
0x180099336  mov     [rsp+130h+packagedComDefaultIcon.m_ptr], rsi
0x18009933b  mov     rclsid, r14
0x18009933e  mov     rax, r12
0x180099341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099346  test    eax, eax
0x180099348  jns     short loc_180099351
0x18009934a  xor     ebx, ebx
0x18009934c  jmp     loc_180099542
0x180099351  mov     rclsid, [rsp+130h+packagedComDefaultIcon.m_ptr]; string
0x180099356  xor     edx, edx; length
0x180099358  call    cs:__imp_WindowsGetStringRawBuffer
0x18009935e  mov     r12, [rsp+130h+var_D8]
0x180099363  mov     r14, rax
0x180099366  jmp     loc_1800994D2
0x18009936b  mov     rclsid, rbx; rclsid
0x18009936e  call    cs:__imp_CoIsOle1Class
0x180099374  mov     [rsp+130h+pszClass], rsi
0x180099379  lea     pszEXE, [rsp+130h+pszClass]; lplpsz
0x18009937e  mov     rclsid, rbx; rclsid
0x180099381  test    eax, eax
0x180099383  jz      loc_180099412
0x180099389  call    cs:__imp_ProgIDFromCLSID
0x18009938f  mov     rclsid, [rsp+130h+pszClass]; pszSubKey
0x180099394  lea     r8, [rsp+130h+hKey]; phkResult
0x180099399  mov     edx, 2000000h; samDesired
0x18009939e  call    OpenClassesRootKeyExW
0x1800993a3  mov     rclsid, [rsp+130h+pszClass]; pv
0x1800993a8  mov     ebx, eax
0x1800993aa  call    cs:__imp_CoTaskMemFree
0x1800993b0  test    ebx, ebx
0x1800993b2  jnz     short loc_18009934A
0x1800993b4  mov     rclsid, [rsp+130h+hKey]; hKey
0x1800993b9  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x1800993be  lea     pszEXE, aProtocolStdfil_0; "Protocol\\StdFileEditing\\Server"
0x1800993c5  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x1800993ca  mov     rclsid, [rsp+130h+hKey]; hKey
0x1800993cf  mov     ebx, eax
0x1800993d1  call    cs:__imp_RegCloseKey
0x1800993d7  mov     rdi, [rsp+130h+lpBuffer]
0x1800993dc  test    ebx, ebx
0x1800993de  jnz     loc_180099524
0x1800993e4  mov     cch, r15d; nSize
0x1800993e7  mov     pszEXE, r12; lpDst
0x1800993ea  mov     rclsid, rdi; lpSrc
0x1800993ed  call    cs:__imp_ExpandEnvironmentStringsW
0x1800993f3  test    eax, eax
0x1800993f5  jz      loc_180099524
0x1800993fb  cmp     eax, r15d
0x1800993fe  ja      loc_180099524
0x180099404  mov     [r13+0], esi
0x180099408  mov     ebx, 1
0x18009940d  jmp     $ErrRtn_1
0x180099412  call    cs:__imp_StringFromCLSID
0x180099418  mov     r10d, 40h ; '@'
0x18009941e  lea     r8, aClsid_0; "CLSID\\"
0x180099425  mov     edx, r10d; cchDest
0x180099428  lea     rclsid, [rsp+130h+szKey]; pszDest
0x18009942d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099432  mov     r8, [rsp+130h+pszClass]; pszSrc
0x180099437  lea     rclsid, [rsp+130h+szKey]; pszDest
0x18009943c  mov     edx, r10d; cchDest
0x18009943f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180099444  mov     rclsid, [rsp+130h+pszClass]; pv
0x180099449  call    cs:__imp_CoTaskMemFree
0x18009944f  lea     r8, [rsp+130h+hKey]; phkResult
0x180099454  mov     edx, 2000000h; samDesired
0x180099459  lea     rclsid, [rsp+130h+szKey]; pszSubKey
0x18009945e  call    OpenClassesRootKeyExW
0x180099463  test    eax, eax
0x180099465  jnz     loc_18009934A
0x18009946b  mov     rclsid, [rsp+130h+hKey]; hKey
0x180099470  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x180099475  lea     pszEXE, ?DefaultIcon@Constants@Catalog@Com@@3QBGB; pszKey
0x18009947c  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x180099481  mov     ebx, eax
0x180099483  test    eax, eax
0x180099485  jz      short loc_1800994BB
0x180099487  mov     rclsid, [rsp+130h+hKey]; hKey
0x18009948c  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x180099491  lea     pszEXE, ?LocalServer32@Constants@Catalog@Com@@3QBGB; pszKey
0x180099498  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x18009949d  mov     ebx, eax
0x18009949f  test    eax, eax
0x1800994a1  jz      short loc_1800994BB
0x1800994a3  mov     rclsid, [rsp+130h+hKey]; hKey
0x1800994a8  lea     r8, [rsp+130h+lpBuffer]; ppszValue
0x1800994ad  lea     pszEXE, aLocalserver; "LocalServer"
0x1800994b4  call    ?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; RegReadDefValue(HKEY__ *,ushort const *,ushort * *)
0x1800994b9  mov     ebx, eax
0x1800994bb  mov     rclsid, [rsp+130h+hKey]; hKey
0x1800994c0  call    cs:__imp_RegCloseKey
0x1800994c6  mov     rdi, [rsp+130h+lpBuffer]
0x1800994cb  test    ebx, ebx
0x1800994cd  jnz     short loc_180099524
0x1800994cf  mov     r14, rdi
0x1800994d2  xor     cch, cch; nSize
0x1800994d5  xor     edx, edx; lpDst
0x1800994d7  mov     rclsid, r14; lpSrc
0x1800994da  call    cs:__imp_ExpandEnvironmentStringsW
0x1800994e0  mov     ebx, eax
0x1800994e2  test    eax, eax
0x1800994e4  jz      short loc_180099524
0x1800994e6  mov     ecx, ebx
0x1800994e8  add     rclsid, rclsid; cb
0x1800994eb  call    cs:__imp_CoTaskMemAlloc
0x1800994f1  mov     cch, ebx; nSize
0x1800994f4  mov     rclsid, r14; lpSrc
0x1800994f7  mov     pszEXE, rax; lpDst
0x1800994fa  mov     rsi, rax
0x1800994fd  call    cs:__imp_ExpandEnvironmentStringsW
0x180099503  test    eax, eax
0x180099505  jz      short loc_180099524
0x180099507  cmp     eax, ebx
0x180099509  ja      short loc_180099524
0x18009950b  mov     r9d, r15d; cchEXE
0x18009950e  mov     [rsp+130h+pIndex], r13; pIndex
0x180099513  mov     r8, r12; pszEXE
0x180099516  mov     pszEXE, rsi; pszInfo
0x180099519  mov     ecx, ebx; dw
0x18009951b  call    ?ExtractNameAndIndex@@YAHKPEAG0IPEAI@Z; ExtractNameAndIndex(ulong,ushort *,ushort *,uint,uint *)
0x180099520  mov     ebx, eax
0x180099522  jmp     short $ErrRtn_1
0x180099524  xor     ebx, ebx
0x180099526  test    rdi, rdi
0x180099529  jz      short loc_180099534
0x18009952b  mov     rclsid, rdi; pv
0x18009952e  call    cs:__imp_CoTaskMemFree
0x180099534  test    rsi, rsi
0x180099537  jz      short loc_180099542
0x180099539  mov     rclsid, rsi; pv
0x18009953c  call    cs:__imp_CoTaskMemFree
0x180099542  mov     rclsid, [rsp+130h+packagedComDefaultIcon.m_ptr]; string
0x180099547  test    rclsid, rclsid
0x18009954a  jz      short loc_180099552
0x18009954c  call    cs:__imp_WindowsDeleteString
0x180099552  lea     rclsid, [rsp+130h+oleClassInfo]; this
0x180099557  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18009955c  mov     eax, ebx
0x18009955e  mov     rclsid, [rbp+4Fh+var_50]
0x180099562  xor     rclsid, rsp; StackCookie
0x180099565  call    __security_check_cookie
0x18009956a  add     rsp, 0F8h
0x180099571  pop     r15
0x180099573  pop     r14
0x180099575  pop     r13
0x180099577  pop     r12
0x180099579  pop     rdi
0x18009957a  pop     rsi
0x18009957b  pop     rbx
0x18009957c  pop     rbp
0x18009957d  retn
```
