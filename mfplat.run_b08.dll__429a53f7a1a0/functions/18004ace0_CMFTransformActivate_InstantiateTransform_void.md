# CMFTransformActivate::InstantiateTransform(void)

- ea: `0x18004ace0`
- end: `0x18004be87`
- name: `?InstantiateTransform@CMFTransformActivate@@MEAAJXZ`
- size: `4519`
- prototype: `__int64 __fastcall(CMFTransformActivate *__hidden this)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004a9b0`

## callees

- `0x180015b20`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18004a6c8`
- `0x18004a700`
- `0x18004ace0`
- `0x18004be90`
- `0x18004befc`
- `0x18004c034`
- `0x18004c0e0`
- `0x18004c290`
- `0x18004ce68`
- `0x180057118`
- `0x18005e3b0`
- `0x18005eb90`
- `0x18005fe00`
- `0x180073290`
- `0x180099450`
- `0x18009e6ec`
- `0x1800aeb78`
- `0x18011fff0`
- `0x180120030`
- `0x1801200d0`
- `0x180120ecc`
- `0x18014aa80`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ad4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ae20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ad4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ae20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ad8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ae47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ad8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ae47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004b940`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004bdf5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004b940`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004bdf5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004ae04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b02e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004ae04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b02e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004bd25`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004bd25`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x18004b455`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x18004be7c`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x18004b455`
- `api-ms-win-core-com-l1-1-3!CoRevokeDeviceCatalog` at `0x18004be7c`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x18004b476`
- `api-ms-win-core-com-l1-1-3!CoRegisterDeviceCatalog` at `0x18004b476`

## pseudocode

```c
__int64 __fastcall CMFTransformActivate::InstantiateTransform(CMFTransformActivate *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  __int64 Item; // rax
  int v4; // r13d
  HRESULT String; // ebx
  int IsDevProxyHwTransform; // eax
  char *v7; // r12
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD v10; // r15d
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  __int64 v14; // rcx
  int (__fastcall ***v15)(_QWORD, GUID *, wil::last_error_context *); // rcx
  CallStackTracing *v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  CallStackTracing *v18; // rcx
  __int64 v19; // rdx
  IUnknown *v20; // rcx
  CallStackTracing *v21; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  DWORD v23; // ebx
  void *v24; // r12
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  __int64 v28; // rbx
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  __int64 v36; // rdx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  __int64 v45; // rdx
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
  struct CallStackContext *v57; // rax
  unsigned __int16 *v58; // rax
  unsigned int v59; // r12d
  unsigned int i; // r15d
  DWORD merit[2]; // [rsp+30h] [rbp-D0h] BYREF
  wil::last_error_context ppv; // [rsp+38h] [rbp-C8h] BYREF
  CallStackScopeTrace v63; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v64; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v66; // [rsp+58h] [rbp-A8h] BYREF
  void *v67; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+78h] [rbp-88h]
  IID rclsid; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v71; // [rsp+90h] [rbp-70h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v73[40]; // [rsp+B0h] [rbp-50h] BYREF

  v66 = 0;
  v67 = 0;
  v65 = 0;
  rclsid = GUID_00000000_0000_0000_0000_000000000000;
  CallStackScopeTrace::CallStackScopeTrace(&v63, "CMFTransformActivate::InstantiateTransform", 143);
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  Item = CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(this, &MFT_TRANSFORM_CLSID_Attribute);
  v4 = -1072875843;
  if ( Item )
  {
    if ( *(_WORD *)Item == 72 )
    {
      String = 0;
      rclsid = *(IID *)*(_QWORD *)(Item + 8);
    }
    else
    {
      String = -1072875843;
    }
  }
  else
  {
    String = -1072875802;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( String < 0 )
  {
    v18 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v18 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v18 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v18->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v18);
      if ( ThreadRelativeContext->m_result != String )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFTransformActivate::InstantiateTransform", 143, String);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_32;
    v19 = 18;
    goto LABEL_67;
  }
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
  {
    memset_0(v73, 0, 0x4Au);
    v71 = rclsid;
    v58 = StringFromGUID(&v71, v73);
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      19,
      (unsigned int)&WPP_09a18ddabd713d953e6a9cf7fb2dfb47_Traceguids,
      (_DWORD)this,
      (__int64)v58);
  }
  merit[0] = 0;
  if ( (int)CMFAttributesImpl<IMFActivate,CMFCSLock>::GetStringLength(this, &MFT_ENUM_DeviceInstanceId_Attribute, merit) >= 0
    && merit[0] )
  {
    v23 = merit[0] + 1;
    ppv = (wil::last_error_context)operator new(saturated_mul(merit[0] + 1, 2u));
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v67, &ppv);
    if ( ppv )
      operator delete(*(void **)&ppv);
    v24 = v67;
    if ( !v67 )
    {
      v25 = CallStackTracing::s_wpInstance;
      String = -2147024882;
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
        v31 = CallStackTracing::GetThreadRelativeContext(v25);
        if ( v31->m_result != -2147024882 )
          CallStackContext::TraceFailure(v31, "CMFTransformActivate::InstantiateTransform", 157, -2147024882);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_32;
      v19 = 20;
      goto LABEL_67;
    }
    String = CMFAttributesImpl<IMFActivate,CMFCSLock>::GetString(
               this,
               &MFT_ENUM_DeviceInstanceId_Attribute,
               v67,
               v23,
               0);
    if ( String < 0 )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v26->m_fEnabled )
      {
        v27 = CallStackTracing::GetThreadRelativeContext(v26);
        if ( v27->m_result != String )
          CallStackContext::TraceFailure(v27, "CMFTransformActivate::InstantiateTransform", 159, String);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_32;
      v19 = 21;
      goto LABEL_67;
    }
    v28 = v65;
    if ( v65 )
    {
      wil::last_error_context::last_error_context(&ppv);
      CoRevokeDeviceCatalog(v28);
      wil::last_error_context::~last_error_context(&ppv);
    }
    v65 = 0;
    String = CoRegisterDeviceCatalog(v24, &v65);
    if ( String < 0 )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v29 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v29->m_fEnabled )
      {
        v30 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( v30->m_result != String )
          CallStackContext::TraceFailure(v30, "CMFTransformActivate::InstantiateTransform", 160, String);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_32;
      v19 = 22;
      goto LABEL_67;
    }
  }
  IsDevProxyHwTransform = CMFTransformActivate::IsDevProxyHwTransform(this);
  String = IsDevProxyHwTransform;
  if ( IsDevProxyHwTransform < 0 )
  {
    v32 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v32 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v32->m_fEnabled )
    {
      v33 = CallStackTracing::GetThreadRelativeContext(v32);
      if ( v33->m_result != String )
        CallStackContext::TraceFailure(v33, "CMFTransformActivate::InstantiateTransform", 163, String);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_32;
    v19 = 23;
    goto LABEL_67;
  }
  if ( !IsDevProxyHwTransform )
  {
    *(_QWORD *)merit = 0;
    ppv = 0;
    v64 = 0;
    pguid = GUID_00000000_0000_0000_0000_000000000000;
    String = CoCreateInstance(&CLSID_FSClientFactory, 0, 1u, &GUID_a9f69869_9293_49e2_af4a_b45164b073cc, (LPVOID *)&ppv);
    if ( String < 0 )
    {
      v16 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v16 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v16->m_fEnabled )
      {
        v34 = CallStackTracing::GetThreadRelativeContext(v16);
        if ( v34->m_result != String )
          CallStackContext::TraceFailure(v34, "CMFTransformActivate::InstantiateTransform", 180, String);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_09a18ddabd713d953e6a9cf7fb2dfb47_Traceguids,
          this,
          String);
      if ( v64 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      if ( ppv )
        (*(void (__fastcall **)(wil::last_error_context))(**(_QWORD **)&ppv + 16LL))(ppv);
      if ( *(_QWORD *)merit )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)merit + 16LL))(*(_QWORD *)merit);
      goto LABEL_32;
    }
    String = (*(__int64 (__fastcall **)(wil::last_error_context, CMFTransformActivate *, GUID *, DWORD *))(**(_QWORD **)&ppv + 24LL))(
               ppv,
               this,
               &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
               merit);
    if ( String < 0 )
    {
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
        if ( v37->m_result != String )
          CallStackContext::TraceFailure(v37, "CMFTransformActivate::InstantiateTransform", 183, String);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_177;
      v36 = 25;
    }
    else
    {
      if ( (int)CMFAttributesImpl<IMFActivate,CMFCSLock>::GetGUID(this, &MEDIA_TELEMETRY_SESSION_ID, &pguid) < 0 )
      {
        CoCreateGuid(&pguid);
        String = CMFAttributesImpl<IMFActivate,CMFCSLock>::SetGUID(this, &MEDIA_TELEMETRY_SESSION_ID, &pguid);
        if ( String < 0 )
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
            if ( v39->m_result != String )
              CallStackContext::TraceFailure(v39, "CMFTransformActivate::InstantiateTransform", 190, String);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_177;
          v36 = 26;
          goto LABEL_187;
        }
        String = CMFAttributesImpl<IMFActivate,CMFCSLock>::SetUINT32(
                   this,
                   &MF_DEVICESOURCE_GENERATE_TELEMETRY_REPORT,
                   1);
        if ( String < 0 )
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
            v41 = CallStackTracing::GetThreadRelativeContext(v40);
            if ( v41->m_result != String )
              CallStackContext::TraceFailure(v41, "CMFTransformActivate::InstantiateTransform", 191, String);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_177;
          v36 = 27;
          goto LABEL_187;
        }
      }
      String = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)merit + 64LL))(*(_QWORD *)merit, &v64);
      if ( String < 0 )
      {
        v42 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v42 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v42->m_fEnabled )
        {
          v43 = CallStackTracing::GetThreadRelativeContext(v42);
          if ( v43->m_result != String )
            CallStackContext::TraceFailure(v43, "CMFTransformActivate::InstantiateTransform", 196, String);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_177;
        v36 = 28;
      }
      else
      {
        v59 = *((_DWORD *)this + 15);
        for ( i = 0; i < v59; ++i )
        {
          v69 = 0;
          v71 = GUID_00000000_0000_0000_0000_000000000000;
          *(_OWORD *)pvar = 0;
          String = CMFAttributesImpl<IMFActivate,CMFCSLock>::GetItemByIndex(this, i, &v71, pvar);
          if ( String < 0 )
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
              if ( v48->m_result != String )
                CallStackContext::TraceFailure(v48, "CMFTransformActivate::InstantiateTransform", 202, String);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v45 = 30;
LABEL_175:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v45,
                &WPP_09a18ddabd713d953e6a9cf7fb2dfb47_Traceguids,
                this,
                String);
            }
LABEL_176:
            PropVariantClear(pvar);
            goto LABEL_177;
          }
          String = (*(__int64 (__fastcall **)(__int64, struct _GUID *, PROPVARIANT *))(*(_QWORD *)v64 + 144LL))(
                     v64,
                     &v71,
                     pvar);
          if ( String < 0 )
          {
            v44 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v44 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v44 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v44->m_fEnabled )
            {
              v46 = CallStackTracing::GetThreadRelativeContext(v44);
              if ( v46->m_result != String )
                CallStackContext::TraceFailure(v46, "CMFTransformActivate::InstantiateTransform", 205, String);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v45 = 31;
              goto LABEL_175;
            }
            goto LABEL_176;
          }
          PropVariantClear(pvar);
        }
        v7 = (char *)this + 96;
        String = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))merit)(
                   *(_QWORD *)merit,
                   &GUID_00000000_0000_0000_c000_000000000046,
                   (char *)this + 96);
        if ( String >= 0 )
        {
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(merit);
          v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
LABEL_11:
          v66 = 0;
          EnterCriticalSection(v2);
          v8 = CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(this, &MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE);
          if ( v8 )
          {
            if ( *(_WORD *)v8 == 13 )
            {
              v17 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v8 + 8);
              if ( v17 )
                v4 = (**v17)(v17, &GUID_627d2ca6_e1cd_4898_999d_101308f1d431, &v66);
            }
            v7 = (char *)this + 96;
          }
          else
          {
            v4 = -1072875802;
          }
          LeaveCriticalSection(v2);
          if ( v4 >= 0 )
          {
            v15 = *(int (__fastcall ****)(_QWORD, GUID *, wil::last_error_context *))v7;
            ppv = 0;
            if ( (**v15)(v15, &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803, &ppv) >= 0 )
              (*(void (__fastcall **)(wil::last_error_context, __int64))(**(_QWORD **)&ppv + 32LL))(ppv, v66);
            if ( ppv )
              (*(void (__fastcall **)(wil::last_error_context))(**(_QWORD **)&ppv + 16LL))(ppv);
          }
          String = CMFTransformActivate::ConfigFieldOfUse(this);
          if ( String < 0 )
          {
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
              if ( v52->m_result != String )
                CallStackContext::TraceFailure(v52, "CMFTransformActivate::InstantiateTransform", 237, String);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_32;
            v19 = 34;
          }
          else
          {
            String = CMFTransformActivate::ConfigTransform(this);
            if ( String < 0 )
            {
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
                if ( v54->m_result != String )
                  CallStackContext::TraceFailure(v54, "CMFTransformActivate::InstantiateTransform", 242, String);
              }
              if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                goto LABEL_32;
              v19 = 35;
            }
            else
            {
              v9 = *(_QWORD *)this;
              merit[0] = 0;
              if ( (*(int (__fastcall **)(CMFTransformActivate *, const GUID *, DWORD *))(v9 + 56))(
                     this,
                     &MFT_CODEC_MERIT_Attribute,
                     merit) >= 0 )
                v10 = merit[0];
              else
                v10 = 0;
              if ( !v10 )
                goto LABEL_19;
              v20 = *(IUnknown **)v7;
              merit[0] = v10;
              String = MFGetMFTMerit(v20, 0x10u, (const BYTE *)&rclsid, merit);
              if ( String < 0 )
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
                  if ( v56->m_result != String )
                    CallStackContext::TraceFailure(v56, "CMFTransformActivate::InstantiateTransform", 262, String);
                }
                if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                  goto LABEL_32;
                v19 = 36;
              }
              else
              {
                if ( merit[0] >= v10 )
                  goto LABEL_19;
                v21 = CallStackTracing::s_wpInstance;
                String = -1072875773;
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
                  v57 = CallStackTracing::GetThreadRelativeContext(v21);
                  if ( v57->m_result != -1072875773 )
                    CallStackContext::TraceFailure(v57, "CMFTransformActivate::InstantiateTransform", 264, -1072875773);
                }
                if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
                  goto LABEL_32;
                v19 = 37;
              }
            }
          }
          goto LABEL_67;
        }
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
          if ( v50->m_result != String )
            CallStackContext::TraceFailure(v50, "CMFTransformActivate::InstantiateTransform", 207, String);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
LABEL_177:
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v64);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppv);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(merit);
          goto LABEL_32;
        }
        v36 = 32;
      }
    }
LABEL_187:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, &WPP_09a18ddabd713d953e6a9cf7fb2dfb47_Traceguids, this, String);
    goto LABEL_177;
  }
  v7 = (char *)this + 96;
  String = CoCreateInstance(&rclsid, 0, 1u, &IID_IMFTransform, (LPVOID *)this + 12);
  if ( String >= 0 )
    goto LABEL_11;
  v12 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v12 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v12->m_fEnabled )
  {
    v13 = CallStackTracing::GetThreadRelativeContext(v12);
    if ( v13->m_result != String )
      CallStackContext::TraceFailure(v13, "CMFTransformActivate::InstantiateTransform", 217, String);
  }
  if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
    goto LABEL_32;
  v19 = 33;
LABEL_67:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_09a18ddabd713d953e6a9cf7fb2dfb47_Traceguids, this, String);
LABEL_32:
  v14 = *((_QWORD *)this + 12);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 12) = 0;
  }
  if ( String == -1073418223 )
    InvalidateMFTEnumCache();
LABEL_19:
  operator delete(0);
  operator delete(0);
  CallStackScopeTrace::~CallStackScopeTrace(&v63);
  if ( v65 )
    CoRevokeDeviceCatalog(v65);
  if ( v67 )
    operator delete(v67);
  if ( v66 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18004ace0  push    rbp
0x18004ace2  push    rbx
0x18004ace3  push    rsi
0x18004ace4  push    rdi
0x18004ace5  push    r12
0x18004ace7  push    r13
0x18004ace9  push    r14
0x18004aceb  push    r15
0x18004aced  lea     rbp, [rsp-18h]
0x18004acf2  sub     rsp, 118h
0x18004acf9  mov     rax, cs:__security_cookie
0x18004ad00  xor     rax, rsp
0x18004ad03  mov     [rbp+50h+var_50], rax
0x18004ad07  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004ad0e  xor     esi, esi
0x18004ad10  lea     r12, aCmftransformac_3; "CMFTransformActivate::InstantiateTransf"...
0x18004ad17  mov     rdi, rcx
0x18004ad1a  mov     [rsp+150h+var_F8], rsi
0x18004ad1f  mov     r14d, 8Fh
0x18004ad25  mov     [rsp+150h+var_F0], rsi
0x18004ad2a  mov     r8d, r14d; int
0x18004ad2d  mov     [rsp+150h+var_100], rsi
0x18004ad32  mov     rdx, r12; char *
0x18004ad35  lea     rcx, [rsp+150h+var_110]; this
0x18004ad3a  movdqu  xmmword ptr [rbp+50h+rclsid.Data1], xmm0
0x18004ad3f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004ad44  lea     r15, [rdi+8]
0x18004ad48  mov     rcx, r15; lpCriticalSection
0x18004ad4b  call    cs:__imp_EnterCriticalSection
0x18004ad51  lea     rdx, MFT_TRANSFORM_CLSID_Attribute
0x18004ad58  mov     rcx, rdi
0x18004ad5b  call    ?_FindItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(_GUID const &)
0x18004ad60  mov     r13d, 0C00D36BDh
0x18004ad66  test    rax, rax
0x18004ad69  jz      loc_18004AF1D
0x18004ad6f  cmp     word ptr [rax], 48h ; 'H'
0x18004ad73  jnz     loc_18004B1E0
0x18004ad79  mov     rax, [rax+8]
0x18004ad7d  mov     ebx, esi
0x18004ad7f  movups  xmm0, xmmword ptr [rax]
0x18004ad82  movdqu  xmmword ptr [rbp+50h+rclsid.Data1], xmm0
0x18004ad87  mov     rcx, r15; lpCriticalSection
0x18004ad8a  call    cs:__imp_LeaveCriticalSection
0x18004ad90  test    ebx, ebx
0x18004ad92  js      loc_18004B0EC
0x18004ad98  cmp     cs:byte_1801FD289, 10h
0x18004ad9f  lea     r14, WPP_09a18ddabd713d953e6a9cf7fb2dfb47_Traceguids
0x18004ada6  jnb     loc_18004BC34
0x18004adac  lea     r8, [rsp+150h+merit]
0x18004adb1  mov     [rsp+150h+merit], esi
0x18004adb5  lea     rdx, MFT_ENUM_DeviceInstanceId_Attribute
0x18004adbc  mov     rcx, rdi
0x18004adbf  call    ?GetStringLength@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@UEAAJAEBU_GUID@@PEAI@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::GetStringLength(_GUID const &,uint *)
0x18004adc4  mov     esi, 1
0x18004adc9  test    eax, eax
0x18004adcb  jns     loc_18004BC7E
0x18004add1  mov     rcx, rdi; this
0x18004add4  call    ?IsDevProxyHwTransform@CMFTransformActivate@@IEAAJXZ; CMFTransformActivate::IsDevProxyHwTransform(void)
0x18004add9  mov     ebx, eax
0x18004addb  test    eax, eax
0x18004addd  js      loc_18004B54D
0x18004ade3  xor     edx, edx; pUnkOuter
0x18004ade5  mov     r8d, esi; dwClsContext
0x18004ade8  test    eax, eax
0x18004adea  jz      loc_18004AFEF
0x18004adf0  lea     r12, [rdi+60h]
0x18004adf4  lea     r9, IID_IMFTransform; riid
0x18004adfb  mov     [rsp+150h+ppv], r12; ppv
0x18004ae00  lea     rcx, [rbp+50h+rclsid]; rclsid
0x18004ae04  call    cs:__imp_CoCreateInstance
0x18004ae0a  mov     ebx, eax
0x18004ae0c  test    eax, eax
0x18004ae0e  js      loc_18004AF27
0x18004ae14  mov     rcx, r15; lpCriticalSection
0x18004ae17  mov     [rsp+150h+var_F8], 0
0x18004ae20  call    cs:__imp_EnterCriticalSection
0x18004ae26  lea     rdx, MF_TELEMETRY_SESSION_OBJECT_ATTRIBUTE
0x18004ae2d  mov     rcx, rdi
0x18004ae30  call    ?_FindItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(_GUID const &)
0x18004ae35  test    rax, rax
0x18004ae38  jnz     loc_18004B0BA
0x18004ae3e  mov     r13d, 0C00D36E6h
0x18004ae44  mov     rcx, r15; lpCriticalSection
0x18004ae47  call    cs:__imp_LeaveCriticalSection
0x18004ae4d  test    r13d, r13d
0x18004ae50  jns     loc_18004AF92
0x18004ae56  mov     rcx, rdi; this
0x18004ae59  call    ?ConfigFieldOfUse@CMFTransformActivate@@MEAAJXZ; CMFTransformActivate::ConfigFieldOfUse(void)
0x18004ae5e  mov     ebx, eax
0x18004ae60  test    eax, eax
0x18004ae62  js      loc_18004BA47
0x18004ae68  mov     rcx, rdi; this
0x18004ae6b  call    ?ConfigTransform@CMFTransformActivate@@MEAAJXZ; CMFTransformActivate::ConfigTransform(void)
0x18004ae70  mov     ebx, eax
0x18004ae72  test    eax, eax
0x18004ae74  js      loc_18004BAD8
0x18004ae7a  mov     rax, [rdi]
0x18004ae7d  lea     r8, [rsp+150h+merit]
0x18004ae82  lea     rdx, MFT_CODEC_MERIT_Attribute
0x18004ae89  mov     [rsp+150h+merit], 0
0x18004ae91  mov     rcx, rdi
0x18004ae94  mov     rax, [rax+38h]
0x18004ae98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae9d  test    eax, eax
0x18004ae9f  jns     loc_18004BE59
0x18004aea5  xor     r15d, r15d
0x18004aea8  test    r15d, r15d
0x18004aeab  jnz     loc_18004B127
0x18004aeb1  xor     ecx, ecx; void *
0x18004aeb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004aeb8  xor     ecx, ecx; void *
0x18004aeba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004aebf  lea     rcx, [rsp+150h+var_110]; this
0x18004aec4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004aec9  mov     rcx, [rsp+150h+var_100]
0x18004aece  test    rcx, rcx
0x18004aed1  jnz     loc_18004BE7C
0x18004aed7  mov     rcx, [rsp+150h+var_F0]; void *
0x18004aedc  test    rcx, rcx
0x18004aedf  jnz     loc_18004B0B0
0x18004aee5  mov     rcx, [rsp+150h+var_F8]
0x18004aeea  test    rcx, rcx
0x18004aeed  jz      short loc_18004AEFB
0x18004aeef  mov     rax, [rcx]
0x18004aef2  mov     rax, [rax+10h]
0x18004aef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aefb  mov     eax, ebx
0x18004aefd  mov     rcx, [rbp+50h+var_50]
0x18004af01  xor     rcx, rsp; StackCookie
0x18004af04  call    __security_check_cookie
0x18004af09  add     rsp, 118h
0x18004af10  pop     r15
0x18004af12  pop     r14
0x18004af14  pop     r13
0x18004af16  pop     r12
0x18004af18  pop     rdi
0x18004af19  pop     rsi
0x18004af1a  pop     rbx
0x18004af1b  pop     rbp
0x18004af1c  retn
0x18004af1d  mov     ebx, 0C00D36E6h
0x18004af22  jmp     loc_18004AD87
0x18004af27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004af2e  test    rcx, rcx
0x18004af31  jz      loc_18004B1E8
0x18004af37  cmp     byte ptr [rcx+8], 0
0x18004af3b  jz      short loc_18004AF62
0x18004af3d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004af42  cmp     [rax+7CCh], ebx
0x18004af48  jz      short loc_18004AF62
0x18004af4a  mov     r9d, ebx; int
0x18004af4d  lea     rdx, aCmftransformac_3; "CMFTransformActivate::InstantiateTransf"...
0x18004af54  mov     r8d, 0D9h; int
0x18004af5a  mov     rcx, rax; this
0x18004af5d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004af62  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18004af69  jnb     loc_18004BE4F
0x18004af6f  mov     rcx, [rdi+60h]
0x18004af73  test    rcx, rcx
0x18004af76  jnz     loc_18004BE63
0x18004af7c  cmp     ebx, 0C004F011h
0x18004af82  jnz     loc_18004AEB1
0x18004af88  call    ?InvalidateMFTEnumCache@@YAXXZ; InvalidateMFTEnumCache(void)
0x18004af8d  jmp     loc_18004AEB1
0x18004af92  mov     rcx, [r12]
0x18004af96  lea     r8, [rsp+150h+var_118]
0x18004af9b  mov     qword ptr [rsp+150h+var_118.m_dismissed], 0
0x18004afa4  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x18004afab  mov     rax, [rcx]
0x18004afae  mov     rax, [rax]
0x18004afb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afb6  test    eax, eax
0x18004afb8  js      short loc_18004AFD0
0x18004afba  mov     rcx, qword ptr [rsp+150h+var_118.m_dismissed]
0x18004afbf  mov     rdx, [rsp+150h+var_F8]
0x18004afc4  mov     rax, [rcx]
0x18004afc7  mov     rax, [rax+20h]
0x18004afcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afd0  mov     rcx, qword ptr [rsp+150h+var_118.m_dismissed]
0x18004afd5  test    rcx, rcx
0x18004afd8  jz      loc_18004AE56
0x18004afde  mov     rax, [rcx]
0x18004afe1  mov     rax, [rax+10h]
0x18004afe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afea  jmp     loc_18004AE56
0x18004afef  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004aff6  lea     rax, [rsp+150h+var_118]
0x18004affb  mov     qword ptr [rsp+150h+merit], 0
0x18004b004  lea     r9, _GUID_a9f69869_9293_49e2_af4a_b45164b073cc; riid
0x18004b00b  mov     qword ptr [rsp+150h+var_118.m_dismissed], 0
0x18004b014  lea     rcx, CLSID_FSClientFactory; rclsid
0x18004b01b  mov     [rsp+150h+var_108], 0
0x18004b024  movdqu  xmmword ptr [rbp+50h+pguid.Data1], xmm0
0x18004b029  mov     [rsp+150h+ppv], rax; ppv
0x18004b02e  call    cs:__imp_CoCreateInstance
0x18004b034  mov     ebx, eax
0x18004b036  test    eax, eax
0x18004b038  jns     loc_18004BCE0
0x18004b03e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b045  test    rcx, rcx
0x18004b048  jz      loc_18004B231
0x18004b04e  cmp     byte ptr [rcx+8], 0
0x18004b052  jnz     loc_18004B5DA
0x18004b058  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18004b05f  jnb     loc_18004BCBC
0x18004b065  mov     rcx, [rsp+150h+var_108]
0x18004b06a  test    rcx, rcx
0x18004b06d  jz      short loc_18004B07B
0x18004b06f  mov     rax, [rcx]
0x18004b072  mov     rax, [rax+10h]
0x18004b076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b07b  mov     rcx, qword ptr [rsp+150h+var_118.m_dismissed]
0x18004b080  test    rcx, rcx
0x18004b083  jz      short loc_18004B091
0x18004b085  mov     rax, [rcx]
0x18004b088  mov     rax, [rax+10h]
0x18004b08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b091  mov     rcx, qword ptr [rsp+150h+merit]
0x18004b096  test    rcx, rcx
0x18004b099  jz      loc_18004AF6F
0x18004b09f  mov     rax, [rcx]
0x18004b0a2  mov     rax, [rax+10h]
0x18004b0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0ab  jmp     loc_18004AF6F
0x18004b0b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b0b5  jmp     loc_18004AEE5
0x18004b0ba  cmp     word ptr [rax], 0Dh
0x18004b0be  jnz     short loc_18004B0E3
0x18004b0c0  mov     rcx, [rax+8]
0x18004b0c4  test    rcx, rcx
0x18004b0c7  jz      short loc_18004B0E3
0x18004b0c9  mov     rax, [rcx]
0x18004b0cc  lea     r8, [rsp+150h+var_F8]
0x18004b0d1  lea     rdx, _GUID_627d2ca6_e1cd_4898_999d_101308f1d431
0x18004b0d8  mov     rax, [rax]
0x18004b0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0e0  mov     r13d, eax
0x18004b0e3  lea     r12, [rdi+60h]
0x18004b0e7  jmp     loc_18004AE44
0x18004b0ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18004b0f3  test    rcx, rcx
0x18004b0f6  jz      loc_18004B27A
0x18004b0fc  cmp     [rcx+8], sil
0x18004b100  jnz     loc_18004B2C3
0x18004b106  mov     esi, 1
0x18004b10b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18004b112  jb      loc_18004AF6F
0x18004b118  lea     edx, [rsi+11h]
0x18004b11b  lea     r8, WPP_09a18ddabd713d953e6a9cf7fb2dfb47_Traceguids
0x18004b122  jmp     loc_18004B1C4
0x18004b127  mov     rcx, [r12]; pMFT
0x18004b12b  lea     r9, [rsp+150h+merit]; merit
0x18004b130  lea     r8, [rbp+50h+rclsid]; verifier
0x18004b134  mov     [rsp+150h+merit], r15d
0x18004b139  mov     edx, 10h; cbVerifier
0x18004b13e  call    MFGetMFTMerit
0x18004b143  mov     ebx, eax
0x18004b145  test    eax, eax
0x18004b147  js      loc_18004BB69
0x18004b14d  cmp     [rsp+150h+merit], r15d
0x18004b152  jnb     loc_18004AEB1
0x18004b158  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b15f  mov     ebx, 0C00D3703h
0x18004b164  test    rcx, rcx
0x18004b167  jnz     short loc_18004B1A5
0x18004b169  mov     rax, cs:stru_1801FC290.__vftable
0x18004b170  lea     r8, stru_1801FC290
0x18004b177  mov     edx, 7F0h
0x18004b17c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b183  mov     rcx, r8
0x18004b186  mov     rax, [rax+8]
0x18004b18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b18f  test    eax, eax
0x18004b191  jnz     loc_18004BBFA
0x18004b197  lea     rcx, stru_1801F8A30; this
0x18004b19e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b1a5  cmp     byte ptr [rcx+8], 0
0x18004b1a9  jnz     loc_18004BC06
0x18004b1af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18004b1b6  jb      loc_18004AF6F
0x18004b1bc  mov     edx, 25h ; '%'
0x18004b1c1  mov     r8, r14
0x18004b1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b1cb  mov     r9, rdi
0x18004b1ce  mov     dword ptr [rsp+150h+ppv], ebx
0x18004b1d2  mov     rcx, [rcx+10h]
0x18004b1d6  call    WPP_SF_qD
0x18004b1db  jmp     loc_18004AF6F
0x18004b1e0  mov     ebx, r13d
0x18004b1e3  jmp     loc_18004AD87
0x18004b1e8  mov     rax, cs:stru_1801FC290.__vftable
0x18004b1ef  lea     r8, stru_1801FC290
0x18004b1f6  mov     edx, 7F0h
0x18004b1fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b202  mov     rcx, r8
0x18004b205  mov     rax, [rax+8]
0x18004b209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b20e  test    eax, eax
0x18004b210  jnz     short loc_18004B225
0x18004b212  lea     rcx, stru_1801F8A30
  ... truncated ...
```
