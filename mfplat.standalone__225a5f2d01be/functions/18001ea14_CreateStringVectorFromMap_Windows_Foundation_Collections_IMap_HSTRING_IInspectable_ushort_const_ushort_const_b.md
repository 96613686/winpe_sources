# CreateStringVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,bool,Windows::Foundation::Collections::IVector<HSTRING__ *> * *)

- ea: `0x18001ea14`
- end: `0x18001f3a4`
- name: `?CreateStringVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG1_NPEAPEAU?$IVector@PEAUHSTRING__@@@234@@Z`
- size: `2448`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dab0`
- `0x18009e740`

## callees

- `0x180004870`
- `0x18001e084`
- `0x18001ea14`
- `0x18001fce4`
- `0x180020b80`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800a0074`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ebbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001edb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f38c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001eb76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ebbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ed07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001edb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f229`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f346`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f38c`

## string_xrefs

- `0x18001ea5f`: `CreateStringVectorFromMap`
- `0x18001ef17`: `CreateStringVectorFromMap`
- `0x18001efab`: `CreateStringVectorFromMap`
- `0x18001efd6`: `CreateStringVectorFromMap`
- `0x18001f004`: `CreateStringVectorFromMap`
- `0x18001f032`: `CreateStringVectorFromMap`
- `0x18001f0e9`: `CreateStringVectorFromMap`
- `0x18001f198`: `CreateStringVectorFromMap`
- `0x18001f255`: `CreateStringVectorFromMap`
- `0x18001f2e6`: `CreateStringVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringVectorFromMap(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v8; // rcx
  int v9; // ebx
  __int64 (__fastcall *v10)(__int64, HSTRING__ *, _QWORD); // rbx
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  unsigned int i; // esi
  __int64 (__fastcall ***v14)(_QWORD, GUID *, HSTRING *); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, HSTRING *); // rbx
  HSTRING v16; // rcx
  _QWORD *v17; // rcx
  int (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v19; // rcx
  CallStackTracing *v21; // rcx
  __int64 v22; // rdx
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rcx
  unsigned int j; // edi
  __int64 v26; // rdx
  CallStackTracing *v27; // rcx
  HSTRING v28; // rcx
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  HSTRING *p_string; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  __int64 v41; // rdx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  HSTRING v45; // [rsp+30h] [rbp-41h] BYREF
  HSTRING string; // [rsp+38h] [rbp-39h] BYREF
  CallStackScopeTrace v47; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v48; // [rsp+44h] [rbp-2Dh] BYREF
  __int64 v49; // [rsp+48h] [rbp-29h] BYREF
  int (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-19h] BYREF
  __int64 v52; // [rsp+60h] [rbp-11h] BYREF
  Windows::Internal::StringReference v53; // [rsp+68h] [rbp-9h] BYREF

  v52 = 0;
  v50 = 0;
  v48 = 0;
  pv = 0;
  v49 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v47, "CreateStringVectorFromMap", 508);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
         v8,
         &v49);
  if ( v9 >= 0 )
  {
    if ( !a1 )
    {
LABEL_14:
      *a5 = v49;
      v49 = 0;
      goto LABEL_15;
    }
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING__ *, _QWORD))(*(_QWORD *)a1 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    Windows::Internal::StringReference::_ConstructorHelper(&v53, a2);
    v9 = v10(a1, v53._hstring, &v50);
    if ( v9 < 0 )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v30 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v30->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v30);
        if ( ThreadRelativeContext->m_result != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStringVectorFromMap", 523, v9);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v22 = 70;
        goto LABEL_27;
      }
      goto LABEL_15;
    }
    v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
    v12 = **v50;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    if ( v12(v11, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v52) >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v52 + 304LL))(v52, &v48, &pv);
      if ( v9 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v48 )
            goto LABEL_14;
          v45 = 0;
          v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, HSTRING *))*((_QWORD *)pv + i);
          v15 = **v14;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
          v9 = v15(v14, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v45);
          if ( v9 < 0 )
            break;
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          v9 = CreateStringFromMap(v45, a3, &string);
          if ( v9 < 0 )
          {
            v23 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v23 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v23->m_fEnabled )
            {
              v34 = CallStackTracing::GetThreadRelativeContext(v23);
              if ( v34->m_result != v9 )
                CallStackContext::TraceFailure(v34, "CreateStringVectorFromMap", 543, v9);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
            WindowsDeleteString(string);
            string = 0;
LABEL_83:
            p_string = &v45;
            goto LABEL_84;
          }
          v9 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v49 + 104LL))(v49, string);
          if ( v9 < 0 )
          {
            v27 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v27 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v27 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v27->m_fEnabled )
            {
              v33 = CallStackTracing::GetThreadRelativeContext(v27);
              if ( v33->m_result != v9 )
                CallStackContext::TraceFailure(v33, "CreateStringVectorFromMap", 546, v9);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
            WindowsDeleteString(string);
            v28 = v45;
            string = 0;
            if ( v45 )
            {
              v45 = 0;
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v28 + 16LL))(v28);
            }
            goto LABEL_15;
          }
          WindowsDeleteString(string);
          v16 = v45;
          string = 0;
          if ( v45 )
          {
            v45 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v16 + 16LL))(v16);
          }
        }
        v35 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v35 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v35->m_fEnabled )
        {
          v37 = CallStackTracing::GetThreadRelativeContext(v35);
          if ( v37->m_result != v9 )
            CallStackContext::TraceFailure(v37, "CreateStringVectorFromMap", 532, v9);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
        goto LABEL_83;
      }
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v21 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v21->m_fEnabled )
      {
        v32 = CallStackTracing::GetThreadRelativeContext(v21);
        if ( v32->m_result != v9 )
          CallStackContext::TraceFailure(v32, "CreateStringVectorFromMap", 527, v9);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v22 = 71;
LABEL_27:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
    string = 0;
    v9 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v50,
           &string);
    if ( v9 < 0 )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v38 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v38->m_fEnabled )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(v38);
        if ( v39->m_result != v9 )
          CallStackContext::TraceFailure(v39, "CreateStringVectorFromMap", 552, v9);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
LABEL_105:
      p_string = &string;
LABEL_84:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(p_string);
      goto LABEL_15;
    }
    WindowsDeleteString(0);
    v45 = 0;
    v9 = CreateStringFromMap(string, a3, &v45);
    if ( v9 < 0 )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v40 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v40->m_fEnabled )
      {
        v42 = CallStackTracing::GetThreadRelativeContext(v40);
        if ( v42->m_result != v9 )
          CallStackContext::TraceFailure(v42, "CreateStringVectorFromMap", 563, v9);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_104;
      v41 = 78;
    }
    else
    {
      v9 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v49 + 104LL))(v49, v45);
      if ( v9 >= 0 )
      {
        WindowsDeleteString(v45);
        v45 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        goto LABEL_14;
      }
      v43 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v43 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v43->m_fEnabled )
      {
        v44 = CallStackTracing::GetThreadRelativeContext(v43);
        if ( v44->m_result != v9 )
          CallStackContext::TraceFailure(v44, "CreateStringVectorFromMap", 566, v9);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_104;
      v41 = 79;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v41, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
LABEL_104:
    WindowsDeleteString(v45);
    v45 = 0;
    goto LABEL_105;
  }
  v24 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v24 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v24 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v24->m_fEnabled )
  {
    v29 = CallStackTracing::GetThreadRelativeContext(v24);
    if ( v29->m_result != v9 )
      CallStackContext::TraceFailure(v29, "CreateStringVectorFromMap", 508, v9);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v22 = 69;
    goto LABEL_27;
  }
LABEL_15:
  v17 = pv;
  if ( pv )
  {
    for ( j = 0; j < v48; ++j )
    {
      v26 = v17[j];
      if ( v26 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v17[j]);
        *((_QWORD *)pv + j) = 0;
        v17 = pv;
      }
    }
    CoTaskMemFree(v17);
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v47);
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  v18 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
  if ( v50 )
  {
    v50 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
  }
  v19 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ea14  push    rbp
0x18001ea16  push    rbx
0x18001ea17  push    rsi
0x18001ea18  push    rdi
0x18001ea19  push    r12
0x18001ea1b  push    r14
0x18001ea1d  push    r15
0x18001ea1f  lea     rbp, [rsp-1Fh]
0x18001ea24  sub     rsp, 90h
0x18001ea2b  mov     rax, cs:__security_cookie
0x18001ea32  xor     rax, rsp
0x18001ea35  mov     [rbp+4Fh+var_38], rax
0x18001ea39  mov     r14, [rbp+4Fh+arg_20]
0x18001ea3d  xor     r12d, r12d
0x18001ea40  mov     r15, r8
0x18001ea43  mov     [rbp+4Fh+var_60], r12
0x18001ea47  mov     rsi, rdx
0x18001ea4a  mov     [rbp+4Fh+var_70], r12
0x18001ea4e  mov     rdi, rcx
0x18001ea51  mov     [rbp+4Fh+var_7C], r12d
0x18001ea55  mov     r8d, 1FCh; int
0x18001ea5b  mov     [rbp+4Fh+pv], r12
0x18001ea5f  lea     rdx, aCreatestringve; "CreateStringVectorFromMap"
0x18001ea66  mov     [rbp+4Fh+var_78], r12
0x18001ea6a  lea     rcx, [rbp+4Fh+var_80]; this
0x18001ea6e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001ea73  lea     rcx, [rbp+4Fh+var_78]
0x18001ea77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ea7c  lea     rdx, [rbp+4Fh+var_78]
0x18001ea80  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18001ea85  mov     ebx, eax
0x18001ea87  test    eax, eax
0x18001ea89  js      loc_18001ED16
0x18001ea8f  test    rdi, rdi
0x18001ea92  jz      loc_18001EBE6
0x18001ea98  mov     rax, [rdi]
0x18001ea9b  lea     rcx, [rbp+4Fh+var_70]
0x18001ea9f  mov     rbx, [rax+30h]
0x18001eaa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001eaa8  mov     rdx, rsi; unsigned __int16 *
0x18001eaab  lea     rcx, [rbp+4Fh+var_58]; this
0x18001eaaf  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001eab4  mov     rdx, [rbp+4Fh+var_58._hstring]
0x18001eab8  lea     r8, [rbp+4Fh+var_70]
0x18001eabc  mov     rcx, rdi
0x18001eabf  mov     rax, rbx
0x18001eac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eac7  mov     ebx, eax
0x18001eac9  test    eax, eax
0x18001eacb  js      loc_18001EF31
0x18001ead1  mov     rbx, [rbp+4Fh+var_70]
0x18001ead5  lea     rcx, [rbp+4Fh+var_60]
0x18001ead9  mov     rax, [rbx]
0x18001eadc  mov     rdi, [rax]
0x18001eadf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001eae4  lea     r8, [rbp+4Fh+var_60]
0x18001eae8  mov     rcx, rbx
0x18001eaeb  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001eaf2  mov     rax, rdi
0x18001eaf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eafa  test    eax, eax
0x18001eafc  js      loc_18001F325
0x18001eb02  mov     rcx, [rbp+4Fh+var_60]
0x18001eb06  lea     r8, [rbp+4Fh+pv]
0x18001eb0a  lea     rdx, [rbp+4Fh+var_7C]
0x18001eb0e  mov     rax, [rcx]
0x18001eb11  mov     rax, [rax+130h]
0x18001eb18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb1d  mov     ebx, eax
0x18001eb1f  test    eax, eax
0x18001eb21  js      loc_18001EC6E
0x18001eb27  mov     esi, r12d
0x18001eb2a  cmp     esi, [rbp+4Fh+var_7C]
0x18001eb2d  jnb     loc_18001EBE6
0x18001eb33  mov     rax, [rbp+4Fh+pv]
0x18001eb37  mov     [rbp+4Fh+var_90], r12
0x18001eb3b  mov     ecx, esi
0x18001eb3d  mov     rdi, [rax+rcx*8]
0x18001eb41  lea     rcx, [rbp+4Fh+var_90]
0x18001eb45  mov     rax, [rdi]
0x18001eb48  mov     rbx, [rax]
0x18001eb4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001eb50  lea     r8, [rbp+4Fh+var_90]
0x18001eb54  mov     rcx, rdi
0x18001eb57  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001eb5e  mov     rax, rbx
0x18001eb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb66  mov     ebx, eax
0x18001eb68  test    eax, eax
0x18001eb6a  js      loc_18001F04C
0x18001eb70  xor     ecx, ecx; string
0x18001eb72  mov     [rbp+4Fh+string], r12
0x18001eb76  call    cs:__imp_WindowsDeleteString
0x18001eb7c  mov     rcx, [rbp+4Fh+var_90]
0x18001eb80  lea     r8, [rbp+4Fh+string]
0x18001eb84  mov     rdx, r15
0x18001eb87  mov     [rbp+4Fh+string], r12
0x18001eb8b  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18001eb90  mov     ebx, eax
0x18001eb92  test    eax, eax
0x18001eb94  js      loc_18001ECBD
0x18001eb9a  mov     rcx, [rbp+4Fh+var_78]
0x18001eb9e  mov     rdx, [rbp+4Fh+string]
0x18001eba2  mov     rax, [rcx]
0x18001eba5  mov     rax, [rax+68h]
0x18001eba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebae  mov     ebx, eax
0x18001ebb0  test    eax, eax
0x18001ebb2  js      loc_18001ED88
0x18001ebb8  mov     rcx, [rbp+4Fh+string]; string
0x18001ebbc  call    cs:__imp_WindowsDeleteString
0x18001ebc2  mov     rcx, [rbp+4Fh+var_90]
0x18001ebc6  mov     [rbp+4Fh+string], r12
0x18001ebca  test    rcx, rcx
0x18001ebcd  jz      short loc_18001EBDF
0x18001ebcf  mov     [rbp+4Fh+var_90], r12
0x18001ebd3  mov     rax, [rcx]
0x18001ebd6  mov     rax, [rax+10h]
0x18001ebda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebdf  inc     esi
0x18001ebe1  jmp     loc_18001EB2A
0x18001ebe6  mov     rax, [rbp+4Fh+var_78]
0x18001ebea  mov     [r14], rax
0x18001ebed  mov     [rbp+4Fh+var_78], r12
0x18001ebf1  mov     rcx, [rbp+4Fh+pv]
0x18001ebf5  test    rcx, rcx
0x18001ebf8  jnz     loc_18001ED47
0x18001ebfe  lea     rcx, [rbp+4Fh+var_80]; this
0x18001ec02  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001ec07  mov     rcx, [rbp+4Fh+var_78]
0x18001ec0b  test    rcx, rcx
0x18001ec0e  jz      short loc_18001EC1C
0x18001ec10  mov     rax, [rcx]
0x18001ec13  mov     rax, [rax+10h]
0x18001ec17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec1c  mov     rcx, [rbp+4Fh+var_70]
0x18001ec20  test    rcx, rcx
0x18001ec23  jz      short loc_18001EC35
0x18001ec25  mov     [rbp+4Fh+var_70], r12
0x18001ec29  mov     rax, [rcx]
0x18001ec2c  mov     rax, [rax+10h]
0x18001ec30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec35  mov     rcx, [rbp+4Fh+var_60]
0x18001ec39  test    rcx, rcx
0x18001ec3c  jz      short loc_18001EC4E
0x18001ec3e  mov     [rbp+4Fh+var_60], r12
0x18001ec42  mov     rax, [rcx]
0x18001ec45  mov     rax, [rax+10h]
0x18001ec49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec4e  mov     eax, ebx
0x18001ec50  mov     rcx, [rbp+4Fh+var_38]
0x18001ec54  xor     rcx, rsp; StackCookie
0x18001ec57  call    __security_check_cookie
0x18001ec5c  add     rsp, 90h
0x18001ec63  pop     r15
0x18001ec65  pop     r14
0x18001ec67  pop     r12
0x18001ec69  pop     rdi
0x18001ec6a  pop     rsi
0x18001ec6b  pop     rbx
0x18001ec6c  pop     rbp
0x18001ec6d  retn
0x18001ec6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001ec75  test    rcx, rcx
0x18001ec78  jz      loc_18001EDDF
0x18001ec7e  cmp     [rcx+8], r12b
0x18001ec82  jnz     loc_18001EFC2
0x18001ec88  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ec8f  jb      loc_18001EBF1
0x18001ec95  mov     edx, 47h ; 'G'
0x18001ec9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eca1  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18001eca8  xor     r9d, r9d
0x18001ecab  mov     [rsp+0C0h+var_A0], ebx
0x18001ecaf  mov     rcx, [rcx+10h]
0x18001ecb3  call    WPP_SF_qD
0x18001ecb8  jmp     loc_18001EBF1
0x18001ecbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001ecc4  test    rcx, rcx
0x18001ecc7  jz      loc_18001EEBA
0x18001eccd  cmp     [rcx+8], r12b
0x18001ecd1  jnz     loc_18001F01E
0x18001ecd7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ecde  jb      short loc_18001ED03
0x18001ece0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ece7  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18001ecee  mov     edx, 4Ah ; 'J'
0x18001ecf3  mov     [rsp+0C0h+var_A0], ebx
0x18001ecf7  xor     r9d, r9d
0x18001ecfa  mov     rcx, [rcx+10h]
0x18001ecfe  call    WPP_SF_qD
0x18001ed03  mov     rcx, [rbp+4Fh+string]; string
0x18001ed07  call    cs:__imp_WindowsDeleteString
0x18001ed0d  mov     [rbp+4Fh+string], r12
0x18001ed11  jmp     loc_18001F0C2
0x18001ed16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001ed1d  test    rcx, rcx
0x18001ed20  jz      loc_18001EE28
0x18001ed26  cmp     [rcx+8], r12b
0x18001ed2a  jnz     loc_18001EF03
0x18001ed30  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ed37  jb      loc_18001EBF1
0x18001ed3d  mov     edx, 45h ; 'E'
0x18001ed42  jmp     loc_18001EC9A
0x18001ed47  mov     edi, r12d
0x18001ed4a  cmp     [rbp+4Fh+var_7C], r12d
0x18001ed4e  jbe     short loc_18001ED7D
0x18001ed50  mov     esi, edi
0x18001ed52  mov     rdx, [rcx+rsi*8]
0x18001ed56  test    rdx, rdx
0x18001ed59  jz      short loc_18001ED76
0x18001ed5b  mov     rax, [rdx]
0x18001ed5e  mov     rcx, rdx
0x18001ed61  mov     rax, [rax+10h]
0x18001ed65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed6a  mov     rax, [rbp+4Fh+pv]
0x18001ed6e  mov     [rax+rsi*8], r12
0x18001ed72  mov     rcx, [rbp+4Fh+pv]; pv
0x18001ed76  inc     edi
0x18001ed78  cmp     edi, [rbp+4Fh+var_7C]
0x18001ed7b  jb      short loc_18001ED50
0x18001ed7d  call    cs:__imp_CoTaskMemFree
0x18001ed83  jmp     loc_18001EBFE
0x18001ed88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001ed8f  test    rcx, rcx
0x18001ed92  jz      loc_18001EE71
0x18001ed98  cmp     [rcx+8], r12b
0x18001ed9c  jnz     loc_18001EFF0
0x18001eda2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001eda9  jnb     loc_18001F2FD
0x18001edaf  mov     rcx, [rbp+4Fh+string]; string
0x18001edb3  call    cs:__imp_WindowsDeleteString
0x18001edb9  mov     rcx, [rbp+4Fh+var_90]
0x18001edbd  mov     [rbp+4Fh+string], r12
0x18001edc1  test    rcx, rcx
0x18001edc4  jz      loc_18001EBF1
0x18001edca  mov     [rbp+4Fh+var_90], r12
0x18001edce  mov     rax, [rcx]
0x18001edd1  mov     rax, [rax+10h]
0x18001edd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edda  jmp     loc_18001EBF1
0x18001eddf  mov     rax, cs:stru_1801FC290.__vftable
0x18001ede6  lea     r8, stru_1801FC290
0x18001eded  mov     edx, 7F0h
0x18001edf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18001edf9  mov     rcx, r8
0x18001edfc  mov     rax, [rax+8]
0x18001ee00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee05  test    eax, eax
0x18001ee07  jnz     short loc_18001EE1C
0x18001ee09  lea     rcx, stru_1801F8A30
0x18001ee10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ee17  jmp     loc_18001EC7E
0x18001ee1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ee23  jmp     loc_18001EC7E
0x18001ee28  mov     rcx, cs:stru_1801FC290.__vftable
0x18001ee2f  lea     r8, stru_1801FC290
0x18001ee36  mov     edx, 7F0h
0x18001ee3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ee42  mov     rax, [rcx+8]
0x18001ee46  mov     rcx, r8
0x18001ee49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee4e  test    eax, eax
0x18001ee50  jnz     short loc_18001EE65
0x18001ee52  lea     rcx, stru_1801F8A30
0x18001ee59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ee60  jmp     loc_18001ED26
0x18001ee65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ee6c  jmp     loc_18001ED26
0x18001ee71  mov     rax, cs:stru_1801FC290.__vftable
0x18001ee78  lea     r8, stru_1801FC290
0x18001ee7f  mov     edx, 7F0h
0x18001ee84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ee8b  mov     rcx, r8
0x18001ee8e  mov     rax, [rax+8]
0x18001ee92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee97  test    eax, eax
0x18001ee99  jnz     short loc_18001EEAE
0x18001ee9b  lea     rcx, stru_1801F8A30
0x18001eea2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eea9  jmp     loc_18001ED98
0x18001eeae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eeb5  jmp     loc_18001ED98
0x18001eeba  mov     rax, cs:stru_1801FC290.__vftable
0x18001eec1  lea     r8, stru_1801FC290
0x18001eec8  mov     edx, 7F0h
0x18001eecd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eed4  mov     rcx, r8
0x18001eed7  mov     rax, [rax+8]
0x18001eedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eee0  test    eax, eax
0x18001eee2  jnz     short loc_18001EEF7
0x18001eee4  lea     rcx, stru_1801F8A30
0x18001eeeb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eef2  jmp     loc_18001ECCD
0x18001eef7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eefe  jmp     loc_18001ECCD
0x18001ef03  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001ef08  cmp     [rax+7CCh], ebx
0x18001ef0e  jz      loc_18001ED30
  ... truncated ...
```
