# CMFWinRTActivate::SavePropertiesToIStream(IStream *,Windows::Foundation::Collections::IPropertySet *,bool)

- ea: `0x18014da44`
- end: `0x18014e82e`
- name: `?SavePropertiesToIStream@CMFWinRTActivate@@SAJPEAUIStream@@PEAUIPropertySet@Collections@Foundation@Windows@@_N@Z`
- size: `3562`
- prototype: `__int64 __fastcall(LPSTREAM pStm, struct Windows::Foundation::Collections::IPropertySet *, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18014d630`

## callees

- `0x180004870`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180035e28`
- `0x180038bf0`
- `0x18007b720`
- `0x180082eac`
- `0x1800b2058`
- `0x18014caf0`
- `0x18014da44`
- `0x18014e9fc`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18014df08`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18014df5d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18014df08`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18014df5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18014de47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18014de47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014de90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014de90`

## pseudocode

```c
__int64 __fastcall CMFWinRTActivate::SavePropertiesToIStream(
        LPSTREAM pStm,
        struct Windows::Foundation::Collections::IPropertySet *a2,
        char a3)
{
  CallStackTracing *v6; // rcx
  HRESULT Type; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  unsigned int v15; // esi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 **); // rbx
  __int64 v20; // rax
  UINT32 StringLen; // eax
  UINT32 v22; // ebx
  HRESULT (__fastcall *Write)(ISequentialStream *, const void *, unsigned int, unsigned int *); // rdi
  PCWSTR StringRawBuffer; // rax
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  CallStackTracing *v45; // rcx
  struct CallStackContext *v46; // rax
  CallStackTracing *v47; // rcx
  struct CallStackContext *v48; // rax
  CallStackTracing *v49; // rcx
  struct CallStackContext *v50; // rax
  CallStackTracing *v51; // rcx
  struct CallStackContext *v52; // rax
  CallStackTracing *v53; // rcx
  struct CallStackContext *v54; // rax
  CallStackTracing *v55; // rcx
  struct CallStackContext *v56; // rax
  __int64 v58; // [rsp+30h] [rbp-69h] BYREF
  __int64 *v59; // [rsp+38h] [rbp-61h] BYREF
  HSTRING string; // [rsp+40h] [rbp-59h] BYREF
  __int64 v61; // [rsp+48h] [rbp-51h] BYREF
  int v62; // [rsp+50h] [rbp-49h]
  UINT32 length; // [rsp+58h] [rbp-41h] BYREF
  enum Windows::Foundation::PropertyType v64; // [rsp+5Ch] [rbp-3Dh] BYREF
  LPUNKNOWN pUnk; // [rsp+60h] [rbp-39h] BYREF
  int v66; // [rsp+68h] [rbp-31h] BYREF
  __int64 v67; // [rsp+70h] [rbp-29h] BYREF
  int v68; // [rsp+78h] [rbp-21h] BYREF
  LPUNKNOWN v69; // [rsp+80h] [rbp-19h] BYREF
  int v70; // [rsp+88h] [rbp-11h]
  RoVariant *v71; // [rsp+90h] [rbp-9h]
  struct IInspectable *v72; // [rsp+98h] [rbp-1h] BYREF
  __int64 v73; // [rsp+A0h] [rbp+7h] BYREF
  int v74; // [rsp+A8h] [rbp+Fh]
  __int64 v75; // [rsp+B0h] [rbp+17h] BYREF
  int v76; // [rsp+B8h] [rbp+1Fh]
  CallStackScopeTrace v77; // [rsp+100h] [rbp+67h] BYREF
  int v78; // [rsp+118h] [rbp+7Fh] BYREF

  v78 = 0;
  v67 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v77, "CMFWinRTActivate::SavePropertiesToIStream", 788);
  if ( !pStm )
  {
    v6 = CallStackTracing::s_wpInstance;
    Type = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v6 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v6->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
      if ( ThreadRelativeContext->m_result != -2147024809 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFWinRTActivate::SavePropertiesToIStream",
          788,
          -2147024809);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_200;
    v9 = 122;
    goto LABEL_11;
  }
  if ( !a2 )
  {
    v10 = CallStackTracing::s_wpInstance;
    Type = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v10 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v10->m_fEnabled )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( v11->m_result != -2147024809 )
        CallStackContext::TraceFailure(v11, "CMFWinRTActivate::SavePropertiesToIStream", 789, -2147024809);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_200;
    v9 = 123;
LABEL_11:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids, 0, -2147024809);
    goto LABEL_200;
  }
  QueryInterface = a2->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  Type = QueryInterface(a2, &GUID_fe2f3d47_5d47_5499_8374_430c7cda0204, (void **)&v67);
  if ( Type < 0 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v13 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v13->m_fEnabled )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( v14->m_result != Type )
        CallStackContext::TraceFailure(v14, "CMFWinRTActivate::SavePropertiesToIStream", 791, Type);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids, 0, Type);
    goto LABEL_200;
  }
  v68 = 0;
  v15 = 0;
LABEL_34:
  if ( v15 < 2 )
  {
    v58 = 0;
    if ( v15 == 1 )
    {
      Type = pStm->Write(pStm, &v78, 4u, (unsigned int *)&v68);
      if ( Type < 0 )
      {
        v25 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v25 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v25->m_fEnabled )
        {
          v26 = CallStackTracing::GetThreadRelativeContext(v25);
          if ( v26->m_result != Type )
            CallStackContext::TraceFailure(v26, "CMFWinRTActivate::SavePropertiesToIStream", 805, Type);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_199;
        v27 = 125;
        goto LABEL_198;
      }
      if ( !v78 )
        goto LABEL_199;
    }
    v16 = v67;
    v77 = 0;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    Type = v17(v16, &v58);
    if ( Type < 0 )
    {
      v55 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v55 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v55 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v55->m_fEnabled )
      {
        v56 = CallStackTracing::GetThreadRelativeContext(v55);
        if ( v56->m_result != Type )
          CallStackContext::TraceFailure(v56, "CMFWinRTActivate::SavePropertiesToIStream", 813, Type);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_199;
      v27 = 126;
    }
    else
    {
      Type = (*(__int64 (__fastcall **)(__int64, CallStackScopeTrace *))(*(_QWORD *)v58 + 56LL))(v58, &v77);
      if ( Type >= 0 )
      {
        while ( 1 )
        {
          if ( !*(_BYTE *)&v77 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
            ++v15;
            goto LABEL_34;
          }
          v18 = v58;
          v59 = 0;
          string = 0;
          v61 = 0;
          v62 = 0;
          v64 = PropertyType_Empty;
          v19 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v58 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
          Type = v19(v18, &v59);
          if ( Type < 0 )
            break;
          Type = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v59 + 48))(v59, &string);
          if ( Type < 0 )
          {
            v49 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v49 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v49 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v49->m_fEnabled )
            {
              v50 = CallStackTracing::GetThreadRelativeContext(v49);
              if ( v50->m_result != Type )
                CallStackContext::TraceFailure(v50, "CMFWinRTActivate::SavePropertiesToIStream", 824, Type);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_85;
            v40 = 129;
            goto LABEL_124;
          }
          v20 = *v59;
          v71 = (RoVariant *)&v61;
          v72 = 0;
          Type = (*(__int64 (__fastcall **)(__int64 *, struct IInspectable **))(v20 + 56))(v59, &v72);
          RoVariant::Attach(v71, v72);
          if ( Type < 0 )
          {
            v47 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v47 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v47 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v47->m_fEnabled )
            {
              v48 = CallStackTracing::GetThreadRelativeContext(v47);
              if ( v48->m_result != Type )
                CallStackContext::TraceFailure(v48, "CMFWinRTActivate::SavePropertiesToIStream", 825, Type);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_85;
            v40 = 130;
            goto LABEL_124;
          }
          v73 = v61;
          v74 = v62;
          Type = RoVariant::Accessor::get_Type((RoVariant::Accessor *)&v73, &v64);
          if ( Type < 0 )
          {
            v45 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v45 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v45->m_fEnabled )
            {
              v46 = CallStackTracing::GetThreadRelativeContext(v45);
              if ( v46->m_result != Type )
                CallStackContext::TraceFailure(v46, "CMFWinRTActivate::SavePropertiesToIStream", 826, Type);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_85;
            v40 = 131;
            goto LABEL_124;
          }
          if ( v64 != PropertyType_InspectableArray
            && v64 != PropertyType_OtherType
            && v64 != PropertyType_OtherTypeArray
            && v64
            && (v64 != PropertyType_Inspectable || a3) )
          {
            if ( v15 )
            {
              StringLen = WindowsGetStringLen(string);
              v66 = 0;
              length = StringLen;
              Type = pStm->Write(pStm, &length, 4u, (unsigned int *)&v66);
              if ( Type < 0 )
              {
                v41 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  CallStackTracing::s_wpInstance = &stru_1801FC290;
                  if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                  {
                    v41 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v41 = &stru_1801F8A30;
                    CallStackTracing::s_wpInstance = &stru_1801F8A30;
                  }
                }
                if ( v41->m_fEnabled )
                {
                  v42 = CallStackTracing::GetThreadRelativeContext(v41);
                  if ( v42->m_result != Type )
                    CallStackContext::TraceFailure(v42, "CMFWinRTActivate::SavePropertiesToIStream", 840, Type);
                }
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                {
                  v40 = 132;
                  goto LABEL_124;
                }
                goto LABEL_85;
              }
              v22 = 2 * length;
              Write = pStm->Write;
              StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
              Type = Write(pStm, StringRawBuffer, v22, (unsigned int *)&v66);
              if ( Type < 0 )
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
                  if ( v39->m_result != Type )
                    CallStackContext::TraceFailure(v39, "CMFWinRTActivate::SavePropertiesToIStream", 841, Type);
                }
                if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                {
                  v40 = 133;
                  goto LABEL_124;
                }
                goto LABEL_85;
              }
              if ( v64 == PropertyType_Inspectable )
              {
                v75 = v61;
                v76 = v62;
                pUnk = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
                Type = RoVariant::Accessor::GetInspectable((RoVariant::Accessor *)&v75, (struct IInspectable **)&pUnk);
                if ( Type < 0 )
                {
                  v31 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v31 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v31 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v31->m_fEnabled )
                  {
                    v32 = CallStackTracing::GetThreadRelativeContext(v31);
                    if ( v32->m_result != Type )
                      CallStackContext::TraceFailure(v32, "CMFWinRTActivate::SavePropertiesToIStream", 847, Type);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v30 = 134;
LABEL_83:
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v30,
                      &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
                      0,
                      Type);
                  }
LABEL_84:
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
                  goto LABEL_85;
                }
                Type = CoMarshalInterface(pStm, &IID_IInspectable, pUnk, 0, 0, 0);
                if ( Type < 0 )
                {
                  v28 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v28 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v28 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v28->m_fEnabled )
                  {
                    v29 = CallStackTracing::GetThreadRelativeContext(v28);
                    if ( v29->m_result != Type )
                      CallStackContext::TraceFailure(v29, "CMFWinRTActivate::SavePropertiesToIStream", 848, Type);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v30 = 135;
                    goto LABEL_83;
                  }
                  goto LABEL_84;
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
              }
              else
              {
                v69 = 0;
                v70 = 0;
                Type = ClonePropertyValue(&v61, &v69);
                if ( Type < 0 )
                {
                  v36 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v36 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v36 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v36->m_fEnabled )
                  {
                    v37 = CallStackTracing::GetThreadRelativeContext(v36);
                    if ( v37->m_result != Type )
                      CallStackContext::TraceFailure(v37, "CMFWinRTActivate::SavePropertiesToIStream", 856, Type);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v35 = 136;
LABEL_104:
                    WPP_SF_qD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v35,
                      &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids,
                      0,
                      Type);
                  }
LABEL_105:
                  RoVariant::~RoVariant((RoVariant *)&v69);
                  goto LABEL_85;
                }
                Type = CoMarshalInterface(pStm, &IID_IInspectable, v69, 0, 0, 0);
                if ( Type < 0 )
                {
                  v33 = CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    CallStackTracing::s_wpInstance = &stru_1801FC290;
                    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                    {
                      v33 = CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v33 = &stru_1801F8A30;
                      CallStackTracing::s_wpInstance = &stru_1801F8A30;
                    }
                  }
                  if ( v33->m_fEnabled )
                  {
                    v34 = CallStackTracing::GetThreadRelativeContext(v33);
                    if ( v34->m_result != Type )
                      CallStackContext::TraceFailure(v34, "CMFWinRTActivate::SavePropertiesToIStream", 857, Type);
                  }
                  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                  {
                    v35 = 137;
                    goto LABEL_104;
                  }
                  goto LABEL_105;
                }
                RoVariant::~RoVariant((RoVariant *)&v69);
              }
            }
            else
            {
              ++v78;
            }
          }
          Type = (*(__int64 (__fastcall **)(__int64, CallStackScopeTrace *))(*(_QWORD *)v58 + 64LL))(v58, &v77);
          if ( Type < 0 )
          {
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
              if ( v44->m_result != Type )
                CallStackContext::TraceFailure(v44, "CMFWinRTActivate::SavePropertiesToIStream", 862, Type);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v40 = 138;
              goto LABEL_124;
            }
LABEL_85:
            RoVariant::~RoVariant((RoVariant *)&v61);
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
LABEL_199:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
            goto LABEL_200;
          }
          RoVariant::~RoVariant((RoVariant *)&v61);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
        }
        v51 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v51 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v51 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v51->m_fEnabled )
        {
          v52 = CallStackTracing::GetThreadRelativeContext(v51);
          if ( v52->m_result != Type )
            CallStackContext::TraceFailure(v52, "CMFWinRTActivate::SavePropertiesToIStream", 823, Type);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_85;
        v40 = 128;
LABEL_124:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids, 0, Type);
        goto LABEL_85;
      }
      v53 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v53 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v53 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v53->m_fEnabled )
      {
        v54 = CallStackTracing::GetThreadRelativeContext(v53);
        if ( v54->m_result != Type )
          CallStackContext::TraceFailure(v54, "CMFWinRTActivate::SavePropertiesToIStream", 814, Type);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_199;
      v27 = 127;
    }
LABEL_198:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids, 0, Type);
    goto LABEL_199;
  }
LABEL_200:
  CallStackScopeTrace::~CallStackScopeTrace(&v77);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
  return (unsigned int)Type;
}

```

## disassembly

```asm
0x18014da44  mov     [rsp-8+arg_8], rbx
0x18014da49  push    rbp
0x18014da4a  push    rsi
0x18014da4b  push    rdi
0x18014da4c  push    r12
0x18014da4e  push    r13
0x18014da50  push    r14
0x18014da52  push    r15
0x18014da54  lea     rbp, [rsp-27h]
0x18014da59  sub     rsp, 0C0h
0x18014da60  mov     r15b, r8b
0x18014da63  lea     r13, aCmfwinrtactiva_9; "CMFWinRTActivate::SavePropertiesToIStre"...
0x18014da6a  mov     rdi, rdx
0x18014da6d  mov     r14, rcx
0x18014da70  xor     r12d, r12d
0x18014da73  lea     rcx, [rbp+57h+arg_0]; this
0x18014da77  mov     esi, 314h
0x18014da7c  mov     [rbp+57h+arg_18], r12d
0x18014da80  mov     r8d, esi; int
0x18014da83  mov     [rbp+57h+var_80], r12
0x18014da87  mov     rdx, r13; char *
0x18014da8a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18014da8f  test    r14, r14
0x18014da92  jnz     loc_18014DB45
0x18014da98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014da9f  mov     edi, 80070057h
0x18014daa4  mov     ebx, edi
0x18014daa6  test    rcx, rcx
0x18014daa9  jnz     short loc_18014DAEC
0x18014daab  mov     rax, cs:stru_1801FC290.__vftable
0x18014dab2  lea     r8, stru_1801FC290
0x18014dab9  mov     edx, 7F0h
0x18014dabe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dac5  mov     rcx, r8
0x18014dac8  mov     rax, [rax+8]
0x18014dacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dad1  test    eax, eax
0x18014dad3  jnz     short loc_18014DAE5
0x18014dad5  lea     rcx, stru_1801F8A30
0x18014dadc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dae3  jmp     short loc_18014DAEC
0x18014dae5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014daec  cmp     [rcx+8], r12b
0x18014daf0  jz      short loc_18014DB10
0x18014daf2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014daf7  cmp     [rax+7CCh], edi
0x18014dafd  jz      short loc_18014DB10
0x18014daff  mov     r9d, edi; int
0x18014db02  mov     r8d, esi; int
0x18014db05  mov     rdx, r13; char *
0x18014db08  mov     rcx, rax; this
0x18014db0b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014db10  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014db17  jb      loc_18014E7FF
0x18014db1d  mov     edx, 7Ah ; 'z'
0x18014db22  mov     dword ptr [rsp+0F0h+pvDestContext], edi
0x18014db26  mov     rcx, cs:WPP_GLOBAL_Control
0x18014db2d  lea     r8, WPP_dd9be7cc25fa36005e5c2ad9e013903d_Traceguids
0x18014db34  xor     r9d, r9d
0x18014db37  mov     rcx, [rcx+10h]
0x18014db3b  call    WPP_SF_qD
0x18014db40  jmp     loc_18014E7FF
0x18014db45  test    rdi, rdi
0x18014db48  jnz     loc_18014DBE0
0x18014db4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014db55  mov     edi, 80070057h
0x18014db5a  mov     ebx, edi
0x18014db5c  test    rcx, rcx
0x18014db5f  jnz     short loc_18014DBA2
0x18014db61  mov     rax, cs:stru_1801FC290.__vftable
0x18014db68  lea     r8, stru_1801FC290
0x18014db6f  mov     edx, 7F0h
0x18014db74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18014db7b  mov     rcx, r8
0x18014db7e  mov     rax, [rax+8]
0x18014db82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014db87  test    eax, eax
0x18014db89  jnz     short loc_18014DB9B
0x18014db8b  lea     rcx, stru_1801F8A30
0x18014db92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014db99  jmp     short loc_18014DBA2
0x18014db9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014dba2  cmp     [rcx+8], r12b
0x18014dba6  jz      short loc_18014DBC9
0x18014dba8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014dbad  cmp     [rax+7CCh], edi
0x18014dbb3  jz      short loc_18014DBC9
0x18014dbb5  mov     r9d, edi; int
0x18014dbb8  mov     r8d, 315h; int
0x18014dbbe  mov     rdx, r13; char *
0x18014dbc1  mov     rcx, rax; this
0x18014dbc4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014dbc9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014dbd0  jb      loc_18014E7FF
0x18014dbd6  mov     edx, 7Bh ; '{'
0x18014dbdb  jmp     loc_18014DB22
0x18014dbe0  mov     rax, [rdi]
0x18014dbe3  lea     rcx, [rbp+57h+var_80]
0x18014dbe7  mov     rbx, [rax]
0x18014dbea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014dbef  lea     r8, [rbp+57h+var_80]
0x18014dbf3  mov     rcx, rdi
0x18014dbf6  lea     rdx, _GUID_fe2f3d47_5d47_5499_8374_430c7cda0204
0x18014dbfd  mov     rax, rbx
0x18014dc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dc05  mov     ebx, eax
0x18014dc07  test    eax, eax
0x18014dc09  jns     loc_18014DC9E
0x18014dc0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dc16  test    rcx, rcx
0x18014dc19  jnz     short loc_18014DC5C
0x18014dc1b  mov     rcx, cs:stru_1801FC290.__vftable
0x18014dc22  lea     r8, stru_1801FC290
0x18014dc29  mov     edx, 7F0h
0x18014dc2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dc35  mov     rax, [rcx+8]
0x18014dc39  mov     rcx, r8
0x18014dc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dc41  test    eax, eax
0x18014dc43  jnz     short loc_18014DC55
0x18014dc45  lea     rcx, stru_1801F8A30
0x18014dc4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014dc53  jmp     short loc_18014DC5C
0x18014dc55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014dc5c  cmp     [rcx+8], r12b
0x18014dc60  jz      short loc_18014DC83
0x18014dc62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014dc67  cmp     [rax+7CCh], ebx
0x18014dc6d  jz      short loc_18014DC83
0x18014dc6f  mov     r9d, ebx; int
0x18014dc72  mov     r8d, 317h; int
0x18014dc78  mov     rdx, r13; char *
0x18014dc7b  mov     rcx, rax; this
0x18014dc7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014dc83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014dc8a  jb      loc_18014E7FF
0x18014dc90  mov     edx, 7Ch ; '|'
0x18014dc95  mov     dword ptr [rsp+0F0h+pvDestContext], ebx
0x18014dc99  jmp     loc_18014DB26
0x18014dc9e  mov     [rbp+57h+var_78], r12d
0x18014dca2  mov     esi, r12d
0x18014dca5  cmp     esi, 2
0x18014dca8  jnb     loc_18014E7FF
0x18014dcae  mov     [rbp+57h+var_C0], r12
0x18014dcb2  cmp     esi, 1
0x18014dcb5  jnz     short loc_18014DCE6
0x18014dcb7  mov     rax, [r14]
0x18014dcba  lea     r9, [rbp+57h+var_78]
0x18014dcbe  lea     r8d, [rsi+3]
0x18014dcc2  mov     rcx, r14
0x18014dcc5  lea     rdx, [rbp+57h+arg_18]
0x18014dcc9  mov     rax, [rax+20h]
0x18014dccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dcd2  mov     ebx, eax
0x18014dcd4  test    eax, eax
0x18014dcd6  js      loc_18014DFC4
0x18014dcdc  cmp     [rbp+57h+arg_18], r12d
0x18014dce0  jz      loc_18014E7F6
0x18014dce6  mov     rdi, [rbp+57h+var_80]
0x18014dcea  lea     rcx, [rbp+57h+var_C0]
0x18014dcee  mov     byte ptr [rbp+57h+arg_0], r12b
0x18014dcf2  mov     rax, [rdi]
0x18014dcf5  mov     rbx, [rax+30h]
0x18014dcf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014dcfe  lea     rdx, [rbp+57h+var_C0]
0x18014dd02  mov     rcx, rdi
0x18014dd05  mov     rax, rbx
0x18014dd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dd0d  mov     ebx, eax
0x18014dd0f  test    eax, eax
0x18014dd11  js      loc_18014E756
0x18014dd17  mov     rcx, [rbp+57h+var_C0]
0x18014dd1b  lea     rdx, [rbp+57h+arg_0]
0x18014dd1f  mov     rax, [rcx]
0x18014dd22  mov     rax, [rax+38h]
0x18014dd26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dd2b  mov     ebx, eax
0x18014dd2d  test    eax, eax
0x18014dd2f  js      loc_18014E6CB
0x18014dd35  cmp     byte ptr [rbp+57h+arg_0], r12b
0x18014dd39  jz      loc_18014DFB4
0x18014dd3f  mov     rdi, [rbp+57h+var_C0]
0x18014dd43  lea     rcx, [rbp+57h+var_B8]
0x18014dd47  mov     [rbp+57h+var_B8], r12
0x18014dd4b  mov     [rbp+57h+string], r12
0x18014dd4f  mov     [rbp+57h+var_A8], r12
0x18014dd53  mov     [rbp+57h+var_A0], r12d
0x18014dd57  mov     [rbp+57h+var_94], r12d
0x18014dd5b  mov     rax, [rdi]
0x18014dd5e  mov     rbx, [rax+30h]
0x18014dd62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014dd67  lea     rdx, [rbp+57h+var_B8]
0x18014dd6b  mov     rcx, rdi
0x18014dd6e  mov     rax, rbx
0x18014dd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dd76  mov     ebx, eax
0x18014dd78  test    eax, eax
0x18014dd7a  js      loc_18014E640
0x18014dd80  mov     rcx, [rbp+57h+var_B8]
0x18014dd84  lea     rdx, [rbp+57h+string]
0x18014dd88  mov     rax, [rcx]
0x18014dd8b  mov     rax, [rax+30h]
0x18014dd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014dd94  mov     ebx, eax
0x18014dd96  test    eax, eax
0x18014dd98  js      loc_18014E5B5
0x18014dd9e  mov     rcx, [rbp+57h+var_B8]
0x18014dda2  lea     rdx, [rbp+57h+var_A8]
0x18014dda6  mov     rax, [rcx]
0x18014dda9  mov     [rbp+57h+var_60], rdx
0x18014ddad  lea     rdx, [rbp+57h+var_58]
0x18014ddb1  mov     [rbp+57h+var_58], r12
0x18014ddb5  mov     rax, [rax+38h]
0x18014ddb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ddbe  mov     rdx, [rbp+57h+var_58]; struct IInspectable *
0x18014ddc2  mov     ebx, eax
0x18014ddc4  mov     rcx, [rbp+57h+var_60]; this
0x18014ddc8  call    ?Attach@RoVariant@@QEAAXPEAUIInspectable@@@Z; RoVariant::Attach(IInspectable *)
0x18014ddcd  mov     eax, ebx
0x18014ddcf  shr     eax, 1Fh
0x18014ddd2  test    al, al
0x18014ddd4  jnz     loc_18014E526
0x18014ddda  mov     rax, [rbp+57h+var_A8]
0x18014ddde  lea     rdx, [rbp+57h+var_94]; enum Windows::Foundation::PropertyType *
0x18014dde2  mov     [rbp+57h+var_50], rax
0x18014dde6  lea     rcx, [rbp+57h+var_50]; this
0x18014ddea  mov     eax, [rbp+57h+var_A0]
0x18014dded  mov     [rbp+57h+var_48], eax
0x18014ddf0  call    ?get_Type@Accessor@RoVariant@@QEBAJPEAW4PropertyType@Foundation@Windows@@@Z; RoVariant::Accessor::get_Type(Windows::Foundation::PropertyType *)
0x18014ddf5  mov     ebx, eax
0x18014ddf7  test    eax, eax
0x18014ddf9  js      loc_18014E49B
0x18014ddff  mov     eax, [rbp+57h+var_94]
0x18014de02  cmp     eax, 40Dh
0x18014de07  jz      loc_18014DF76
0x18014de0d  cmp     eax, 14h
0x18014de10  jz      loc_18014DF76
0x18014de16  cmp     eax, 414h
0x18014de1b  jz      loc_18014DF76
0x18014de21  test    eax, eax
0x18014de23  jz      loc_18014DF76
0x18014de29  cmp     eax, 0Dh
0x18014de2c  jnz     short loc_18014DE37
0x18014de2e  test    r15b, r15b
0x18014de31  jz      loc_18014DF76
0x18014de37  test    esi, esi
0x18014de39  jnz     short loc_18014DE43
0x18014de3b  inc     [rbp+57h+arg_18]
0x18014de3e  jmp     loc_18014DF76
0x18014de43  mov     rcx, [rbp+57h+string]; string
0x18014de47  call    cs:__imp_WindowsGetStringLen
0x18014de4d  lea     r9, [rbp+57h+var_88]
0x18014de51  mov     [rbp+57h+var_88], r12d
0x18014de55  mov     [rbp+57h+length], eax
0x18014de58  lea     rdx, [rbp+57h+length]
0x18014de5c  mov     rax, [r14]
0x18014de5f  mov     r8d, 4
0x18014de65  mov     rcx, r14
0x18014de68  mov     rax, [rax+20h]
0x18014de6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014de71  mov     ebx, eax
0x18014de73  test    eax, eax
0x18014de75  js      loc_18014E385
0x18014de7b  mov     ecx, [rbp+57h+length]
0x18014de7e  lea     rdx, [rbp+57h+length]; length
0x18014de82  mov     rax, [r14]
0x18014de85  lea     ebx, [rcx+rcx]
0x18014de88  mov     rcx, [rbp+57h+string]; string
0x18014de8c  mov     rdi, [rax+20h]
0x18014de90  call    cs:__imp_WindowsGetStringRawBuffer
0x18014de96  lea     r9, [rbp+57h+var_88]
0x18014de9a  mov     r8d, ebx
0x18014de9d  mov     rdx, rax
0x18014dea0  mov     rcx, r14
0x18014dea3  mov     rax, rdi
0x18014dea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014deab  mov     ebx, eax
0x18014dead  test    eax, eax
0x18014deaf  js      loc_18014E2DC
0x18014deb5  cmp     [rbp+57h+var_94], 0Dh
0x18014deb9  jnz     short loc_18014DF23
0x18014debb  mov     rax, [rbp+57h+var_A8]
0x18014debf  lea     rcx, [rbp+57h+pUnk]
0x18014dec3  mov     [rbp+57h+var_40], rax
0x18014dec7  mov     eax, [rbp+57h+var_A0]
0x18014deca  mov     [rbp+57h+var_38], eax
0x18014decd  mov     [rbp+57h+pUnk], r12
0x18014ded1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014ded6  lea     rdx, [rbp+57h+pUnk]; struct IInspectable **
0x18014deda  lea     rcx, [rbp+57h+var_40]; this
0x18014dede  call    ?GetInspectable@Accessor@RoVariant@@QEBAJPEAPEAUIInspectable@@@Z; RoVariant::Accessor::GetInspectable(IInspectable * *)
0x18014dee3  mov     ebx, eax
0x18014dee5  test    eax, eax
0x18014dee7  js      loc_18014E118
0x18014deed  mov     r8, [rbp+57h+pUnk]; pUnk
0x18014def1  lea     rdx, IID_IInspectable; riid
0x18014def8  mov     [rsp+0F0h+mshlflags], r12d; mshlflags
0x18014defd  xor     r9d, r9d; dwDestContext
0x18014df00  mov     rcx, r14; pStm
0x18014df03  mov     [rsp+0F0h+pvDestContext], r12; pvDestContext
  ... truncated ...
```
