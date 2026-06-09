# MapsBackgroundTransferJob::StoreActiveRequests(void)

- ea: `0x18000f49c`
- end: `0x18000f902`
- name: `?StoreActiveRequests@MapsBackgroundTransferJob@@AEAAJXZ`
- size: `1126`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000f910`

## callees

- `0x180001e70`
- `0x18000398c`
- `0x180003c34`
- `0x180004094`
- `0x1800043e4`
- `0x180004408`
- `0x1800047cc`
- `0x180008d3c`
- `0x18000a10c`
- `0x18000a9b8`
- `0x18000adf0`
- `0x18000ae58`
- `0x18000ae88`
- `0x18000aeb8`
- `0x18000b070`
- `0x18000b0cc`
- `0x18000b128`
- `0x18000b3dc`
- `0x18000b738`
- `0x18000b7dc`
- `0x18000f49c`
- `0x18001074c`
- `0x180010954`
- `0x180010f80`
- `0x180011160`
- `0x1800111d0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f5cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f5cd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f61b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f61b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f655`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f655`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000f7bf`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000f7bf`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000f67b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000f6a5`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000f67b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000f6a5`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::StoreActiveRequests(MapsBackgroundTransferJob *this)
{
  unsigned int v2; // r14d
  __int64 *v3; // rdi
  __int64 *i; // rbx
  __int64 *v5; // rdi
  __int64 *j; // rbx
  __int64 *v7; // rdi
  __int64 *k; // rbx
  HKEY v9; // rbx
  const WCHAR *v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r9
  _DWORD v22[4]; // [rsp+50h] [rbp-168h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-158h] BYREF
  BYTE *lpData[2]; // [rsp+68h] [rbp-150h] BYREF
  __int64 v25; // [rsp+78h] [rbp-140h]
  MapsBackgroundTransferJob *v26; // [rsp+80h] [rbp-138h]
  _BYTE v27[8]; // [rsp+90h] [rbp-128h] BYREF
  __int64 *v28; // [rsp+98h] [rbp-120h]
  _BYTE v29[8]; // [rsp+D0h] [rbp-E8h] BYREF
  __int64 *v30; // [rsp+D8h] [rbp-E0h]
  _BYTE v31[8]; // [rsp+110h] [rbp-A8h] BYREF
  __int64 *v32; // [rsp+118h] [rbp-A0h]
  _BYTE v33[16]; // [rsp+150h] [rbp-68h] BYREF
  unsigned __int16 v34[8]; // [rsp+170h] [rbp-48h] BYREF
  int v35; // [rsp+180h] [rbp-38h]

  v26 = this;
  v2 = 0;
  hKey = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>(lpData);
  std::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>(v31);
  std::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>(v29);
  std::unordered_map<std::wstring,unsigned long>::unordered_map<std::wstring,unsigned long>(v27);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v22,
    (char *)this + 784);
  std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::operator=(
    v29,
    (char *)this + 672);
  std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::operator=(
    v31,
    (char *)this + 608);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v22);
  v3 = v30;
  for ( i = (__int64 *)*v30; i != v3; i = (__int64 *)*i )
  {
    v22[0] = *((_DWORD *)i + 20);
    std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::emplace<std::wstring const &,unsigned long>(
      v27,
      v34,
      i + 2,
      v22);
  }
  v5 = v32;
  for ( j = (__int64 *)*v32; j != v5; j = (__int64 *)*j )
  {
    v22[0] = *((_DWORD *)j + 20);
    std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::emplace<std::wstring const &,unsigned long>(
      v27,
      v34,
      j + 2,
      v22);
    while ( j[10] )
    {
      v16 = std::queue<MapsBackgroundTransferJob::RequestContext>::front(j + 6);
      v19 = std::deque<MapsBackgroundTransferJob::RequestContext>::pop_front(j + 6, v17, v18, v16);
      if ( *(_QWORD *)v19 )
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))v19)(
          0,
          2147500036LL,
          0,
          *(_QWORD *)(v20 + 8),
          *(_QWORD *)(v19 + 16));
    }
  }
  v7 = v28;
  for ( k = (__int64 *)*v28; k != v7; k = (__int64 *)*k )
  {
    *(_OWORD *)v34 = 0;
    v35 = 0;
    v13 = StringCchPrintfW(v34, 0xAu, L"%u", *((unsigned int *)k + 12));
    if ( v13 < 0 )
    {
      v2 = ZTraceReportPropagation(v13, "MapsBackgroundTransferJob::StoreActiveRequests", 1124, this);
      goto LABEL_27;
    }
    std::wstring::wstring(v33, v34);
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    std::vector<unsigned short>::_Insert_counted_range<unsigned short const *>(lpData, lpData[1], v14);
    LOWORD(v22[0]) = 59;
    std::vector<unsigned short>::push_back(lpData, v22);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(k + 2);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(k + 2);
    std::vector<unsigned short>::_Insert_counted_range<unsigned short const *>(lpData, lpData[1], v15);
    LOWORD(v22[0]) = 0;
    std::vector<unsigned short>::push_back(lpData, v22);
    std::wstring::_Tidy_deallocate(v33);
  }
  if ( lpData[0] != lpData[1] )
  {
    LOWORD(v22[0]) = 0;
    std::vector<unsigned short>::push_back(lpData, v22);
    v9 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v22);
      RegCloseKey(v9);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v22);
    }
    hKey = 0;
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
    v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v11 )
    {
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v2 = ZTraceReportOrigination(v11, "MapsBackgroundTransferJob::StoreActiveRequests", 1148, this);
    }
    else
    {
      v12 = RegSetValueExW(hKey, L"ActiveRequests", 0, 7u, lpData[0], 2 * ((lpData[1] - lpData[0]) >> 1));
      if ( v12 )
      {
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        v2 = ZTraceReportOrigination(v12, "MapsBackgroundTransferJob::StoreActiveRequests", 1156, this);
      }
    }
  }
LABEL_27:
  std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v27);
  __1___Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__queue_V__CComPtr_UIBackgroundCopyFile___ATL__V__deque_V__CComPtr_UIBackgroundCopyFile___ATL__V__allocator_V__CComPtr_UIBackgroundCopyFile___ATL___std___std___2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__queue_V__CComPtr_UIBackgroundCopyFile___ATL__V__deque_V__CComPtr_UIBackgroundCopyFile___ATL__V__allocator_V__CComPtr_UIBackgroundCopyFile___ATL___std___std___2__std___2__0A__std___std__QEAA_XZ(v29);
  std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>(v31);
  if ( lpData[0] )
  {
    std::_Deallocate<16>(lpData[0], 2 * ((signed __int64)(v25 - (unsigned __int64)lpData[0]) >> 1));
    *(_OWORD *)lpData = 0;
    v25 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x18000f49c  mov     [rsp+arg_8], rbx
0x18000f4a1  mov     [rsp+arg_10], rsi
0x18000f4a6  push    rdi
0x18000f4a7  push    r12
0x18000f4a9  push    r13
0x18000f4ab  push    r14
0x18000f4ad  push    r15
0x18000f4af  sub     rsp, 190h
0x18000f4b6  mov     rax, cs:__security_cookie
0x18000f4bd  xor     rax, rsp
0x18000f4c0  mov     [rsp+1B8h+var_30], rax
0x18000f4c8  mov     r15, rcx
0x18000f4cb  mov     [rsp+1B8h+var_138], rcx
0x18000f4d3  xor     esi, esi
0x18000f4d5  mov     r14d, esi
0x18000f4d8  mov     [rsp+1B8h+hKey], rsi
0x18000f4dd  lea     rcx, [rsp+1B8h+lpData]
0x18000f4e2  call    ??$?0AEBV?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@QEAVMapsBackgroundTransferJob@@V?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>>>>>>(std::allocator<std::pair<MapsBackgroundTransferJob * const,std::shared_ptr<MapsBackgroundTransferJob>>> const &)
0x18000f4e7  nop
0x18000f4e8  lea     rcx, [rsp+1B8h+var_A8]
0x18000f4f0  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>(void)
0x18000f4f5  nop
0x18000f4f6  lea     rcx, [rsp+1B8h+var_E8]
0x18000f4fe  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>(void)
0x18000f503  nop
0x18000f504  lea     rcx, [rsp+1B8h+var_128]
0x18000f50c  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,ulong>::unordered_map<std::wstring,ulong>(void)
0x18000f511  nop
0x18000f512  lea     rdx, [r15+310h]
0x18000f519  lea     rcx, [rsp+1B8h+var_168]
0x18000f51e  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18000f523  lea     rdx, [r15+2A0h]
0x18000f52a  lea     rcx, [rsp+1B8h+var_E8]
0x18000f532  call    ??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>> &&)
0x18000f537  lea     rdx, [r15+260h]
0x18000f53e  lea     rcx, [rsp+1B8h+var_A8]
0x18000f546  call    ??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>> &&)
0x18000f54b  lea     rcx, [rsp+1B8h+var_168]
0x18000f550  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000f555  nop
0x18000f556  mov     rdi, [rsp+1B8h+var_E0]
0x18000f55e  mov     rbx, [rdi]
0x18000f561  cmp     rbx, rdi
0x18000f564  jnz     loc_18000F83E
0x18000f56a  mov     rdi, [rsp+1B8h+var_A0]
0x18000f572  mov     rbx, [rdi]
0x18000f575  cmp     rbx, rdi
0x18000f578  jnz     loc_18000F7CD
0x18000f57e  mov     rdi, [rsp+1B8h+var_120]
0x18000f586  mov     rbx, [rdi]
0x18000f589  cmp     rbx, rdi
0x18000f58c  jnz     loc_18000F6B8
0x18000f592  mov     rax, [rsp+1B8h+lpData+8]
0x18000f597  cmp     [rsp+1B8h+lpData], rax
0x18000f59c  jz      loc_18000F6B3
0x18000f5a2  mov     word ptr [rsp+1B8h+var_168], si
0x18000f5a7  lea     rdx, [rsp+1B8h+var_168]
0x18000f5ac  lea     rcx, [rsp+1B8h+lpData]
0x18000f5b1  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18000f5b6  mov     rbx, [rsp+1B8h+hKey]
0x18000f5bb  test    rbx, rbx
0x18000f5be  jz      short loc_18000F5DD
0x18000f5c0  lea     rcx, [rsp+1B8h+var_168]; this
0x18000f5c5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000f5ca  mov     rcx, rbx; hKey
0x18000f5cd  call    cs:__imp_RegCloseKey
0x18000f5d3  lea     rcx, [rsp+1B8h+var_168]; this
0x18000f5d8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000f5dd  mov     [rsp+1B8h+hKey], rsi
0x18000f5e2  lea     rcx, [r15+30h]
0x18000f5e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f5eb  mov     [rsp+1B8h+lpdwDisposition], rsi; lpdwDisposition
0x18000f5f0  lea     rcx, [rsp+1B8h+hKey]
0x18000f5f5  mov     [rsp+1B8h+phkResult], rcx; phkResult
0x18000f5fa  mov     [rsp+1B8h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000f5ff  mov     [rsp+1B8h+samDesired], 20006h; samDesired
0x18000f607  mov     [rsp+1B8h+dwOptions], esi; dwOptions
0x18000f60b  xor     r9d, r9d; lpClass
0x18000f60e  xor     r8d, r8d; Reserved
0x18000f611  mov     rdx, rax; lpSubKey
0x18000f614  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f61b  call    cs:__imp_RegCreateKeyExW
0x18000f621  test    eax, eax
0x18000f623  jnz     short loc_18000F689
0x18000f625  mov     rdx, [rsp+1B8h+lpData]
0x18000f62a  mov     rax, [rsp+1B8h+lpData+8]
0x18000f62f  sub     rax, rdx
0x18000f632  sar     rax, 1
0x18000f635  add     eax, eax
0x18000f637  mov     [rsp+1B8h+samDesired], eax; cbData
0x18000f63b  mov     qword ptr [rsp+1B8h+dwOptions], rdx; lpData
0x18000f640  mov     r9d, 7; dwType
0x18000f646  xor     r8d, r8d; Reserved
0x18000f649  lea     rdx, ValueName; "ActiveRequests"
0x18000f650  mov     rcx, [rsp+1B8h+hKey]; hKey
0x18000f655  call    cs:__imp_RegSetValueExW
0x18000f65b  test    eax, eax
0x18000f65d  jz      short loc_18000F6B3
0x18000f65f  jle     short loc_18000F669
0x18000f661  movzx   eax, ax
0x18000f664  or      eax, 80070000h
0x18000f669  mov     r9, r15
0x18000f66c  mov     r8d, 484h
0x18000f672  lea     rdx, aMapsbackground_29; "MapsBackgroundTransferJob::StoreActiveR"...
0x18000f679  mov     ecx, eax
0x18000f67b  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000f681  mov     r14d, eax
0x18000f684  jmp     loc_18000F873
0x18000f689  jle     short loc_18000F693
0x18000f68b  movzx   eax, ax
0x18000f68e  or      eax, 80070000h
0x18000f693  mov     r9, r15
0x18000f696  mov     r8d, 47Ch
0x18000f69c  lea     rdx, aMapsbackground_29; "MapsBackgroundTransferJob::StoreActiveR"...
0x18000f6a3  mov     ecx, eax
0x18000f6a5  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000f6ab  mov     r14d, eax
0x18000f6ae  jmp     loc_18000F873
0x18000f6b3  jmp     loc_18000F873
0x18000f6b8  xorps   xmm0, xmm0
0x18000f6bb  xor     eax, eax
0x18000f6bd  movups  xmmword ptr [rsp+1B8h+var_48], xmm0
0x18000f6c5  mov     [rsp+1B8h+var_38], eax
0x18000f6cc  mov     r9d, [rbx+30h]
0x18000f6d0  lea     r8, aU; "%u"
0x18000f6d7  lea     edx, [rax+0Ah]; unsigned __int64
0x18000f6da  lea     rcx, [rsp+1B8h+var_48]; unsigned __int16 *
0x18000f6e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f6e7  test    eax, eax
0x18000f6e9  js      loc_18000F7AD
0x18000f6ef  lea     rdx, [rsp+1B8h+var_48]
0x18000f6f7  lea     rcx, [rsp+1B8h+var_68]
0x18000f6ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000f704  nop
0x18000f705  mov     rax, [rsp+1B8h+var_58]
0x18000f70d  lea     r9, [rax+rax]
0x18000f711  sar     r9, 1
0x18000f714  lea     rcx, [rsp+1B8h+var_68]
0x18000f71c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f721  mov     r8, rax
0x18000f724  mov     rdx, [rsp+1B8h+lpData+8]
0x18000f729  lea     rcx, [rsp+1B8h+lpData]
0x18000f72e  call    ??$_Insert_counted_range@PEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@1@PEBG_K@Z; std::vector<ushort>::_Insert_counted_range<ushort const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort const *,unsigned __int64)
0x18000f733  mov     eax, 3Bh ; ';'
0x18000f738  mov     word ptr [rsp+1B8h+var_168], ax
0x18000f73d  lea     rdx, [rsp+1B8h+var_168]
0x18000f742  lea     rcx, [rsp+1B8h+lpData]
0x18000f747  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18000f74c  lea     rcx, [rbx+10h]
0x18000f750  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f755  mov     r8, rax
0x18000f758  lea     rcx, [rbx+10h]
0x18000f75c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f761  mov     r9, rax
0x18000f764  mov     rax, [rbx+20h]
0x18000f768  add     rax, rax
0x18000f76b  sub     rax, r8
0x18000f76e  add     r9, rax
0x18000f771  sar     r9, 1
0x18000f774  mov     rdx, [rsp+1B8h+lpData+8]
0x18000f779  lea     rcx, [rsp+1B8h+lpData]
0x18000f77e  call    ??$_Insert_counted_range@PEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@1@PEBG_K@Z; std::vector<ushort>::_Insert_counted_range<ushort const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,ushort const *,unsigned __int64)
0x18000f783  mov     word ptr [rsp+1B8h+var_168], si
0x18000f788  lea     rdx, [rsp+1B8h+var_168]
0x18000f78d  lea     rcx, [rsp+1B8h+lpData]
0x18000f792  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18000f797  nop
0x18000f798  lea     rcx, [rsp+1B8h+var_68]
0x18000f7a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f7a5  mov     rbx, [rbx]
0x18000f7a8  jmp     loc_18000F589
0x18000f7ad  mov     r9, r15
0x18000f7b0  mov     r8d, 464h
0x18000f7b6  lea     rdx, aMapsbackground_29; "MapsBackgroundTransferJob::StoreActiveR"...
0x18000f7bd  mov     ecx, eax
0x18000f7bf  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000f7c5  mov     r14d, eax
0x18000f7c8  jmp     loc_18000F873
0x18000f7cd  mov     eax, [rbx+50h]
0x18000f7d0  mov     [rsp+1B8h+var_168], eax
0x18000f7d4  lea     r9, [rsp+1B8h+var_168]
0x18000f7d9  lea     r8, [rbx+10h]
0x18000f7dd  lea     rdx, [rsp+1B8h+var_48]
0x18000f7e5  lea     rcx, [rsp+1B8h+var_128]
0x18000f7ed  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAK@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::emplace<std::wstring const &,ulong>(std::wstring const &,ulong &&)
0x18000f7f2  cmp     [rbx+50h], rsi
0x18000f7f6  jnz     short loc_18000F800
0x18000f7f8  mov     rbx, [rbx]
0x18000f7fb  jmp     loc_18000F575
0x18000f800  lea     rcx, [rbx+30h]
0x18000f804  call    ?front@?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@std@@QEAAAEAURequestContext@MapsBackgroundTransferJob@@XZ; std::queue<MapsBackgroundTransferJob::RequestContext>::front(void)
0x18000f809  mov     r9, rax
0x18000f80c  lea     rcx, [rbx+30h]
0x18000f810  call    ?pop_front@?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@QEAAXXZ; std::deque<MapsBackgroundTransferJob::RequestContext>::pop_front(void)
0x18000f815  mov     r10, [rax]
0x18000f818  test    r10, r10
0x18000f81b  jz      short loc_18000F7F2
0x18000f81d  mov     rax, [rax+10h]
0x18000f821  mov     qword ptr [rsp+1B8h+dwOptions], rax
0x18000f826  mov     r9, [r9+8]
0x18000f82a  xor     r8d, r8d
0x18000f82d  mov     edx, 80004004h
0x18000f832  xor     ecx, ecx
0x18000f834  mov     rax, r10
0x18000f837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f83c  jmp     short loc_18000F7F2
0x18000f83e  lea     r8, [rbx+10h]
0x18000f842  mov     eax, [r8+40h]
0x18000f846  mov     [rsp+1B8h+var_168], eax
0x18000f84a  lea     r9, [rsp+1B8h+var_168]
0x18000f84f  lea     rdx, [rsp+1B8h+var_48]
0x18000f857  lea     rcx, [rsp+1B8h+var_128]
0x18000f85f  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAK@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::emplace<std::wstring const &,ulong>(std::wstring const &,ulong &&)
0x18000f864  mov     rbx, [rbx]
0x18000f867  jmp     loc_18000F561
0x18000f86c  xor     esi, esi
0x18000f86e  mov     r14d, [rsp+1B8h+var_168]
0x18000f873  lea     rcx, [rsp+1B8h+var_128]
0x18000f87b  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::~_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>(void)
0x18000f880  nop
0x18000f881  lea     rcx, [rsp+1B8h+var_E8]
0x18000f889  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>(void)
0x18000f88e  nop
0x18000f88f  lea     rcx, [rsp+1B8h+var_A8]
0x18000f897  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>(void)
0x18000f89c  nop
0x18000f89d  mov     rcx, [rsp+1B8h+lpData]
0x18000f8a2  test    rcx, rcx
0x18000f8a5  jz      short loc_18000F8C8
0x18000f8a7  mov     rdx, [rsp+1B8h+var_140]
0x18000f8ac  sub     rdx, rcx
0x18000f8af  sar     rdx, 1
0x18000f8b2  add     rdx, rdx
0x18000f8b5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f8ba  xorps   xmm0, xmm0
0x18000f8bd  movdqu  xmmword ptr [rsp+1B8h+lpData], xmm0
0x18000f8c3  mov     [rsp+1B8h+var_140], rsi
0x18000f8c8  lea     rcx, [rsp+1B8h+hKey]
0x18000f8cd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000f8d2  mov     eax, r14d
0x18000f8d5  mov     rcx, [rsp+1B8h+var_30]
0x18000f8dd  xor     rcx, rsp; StackCookie
0x18000f8e0  call    __security_check_cookie
0x18000f8e5  lea     r11, [rsp+1B8h+var_28]
0x18000f8ed  mov     rbx, [r11+38h]
0x18000f8f1  mov     rsi, [r11+40h]
0x18000f8f5  mov     rsp, r11
0x18000f8f8  pop     r15
0x18000f8fa  pop     r14
0x18000f8fc  pop     r13
0x18000f8fe  pop     r12
0x18000f900  pop     rdi
0x18000f901  retn
```
