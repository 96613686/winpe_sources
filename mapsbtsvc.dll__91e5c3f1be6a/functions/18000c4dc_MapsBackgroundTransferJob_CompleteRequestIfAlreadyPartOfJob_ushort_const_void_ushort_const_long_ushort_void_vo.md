# MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob(ushort const *,void (*)(ushort const *,long,ushort *,void *,void *),void *,void *,bool *,bool *)

- ea: `0x18000c4dc`
- end: `0x18000c82e`
- name: `?CompleteRequestIfAlreadyPartOfJob@MapsBackgroundTransferJob@@AEAAJPEBGP6AX0JPEAGPEAX2@Z22PEA_N4@Z`
- size: `850`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *__hidden this, const unsigned __int16 *, void (*)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *), void *, void *, bool *, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000bb70`

## callees

- `0x180001e70`
- `0x1800033d4`
- `0x180003458`
- `0x180004094`
- `0x1800043e4`
- `0x180004408`
- `0x180004680`
- `0x1800047cc`
- `0x180009e94`
- `0x18000a6d8`
- `0x18000adf0`
- `0x18000c4dc`
- `0x180010954`
- `0x180010ed4`
- `0x180010f8c`
- `0x18001117c`
- `0x18001357c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c6b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c6b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c7e7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c7a9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000c7a9`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000c7dc`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000c7dc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c622`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c678`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c622`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c678`

## string_xrefs

- `0x18000c5e0`: `MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob(
        MapsBackgroundTransferJob *this,
        const unsigned __int16 *a2,
        void (*a3)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *),
        void *a4,
        void *a5,
        bool *a6,
        bool *a7)
{
  struct IUnknown *v9; // rbx
  char v10; // di
  char v11; // r15
  __int64 v12; // r14
  struct IUnknown *v13; // rdx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // r8d
  __int64 v18; // r14
  __int64 (__fastcall *v19)(__int64, LPVOID *); // r15
  void (__fastcall *v20)(_QWORD, __int64, _QWORD); // rax
  signed int LastError; // eax
  bool v23; // [rsp+30h] [rbp-A1h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-99h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-91h] BYREF
  LPVOID v26; // [rsp+50h] [rbp-81h] BYREF
  struct IUnknown *v27; // [rsp+58h] [rbp-79h] BYREF
  _BYTE v28[16]; // [rsp+60h] [rbp-71h] BYREF
  void *v29; // [rsp+70h] [rbp-61h]
  void *v30; // [rsp+78h] [rbp-59h]
  bool *v31; // [rsp+80h] [rbp-51h]
  bool *v32; // [rsp+88h] [rbp-49h]
  __int128 v33; // [rsp+90h] [rbp-41h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-31h]
  _BYTE v35[32]; // [rsp+A8h] [rbp-29h] BYREF

  v30 = a4;
  v29 = a5;
  v31 = a6;
  v32 = a7;
  v26 = 0;
  pv = 0;
  v9 = 0;
  v27 = 0;
  v10 = 0;
  v11 = 0;
  *a6 = 0;
  *a7 = 0;
  std::wstring::wstring(v35, a2);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v25,
    (char *)this + 784);
  if ( *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::find(
                    (char *)this + 672,
                    v28,
                    v35) != *((_QWORD *)this + 85) )
  {
    v12 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Try_emplace<std::wstring const &,>(
                       (char *)this + 672,
                       v28,
                       v35);
    v13 = *(struct IUnknown **)std::queue<ATL::CComPtr<IBackgroundCopyFile>>::front(v12 + 48);
    if ( v13 )
    {
      ATL::AtlComPtrAssign(&v27, v13);
      v9 = v27;
    }
    std::deque<ATL::CComPtr<IBackgroundCopyFile>>::pop_front(v12 + 48);
    if ( !*(_QWORD *)(v12 + 80) )
      std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Erase<std::wstring>(
        (char *)this + 672,
        v35);
  }
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v25);
  if ( !v9 )
    goto LABEL_28;
  v33 = 0;
  v34 = 0;
  v14 = ((__int64 (__fastcall *)(struct IUnknown *, __int128 *))v9->lpVtbl[1].Release)(v9, &v33);
  if ( v14 >= 0 )
  {
    if ( *((_QWORD *)&v33 + 1) == (_QWORD)v33 )
    {
      v25[0] = 0;
      v23 = 0;
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))v9->lpVtbl->QueryInterface)(
              v9,
              &GUID_85c1657f_dafc_40e8_8834_df18ea25717e,
              v25);
      if ( v16 < 0 )
      {
        v17 = 1023;
LABEL_12:
        v15 = ZTraceReportPropagation(v16, "MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob", v17, this);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
        goto LABEL_29;
      }
      v18 = v25[0];
      v19 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v25[0] + 64LL);
      if ( pv )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v28);
        CoTaskMemFree(pv);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v28);
      }
      pv = 0;
      v16 = v19(v18, &pv);
      if ( v16 < 0 )
      {
        v17 = 1024;
        goto LABEL_12;
      }
      v16 = FileExists((const unsigned __int16 *)pv, &v23);
      if ( v16 < 0 )
      {
        v17 = 1025;
        goto LABEL_12;
      }
      if ( v23 )
      {
        v10 = 1;
        if ( a3 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID *))(*(_QWORD *)v25[0] + 112LL))(v25[0], 1, &v26);
          if ( v16 < 0 )
          {
            v17 = 1032;
            goto LABEL_12;
          }
          ((void (__fastcall *)(LPVOID, _QWORD, LPVOID, void *, void *))a3)(pv, 0, v26, v30, v29);
        }
        v20 = (void (__fastcall *)(_QWORD, __int64, _QWORD))*((_QWORD *)this + 94);
        if ( v20 )
          v20(*((_QWORD *)this + 95), 1, v33);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
      v11 = v10;
    }
    else
    {
      v10 = 1;
    }
LABEL_28:
    v15 = 0;
    *v31 = v10;
    *v32 = v11;
    goto LABEL_29;
  }
  v15 = ZTraceReportPropagation(v14, "MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob", 1014, this);
LABEL_29:
  if ( pv && !DeleteFileW((LPCWSTR)pv) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    ZTraceReportIgnore(LastError, "MapsBackgroundTransferJob::CompleteRequestIfAlreadyPartOfJob", 1063, this);
  }
  CoTaskMemFree(v26);
  std::wstring::_Tidy_deallocate(v35);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  return v15;
}

```

## disassembly

```asm
0x18000c4dc  push    rbp
0x18000c4de  push    rbx
0x18000c4df  push    rsi
0x18000c4e0  push    rdi
0x18000c4e1  push    r12
0x18000c4e3  push    r13
0x18000c4e5  push    r14
0x18000c4e7  push    r15
0x18000c4e9  lea     rbp, [rsp-7]
0x18000c4ee  sub     rsp, 0D8h
0x18000c4f5  mov     rax, cs:__security_cookie
0x18000c4fc  xor     rax, rsp
0x18000c4ff  mov     [rbp+3Fh+var_48], rax
0x18000c503  mov     [rbp+3Fh+var_98], r9
0x18000c507  mov     r13, r8
0x18000c50a  mov     rsi, rcx
0x18000c50d  mov     rax, [rbp+3Fh+arg_20]
0x18000c511  mov     [rbp+3Fh+var_A0], rax
0x18000c515  mov     rax, [rbp+3Fh+arg_28]
0x18000c519  mov     [rbp+3Fh+var_90], rax
0x18000c51d  mov     rcx, [rbp+3Fh+arg_30]
0x18000c521  mov     [rbp+3Fh+var_88], rcx
0x18000c525  mov     [rsp+110h+var_C0], 0
0x18000c52e  mov     [rsp+110h+pv], 0
0x18000c537  xor     ebx, ebx
0x18000c539  mov     [rbp+3Fh+var_B8], rbx
0x18000c53d  xor     dil, dil
0x18000c540  xor     r15b, r15b
0x18000c543  mov     [rax], dil
0x18000c546  mov     [rcx], dil
0x18000c549  lea     rcx, [rbp+3Fh+var_68]
0x18000c54d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c552  nop
0x18000c553  lea     rdx, [rsi+310h]
0x18000c55a  lea     rcx, [rsp+110h+var_D0]
0x18000c55f  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18000c564  nop
0x18000c565  lea     r12, [rsi+2A0h]
0x18000c56c  lea     r8, [rbp+3Fh+var_68]
0x18000c570  lea     rdx, [rbp+3Fh+var_B0]
0x18000c574  mov     rcx, r12
0x18000c577  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::find(std::wstring const &)
0x18000c57c  mov     rcx, [rsi+2A8h]
0x18000c583  cmp     [rax], rcx
0x18000c586  jz      short loc_18000C5D6
0x18000c588  lea     r8, [rbp+3Fh+var_68]
0x18000c58c  lea     rdx, [rbp+3Fh+var_B0]
0x18000c590  mov     rcx, r12
0x18000c593  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18000c598  mov     r14, [rax]
0x18000c59b  lea     rcx, [r14+30h]
0x18000c59f  call    ?front@?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@std@@QEAAAEAV?$CComPtr@UIBackgroundCopyFile@@@ATL@@XZ; std::queue<ATL::CComPtr<IBackgroundCopyFile>>::front(void)
0x18000c5a4  mov     rdx, [rax]; struct IUnknown *
0x18000c5a7  test    rdx, rdx
0x18000c5aa  jz      short loc_18000C5B9
0x18000c5ac  lea     rcx, [rbp+3Fh+var_B8]; struct IUnknown **
0x18000c5b0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000c5b5  mov     rbx, [rbp+3Fh+var_B8]
0x18000c5b9  lea     rcx, [r14+30h]
0x18000c5bd  call    ?pop_front@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@QEAAXXZ; std::deque<ATL::CComPtr<IBackgroundCopyFile>>::pop_front(void)
0x18000c5c2  cmp     qword ptr [r14+50h], 0
0x18000c5c7  jnz     short loc_18000C5D6
0x18000c5c9  lea     rdx, [rbp+3Fh+var_68]
0x18000c5cd  mov     rcx, r12
0x18000c5d0  call    ??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Erase<std::wstring>(std::wstring const &)
0x18000c5d5  nop
0x18000c5d6  lea     rcx, [rsp+110h+var_D0]
0x18000c5db  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000c5e0  lea     r12, aMapsbackground_25; "MapsBackgroundTransferJob::CompleteRequ"...
0x18000c5e7  test    rbx, rbx
0x18000c5ea  jz      loc_18000C78F
0x18000c5f0  xorps   xmm0, xmm0
0x18000c5f3  xor     eax, eax
0x18000c5f5  movups  [rbp+3Fh+var_80], xmm0
0x18000c5f9  mov     [rbp+3Fh+var_70], rax
0x18000c5fd  mov     rax, [rbx]
0x18000c600  lea     rdx, [rbp+3Fh+var_80]
0x18000c604  mov     rcx, rbx
0x18000c607  mov     rax, [rax+28h]
0x18000c60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c610  test    eax, eax
0x18000c612  jns     short loc_18000C62F
0x18000c614  mov     r9, rsi
0x18000c617  mov     r8d, 3F6h
0x18000c61d  mov     rdx, r12
0x18000c620  mov     ecx, eax
0x18000c622  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000c628  mov     ebx, eax
0x18000c62a  jmp     loc_18000C79F
0x18000c62f  mov     rax, qword ptr [rbp+3Fh+var_80]
0x18000c633  cmp     qword ptr [rbp+3Fh+var_80+8], rax
0x18000c637  jnz     loc_18000C78A
0x18000c63d  mov     [rsp+110h+var_D0], 0
0x18000c646  mov     [rsp+110h+var_E0], 0
0x18000c64b  mov     rax, [rbx]
0x18000c64e  lea     r8, [rsp+110h+var_D0]
0x18000c653  lea     rdx, _GUID_85c1657f_dafc_40e8_8834_df18ea25717e
0x18000c65a  mov     rcx, rbx
0x18000c65d  mov     rax, [rax]
0x18000c660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c665  nop
0x18000c666  test    eax, eax
0x18000c668  jns     short loc_18000C68F
0x18000c66a  mov     r8d, 3FFh
0x18000c670  mov     r9, rsi
0x18000c673  mov     rdx, r12
0x18000c676  mov     ecx, eax
0x18000c678  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000c67e  mov     ebx, eax
0x18000c680  lea     rcx, [rsp+110h+var_D0]
0x18000c685  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c68a  jmp     loc_18000C79F
0x18000c68f  mov     r14, [rsp+110h+var_D0]
0x18000c694  mov     rax, [r14]
0x18000c697  mov     r15, [rax+40h]
0x18000c69b  mov     rbx, [rsp+110h+pv]
0x18000c6a0  test    rbx, rbx
0x18000c6a3  jz      short loc_18000C6C0
0x18000c6a5  lea     rcx, [rbp+3Fh+var_B0]; this
0x18000c6a9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000c6ae  mov     rcx, rbx; pv
0x18000c6b1  call    cs:__imp_CoTaskMemFree
0x18000c6b7  lea     rcx, [rbp+3Fh+var_B0]; this
0x18000c6bb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000c6c0  mov     [rsp+110h+pv], 0
0x18000c6c9  lea     rdx, [rsp+110h+pv]
0x18000c6ce  mov     rcx, r14
0x18000c6d1  mov     rax, r15
0x18000c6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6d9  test    eax, eax
0x18000c6db  jns     short loc_18000C6E5
0x18000c6dd  mov     r8d, 400h
0x18000c6e3  jmp     short loc_18000C670
0x18000c6e5  lea     rdx, [rsp+110h+var_E0]; bool *
0x18000c6ea  mov     rcx, [rsp+110h+pv]; unsigned __int16 *
0x18000c6ef  call    ?FileExists@@YAJPEBGPEA_N@Z; FileExists(ushort const *,bool *)
0x18000c6f4  test    eax, eax
0x18000c6f6  jns     short loc_18000C703
0x18000c6f8  mov     r8d, 401h
0x18000c6fe  jmp     loc_18000C670
0x18000c703  cmp     [rsp+110h+var_E0], 0
0x18000c708  jz      short loc_18000C77B
0x18000c70a  mov     edi, 1
0x18000c70f  test    r13, r13
0x18000c712  jz      short loc_18000C75C
0x18000c714  mov     rcx, [rsp+110h+var_D0]
0x18000c719  mov     rax, [rcx]
0x18000c71c  lea     r8, [rsp+110h+var_C0]
0x18000c721  mov     edx, edi
0x18000c723  mov     rax, [rax+70h]
0x18000c727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c72c  test    eax, eax
0x18000c72e  jns     short loc_18000C73B
0x18000c730  mov     r8d, 408h
0x18000c736  jmp     loc_18000C670
0x18000c73b  mov     rax, [rbp+3Fh+var_A0]
0x18000c73f  mov     [rsp+110h+var_F0], rax
0x18000c744  mov     r9, [rbp+3Fh+var_98]
0x18000c748  mov     r8, [rsp+110h+var_C0]
0x18000c74d  xor     edx, edx
0x18000c74f  mov     rcx, [rsp+110h+pv]
0x18000c754  mov     rax, r13
0x18000c757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c75c  mov     rax, [rsi+2F0h]
0x18000c763  test    rax, rax
0x18000c766  jz      short loc_18000C77B
0x18000c768  mov     r8, qword ptr [rbp+3Fh+var_80]
0x18000c76c  mov     edx, edi
0x18000c76e  mov     rcx, [rsi+2F8h]
0x18000c775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c77a  nop
0x18000c77b  lea     rcx, [rsp+110h+var_D0]
0x18000c780  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c785  mov     r15b, dil
0x18000c788  jmp     short loc_18000C78F
0x18000c78a  mov     edi, 1
0x18000c78f  xor     ebx, ebx
0x18000c791  mov     rax, [rbp+3Fh+var_90]
0x18000c795  mov     [rax], dil
0x18000c798  mov     rax, [rbp+3Fh+var_88]
0x18000c79c  mov     [rax], r15b
0x18000c79f  mov     rcx, [rsp+110h+pv]; lpFileName
0x18000c7a4  test    rcx, rcx
0x18000c7a7  jz      short loc_18000C7E2
0x18000c7a9  call    cs:__imp_DeleteFileW
0x18000c7af  test    eax, eax
0x18000c7b1  jnz     short loc_18000C7E2
0x18000c7b3  call    cs:__imp_GetLastError
0x18000c7b9  test    eax, eax
0x18000c7bb  jz      short loc_18000C7C9
0x18000c7bd  jle     short loc_18000C7CE
0x18000c7bf  movzx   eax, ax
0x18000c7c2  or      eax, 80070000h
0x18000c7c7  jmp     short loc_18000C7CE
0x18000c7c9  mov     eax, 80390004h
0x18000c7ce  mov     r9, rsi
0x18000c7d1  mov     r8d, 427h
0x18000c7d7  mov     rdx, r12
0x18000c7da  mov     ecx, eax
0x18000c7dc  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000c7e2  mov     rcx, [rsp+110h+var_C0]; pv
0x18000c7e7  call    cs:__imp_CoTaskMemFree
0x18000c7ed  nop
0x18000c7ee  lea     rcx, [rbp+3Fh+var_68]
0x18000c7f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c7f7  nop
0x18000c7f8  lea     rcx, [rbp+3Fh+var_B8]
0x18000c7fc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000c801  nop
0x18000c802  lea     rcx, [rsp+110h+pv]
0x18000c807  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c80c  mov     eax, ebx
0x18000c80e  mov     rcx, [rbp+3Fh+var_48]
0x18000c812  xor     rcx, rsp; StackCookie
0x18000c815  call    __security_check_cookie
0x18000c81a  add     rsp, 0D8h
0x18000c821  pop     r15
0x18000c823  pop     r14
0x18000c825  pop     r13
0x18000c827  pop     r12
0x18000c829  pop     rdi
0x18000c82a  pop     rsi
0x18000c82b  pop     rbx
0x18000c82c  pop     rbp
0x18000c82d  retn
```
