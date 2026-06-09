# CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)

- ea: `0x180079a58`
- end: `0x18007a0dd`
- name: `?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z`
- size: `1669`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007a0e4`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18003dea8`
- `0x1800744d8`
- `0x1800782dc`
- `0x180079a58`
- `0x18007ab98`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079e82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079e82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079adb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079b9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079c4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079d28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079eb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079f67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a015`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079adb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079b9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079c4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079d28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079eb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079f67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007a015`

## string_xrefs

- `0x180079a7a`: `CreateExtensionInfoFromMediaExtensionMap`
- `0x180079ff3`: `webPlatformMediaExtension`
- `0x180079f45`: `inProcessMediaExtension`
- `0x180079cd4`: `@AppServiceName`
- `0x180079dd1`: `@AppServiceName`

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
                v37 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                      v55 = &qword_1800DBF70;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v49 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v43 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v31 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v23 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v17 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v10 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180079a58  mov     [rsp+arg_18], rbx
0x180079a5d  push    rbp
0x180079a5e  push    rsi
0x180079a5f  push    rdi
0x180079a60  push    r14
0x180079a62  push    r15
0x180079a64  sub     rsp, 60h
0x180079a68  mov     rax, cs:__security_cookie
0x180079a6f  xor     rax, rsp
0x180079a72  mov     [rsp+88h+var_30], rax
0x180079a77  mov     rdi, r8
0x180079a7a  lea     r15, aCreateextensio_0; "CreateExtensionInfoFromMediaExtensionMa"...
0x180079a81  mov     r14, rdx
0x180079a84  mov     rsi, rcx
0x180079a87  xor     ebp, ebp
0x180079a89  lea     rcx, [rsp+88h+var_57]; this
0x180079a8e  mov     rdx, r15; char *
0x180079a91  mov     [rsp+88h+var_58], bpl
0x180079a96  mov     r8d, 39Fh; int
0x180079a9c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180079aa1  mov     rcx, [rdi]; string
0x180079aa4  call    cs:__imp_WindowsDeleteString
0x180079aab  nop     dword ptr [rax+rax+00h]
0x180079ab0  mov     r8, rdi
0x180079ab3  mov     [rdi], rbp
0x180079ab6  lea     rdx, aPackagefamilyn; "@PackageFamilyName"
0x180079abd  mov     rcx, rsi
0x180079ac0  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180079ac5  mov     ebx, eax
0x180079ac7  test    eax, eax
0x180079ac9  jns     loc_180079B60
0x180079acf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079ad6  test    rcx, rcx
0x180079ad9  jnz     short loc_180079B22
0x180079adb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079ae2  nop     dword ptr [rax+rax+00h]
0x180079ae7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079aee  mov     rcx, rax
0x180079af1  test    rax, rax
0x180079af4  jz      short loc_180079B14
0x180079af6  mov     rax, [rax]
0x180079af9  mov     edx, 7F0h
0x180079afe  mov     rax, [rax+8]
0x180079b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079b07  test    eax, eax
0x180079b09  jz      short loc_180079B14
0x180079b0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079b12  jmp     short loc_180079B22
0x180079b14  lea     rcx, qword_1800DBF70; this
0x180079b1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079b22  cmp     [rcx+8], bpl
0x180079b26  jz      short loc_180079B49
0x180079b28  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180079b2d  cmp     [rax+7CCh], ebx
0x180079b33  jz      short loc_180079B49
0x180079b35  mov     r9d, ebx; int
0x180079b38  mov     r8d, 39Fh; int
0x180079b3e  mov     rdx, r15; char *
0x180079b41  mov     rcx, rax; this
0x180079b44  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079b49  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079b50  jb      loc_18007A0AF
0x180079b56  mov     edx, 73h ; 's'
0x180079b5b  jmp     loc_18007A091
0x180079b60  lea     rbx, [rdi+8]
0x180079b64  mov     rcx, [rbx]; string
0x180079b67  call    cs:__imp_WindowsDeleteString
0x180079b6e  nop     dword ptr [rax+rax+00h]
0x180079b73  mov     r8, rbx
0x180079b76  mov     [rbx], rbp
0x180079b79  lea     rdx, aPackagefullnam; "@PackageFullName"
0x180079b80  mov     rcx, rsi
0x180079b83  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180079b88  mov     ebx, eax
0x180079b8a  test    eax, eax
0x180079b8c  jns     loc_180079C23
0x180079b92  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079b99  test    rcx, rcx
0x180079b9c  jnz     short loc_180079BE5
0x180079b9e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079ba5  nop     dword ptr [rax+rax+00h]
0x180079baa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079bb1  mov     rcx, rax
0x180079bb4  test    rax, rax
0x180079bb7  jz      short loc_180079BD7
0x180079bb9  mov     rax, [rax]
0x180079bbc  mov     edx, 7F0h
0x180079bc1  mov     rax, [rax+8]
0x180079bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079bca  test    eax, eax
0x180079bcc  jz      short loc_180079BD7
0x180079bce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079bd5  jmp     short loc_180079BE5
0x180079bd7  lea     rcx, qword_1800DBF70; this
0x180079bde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079be5  cmp     [rcx+8], bpl
0x180079be9  jz      short loc_180079C0C
0x180079beb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180079bf0  cmp     [rax+7CCh], ebx
0x180079bf6  jz      short loc_180079C0C
0x180079bf8  mov     r9d, ebx; int
0x180079bfb  mov     r8d, 3A0h; int
0x180079c01  mov     rdx, r15; char *
0x180079c04  mov     rcx, rax; this
0x180079c07  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079c0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079c13  jb      loc_18007A0AF
0x180079c19  mov     edx, 74h ; 't'
0x180079c1e  jmp     loc_18007A091
0x180079c23  lea     r8, [rdi+20h]
0x180079c27  mov     rcx, rsi
0x180079c2a  lea     rdx, aPackagerequire; "@PackageRequiresRegistration"
0x180079c31  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x180079c36  mov     ebx, eax
0x180079c38  test    eax, eax
0x180079c3a  jns     loc_180079CD1
0x180079c40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079c47  test    rcx, rcx
0x180079c4a  jnz     short loc_180079C93
0x180079c4c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079c53  nop     dword ptr [rax+rax+00h]
0x180079c58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079c5f  mov     rcx, rax
0x180079c62  test    rax, rax
0x180079c65  jz      short loc_180079C85
0x180079c67  mov     rax, [rax]
0x180079c6a  mov     edx, 7F0h
0x180079c6f  mov     rax, [rax+8]
0x180079c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c78  test    eax, eax
0x180079c7a  jz      short loc_180079C85
0x180079c7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079c83  jmp     short loc_180079C93
0x180079c85  lea     rcx, qword_1800DBF70; this
0x180079c8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079c93  cmp     [rcx+8], bpl
0x180079c97  jz      short loc_180079CBA
0x180079c99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180079c9e  cmp     [rax+7CCh], ebx
0x180079ca4  jz      short loc_180079CBA
0x180079ca6  mov     r9d, ebx; int
0x180079ca9  mov     r8d, 3A1h; int
0x180079caf  mov     rdx, r15; char *
0x180079cb2  mov     rcx, rax; this
0x180079cb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079cba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079cc1  jb      loc_18007A0AF
0x180079cc7  mov     edx, 75h ; 'u'
0x180079ccc  jmp     loc_18007A091
0x180079cd1  mov     rax, [r14]
0x180079cd4  lea     rdx, aAppservicename; "@AppServiceName"
0x180079cdb  mov     r9d, 0Fh; unsigned int
0x180079ce1  mov     [rsp+88h+var_38], rbp
0x180079ce6  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x180079ceb  mov     rbx, [rax+40h]
0x180079cef  lea     r8d, [r9+1]; unsigned int
0x180079cf3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180079cf8  mov     rdx, [rsp+88h+var_38]
0x180079cfd  lea     r8, [rsp+88h+var_58]
0x180079d02  mov     rcx, r14
0x180079d05  mov     rax, rbx
0x180079d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d0d  mov     ebx, eax
0x180079d0f  test    eax, eax
0x180079d11  jns     loc_180079DAD
0x180079d17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079d1e  mov     [rsp+88h+var_38], rbp
0x180079d23  test    rcx, rcx
0x180079d26  jnz     short loc_180079D6F
0x180079d28  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079d2f  nop     dword ptr [rax+rax+00h]
0x180079d34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079d3b  mov     rcx, rax
0x180079d3e  test    rax, rax
0x180079d41  jz      short loc_180079D61
0x180079d43  mov     rax, [rax]
0x180079d46  mov     edx, 7F0h
0x180079d4b  mov     rax, [rax+8]
0x180079d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079d54  test    eax, eax
0x180079d56  jz      short loc_180079D61
0x180079d58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079d5f  jmp     short loc_180079D6F
0x180079d61  lea     rcx, qword_1800DBF70; this
0x180079d68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079d6f  cmp     [rcx+8], bpl
0x180079d73  jz      short loc_180079D96
0x180079d75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180079d7a  cmp     [rax+7CCh], ebx
0x180079d80  jz      short loc_180079D96
0x180079d82  mov     r9d, ebx; int
0x180079d85  mov     r8d, 3A3h; int
0x180079d8b  mov     rdx, r15; char *
0x180079d8e  mov     rcx, rax; this
0x180079d91  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079d96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079d9d  jb      loc_18007A0AF
0x180079da3  mov     edx, 76h ; 'v'
0x180079da8  jmp     loc_18007A091
0x180079dad  cmp     [rsp+88h+var_58], bpl
0x180079db2  jz      loc_180079E7B
0x180079db8  lea     rbx, [rdi+10h]
0x180079dbc  mov     rcx, [rbx]; string
0x180079dbf  call    cs:__imp_WindowsDeleteString
0x180079dc6  nop     dword ptr [rax+rax+00h]
0x180079dcb  mov     r8, rbx
0x180079dce  mov     [rbx], rbp
0x180079dd1  lea     rdx, aAppservicename; "@AppServiceName"
0x180079dd8  mov     rcx, r14
0x180079ddb  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180079de0  mov     ebx, eax
0x180079de2  test    eax, eax
0x180079de4  jns     loc_180079E7B
0x180079dea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079df1  test    rcx, rcx
0x180079df4  jnz     short loc_180079E3D
0x180079df6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079dfd  nop     dword ptr [rax+rax+00h]
0x180079e02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e09  mov     rcx, rax
0x180079e0c  test    rax, rax
0x180079e0f  jz      short loc_180079E2F
0x180079e11  mov     rax, [rax]
0x180079e14  mov     edx, 7F0h
0x180079e19  mov     rax, [rax+8]
0x180079e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079e22  test    eax, eax
0x180079e24  jz      short loc_180079E2F
0x180079e26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e2d  jmp     short loc_180079E3D
0x180079e2f  lea     rcx, qword_1800DBF70; this
0x180079e36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079e3d  cmp     [rcx+8], bpl
0x180079e41  jz      short loc_180079E64
0x180079e43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180079e48  cmp     [rax+7CCh], ebx
0x180079e4e  jz      short loc_180079E64
0x180079e50  mov     r9d, ebx; int
0x180079e53  mov     r8d, 3A7h; int
0x180079e59  mov     rdx, r15; char *
0x180079e5c  mov     rcx, rax; this
0x180079e5f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079e64  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079e6b  jb      loc_18007A0AF
0x180079e71  mov     edx, 77h ; 'w'
0x180079e76  jmp     loc_18007A091
0x180079e7b  lea     rbx, [rdi+18h]
0x180079e7f  mov     rcx, [rbx]; string
0x180079e82  call    cs:__imp_WindowsDeleteString
0x180079e89  nop     dword ptr [rax+rax+00h]
0x180079e8e  mov     r8, rbx
0x180079e91  mov     [rbx], rbp
0x180079e94  lea     rdx, aDisplayname; "@DisplayName"
0x180079e9b  mov     rcx, r14
0x180079e9e  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180079ea3  mov     ebx, eax
0x180079ea5  test    eax, eax
0x180079ea7  jns     loc_180079F3E
0x180079ead  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079eb4  test    rcx, rcx
0x180079eb7  jnz     short loc_180079F00
0x180079eb9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180079ec0  nop     dword ptr [rax+rax+00h]
0x180079ec5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180079ecc  mov     rcx, rax
0x180079ecf  test    rax, rax
0x180079ed2  jz      short loc_180079EF2
0x180079ed4  mov     rax, [rax]
0x180079ed7  mov     edx, 7F0h
0x180079edc  mov     rax, [rax+8]
0x180079ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ee5  test    eax, eax
0x180079ee7  jz      short loc_180079EF2
0x180079ee9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079ef0  jmp     short loc_180079F00
0x180079ef2  lea     rcx, qword_1800DBF70; this
0x180079ef9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079f00  cmp     [rcx+8], bpl
0x180079f04  jz      short loc_180079F27
0x180079f06  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180079f0b  cmp     [rax+7CCh], ebx
0x180079f11  jz      short loc_180079F27
0x180079f13  mov     r9d, ebx; int
0x180079f16  mov     r8d, 3AAh; int
0x180079f1c  mov     rdx, r15; char *
0x180079f1f  mov     rcx, rax; this
0x180079f22  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079f27  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079f2e  jb      loc_18007A0AF
0x180079f34  mov     edx, 78h ; 'x'
0x180079f39  jmp     loc_18007A091
0x180079f3e  lea     r8, [rdi+21h]
0x180079f42  mov     rcx, rsi
0x180079f45  lea     rdx, aInprocessmedia; "inProcessMediaExtension"
0x180079f4c  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x180079f51  mov     ebx, eax
0x180079f53  test    eax, eax
0x180079f55  jns     loc_180079FEC
0x180079f5b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079f62  test    rcx, rcx
  ... truncated ...
```
