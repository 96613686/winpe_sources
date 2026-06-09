# CWMPropHandlerBase::AddProperty(_tagpropertykey const &,tagPROPVARIANT const &,CMFProperty::MF_MDACCESS,CMFProperty::MF_MDVALUESOURCE)

- ea: `0x180042130`
- end: `0x180042b58`
- name: `?AddProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@W4MF_MDACCESS@CMFProperty@@W4MF_MDVALUESOURCE@5@@Z`
- size: `2600`
- prototype: `int __high(const struct _tagpropertykey *, const struct tagPROPVARIANT *, enum CMFProperty::MF_MDACCESS, enum CMFProperty::MF_MDVALUESOURCE)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callees

- `0x180001e80`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003abd0`
- `0x18003d458`
- `0x18003e688`
- `0x180042130`
- `0x180056010`

## import_xrefs

- `PROPSYS!PSStringFromPropertyKey` at `0x1800423bb`
- `PROPSYS!PSStringFromPropertyKey` at `0x1800423bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800421b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800423d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004248f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042546`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800425fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042706`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800427c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042877`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042926`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800429dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042a73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800421b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042363`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800423d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004248f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042546`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800425fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042706`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800427c3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042877`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042926`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800429dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042a73`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::AddProperty(__int64 *a1, const PROPERTYKEY *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v8; // rax
  __int64 (__fastcall *v9)(__int64 *, const PROPERTYKEY *, __int64 *); // rax
  __int64 v10; // rdx
  HRESULT v11; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r15
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  _BYTE v67[8]; // [rsp+30h] [rbp-81h] BYREF
  __int64 v68; // [rsp+38h] [rbp-79h] BYREF
  int v69; // [rsp+40h] [rbp-71h] BYREF
  __int64 v70; // [rsp+48h] [rbp-69h] BYREF
  WCHAR psz[56]; // [rsp+50h] [rbp-61h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v67, "CWMPropHandlerBase::AddProperty", 839);
  v8 = *a1;
  v68 = 0;
  v70 = 0;
  v9 = *(__int64 (__fastcall **)(__int64 *, const PROPERTYKEY *, __int64 *))(v8 + 56);
  v69 = 0;
  v11 = v9(a1, a2, &v68);
  if ( v11 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropHandlerBase::AddProperty", 847, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_151;
    v15 = 70;
    goto LABEL_150;
  }
  if ( !(unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(a1 + 163, a2, &v70) )
  {
    if ( *((_DWORD *)a1 + 228) )
    {
      v11 = PSStringFromPropertyKey(a2, psz, 0x32u);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, WCHAR *))(*(_QWORD *)v68 + 200LL))(v68, MF_MD_NAME, psz);
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v68 + 168LL))(
                  v68,
                  MF_MD_ACCESSTYPE,
                  1);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v68 + 168LL))(
                    v68,
                    MF_MD_EXTENDEDPROP,
                    1);
            if ( v11 >= 0 )
              goto LABEL_25;
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
              CallStackTracing::s_wpInstance = v39;
              if ( v39
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
              {
                v38 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v38 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v38 + 8) )
            {
              v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
              if ( *((_DWORD *)v40 + 499) != v11 )
                CallStackContext::TraceFailure(v40, "CWMPropHandlerBase::AddProperty", 868, v11);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_151;
            v15 = 75;
          }
          else
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34);
              CallStackTracing::s_wpInstance = v36;
              if ( v36
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v35 = &qword_18006EB20;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
              }
            }
            if ( *((_BYTE *)v35 + 8) )
            {
              v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
              if ( *((_DWORD *)v37 + 499) != v11 )
                CallStackContext::TraceFailure(v37, "CWMPropHandlerBase::AddProperty", 864, v11);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_151;
            v15 = 74;
          }
        }
        else
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_18006EB20;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != v11 )
              CallStackContext::TraceFailure(v33, "CWMPropHandlerBase::AddProperty", 863, v11);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_151;
          v15 = 73;
        }
      }
      else
      {
        v27 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_18006EB20;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v11 )
            CallStackContext::TraceFailure(v29, "CWMPropHandlerBase::AddProperty", 862, v11);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_151;
        v15 = 72;
      }
    }
    else
    {
      v63 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147287035;
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v64;
        if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
        {
          v63 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v63 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v63 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
        if ( *((_DWORD *)v65 + 499) != -2147287035 )
          CallStackContext::TraceFailure(v65, "CWMPropHandlerBase::AddProperty", 875, -2147287035);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_151;
      v15 = 76;
    }
LABEL_150:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, a1, v11);
LABEL_151:
    if ( v68 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      v68 = 0;
    }
    goto LABEL_153;
  }
  v17 = v70;
  v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 256LL))(v70, v68);
  if ( v11 < 0 )
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != v11 )
        CallStackContext::TraceFailure(v21, "CWMPropHandlerBase::AddProperty", 854, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_151;
    v15 = 71;
    goto LABEL_150;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
LABEL_25:
  if ( !a5 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 288LL))(v68, a3);
    if ( v11 < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v41 + 499) != v11 )
          CallStackContext::TraceFailure(v41, "CWMPropHandlerBase::AddProperty", 880, v11);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_151;
      v15 = 77;
      goto LABEL_150;
    }
    goto LABEL_94;
  }
  if ( a5 != 1 )
  {
    v60 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
      CallStackTracing::s_wpInstance = v61;
      if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
      {
        v60 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v60 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v60 + 8) )
    {
      v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
      if ( *((_DWORD *)v62 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v62, "CWMPropHandlerBase::AddProperty", 889, -2147418113);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_151;
    v55 = 79;
LABEL_116:
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v55,
      WPP_d497573e8d0434bb74893564de0342d6_Traceguids,
      a1,
      -2147418113);
    goto LABEL_151;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 296LL))(v68, a3);
  if ( v11 < 0 )
  {
    v43 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42);
      CallStackTracing::s_wpInstance = v44;
      if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v43 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
      if ( *((_DWORD *)v45 + 499) != v11 )
        CallStackContext::TraceFailure(v45, "CWMPropHandlerBase::AddProperty", 884, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_151;
    v15 = 78;
    goto LABEL_150;
  }
LABEL_94:
  v46 = v68;
  *(GUID *)(v68 + 76) = a2->fmtid;
  *(_DWORD *)(v46 + 92) = a2->pid;
  v11 = CTBucketHash<_tagpropertykey,CMFProperty *>::Insert(a1 + 6, a2, &v68);
  if ( v11 < 0 )
  {
    v48 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
      CallStackTracing::s_wpInstance = v49;
      if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      {
        v48 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v48 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v48 + 8) )
    {
      v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
      if ( *((_DWORD *)v50 + 499) != v11 )
        CallStackContext::TraceFailure(v50, "CWMPropHandlerBase::AddProperty", 894, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_151;
    v15 = 80;
    goto LABEL_150;
  }
  if ( !(unsigned int)CTDynArray<_tagpropertykey,20>::Add(a1 + 53, a2, &v69) )
  {
    v52 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
      CallStackTracing::s_wpInstance = v53;
      if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
      {
        v52 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v52 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v52 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
      if ( *((_DWORD *)v54 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v54, "CWMPropHandlerBase::AddProperty", 898, -2147418113);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_151;
    v55 = 81;
    goto LABEL_116;
  }
  v11 = CTBucketHash<_tagpropertykey,CMFProperty *>::Insert(a1 + 163, a2, &v68);
  if ( v11 < 0 )
  {
    v57 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56);
      CallStackTracing::s_wpInstance = v58;
      if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
      {
        v57 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v57 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v57 + 8) )
    {
      v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
      if ( *((_DWORD *)v59 + 499) != v11 )
        CallStackContext::TraceFailure(v59, "CWMPropHandlerBase::AddProperty", 901, v11);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_151;
    v15 = 82;
    goto LABEL_150;
  }
  if ( v68 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v68);
LABEL_153:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v67);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180042130  mov     [rsp-8+arg_18], rbx
0x180042135  push    rbp
0x180042136  push    rsi
0x180042137  push    rdi
0x180042138  push    r12
0x18004213a  push    r13
0x18004213c  push    r14
0x18004213e  push    r15
0x180042140  lea     rbp, [rsp-1Fh]
0x180042145  sub     rsp, 0D0h
0x18004214c  mov     rax, cs:__security_cookie
0x180042153  xor     rax, rsp
0x180042156  mov     [rbp+4Fh+var_40], rax
0x18004215a  mov     r13, r8
0x18004215d  mov     r14, rdx
0x180042160  mov     rsi, rcx
0x180042163  lea     rdx, aCwmprophandler_3; "CWMPropHandlerBase::AddProperty"
0x18004216a  mov     r8d, 347h; int
0x180042170  lea     rcx, [rsp+100h+var_D0]; this
0x180042175  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004217a  mov     rax, [rsi]
0x18004217d  lea     r8, [rbp+4Fh+var_C8]
0x180042181  xor     r15d, r15d
0x180042184  mov     rdx, r14
0x180042187  mov     rcx, rsi
0x18004218a  mov     [rbp+4Fh+var_C8], r15
0x18004218e  mov     [rbp+4Fh+var_B8], r15
0x180042192  mov     rax, [rax+38h]
0x180042196  mov     [rbp+4Fh+var_C0], r15d
0x18004219a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004219f  mov     ebx, eax
0x1800421a1  test    eax, eax
0x1800421a3  jns     loc_18004223C
0x1800421a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800421b0  test    rcx, rcx
0x1800421b3  jnz     short loc_1800421F6
0x1800421b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800421bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800421c2  mov     rcx, rax
0x1800421c5  test    rax, rax
0x1800421c8  jz      short loc_1800421E8
0x1800421ca  mov     rax, [rax]
0x1800421cd  mov     edx, 7F0h
0x1800421d2  mov     rax, [rax+8]
0x1800421d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421db  test    eax, eax
0x1800421dd  jz      short loc_1800421E8
0x1800421df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800421e6  jmp     short loc_1800421F6
0x1800421e8  lea     rcx, qword_18006EB20; this
0x1800421ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800421f6  cmp     [rcx+8], r15b
0x1800421fa  jz      short loc_180042221
0x1800421fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042201  cmp     [rax+7CCh], ebx
0x180042207  jz      short loc_180042221
0x180042209  mov     r9d, ebx; int
0x18004220c  lea     rdx, aCwmprophandler_3; "CWMPropHandlerBase::AddProperty"
0x180042213  mov     r8d, 34Fh; int
0x180042219  mov     rcx, rax; this
0x18004221c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042221  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042226  mov     edi, 1
0x18004222b  cmp     al, dil
0x18004222e  jb      loc_180042B0C
0x180042234  lea     edx, [rdi+45h]
0x180042237  jmp     loc_180042AEE
0x18004223c  lea     r12, [rsi+518h]
0x180042243  mov     rdx, r14
0x180042246  mov     rcx, r12
0x180042249  lea     r8, [rbp+4Fh+var_B8]
0x18004224d  call    ?Remove@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(_tagpropertykey const &,CMFProperty * &)
0x180042252  mov     edi, 1
0x180042257  test    eax, eax
0x180042259  jz      loc_1800423A1
0x18004225f  mov     r15, [rbp+4Fh+var_B8]
0x180042263  mov     rdx, [rbp+4Fh+var_C8]
0x180042267  mov     rcx, r15
0x18004226a  mov     rax, [r15]
0x18004226d  mov     rax, [rax+100h]
0x180042274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042279  mov     ebx, eax
0x18004227b  test    eax, eax
0x18004227d  jns     loc_180042316
0x180042283  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004228a  xor     r15d, r15d
0x18004228d  test    rcx, rcx
0x180042290  jnz     short loc_1800422D3
0x180042292  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042298  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004229f  mov     rcx, rax
0x1800422a2  test    rax, rax
0x1800422a5  jz      short loc_1800422C5
0x1800422a7  mov     rax, [rax]
0x1800422aa  mov     edx, 7F0h
0x1800422af  mov     rax, [rax+8]
0x1800422b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800422b8  test    eax, eax
0x1800422ba  jz      short loc_1800422C5
0x1800422bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800422c3  jmp     short loc_1800422D3
0x1800422c5  lea     rcx, qword_18006EB20; this
0x1800422cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800422d3  cmp     [rcx+8], r15b
0x1800422d7  jz      short loc_1800422FE
0x1800422d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800422de  cmp     [rax+7CCh], ebx
0x1800422e4  jz      short loc_1800422FE
0x1800422e6  mov     r9d, ebx; int
0x1800422e9  lea     rdx, aCwmprophandler_3; "CWMPropHandlerBase::AddProperty"
0x1800422f0  mov     r8d, 356h; int
0x1800422f6  mov     rcx, rax; this
0x1800422f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800422fe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042303  cmp     al, dil
0x180042306  jb      loc_180042B0C
0x18004230c  mov     edx, 47h ; 'G'
0x180042311  jmp     loc_180042AEE
0x180042316  mov     rax, [r15]
0x180042319  mov     rcx, r15
0x18004231c  mov     rax, [rax+10h]
0x180042320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042325  xor     r15d, r15d
0x180042328  mov     eax, [rbp+4Fh+arg_20]
0x18004232b  test    eax, eax
0x18004232d  jnz     loc_1800426D2
0x180042333  mov     rcx, [rbp+4Fh+var_C8]
0x180042337  mov     rdx, r13
0x18004233a  mov     rax, [rcx]
0x18004233d  mov     rax, [rax+120h]
0x180042344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042349  mov     ebx, eax
0x18004234b  test    eax, eax
0x18004234d  jns     loc_18004278A
0x180042353  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004235a  test    rcx, rcx
0x18004235d  jnz     loc_18004268F
0x180042363  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042369  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042370  mov     rcx, rax
0x180042373  test    rax, rax
0x180042376  jz      loc_180042681
0x18004237c  mov     rax, [rax]
0x18004237f  mov     edx, 7F0h
0x180042384  mov     rax, [rax+8]
0x180042388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004238d  test    eax, eax
0x18004238f  jz      loc_180042681
0x180042395  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004239c  jmp     loc_18004268F
0x1800423a1  cmp     [rsi+390h], r15d
0x1800423a8  jz      loc_180042A62
0x1800423ae  mov     r8d, 32h ; '2'; cch
0x1800423b4  lea     rdx, [rbp+4Fh+psz]; psz
0x1800423b8  mov     rcx, r14; pkey
0x1800423bb  call    cs:__imp_PSStringFromPropertyKey
0x1800423c1  mov     ebx, eax
0x1800423c3  test    eax, eax
0x1800423c5  jns     loc_18004245B
0x1800423cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800423d2  test    rcx, rcx
0x1800423d5  jnz     short loc_180042418
0x1800423d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800423dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800423e4  mov     rcx, rax
0x1800423e7  test    rax, rax
0x1800423ea  jz      short loc_18004240A
0x1800423ec  mov     rax, [rax]
0x1800423ef  mov     edx, 7F0h
0x1800423f4  mov     rax, [rax+8]
0x1800423f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423fd  test    eax, eax
0x1800423ff  jz      short loc_18004240A
0x180042401  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042408  jmp     short loc_180042418
0x18004240a  lea     rcx, qword_18006EB20; this
0x180042411  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042418  cmp     [rcx+8], r15b
0x18004241c  jz      short loc_180042443
0x18004241e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042423  cmp     [rax+7CCh], ebx
0x180042429  jz      short loc_180042443
0x18004242b  mov     r9d, ebx; int
0x18004242e  lea     rdx, aCwmprophandler_3; "CWMPropHandlerBase::AddProperty"
0x180042435  mov     r8d, 35Eh; int
0x18004243b  mov     rcx, rax; this
0x18004243e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042443  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042448  cmp     al, dil
0x18004244b  jb      loc_180042B0C
0x180042451  mov     edx, 48h ; 'H'
0x180042456  jmp     loc_180042AEE
0x18004245b  mov     rcx, [rbp+4Fh+var_C8]
0x18004245f  lea     r8, [rbp+4Fh+psz]
0x180042463  lea     rdx, MF_MD_NAME
0x18004246a  mov     rax, [rcx]
0x18004246d  mov     rax, [rax+0C8h]
0x180042474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042479  mov     ebx, eax
0x18004247b  test    eax, eax
0x18004247d  jns     loc_180042513
0x180042483  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004248a  test    rcx, rcx
0x18004248d  jnz     short loc_1800424D0
0x18004248f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042495  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004249c  mov     rcx, rax
0x18004249f  test    rax, rax
0x1800424a2  jz      short loc_1800424C2
0x1800424a4  mov     rax, [rax]
0x1800424a7  mov     edx, 7F0h
0x1800424ac  mov     rax, [rax+8]
0x1800424b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424b5  test    eax, eax
0x1800424b7  jz      short loc_1800424C2
0x1800424b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800424c0  jmp     short loc_1800424D0
0x1800424c2  lea     rcx, qword_18006EB20; this
0x1800424c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800424d0  cmp     [rcx+8], r15b
0x1800424d4  jz      short loc_1800424FB
0x1800424d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800424db  cmp     [rax+7CCh], ebx
0x1800424e1  jz      short loc_1800424FB
0x1800424e3  mov     r9d, ebx; int
0x1800424e6  lea     rdx, aCwmprophandler_3; "CWMPropHandlerBase::AddProperty"
0x1800424ed  mov     r8d, 35Fh; int
0x1800424f3  mov     rcx, rax; this
0x1800424f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800424fb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042500  cmp     al, dil
0x180042503  jb      loc_180042B0C
0x180042509  mov     edx, 49h ; 'I'
0x18004250e  jmp     loc_180042AEE
0x180042513  mov     rcx, [rbp+4Fh+var_C8]
0x180042517  lea     rdx, MF_MD_ACCESSTYPE
0x18004251e  mov     r8d, edi
0x180042521  mov     rax, [rcx]
0x180042524  mov     rax, [rax+0A8h]
0x18004252b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042530  mov     ebx, eax
0x180042532  test    eax, eax
0x180042534  jns     loc_1800425CA
0x18004253a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042541  test    rcx, rcx
0x180042544  jnz     short loc_180042587
0x180042546  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004254c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042553  mov     rcx, rax
0x180042556  test    rax, rax
0x180042559  jz      short loc_180042579
0x18004255b  mov     rax, [rax]
0x18004255e  mov     edx, 7F0h
0x180042563  mov     rax, [rax+8]
0x180042567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004256c  test    eax, eax
0x18004256e  jz      short loc_180042579
0x180042570  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042577  jmp     short loc_180042587
0x180042579  lea     rcx, qword_18006EB20; this
0x180042580  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042587  cmp     [rcx+8], r15b
0x18004258b  jz      short loc_1800425B2
0x18004258d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042592  cmp     [rax+7CCh], ebx
0x180042598  jz      short loc_1800425B2
0x18004259a  mov     r9d, ebx; int
0x18004259d  lea     rdx, aCwmprophandler_3; "CWMPropHandlerBase::AddProperty"
0x1800425a4  mov     r8d, 360h; int
0x1800425aa  mov     rcx, rax; this
0x1800425ad  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800425b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800425b7  cmp     al, dil
0x1800425ba  jb      loc_180042B0C
0x1800425c0  mov     edx, 4Ah ; 'J'
0x1800425c5  jmp     loc_180042AEE
0x1800425ca  mov     rcx, [rbp+4Fh+var_C8]
0x1800425ce  lea     rdx, MF_MD_EXTENDEDPROP
0x1800425d5  mov     r8d, edi
0x1800425d8  mov     rax, [rcx]
0x1800425db  mov     rax, [rax+0A8h]
0x1800425e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425e7  mov     ebx, eax
0x1800425e9  test    eax, eax
0x1800425eb  jns     loc_180042328
0x1800425f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800425f8  test    rcx, rcx
0x1800425fb  jnz     short loc_18004263E
0x1800425fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042603  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004260a  mov     rcx, rax
0x18004260d  test    rax, rax
0x180042610  jz      short loc_180042630
0x180042612  mov     rax, [rax]
0x180042615  mov     edx, 7F0h
0x18004261a  mov     rax, [rax+8]
0x18004261e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042623  test    eax, eax
0x180042625  jz      short loc_180042630
0x180042627  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
