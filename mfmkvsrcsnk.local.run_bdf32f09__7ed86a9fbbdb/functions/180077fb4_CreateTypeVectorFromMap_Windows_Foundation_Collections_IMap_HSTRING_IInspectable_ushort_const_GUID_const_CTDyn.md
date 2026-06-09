# CreateTypeVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,CTDynArray<_GUID,20> &)

- ea: `0x180077fb4`
- end: `0x180078834`
- name: `?CreateTypeVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@AEAV?$CTDynArray@U_GUID@@$0BE@@@@Z`
- size: `2176`
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
- `0x180074ed8`
- `0x1800771e4`
- `0x180077fb4`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007804c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007804c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800787ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800787ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007805f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007805f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007808e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078179`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007821a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800782ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800783e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078476`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078509`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800785b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007865c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007870a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007808e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078179`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007821a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800782ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800783e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078476`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078509`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800785b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007865c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007870a`

## string_xrefs

- `0x180077ffc`: `CreateTypeVectorFromMap`
- `0x1800780e5`: `CreateTypeVectorFromMap`
- `0x1800781d0`: `CreateTypeVectorFromMap`
- `0x180078271`: `CreateTypeVectorFromMap`
- `0x180078325`: `CreateTypeVectorFromMap`
- `0x18007843e`: `CreateTypeVectorFromMap`
- `0x1800784cd`: `CreateTypeVectorFromMap`
- `0x180078560`: `CreateTypeVectorFromMap`
- `0x18007860a`: `CreateTypeVectorFromMap`
- `0x1800786b3`: `CreateTypeVectorFromMap`
- `0x180078761`: `CreateTypeVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateTypeVectorFromMap(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // r12
  unsigned __int64 v9; // rbx
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
  unsigned int v80; // [rsp+40h] [rbp-39h] BYREF
  int v81; // [rsp+44h] [rbp-35h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  __int64 v83; // [rsp+50h] [rbp-29h] BYREF
  __int64 v84; // [rsp+58h] [rbp-21h] BYREF
  __int128 v85; // [rsp+60h] [rbp-19h] BYREF
  HSTRING string; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF

  v84 = 0;
  v83 = 0;
  v80 = 0;
  pv = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v78, "CreateTypeVectorFromMap", 325);
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v83);
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    LODWORD(v9) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v9, &hstringHeader, &string);
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
        v14 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v71 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v65 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v59 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
  v81 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v84 + 48LL))(v84, &v81);
  if ( v11 >= 0 )
  {
    if ( v81 == 1037 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v84 + 304LL))(v84, &v80, &pv);
      if ( v11 >= 0 )
      {
        for ( i = 0; i < v80; ++i )
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
                v53 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v49 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v45 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v30 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v21 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    for ( j = 0; j < v80; ++j )
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
0x180077fb4  mov     [rsp-8+arg_10], rbx
0x180077fb9  push    rbp
0x180077fba  push    rsi
0x180077fbb  push    rdi
0x180077fbc  push    r12
0x180077fbe  push    r13
0x180077fc0  push    r14
0x180077fc2  push    r15
0x180077fc4  lea     rbp, [rsp-27h]
0x180077fc9  sub     rsp, 0A0h
0x180077fd0  mov     rax, cs:__security_cookie
0x180077fd7  xor     rax, rsp
0x180077fda  mov     [rbp+57h+var_40], rax
0x180077fde  xor     r13d, r13d
0x180077fe1  mov     r15, r8
0x180077fe4  mov     rdi, rdx
0x180077fe7  mov     [rbp+57h+var_78], r13
0x180077feb  mov     rsi, rcx
0x180077fee  mov     [rbp+57h+var_80], r13
0x180077ff2  mov     r8d, 145h; int
0x180077ff8  mov     [rbp+57h+var_90], r13d
0x180077ffc  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x180078003  mov     [rbp+57h+pv], r13
0x180078007  lea     rcx, [rbp+57h+var_A0]; this
0x18007800b  mov     r14, r9
0x18007800e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180078013  mov     rax, [rsi]
0x180078016  lea     rcx, [rbp+57h+var_80]
0x18007801a  mov     r12, [rax+30h]
0x18007801e  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x180078023  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180078027  inc     rbx
0x18007802a  cmp     [rdi+rbx*2], r13w
0x18007802f  jnz     short loc_180078027
0x180078031  mov     eax, 0FFFFFFFFh
0x180078036  cmp     rbx, rax
0x180078039  jbe     short loc_180078052
0x18007803b  xor     r9d, r9d; lpArguments
0x18007803e  xor     r8d, r8d; nNumberOfArguments
0x180078041  mov     ecx, 0C000000Dh; dwExceptionCode
0x180078046  mov     ebx, eax
0x180078048  lea     edx, [r9+1]; dwExceptionFlags
0x18007804c  call    cs:__imp_RaiseException
0x180078052  lea     r9, [rbp+57h+string]; string
0x180078056  mov     edx, ebx; length
0x180078058  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007805c  mov     rcx, rdi; sourceString
0x18007805f  call    cs:__imp_WindowsCreateStringReference
0x180078065  mov     rdx, [rbp+57h+string]
0x180078069  lea     r8, [rbp+57h+var_80]
0x18007806d  mov     rcx, rsi
0x180078070  mov     rax, r12
0x180078073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078078  mov     ebx, eax
0x18007807a  test    eax, eax
0x18007807c  jns     loc_18007812F
0x180078082  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078089  test    rcx, rcx
0x18007808c  jnz     short loc_1800780CF
0x18007808e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078094  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007809b  mov     rcx, rax
0x18007809e  test    rax, rax
0x1800780a1  jz      short loc_1800780C1
0x1800780a3  mov     rax, [rax]
0x1800780a6  mov     edx, 7F0h
0x1800780ab  mov     rax, [rax+8]
0x1800780af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800780b4  test    eax, eax
0x1800780b6  jz      short loc_1800780C1
0x1800780b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800780bf  jmp     short loc_1800780CF
0x1800780c1  lea     rcx, qword_1800D6F70; this
0x1800780c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800780cf  cmp     [rcx+8], r13b
0x1800780d3  jz      short loc_1800780FA
0x1800780d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800780da  cmp     [rax+7CCh], ebx
0x1800780e0  jz      short loc_1800780FA
0x1800780e2  mov     r9d, ebx; int
0x1800780e5  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x1800780ec  mov     r8d, 145h; int
0x1800780f2  mov     rcx, rax; this
0x1800780f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800780fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078101  jb      loc_1800787AB
0x180078107  mov     edx, 28h ; '('
0x18007810c  mov     rcx, cs:WPP_GLOBAL_Control
0x180078113  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007811a  xor     r9d, r9d
0x18007811d  mov     [rsp+0D0h+var_B0], ebx
0x180078121  mov     rcx, [rcx+10h]
0x180078125  call    WPP_SF_qD
0x18007812a  jmp     loc_1800787AB
0x18007812f  xorps   xmm0, xmm0
0x180078132  lea     rdx, [rbp+57h+var_78]
0x180078136  lea     rcx, [rbp+57h+var_80]
0x18007813a  movups  [rbp+57h+var_70], xmm0
0x18007813e  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x180078143  test    eax, eax
0x180078145  js      loc_18007858C
0x18007814b  mov     rcx, [rbp+57h+var_78]
0x18007814f  lea     rdx, [rbp+57h+var_8C]
0x180078153  mov     [rbp+57h+var_8C], r13d
0x180078157  mov     rax, [rcx]
0x18007815a  mov     rax, [rax+30h]
0x18007815e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078163  mov     ebx, eax
0x180078165  test    eax, eax
0x180078167  jns     loc_1800781FC
0x18007816d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078174  test    rcx, rcx
0x180078177  jnz     short loc_1800781BA
0x180078179  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007817f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078186  mov     rcx, rax
0x180078189  test    rax, rax
0x18007818c  jz      short loc_1800781AC
0x18007818e  mov     rax, [rax]
0x180078191  mov     edx, 7F0h
0x180078196  mov     rax, [rax+8]
0x18007819a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007819f  test    eax, eax
0x1800781a1  jz      short loc_1800781AC
0x1800781a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800781aa  jmp     short loc_1800781BA
0x1800781ac  lea     rcx, qword_1800D6F70; this
0x1800781b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800781ba  cmp     [rcx+8], r13b
0x1800781be  jz      short loc_1800781E5
0x1800781c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800781c5  cmp     [rax+7CCh], ebx
0x1800781cb  jz      short loc_1800781E5
0x1800781cd  mov     r9d, ebx; int
0x1800781d0  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x1800781d7  mov     r8d, 14Bh; int
0x1800781dd  mov     rcx, rax; this
0x1800781e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800781e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800781ec  jb      loc_1800787AB
0x1800781f2  mov     edx, 29h ; ')'
0x1800781f7  jmp     loc_18007810C
0x1800781fc  cmp     [rbp+57h+var_8C], 40Dh
0x180078203  jz      loc_18007829D
0x180078209  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078210  mov     ebx, 0C00D36BBh
0x180078215  test    rcx, rcx
0x180078218  jnz     short loc_18007825B
0x18007821a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078220  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078227  mov     rcx, rax
0x18007822a  test    rax, rax
0x18007822d  jz      short loc_18007824D
0x18007822f  mov     rax, [rax]
0x180078232  mov     edx, 7F0h
0x180078237  mov     rax, [rax+8]
0x18007823b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078240  test    eax, eax
0x180078242  jz      short loc_18007824D
0x180078244  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007824b  jmp     short loc_18007825B
0x18007824d  lea     rcx, qword_1800D6F70; this
0x180078254  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007825b  cmp     [rcx+8], r13b
0x18007825f  jz      short loc_180078286
0x180078261  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078266  cmp     [rax+7CCh], ebx
0x18007826c  jz      short loc_180078286
0x18007826e  mov     r9d, ebx; int
0x180078271  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x180078278  mov     r8d, 14Fh; int
0x18007827e  mov     rcx, rax; this
0x180078281  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078286  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007828d  jb      loc_1800787AB
0x180078293  mov     edx, 2Ah ; '*'
0x180078298  jmp     loc_18007810C
0x18007829d  mov     rcx, [rbp+57h+var_78]
0x1800782a1  lea     r8, [rbp+57h+pv]
0x1800782a5  lea     rdx, [rbp+57h+var_90]
0x1800782a9  mov     rax, [rcx]
0x1800782ac  mov     rax, [rax+130h]
0x1800782b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782b8  mov     ebx, eax
0x1800782ba  test    eax, eax
0x1800782bc  jns     loc_180078351
0x1800782c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800782c9  test    rcx, rcx
0x1800782cc  jnz     short loc_18007830F
0x1800782ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800782d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800782db  mov     rcx, rax
0x1800782de  test    rax, rax
0x1800782e1  jz      short loc_180078301
0x1800782e3  mov     rax, [rax]
0x1800782e6  mov     edx, 7F0h
0x1800782eb  mov     rax, [rax+8]
0x1800782ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782f4  test    eax, eax
0x1800782f6  jz      short loc_180078301
0x1800782f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800782ff  jmp     short loc_18007830F
0x180078301  lea     rcx, qword_1800D6F70; this
0x180078308  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007830f  cmp     [rcx+8], r13b
0x180078313  jz      short loc_18007833A
0x180078315  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007831a  cmp     [rax+7CCh], ebx
0x180078320  jz      short loc_18007833A
0x180078322  mov     r9d, ebx; int
0x180078325  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x18007832c  mov     r8d, 152h; int
0x180078332  mov     rcx, rax; this
0x180078335  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007833a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078341  jb      loc_1800787AB
0x180078347  mov     edx, 2Bh ; '+'
0x18007834c  jmp     loc_18007810C
0x180078351  mov     esi, r13d
0x180078354  cmp     esi, [rbp+57h+var_90]
0x180078357  jnb     loc_1800787AB
0x18007835d  mov     rax, [rbp+57h+pv]
0x180078361  mov     [rbp+57h+var_98], r13
0x180078365  mov     ecx, esi
0x180078367  mov     rdi, [rax+rcx*8]
0x18007836b  lea     rcx, [rbp+57h+var_98]
0x18007836f  mov     rax, [rdi]
0x180078372  mov     rbx, [rax]
0x180078375  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007837a  lea     r8, [rbp+57h+var_98]
0x18007837e  mov     rcx, rdi
0x180078381  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180078388  mov     rax, rbx
0x18007838b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078390  mov     ebx, eax
0x180078392  test    eax, eax
0x180078394  js      loc_1800784FD
0x18007839a  mov     rcx, [rbp+57h+var_98]
0x18007839e  lea     r9, [rbp+57h+var_70]
0x1800783a2  mov     r8, r15
0x1800783a5  call    ?CreateMediaSubTypeFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@PEAU5@@Z; CreateMediaSubTypeFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,_GUID *)
0x1800783aa  mov     ebx, eax
0x1800783ac  test    eax, eax
0x1800783ae  js      loc_18007846A
0x1800783b4  lea     rdx, [rbp+57h+var_70]
0x1800783b8  mov     rcx, r14
0x1800783bb  call    ?Add@?$CTDynArray@U_GUID@@$0BE@@@QEAAHAEBU_GUID@@PEAK@Z; CTDynArray<_GUID,20>::Add(_GUID const &,ulong *)
0x1800783c0  test    eax, eax
0x1800783c2  jz      short loc_1800783D4
0x1800783c4  lea     rcx, [rbp+57h+var_98]
0x1800783c8  mov     ebx, r13d
0x1800783cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800783d0  inc     esi
0x1800783d2  jmp     short loc_180078354
0x1800783d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800783db  mov     edi, 8007000Eh
0x1800783e0  mov     ebx, edi
0x1800783e2  test    rcx, rcx
0x1800783e5  jnz     short loc_180078428
0x1800783e7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800783ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800783f4  mov     rcx, rax
0x1800783f7  test    rax, rax
0x1800783fa  jz      short loc_18007841A
0x1800783fc  mov     rax, [rax]
0x1800783ff  mov     edx, 7F0h
0x180078404  mov     rax, [rax+8]
0x180078408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007840d  test    eax, eax
0x18007840f  jz      short loc_18007841A
0x180078411  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078418  jmp     short loc_180078428
0x18007841a  lea     rcx, qword_1800D6F70; this
0x180078421  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078428  cmp     [rcx+8], r13b
0x18007842c  jz      short loc_180078453
0x18007842e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078433  cmp     [rax+7CCh], edi
0x180078439  jz      short loc_180078453
0x18007843b  mov     r9d, edi; int
0x18007843e  lea     rdx, aCreatetypevect; "CreateTypeVectorFromMap"
0x180078445  mov     r8d, 15Bh; int
0x18007844b  mov     rcx, rax; this
0x18007844e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078453  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007845a  jb      loc_1800787A2
0x180078460  mov     edx, 2Eh ; '.'
0x180078465  jmp     loc_180078784
0x18007846a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078471  test    rcx, rcx
0x180078474  jnz     short loc_1800784B7
0x180078476  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007847c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078483  mov     rcx, rax
0x180078486  test    rax, rax
0x180078489  jz      short loc_1800784A9
0x18007848b  mov     rax, [rax]
0x18007848e  mov     edx, 7F0h
0x180078493  mov     rax, [rax+8]
0x180078497  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
