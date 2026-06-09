# CreateTypeVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,CTDynArray<_GUID,20> &)

- ea: `0x18001976c`
- end: `0x180019f7b`
- name: `?CreateTypeVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@AEAV?$CTDynArray@U_GUID@@$0BE@@@@Z`
- size: `2063`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018708`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001976c`
- `0x18003639c`
- `0x180054140`
- `0x1800b649c`
- `0x1800b64ec`
- `0x1800ca464`
- `0x1800ca854`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800197ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800197ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019f10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800198c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019a16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019b28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019bb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019c42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019ce8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019d8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019e34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800198c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019a16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019b28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019bb3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019c42`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019ce8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019d8a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019e34`

## string_xrefs

- `0x18001979b`: `CreateTypeVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateTypeVectorFromMap(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *); // rbx
  int v7; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  unsigned int i; // esi
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  _QWORD *v47; // rcx
  unsigned int j; // edi
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rcx
  _BYTE v53[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v54; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v55; // [rsp+40h] [rbp-29h] BYREF
  __int64 v56; // [rsp+48h] [rbp-21h] BYREF
  int v57; // [rsp+50h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-11h] BYREF
  __int64 v59; // [rsp+60h] [rbp-9h] BYREF
  __int128 v60; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+17h] BYREF

  v59 = 0;
  v56 = 0;
  v55 = 0;
  pv = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CreateTypeVectorFromMap", 325);
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
  WindowsCreateStringReference(L"InputType", 9u, &hstringHeader, &string);
  v7 = v6(a1, string, &v56);
  if ( v7 < 0 )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateTypeVectorFromMap", 325, v7);
    }
    if ( g_wppLevels )
    {
      v10 = 40;
LABEL_9:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v7);
      goto LABEL_117;
    }
    goto LABEL_117;
  }
  v60 = 0;
  if ( (int)Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v56, &v59) < 0 )
  {
    v54 = 0;
    v7 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
           &v56,
           &v54);
    if ( v7 >= 0 )
    {
      v7 = CreateMediaSubTypeFromMap(v54, v36, v37, &v60);
      if ( v7 >= 0 )
      {
        if ( (unsigned int)CTDynArray<_GUID,20>::Add(a4, &v60) )
        {
          v7 = 0;
        }
        else
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
          v7 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v45;
            if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
            {
              v44 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v44 + 8) )
          {
            v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
            if ( *((_DWORD *)v46 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v46, "CreateTypeVectorFromMap", 357, -2147024882);
          }
          if ( g_wppLevels )
          {
            v28 = 49;
LABEL_115:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v28,
              WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
              0,
              -2147024882);
          }
        }
        goto LABEL_116;
      }
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != v7 )
          CallStackContext::TraceFailure(v43, "CreateTypeVectorFromMap", 355, v7);
      }
      if ( !g_wppLevels )
      {
LABEL_116:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        goto LABEL_117;
      }
      v32 = 48;
    }
    else
    {
      v38 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
        if ( *((_DWORD *)v40 + 499) != v7 )
          CallStackContext::TraceFailure(v40, "CreateTypeVectorFromMap", 353, v7);
      }
      if ( !g_wppLevels )
        goto LABEL_116;
      v32 = 47;
    }
LABEL_70:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v32, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v7);
    goto LABEL_116;
  }
  v57 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v59 + 48LL))(v59, &v57);
  if ( v7 >= 0 )
  {
    if ( v57 == 1037 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v59 + 304LL))(v59, &v55, &pv);
      if ( v7 >= 0 )
      {
        for ( i = 0; i < v55; ++i )
        {
          v54 = 0;
          v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)pv + i);
          v22 = **v21;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
          v7 = v22(v21, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v54);
          if ( v7 < 0 )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
              if ( *((_DWORD *)v35 + 499) != v7 )
                CallStackContext::TraceFailure(v35, "CreateTypeVectorFromMap", 343, v7);
            }
            if ( g_wppLevels )
            {
              v32 = 44;
              goto LABEL_70;
            }
            goto LABEL_116;
          }
          v7 = CreateMediaSubTypeFromMap(v54, v23, v24, &v60);
          if ( v7 < 0 )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
              if ( *((_DWORD *)v31 + 499) != v7 )
                CallStackContext::TraceFailure(v31, "CreateTypeVectorFromMap", 345, v7);
            }
            if ( g_wppLevels )
            {
              v32 = 45;
              goto LABEL_70;
            }
            goto LABEL_116;
          }
          if ( !(unsigned int)CTDynArray<_GUID,20>::Add(a4, &v60) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
            v7 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                v25 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v25 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v25 + 8) )
            {
              v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)v27 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v27, "CreateTypeVectorFromMap", 347, -2147024882);
            }
            if ( g_wppLevels )
            {
              v28 = 46;
              goto LABEL_115;
            }
            goto LABEL_116;
          }
          v7 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        }
      }
      else
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)v19 + 499) != v7 )
            CallStackContext::TraceFailure(v19, "CreateTypeVectorFromMap", 338, v7);
        }
        if ( g_wppLevels )
        {
          v10 = 43;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      v7 = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)v16 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v16, "CreateTypeVectorFromMap", 335, -1072875845);
      }
      if ( g_wppLevels )
      {
        v10 = 42;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v7 )
        CallStackContext::TraceFailure(v13, "CreateTypeVectorFromMap", 331, v7);
    }
    if ( g_wppLevels )
    {
      v10 = 41;
      goto LABEL_9;
    }
  }
LABEL_117:
  v47 = pv;
  if ( pv )
  {
    for ( j = 0; j < v55; ++j )
    {
      v49 = v47[j];
      if ( v49 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v49 + 16LL))(v47[j]);
        *((_QWORD *)pv + j) = 0;
        v47 = pv;
      }
    }
    CoTaskMemFree(v47);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  v50 = v56;
  if ( v56 )
  {
    v56 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001976c  mov     [rsp-8+arg_8], rbx
0x180019771  mov     [rsp-8+arg_10], rsi
0x180019776  push    rbp
0x180019777  push    rdi
0x180019778  push    r13
0x18001977a  push    r14
0x18001977c  push    r15
0x18001977e  lea     rbp, [rsp-37h]
0x180019783  sub     rsp, 0A0h
0x18001978a  mov     rax, cs:__security_cookie
0x180019791  xor     rax, rsp
0x180019794  mov     [rbp+57h+var_28], rax
0x180019798  xor     r15d, r15d
0x18001979b  lea     r13, aCreatetypevect; "CreateTypeVectorFromMap"
0x1800197a2  mov     rdi, rcx
0x1800197a5  mov     [rbp+57h+var_60], r15
0x1800197a9  mov     esi, 145h
0x1800197ae  mov     [rbp+57h+var_78], r15
0x1800197b2  mov     r8d, esi; int
0x1800197b5  mov     [rbp+57h+var_80], r15d
0x1800197b9  mov     rdx, r13; char *
0x1800197bc  mov     [rbp+57h+pv], r15
0x1800197c0  lea     rcx, [rbp+57h+var_90]; this
0x1800197c4  mov     r14, r9
0x1800197c7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800197cc  mov     rax, [rdi]
0x1800197cf  lea     rcx, [rbp+57h+var_78]
0x1800197d3  mov     rbx, [rax+30h]
0x1800197d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800197dc  lea     r9, [rbp+57h+string]; string
0x1800197e0  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800197e4  lea     edx, [r15+9]; length
0x1800197e8  lea     rcx, aInputtype; "InputType"
0x1800197ef  call    cs:__imp_WindowsCreateStringReference
0x1800197f5  mov     rdx, [rbp+57h+string]
0x1800197f9  lea     r8, [rbp+57h+var_78]
0x1800197fd  mov     rcx, rdi
0x180019800  mov     rax, rbx
0x180019803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019808  mov     ebx, eax
0x18001980a  test    eax, eax
0x18001980c  jns     short loc_18001987F
0x18001980e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019815  test    rcx, rcx
0x180019818  jnz     short loc_180019826
0x18001981a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001981f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180019826  cmp     [rcx+8], r15b
0x18001982a  jz      short loc_18001984A
0x18001982c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019831  cmp     [rax+7CCh], ebx
0x180019837  jz      short loc_18001984A
0x180019839  mov     r9d, ebx; int
0x18001983c  mov     r8d, esi; int
0x18001983f  mov     rdx, r13; char *
0x180019842  mov     rcx, rax; this
0x180019845  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001984a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019851  jb      loc_180019ED1
0x180019857  mov     edx, 28h ; '('
0x18001985c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019863  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18001986a  xor     r9d, r9d
0x18001986d  mov     [rsp+0C0h+var_A0], ebx
0x180019871  mov     rcx, [rcx+10h]
0x180019875  call    WPP_SF_qD
0x18001987a  jmp     loc_180019ED1
0x18001987f  xorps   xmm0, xmm0
0x180019882  lea     rdx, [rbp+57h+var_60]
0x180019886  lea     rcx, [rbp+57h+var_78]
0x18001988a  movups  [rbp+57h+var_58], xmm0
0x18001988e  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x180019893  test    eax, eax
0x180019895  js      loc_180019CC1
0x18001989b  mov     rcx, [rbp+57h+var_60]
0x18001989f  lea     rdx, [rbp+57h+var_70]
0x1800198a3  mov     [rbp+57h+var_70], r15d
0x1800198a7  mov     rax, [rcx]
0x1800198aa  mov     rax, [rax+30h]
0x1800198ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198b3  mov     ebx, eax
0x1800198b5  test    eax, eax
0x1800198b7  jns     loc_180019948
0x1800198bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800198c4  test    rcx, rcx
0x1800198c7  jnz     short loc_18001990A
0x1800198c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800198cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800198d6  mov     rcx, rax
0x1800198d9  test    rax, rax
0x1800198dc  jz      short loc_1800198FC
0x1800198de  mov     rax, [rax]
0x1800198e1  mov     edx, 7F0h
0x1800198e6  mov     rax, [rax+8]
0x1800198ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198ef  test    eax, eax
0x1800198f1  jz      short loc_1800198FC
0x1800198f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800198fa  jmp     short loc_18001990A
0x1800198fc  lea     rcx, qword_180153440; this
0x180019903  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001990a  cmp     [rcx+8], r15b
0x18001990e  jz      short loc_180019931
0x180019910  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019915  cmp     [rax+7CCh], ebx
0x18001991b  jz      short loc_180019931
0x18001991d  mov     r9d, ebx; int
0x180019920  mov     r8d, 14Bh; int
0x180019926  mov     rdx, r13; char *
0x180019929  mov     rcx, rax; this
0x18001992c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019931  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019938  jb      loc_180019ED1
0x18001993e  mov     edx, 29h ; ')'
0x180019943  jmp     loc_18001985C
0x180019948  cmp     [rbp+57h+var_70], 40Dh
0x18001994f  jz      loc_1800199E5
0x180019955  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001995c  mov     ebx, 0C00D36BBh
0x180019961  test    rcx, rcx
0x180019964  jnz     short loc_1800199A7
0x180019966  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001996c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019973  mov     rcx, rax
0x180019976  test    rax, rax
0x180019979  jz      short loc_180019999
0x18001997b  mov     rax, [rax]
0x18001997e  mov     edx, 7F0h
0x180019983  mov     rax, [rax+8]
0x180019987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001998c  test    eax, eax
0x18001998e  jz      short loc_180019999
0x180019990  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019997  jmp     short loc_1800199A7
0x180019999  lea     rcx, qword_180153440; this
0x1800199a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800199a7  cmp     [rcx+8], r15b
0x1800199ab  jz      short loc_1800199CE
0x1800199ad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800199b2  cmp     [rax+7CCh], ebx
0x1800199b8  jz      short loc_1800199CE
0x1800199ba  mov     r9d, ebx; int
0x1800199bd  mov     r8d, 14Fh; int
0x1800199c3  mov     rdx, r13; char *
0x1800199c6  mov     rcx, rax; this
0x1800199c9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800199ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800199d5  jb      loc_180019ED1
0x1800199db  mov     edx, 2Ah ; '*'
0x1800199e0  jmp     loc_18001985C
0x1800199e5  mov     rcx, [rbp+57h+var_60]
0x1800199e9  lea     r8, [rbp+57h+pv]
0x1800199ed  lea     rdx, [rbp+57h+var_80]
0x1800199f1  mov     rax, [rcx]
0x1800199f4  mov     rax, [rax+130h]
0x1800199fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a00  mov     ebx, eax
0x180019a02  test    eax, eax
0x180019a04  jns     loc_180019A95
0x180019a0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a11  test    rcx, rcx
0x180019a14  jnz     short loc_180019A57
0x180019a16  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019a1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a23  mov     rcx, rax
0x180019a26  test    rax, rax
0x180019a29  jz      short loc_180019A49
0x180019a2b  mov     rax, [rax]
0x180019a2e  mov     edx, 7F0h
0x180019a33  mov     rax, [rax+8]
0x180019a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a3c  test    eax, eax
0x180019a3e  jz      short loc_180019A49
0x180019a40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a47  jmp     short loc_180019A57
0x180019a49  lea     rcx, qword_180153440; this
0x180019a50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a57  cmp     [rcx+8], r15b
0x180019a5b  jz      short loc_180019A7E
0x180019a5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019a62  cmp     [rax+7CCh], ebx
0x180019a68  jz      short loc_180019A7E
0x180019a6a  mov     r9d, ebx; int
0x180019a6d  mov     r8d, 152h; int
0x180019a73  mov     rdx, r13; char *
0x180019a76  mov     rcx, rax; this
0x180019a79  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019a7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019a85  jb      loc_180019ED1
0x180019a8b  mov     edx, 2Bh ; '+'
0x180019a90  jmp     loc_18001985C
0x180019a95  mov     esi, r15d
0x180019a98  cmp     esi, [rbp+57h+var_80]
0x180019a9b  jnb     loc_180019ED1
0x180019aa1  mov     rax, [rbp+57h+pv]
0x180019aa5  mov     [rbp+57h+var_88], r15
0x180019aa9  mov     ecx, esi
0x180019aab  mov     rdi, [rax+rcx*8]
0x180019aaf  lea     rcx, [rbp+57h+var_88]
0x180019ab3  mov     rax, [rdi]
0x180019ab6  mov     rbx, [rax]
0x180019ab9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019abe  lea     r8, [rbp+57h+var_88]
0x180019ac2  mov     rcx, rdi
0x180019ac5  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180019acc  mov     rax, rbx
0x180019acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ad4  mov     ebx, eax
0x180019ad6  test    eax, eax
0x180019ad8  js      loc_180019C36
0x180019ade  mov     rcx, [rbp+57h+var_88]
0x180019ae2  lea     r9, [rbp+57h+var_58]
0x180019ae6  call    ?CreateMediaSubTypeFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGAEBU_GUID@@PEAU5@@Z; CreateMediaSubTypeFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,_GUID const &,_GUID *)
0x180019aeb  mov     ebx, eax
0x180019aed  test    eax, eax
0x180019aef  js      loc_180019BA7
0x180019af5  lea     rdx, [rbp+57h+var_58]
0x180019af9  mov     rcx, r14
0x180019afc  call    ?Add@?$CTDynArray@U_GUID@@$0BE@@@QEAAHAEBU_GUID@@PEAK@Z; CTDynArray<_GUID,20>::Add(_GUID const &,ulong *)
0x180019b01  test    eax, eax
0x180019b03  jz      short loc_180019B15
0x180019b05  lea     rcx, [rbp+57h+var_88]
0x180019b09  mov     ebx, r15d
0x180019b0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019b11  inc     esi
0x180019b13  jmp     short loc_180019A98
0x180019b15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b1c  mov     edi, 8007000Eh
0x180019b21  mov     ebx, edi
0x180019b23  test    rcx, rcx
0x180019b26  jnz     short loc_180019B69
0x180019b28  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019b2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b35  mov     rcx, rax
0x180019b38  test    rax, rax
0x180019b3b  jz      short loc_180019B5B
0x180019b3d  mov     rax, [rax]
0x180019b40  mov     edx, 7F0h
0x180019b45  mov     rax, [rax+8]
0x180019b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b4e  test    eax, eax
0x180019b50  jz      short loc_180019B5B
0x180019b52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b59  jmp     short loc_180019B69
0x180019b5b  lea     rcx, qword_180153440; this
0x180019b62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019b69  cmp     [rcx+8], r15b
0x180019b6d  jz      short loc_180019B90
0x180019b6f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019b74  cmp     [rax+7CCh], edi
0x180019b7a  jz      short loc_180019B90
0x180019b7c  mov     r9d, edi; int
0x180019b7f  mov     r8d, 15Bh; int
0x180019b85  mov     rdx, r13; char *
0x180019b88  mov     rcx, rax; this
0x180019b8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019b90  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019b97  jb      loc_180019EC8
0x180019b9d  mov     edx, 2Eh ; '.'
0x180019ba2  jmp     loc_180019EAA
0x180019ba7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019bae  test    rcx, rcx
0x180019bb1  jnz     short loc_180019BF4
0x180019bb3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019bb9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019bc0  mov     rcx, rax
0x180019bc3  test    rax, rax
0x180019bc6  jz      short loc_180019BE6
0x180019bc8  mov     rax, [rax]
0x180019bcb  mov     edx, 7F0h
0x180019bd0  mov     rax, [rax+8]
0x180019bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bd9  test    eax, eax
0x180019bdb  jz      short loc_180019BE6
0x180019bdd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019be4  jmp     short loc_180019BF4
0x180019be6  lea     rcx, qword_180153440; this
0x180019bed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019bf4  cmp     [rcx+8], r15b
0x180019bf8  jz      short loc_180019C1B
0x180019bfa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019bff  cmp     [rax+7CCh], ebx
0x180019c05  jz      short loc_180019C1B
0x180019c07  mov     r9d, ebx; int
0x180019c0a  mov     r8d, 159h; int
0x180019c10  mov     rdx, r13; char *
0x180019c13  mov     rcx, rax; this
0x180019c16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019c1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019c22  jb      loc_180019EC8
0x180019c28  mov     edx, 2Dh ; '-'
0x180019c2d  mov     [rsp+0C0h+var_A0], ebx
0x180019c31  jmp     loc_180019EAE
0x180019c36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c3d  test    rcx, rcx
0x180019c40  jnz     short loc_180019C83
0x180019c42  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019c48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c4f  mov     rcx, rax
0x180019c52  test    rax, rax
  ... truncated ...
```
