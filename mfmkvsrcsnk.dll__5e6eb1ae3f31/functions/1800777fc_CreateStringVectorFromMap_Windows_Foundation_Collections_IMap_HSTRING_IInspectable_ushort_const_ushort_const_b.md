# CreateStringVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,bool,CTDynArray<HSTRING__ *,20> &)

- ea: `0x1800777fc`
- end: `0x180077fae`
- name: `?CreateStringVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG1_NAEAV?$CTDynArray@PEAUHSTRING__@@$0BE@@@@Z`
- size: `1970`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007559c`

## callees

- `0x1800023e0`
- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180069a78`
- `0x180071330`
- `0x180074e04`
- `0x180074e54`
- `0x180074ea4`
- `0x1800775b0`
- `0x1800777fc`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077f63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077f63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180077a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180077da5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180077a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180077da5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077acc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077acc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077d8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077882`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800778b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077af2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077b8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077c1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077ce3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077dc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077e79`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800778b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077af2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077b8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077c1b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077ce3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077dc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180077e79`

## string_xrefs

- `0x18007782c`: `CreateStringVectorFromMap`
- `0x180077b49`: `CreateStringVectorFromMap`
- `0x180077be3`: `CreateStringVectorFromMap`
- `0x180077c72`: `CreateStringVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringVectorFromMap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 *); // rbx
  __int64 v8; // rdx
  HRESULT v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned int i; // esi
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  HSTRING v61; // rcx
  __int64 *v62; // rcx
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  _QWORD *v65; // rcx
  unsigned int j; // edi
  __int64 v67; // rdx
  HSTRING v69; // [rsp+30h] [rbp-41h] BYREF
  _BYTE v70[8]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v71; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v72; // [rsp+48h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-21h] BYREF
  __int64 v74; // [rsp+58h] [rbp-19h] BYREF
  __int64 v75; // [rsp+60h] [rbp-11h] BYREF
  HSTRING v76; // [rsp+68h] [rbp-9h] BYREF
  HSTRING string; // [rsp+70h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+7h] BYREF

  v75 = 0;
  v74 = 0;
  v72 = 0;
  pv = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v70, "CreateStringVectorFromMap", 607);
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v74);
  WindowsCreateStringReference(L"InputType", 9u, &hstringHeader, &string);
  v9 = v7(a1, string, &v74);
  if ( v9 < 0 )
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStringVectorFromMap", 607, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 80;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
      goto LABEL_103;
    }
    goto LABEL_103;
  }
  if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v74, &v75) < 0 )
  {
    v71 = 0;
    v9 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v74,
           &v71);
    if ( v9 < 0 )
    {
      v49 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
        if ( *((_DWORD *)v51 + 499) != v9 )
          CallStackContext::TraceFailure(v51, "CreateStringVectorFromMap", 641, v9);
      }
      if ( g_wppLevels )
      {
        v45 = 86;
LABEL_63:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
      }
      goto LABEL_102;
    }
    WindowsDeleteString(0);
    v69 = 0;
    if ( (int)CreateStringFromMap(v71, a3, &v69) >= 0
      || (WindowsDeleteString(v69), v69 = 0, v9 = WindowsCreateString(&word_1800B72F8, 0, &v69), v9 >= 0) )
    {
      v76 = v69;
      if ( (unsigned int)CTDynArray<HSTRING__ *,20>::Add(a5, &v76) )
      {
        v9 = 0;
        v69 = 0;
        v61 = 0;
LABEL_101:
        WindowsDeleteString(v61);
        v69 = 0;
LABEL_102:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
        goto LABEL_103;
      }
      v62 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
        CallStackTracing::s_wpInstance = v63;
        if ( v63 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
        {
          v62 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v62 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v62 + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v62);
        if ( *((_DWORD *)v64 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v64, "CreateStringVectorFromMap", 657, -2147024882);
      }
      if ( g_wppLevels )
      {
        v41 = 89;
LABEL_99:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v41,
          WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
          0,
          -2147024882);
      }
    }
    else
    {
      v55 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
        CallStackTracing::s_wpInstance = v56;
        if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
        {
          v55 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v55 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v55 + 8) )
      {
        v57 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
        if ( *((_DWORD *)v57 + 499) != v9 )
          CallStackContext::TraceFailure(v57, "CreateStringVectorFromMap", 648, v9);
      }
      if ( g_wppLevels )
      {
        v37 = 87;
LABEL_42:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v9);
      }
    }
LABEL_100:
    v61 = v69;
    goto LABEL_101;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v75 + 304LL))(v75, &v72, &pv);
  if ( v9 >= 0 )
  {
    for ( i = 0; i < v72; ++i )
    {
      v71 = 0;
      v23 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)pv + i);
      v24 = **v23;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
      v9 = v24(v23, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v71);
      if ( v9 < 0 )
      {
        v42 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26, v27);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != v9 )
            CallStackContext::TraceFailure(v44, "CreateStringVectorFromMap", 616, v9);
        }
        if ( g_wppLevels )
        {
          v45 = 82;
          goto LABEL_63;
        }
        goto LABEL_102;
      }
      v69 = 0;
      WindowsDeleteString(0);
      v69 = 0;
      if ( (int)CreateStringFromMap(v71, a3, &v69) < 0 )
      {
        WindowsDeleteString(v69);
        v69 = 0;
        v9 = WindowsCreateString(&word_1800B72F8, 0, &v69);
        if ( v9 < 0 )
        {
          v34 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
            CallStackTracing::s_wpInstance = v35;
            if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v34 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v34 + 8) )
          {
            v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
            if ( *((_DWORD *)v36 + 499) != v9 )
              CallStackContext::TraceFailure(v36, "CreateStringVectorFromMap", 623, v9);
          }
          if ( g_wppLevels )
          {
            v37 = 83;
            goto LABEL_42;
          }
          goto LABEL_100;
        }
      }
      v76 = v69;
      if ( !(unsigned int)CTDynArray<HSTRING__ *,20>::Add(a5, &v76) )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        v9 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v40, "CreateStringVectorFromMap", 632, -2147024882);
        }
        if ( g_wppLevels )
        {
          v41 = 85;
          goto LABEL_99;
        }
        goto LABEL_100;
      }
      v69 = 0;
      v9 = 0;
      WindowsDeleteString(0);
      v69 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
    }
  }
  else
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != v9 )
        CallStackContext::TraceFailure(v21, "CreateStringVectorFromMap", 611, v9);
    }
    if ( g_wppLevels )
    {
      v15 = 81;
      goto LABEL_12;
    }
  }
LABEL_103:
  v65 = pv;
  if ( pv )
  {
    for ( j = 0; j < v72; ++j )
    {
      v67 = v65[j];
      if ( v67 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v67 + 16LL))(v65[j]);
        *((_QWORD *)pv + j) = 0;
        v65 = pv;
      }
    }
    CoTaskMemFree(v65);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v70);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v75);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800777fc  mov     [rsp-8+arg_8], rbx
0x180077801  mov     [rsp-8+arg_18], rsi
0x180077806  push    rbp
0x180077807  push    rdi
0x180077808  push    r12
0x18007780a  push    r14
0x18007780c  push    r15
0x18007780e  lea     rbp, [rsp-2Fh]
0x180077813  sub     rsp, 0A0h
0x18007781a  mov     rax, cs:__security_cookie
0x180077821  xor     rax, rsp
0x180077824  mov     [rbp+4Fh+var_30], rax
0x180077828  mov     r14, [rbp+4Fh+arg_20]
0x18007782c  lea     rsi, aCreatestringve; "CreateStringVectorFromMap"
0x180077833  xor     r12d, r12d
0x180077836  mov     r15, r8
0x180077839  mov     rdi, rcx
0x18007783c  mov     [rbp+4Fh+var_60], r12
0x180077840  mov     rdx, rsi; char *
0x180077843  mov     [rbp+4Fh+var_68], r12
0x180077847  mov     r8d, 25Fh; int
0x18007784d  mov     [rbp+4Fh+var_78], r12d
0x180077851  lea     rcx, [rbp+4Fh+var_88]; this
0x180077855  mov     [rbp+4Fh+pv], r12
0x180077859  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007785e  mov     rax, [rdi]
0x180077861  lea     rcx, [rbp+4Fh+var_68]
0x180077865  mov     rbx, [rax+30h]
0x180077869  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18007786e  lea     r9, [rbp+4Fh+string]; string
0x180077872  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180077876  lea     edx, [r12+9]; length
0x18007787b  lea     rcx, aInputtype; "InputType"
0x180077882  call    cs:__imp_WindowsCreateStringReference
0x180077888  mov     rdx, [rbp+4Fh+string]
0x18007788c  lea     r8, [rbp+4Fh+var_68]
0x180077890  mov     rcx, rdi
0x180077893  mov     rax, rbx
0x180077896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007789b  mov     ebx, eax
0x18007789d  test    eax, eax
0x18007789f  jns     loc_18007794E
0x1800778a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778ac  test    rcx, rcx
0x1800778af  jnz     short loc_1800778F2
0x1800778b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800778b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778be  mov     rcx, rax
0x1800778c1  test    rax, rax
0x1800778c4  jz      short loc_1800778E4
0x1800778c6  mov     rax, [rax]
0x1800778c9  mov     edx, 7F0h
0x1800778ce  mov     rax, [rax+8]
0x1800778d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778d7  test    eax, eax
0x1800778d9  jz      short loc_1800778E4
0x1800778db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778e2  jmp     short loc_1800778F2
0x1800778e4  lea     rcx, qword_1800D6F70; this
0x1800778eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800778f2  cmp     [rcx+8], r12b
0x1800778f6  jz      short loc_180077919
0x1800778f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800778fd  cmp     [rax+7CCh], ebx
0x180077903  jz      short loc_180077919
0x180077905  mov     r9d, ebx; int
0x180077908  mov     r8d, 25Fh; int
0x18007790e  mov     rdx, rsi; char *
0x180077911  mov     rcx, rax; this
0x180077914  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077919  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077920  jb      loc_180077F24
0x180077926  mov     edx, 50h ; 'P'
0x18007792b  mov     rcx, cs:WPP_GLOBAL_Control
0x180077932  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180077939  xor     r9d, r9d
0x18007793c  mov     [rsp+0C0h+var_A0], ebx
0x180077940  mov     rcx, [rcx+10h]
0x180077944  call    WPP_SF_qD
0x180077949  jmp     loc_180077F24
0x18007794e  lea     rdx, [rbp+4Fh+var_60]
0x180077952  lea     rcx, [rbp+4Fh+var_68]
0x180077956  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18007795b  test    eax, eax
0x18007795d  js      loc_180077CBC
0x180077963  mov     rcx, [rbp+4Fh+var_60]
0x180077967  lea     r8, [rbp+4Fh+pv]
0x18007796b  lea     rdx, [rbp+4Fh+var_78]
0x18007796f  mov     rax, [rcx]
0x180077972  mov     rax, [rax+130h]
0x180077979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007797e  mov     ebx, eax
0x180077980  test    eax, eax
0x180077982  jns     loc_180077A13
0x180077988  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007798f  test    rcx, rcx
0x180077992  jnz     short loc_1800779D5
0x180077994  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007799a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800779a1  mov     rcx, rax
0x1800779a4  test    rax, rax
0x1800779a7  jz      short loc_1800779C7
0x1800779a9  mov     rax, [rax]
0x1800779ac  mov     edx, 7F0h
0x1800779b1  mov     rax, [rax+8]
0x1800779b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779ba  test    eax, eax
0x1800779bc  jz      short loc_1800779C7
0x1800779be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800779c5  jmp     short loc_1800779D5
0x1800779c7  lea     rcx, qword_1800D6F70; this
0x1800779ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800779d5  cmp     [rcx+8], r12b
0x1800779d9  jz      short loc_1800779FC
0x1800779db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800779e0  cmp     [rax+7CCh], ebx
0x1800779e6  jz      short loc_1800779FC
0x1800779e8  mov     r9d, ebx; int
0x1800779eb  mov     r8d, 263h; int
0x1800779f1  mov     rdx, rsi; char *
0x1800779f4  mov     rcx, rax; this
0x1800779f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800779fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077a03  jb      loc_180077F24
0x180077a09  mov     edx, 51h ; 'Q'
0x180077a0e  jmp     loc_18007792B
0x180077a13  mov     esi, r12d
0x180077a16  cmp     esi, [rbp+4Fh+var_78]
0x180077a19  jnb     loc_180077F24
0x180077a1f  mov     rax, [rbp+4Fh+pv]
0x180077a23  mov     [rbp+4Fh+var_80], r12
0x180077a27  mov     ecx, esi
0x180077a29  mov     rdi, [rax+rcx*8]
0x180077a2d  lea     rcx, [rbp+4Fh+var_80]
0x180077a31  mov     rax, [rdi]
0x180077a34  mov     rbx, [rax]
0x180077a37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077a3c  lea     r8, [rbp+4Fh+var_80]
0x180077a40  mov     rcx, rdi
0x180077a43  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180077a4a  mov     rax, rbx
0x180077a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a52  mov     ebx, eax
0x180077a54  test    eax, eax
0x180077a56  js      loc_180077C0F
0x180077a5c  xor     ecx, ecx; string
0x180077a5e  mov     [rbp+4Fh+var_90], r12
0x180077a62  call    cs:__imp_WindowsDeleteString
0x180077a68  mov     rcx, [rbp+4Fh+var_80]
0x180077a6c  lea     r8, [rbp+4Fh+var_90]
0x180077a70  mov     rdx, r15
0x180077a73  mov     [rbp+4Fh+var_90], r12
0x180077a77  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180077a7c  test    eax, eax
0x180077a7e  jns     short loc_180077AA7
0x180077a80  mov     rcx, [rbp+4Fh+var_90]; string
0x180077a84  call    cs:__imp_WindowsDeleteString
0x180077a8a  lea     r8, [rbp+4Fh+var_90]; string
0x180077a8e  mov     [rbp+4Fh+var_90], r12
0x180077a92  xor     edx, edx; length
0x180077a94  lea     rcx, word_1800B72F8; sourceString
0x180077a9b  call    cs:__imp_WindowsCreateString
0x180077aa1  mov     ebx, eax
0x180077aa3  test    eax, eax
0x180077aa5  js      short loc_180077AE6
0x180077aa7  mov     rax, [rbp+4Fh+var_90]
0x180077aab  lea     rdx, [rbp+4Fh+var_58]
0x180077aaf  mov     rcx, r14
0x180077ab2  mov     [rbp+4Fh+var_58], rax
0x180077ab6  call    ?Add@?$CTDynArray@PEAUHSTRING__@@$0BE@@@QEAAHAEBQEAUHSTRING__@@PEAK@Z; CTDynArray<HSTRING__ *,20>::Add(HSTRING__ * const &,ulong *)
0x180077abb  test    eax, eax
0x180077abd  jz      loc_180077B79
0x180077ac3  xor     ecx, ecx; string
0x180077ac5  mov     [rbp+4Fh+var_90], r12
0x180077ac9  mov     ebx, r12d
0x180077acc  call    cs:__imp_WindowsDeleteString
0x180077ad2  lea     rcx, [rbp+4Fh+var_80]
0x180077ad6  mov     [rbp+4Fh+var_90], r12
0x180077ada  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180077adf  inc     esi
0x180077ae1  jmp     loc_180077A16
0x180077ae6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077aed  test    rcx, rcx
0x180077af0  jnz     short loc_180077B33
0x180077af2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077af8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077aff  mov     rcx, rax
0x180077b02  test    rax, rax
0x180077b05  jz      short loc_180077B25
0x180077b07  mov     rax, [rax]
0x180077b0a  mov     edx, 7F0h
0x180077b0f  mov     rax, [rax+8]
0x180077b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b18  test    eax, eax
0x180077b1a  jz      short loc_180077B25
0x180077b1c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077b23  jmp     short loc_180077B33
0x180077b25  lea     rcx, qword_1800D6F70; this
0x180077b2c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180077b33  cmp     [rcx+8], r12b
0x180077b37  jz      short loc_180077B5E
0x180077b39  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077b3e  cmp     [rax+7CCh], ebx
0x180077b44  jz      short loc_180077B5E
0x180077b46  mov     r9d, ebx; int
0x180077b49  lea     rdx, aCreatestringve; "CreateStringVectorFromMap"
0x180077b50  mov     r8d, 26Fh; int
0x180077b56  mov     rcx, rax; this
0x180077b59  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077b5e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077b65  jb      loc_180077F0D
0x180077b6b  mov     edx, 53h ; 'S'
0x180077b70  mov     [rsp+0C0h+var_A0], ebx
0x180077b74  jmp     loc_180077EF3
0x180077b79  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077b80  mov     edi, 8007000Eh
0x180077b85  mov     ebx, edi
0x180077b87  test    rcx, rcx
0x180077b8a  jnz     short loc_180077BCD
0x180077b8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077b92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077b99  mov     rcx, rax
0x180077b9c  test    rax, rax
0x180077b9f  jz      short loc_180077BBF
0x180077ba1  mov     rax, [rax]
0x180077ba4  mov     edx, 7F0h
0x180077ba9  mov     rax, [rax+8]
0x180077bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077bb2  test    eax, eax
0x180077bb4  jz      short loc_180077BBF
0x180077bb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077bbd  jmp     short loc_180077BCD
0x180077bbf  lea     rcx, qword_1800D6F70; this
0x180077bc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180077bcd  cmp     [rcx+8], r12b
0x180077bd1  jz      short loc_180077BF8
0x180077bd3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077bd8  cmp     [rax+7CCh], edi
0x180077bde  jz      short loc_180077BF8
0x180077be0  mov     r9d, edi; int
0x180077be3  lea     rdx, aCreatestringve; "CreateStringVectorFromMap"
0x180077bea  mov     r8d, 278h; int
0x180077bf0  mov     rcx, rax; this
0x180077bf3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077bf8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077bff  jb      loc_180077F0D
0x180077c05  mov     edx, 55h ; 'U'
0x180077c0a  jmp     loc_180077EEF
0x180077c0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077c16  test    rcx, rcx
0x180077c19  jnz     short loc_180077C5C
0x180077c1b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077c21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077c28  mov     rcx, rax
0x180077c2b  test    rax, rax
0x180077c2e  jz      short loc_180077C4E
0x180077c30  mov     rax, [rax]
0x180077c33  mov     edx, 7F0h
0x180077c38  mov     rax, [rax+8]
0x180077c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077c41  test    eax, eax
0x180077c43  jz      short loc_180077C4E
0x180077c45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077c4c  jmp     short loc_180077C5C
0x180077c4e  lea     rcx, qword_1800D6F70; this
0x180077c55  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180077c5c  cmp     [rcx+8], r12b
0x180077c60  jz      short loc_180077C87
0x180077c62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180077c67  cmp     [rax+7CCh], ebx
0x180077c6d  jz      short loc_180077C87
0x180077c6f  mov     r9d, ebx; int
0x180077c72  lea     rdx, aCreatestringve; "CreateStringVectorFromMap"
0x180077c79  mov     r8d, 268h; int
0x180077c7f  mov     rcx, rax; this
0x180077c82  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180077c87  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180077c8e  jb      loc_180077F1B
0x180077c94  mov     edx, 52h ; 'R'
0x180077c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180077ca0  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180077ca7  xor     r9d, r9d
0x180077caa  mov     [rsp+0C0h+var_A0], ebx
0x180077cae  mov     rcx, [rcx+10h]
0x180077cb2  call    WPP_SF_qD
0x180077cb7  jmp     loc_180077F1B
0x180077cbc  lea     rdx, [rbp+4Fh+var_80]
0x180077cc0  mov     [rbp+4Fh+var_80], r12
0x180077cc4  lea     rcx, [rbp+4Fh+var_68]
0x180077cc8  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180077ccd  mov     ebx, eax
0x180077ccf  test    eax, eax
0x180077cd1  jns     loc_180077D62
0x180077cd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180077cde  test    rcx, rcx
0x180077ce1  jnz     short loc_180077D24
0x180077ce3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180077ce9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180077cf0  mov     rcx, rax
0x180077cf3  test    rax, rax
  ... truncated ...
```
