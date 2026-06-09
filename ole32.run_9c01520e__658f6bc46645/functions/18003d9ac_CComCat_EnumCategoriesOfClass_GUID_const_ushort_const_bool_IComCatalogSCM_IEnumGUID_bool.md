# CComCat::EnumCategoriesOfClass(_GUID const &,ushort const *,bool,IComCatalogSCM *,IEnumGUID * *,bool)

- ea: `0x18003d9ac`
- end: `0x18003dbc9`
- name: `?EnumCategoriesOfClass@CComCat@@CAJAEBU_GUID@@PEBG_NPEAUIComCatalogSCM@@PEAPEAUIEnumGUID@@2@Z`
- size: `541`
- prototype: `HRESULT __fastcall(const _GUID *rclsid, const wchar_t *lpszSubKey, bool pComCatalog, IComCatalogSCM *ppenumCatid, IEnumGUID **disablePackagedComForTesting, bool rclsid)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800af7e0`
- `0x1800af930`

## callees

- `0x18000f358`
- `0x180011800`
- `0x18001217c`
- `0x18003bee0`
- `0x18003d9ac`
- `0x18009bb14`
- `0x1800af350`
- `0x1800b14d4`
- `0x1800b1cb0`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003db1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003db1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dacf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dacf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003da87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003db8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003da87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003db8e`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18003da54`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18003da54`

## string_xrefs

- `0x18003da6a`: `com\ole32\comcat\src\comcat.cpp`
- `0x18003dae3`: `com\ole32\comcat\src\comcat.cpp`

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
  HKEY__ *v23; // rcx
  unsigned int v24; // edx
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (__cdecl*)(HKEY__ *),&RegCloseKey,wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t> > > hkeyClsid; // [rsp+30h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<IComClassCategoryInfo> classCategoryInfo; // [rsp+38h] [rbp-18h] BYREF
  HKEY__ *hKey; // [rsp+40h] [rbp-10h] BYREF
  IComClassCategoryInfo *ptr; // [rsp+48h] [rbp-8h] BYREF
  void *retaddr; // [rsp+58h] [rbp+8h]
  bool v30; // [rsp+70h] [rbp+20h] BYREF

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
LABEL_21:
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
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyClsid);
    }
    else
    {
      v18 = disablePackagedComForTesting;
      v19 = g_hHeap;
      *disablePackagedComForTesting = 0;
      v20 = (CEnumCategoriesOfClass *)HeapAlloc(v19, 0, 0x40u);
      if ( v20 && (CEnumCategoriesOfClass::CEnumCategoriesOfClass(v20), (v22 = v21) != 0) )
      {
        v23 = hKey;
        v21->m_bMapOldKeys = 0;
        v21->m_hKey = v23;
        if ( ((__int64 (__fastcall *)(CEnumCategoriesOfClass *, GUID *, IEnumGUID **))v21->lpVtbl->QueryInterface)(
               v21,
               &IID_IEnumGUID,
               v18) >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyClsid);
          v12 = 0;
        }
        else
        {
          CEnumCategoriesOfClass::`scalar deleting destructor'(v22, v24);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyClsid);
          v12 = -2147418113;
        }
      }
      else
      {
        RegCloseKey(hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkeyClsid);
        v12 = -2147024882;
      }
    }
    goto LABEL_21;
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
0x18003d9ac  mov     rax, rsp
0x18003d9af  mov     [rax+8], rbx
0x18003d9b3  mov     [rax+10h], rsi
0x18003d9b7  mov     [rax+20h], rdi
0x18003d9bb  mov     [rax+18h], r8b
0x18003d9bf  push    rbp
0x18003d9c0  mov     rbp, rsp
0x18003d9c3  sub     rsp, 50h
0x18003d9c7  and     [rbp+classCategoryInfo.ptr_], 0
0x18003d9cc  mov     rsi, pComCatalog
0x18003d9cf  cmp     [rbp+rclsid_0], 0
0x18003d9d3  mov     rbx, lpszSubKey
0x18003d9d6  mov     rdi, rclsid
0x18003d9d9  jnz     short loc_18003DA41
0x18003d9db  lea     rclsid, [rbp+classCategoryInfo]; this
0x18003d9df  call    ?InternalRelease@?$ComPtr@UIEnterpriseDropTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(void)
0x18003d9e4  lea     pComCatalog, [rbp+classCategoryInfo]; ppv
0x18003d9e8  mov     lpszSubKey, rsi; pComCatalog
0x18003d9eb  lea     r8, _GUID_00d489b0_06a7_0074_9ce0_065132561673; riid
0x18003d9f2  mov     rclsid, rdi; clsid
0x18003d9f5  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18003d9fa  test    eax, eax
0x18003d9fc  js      short loc_18003DA41
0x18003d9fe  lea     rclsid, ?Implemented_Categories@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::Implemented_Categories
0x18003da05  sub     rclsid, rbx
0x18003da08  movzx   edx, word ptr [rbx]
0x18003da0b  movzx   eax, word ptr [rbx+rclsid]
0x18003da0f  sub     edx, eax
0x18003da11  jnz     short loc_18003DA1B
0x18003da13  add     rbx, 2
0x18003da17  test    eax, eax
0x18003da19  jnz     short loc_18003DA08
0x18003da1b  mov     rax, [rbp+classCategoryInfo.ptr_]
0x18003da1f  lea     r8, [rbp+arg_10]; <args_1>
0x18003da23  mov     rclsid, [rbp+result]; result
0x18003da27  test    edx, edx
0x18003da29  lea     lpszSubKey, [rbp+var_8]; <args_0>
0x18003da2d  mov     [rbp+var_8], rax
0x18003da31  setz    [rbp+arg_10]
0x18003da35  call    ??$MakeAndInitialize@VCEnumCategoriesOfCatalogClass@@UIEnumGUID@@AEAPEAUIComClassCategoryInfo@@AEA_N@Details@WRL@Microsoft@@YAJPEAPEAUIEnumGUID@@AEAPEAUIComClassCategoryInfo@@AEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<CEnumCategoriesOfCatalogClass,IEnumGUID,IComClassCategoryInfo * &,bool &>(IEnumGUID * *,IComClassCategoryInfo * &,bool &)
0x18003da3a  mov     ebx, eax
0x18003da3c  jmp     loc_18003DBA8
0x18003da41  and     [rbp+hkeyClsid.m_ptr], 0
0x18003da46  lea     r8, [rbp+hkeyClsid]
0x18003da4a  mov     esi, 20019h
0x18003da4f  mov     rclsid, rdi
0x18003da52  mov     edx, esi
0x18003da54  call    cs:__imp_InternalRegOpenClassKey
0x18003da5b  nop     dword ptr [rax+rax+00h]
0x18003da60  mov     edi, eax
0x18003da62  test    eax, eax
0x18003da64  jns     short loc_18003DAB4
0x18003da66  mov     rclsid, [rbp+8]; callerReturnAddress
0x18003da6a  lea     r8, aComOle32Comcat; "com\\ole32\\comcat\\src\\comcat.cpp"
0x18003da71  mov     r9d, eax; hr
0x18003da74  mov     edx, 479h; lineNumber
0x18003da79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003da7e  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x18003da82  test    rclsid, rclsid
0x18003da85  jz      short loc_18003DA93
0x18003da87  call    cs:__imp_RegCloseKey
0x18003da8e  nop     dword ptr [rax+rax+00h]
0x18003da93  mov     rclsid, [rbp+classCategoryInfo.ptr_]
0x18003da97  test    rclsid, rclsid
0x18003da9a  jz      short loc_18003DAAD
0x18003da9c  and     [rbp+classCategoryInfo.ptr_], 0
0x18003daa1  mov     rax, [rclsid]
0x18003daa4  mov     rax, [rax+10h]
0x18003daa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003daad  mov     eax, edi
0x18003daaf  jmp     loc_18003DBB3
0x18003dab4  mov     rclsid, [rbp+hkeyClsid.m_ptr]; hKey
0x18003dab8  lea     rax, [rbp+hKey]
0x18003dabc  and     [rbp+hKey], 0
0x18003dac1  mov     r9d, esi; samDesired
0x18003dac4  xor     r8d, r8d; ulOptions
0x18003dac7  mov     [rsp+50h+phkResult], rax; phkResult
0x18003dacc  mov     lpszSubKey, rbx; lpSubKey
0x18003dacf  call    cs:__imp_RegOpenKeyExW
0x18003dad6  nop     dword ptr [rax+rax+00h]
0x18003dadb  test    eax, eax
0x18003dadd  jz      short loc_18003DB07
0x18003dadf  mov     rclsid, [rbp+8]; callerReturnAddress
0x18003dae3  lea     r8, aComOle32Comcat; "com\\ole32\\comcat\\src\\comcat.cpp"
0x18003daea  mov     r9d, eax; err
0x18003daed  mov     edx, 47Ch; lineNumber
0x18003daf2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003daf7  lea     rclsid, [rbp+hkeyClsid]; this
0x18003dafb  mov     ebx, eax
0x18003dafd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003db02  jmp     loc_18003DBA8
0x18003db07  mov     rdi, [rbp+result]
0x18003db0b  xor     edx, edx; dwFlags
0x18003db0d  mov     rclsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003db14  and     qword ptr [rdi], 0
0x18003db18  lea     r8d, [lpszSubKey+40h]; dwBytes
0x18003db1c  call    cs:__imp_HeapAlloc
0x18003db23  nop     dword ptr [rax+rax+00h]
0x18003db28  test    rax, rax
0x18003db2b  jz      short loc_18003DB8A
0x18003db2d  mov     rclsid, rax; this
0x18003db30  call    ??0CEnumCategoriesOfClass@@QEAA@XZ; CEnumCategoriesOfClass::CEnumCategoriesOfClass(void)
0x18003db35  mov     rbx, rax
0x18003db38  test    rax, rax
0x18003db3b  jz      short loc_18003DB8A
0x18003db3d  mov     rclsid, [rbp+hKey]
0x18003db41  lea     lpszSubKey, IID_IEnumGUID
0x18003db48  and     dword ptr [rax+0Ch], 0
0x18003db4c  mov     r8, rdi
0x18003db4f  mov     [rax+10h], rclsid
0x18003db53  mov     rclsid, [rax]
0x18003db56  mov     rax, [rclsid]
0x18003db59  mov     rclsid, rbx
0x18003db5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db61  test    eax, eax
0x18003db63  jns     short loc_18003DB7D
0x18003db65  mov     rclsid, rbx; this
0x18003db68  call    ??_GCEnumCategoriesOfClass@@QEAAPEAXI@Z; CEnumCategoriesOfClass::`scalar deleting destructor'(uint)
0x18003db6d  lea     rclsid, [rbp+hkeyClsid]; this
0x18003db71  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003db76  mov     ebx, 8000FFFFh
0x18003db7b  jmp     short loc_18003DBA8
0x18003db7d  lea     rclsid, [rbp+hkeyClsid]; this
0x18003db81  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003db86  xor     ebx, ebx
0x18003db88  jmp     short loc_18003DBA8
0x18003db8a  mov     rclsid, [rbp+hKey]; hKey
0x18003db8e  call    cs:__imp_RegCloseKey
0x18003db95  nop     dword ptr [rax+rax+00h]
0x18003db9a  lea     rclsid, [rbp+hkeyClsid]; this
0x18003db9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003dba3  mov     ebx, 8007000Eh
0x18003dba8  lea     rclsid, [rbp+classCategoryInfo]; this
0x18003dbac  call    ?InternalRelease@?$ComPtr@UIEnterpriseDropTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IEnterpriseDropTarget>::InternalRelease(void)
0x18003dbb1  mov     eax, ebx
0x18003dbb3  mov     rbx, [rsp+50h+arg_0]
0x18003dbb8  mov     rsi, [rsp+50h+arg_8]
0x18003dbbd  mov     rdi, [rsp+50h+arg_18]
0x18003dbc2  add     rsp, 50h
0x18003dbc6  pop     rbp
0x18003dbc7  retn
```
