# CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)

- ea: `0x18007656c`
- end: `0x180076ba8`
- name: `?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z`
- size: `1596`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180076bb0`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18003c478`
- `0x180071330`
- `0x180074f0c`
- `0x18007656c`
- `0x1800775b0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800765b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007666f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800768af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800765b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007666f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800768af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076966`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800765e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800766a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007681e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800768e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076997`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076a3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076ae7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800765e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800766a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076748`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007681e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800768e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076997`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076a3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180076ae7`

## string_xrefs

- `0x18007658e`: `CreateExtensionInfoFromMediaExtensionMap`
- `0x180076a1d`: `inProcessMediaExtension`
- `0x1800767ca`: `@AppServiceName`
- `0x1800768bb`: `@AppServiceName`
- `0x180076ac5`: `webPlatformMediaExtension`

## pseudocode

```c
__int64 __fastcall CreateExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 *a2, HSTRING *a3)
{
  __int64 v6; // rdx
  int StringFromMap; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rax
  __int64 (__fastcall *v27)(__int64 *, __int64, char *); // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
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
  char v59; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v60[7]; // [rsp+31h] [rbp-57h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-50h] BYREF
  __int64 v62; // [rsp+50h] [rbp-38h]

  v59 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v60, "CreateExtensionInfoFromMediaExtensionMap", 927);
  WindowsDeleteString(*a3);
  *a3 = 0;
  StringFromMap = CreateStringFromMap(a1, L"@PackageFamilyName", a3);
  if ( StringFromMap >= 0 )
  {
    WindowsDeleteString(a3[1]);
    a3[1] = 0;
    StringFromMap = CreateStringFromMap(a1, L"@PackageFullName", a3 + 1);
    if ( StringFromMap >= 0 )
    {
      StringFromMap = CreateBOOLFromMap(a1, L"@PackageRequiresRegistration", a3 + 4);
      if ( StringFromMap >= 0 )
      {
        v26 = *a2;
        v62 = 0;
        v27 = *(__int64 (__fastcall **)(__int64 *, __int64, char *))(v26 + 64);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@AppServiceName", 0x10u, 0xFu);
        StringFromMap = v27(a2, v62, &v59);
        if ( StringFromMap >= 0 )
        {
          if ( v59
            && (WindowsDeleteString(a3[2]),
                a3[2] = 0,
                StringFromMap = CreateStringFromMap(a2, L"@AppServiceName", a3 + 2),
                StringFromMap < 0) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
              CallStackTracing::s_wpInstance = v38;
              if ( v38
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
              {
                v37 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v37 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v37 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != StringFromMap )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CreateExtensionInfoFromMediaExtensionMap",
                  935,
                  StringFromMap);
            }
            if ( g_wppLevels )
            {
              v13 = 119;
              goto LABEL_90;
            }
          }
          else
          {
            WindowsDeleteString(a3[3]);
            a3[3] = 0;
            StringFromMap = CreateStringFromMap(a2, L"@DisplayName", a3 + 3);
            if ( StringFromMap >= 0 )
            {
              StringFromMap = CreateBOOLFromMap(a1, L"inProcessMediaExtension", (char *)a3 + 33);
              if ( StringFromMap >= 0 )
              {
                StringFromMap = CreateBOOLFromMap(a1, L"webPlatformMediaExtension", (char *)a3 + 34);
                if ( StringFromMap < 0 )
                {
                  v55 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52, v53, v54);
                    CallStackTracing::s_wpInstance = v56;
                    if ( v56
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
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
                    if ( *((_DWORD *)v57 + 499) != StringFromMap )
                      CallStackContext::TraceFailure(
                        v57,
                        "CreateExtensionInfoFromMediaExtensionMap",
                        941,
                        StringFromMap);
                  }
                  if ( g_wppLevels )
                  {
                    v13 = 122;
                    goto LABEL_90;
                  }
                }
              }
              else
              {
                v49 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46, v47, v48);
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
                  if ( *((_DWORD *)v51 + 499) != StringFromMap )
                    CallStackContext::TraceFailure(v51, "CreateExtensionInfoFromMediaExtensionMap", 940, StringFromMap);
                }
                if ( g_wppLevels )
                {
                  v13 = 121;
                  goto LABEL_90;
                }
              }
            }
            else
            {
              v43 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v40, v41, v42);
                CallStackTracing::s_wpInstance = v44;
                if ( v44
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                {
                  v43 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v43 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v43 + 8) )
              {
                v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                if ( *((_DWORD *)v45 + 499) != StringFromMap )
                  CallStackContext::TraceFailure(v45, "CreateExtensionInfoFromMediaExtensionMap", 938, StringFromMap);
              }
              if ( g_wppLevels )
              {
                v13 = 120;
                goto LABEL_90;
              }
            }
          }
        }
        else
        {
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          v62 = 0;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)v33 + 499) != StringFromMap )
              CallStackContext::TraceFailure(v33, "CreateExtensionInfoFromMediaExtensionMap", 931, StringFromMap);
          }
          if ( g_wppLevels )
          {
            v13 = 118;
            goto LABEL_90;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != StringFromMap )
            CallStackContext::TraceFailure(v25, "CreateExtensionInfoFromMediaExtensionMap", 929, StringFromMap);
        }
        if ( g_wppLevels )
        {
          v13 = 117;
          goto LABEL_90;
        }
      }
    }
    else
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != StringFromMap )
          CallStackContext::TraceFailure(v19, "CreateExtensionInfoFromMediaExtensionMap", 928, StringFromMap);
      }
      if ( g_wppLevels )
      {
        v13 = 116;
        goto LABEL_90;
      }
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != StringFromMap )
        CallStackContext::TraceFailure(v12, "CreateExtensionInfoFromMediaExtensionMap", 927, StringFromMap);
    }
    if ( g_wppLevels )
    {
      v13 = 115;
LABEL_90:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        StringFromMap);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v60);
  return (unsigned int)StringFromMap;
}

```

## disassembly

```asm
0x18007656c  mov     [rsp+arg_18], rbx
0x180076571  push    rbp
0x180076572  push    rsi
0x180076573  push    rdi
0x180076574  push    r14
0x180076576  push    r15
0x180076578  sub     rsp, 60h
0x18007657c  mov     rax, cs:__security_cookie
0x180076583  xor     rax, rsp
0x180076586  mov     [rsp+88h+var_30], rax
0x18007658b  mov     rdi, r8
0x18007658e  lea     r15, aCreateextensio_0; "CreateExtensionInfoFromMediaExtensionMa"...
0x180076595  mov     r14, rdx
0x180076598  mov     rsi, rcx
0x18007659b  xor     ebp, ebp
0x18007659d  lea     rcx, [rsp+88h+var_57]; this
0x1800765a2  mov     rdx, r15; char *
0x1800765a5  mov     [rsp+88h+var_58], bpl
0x1800765aa  mov     r8d, 39Fh; int
0x1800765b0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800765b5  mov     rcx, [rdi]; string
0x1800765b8  call    cs:__imp_WindowsDeleteString
0x1800765be  mov     r8, rdi
0x1800765c1  mov     [rdi], rbp
0x1800765c4  lea     rdx, aPackagefamilyn; "@PackageFamilyName"
0x1800765cb  mov     rcx, rsi
0x1800765ce  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800765d3  mov     ebx, eax
0x1800765d5  test    eax, eax
0x1800765d7  jns     loc_180076668
0x1800765dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800765e4  test    rcx, rcx
0x1800765e7  jnz     short loc_18007662A
0x1800765e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800765ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800765f6  mov     rcx, rax
0x1800765f9  test    rax, rax
0x1800765fc  jz      short loc_18007661C
0x1800765fe  mov     rax, [rax]
0x180076601  mov     edx, 7F0h
0x180076606  mov     rax, [rax+8]
0x18007660a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007660f  test    eax, eax
0x180076611  jz      short loc_18007661C
0x180076613  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007661a  jmp     short loc_18007662A
0x18007661c  lea     rcx, qword_1800D6F70; this
0x180076623  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007662a  cmp     [rcx+8], bpl
0x18007662e  jz      short loc_180076651
0x180076630  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076635  cmp     [rax+7CCh], ebx
0x18007663b  jz      short loc_180076651
0x18007663d  mov     r9d, ebx; int
0x180076640  mov     r8d, 39Fh; int
0x180076646  mov     rdx, r15; char *
0x180076649  mov     rcx, rax; this
0x18007664c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076651  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076658  jb      loc_180076B7B
0x18007665e  mov     edx, 73h ; 's'
0x180076663  jmp     loc_180076B5D
0x180076668  lea     rbx, [rdi+8]
0x18007666c  mov     rcx, [rbx]; string
0x18007666f  call    cs:__imp_WindowsDeleteString
0x180076675  mov     r8, rbx
0x180076678  mov     [rbx], rbp
0x18007667b  lea     rdx, aPackagefullnam; "@PackageFullName"
0x180076682  mov     rcx, rsi
0x180076685  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18007668a  mov     ebx, eax
0x18007668c  test    eax, eax
0x18007668e  jns     loc_18007671F
0x180076694  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007669b  test    rcx, rcx
0x18007669e  jnz     short loc_1800766E1
0x1800766a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800766a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800766ad  mov     rcx, rax
0x1800766b0  test    rax, rax
0x1800766b3  jz      short loc_1800766D3
0x1800766b5  mov     rax, [rax]
0x1800766b8  mov     edx, 7F0h
0x1800766bd  mov     rax, [rax+8]
0x1800766c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766c6  test    eax, eax
0x1800766c8  jz      short loc_1800766D3
0x1800766ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800766d1  jmp     short loc_1800766E1
0x1800766d3  lea     rcx, qword_1800D6F70; this
0x1800766da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800766e1  cmp     [rcx+8], bpl
0x1800766e5  jz      short loc_180076708
0x1800766e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800766ec  cmp     [rax+7CCh], ebx
0x1800766f2  jz      short loc_180076708
0x1800766f4  mov     r9d, ebx; int
0x1800766f7  mov     r8d, 3A0h; int
0x1800766fd  mov     rdx, r15; char *
0x180076700  mov     rcx, rax; this
0x180076703  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076708  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007670f  jb      loc_180076B7B
0x180076715  mov     edx, 74h ; 't'
0x18007671a  jmp     loc_180076B5D
0x18007671f  lea     r8, [rdi+20h]
0x180076723  mov     rcx, rsi
0x180076726  lea     rdx, aPackagerequire; "@PackageRequiresRegistration"
0x18007672d  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x180076732  mov     ebx, eax
0x180076734  test    eax, eax
0x180076736  jns     loc_1800767C7
0x18007673c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076743  test    rcx, rcx
0x180076746  jnz     short loc_180076789
0x180076748  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007674e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076755  mov     rcx, rax
0x180076758  test    rax, rax
0x18007675b  jz      short loc_18007677B
0x18007675d  mov     rax, [rax]
0x180076760  mov     edx, 7F0h
0x180076765  mov     rax, [rax+8]
0x180076769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007676e  test    eax, eax
0x180076770  jz      short loc_18007677B
0x180076772  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076779  jmp     short loc_180076789
0x18007677b  lea     rcx, qword_1800D6F70; this
0x180076782  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076789  cmp     [rcx+8], bpl
0x18007678d  jz      short loc_1800767B0
0x18007678f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076794  cmp     [rax+7CCh], ebx
0x18007679a  jz      short loc_1800767B0
0x18007679c  mov     r9d, ebx; int
0x18007679f  mov     r8d, 3A1h; int
0x1800767a5  mov     rdx, r15; char *
0x1800767a8  mov     rcx, rax; this
0x1800767ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800767b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800767b7  jb      loc_180076B7B
0x1800767bd  mov     edx, 75h ; 'u'
0x1800767c2  jmp     loc_180076B5D
0x1800767c7  mov     rax, [r14]
0x1800767ca  lea     rdx, aAppservicename; "@AppServiceName"
0x1800767d1  mov     r9d, 0Fh; unsigned int
0x1800767d7  mov     [rsp+88h+var_38], rbp
0x1800767dc  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x1800767e1  mov     rbx, [rax+40h]
0x1800767e5  lea     r8d, [r9+1]; unsigned int
0x1800767e9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800767ee  mov     rdx, [rsp+88h+var_38]
0x1800767f3  lea     r8, [rsp+88h+var_58]
0x1800767f8  mov     rcx, r14
0x1800767fb  mov     rax, rbx
0x1800767fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076803  mov     ebx, eax
0x180076805  test    eax, eax
0x180076807  jns     loc_18007689D
0x18007680d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076814  mov     [rsp+88h+var_38], rbp
0x180076819  test    rcx, rcx
0x18007681c  jnz     short loc_18007685F
0x18007681e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076824  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007682b  mov     rcx, rax
0x18007682e  test    rax, rax
0x180076831  jz      short loc_180076851
0x180076833  mov     rax, [rax]
0x180076836  mov     edx, 7F0h
0x18007683b  mov     rax, [rax+8]
0x18007683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076844  test    eax, eax
0x180076846  jz      short loc_180076851
0x180076848  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007684f  jmp     short loc_18007685F
0x180076851  lea     rcx, qword_1800D6F70; this
0x180076858  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007685f  cmp     [rcx+8], bpl
0x180076863  jz      short loc_180076886
0x180076865  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007686a  cmp     [rax+7CCh], ebx
0x180076870  jz      short loc_180076886
0x180076872  mov     r9d, ebx; int
0x180076875  mov     r8d, 3A3h; int
0x18007687b  mov     rdx, r15; char *
0x18007687e  mov     rcx, rax; this
0x180076881  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076886  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007688d  jb      loc_180076B7B
0x180076893  mov     edx, 76h ; 'v'
0x180076898  jmp     loc_180076B5D
0x18007689d  cmp     [rsp+88h+var_58], bpl
0x1800768a2  jz      loc_18007695F
0x1800768a8  lea     rbx, [rdi+10h]
0x1800768ac  mov     rcx, [rbx]; string
0x1800768af  call    cs:__imp_WindowsDeleteString
0x1800768b5  mov     r8, rbx
0x1800768b8  mov     [rbx], rbp
0x1800768bb  lea     rdx, aAppservicename; "@AppServiceName"
0x1800768c2  mov     rcx, r14
0x1800768c5  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800768ca  mov     ebx, eax
0x1800768cc  test    eax, eax
0x1800768ce  jns     loc_18007695F
0x1800768d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800768db  test    rcx, rcx
0x1800768de  jnz     short loc_180076921
0x1800768e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800768e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800768ed  mov     rcx, rax
0x1800768f0  test    rax, rax
0x1800768f3  jz      short loc_180076913
0x1800768f5  mov     rax, [rax]
0x1800768f8  mov     edx, 7F0h
0x1800768fd  mov     rax, [rax+8]
0x180076901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076906  test    eax, eax
0x180076908  jz      short loc_180076913
0x18007690a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076911  jmp     short loc_180076921
0x180076913  lea     rcx, qword_1800D6F70; this
0x18007691a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180076921  cmp     [rcx+8], bpl
0x180076925  jz      short loc_180076948
0x180076927  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007692c  cmp     [rax+7CCh], ebx
0x180076932  jz      short loc_180076948
0x180076934  mov     r9d, ebx; int
0x180076937  mov     r8d, 3A7h; int
0x18007693d  mov     rdx, r15; char *
0x180076940  mov     rcx, rax; this
0x180076943  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076948  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007694f  jb      loc_180076B7B
0x180076955  mov     edx, 77h ; 'w'
0x18007695a  jmp     loc_180076B5D
0x18007695f  lea     rbx, [rdi+18h]
0x180076963  mov     rcx, [rbx]; string
0x180076966  call    cs:__imp_WindowsDeleteString
0x18007696c  mov     r8, rbx
0x18007696f  mov     [rbx], rbp
0x180076972  lea     rdx, aDisplayname; "@DisplayName"
0x180076979  mov     rcx, r14
0x18007697c  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180076981  mov     ebx, eax
0x180076983  test    eax, eax
0x180076985  jns     loc_180076A16
0x18007698b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076992  test    rcx, rcx
0x180076995  jnz     short loc_1800769D8
0x180076997  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007699d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800769a4  mov     rcx, rax
0x1800769a7  test    rax, rax
0x1800769aa  jz      short loc_1800769CA
0x1800769ac  mov     rax, [rax]
0x1800769af  mov     edx, 7F0h
0x1800769b4  mov     rax, [rax+8]
0x1800769b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800769bd  test    eax, eax
0x1800769bf  jz      short loc_1800769CA
0x1800769c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800769c8  jmp     short loc_1800769D8
0x1800769ca  lea     rcx, qword_1800D6F70; this
0x1800769d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800769d8  cmp     [rcx+8], bpl
0x1800769dc  jz      short loc_1800769FF
0x1800769de  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800769e3  cmp     [rax+7CCh], ebx
0x1800769e9  jz      short loc_1800769FF
0x1800769eb  mov     r9d, ebx; int
0x1800769ee  mov     r8d, 3AAh; int
0x1800769f4  mov     rdx, r15; char *
0x1800769f7  mov     rcx, rax; this
0x1800769fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800769ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076a06  jb      loc_180076B7B
0x180076a0c  mov     edx, 78h ; 'x'
0x180076a11  jmp     loc_180076B5D
0x180076a16  lea     r8, [rdi+21h]
0x180076a1a  mov     rcx, rsi
0x180076a1d  lea     rdx, aInprocessmedia; "inProcessMediaExtension"
0x180076a24  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x180076a29  mov     ebx, eax
0x180076a2b  test    eax, eax
0x180076a2d  jns     loc_180076ABE
0x180076a33  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076a3a  test    rcx, rcx
0x180076a3d  jnz     short loc_180076A80
0x180076a3f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076a45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076a4c  mov     rcx, rax
0x180076a4f  test    rax, rax
0x180076a52  jz      short loc_180076A72
0x180076a54  mov     rax, [rax]
0x180076a57  mov     edx, 7F0h
0x180076a5c  mov     rax, [rax+8]
0x180076a60  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
