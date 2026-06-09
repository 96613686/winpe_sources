# CreateStringVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,bool,Windows::Foundation::Collections::IVector<HSTRING__ *> * *)

- ea: `0x180018f2c`
- end: `0x180019766`
- name: `?CreateStringVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG1_NPEAPEAU?$IVector@PEAUHSTRING__@@@234@@Z`
- size: `2106`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018708`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180018a4c`
- `0x180018f2c`
- `0x180019f84`
- `0x180034f2c`
- `0x18003639c`
- `0x180054140`
- `0x1800b649c`
- `0x1800b64ec`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019057`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180019057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001906f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001906f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800193c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019529`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800193c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019529`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019689`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800196e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800196e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001909e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019163`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001929d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800193db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800194a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001955d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019606`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001909e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019163`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001929d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019328`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800193db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800194a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001955d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019606`

## string_xrefs

- `0x180019068`: `VideoRendererExtensionProfile`
- `0x180018f5c`: `CreateStringVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringVectorFromMap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v6; // rcx
  int StringFromMap; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  int v12; // ecx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int i; // esi
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64 *); // rbx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  _QWORD *v42; // rcx
  unsigned int j; // edi
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rcx
  UINT32 length[2]; // [rsp+30h] [rbp-41h] BYREF
  _BYTE v49[8]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v50; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v51; // [rsp+48h] [rbp-29h] BYREF
  __int64 v52; // [rsp+50h] [rbp-21h] BYREF
  __int64 v53; // [rsp+58h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-11h] BYREF
  __int64 v55; // [rsp+68h] [rbp-9h] BYREF
  HSTRING string; // [rsp+70h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+7h] BYREF

  v55 = 0;
  v53 = 0;
  v51 = 0;
  pv = 0;
  v52 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v49, "CreateStringVectorFromMap", 508);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  StringFromMap = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
                    v6,
                    &v52);
  if ( StringFromMap < 0 )
  {
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v8 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != StringFromMap )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStringVectorFromMap", 508, StringFromMap);
    }
    if ( g_wppLevels )
    {
      v10 = 69;
LABEL_9:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        StringFromMap);
      goto LABEL_111;
    }
    goto LABEL_111;
  }
  if ( !a1 )
  {
LABEL_110:
    *a5 = v52;
    v52 = 0;
    goto LABEL_111;
  }
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  length[0] = 0;
  if ( (int)ULongLongToULong(0x1Du, length) < 0 )
    RaiseException(0xC000000D, v12 - 28, 0, 0);
  WindowsCreateStringReference(L"VideoRendererExtensionProfile", length[0], &hstringHeader, &string);
  StringFromMap = v11(a1, string, &v53);
  if ( StringFromMap >= 0 )
  {
    if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v53, &v55) >= 0 )
    {
      StringFromMap = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v55 + 304LL))(
                        v55,
                        &v51,
                        &pv);
      if ( StringFromMap < 0 )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != StringFromMap )
            CallStackContext::TraceFailure(v18, "CreateStringVectorFromMap", 527, StringFromMap);
        }
        if ( g_wppLevels )
        {
          v10 = 71;
          goto LABEL_9;
        }
        goto LABEL_111;
      }
      for ( i = 0; i < v51; ++i )
      {
        v50 = 0;
        v20 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)pv + i);
        v21 = **v20;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        StringFromMap = v21(v20, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v50);
        if ( StringFromMap < 0 )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)v31 + 499) != StringFromMap )
              CallStackContext::TraceFailure(v31, "CreateStringVectorFromMap", 532, StringFromMap);
          }
          if ( g_wppLevels )
          {
            v32 = 72;
            goto LABEL_74;
          }
          goto LABEL_75;
        }
        *(_QWORD *)length = 0;
        WindowsDeleteString(0);
        *(_QWORD *)length = 0;
        StringFromMap = CreateStringFromMap(v50, L"@Profile", length);
        if ( StringFromMap < 0 )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
            if ( *((_DWORD *)v28 + 499) != StringFromMap )
              CallStackContext::TraceFailure(v28, "CreateStringVectorFromMap", 543, StringFromMap);
          }
          if ( g_wppLevels )
          {
            v25 = 74;
            goto LABEL_62;
          }
          goto LABEL_63;
        }
        StringFromMap = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v52 + 104LL))(v52, *(_QWORD *)length);
        if ( StringFromMap < 0 )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != StringFromMap )
              CallStackContext::TraceFailure(v24, "CreateStringVectorFromMap", 546, StringFromMap);
          }
          if ( g_wppLevels )
          {
            v25 = 75;
            goto LABEL_62;
          }
          goto LABEL_63;
        }
        WindowsDeleteString(*(HSTRING *)length);
        *(_QWORD *)length = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      }
      goto LABEL_110;
    }
    v50 = 0;
    StringFromMap = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                      &v53,
                      &v50);
    if ( StringFromMap < 0 )
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v35 + 499) != StringFromMap )
          CallStackContext::TraceFailure(v35, "CreateStringVectorFromMap", 552, StringFromMap);
      }
      if ( g_wppLevels )
      {
        v32 = 76;
LABEL_74:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v32,
          WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
          0,
          StringFromMap);
      }
      goto LABEL_75;
    }
    *(_QWORD *)length = 0;
    WindowsDeleteString(0);
    *(_QWORD *)length = 0;
    StringFromMap = CreateStringFromMap(v50, L"@Profile", length);
    if ( StringFromMap >= 0 )
    {
      StringFromMap = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v52 + 104LL))(v52, *(_QWORD *)length);
      if ( StringFromMap >= 0 )
      {
        WindowsDeleteString(*(HSTRING *)length);
        *(_QWORD *)length = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        goto LABEL_110;
      }
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v41 + 499) != StringFromMap )
          CallStackContext::TraceFailure(v41, "CreateStringVectorFromMap", 566, StringFromMap);
      }
      if ( !g_wppLevels )
        goto LABEL_63;
      v25 = 79;
    }
    else
    {
      v36 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v36 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != StringFromMap )
          CallStackContext::TraceFailure(v38, "CreateStringVectorFromMap", 563, StringFromMap);
      }
      if ( !g_wppLevels )
        goto LABEL_63;
      v25 = 78;
    }
LABEL_62:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
      0,
      StringFromMap);
LABEL_63:
    WindowsDeleteString(*(HSTRING *)length);
    *(_QWORD *)length = 0;
LABEL_75:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    goto LABEL_111;
  }
  v13 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v15 + 499) != StringFromMap )
      CallStackContext::TraceFailure(v15, "CreateStringVectorFromMap", 523, StringFromMap);
  }
  if ( g_wppLevels )
  {
    v10 = 70;
    goto LABEL_9;
  }
LABEL_111:
  v42 = pv;
  if ( pv )
  {
    for ( j = 0; j < v51; ++j )
    {
      v44 = v42[j];
      if ( v44 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v44 + 16LL))(v42[j]);
        *((_QWORD *)pv + j) = 0;
        v42 = pv;
      }
    }
    CoTaskMemFree(v42);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v49);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  v45 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return (unsigned int)StringFromMap;
}

```

## disassembly

```asm
0x180018f2c  mov     [rsp-8+arg_8], rbx
0x180018f31  mov     [rsp-8+arg_10], rsi
0x180018f36  push    rbp
0x180018f37  push    rdi
0x180018f38  push    r13
0x180018f3a  push    r14
0x180018f3c  push    r15
0x180018f3e  lea     rbp, [rsp-2Fh]
0x180018f43  sub     rsp, 0A0h
0x180018f4a  mov     rax, cs:__security_cookie
0x180018f51  xor     rax, rsp
0x180018f54  mov     [rbp+4Fh+var_30], rax
0x180018f58  mov     r14, [rbp+4Fh+arg_20]
0x180018f5c  lea     r13, aCreatestringve; "CreateStringVectorFromMap"
0x180018f63  xor     r15d, r15d
0x180018f66  mov     rdi, rcx
0x180018f69  mov     esi, 1FCh
0x180018f6e  mov     [rbp+4Fh+var_58], r15
0x180018f72  mov     r8d, esi; int
0x180018f75  mov     [rbp+4Fh+var_68], r15
0x180018f79  mov     rdx, r13; char *
0x180018f7c  mov     [rbp+4Fh+var_78], r15d
0x180018f80  lea     rcx, [rbp+4Fh+var_88]; this
0x180018f84  mov     [rbp+4Fh+pv], r15
0x180018f88  mov     [rbp+4Fh+var_70], r15
0x180018f8c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180018f91  lea     rcx, [rbp+4Fh+var_70]
0x180018f95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018f9a  lea     rdx, [rbp+4Fh+var_70]
0x180018f9e  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180018fa3  mov     ebx, eax
0x180018fa5  test    eax, eax
0x180018fa7  jns     short loc_18001901A
0x180018fa9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018fb0  test    rcx, rcx
0x180018fb3  jnz     short loc_180018FC1
0x180018fb5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180018fba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180018fc1  cmp     [rcx+8], r15b
0x180018fc5  jz      short loc_180018FE5
0x180018fc7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018fcc  cmp     [rax+7CCh], ebx
0x180018fd2  jz      short loc_180018FE5
0x180018fd4  mov     r9d, ebx; int
0x180018fd7  mov     r8d, esi; int
0x180018fda  mov     rdx, r13; char *
0x180018fdd  mov     rcx, rax; this
0x180018fe0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018fe5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018fec  jb      loc_1800196A7
0x180018ff2  mov     edx, 45h ; 'E'
0x180018ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ffe  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180019005  xor     r9d, r9d
0x180019008  mov     [rsp+0C0h+var_A0], ebx
0x18001900c  mov     rcx, [rcx+10h]
0x180019010  call    WPP_SF_qD
0x180019015  jmp     loc_1800196A7
0x18001901a  test    rdi, rdi
0x18001901d  jz      loc_18001969C
0x180019023  mov     rax, [rdi]
0x180019026  lea     rcx, [rbp+4Fh+var_68]
0x18001902a  mov     rbx, [rax+30h]
0x18001902e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019033  lea     rdx, [rbp+4Fh+length]; unsigned int *
0x180019037  mov     [rbp+4Fh+length], r15d
0x18001903b  mov     ecx, 1Dh; unsigned __int64
0x180019040  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180019045  test    eax, eax
0x180019047  jns     short loc_18001905D
0x180019049  lea     edx, [rcx-1Ch]; dwExceptionFlags
0x18001904c  xor     r9d, r9d; lpArguments
0x18001904f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180019054  xor     r8d, r8d; nNumberOfArguments
0x180019057  call    cs:__imp_RaiseException
0x18001905d  mov     edx, [rbp+4Fh+length]; length
0x180019060  lea     r9, [rbp+4Fh+string]; string
0x180019064  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180019068  lea     rcx, sourceString; "VideoRendererExtensionProfile"
0x18001906f  call    cs:__imp_WindowsCreateStringReference
0x180019075  mov     rdx, [rbp+4Fh+string]
0x180019079  lea     r8, [rbp+4Fh+var_68]
0x18001907d  mov     rcx, rdi
0x180019080  mov     rax, rbx
0x180019083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019088  mov     ebx, eax
0x18001908a  test    eax, eax
0x18001908c  jns     loc_18001911D
0x180019092  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019099  test    rcx, rcx
0x18001909c  jnz     short loc_1800190DF
0x18001909e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800190a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800190ab  mov     rcx, rax
0x1800190ae  test    rax, rax
0x1800190b1  jz      short loc_1800190D1
0x1800190b3  mov     rax, [rax]
0x1800190b6  mov     edx, 7F0h
0x1800190bb  mov     rax, [rax+8]
0x1800190bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190c4  test    eax, eax
0x1800190c6  jz      short loc_1800190D1
0x1800190c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800190cf  jmp     short loc_1800190DF
0x1800190d1  lea     rcx, qword_180153440; this
0x1800190d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800190df  cmp     [rcx+8], r15b
0x1800190e3  jz      short loc_180019106
0x1800190e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800190ea  cmp     [rax+7CCh], ebx
0x1800190f0  jz      short loc_180019106
0x1800190f2  mov     r9d, ebx; int
0x1800190f5  mov     r8d, 20Bh; int
0x1800190fb  mov     rdx, r13; char *
0x1800190fe  mov     rcx, rax; this
0x180019101  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019106  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001910d  jb      loc_1800196A7
0x180019113  mov     edx, 46h ; 'F'
0x180019118  jmp     loc_180018FF7
0x18001911d  lea     rdx, [rbp+4Fh+var_58]
0x180019121  lea     rcx, [rbp+4Fh+var_68]
0x180019125  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18001912a  test    eax, eax
0x18001912c  js      loc_18001947D
0x180019132  mov     rcx, [rbp+4Fh+var_58]
0x180019136  lea     r8, [rbp+4Fh+pv]
0x18001913a  lea     rdx, [rbp+4Fh+var_78]
0x18001913e  mov     rax, [rcx]
0x180019141  mov     rax, [rax+130h]
0x180019148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001914d  mov     ebx, eax
0x18001914f  test    eax, eax
0x180019151  jns     loc_1800191E2
0x180019157  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001915e  test    rcx, rcx
0x180019161  jnz     short loc_1800191A4
0x180019163  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019169  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019170  mov     rcx, rax
0x180019173  test    rax, rax
0x180019176  jz      short loc_180019196
0x180019178  mov     rax, [rax]
0x18001917b  mov     edx, 7F0h
0x180019180  mov     rax, [rax+8]
0x180019184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019189  test    eax, eax
0x18001918b  jz      short loc_180019196
0x18001918d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019194  jmp     short loc_1800191A4
0x180019196  lea     rcx, qword_180153440; this
0x18001919d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800191a4  cmp     [rcx+8], r15b
0x1800191a8  jz      short loc_1800191CB
0x1800191aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800191af  cmp     [rax+7CCh], ebx
0x1800191b5  jz      short loc_1800191CB
0x1800191b7  mov     r9d, ebx; int
0x1800191ba  mov     r8d, 20Fh; int
0x1800191c0  mov     rdx, r13; char *
0x1800191c3  mov     rcx, rax; this
0x1800191c6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800191cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800191d2  jb      loc_1800196A7
0x1800191d8  mov     edx, 47h ; 'G'
0x1800191dd  jmp     loc_180018FF7
0x1800191e2  mov     esi, r15d
0x1800191e5  cmp     esi, [rbp+4Fh+var_78]
0x1800191e8  jnb     loc_18001969C
0x1800191ee  mov     rax, [rbp+4Fh+pv]
0x1800191f2  mov     [rbp+4Fh+var_80], r15
0x1800191f6  mov     ecx, esi
0x1800191f8  mov     rdi, [rax+rcx*8]
0x1800191fc  lea     rcx, [rbp+4Fh+var_80]
0x180019200  mov     rax, [rdi]
0x180019203  mov     rbx, [rax]
0x180019206  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001920b  lea     r8, [rbp+4Fh+var_80]
0x18001920f  mov     rcx, rdi
0x180019212  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180019219  mov     rax, rbx
0x18001921c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019221  mov     ebx, eax
0x180019223  test    eax, eax
0x180019225  js      loc_1800193CF
0x18001922b  xor     ecx, ecx; string
0x18001922d  mov     qword ptr [rbp+4Fh+length], r15
0x180019231  call    cs:__imp_WindowsDeleteString
0x180019237  mov     rcx, [rbp+4Fh+var_80]
0x18001923b  lea     r8, [rbp+4Fh+length]
0x18001923f  lea     rdx, aProfile; "@Profile"
0x180019246  mov     qword ptr [rbp+4Fh+length], r15
0x18001924a  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18001924f  mov     ebx, eax
0x180019251  test    eax, eax
0x180019253  js      loc_18001931C
0x180019259  mov     rcx, [rbp+4Fh+var_70]
0x18001925d  mov     rdx, qword ptr [rbp+4Fh+length]
0x180019261  mov     rax, [rcx]
0x180019264  mov     rax, [rax+68h]
0x180019268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001926d  mov     ebx, eax
0x18001926f  test    eax, eax
0x180019271  js      short loc_180019291
0x180019273  mov     rcx, qword ptr [rbp+4Fh+length]; string
0x180019277  call    cs:__imp_WindowsDeleteString
0x18001927d  lea     rcx, [rbp+4Fh+var_80]
0x180019281  mov     qword ptr [rbp+4Fh+length], r15
0x180019285  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001928a  inc     esi
0x18001928c  jmp     loc_1800191E5
0x180019291  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019298  test    rcx, rcx
0x18001929b  jnz     short loc_1800192DE
0x18001929d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800192a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800192aa  mov     rcx, rax
0x1800192ad  test    rax, rax
0x1800192b0  jz      short loc_1800192D0
0x1800192b2  mov     rax, [rax]
0x1800192b5  mov     edx, 7F0h
0x1800192ba  mov     rax, [rax+8]
0x1800192be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192c3  test    eax, eax
0x1800192c5  jz      short loc_1800192D0
0x1800192c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800192ce  jmp     short loc_1800192DE
0x1800192d0  lea     rcx, qword_180153440; this
0x1800192d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800192de  cmp     [rcx+8], r15b
0x1800192e2  jz      short loc_180019305
0x1800192e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800192e9  cmp     [rax+7CCh], ebx
0x1800192ef  jz      short loc_180019305
0x1800192f1  mov     r9d, ebx; int
0x1800192f4  mov     r8d, 222h; int
0x1800192fa  mov     rdx, r13; char *
0x1800192fd  mov     rcx, rax; this
0x180019300  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019305  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001930c  jb      loc_1800193BC
0x180019312  mov     edx, 4Bh ; 'K'
0x180019317  jmp     loc_18001939E
0x18001931c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019323  test    rcx, rcx
0x180019326  jnz     short loc_180019369
0x180019328  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001932e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019335  mov     rcx, rax
0x180019338  test    rax, rax
0x18001933b  jz      short loc_18001935B
0x18001933d  mov     rax, [rax]
0x180019340  mov     edx, 7F0h
0x180019345  mov     rax, [rax+8]
0x180019349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001934e  test    eax, eax
0x180019350  jz      short loc_18001935B
0x180019352  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019359  jmp     short loc_180019369
0x18001935b  lea     rcx, qword_180153440; this
0x180019362  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019369  cmp     [rcx+8], r15b
0x18001936d  jz      short loc_180019390
0x18001936f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019374  cmp     [rax+7CCh], ebx
0x18001937a  jz      short loc_180019390
0x18001937c  mov     r9d, ebx; int
0x18001937f  mov     r8d, 21Fh; int
0x180019385  mov     rdx, r13; char *
0x180019388  mov     rcx, rax; this
0x18001938b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019390  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019397  jb      short loc_1800193BC
0x180019399  mov     edx, 4Ah ; 'J'
0x18001939e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193a5  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800193ac  xor     r9d, r9d
0x1800193af  mov     [rsp+0C0h+var_A0], ebx
0x1800193b3  mov     rcx, [rcx+10h]
0x1800193b7  call    WPP_SF_qD
0x1800193bc  mov     rcx, qword ptr [rbp+4Fh+length]; string
0x1800193c0  call    cs:__imp_WindowsDeleteString
0x1800193c6  mov     qword ptr [rbp+4Fh+length], r15
0x1800193ca  jmp     loc_18001946F
0x1800193cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800193d6  test    rcx, rcx
0x1800193d9  jnz     short loc_18001941C
0x1800193db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800193e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800193e8  mov     rcx, rax
0x1800193eb  test    rax, rax
0x1800193ee  jz      short loc_18001940E
0x1800193f0  mov     rax, [rax]
0x1800193f3  mov     edx, 7F0h
0x1800193f8  mov     rax, [rax+8]
0x1800193fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019401  test    eax, eax
0x180019403  jz      short loc_18001940E
0x180019405  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001940c  jmp     short loc_18001941C
  ... truncated ...
```
