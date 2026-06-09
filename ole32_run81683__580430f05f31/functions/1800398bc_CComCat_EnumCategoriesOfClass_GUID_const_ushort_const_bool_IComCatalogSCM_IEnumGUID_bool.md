# CComCat::EnumCategoriesOfClass(_GUID const &,ushort const *,bool,IComCatalogSCM *,IEnumGUID * *,bool)

- ea: `0x1800398bc`
- end: `0x180039ad1`
- name: `?EnumCategoriesOfClass@CComCat@@CAJAEBU_GUID@@PEBG_NPEAUIComCatalogSCM@@PEAPEAUIEnumGUID@@2@Z`
- size: `533`
- prototype: `HRESULT __fastcall(const _GUID *rclsid, const wchar_t *lpszSubKey, bool pComCatalog, IComCatalogSCM *ppenumCatid, IEnumGUID **disablePackagedComForTesting, bool rclsid)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a8420`
- `0x1800a8550`

## callees

- `0x180017c88`
- `0x1800185ec`
- `0x18001a3c8`
- `0x1800398bc`
- `0x1800472ec`
- `0x18004e8f0`
- `0x18004fdfc`
- `0x1800aa558`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039a28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003998c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039aa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039ab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003998c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039aa3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039ab2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800399d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800399d4`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18003995f`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18003995f`

## string_xrefs

- `0x18003996f`: `com\ole32\comcat\src\comcat.cpp`
- `0x1800399e2`: `com\ole32\comcat\src\comcat.cpp`

## pseudocode

```c
__int64 __fastcall CComCat::EnumCategoriesOfClass(
        const _GUID *rclsid,
        const wchar_t *lpszSubKey,
        bool pComCatalog,
        IComCatalogSCM *ppenumCatid,
        IEnumGUID **disablePackagedComForTesting,
        bool rclsid_0)
{
  signed __int64 v9; // rcx
  int v10; // eax
  int v11; // edx
  unsigned int v12; // ebx
  HRESULT v13; // eax
  unsigned int v14; // edi
  IComClassCategoryInfo *v15; // rcx
  LSTATUS v17; // eax
  IEnumGUID **v18; // rdi
  HANDLE v19; // rcx
  CEnumCategoriesOfClass *v20; // rax
  CEnumCategoriesOfClass *v21; // rax
  CEnumCategoriesOfClass *v22; // rbx
  struct IUnknownVtbl *lpVtbl; // rcx
  unsigned int v24; // edx
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > hkeyClsid; // [rsp+30h] [rbp-28h] BYREF
  Microsoft::WRL::ComPtr<IComClassCategoryInfo> classCategoryInfo; // [rsp+38h] [rbp-20h] BYREF
  HKEY__ *hKey; // [rsp+40h] [rbp-18h] BYREF
  IComClassCategoryInfo *ptr; // [rsp+48h] [rbp-10h] BYREF
  void *retaddr; // [rsp+78h] [rbp+20h]
  bool v30; // [rsp+90h] [rbp+38h] BYREF

  v30 = pComCatalog;
  classCategoryInfo.ptr_ = 0;
  if ( !rclsid_0 )
  {
    Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease((Microsoft::WRL::ComPtr<IEnterpriseDropTarget> *)&classCategoryInfo);
    if ( GetClassInfoWithInprocOrLocalServer(
           rclsid,
           ppenumCatid,
           &GUID_00d489b0_06a7_0074_9ce0_065132561673,
           (void **)&classCategoryInfo.ptr_) >= 0 )
    {
      v9 = (char *)Com::Catalog::Constants::Implemented_Categories - (char *)lpszSubKey;
      do
      {
        v10 = *(const wchar_t *)((char *)lpszSubKey + v9);
        v11 = *lpszSubKey - v10;
        if ( v11 )
          break;
        ++lpszSubKey;
      }
      while ( v10 );
      ptr = classCategoryInfo.ptr_;
      v30 = v11 == 0;
      v12 = Microsoft::WRL::Details::MakeAndInitialize<CEnumCategoriesOfCatalogClass,IEnumGUID,IComClassCategoryInfo * &,bool &>(
              disablePackagedComForTesting,
              &ptr,
              &v30);
LABEL_28:
      Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease((Microsoft::WRL::ComPtr<IEnterpriseDropTarget> *)&classCategoryInfo);
      return v12;
    }
  }
  hkeyClsid.m_ptr = 0;
  v13 = InternalRegOpenClassKey(rclsid, 131097, &hkeyClsid);
  v14 = v13;
  if ( v13 >= 0 )
  {
    hKey = 0;
    v17 = RegOpenKeyExW(hkeyClsid.m_ptr, lpszSubKey, 0, 0x20019u, &hKey);
    if ( v17 )
    {
      v12 = wil::details::in1diag3::Return_Win32(retaddr, 0x47Cu, "com\\ole32\\comcat\\src\\comcat.cpp", v17);
      if ( hkeyClsid.m_ptr )
        RegCloseKey(hkeyClsid.m_ptr);
    }
    else
    {
      v18 = disablePackagedComForTesting;
      v19 = g_hHeap;
      *disablePackagedComForTesting = 0;
      v20 = (CEnumCategoriesOfClass *)HeapAlloc(v19, 0, 0x40u);
      if ( v20 && (CEnumCategoriesOfClass::CEnumCategoriesOfClass(v20), (v22 = v21) != 0) )
      {
        v21->m_hKey = hKey;
        lpVtbl = v21->lpVtbl;
        v21->m_bMapOldKeys = 0;
        if ( ((int (__fastcall *)(CEnumCategoriesOfClass *, GUID *, IEnumGUID **))lpVtbl->QueryInterface)(
               v21,
               &IID_IEnumGUID,
               v18) >= 0 )
        {
          if ( hkeyClsid.m_ptr )
            RegCloseKey(hkeyClsid.m_ptr);
          v12 = 0;
        }
        else
        {
          CEnumCategoriesOfClass::`scalar deleting destructor'(v22, v24);
          if ( hkeyClsid.m_ptr )
            RegCloseKey(hkeyClsid.m_ptr);
          v12 = -2147418113;
        }
      }
      else
      {
        RegCloseKey(hKey);
        if ( hkeyClsid.m_ptr )
          RegCloseKey(hkeyClsid.m_ptr);
        v12 = -2147024882;
      }
    }
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(retaddr, 0x479u, "com\\ole32\\comcat\\src\\comcat.cpp", v13);
  if ( hkeyClsid.m_ptr )
    RegCloseKey(hkeyClsid.m_ptr);
  v15 = classCategoryInfo.ptr_;
  if ( classCategoryInfo.ptr_ )
  {
    classCategoryInfo.ptr_ = 0;
    ((void (__fastcall *)(IComClassCategoryInfo *))v15->lpVtbl->Release)(v15);
  }
  return v14;
}

```

## disassembly

```asm
0x1800398bc  mov     [rsp-20h+arg_10], r8b
0x1800398c1  push    rbp
0x1800398c2  push    rbx
0x1800398c3  push    rsi
0x1800398c4  push    rdi
0x1800398c5  mov     rbp, rsp
0x1800398c8  sub     rsp, 58h
0x1800398cc  cmp     [rbp+rclsid_0], 0
0x1800398d0  mov     rsi, pComCatalog
0x1800398d3  mov     rbx, lpszSubKey
0x1800398d6  mov     [rbp+classCategoryInfo.ptr_], 0
0x1800398de  mov     rdi, rclsid
0x1800398e1  jnz     short loc_180039949
0x1800398e3  lea     rclsid, [rbp+classCategoryInfo]; this
0x1800398e7  call    ?InternalRelease@?$ComPtr@UIEnterpriseDropTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(void)
0x1800398ec  lea     pComCatalog, [rbp+classCategoryInfo]; ppv
0x1800398f0  mov     lpszSubKey, rsi; pComCatalog
0x1800398f3  lea     r8, _GUID_00d489b0_06a7_0074_9ce0_065132561673; riid
0x1800398fa  mov     rclsid, rdi; clsid
0x1800398fd  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x180039902  test    eax, eax
0x180039904  js      short loc_180039949
0x180039906  lea     rclsid, ?Implemented_Categories@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::Implemented_Categories
0x18003990d  sub     rclsid, rbx
0x180039910  movzx   edx, word ptr [rbx]
0x180039913  movzx   eax, word ptr [rbx+rclsid]
0x180039917  sub     edx, eax
0x180039919  jnz     short loc_180039923
0x18003991b  add     rbx, 2
0x18003991f  test    eax, eax
0x180039921  jnz     short loc_180039910
0x180039923  mov     rax, [rbp+classCategoryInfo.ptr_]
0x180039927  lea     r8, [rbp+arg_10]; <args_1>
0x18003992b  mov     rclsid, [rbp+result]; result
0x18003992f  test    edx, edx
0x180039931  lea     lpszSubKey, [rbp+var_10]; <args_0>
0x180039935  mov     [rbp+var_10], rax
0x180039939  setz    [rbp+arg_10]
0x18003993d  call    ??$MakeAndInitialize@VCEnumCategoriesOfCatalogClass@@UIEnumGUID@@AEAPEAUIComClassCategoryInfo@@AEA_N@Details@WRL@Microsoft@@YAJPEAPEAUIEnumGUID@@AEAPEAUIComClassCategoryInfo@@AEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<CEnumCategoriesOfCatalogClass,IEnumGUID,IComClassCategoryInfo * &,bool &>(IEnumGUID * *,IComClassCategoryInfo * &,bool &)
0x180039942  mov     ebx, eax
0x180039944  jmp     loc_180039ABD
0x180039949  mov     esi, 20019h
0x18003994e  mov     [rbp+hkeyClsid.m_ptr], 0
0x180039956  mov     edx, esi
0x180039958  lea     r8, [rbp+hkeyClsid]
0x18003995c  mov     rclsid, rdi
0x18003995f  call    cs:__imp_InternalRegOpenClassKey
0x180039965  mov     edi, eax
0x180039967  test    eax, eax
0x180039969  jns     short loc_1800399B6
0x18003996b  mov     rclsid, [rbp+20h]; callerReturnAddress
0x18003996f  lea     r8, aComOle32Comcat; "com\\ole32\\comcat\\src\\comcat.cpp"
0x180039976  mov     r9d, eax; hr
0x180039979  mov     edx, 479h; lineNumber
0x18003997e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039983  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x180039987  test    rclsid, rclsid
0x18003998a  jz      short loc_180039992
0x18003998c  call    cs:__imp_RegCloseKey
0x180039992  mov     rclsid, [rbp+classCategoryInfo.ptr_]
0x180039996  test    rclsid, rclsid
0x180039999  jz      short loc_1800399AF
0x18003999b  mov     [rbp+classCategoryInfo.ptr_], 0
0x1800399a3  mov     rax, [rclsid]
0x1800399a6  mov     rax, [rax+10h]
0x1800399aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399af  mov     eax, edi
0x1800399b1  jmp     loc_180039AC8
0x1800399b6  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x1800399ba  lea     rax, [rbp+hKey]
0x1800399be  mov     r9d, esi; samDesired
0x1800399c1  mov     [rsp+58h+phkResult], rax; phkResult
0x1800399c6  xor     r8d, r8d; ulOptions
0x1800399c9  mov     [rbp+hKey], 0
0x1800399d1  mov     lpszSubKey, rbx; lpSubKey
0x1800399d4  call    cs:__imp_RegOpenKeyExW
0x1800399da  test    eax, eax
0x1800399dc  jz      short loc_180039A10
0x1800399de  mov     rclsid, [rbp+20h]; callerReturnAddress
0x1800399e2  lea     r8, aComOle32Comcat; "com\\ole32\\comcat\\src\\comcat.cpp"
0x1800399e9  mov     r9d, eax; err
0x1800399ec  mov     edx, 47Ch; lineNumber
0x1800399f1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800399f6  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x1800399fa  mov     ebx, eax
0x1800399fc  test    rclsid, rclsid
0x1800399ff  jz      loc_180039ABD
0x180039a05  call    cs:__imp_RegCloseKey
0x180039a0b  jmp     loc_180039ABD
0x180039a10  mov     rdi, [rbp+result]
0x180039a14  xor     edx, edx; dwFlags
0x180039a16  mov     rclsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x180039a1d  lea     r8d, [lpszSubKey+40h]; dwBytes
0x180039a21  mov     qword ptr [rdi], 0
0x180039a28  call    cs:__imp_HeapAlloc
0x180039a2e  test    rax, rax
0x180039a31  jz      short loc_180039A9F
0x180039a33  mov     rclsid, rax; this
0x180039a36  call    ??0CEnumCategoriesOfClass@@QEAA@XZ; CEnumCategoriesOfClass::CEnumCategoriesOfClass(void)
0x180039a3b  mov     rbx, rax
0x180039a3e  test    rax, rax
0x180039a41  jz      short loc_180039A9F
0x180039a43  mov     rclsid, [rbp+hKey]
0x180039a47  lea     lpszSubKey, IID_IEnumGUID
0x180039a4e  mov     [rax+10h], rclsid
0x180039a52  mov     r8, rdi
0x180039a55  mov     rclsid, [rax]
0x180039a58  mov     dword ptr [rax+0Ch], 0
0x180039a5f  mov     rax, [rclsid]
0x180039a62  mov     rclsid, rbx
0x180039a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a6a  test    eax, eax
0x180039a6c  jns     short loc_180039A8C
0x180039a6e  mov     rclsid, rbx; this
0x180039a71  call    ??_GCEnumCategoriesOfClass@@QEAAPEAXI@Z; CEnumCategoriesOfClass::`scalar deleting destructor'(uint)
0x180039a76  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x180039a7a  test    rclsid, rclsid
0x180039a7d  jz      short loc_180039A85
0x180039a7f  call    cs:__imp_RegCloseKey
0x180039a85  mov     ebx, 8000FFFFh
0x180039a8a  jmp     short loc_180039ABD
0x180039a8c  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x180039a90  test    rclsid, rclsid
0x180039a93  jz      short loc_180039A9B
0x180039a95  call    cs:__imp_RegCloseKey
0x180039a9b  xor     ebx, ebx
0x180039a9d  jmp     short loc_180039ABD
0x180039a9f  mov     rclsid, [rbp+hKey]; hKey
0x180039aa3  call    cs:__imp_RegCloseKey
0x180039aa9  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x180039aad  test    rclsid, rclsid
0x180039ab0  jz      short loc_180039AB8
0x180039ab2  call    cs:__imp_RegCloseKey
0x180039ab8  mov     ebx, 8007000Eh
0x180039abd  lea     rclsid, [rbp+classCategoryInfo]; this
0x180039ac1  call    ?InternalRelease@?$ComPtr@UIEnterpriseDropTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(void)
0x180039ac6  mov     eax, ebx
0x180039ac8  add     rsp, 58h
0x180039acc  pop     rdi
0x180039acd  pop     rsi
0x180039ace  pop     rbx
0x180039acf  pop     rbp
0x180039ad0  retn
```
