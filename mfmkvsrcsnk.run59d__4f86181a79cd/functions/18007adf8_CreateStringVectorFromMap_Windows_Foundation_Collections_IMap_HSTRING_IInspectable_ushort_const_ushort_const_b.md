# CreateStringVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,bool,CTDynArray<HSTRING__ *,20> &)

- ea: `0x18007adf8`
- end: `0x18007b645`
- name: `?CreateStringVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG1_NAEAV?$CTDynArray@PEAUHSTRING__@@$0BE@@@@Z`
- size: `2125`
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
- `0x180078274`
- `0x18007ab98`
- `0x18007adf8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ae8e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ae8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b5f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b5f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b0e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b41d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b0e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007b41d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b09e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b0c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b11a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b59b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b09e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b0c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b11a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b59b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007aeac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007aeac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aee1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007afca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b146`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b1e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b27b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b43f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b4fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007aee1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007afca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b146`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b1e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b27b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b43f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b4fd`

## string_xrefs

- `0x18007ae28`: `CreateStringVectorFromMap`
- `0x18007b1a3`: `CreateStringVectorFromMap`
- `0x18007b243`: `CreateStringVectorFromMap`
- `0x18007b2d8`: `CreateStringVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringVectorFromMap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 *); // rdi
  int v8; // ecx
  __int64 v9; // rdx
  HRESULT v10; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  unsigned int i; // esi
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 v42; // rdx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  HSTRING v62; // rcx
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  _QWORD *v66; // rcx
  unsigned int j; // edi
  __int64 v68; // rdx
  UINT32 length[2]; // [rsp+30h] [rbp-41h] BYREF
  _BYTE v71[8]; // [rsp+38h] [rbp-39h] BYREF
  __int64 v72; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v73; // [rsp+48h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-21h] BYREF
  __int64 v75; // [rsp+58h] [rbp-19h] BYREF
  __int64 v76; // [rsp+60h] [rbp-11h] BYREF
  HSTRING v77; // [rsp+68h] [rbp-9h] BYREF
  HSTRING string; // [rsp+70h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+7h] BYREF

  v76 = 0;
  v75 = 0;
  v73 = 0;
  pv = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v71, "CreateStringVectorFromMap", 607);
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v75);
  length[0] = 0;
  if ( (int)ULongLongToUInt(9u, length) < 0 )
    RaiseException(0xC000000D, v8 - 8, 0, 0);
  WindowsCreateStringReference(L"InputType", length[0], &hstringHeader, &string);
  v10 = v7(a1, string, &v75);
  if ( v10 < 0 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v11, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStringVectorFromMap", 607, v10);
    }
    if ( g_wppLevels )
    {
      v16 = 80;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v10);
      goto LABEL_105;
    }
    goto LABEL_105;
  }
  if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v75, &v76) < 0 )
  {
    v72 = 0;
    v10 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            &v75,
            &v72);
    if ( v10 < 0 )
    {
      v50 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != v10 )
          CallStackContext::TraceFailure(v52, "CreateStringVectorFromMap", 641, v10);
      }
      if ( g_wppLevels )
      {
        v46 = 86;
LABEL_65:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v46, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v10);
      }
      goto LABEL_104;
    }
    *(_QWORD *)length = 0;
    WindowsDeleteString(0);
    *(_QWORD *)length = 0;
    if ( (int)CreateStringFromMap(v72, a3, length) >= 0
      || (WindowsDeleteString(*(HSTRING *)length),
          *(_QWORD *)length = 0,
          v10 = WindowsCreateString(&word_1800BC2F8, 0, (HSTRING *)length),
          v10 >= 0) )
    {
      v77 = *(HSTRING *)length;
      if ( (unsigned int)CTDynArray<HSTRING__ *,20>::Add(a5, &v77) )
      {
        v10 = 0;
        *(_QWORD *)length = 0;
        v62 = 0;
LABEL_103:
        WindowsDeleteString(v62);
        *(_QWORD *)length = 0;
LABEL_104:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        goto LABEL_105;
      }
      v63 = (__int64 *)CallStackTracing::s_wpInstance;
      v10 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59, v60, v61);
        CallStackTracing::s_wpInstance = v64;
        if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
        {
          v63 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v63 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v63 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
        if ( *((_DWORD *)v65 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v65, "CreateStringVectorFromMap", 657, -2147024882);
      }
      if ( g_wppLevels )
      {
        v42 = 89;
LABEL_101:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v42,
          WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
          0,
          -2147024882);
      }
    }
    else
    {
      v56 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53, v54, v55);
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)v58 + 499) != v10 )
          CallStackContext::TraceFailure(v58, "CreateStringVectorFromMap", 648, v10);
      }
      if ( g_wppLevels )
      {
        v38 = 87;
LABEL_44:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v10);
      }
    }
LABEL_102:
    v62 = *(HSTRING *)length;
    goto LABEL_103;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v76 + 304LL))(v76, &v73, &pv);
  if ( v10 >= 0 )
  {
    for ( i = 0; i < v73; ++i )
    {
      v72 = 0;
      v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)pv + i);
      v25 = **v24;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      v10 = v25(v24, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v72);
      if ( v10 < 0 )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != v10 )
            CallStackContext::TraceFailure(v45, "CreateStringVectorFromMap", 616, v10);
        }
        if ( g_wppLevels )
        {
          v46 = 82;
          goto LABEL_65;
        }
        goto LABEL_104;
      }
      *(_QWORD *)length = 0;
      WindowsDeleteString(0);
      *(_QWORD *)length = 0;
      if ( (int)CreateStringFromMap(v72, a3, length) < 0 )
      {
        WindowsDeleteString(*(HSTRING *)length);
        *(_QWORD *)length = 0;
        v10 = WindowsCreateString(&word_1800BC2F8, 0, (HSTRING *)length);
        if ( v10 < 0 )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != v10 )
              CallStackContext::TraceFailure(v37, "CreateStringVectorFromMap", 623, v10);
          }
          if ( g_wppLevels )
          {
            v38 = 83;
            goto LABEL_44;
          }
          goto LABEL_102;
        }
      }
      v77 = *(HSTRING *)length;
      if ( !(unsigned int)CTDynArray<HSTRING__ *,20>::Add(a5, &v77) )
      {
        v39 = (__int64 *)CallStackTracing::s_wpInstance;
        v10 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
          CallStackTracing::s_wpInstance = v40;
          if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
          {
            v39 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v39 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v39 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v41 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v41, "CreateStringVectorFromMap", 632, -2147024882);
        }
        if ( g_wppLevels )
        {
          v42 = 85;
          goto LABEL_101;
        }
        goto LABEL_102;
      }
      *(_QWORD *)length = 0;
      v10 = 0;
      WindowsDeleteString(0);
      *(_QWORD *)length = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
    }
  }
  else
  {
    v20 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
      CallStackTracing::s_wpInstance = v21;
      if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      {
        v20 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v20 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v20 + 8) )
    {
      v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
      if ( *((_DWORD *)v22 + 499) != v10 )
        CallStackContext::TraceFailure(v22, "CreateStringVectorFromMap", 611, v10);
    }
    if ( g_wppLevels )
    {
      v16 = 81;
      goto LABEL_14;
    }
  }
LABEL_105:
  v66 = pv;
  if ( pv )
  {
    for ( j = 0; j < v73; ++j )
    {
      v68 = v66[j];
      if ( v68 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v68 + 16LL))(v66[j]);
        *((_QWORD *)pv + j) = 0;
        v66 = pv;
      }
    }
    CoTaskMemFree(v66);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v71);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(&v76);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007adf8  mov     [rsp-8+arg_8], rbx
0x18007adfd  mov     [rsp-8+arg_18], rsi
0x18007ae02  push    rbp
0x18007ae03  push    rdi
0x18007ae04  push    r12
0x18007ae06  push    r14
0x18007ae08  push    r15
0x18007ae0a  lea     rbp, [rsp-2Fh]
0x18007ae0f  sub     rsp, 0A0h
0x18007ae16  mov     rax, cs:__security_cookie
0x18007ae1d  xor     rax, rsp
0x18007ae20  mov     [rbp+4Fh+var_30], rax
0x18007ae24  mov     r14, [rbp+4Fh+arg_20]
0x18007ae28  lea     rsi, aCreatestringve; "CreateStringVectorFromMap"
0x18007ae2f  xor     r12d, r12d
0x18007ae32  mov     r15, r8
0x18007ae35  mov     rbx, rcx
0x18007ae38  mov     [rbp+4Fh+var_60], r12
0x18007ae3c  mov     rdx, rsi; char *
0x18007ae3f  mov     [rbp+4Fh+var_68], r12
0x18007ae43  mov     r8d, 25Fh; int
0x18007ae49  mov     [rbp+4Fh+var_78], r12d
0x18007ae4d  lea     rcx, [rbp+4Fh+var_88]; this
0x18007ae51  mov     [rbp+4Fh+pv], r12
0x18007ae55  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007ae5a  mov     rax, [rbx]
0x18007ae5d  lea     rcx, [rbp+4Fh+var_68]
0x18007ae61  mov     rdi, [rax+30h]
0x18007ae65  call    ?InternalRelease@?$ComPtr@UIMFTransform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFTransform>::InternalRelease(void)
0x18007ae6a  lea     rdx, [rbp+4Fh+length]; unsigned int *
0x18007ae6e  mov     [rbp+4Fh+length], r12d
0x18007ae72  lea     ecx, [r12+9]; unsigned __int64
0x18007ae77  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18007ae7c  test    eax, eax
0x18007ae7e  jns     short loc_18007AE9A
0x18007ae80  lea     edx, [rcx-8]; dwExceptionFlags
0x18007ae83  xor     r9d, r9d; lpArguments
0x18007ae86  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007ae8b  xor     r8d, r8d; nNumberOfArguments
0x18007ae8e  call    cs:__imp_RaiseException
0x18007ae95  nop     dword ptr [rax+rax+00h]
0x18007ae9a  mov     edx, [rbp+4Fh+length]; length
0x18007ae9d  lea     r9, [rbp+4Fh+string]; string
0x18007aea1  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x18007aea5  lea     rcx, aInputtype; "InputType"
0x18007aeac  call    cs:__imp_WindowsCreateStringReference
0x18007aeb3  nop     dword ptr [rax+rax+00h]
0x18007aeb8  mov     rdx, [rbp+4Fh+string]
0x18007aebc  lea     r8, [rbp+4Fh+var_68]
0x18007aec0  mov     rcx, rbx
0x18007aec3  mov     rax, rdi
0x18007aec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aecb  mov     ebx, eax
0x18007aecd  test    eax, eax
0x18007aecf  jns     loc_18007AF84
0x18007aed5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aedc  test    rcx, rcx
0x18007aedf  jnz     short loc_18007AF28
0x18007aee1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007aee8  nop     dword ptr [rax+rax+00h]
0x18007aeed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007aef4  mov     rcx, rax
0x18007aef7  test    rax, rax
0x18007aefa  jz      short loc_18007AF1A
0x18007aefc  mov     rax, [rax]
0x18007aeff  mov     edx, 7F0h
0x18007af04  mov     rax, [rax+8]
0x18007af08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af0d  test    eax, eax
0x18007af0f  jz      short loc_18007AF1A
0x18007af11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007af18  jmp     short loc_18007AF28
0x18007af1a  lea     rcx, qword_1800DBF70; this
0x18007af21  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007af28  cmp     [rcx+8], r12b
0x18007af2c  jz      short loc_18007AF4F
0x18007af2e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007af33  cmp     [rax+7CCh], ebx
0x18007af39  jz      short loc_18007AF4F
0x18007af3b  mov     r9d, ebx; int
0x18007af3e  mov     r8d, 25Fh; int
0x18007af44  mov     rdx, rsi; char *
0x18007af47  mov     rcx, rax; this
0x18007af4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007af4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007af56  jb      loc_18007B5B4
0x18007af5c  mov     edx, 50h ; 'P'
0x18007af61  mov     rcx, cs:WPP_GLOBAL_Control
0x18007af68  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007af6f  xor     r9d, r9d
0x18007af72  mov     [rsp+0C0h+var_A0], ebx
0x18007af76  mov     rcx, [rcx+10h]
0x18007af7a  call    WPP_SF_qD
0x18007af7f  jmp     loc_18007B5B4
0x18007af84  lea     rdx, [rbp+4Fh+var_60]
0x18007af88  lea     rcx, [rbp+4Fh+var_68]
0x18007af8c  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18007af91  test    eax, eax
0x18007af93  js      loc_18007B322
0x18007af99  mov     rcx, [rbp+4Fh+var_60]
0x18007af9d  lea     r8, [rbp+4Fh+pv]
0x18007afa1  lea     rdx, [rbp+4Fh+var_78]
0x18007afa5  mov     rax, [rcx]
0x18007afa8  mov     rax, [rax+130h]
0x18007afaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007afb4  mov     ebx, eax
0x18007afb6  test    eax, eax
0x18007afb8  jns     loc_18007B04F
0x18007afbe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007afc5  test    rcx, rcx
0x18007afc8  jnz     short loc_18007B011
0x18007afca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007afd1  nop     dword ptr [rax+rax+00h]
0x18007afd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007afdd  mov     rcx, rax
0x18007afe0  test    rax, rax
0x18007afe3  jz      short loc_18007B003
0x18007afe5  mov     rax, [rax]
0x18007afe8  mov     edx, 7F0h
0x18007afed  mov     rax, [rax+8]
0x18007aff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aff6  test    eax, eax
0x18007aff8  jz      short loc_18007B003
0x18007affa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b001  jmp     short loc_18007B011
0x18007b003  lea     rcx, qword_1800DBF70; this
0x18007b00a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b011  cmp     [rcx+8], r12b
0x18007b015  jz      short loc_18007B038
0x18007b017  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b01c  cmp     [rax+7CCh], ebx
0x18007b022  jz      short loc_18007B038
0x18007b024  mov     r9d, ebx; int
0x18007b027  mov     r8d, 263h; int
0x18007b02d  mov     rdx, rsi; char *
0x18007b030  mov     rcx, rax; this
0x18007b033  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b038  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b03f  jb      loc_18007B5B4
0x18007b045  mov     edx, 51h ; 'Q'
0x18007b04a  jmp     loc_18007AF61
0x18007b04f  mov     esi, r12d
0x18007b052  cmp     esi, [rbp+4Fh+var_78]
0x18007b055  jnb     loc_18007B5B4
0x18007b05b  mov     rax, [rbp+4Fh+pv]
0x18007b05f  mov     [rbp+4Fh+var_80], r12
0x18007b063  mov     ecx, esi
0x18007b065  mov     rdi, [rax+rcx*8]
0x18007b069  lea     rcx, [rbp+4Fh+var_80]
0x18007b06d  mov     rax, [rdi]
0x18007b070  mov     rbx, [rax]
0x18007b073  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007b078  lea     r8, [rbp+4Fh+var_80]
0x18007b07c  mov     rcx, rdi
0x18007b07f  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007b086  mov     rax, rbx
0x18007b089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b08e  mov     ebx, eax
0x18007b090  test    eax, eax
0x18007b092  js      loc_18007B26F
0x18007b098  xor     ecx, ecx; string
0x18007b09a  mov     qword ptr [rbp+4Fh+length], r12
0x18007b09e  call    cs:__imp_WindowsDeleteString
0x18007b0a5  nop     dword ptr [rax+rax+00h]
0x18007b0aa  mov     rcx, [rbp+4Fh+var_80]
0x18007b0ae  lea     r8, [rbp+4Fh+length]
0x18007b0b2  mov     rdx, r15
0x18007b0b5  mov     qword ptr [rbp+4Fh+length], r12
0x18007b0b9  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18007b0be  test    eax, eax
0x18007b0c0  jns     short loc_18007B0F5
0x18007b0c2  mov     rcx, qword ptr [rbp+4Fh+length]; string
0x18007b0c6  call    cs:__imp_WindowsDeleteString
0x18007b0cd  nop     dword ptr [rax+rax+00h]
0x18007b0d2  lea     r8, [rbp+4Fh+length]; string
0x18007b0d6  mov     qword ptr [rbp+4Fh+length], r12
0x18007b0da  xor     edx, edx; length
0x18007b0dc  lea     rcx, word_1800BC2F8; sourceString
0x18007b0e3  call    cs:__imp_WindowsCreateString
0x18007b0ea  nop     dword ptr [rax+rax+00h]
0x18007b0ef  mov     ebx, eax
0x18007b0f1  test    eax, eax
0x18007b0f3  js      short loc_18007B13A
0x18007b0f5  mov     rax, qword ptr [rbp+4Fh+length]
0x18007b0f9  lea     rdx, [rbp+4Fh+var_58]
0x18007b0fd  mov     rcx, r14
0x18007b100  mov     [rbp+4Fh+var_58], rax
0x18007b104  call    ?Add@?$CTDynArray@PEAUHSTRING__@@$0BE@@@QEAAHAEBQEAUHSTRING__@@PEAK@Z; CTDynArray<HSTRING__ *,20>::Add(HSTRING__ * const &,ulong *)
0x18007b109  test    eax, eax
0x18007b10b  jz      loc_18007B1D3
0x18007b111  xor     ecx, ecx; string
0x18007b113  mov     qword ptr [rbp+4Fh+length], r12
0x18007b117  mov     ebx, r12d
0x18007b11a  call    cs:__imp_WindowsDeleteString
0x18007b121  nop     dword ptr [rax+rax+00h]
0x18007b126  lea     rcx, [rbp+4Fh+var_80]
0x18007b12a  mov     qword ptr [rbp+4Fh+length], r12
0x18007b12e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007b133  inc     esi
0x18007b135  jmp     loc_18007B052
0x18007b13a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b141  test    rcx, rcx
0x18007b144  jnz     short loc_18007B18D
0x18007b146  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b14d  nop     dword ptr [rax+rax+00h]
0x18007b152  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b159  mov     rcx, rax
0x18007b15c  test    rax, rax
0x18007b15f  jz      short loc_18007B17F
0x18007b161  mov     rax, [rax]
0x18007b164  mov     edx, 7F0h
0x18007b169  mov     rax, [rax+8]
0x18007b16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b172  test    eax, eax
0x18007b174  jz      short loc_18007B17F
0x18007b176  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b17d  jmp     short loc_18007B18D
0x18007b17f  lea     rcx, qword_1800DBF70; this
0x18007b186  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b18d  cmp     [rcx+8], r12b
0x18007b191  jz      short loc_18007B1B8
0x18007b193  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b198  cmp     [rax+7CCh], ebx
0x18007b19e  jz      short loc_18007B1B8
0x18007b1a0  mov     r9d, ebx; int
0x18007b1a3  lea     rdx, aCreatestringve; "CreateStringVectorFromMap"
0x18007b1aa  mov     r8d, 26Fh; int
0x18007b1b0  mov     rcx, rax; this
0x18007b1b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b1b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b1bf  jb      loc_18007B597
0x18007b1c5  mov     edx, 53h ; 'S'
0x18007b1ca  mov     [rsp+0C0h+var_A0], ebx
0x18007b1ce  jmp     loc_18007B57D
0x18007b1d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b1da  mov     edi, 8007000Eh
0x18007b1df  mov     ebx, edi
0x18007b1e1  test    rcx, rcx
0x18007b1e4  jnz     short loc_18007B22D
0x18007b1e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b1ed  nop     dword ptr [rax+rax+00h]
0x18007b1f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b1f9  mov     rcx, rax
0x18007b1fc  test    rax, rax
0x18007b1ff  jz      short loc_18007B21F
0x18007b201  mov     rax, [rax]
0x18007b204  mov     edx, 7F0h
0x18007b209  mov     rax, [rax+8]
0x18007b20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b212  test    eax, eax
0x18007b214  jz      short loc_18007B21F
0x18007b216  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b21d  jmp     short loc_18007B22D
0x18007b21f  lea     rcx, qword_1800DBF70; this
0x18007b226  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b22d  cmp     [rcx+8], r12b
0x18007b231  jz      short loc_18007B258
0x18007b233  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b238  cmp     [rax+7CCh], edi
0x18007b23e  jz      short loc_18007B258
0x18007b240  mov     r9d, edi; int
0x18007b243  lea     rdx, aCreatestringve; "CreateStringVectorFromMap"
0x18007b24a  mov     r8d, 278h; int
0x18007b250  mov     rcx, rax; this
0x18007b253  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b258  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b25f  jb      loc_18007B597
0x18007b265  mov     edx, 55h ; 'U'
0x18007b26a  jmp     loc_18007B579
0x18007b26f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b276  test    rcx, rcx
0x18007b279  jnz     short loc_18007B2C2
0x18007b27b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b282  nop     dword ptr [rax+rax+00h]
0x18007b287  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b28e  mov     rcx, rax
0x18007b291  test    rax, rax
0x18007b294  jz      short loc_18007B2B4
0x18007b296  mov     rax, [rax]
0x18007b299  mov     edx, 7F0h
0x18007b29e  mov     rax, [rax+8]
0x18007b2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b2a7  test    eax, eax
0x18007b2a9  jz      short loc_18007B2B4
0x18007b2ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b2b2  jmp     short loc_18007B2C2
0x18007b2b4  lea     rcx, qword_1800DBF70; this
0x18007b2bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b2c2  cmp     [rcx+8], r12b
0x18007b2c6  jz      short loc_18007B2ED
0x18007b2c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b2cd  cmp     [rax+7CCh], ebx
0x18007b2d3  jz      short loc_18007B2ED
0x18007b2d5  mov     r9d, ebx; int
0x18007b2d8  lea     rdx, aCreatestringve; "CreateStringVectorFromMap"
0x18007b2df  mov     r8d, 268h; int
0x18007b2e5  mov     rcx, rax; this
0x18007b2e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b2ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b2f4  jb      loc_18007B5AB
  ... truncated ...
```
