# CreateStringVectorFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,bool,CTDynArray<HSTRING__ *,20> &)

- ea: `0x18001e1c4`
- end: `0x18001ea0d`
- name: `?CreateStringVectorFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG1_NAEAV?$CTDynArray@PEAUHSTRING__@@$0BE@@@@Z`
- size: `2121`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a9620`

## callees

- `0x180004870`
- `0x18001df94`
- `0x18001dfc8`
- `0x18001e1c4`
- `0x18001fce4`
- `0x180020b80`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180097b3c`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e2c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e2c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e46f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e3d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e458`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e9a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e3d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e458`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e9a1`

## string_xrefs

- `0x18001e1f4`: `CreateStringVectorFromMap`
- `0x18001e703`: `CreateStringVectorFromMap`
- `0x18001e79b`: `CreateStringVectorFromMap`
- `0x18001e829`: `CreateStringVectorFromMap`

## pseudocode

```c
__int64 __fastcall CreateStringVectorFromMap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 (__fastcall *v7)(__int64, HSTRING__ *, _QWORD); // rbx
  HRESULT v8; // ebx
  CallStackTracing *v9; // rcx
  _QWORD *v10; // rcx
  unsigned int j; // edi
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v14; // rcx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rdi
  unsigned int i; // esi
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v21; // rdx
  __int64 v22; // rcx
  CallStackTracing *v23; // rcx
  __int64 v24; // rdx
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rdi
  CallStackTracing *v27; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v29; // rcx
  __int64 v30; // rdx
  struct CallStackContext *v31; // rax
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  __int64 v34; // rdx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rdx
  struct CallStackContext *v38; // rax
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  HSTRING v43; // rcx
  struct CallStackContext *v44; // rax
  HSTRING string; // [rsp+30h] [rbp-31h] BYREF
  __int64 v46; // [rsp+38h] [rbp-29h] BYREF
  CallStackScopeTrace v47; // [rsp+40h] [rbp-21h] BYREF
  unsigned int v48; // [rsp+44h] [rbp-1Dh] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-11h] BYREF
  __int64 v51; // [rsp+58h] [rbp-9h] BYREF
  HSTRING v52; // [rsp+60h] [rbp-1h] BYREF
  Windows::Internal::StringReference v53; // [rsp+68h] [rbp+7h] BYREF

  v51 = 0;
  v49 = 0;
  v48 = 0;
  pv = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v47, "CreateStringVectorFromMap", 607);
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING__ *, _QWORD))(*(_QWORD *)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  Windows::Internal::StringReference::_ConstructorHelper(&v53, L"InputType");
  v8 = v7(a1, v53._hstring, &v49);
  if ( v8 < 0 )
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v9->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
      if ( ThreadRelativeContext->m_result != v8 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateStringVectorFromMap", 607, v8);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_5;
    v30 = 80;
LABEL_54:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v8);
    goto LABEL_5;
  }
  v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
  v17 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))**v49;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  if ( v17(v16, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v51) < 0 )
  {
    v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
    v46 = 0;
    v26 = **v49;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v8 = v26(v25, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v46);
    if ( v8 < 0 )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v39 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v39->m_fEnabled )
      {
        v40 = CallStackTracing::GetThreadRelativeContext(v39);
        if ( v40->m_result != v8 )
          CallStackContext::TraceFailure(v40, "CreateStringVectorFromMap", 641, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v37 = 86;
LABEL_85:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v8);
      }
      goto LABEL_86;
    }
    WindowsDeleteString(0);
    string = 0;
    if ( (int)CreateStringFromMap(v46, a3, &string) >= 0
      || (v8 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, &word_1801CC94C, 0),
          v8 >= 0) )
    {
      v52 = string;
      if ( (unsigned int)CTDynArray<HSTRING__ *,20>::Add(a5, &v52) )
      {
        v8 = 0;
        string = 0;
        v43 = 0;
        goto LABEL_101;
      }
      v42 = CallStackTracing::s_wpInstance;
      v8 = -2147024882;
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
        v44 = CallStackTracing::GetThreadRelativeContext(v42);
        if ( v44->m_result != -2147024882 )
          CallStackContext::TraceFailure(v44, "CreateStringVectorFromMap", 657, -2147024882);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v34 = 89;
LABEL_99:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v34,
          WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
          0,
          -2147024882);
      }
    }
    else
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
        v41 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( v41->m_result != v8 )
          CallStackContext::TraceFailure(v41, "CreateStringVectorFromMap", 648, v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v24 = 87;
LABEL_42:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v8);
      }
    }
LABEL_100:
    v43 = string;
LABEL_101:
    WindowsDeleteString(v43);
    string = 0;
LABEL_86:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    goto LABEL_5;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v51 + 304LL))(v51, &v48, &pv);
  if ( v8 < 0 )
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
      v31 = CallStackTracing::GetThreadRelativeContext(v29);
      if ( v31->m_result != v8 )
        CallStackContext::TraceFailure(v31, "CreateStringVectorFromMap", 611, v8);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v30 = 81;
      goto LABEL_54;
    }
  }
  else
  {
    for ( i = 0; i < v48; ++i )
    {
      v46 = 0;
      v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)pv + i);
      v20 = **v19;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      v8 = v20(v19, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v46);
      if ( v8 < 0 )
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
          v38 = CallStackTracing::GetThreadRelativeContext(v36);
          if ( v38->m_result != v8 )
            CallStackContext::TraceFailure(v38, "CreateStringVectorFromMap", 616, v8);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v37 = 82;
          goto LABEL_85;
        }
        goto LABEL_86;
      }
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      if ( (int)CreateStringFromMap(v46, a3, &string) < 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        v8 = WindowsCreateString(&word_1801CC94C, 0, &string);
        if ( v8 < 0 )
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
            v32 = CallStackTracing::GetThreadRelativeContext(v23);
            if ( v32->m_result != v8 )
              CallStackContext::TraceFailure(v32, "CreateStringVectorFromMap", 623, v8);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v24 = 83;
            goto LABEL_42;
          }
          goto LABEL_100;
        }
      }
      v21 = *(unsigned int *)(a5 + 200);
      v52 = string;
      if ( (int)CTSparseBlock<unsigned long,HSTRING__ *,20,0>::SetValue(a5, v21, &v52) < 0 )
      {
        v33 = CallStackTracing::s_wpInstance;
        v8 = -2147024882;
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
          v35 = CallStackTracing::GetThreadRelativeContext(v33);
          if ( v35->m_result != -2147024882 )
            CallStackContext::TraceFailure(v35, "CreateStringVectorFromMap", 632, -2147024882);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v34 = 85;
          goto LABEL_99;
        }
        goto LABEL_100;
      }
      ++*(_DWORD *)(a5 + 200);
      v8 = 0;
      string = 0;
      WindowsDeleteString(0);
      v22 = v46;
      string = 0;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
  }
LABEL_5:
  v10 = pv;
  if ( pv )
  {
    for ( j = 0; j < v48; ++j )
    {
      v12 = v10[j];
      if ( v12 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 16LL))(v10[j]);
        *((_QWORD *)pv + j) = 0;
        v10 = pv;
      }
    }
    CoTaskMemFree(v10);
  }
  CallStackScopeTrace::~CallStackScopeTrace(&v47);
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
  if ( v49 )
  {
    v49 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
  }
  v14 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001e1c4  mov     [rsp-8+arg_8], rbx
0x18001e1c9  mov     [rsp-8+arg_18], rsi
0x18001e1ce  push    rbp
0x18001e1cf  push    rdi
0x18001e1d0  push    r12
0x18001e1d2  push    r14
0x18001e1d4  push    r15
0x18001e1d6  lea     rbp, [rsp-2Fh]
0x18001e1db  sub     rsp, 90h
0x18001e1e2  mov     rax, cs:__security_cookie
0x18001e1e9  xor     rax, rsp
0x18001e1ec  mov     [rbp+4Fh+var_28], rax
0x18001e1f0  mov     r14, [rbp+4Fh+arg_20]
0x18001e1f4  lea     rsi, aCreatestringve; "CreateStringVectorFromMap"
0x18001e1fb  xor     r12d, r12d
0x18001e1fe  mov     r15, r8
0x18001e201  mov     rdi, rcx
0x18001e204  mov     [rbp+4Fh+var_58], r12
0x18001e208  mov     rdx, rsi; char *
0x18001e20b  mov     [rbp+4Fh+var_68], r12
0x18001e20f  mov     r8d, 25Fh; int
0x18001e215  mov     [rbp+4Fh+var_6C], r12d
0x18001e219  lea     rcx, [rbp+4Fh+var_70]; this
0x18001e21d  mov     [rbp+4Fh+pv], r12
0x18001e221  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001e226  mov     rax, [rdi]
0x18001e229  lea     rcx, [rbp+4Fh+var_68]
0x18001e22d  mov     rbx, [rax+30h]
0x18001e231  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001e236  lea     rdx, aInputtype; "InputType"
0x18001e23d  lea     rcx, [rbp+4Fh+var_48]; this
0x18001e241  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001e246  mov     rdx, [rbp+4Fh+var_48._hstring]
0x18001e24a  lea     r8, [rbp+4Fh+var_68]
0x18001e24e  mov     rcx, rdi
0x18001e251  mov     rax, rbx
0x18001e254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e259  mov     ebx, eax
0x18001e25b  test    eax, eax
0x18001e25d  jns     loc_18001E334
0x18001e263  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001e26a  test    rcx, rcx
0x18001e26d  jz      loc_18001E5CB
0x18001e273  cmp     [rcx+8], r12b
0x18001e277  jnz     loc_18001E611
0x18001e27d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e284  jnb     loc_18001E9DC
0x18001e28a  mov     rcx, [rbp+4Fh+pv]
0x18001e28e  test    rcx, rcx
0x18001e291  jz      short loc_18001E2CF
0x18001e293  mov     edi, r12d
0x18001e296  cmp     [rbp+4Fh+var_6C], r12d
0x18001e29a  jbe     short loc_18001E2C9
0x18001e29c  mov     esi, edi
0x18001e29e  mov     rdx, [rcx+rsi*8]
0x18001e2a2  test    rdx, rdx
0x18001e2a5  jz      short loc_18001E2C2
0x18001e2a7  mov     rax, [rdx]
0x18001e2aa  mov     rcx, rdx
0x18001e2ad  mov     rax, [rax+10h]
0x18001e2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2b6  mov     rax, [rbp+4Fh+pv]
0x18001e2ba  mov     [rax+rsi*8], r12
0x18001e2be  mov     rcx, [rbp+4Fh+pv]; pv
0x18001e2c2  inc     edi
0x18001e2c4  cmp     edi, [rbp+4Fh+var_6C]
0x18001e2c7  jb      short loc_18001E29C
0x18001e2c9  call    cs:__imp_CoTaskMemFree
0x18001e2cf  lea     rcx, [rbp+4Fh+var_70]; this
0x18001e2d3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001e2d8  mov     rcx, [rbp+4Fh+var_68]
0x18001e2dc  test    rcx, rcx
0x18001e2df  jz      short loc_18001E2F1
0x18001e2e1  mov     [rbp+4Fh+var_68], r12
0x18001e2e5  mov     rax, [rcx]
0x18001e2e8  mov     rax, [rax+10h]
0x18001e2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2f1  mov     rcx, [rbp+4Fh+var_58]
0x18001e2f5  test    rcx, rcx
0x18001e2f8  jz      short loc_18001E30A
0x18001e2fa  mov     [rbp+4Fh+var_58], r12
0x18001e2fe  mov     rax, [rcx]
0x18001e301  mov     rax, [rax+10h]
0x18001e305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e30a  mov     eax, ebx
0x18001e30c  mov     rcx, [rbp+4Fh+var_28]
0x18001e310  xor     rcx, rsp; StackCookie
0x18001e313  call    __security_check_cookie
0x18001e318  lea     r11, [rsp+0B0h+var_20]
0x18001e320  mov     rbx, [r11+38h]
0x18001e324  mov     rsi, [r11+48h]
0x18001e328  mov     rsp, r11
0x18001e32b  pop     r15
0x18001e32d  pop     r14
0x18001e32f  pop     r12
0x18001e331  pop     rdi
0x18001e332  pop     rbp
0x18001e333  retn
0x18001e334  mov     rbx, [rbp+4Fh+var_68]
0x18001e338  lea     rcx, [rbp+4Fh+var_58]
0x18001e33c  mov     rax, [rbx]
0x18001e33f  mov     rdi, [rax]
0x18001e342  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001e347  lea     r8, [rbp+4Fh+var_58]
0x18001e34b  mov     rcx, rbx
0x18001e34e  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18001e355  mov     rax, rdi
0x18001e358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e35d  test    eax, eax
0x18001e35f  js      loc_18001E4E5
0x18001e365  mov     rcx, [rbp+4Fh+var_58]
0x18001e369  lea     r8, [rbp+4Fh+pv]
0x18001e36d  lea     rdx, [rbp+4Fh+var_6C]
0x18001e371  mov     rax, [rcx]
0x18001e374  mov     rax, [rax+130h]
0x18001e37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e380  mov     ebx, eax
0x18001e382  test    eax, eax
0x18001e384  js      loc_18001E63B
0x18001e38a  mov     esi, r12d
0x18001e38d  cmp     esi, [rbp+4Fh+var_6C]
0x18001e390  jnb     loc_18001E28A
0x18001e396  mov     rax, [rbp+4Fh+pv]
0x18001e39a  mov     [rbp+4Fh+var_78], r12
0x18001e39e  mov     ecx, esi
0x18001e3a0  mov     rdi, [rax+rcx*8]
0x18001e3a4  lea     rcx, [rbp+4Fh+var_78]
0x18001e3a8  mov     rax, [rdi]
0x18001e3ab  mov     rbx, [rax]
0x18001e3ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001e3b3  lea     r8, [rbp+4Fh+var_78]
0x18001e3b7  mov     rcx, rdi
0x18001e3ba  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001e3c1  mov     rax, rbx
0x18001e3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3c9  mov     ebx, eax
0x18001e3cb  test    eax, eax
0x18001e3cd  js      loc_18001E7B2
0x18001e3d3  xor     ecx, ecx; string
0x18001e3d5  mov     [rbp+4Fh+string], r12
0x18001e3d9  call    cs:__imp_WindowsDeleteString
0x18001e3df  mov     rcx, [rbp+4Fh+var_78]
0x18001e3e3  lea     r8, [rbp+4Fh+string]
0x18001e3e7  mov     rdx, r15
0x18001e3ea  mov     [rbp+4Fh+string], r12
0x18001e3ee  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18001e3f3  test    eax, eax
0x18001e3f5  js      short loc_18001E454
0x18001e3f7  mov     rax, [rbp+4Fh+string]
0x18001e3fb  lea     r8, [rbp+4Fh+var_50]
0x18001e3ff  mov     edx, [r14+0C8h]
0x18001e406  mov     rcx, r14
0x18001e409  mov     [rbp+4Fh+var_50], rax
0x18001e40d  call    ?SetValue@?$CTSparseBlock@KPEAUHSTRING__@@$0BE@$0A@@@QEAAJKAEBQEAUHSTRING__@@@Z; CTSparseBlock<ulong,HSTRING__ *,20,0>::SetValue(ulong,HSTRING__ * const &)
0x18001e412  test    eax, eax
0x18001e414  js      loc_18001E71D
0x18001e41a  inc     dword ptr [r14+0C8h]
0x18001e421  xor     ecx, ecx; string
0x18001e423  mov     ebx, r12d
0x18001e426  mov     [rbp+4Fh+string], r12
0x18001e42a  call    cs:__imp_WindowsDeleteString
0x18001e430  mov     rcx, [rbp+4Fh+var_78]
0x18001e434  mov     [rbp+4Fh+string], r12
0x18001e438  test    rcx, rcx
0x18001e43b  jz      short loc_18001E44D
0x18001e43d  mov     [rbp+4Fh+var_78], r12
0x18001e441  mov     rax, [rcx]
0x18001e444  mov     rax, [rax+10h]
0x18001e448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e44d  inc     esi
0x18001e44f  jmp     loc_18001E38D
0x18001e454  mov     rcx, [rbp+4Fh+string]; string
0x18001e458  call    cs:__imp_WindowsDeleteString
0x18001e45e  lea     r8, [rbp+4Fh+string]; string
0x18001e462  mov     [rbp+4Fh+string], r12
0x18001e466  xor     edx, edx; length
0x18001e468  lea     rcx, word_1801CC94C; sourceString
0x18001e46f  call    cs:__imp_WindowsCreateString
0x18001e475  mov     ebx, eax
0x18001e477  test    eax, eax
0x18001e479  jns     loc_18001E3F7
0x18001e47f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e486  test    rcx, rcx
0x18001e489  jnz     short loc_18001E4C4
0x18001e48b  mov     rax, cs:stru_1801FC290.__vftable
0x18001e492  lea     rcx, stru_1801FC290
0x18001e499  mov     edx, 7F0h
0x18001e49e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e4a5  mov     rax, [rax+8]
0x18001e4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ae  test    eax, eax
0x18001e4b0  jnz     loc_18001E6E3
0x18001e4b6  lea     rcx, stru_1801F8A30; this
0x18001e4bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e4c4  cmp     [rcx+8], r12b
0x18001e4c8  jnz     loc_18001E6EF
0x18001e4ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e4d5  jb      loc_18001E99D
0x18001e4db  mov     edx, 53h ; 'S'
0x18001e4e0  jmp     loc_18001E5C2
0x18001e4e5  mov     rbx, [rbp+4Fh+var_68]
0x18001e4e9  lea     rcx, [rbp+4Fh+var_78]
0x18001e4ed  mov     [rbp+4Fh+var_78], r12
0x18001e4f1  mov     rax, [rbx]
0x18001e4f4  mov     rdi, [rax]
0x18001e4f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001e4fc  lea     r8, [rbp+4Fh+var_78]
0x18001e500  mov     rcx, rbx
0x18001e503  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001e50a  mov     rax, rdi
0x18001e50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e512  mov     ebx, eax
0x18001e514  test    eax, eax
0x18001e516  js      loc_18001E840
0x18001e51c  xor     ecx, ecx; string
0x18001e51e  mov     [rbp+4Fh+string], r12
0x18001e522  call    cs:__imp_WindowsDeleteString
0x18001e528  mov     rcx, [rbp+4Fh+var_78]
0x18001e52c  lea     r8, [rbp+4Fh+string]
0x18001e530  mov     rdx, r15
0x18001e533  mov     [rbp+4Fh+string], r12
0x18001e537  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18001e53c  test    eax, eax
0x18001e53e  jns     loc_18001E9E6
0x18001e544  xor     r8d, r8d; unsigned int
0x18001e547  lea     rdx, word_1801CC94C; unsigned __int16 *
0x18001e54e  lea     rcx, [rbp+4Fh+string]; this
0x18001e552  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001e557  mov     ebx, eax
0x18001e559  test    eax, eax
0x18001e55b  jns     loc_18001E9E6
0x18001e561  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e568  test    rcx, rcx
0x18001e56b  jnz     short loc_18001E5A6
0x18001e56d  mov     rax, cs:stru_1801FC290.__vftable
0x18001e574  lea     rcx, stru_1801FC290
0x18001e57b  mov     edx, 7F0h
0x18001e580  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e587  mov     rax, [rax+8]
0x18001e58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e590  test    eax, eax
0x18001e592  jnz     loc_18001E8ED
0x18001e598  lea     rcx, stru_1801F8A30; this
0x18001e59f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e5a6  cmp     [rcx+8], r12b
0x18001e5aa  jnz     loc_18001E8F9
0x18001e5b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e5b7  jb      loc_18001E99D
0x18001e5bd  mov     edx, 57h ; 'W'
0x18001e5c2  mov     [rsp+0B0h+var_90], ebx
0x18001e5c6  jmp     loc_18001E983
0x18001e5cb  mov     rdx, cs:stru_1801FC290.__vftable
0x18001e5d2  lea     rcx, stru_1801FC290
0x18001e5d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e5e0  mov     rax, [rdx+8]
0x18001e5e4  mov     edx, 7F0h
0x18001e5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ee  test    eax, eax
0x18001e5f0  jnz     short loc_18001E605
0x18001e5f2  lea     rcx, stru_1801F8A30
0x18001e5f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e600  jmp     loc_18001E273
0x18001e605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e60c  jmp     loc_18001E273
0x18001e611  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001e616  cmp     [rax+7CCh], ebx
0x18001e61c  jz      loc_18001E27D
0x18001e622  mov     r9d, ebx; int
0x18001e625  mov     r8d, 25Fh; int
0x18001e62b  mov     rdx, rsi; char *
0x18001e62e  mov     rcx, rax; this
0x18001e631  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001e636  jmp     loc_18001E27D
0x18001e63b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e642  test    rcx, rcx
0x18001e645  jnz     short loc_18001E67C
0x18001e647  mov     rax, cs:stru_1801FC290.__vftable
0x18001e64e  lea     rcx, stru_1801FC290
0x18001e655  mov     edx, 7F0h
0x18001e65a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e661  mov     rax, [rax+8]
0x18001e665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e66a  test    eax, eax
0x18001e66c  jnz     short loc_18001E6B7
0x18001e66e  lea     rcx, stru_1801F8A30; this
0x18001e675  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e67c  cmp     [rcx+8], r12b
0x18001e680  jnz     short loc_18001E6C0
0x18001e682  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e689  jb      loc_18001E28A
0x18001e68f  mov     edx, 51h ; 'Q'
0x18001e694  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e69b  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18001e6a2  xor     r9d, r9d
0x18001e6a5  mov     [rsp+0B0h+var_90], ebx
0x18001e6a9  mov     rcx, [rcx+10h]
0x18001e6ad  call    WPP_SF_qD
0x18001e6b2  jmp     loc_18001E28A
0x18001e6b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001e6be  jmp     short loc_18001E67C
  ... truncated ...
```
