# DusmWwan::UpdateConnectionList(void)

- ea: `0x18003b814`
- end: `0x18003be15`
- name: `?UpdateConnectionList@DusmWwan@@AEBAXXZ`
- size: `1537`
- prototype: `void __fastcall(DusmWwan *__hidden this)`
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003b56c`
- `0x18003c1c0`

## callees

- `0x180001234`
- `0x1800021e4`
- `0x180006c38`
- `0x180006ccc`
- `0x180007c90`
- `0x180008704`
- `0x18000e474`
- `0x18000e6e4`
- `0x18000e828`
- `0x18000ee34`
- `0x18000f094`
- `0x18000f214`
- `0x180012368`
- `0x180013114`
- `0x180013444`
- `0x180017cec`
- `0x180018050`
- `0x180018080`
- `0x18001db50`
- `0x18002f510`
- `0x1800394b8`
- `0x18003968c`
- `0x180039774`
- `0x1800397b4`
- `0x18003a084`
- `0x18003a1e4`
- `0x18003ad84`
- `0x18003adf0`
- `0x18003b814`
- `0x18003be1c`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b855`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b855`
- `wwapi!WwanEnumerateInterfaces` at `0x18003b8a5`
- `wwapi!WwanEnumerateInterfaces` at `0x18003b8a5`
- `wwapi!WwanGetProfileList` at `0x18003bb79`
- `wwapi!WwanGetProfileList` at `0x18003bb79`
- `wwapi!WwanFreeMemory` at `0x18003bda6`
- `wwapi!WwanFreeMemory` at `0x18003bdc0`
- `wwapi!WwanFreeMemory` at `0x18003bdec`
- `wwapi!WwanFreeMemory` at `0x18003bda6`
- `wwapi!WwanFreeMemory` at `0x18003bdc0`
- `wwapi!WwanFreeMemory` at `0x18003bdec`

## string_xrefs

- `0x18003b8b5`: `DusmWwan::UpdateConnectionList::WwanEnumerateInterfaces`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall DusmWwan::UpdateConnectionList(DusmWwan *this)
{
  char *v2; // rbx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  __int64 *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  int *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int i; // r15d
  _DWORD *v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rdi
  struct _GUID *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // rcx
  _DWORD *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rax
  int *v27; // rdx
  __int64 v28; // rdx
  __int64 *v29; // rcx
  __int64 v30; // rcx
  int ProfileList; // ebx
  __int64 v32; // rdx
  __int64 v33; // rcx
  _DWORD *v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  const wchar_t *v37; // rbx
  __int64 v38; // rdi
  __int64 v39; // rdx
  _DWORD *v40; // rdx
  __int64 v41; // r8
  _DWORD *v42; // rdx
  __int64 v43; // r8
  _DWORD *v44; // rcx
  __int64 v45; // r9
  __int64 v46; // r8
  const WCHAR *v47; // rcx
  _DWORD *v48; // rcx
  const char *v49; // [rsp+28h] [rbp-D8h]
  int v50; // [rsp+40h] [rbp-C0h] BYREF
  struct _GUID *v51; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v52; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v53; // [rsp+58h] [rbp-A8h] BYREF
  char *v54; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v55; // [rsp+68h] [rbp-98h] BYREF
  __int64 v56; // [rsp+70h] [rbp-90h] BYREF
  char v57; // [rsp+78h] [rbp-88h]
  const WCHAR **v58; // [rsp+80h] [rbp-80h] BYREF
  __int64 v59; // [rsp+88h] [rbp-78h] BYREF
  char v60; // [rsp+90h] [rbp-70h]
  struct _GUID v61; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+C8h] [rbp-38h]
  __int128 v65; // [rsp+D0h] [rbp-30h]
  __int64 v66; // [rsp+E0h] [rbp-20h]
  __int64 v67; // [rsp+E8h] [rbp-18h]
  __int128 v68; // [rsp+F0h] [rbp-10h]
  __int64 v69; // [rsp+100h] [rbp+0h]
  __int64 v70; // [rsp+108h] [rbp+8h]
  int v71; // [rsp+110h] [rbp+10h]
  _BYTE v72[56]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v73; // [rsp+158h] [rbp+58h]
  struct _GUID v74; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v75[64]; // [rsp+170h] [rbp+70h] BYREF
  int *v76; // [rsp+1B0h] [rbp+B0h] BYREF
  const WCHAR *v77; // [rsp+1B8h] [rbp+B8h] BYREF
  _DWORD *v78; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v79[8]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v80[112]; // [rsp+210h] [rbp+110h] BYREF
  char v81[32]; // [rsp+280h] [rbp+180h] BYREF
  char v82[176]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v78 = 0;
  v2 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v54 = v2;
  v4 = (_QWORD *)*((_QWORD *)this + 8);
  if ( !v4 || *v4 == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3);
  v55 = (__int64 *)&v78;
  v56 = 0;
  v57 = 1;
  v5 = (__int64 *)*((_QWORD *)this + 8);
  if ( v5 )
    v6 = *v5;
  else
    v6 = -1;
  v7 = WwanEnumerateInterfaces(v6, 0, &v56);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xDE,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
    (const char *)v7,
    (unsigned int)"DusmWwan::UpdateConnectionList::WwanEnumerateInterfaces",
    v49);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v55);
  v11 = *(int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v9, v8) + 8);
  if ( (unsigned int)*v11 > 5 )
  {
    v50 = *v78;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)v11,
      (int)&byte_18005B207,
      v12,
      v13,
      (__int64)&v50);
  }
  for ( i = 0; ; ++i )
  {
    v15 = v78;
    v16 = v78 ? *v78 : 0;
    if ( i >= v16 )
      break;
    v17 = 147LL * i;
    if ( v78[v17 + 139] )
    {
      v11 = *(int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v11, v10) + 8);
      if ( (unsigned int)*v11 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (int)v11,
          (int)&word_18005B186);
    }
    else
    {
      v18 = (struct _GUID *)&v78[v17 + 1];
      if ( (unsigned int)DusmWwan::IsWwanSimInserted(this, v18) )
      {
        v21 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v20, v19) + 8);
        if ( *v21 > 4u )
        {
          v52 = (int)v15[v17 + 134];
          v50 = v15[v17 + 133];
          v51 = (struct _GUID *)&v15[v17 + 1];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (int)v21,
            (int)byte_18005B0A5,
            v22,
            v23,
            (__int64 *)&v51,
            (__int64)&v50,
            (__int64)&v52);
        }
        DusmWwan::QueryWwanSubscriberInfo(v21, &v76, &v15[v17 + 1]);
        v24 = std::wstring::wstring((__int64)v79, (__int64)&v15[v17 + 5]);
        v25 = std::wstring::wstring((__int64)v72, (__int64)(v76 + 10));
        v26 = std::wstring::wstring((__int64)&v58, (__int64)(v76 + 2));
        v27 = v76;
        v61 = *v18;
        v62 = 0;
        v62 = *(_OWORD *)v24;
        v63 = *(_QWORD *)(v24 + 16);
        v64 = *(_QWORD *)(v24 + 24);
        *(_QWORD *)(v24 + 24) = 7;
        *(_WORD *)v24 = 0;
        *(_QWORD *)(v24 + 16) = 0;
        v65 = 0;
        v65 = *(_OWORD *)v25;
        v66 = *(_QWORD *)(v25 + 16);
        v67 = *(_QWORD *)(v25 + 24);
        *(_QWORD *)(v25 + 24) = 7;
        *(_WORD *)v25 = 0;
        *(_QWORD *)(v25 + 16) = 0;
        v68 = 0;
        v68 = *(_OWORD *)v26;
        v69 = *(_QWORD *)(v26 + 16);
        v70 = *(_QWORD *)(v26 + 24);
        *(_WORD *)v26 = 0;
        *(_QWORD *)(v26 + 16) = 0;
        *(_QWORD *)(v26 + 24) = 7;
        v71 = *v27;
        std::function_void___cdecl_void__::function_void___cdecl_void____DusmWwan::UpdateConnectionList_::_9_::_lambda_1__0_(
          &v74,
          &v61);
        DusmAsync::SubmitOrderedWork((__int64)&v74);
        std::function<long (void)>::~function<long (void)>((__int64)&v74, v28);
        DusmWwan::UpdateConnectionList_::_9_::_lambda_1_::__lambda_1_(&v61);
        std::wstring::_Tidy_deallocate(&v58);
        std::wstring::_Tidy_deallocate(v72);
        std::wstring::_Tidy_deallocate(v79);
        v77 = 0;
        v58 = &v77;
        v59 = 0;
        v60 = 1;
        v29 = (__int64 *)*((_QWORD *)this + 8);
        if ( v29 )
          v30 = *v29;
        else
          v30 = -1;
        ProfileList = WwanGetProfileList(v30, v18, 0, &v59);
        wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>((__int64 **)&v58);
        if ( ProfileList )
        {
          v34 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v33, v32) + 8);
          if ( *v34 > 5u )
          {
            LODWORD(v51) = ProfileList;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (int)v34,
              (int)&word_18005B136,
              v35,
              v36,
              (__int64)&v51);
          }
        }
        else if ( *(_DWORD *)v77 )
        {
          memset_0(v79, 0, sizeof(v79));
          std::unordered_set<unsigned long>::unordered_set<unsigned long>(v79);
          v37 = v77 + 2;
          v38 = (__int64)&v77[258 * *(unsigned int *)v77 + 2];
          while ( v37 != (const wchar_t *)v38 )
          {
            LODWORD(v51) = QueryProfileIndexImpl(v18, v37);
            std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::emplace<unsigned long const &>(
              v79,
              (__int64)&v55,
              (unsigned __int8 *)&v51);
            v37 += 258;
          }
          v74 = *v18;
          std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>(
            (__int64)v75,
            (__int64)v79);
          v73 = 0;
          v73 = std::_Global_new_std::_Func_impl_no_alloc__DusmWwan::UpdateConnectionList_::_43_::_lambda_2__void___DusmWwan::UpdateConnectionList_::_43_::_lambda_2___(&v74);
          DusmAsync::SubmitOrderedWork((__int64)v72);
          std::function<long (void)>::~function<long (void)>((__int64)v72, v39);
          std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>((__int64)v75);
          if ( *v76 == 1 )
          {
            memset_0(v80, 0, 0x140u);
            DusmConnection::DusmConnection((__int64)v80, v18, v77 + 2, 3, 0);
            v40 = v76 + 10;
            v41 = -1;
            do
              ++v41;
            while ( *((_WORD *)v40 + v41) );
            std::wstring::_Assign<wchar_t>(v82, v40, v41);
            v42 = v76 + 2;
            v43 = -1;
            do
              ++v43;
            while ( *((_WORD *)v42 + v43) );
            std::wstring::_Assign<wchar_t>(v81, v42, v43);
            DusmWwan::MigrateCostSetting(this, (const struct DusmConnection *)v80);
            DusmConnection::~DusmConnection((DusmConnection *)v80);
          }
          std::_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>::~_Hash<std::_Uset_traits<unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<unsigned long>,0>>((__int64)v79);
        }
        else
        {
          v44 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v33, v32) + 8);
          if ( *v44 > 3u )
          {
            v46 = *(unsigned int *)v77;
            v53 = v46;
            v51 = v18;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
              (int)v44,
              (int)&byte_18005AFDF,
              v46,
              v45,
              (__int64 *)&v51,
              (__int64)&v53);
          }
        }
        DusmWwan::UpdateConnectionStatesAndNotifyNLM(this, v18, 10);
        v47 = v77;
        v77 = 0;
        if ( v47 )
          WwanFreeMemory(v47);
        v11 = v76;
        v76 = 0;
        if ( v11 )
          WwanFreeMemory(v11);
      }
      else
      {
        v11 = *(int **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v20, v19) + 8);
        if ( (unsigned int)*v11 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            (int)v11,
            (int)&word_18005B1C6);
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v54);
  v48 = v78;
  v78 = 0;
  if ( v48 )
    WwanFreeMemory(v48);
}

```

## disassembly

```asm
0x18003b814  push    rbp
0x18003b816  push    rbx
0x18003b817  push    rsi
0x18003b818  push    rdi
0x18003b819  push    r12
0x18003b81b  push    r13
0x18003b81d  push    r14
0x18003b81f  push    r15
0x18003b821  lea     rbp, [rsp-268h]
0x18003b829  sub     rsp, 368h
0x18003b830  mov     rax, cs:__security_cookie
0x18003b837  xor     rax, rsp
0x18003b83a  mov     [rbp+2A0h+var_50], rax
0x18003b841  mov     r14, rcx
0x18003b844  xor     r12d, r12d
0x18003b847  mov     [rbp+2A0h+var_1E0], r12
0x18003b84e  lea     rbx, [rcx+18h]
0x18003b852  mov     rcx, rbx; lpCriticalSection
0x18003b855  call    cs:__imp_EnterCriticalSection
0x18003b85b  mov     [rsp+3A0h+var_340], rbx
0x18003b860  mov     rax, [r14+40h]
0x18003b864  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003b868  test    rax, rax
0x18003b86b  jz      short loc_18003B872
0x18003b86d  cmp     [rax], r13
0x18003b870  jnz     short loc_18003B877
0x18003b872  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b877  lea     rax, [rbp+2A0h+var_1E0]
0x18003b87e  mov     [rsp+3A0h+var_338], rax
0x18003b883  mov     [rsp+3A0h+var_330], r12
0x18003b888  mov     [rsp+3A0h+var_328], 1
0x18003b88d  mov     rax, [r14+40h]
0x18003b891  test    rax, rax
0x18003b894  jz      short loc_18003B89B
0x18003b896  mov     rcx, [rax]
0x18003b899  jmp     short loc_18003B89E
0x18003b89b  mov     rcx, r13
0x18003b89e  lea     r8, [rsp+3A0h+var_330]
0x18003b8a3  xor     edx, edx
0x18003b8a5  call    cs:__imp_WwanEnumerateInterfaces
0x18003b8ab  mov     r9d, eax; char *
0x18003b8ae  mov     rcx, [rbp+2A8h]; this
0x18003b8b5  lea     rax, aDusmwwanUpdate_0; "DusmWwan::UpdateConnectionList::WwanEnu"...
0x18003b8bc  mov     qword ptr [rsp+3A0h+var_380], rax; unsigned int
0x18003b8c1  lea     r8, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003b8c8  mov     edx, 0DEh; void *
0x18003b8cd  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003b8d2  nop
0x18003b8d3  lea     rcx, [rsp+3A0h+var_338]
0x18003b8d8  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@UWWAN_INTERFACE_OBJECT@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18003b8dd  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b8e2  mov     rcx, [rax+8]
0x18003b8e6  mov     eax, [rcx]
0x18003b8e8  cmp     eax, 5
0x18003b8eb  jbe     short loc_18003B910
0x18003b8ed  mov     rax, [rbp+2A0h+var_1E0]
0x18003b8f4  mov     edx, [rax]
0x18003b8f6  mov     [rsp+3A0h+var_360], edx
0x18003b8fa  lea     rax, [rsp+3A0h+var_360]
0x18003b8ff  mov     qword ptr [rsp+3A0h+var_380], rax
0x18003b904  lea     rdx, byte_18005B207
0x18003b90b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003b910  mov     r15d, r12d
0x18003b913  mov     rbx, [rbp+2A0h+var_1E0]
0x18003b91a  test    rbx, rbx
0x18003b91d  jz      short loc_18003B923
0x18003b91f  mov     eax, [rbx]
0x18003b921  jmp     short loc_18003B926
0x18003b923  mov     eax, r12d
0x18003b926  cmp     r15d, eax
0x18003b929  jnb     loc_18003BDCE
0x18003b92f  mov     eax, r15d
0x18003b932  imul    rdi, rax, 24Ch
0x18003b939  cmp     [rdi+rbx+22Ch], r12d
0x18003b941  jz      short loc_18003B968
0x18003b943  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b948  mov     rcx, [rax+8]
0x18003b94c  mov     eax, [rcx]
0x18003b94e  cmp     eax, 5
0x18003b951  jbe     loc_18003BDC6
0x18003b957  lea     rdx, word_18005B186
0x18003b95e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003b963  jmp     loc_18003BDC6
0x18003b968  lea     rsi, [rbx+4]
0x18003b96c  add     rsi, rdi
0x18003b96f  mov     rdx, rsi; struct _GUID *
0x18003b972  mov     rcx, r14; this
0x18003b975  call    ?IsWwanSimInserted@DusmWwan@@AEBAHAEBU_GUID@@@Z; DusmWwan::IsWwanSimInserted(_GUID const &)
0x18003b97a  test    eax, eax
0x18003b97c  jnz     short loc_18003B9A3
0x18003b97e  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b983  mov     rcx, [rax+8]
0x18003b987  mov     eax, [rcx]
0x18003b989  cmp     eax, 5
0x18003b98c  jbe     loc_18003BDC6
0x18003b992  lea     rdx, word_18005B1C6
0x18003b999  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003b99e  jmp     loc_18003BDC6
0x18003b9a3  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003b9a8  mov     rcx, [rax+8]
0x18003b9ac  mov     eax, [rcx]
0x18003b9ae  cmp     eax, 4
0x18003b9b1  jbe     short loc_18003B9FA
0x18003b9b3  movsxd  rax, dword ptr [rdi+rbx+218h]
0x18003b9bb  mov     [rsp+3A0h+var_350], rax
0x18003b9c0  mov     eax, [rdi+rbx+214h]
0x18003b9c7  mov     [rsp+3A0h+var_360], eax
0x18003b9cb  mov     [rsp+3A0h+var_358], rsi
0x18003b9d0  lea     rax, [rsp+3A0h+var_350]
0x18003b9d5  mov     [rsp+3A0h+var_370], rax
0x18003b9da  lea     rax, [rsp+3A0h+var_360]
0x18003b9df  mov     [rsp+3A0h+var_378], rax
0x18003b9e4  lea     rax, [rsp+3A0h+var_358]
0x18003b9e9  mov     qword ptr [rsp+3A0h+var_380], rax
0x18003b9ee  lea     rdx, byte_18005B0A5
0x18003b9f5  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003b9fa  mov     r8, rsi
0x18003b9fd  lea     rdx, [rbp+2A0h+var_1F0]
0x18003ba04  call    ?QueryWwanSubscriberInfo@DusmWwan@@AEBA?AV?$unique_ptr@UWWAN_SUBSCRIBER_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@AEBU_GUID@@@Z; DusmWwan::QueryWwanSubscriberInfo(_GUID const &)
0x18003ba09  nop
0x18003ba0a  lea     rdx, [rbx+14h]
0x18003ba0e  add     rdx, rdi
0x18003ba11  lea     rcx, [rbp+2A0h+var_1D0]
0x18003ba18  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003ba1d  mov     rbx, rax
0x18003ba20  mov     rdx, [rbp+2A0h+var_1F0]
0x18003ba27  add     rdx, 28h ; '('
0x18003ba2b  lea     rcx, [rbp+2A0h+var_280]
0x18003ba2f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003ba34  mov     rdi, rax
0x18003ba37  mov     rdx, [rbp+2A0h+var_1F0]
0x18003ba3e  add     rdx, 8
0x18003ba42  lea     rcx, [rbp+2A0h+var_320]
0x18003ba46  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003ba4b  mov     r8, rax
0x18003ba4e  mov     rdx, [rbp+2A0h+var_1F0]
0x18003ba55  movups  xmm0, xmmword ptr [rsi]
0x18003ba58  movdqu  [rbp+2A0h+var_300], xmm0
0x18003ba5d  xorps   xmm1, xmm1
0x18003ba60  movups  [rbp+2A0h+var_2F0], xmm1
0x18003ba64  mov     rcx, [rbx]
0x18003ba67  mov     qword ptr [rbp+2A0h+var_2F0], rcx
0x18003ba6b  mov     rcx, [rbx+8]
0x18003ba6f  mov     qword ptr [rbp+2A0h+var_2F0+8], rcx
0x18003ba73  mov     rcx, [rbx+10h]
0x18003ba77  mov     [rbp+2A0h+var_2E0], rcx
0x18003ba7b  mov     rax, [rbx+18h]
0x18003ba7f  mov     [rbp+2A0h+var_2D8], rax
0x18003ba83  mov     ecx, 7
0x18003ba88  mov     [rbx+18h], rcx
0x18003ba8c  mov     [rbx], r12w
0x18003ba90  mov     [rbx+10h], r12
0x18003ba94  xorps   xmm0, xmm0
0x18003ba97  movups  [rbp+2A0h+var_2D0], xmm0
0x18003ba9b  mov     rax, [rdi]
0x18003ba9e  mov     qword ptr [rbp+2A0h+var_2D0], rax
0x18003baa2  mov     rax, [rdi+8]
0x18003baa6  mov     qword ptr [rbp+2A0h+var_2D0+8], rax
0x18003baaa  mov     rax, [rdi+10h]
0x18003baae  mov     [rbp+2A0h+var_2C0], rax
0x18003bab2  mov     rax, [rdi+18h]
0x18003bab6  mov     [rbp+2A0h+var_2B8], rax
0x18003baba  mov     [rdi+18h], rcx
0x18003babe  mov     [rdi], r12w
0x18003bac2  mov     [rdi+10h], r12
0x18003bac6  movups  [rbp+2A0h+var_2B0], xmm0
0x18003baca  mov     rax, [r8]
0x18003bacd  mov     qword ptr [rbp+2A0h+var_2B0], rax
0x18003bad1  mov     rax, [r8+8]
0x18003bad5  mov     qword ptr [rbp+2A0h+var_2B0+8], rax
0x18003bad9  mov     rax, [r8+10h]
0x18003badd  mov     [rbp+2A0h+var_2A0], rax
0x18003bae1  mov     rax, [r8+18h]
0x18003bae5  mov     [rbp+2A0h+var_298], rax
0x18003bae9  mov     [r8], r12w
0x18003baed  mov     [r8+10h], r12
0x18003baf1  mov     [r8+18h], rcx
0x18003baf5  mov     eax, [rdx]
0x18003baf7  mov     [rbp+2A0h+var_290], eax
0x18003bafa  lea     rdx, [rbp+2A0h+var_300]
0x18003bafe  lea     rcx, [rbp+2A0h+var_240]
0x18003bb02  call    std__function_void___cdecl_void____function_void___cdecl_void____DusmWwan__UpdateConnectionList____9____lambda_1__0_
0x18003bb07  lea     rcx, [rbp+2A0h+var_240]
0x18003bb0b  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x18003bb10  lea     rcx, [rbp+2A0h+var_240]
0x18003bb14  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18003bb19  nop
0x18003bb1a  lea     rcx, [rbp+2A0h+var_300]
0x18003bb1e  call    _DusmWwan__UpdateConnectionList____9____lambda_1_____lambda_1_
0x18003bb23  nop
0x18003bb24  lea     rcx, [rbp+2A0h+var_320]
0x18003bb28  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bb2d  nop
0x18003bb2e  lea     rcx, [rbp+2A0h+var_280]
0x18003bb32  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bb37  nop
0x18003bb38  lea     rcx, [rbp+2A0h+var_1D0]
0x18003bb3f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bb44  mov     [rbp+2A0h+var_1E8], r12
0x18003bb4b  lea     rax, [rbp+2A0h+var_1E8]
0x18003bb52  mov     [rbp+2A0h+var_320], rax
0x18003bb56  mov     [rbp+2A0h+var_318], r12
0x18003bb5a  mov     [rbp+2A0h+var_310], 1
0x18003bb5e  mov     rcx, [r14+40h]
0x18003bb62  test    rcx, rcx
0x18003bb65  jz      short loc_18003BB6C
0x18003bb67  mov     rcx, [rcx]
0x18003bb6a  jmp     short loc_18003BB6F
0x18003bb6c  mov     rcx, r13
0x18003bb6f  lea     r9, [rbp+2A0h+var_318]
0x18003bb73  xor     r8d, r8d
0x18003bb76  mov     rdx, rsi
0x18003bb79  call    cs:__imp_WwanGetProfileList
0x18003bb7f  mov     ebx, eax
0x18003bb81  lea     rcx, [rbp+2A0h+var_320]
0x18003bb85  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@UWWAN_INTERFACE_OBJECT@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18003bb8a  test    ebx, ebx
0x18003bb8c  jz      short loc_18003BBC1
0x18003bb8e  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003bb93  mov     rcx, [rax+8]
0x18003bb97  mov     edx, [rcx]
0x18003bb99  cmp     edx, 5
0x18003bb9c  jbe     loc_18003BD81
0x18003bba2  mov     dword ptr [rsp+3A0h+var_358], ebx
0x18003bba6  lea     rax, [rsp+3A0h+var_358]
0x18003bbab  mov     qword ptr [rsp+3A0h+var_380], rax
0x18003bbb0  lea     rdx, word_18005B136
0x18003bbb7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003bbbc  jmp     loc_18003BD81
0x18003bbc1  mov     rax, [rbp+2A0h+var_1E8]
0x18003bbc8  cmp     [rax], r12d
0x18003bbcb  jbe     loc_18003BD3D
0x18003bbd1  xor     edx, edx; Val
0x18003bbd3  lea     r8d, [rdx+40h]; Size
0x18003bbd7  lea     rcx, [rbp+2A0h+var_1D0]; void *
0x18003bbde  call    memset_0
0x18003bbe3  lea     rcx, [rbp+2A0h+var_1D0]
0x18003bbea  call    ??0?$unordered_set@KU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@K@2@@std@@QEAA@XZ; std::unordered_set<ulong>::unordered_set<ulong>(void)
0x18003bbef  nop
0x18003bbf0  mov     rax, [rbp+2A0h+var_1E8]
0x18003bbf7  lea     rbx, [rax+4]
0x18003bbfb  mov     ecx, [rax]
0x18003bbfd  imul    rdi, rcx, 204h
0x18003bc04  add     rdi, rbx
0x18003bc07  jmp     short loc_18003BC35
0x18003bc09  mov     rdx, rbx; wchar_t *
0x18003bc0c  mov     rcx, rsi; struct _GUID *
0x18003bc0f  call    ?QueryProfileIndexImpl@@YAKAEBU_GUID@@PEB_W@Z; QueryProfileIndexImpl(_GUID const &,wchar_t const *)
0x18003bc14  mov     dword ptr [rsp+3A0h+var_358], eax
0x18003bc18  lea     r8, [rsp+3A0h+var_358]
0x18003bc1d  lea     rdx, [rsp+3A0h+var_338]
0x18003bc22  lea     rcx, [rbp+2A0h+var_1D0]
0x18003bc29  call    ??$emplace@AEBK@?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@@std@@_N@1@AEBK@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::emplace<ulong const &>(ulong const &)
0x18003bc2e  add     rbx, 204h
0x18003bc35  cmp     rbx, rdi
0x18003bc38  jnz     short loc_18003BC09
0x18003bc3a  movups  xmm0, xmmword ptr [rsi]
0x18003bc3d  movdqu  [rbp+2A0h+var_240], xmm0
0x18003bc42  lea     rdx, [rbp+2A0h+var_1D0]
0x18003bc49  lea     rcx, [rbp+2A0h+var_230]
0x18003bc4d  call    ??0?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>> &&)
0x18003bc52  nop
0x18003bc53  mov     [rbp+2A0h+var_248], r12
0x18003bc57  lea     rcx, [rbp+2A0h+var_240]
0x18003bc5b  call    std___Global_new_std___Func_impl_no_alloc__DusmWwan__UpdateConnectionList____43____lambda_2__void___DusmWwan__UpdateConnectionList____43____lambda_2___
0x18003bc60  mov     [rbp+2A0h+var_248], rax
0x18003bc64  lea     rcx, [rbp+2A0h+var_280]
0x18003bc68  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x18003bc6d  lea     rcx, [rbp+2A0h+var_280]
0x18003bc71  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18003bc76  nop
0x18003bc77  lea     rcx, [rbp+2A0h+var_230]
0x18003bc7b  call    ??1?$_Hash@V?$_Uset_traits@KV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>::~_Hash<std::_Uset_traits<ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<ulong>,0>>(void)
0x18003bc80  mov     rax, [rbp+2A0h+var_1F0]
0x18003bc87  cmp     dword ptr [rax], 1
0x18003bc8a  jnz     loc_18003BD2F
0x18003bc90  xor     edx, edx; Val
0x18003bc92  mov     r8d, 140h; Size
0x18003bc98  lea     rcx, [rbp+2A0h+var_190]; void *
0x18003bc9f  call    memset_0
0x18003bca4  mov     r8, [rbp+2A0h+var_1E8]
0x18003bcab  add     r8, 4
0x18003bcaf  mov     qword ptr [rsp+3A0h+var_380], r12
0x18003bcb4  mov     r9d, 3
0x18003bcba  mov     rdx, rsi
0x18003bcbd  lea     rcx, [rbp+2A0h+var_190]
0x18003bcc4  call    ??0DusmConnection@@QEAA@PEBU_GUID@@PEB_WW4_DUSM_MEDIA_TYPE@@1@Z; DusmConnection::DusmConnection(_GUID const *,wchar_t const *,_DUSM_MEDIA_TYPE,wchar_t const *)
0x18003bcc9  nop
0x18003bcca  mov     rdx, [rbp+2A0h+var_1F0]
0x18003bcd1  add     rdx, 28h ; '('
0x18003bcd5  mov     r8, r13
0x18003bcd8  inc     r8
0x18003bcdb  cmp     [rdx+r8*2], r12w
0x18003bce0  jnz     short loc_18003BCD8
0x18003bce2  lea     rcx, [rbp+2A0h+var_100]
0x18003bce9  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003bcee  mov     rdx, [rbp+2A0h+var_1F0]
0x18003bcf5  add     rdx, 8
0x18003bcf9  mov     r8, r13
0x18003bcfc  inc     r8
  ... truncated ...
```
