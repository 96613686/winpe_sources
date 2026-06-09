# CreateTypeVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,CTDynArray<_GUID,20> &)

- ea: `0x18007b64c`
- end: `0x18007bf2b`
- name: `?CreateTypeVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@AEAV?$CTDynArray@U_GUID@@$0BE@@@@Z`
- size: `2271`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800789cc`

## callees

- `0x180002400`
- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180042d40`
- `0x18006c764`
- `0x1800744d8`
- `0x1800781d4`
- `0x180078224`
- `0x1800782a8`
- `0x18007a794`
- `0x18007b64c`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007b6ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007b6ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007beda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007beda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b708`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b73d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b82e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b8d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b98f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bab2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bb47`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bbe0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bc90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bd3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bdf3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b73d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b82e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b8d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b98f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bab2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bb47`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bbe0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bc90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bd3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007bdf3`

## string_xrefs

- `0x18007b694`: `CreateTypeVectorFromMap`
- `0x18007b79a`: `CreateTypeVectorFromMap`
- `0x18007b88b`: `CreateTypeVectorFromMap`
- `0x18007b932`: `CreateTypeVectorFromMap`
- `0x18007b9ec`: `CreateTypeVectorFromMap`
- `0x18007bb0f`: `CreateTypeVectorFromMap`
- `0x18007bba4`: `CreateTypeVectorFromMap`
- `0x18007bc3d`: `CreateTypeVectorFromMap`
- `0x18007bced`: `CreateTypeVectorFromMap`
- `0x18007bd9c`: `CreateTypeVectorFromMap`
- `0x18007be50`: `CreateTypeVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateTypeVectorFromMap(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // rsi
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned int i; // esi
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v35)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 *v59; // rcx
  CallStackTracing *v60; // rax
  struct CallStackContext *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 *v65; // rcx
  CallStackTracing *v66; // rax
  struct CallStackContext *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 *v71; // rcx
  CallStackTracing *v72; // rax
  struct CallStackContext *v73; // rax
  _QWORD *v74; // rcx
  unsigned int j; // edi
  __int64 v76; // rdx
  _BYTE v78[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v79; // [rsp+38h] [rbp-41h] BYREF
  UINT32 length; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v81; // [rsp+44h] [rbp-35h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  __int64 v83; // [rsp+50h] [rbp-29h] BYREF
  __int64 v84; // [rsp+58h] [rbp-21h] BYREF
  __int128 v85; // [rsp+60h] [rbp-19h] BYREF
  HSTRING string; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF

  v84 = 0;
  v83 = 0;
  v81 = 0;
  pv = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v78, "CreateTypeVectorFromMap", 325);
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v83);
  v9 = -1;
  length = 0;
  do
    ++v9;
  while ( a2[v9] );
  if ( (int)ULongLongToUInt(v9, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length, &hstringHeader, &string);
  v11 = v8(a1, string, &v83);
  if ( v11 < 0 )
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12, v13);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateTypeVectorFromMap", 325, v11);
    }
    if ( g_wppLevels )
    {
      v17 = 40;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v11);
      goto LABEL_124;
    }
    goto LABEL_124;
  }
  v85 = 0;
  if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v83, &v84) < 0 )
  {
    v79 = 0;
    v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            &v83,
            &v79);
    if ( v11 >= 0 )
    {
      v11 = CreateMediaSubTypeFromMap(v79, v56, a3, &v85);
      if ( v11 >= 0 )
      {
        if ( (unsigned int)CTDynArray<_GUID,20>::Add(a4, &v85) )
        {
          v11 = 0;
        }
        else
        {
          v71 = (__int64 *)CallStackTracing::s_wpInstance;
          v11 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v68, v69, v70);
            CallStackTracing::s_wpInstance = v72;
            if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
            {
              v71 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v71 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v71 + 8) )
          {
            v73 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
            if ( *((_DWORD *)v73 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v73, "CreateTypeVectorFromMap", 357, -2147024882);
          }
          if ( g_wppLevels )
          {
            v48 = 49;
LABEL_122:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v48,
              WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
              0,
              -2147024882);
          }
        }
        goto LABEL_123;
      }
      v65 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v62, v63, v64);
        CallStackTracing::s_wpInstance = v66;
        if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
        {
          v65 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v65 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v65 + 8) )
      {
        v67 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v65);
        if ( *((_DWORD *)v67 + 499) != v11 )
          CallStackContext::TraceFailure(v67, "CreateTypeVectorFromMap", 355, v11);
      }
      if ( !g_wppLevels )
      {
LABEL_123:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
        goto LABEL_124;
      }
      v52 = 48;
    }
    else
    {
      v59 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v56, v57, v58);
        CallStackTracing::s_wpInstance = v60;
        if ( v60 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
        {
          v59 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v59 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v59 + 8) )
      {
        v61 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v59);
        if ( *((_DWORD *)v61 + 499) != v11 )
          CallStackContext::TraceFailure(v61, "CreateTypeVectorFromMap", 353, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_123;
      v52 = 47;
    }
LABEL_77:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v52, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v11);
    goto LABEL_123;
  }
  length = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v84 + 48LL))(v84, &length);
  if ( v11 >= 0 )
  {
    if ( length == 1037 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v84 + 304LL))(v84, &v81, &pv);
      if ( v11 >= 0 )
      {
        for ( i = 0; i < v81; ++i )
        {
          v79 = 0;
          v34 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)pv + i);
          v35 = **v34;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
          v11 = v35(v34, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v79);
          if ( v11 < 0 )
          {
            v53 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v38);
              CallStackTracing::s_wpInstance = v54;
              if ( v54
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
              {
                v53 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v53 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v53 + 8) )
            {
              v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
              if ( *((_DWORD *)v55 + 499) != v11 )
                CallStackContext::TraceFailure(v55, "CreateTypeVectorFromMap", 343, v11);
            }
            if ( g_wppLevels )
            {
              v52 = 44;
              goto LABEL_77;
            }
            goto LABEL_123;
          }
          v11 = CreateMediaSubTypeFromMap(v79, v36, a3, &v85);
          if ( v11 < 0 )
          {
            v49 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39, v40, v41);
              CallStackTracing::s_wpInstance = v50;
              if ( v50
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
              {
                v49 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v49 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v49 + 8) )
            {
              v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
              if ( *((_DWORD *)v51 + 499) != v11 )
                CallStackContext::TraceFailure(v51, "CreateTypeVectorFromMap", 345, v11);
            }
            if ( g_wppLevels )
            {
              v52 = 45;
              goto LABEL_77;
            }
            goto LABEL_123;
          }
          if ( !(unsigned int)CTDynArray<_GUID,20>::Add(a4, &v85) )
          {
            v45 = (__int64 *)CallStackTracing::s_wpInstance;
            v11 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
              CallStackTracing::s_wpInstance = v46;
              if ( v46
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
              {
                v45 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v45 + 8) )
            {
              v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
              if ( *((_DWORD *)v47 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v47, "CreateTypeVectorFromMap", 347, -2147024882);
            }
            if ( g_wppLevels )
            {
              v48 = 46;
              goto LABEL_122;
            }
            goto LABEL_123;
          }
          v11 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
        }
      }
      else
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != v11 )
            CallStackContext::TraceFailure(v32, "CreateTypeVectorFromMap", 338, v11);
        }
        if ( g_wppLevels )
        {
          v17 = 43;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v26, "CreateTypeVectorFromMap", 335, -1072875845);
      }
      if ( g_wppLevels )
      {
        v17 = 42;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v21 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != v11 )
        CallStackContext::TraceFailure(v23, "CreateTypeVectorFromMap", 331, v11);
    }
    if ( g_wppLevels )
    {
      v17 = 41;
      goto LABEL_16;
    }
  }
LABEL_124:
  v74 = pv;
  if ( pv )
  {
    for ( j = 0; j < v81; ++j )
    {
      v76 = v74[j];
      if ( v76 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76 + 16LL))(v74[j]);
        *((_QWORD *)pv + j) = 0;
        v74 = pv;
      }
    }
    CoTaskMemFree(v74);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v78);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v83);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v84);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007b64c  mov     [rsp-8+arg_10], rbx
0x18007b651  push    rbp
0x18007b652  push    rsi
0x18007b653  push    rdi
0x18007b654  push    r12
0x18007b656  push    r13
0x18007b658  push    r14
0x18007b65a  push    r15
0x18007b65c  lea     rbp, [rsp-27h]
0x18007b661  sub     rsp, 0A0h
0x18007b668  mov     rax, cs:__security_cookie
0x18007b66f  xor     rax, rsp
0x18007b672  mov     [rbp+57h+var_40], rax
0x18007b676  xor     r12d, r12d
0x18007b679  mov     r15, r8
0x18007b67c  mov     rbx, rdx
0x18007b67f  mov     [rbp+57h+var_78], r12
0x18007b683  mov     rdi, rcx
0x18007b686  mov     [rbp+57h+var_80], r12
0x18007b68a  mov     r8d, 145h; int
0x18007b690  mov     [rbp+57h+var_8C], r12d
0x18007b694  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x18007b69b  mov     [rbp+57h+pv], r12
0x18007b69f  lea     rcx, [rbp+57h+var_A0]; this
0x18007b6a3  mov     r14, r9
0x18007b6a6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007b6ab  mov     rax, [rdi]
0x18007b6ae  lea     rcx, [rbp+57h+var_80]
0x18007b6b2  mov     rsi, [rax+30h]
0x18007b6b6  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18007b6bb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007b6bf  mov     [rbp+57h+length], r12d
0x18007b6c3  inc     rcx; unsigned __int64
0x18007b6c6  cmp     [rbx+rcx*2], r12w
0x18007b6cb  jnz     short loc_18007B6C3
0x18007b6cd  lea     rdx, [rbp+57h+length]; unsigned int *
0x18007b6d1  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007b6d6  mov     r13d, 1
0x18007b6dc  test    eax, eax
0x18007b6de  jns     short loc_18007B6FA
0x18007b6e0  xor     r9d, r9d; lpArguments
0x18007b6e3  xor     r8d, r8d; nNumberOfArguments
0x18007b6e6  mov     edx, r13d; dwExceptionFlags
0x18007b6e9  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007b6ee  call    cs:__imp_RaiseException
0x18007b6f5  nop     dword ptr [rax+rax+00h]
0x18007b6fa  mov     edx, [rbp+57h+length]; length
0x18007b6fd  lea     r9, [rbp+57h+string]; string
0x18007b701  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007b705  mov     rcx, rbx; sourceString
0x18007b708  call    cs:__imp_WindowsCreateStringReference
0x18007b70f  nop     dword ptr [rax+rax+00h]
0x18007b714  mov     rdx, [rbp+57h+string]
0x18007b718  lea     r8, [rbp+57h+var_80]
0x18007b71c  mov     rcx, rdi
0x18007b71f  mov     rax, rsi
0x18007b722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b727  mov     ebx, eax
0x18007b729  test    eax, eax
0x18007b72b  jns     loc_18007B7E4
0x18007b731  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b738  test    rcx, rcx
0x18007b73b  jnz     short loc_18007B784
0x18007b73d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b744  nop     dword ptr [rax+rax+00h]
0x18007b749  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b750  mov     rcx, rax
0x18007b753  test    rax, rax
0x18007b756  jz      short loc_18007B776
0x18007b758  mov     rax, [rax]
0x18007b75b  mov     edx, 7F0h
0x18007b760  mov     rax, [rax+8]
0x18007b764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b769  test    eax, eax
0x18007b76b  jz      short loc_18007B776
0x18007b76d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b774  jmp     short loc_18007B784
0x18007b776  lea     rcx, qword_1800DBF70; this
0x18007b77d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b784  cmp     [rcx+8], r12b
0x18007b788  jz      short loc_18007B7AF
0x18007b78a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b78f  cmp     [rax+7CCh], ebx
0x18007b795  jz      short loc_18007B7AF
0x18007b797  mov     r9d, ebx; int
0x18007b79a  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x18007b7a1  mov     r8d, 145h; int
0x18007b7a7  mov     rcx, rax; this
0x18007b7aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b7af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18007b7b6  jb      loc_18007BE9A
0x18007b7bc  mov     edx, 28h ; '('
0x18007b7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7c8  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007b7cf  xor     r9d, r9d
0x18007b7d2  mov     [rsp+0D0h+var_B0], ebx
0x18007b7d6  mov     rcx, [rcx+10h]
0x18007b7da  call    WPP_SF_qD
0x18007b7df  jmp     loc_18007BE9A
0x18007b7e4  xorps   xmm0, xmm0
0x18007b7e7  lea     rdx, [rbp+57h+var_78]
0x18007b7eb  lea     rcx, [rbp+57h+var_80]
0x18007b7ef  movups  [rbp+57h+var_70], xmm0
0x18007b7f3  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18007b7f8  test    eax, eax
0x18007b7fa  js      loc_18007BC69
0x18007b800  mov     rcx, [rbp+57h+var_78]
0x18007b804  lea     rdx, [rbp+57h+length]
0x18007b808  mov     [rbp+57h+length], r12d
0x18007b80c  mov     rax, [rcx]
0x18007b80f  mov     rax, [rax+30h]
0x18007b813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b818  mov     ebx, eax
0x18007b81a  test    eax, eax
0x18007b81c  jns     loc_18007B8B7
0x18007b822  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b829  test    rcx, rcx
0x18007b82c  jnz     short loc_18007B875
0x18007b82e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b835  nop     dword ptr [rax+rax+00h]
0x18007b83a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b841  mov     rcx, rax
0x18007b844  test    rax, rax
0x18007b847  jz      short loc_18007B867
0x18007b849  mov     rax, [rax]
0x18007b84c  mov     edx, 7F0h
0x18007b851  mov     rax, [rax+8]
0x18007b855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b85a  test    eax, eax
0x18007b85c  jz      short loc_18007B867
0x18007b85e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b865  jmp     short loc_18007B875
0x18007b867  lea     rcx, qword_1800DBF70; this
0x18007b86e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b875  cmp     [rcx+8], r12b
0x18007b879  jz      short loc_18007B8A0
0x18007b87b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b880  cmp     [rax+7CCh], ebx
0x18007b886  jz      short loc_18007B8A0
0x18007b888  mov     r9d, ebx; int
0x18007b88b  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x18007b892  mov     r8d, 14Bh; int
0x18007b898  mov     rcx, rax; this
0x18007b89b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b8a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18007b8a7  jb      loc_18007BE9A
0x18007b8ad  mov     edx, 29h ; ')'
0x18007b8b2  jmp     loc_18007B7C1
0x18007b8b7  cmp     [rbp+57h+length], 40Dh
0x18007b8be  jz      loc_18007B95E
0x18007b8c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b8cb  mov     ebx, 0C00D36BBh
0x18007b8d0  test    rcx, rcx
0x18007b8d3  jnz     short loc_18007B91C
0x18007b8d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b8dc  nop     dword ptr [rax+rax+00h]
0x18007b8e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b8e8  mov     rcx, rax
0x18007b8eb  test    rax, rax
0x18007b8ee  jz      short loc_18007B90E
0x18007b8f0  mov     rax, [rax]
0x18007b8f3  mov     edx, 7F0h
0x18007b8f8  mov     rax, [rax+8]
0x18007b8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b901  test    eax, eax
0x18007b903  jz      short loc_18007B90E
0x18007b905  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b90c  jmp     short loc_18007B91C
0x18007b90e  lea     rcx, qword_1800DBF70; this
0x18007b915  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b91c  cmp     [rcx+8], r12b
0x18007b920  jz      short loc_18007B947
0x18007b922  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b927  cmp     [rax+7CCh], ebx
0x18007b92d  jz      short loc_18007B947
0x18007b92f  mov     r9d, ebx; int
0x18007b932  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x18007b939  mov     r8d, 14Fh; int
0x18007b93f  mov     rcx, rax; this
0x18007b942  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b947  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18007b94e  jb      loc_18007BE9A
0x18007b954  mov     edx, 2Ah ; '*'
0x18007b959  jmp     loc_18007B7C1
0x18007b95e  mov     rcx, [rbp+57h+var_78]
0x18007b962  lea     r8, [rbp+57h+pv]
0x18007b966  lea     rdx, [rbp+57h+var_8C]
0x18007b96a  mov     rax, [rcx]
0x18007b96d  mov     rax, [rax+130h]
0x18007b974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b979  mov     ebx, eax
0x18007b97b  test    eax, eax
0x18007b97d  jns     loc_18007BA18
0x18007b983  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b98a  test    rcx, rcx
0x18007b98d  jnz     short loc_18007B9D6
0x18007b98f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b996  nop     dword ptr [rax+rax+00h]
0x18007b99b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b9a2  mov     rcx, rax
0x18007b9a5  test    rax, rax
0x18007b9a8  jz      short loc_18007B9C8
0x18007b9aa  mov     rax, [rax]
0x18007b9ad  mov     edx, 7F0h
0x18007b9b2  mov     rax, [rax+8]
0x18007b9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b9bb  test    eax, eax
0x18007b9bd  jz      short loc_18007B9C8
0x18007b9bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b9c6  jmp     short loc_18007B9D6
0x18007b9c8  lea     rcx, qword_1800DBF70; this
0x18007b9cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b9d6  cmp     [rcx+8], r12b
0x18007b9da  jz      short loc_18007BA01
0x18007b9dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b9e1  cmp     [rax+7CCh], ebx
0x18007b9e7  jz      short loc_18007BA01
0x18007b9e9  mov     r9d, ebx; int
0x18007b9ec  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x18007b9f3  mov     r8d, 152h; int
0x18007b9f9  mov     rcx, rax; this
0x18007b9fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ba01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18007ba08  jb      loc_18007BE9A
0x18007ba0e  mov     edx, 2Bh ; '+'
0x18007ba13  jmp     loc_18007B7C1
0x18007ba18  mov     esi, r12d
0x18007ba1b  cmp     esi, [rbp+57h+var_8C]
0x18007ba1e  jnb     loc_18007BE9A
0x18007ba24  mov     rax, [rbp+57h+pv]
0x18007ba28  mov     [rbp+57h+var_98], r12
0x18007ba2c  mov     ecx, esi
0x18007ba2e  mov     rdi, [rax+rcx*8]
0x18007ba32  lea     rcx, [rbp+57h+var_98]
0x18007ba36  mov     rax, [rdi]
0x18007ba39  mov     rbx, [rax]
0x18007ba3c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007ba41  lea     r8, [rbp+57h+var_98]
0x18007ba45  mov     rcx, rdi
0x18007ba48  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007ba4f  mov     rax, rbx
0x18007ba52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ba57  mov     ebx, eax
0x18007ba59  test    eax, eax
0x18007ba5b  js      loc_18007BBD4
0x18007ba61  mov     rcx, [rbp+57h+var_98]
0x18007ba65  lea     r9, [rbp+57h+var_70]
0x18007ba69  mov     r8, r15
0x18007ba6c  call    ?CreateMediaSubTypeFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@PEAU5@@Z; CreateMediaSubTypeFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,_GUID *)
0x18007ba71  mov     ebx, eax
0x18007ba73  test    eax, eax
0x18007ba75  js      loc_18007BB3B
0x18007ba7b  lea     rdx, [rbp+57h+var_70]
0x18007ba7f  mov     rcx, r14
0x18007ba82  call    ?Add@?$CTDynArray@U_GUID@@$0BE@@@QEAAHAEBU_GUID@@PEAK@Z; CTDynArray<_GUID,20>::Add(_GUID const &,ulong *)
0x18007ba87  test    eax, eax
0x18007ba89  jz      short loc_18007BA9F
0x18007ba8b  lea     rcx, [rbp+57h+var_98]
0x18007ba8f  mov     ebx, r12d
0x18007ba92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007ba97  add     esi, r13d
0x18007ba9a  jmp     loc_18007BA1B
0x18007ba9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007baa6  mov     edi, 8007000Eh
0x18007baab  mov     ebx, edi
0x18007baad  test    rcx, rcx
0x18007bab0  jnz     short loc_18007BAF9
0x18007bab2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007bab9  nop     dword ptr [rax+rax+00h]
0x18007babe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007bac5  mov     rcx, rax
0x18007bac8  test    rax, rax
0x18007bacb  jz      short loc_18007BAEB
0x18007bacd  mov     rax, [rax]
0x18007bad0  mov     edx, 7F0h
0x18007bad5  mov     rax, [rax+8]
0x18007bad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bade  test    eax, eax
0x18007bae0  jz      short loc_18007BAEB
0x18007bae2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007bae9  jmp     short loc_18007BAF9
0x18007baeb  lea     rcx, qword_1800DBF70; this
0x18007baf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007baf9  cmp     [rcx+8], r12b
0x18007bafd  jz      short loc_18007BB24
0x18007baff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007bb04  cmp     [rax+7CCh], edi
0x18007bb0a  jz      short loc_18007BB24
0x18007bb0c  mov     r9d, edi; int
0x18007bb0f  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x18007bb16  mov     r8d, 15Bh; int
0x18007bb1c  mov     rcx, rax; this
0x18007bb1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007bb24  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18007bb2b  jb      loc_18007BE91
0x18007bb31  mov     edx, 2Eh ; '.'
0x18007bb36  jmp     loc_18007BE73
0x18007bb3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007bb42  test    rcx, rcx
0x18007bb45  jnz     short loc_18007BB8E
  ... truncated ...
```
