# CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)

- ea: `0x1800180fc`
- end: `0x1800186ff`
- name: `?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z`
- size: `1539`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800347d0`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x1800180fc`
- `0x180018a4c`
- `0x180025b08`
- `0x18003639c`
- `0x1800390a4`
- `0x180054140`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800181c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800184bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800181c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800184bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800181f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001829f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018375`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018437`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800184ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018596`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001863e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800181f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001829f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018375`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018437`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800184ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180018596`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001863e`

## string_xrefs

- `0x18001811e`: `CreateExtensionInfoFromMediaExtensionMap`
- `0x18001861c`: `webPlatformMediaExtension`
- `0x180018321`: `@AppServiceName`
- `0x180018412`: `@AppServiceName`
- `0x180018574`: `inProcessMediaExtension`

## pseudocode

```c
__int64 __fastcall CreateExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 *a2, HSTRING *a3)
{
  int StringFromMap; // ebx
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rax
  __int64 (__fastcall *v17)(__int64 *, __int64, char *); // rbx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  char v34; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v35[7]; // [rsp+31h] [rbp-57h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-50h] BYREF
  __int64 v37; // [rsp+50h] [rbp-38h]

  v34 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v35, "CreateExtensionInfoFromMediaExtensionMap", 927);
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
        v16 = *a2;
        v37 = 0;
        v17 = *(__int64 (__fastcall **)(__int64 *, __int64, char *))(v16 + 64);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@AppServiceName", 0x10u, 0xFu);
        StringFromMap = v17(a2, v37, &v34);
        if ( StringFromMap >= 0 )
        {
          if ( v34
            && (WindowsDeleteString(a3[2]),
                a3[2] = 0,
                StringFromMap = CreateStringFromMap(a2, L"@AppServiceName", a3 + 2),
                StringFromMap < 0) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v22;
              if ( v22
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
              {
                v21 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v21 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v21 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != StringFromMap )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CreateExtensionInfoFromMediaExtensionMap",
                  935,
                  StringFromMap);
            }
            if ( g_wppLevels )
            {
              v9 = 119;
              goto LABEL_87;
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
                  v30 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                    CallStackTracing::s_wpInstance = v31;
                    if ( v31
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                    {
                      v30 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v30 = &qword_180153440;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                    }
                  }
                  if ( *((_BYTE *)v30 + 8) )
                  {
                    v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                    if ( *((_DWORD *)v32 + 499) != StringFromMap )
                      CallStackContext::TraceFailure(
                        v32,
                        "CreateExtensionInfoFromMediaExtensionMap",
                        941,
                        StringFromMap);
                  }
                  if ( g_wppLevels )
                  {
                    v9 = 122;
                    goto LABEL_87;
                  }
                }
              }
              else
              {
                v27 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v28;
                  if ( v28
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                  {
                    v27 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v27 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v27 + 8) )
                {
                  v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
                  if ( *((_DWORD *)v29 + 499) != StringFromMap )
                    CallStackContext::TraceFailure(v29, "CreateExtensionInfoFromMediaExtensionMap", 940, StringFromMap);
                }
                if ( g_wppLevels )
                {
                  v9 = 121;
                  goto LABEL_87;
                }
              }
            }
            else
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v25;
                if ( v25
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
                {
                  v24 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v24 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v24 + 8) )
              {
                v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
                if ( *((_DWORD *)v26 + 499) != StringFromMap )
                  CallStackContext::TraceFailure(v26, "CreateExtensionInfoFromMediaExtensionMap", 938, StringFromMap);
              }
              if ( g_wppLevels )
              {
                v9 = 120;
                goto LABEL_87;
              }
            }
          }
        }
        else
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
          v37 = 0;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v18 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
            if ( *((_DWORD *)v20 + 499) != StringFromMap )
              CallStackContext::TraceFailure(v20, "CreateExtensionInfoFromMediaExtensionMap", 931, StringFromMap);
          }
          if ( g_wppLevels )
          {
            v9 = 118;
            goto LABEL_87;
          }
        }
      }
      else
      {
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
            CallStackContext::TraceFailure(v15, "CreateExtensionInfoFromMediaExtensionMap", 929, StringFromMap);
        }
        if ( g_wppLevels )
        {
          v9 = 117;
          goto LABEL_87;
        }
      }
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != StringFromMap )
          CallStackContext::TraceFailure(v12, "CreateExtensionInfoFromMediaExtensionMap", 928, StringFromMap);
      }
      if ( g_wppLevels )
      {
        v9 = 116;
        goto LABEL_87;
      }
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)v8 + 499) != StringFromMap )
        CallStackContext::TraceFailure(v8, "CreateExtensionInfoFromMediaExtensionMap", 927, StringFromMap);
    }
    if ( g_wppLevels )
    {
      v9 = 115;
LABEL_87:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
        0,
        StringFromMap);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
  return (unsigned int)StringFromMap;
}

```

## disassembly

```asm
0x1800180fc  mov     [rsp+arg_18], rbx
0x180018101  push    rbp
0x180018102  push    rsi
0x180018103  push    rdi
0x180018104  push    r14
0x180018106  push    r15
0x180018108  sub     rsp, 60h
0x18001810c  mov     rax, cs:__security_cookie
0x180018113  xor     rax, rsp
0x180018116  mov     [rsp+88h+var_30], rax
0x18001811b  mov     rdi, r8
0x18001811e  lea     r15, aCreateextensio_0; "CreateExtensionInfoFromMediaExtensionMa"...
0x180018125  mov     r14, rdx
0x180018128  mov     rsi, rcx
0x18001812b  xor     ebp, ebp
0x18001812d  lea     rcx, [rsp+88h+var_57]; this
0x180018132  mov     rdx, r15; char *
0x180018135  mov     [rsp+88h+var_58], bpl
0x18001813a  mov     r8d, 39Fh; int
0x180018140  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180018145  mov     rcx, [rdi]; string
0x180018148  call    cs:__imp_WindowsDeleteString
0x18001814e  mov     r8, rdi
0x180018151  mov     [rdi], rbp
0x180018154  lea     rdx, aPackagefamilyn; "@PackageFamilyName"
0x18001815b  mov     rcx, rsi
0x18001815e  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180018163  mov     ebx, eax
0x180018165  test    eax, eax
0x180018167  jns     short loc_1800181BF
0x180018169  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018170  test    rcx, rcx
0x180018173  jnz     short loc_180018181
0x180018175  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001817a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180018181  cmp     [rcx+8], bpl
0x180018185  jz      short loc_1800181A8
0x180018187  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001818c  cmp     [rax+7CCh], ebx
0x180018192  jz      short loc_1800181A8
0x180018194  mov     r9d, ebx; int
0x180018197  mov     r8d, 39Fh; int
0x18001819d  mov     rdx, r15; char *
0x1800181a0  mov     rcx, rax; this
0x1800181a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800181a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800181af  jb      loc_1800186D2
0x1800181b5  mov     edx, 73h ; 's'
0x1800181ba  jmp     loc_1800186B4
0x1800181bf  lea     rbx, [rdi+8]
0x1800181c3  mov     rcx, [rbx]; string
0x1800181c6  call    cs:__imp_WindowsDeleteString
0x1800181cc  mov     r8, rbx
0x1800181cf  mov     [rbx], rbp
0x1800181d2  lea     rdx, aPackagefullnam; "@PackageFullName"
0x1800181d9  mov     rcx, rsi
0x1800181dc  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800181e1  mov     ebx, eax
0x1800181e3  test    eax, eax
0x1800181e5  jns     loc_180018276
0x1800181eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800181f2  test    rcx, rcx
0x1800181f5  jnz     short loc_180018238
0x1800181f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800181fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018204  mov     rcx, rax
0x180018207  test    rax, rax
0x18001820a  jz      short loc_18001822A
0x18001820c  mov     rax, [rax]
0x18001820f  mov     edx, 7F0h
0x180018214  mov     rax, [rax+8]
0x180018218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001821d  test    eax, eax
0x18001821f  jz      short loc_18001822A
0x180018221  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018228  jmp     short loc_180018238
0x18001822a  lea     rcx, qword_180153440; this
0x180018231  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018238  cmp     [rcx+8], bpl
0x18001823c  jz      short loc_18001825F
0x18001823e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018243  cmp     [rax+7CCh], ebx
0x180018249  jz      short loc_18001825F
0x18001824b  mov     r9d, ebx; int
0x18001824e  mov     r8d, 3A0h; int
0x180018254  mov     rdx, r15; char *
0x180018257  mov     rcx, rax; this
0x18001825a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001825f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180018266  jb      loc_1800186D2
0x18001826c  mov     edx, 74h ; 't'
0x180018271  jmp     loc_1800186B4
0x180018276  lea     r8, [rdi+20h]
0x18001827a  mov     rcx, rsi
0x18001827d  lea     rdx, aPackagerequire; "@PackageRequiresRegistration"
0x180018284  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x180018289  mov     ebx, eax
0x18001828b  test    eax, eax
0x18001828d  jns     loc_18001831E
0x180018293  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001829a  test    rcx, rcx
0x18001829d  jnz     short loc_1800182E0
0x18001829f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800182a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800182ac  mov     rcx, rax
0x1800182af  test    rax, rax
0x1800182b2  jz      short loc_1800182D2
0x1800182b4  mov     rax, [rax]
0x1800182b7  mov     edx, 7F0h
0x1800182bc  mov     rax, [rax+8]
0x1800182c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c5  test    eax, eax
0x1800182c7  jz      short loc_1800182D2
0x1800182c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800182d0  jmp     short loc_1800182E0
0x1800182d2  lea     rcx, qword_180153440; this
0x1800182d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800182e0  cmp     [rcx+8], bpl
0x1800182e4  jz      short loc_180018307
0x1800182e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800182eb  cmp     [rax+7CCh], ebx
0x1800182f1  jz      short loc_180018307
0x1800182f3  mov     r9d, ebx; int
0x1800182f6  mov     r8d, 3A1h; int
0x1800182fc  mov     rdx, r15; char *
0x1800182ff  mov     rcx, rax; this
0x180018302  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018307  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001830e  jb      loc_1800186D2
0x180018314  mov     edx, 75h ; 'u'
0x180018319  jmp     loc_1800186B4
0x18001831e  mov     rax, [r14]
0x180018321  lea     rdx, aAppservicename; "@AppServiceName"
0x180018328  mov     r9d, 0Fh; unsigned int
0x18001832e  mov     [rsp+88h+var_38], rbp
0x180018333  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x180018338  mov     rbx, [rax+40h]
0x18001833c  lea     r8d, [r9+1]; unsigned int
0x180018340  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180018345  mov     rdx, [rsp+88h+var_38]
0x18001834a  lea     r8, [rsp+88h+var_58]
0x18001834f  mov     rcx, r14
0x180018352  mov     rax, rbx
0x180018355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001835a  mov     ebx, eax
0x18001835c  test    eax, eax
0x18001835e  jns     loc_1800183F4
0x180018364  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001836b  mov     [rsp+88h+var_38], rbp
0x180018370  test    rcx, rcx
0x180018373  jnz     short loc_1800183B6
0x180018375  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001837b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018382  mov     rcx, rax
0x180018385  test    rax, rax
0x180018388  jz      short loc_1800183A8
0x18001838a  mov     rax, [rax]
0x18001838d  mov     edx, 7F0h
0x180018392  mov     rax, [rax+8]
0x180018396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001839b  test    eax, eax
0x18001839d  jz      short loc_1800183A8
0x18001839f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800183a6  jmp     short loc_1800183B6
0x1800183a8  lea     rcx, qword_180153440; this
0x1800183af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800183b6  cmp     [rcx+8], bpl
0x1800183ba  jz      short loc_1800183DD
0x1800183bc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800183c1  cmp     [rax+7CCh], ebx
0x1800183c7  jz      short loc_1800183DD
0x1800183c9  mov     r9d, ebx; int
0x1800183cc  mov     r8d, 3A3h; int
0x1800183d2  mov     rdx, r15; char *
0x1800183d5  mov     rcx, rax; this
0x1800183d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800183dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800183e4  jb      loc_1800186D2
0x1800183ea  mov     edx, 76h ; 'v'
0x1800183ef  jmp     loc_1800186B4
0x1800183f4  cmp     [rsp+88h+var_58], bpl
0x1800183f9  jz      loc_1800184B6
0x1800183ff  lea     rbx, [rdi+10h]
0x180018403  mov     rcx, [rbx]; string
0x180018406  call    cs:__imp_WindowsDeleteString
0x18001840c  mov     r8, rbx
0x18001840f  mov     [rbx], rbp
0x180018412  lea     rdx, aAppservicename; "@AppServiceName"
0x180018419  mov     rcx, r14
0x18001841c  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x180018421  mov     ebx, eax
0x180018423  test    eax, eax
0x180018425  jns     loc_1800184B6
0x18001842b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018432  test    rcx, rcx
0x180018435  jnz     short loc_180018478
0x180018437  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001843d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180018444  mov     rcx, rax
0x180018447  test    rax, rax
0x18001844a  jz      short loc_18001846A
0x18001844c  mov     rax, [rax]
0x18001844f  mov     edx, 7F0h
0x180018454  mov     rax, [rax+8]
0x180018458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001845d  test    eax, eax
0x18001845f  jz      short loc_18001846A
0x180018461  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018468  jmp     short loc_180018478
0x18001846a  lea     rcx, qword_180153440; this
0x180018471  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180018478  cmp     [rcx+8], bpl
0x18001847c  jz      short loc_18001849F
0x18001847e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180018483  cmp     [rax+7CCh], ebx
0x180018489  jz      short loc_18001849F
0x18001848b  mov     r9d, ebx; int
0x18001848e  mov     r8d, 3A7h; int
0x180018494  mov     rdx, r15; char *
0x180018497  mov     rcx, rax; this
0x18001849a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001849f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800184a6  jb      loc_1800186D2
0x1800184ac  mov     edx, 77h ; 'w'
0x1800184b1  jmp     loc_1800186B4
0x1800184b6  lea     rbx, [rdi+18h]
0x1800184ba  mov     rcx, [rbx]; string
0x1800184bd  call    cs:__imp_WindowsDeleteString
0x1800184c3  mov     r8, rbx
0x1800184c6  mov     [rbx], rbp
0x1800184c9  lea     rdx, aDisplayname; "@DisplayName"
0x1800184d0  mov     rcx, r14
0x1800184d3  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800184d8  mov     ebx, eax
0x1800184da  test    eax, eax
0x1800184dc  jns     loc_18001856D
0x1800184e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800184e9  test    rcx, rcx
0x1800184ec  jnz     short loc_18001852F
0x1800184ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800184f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800184fb  mov     rcx, rax
0x1800184fe  test    rax, rax
0x180018501  jz      short loc_180018521
0x180018503  mov     rax, [rax]
0x180018506  mov     edx, 7F0h
0x18001850b  mov     rax, [rax+8]
0x18001850f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018514  test    eax, eax
0x180018516  jz      short loc_180018521
0x180018518  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001851f  jmp     short loc_18001852F
0x180018521  lea     rcx, qword_180153440; this
0x180018528  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001852f  cmp     [rcx+8], bpl
0x180018533  jz      short loc_180018556
0x180018535  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001853a  cmp     [rax+7CCh], ebx
0x180018540  jz      short loc_180018556
0x180018542  mov     r9d, ebx; int
0x180018545  mov     r8d, 3AAh; int
0x18001854b  mov     rdx, r15; char *
0x18001854e  mov     rcx, rax; this
0x180018551  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180018556  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001855d  jb      loc_1800186D2
0x180018563  mov     edx, 78h ; 'x'
0x180018568  jmp     loc_1800186B4
0x18001856d  lea     r8, [rdi+21h]
0x180018571  mov     rcx, rsi
0x180018574  lea     rdx, aInprocessmedia; "inProcessMediaExtension"
0x18001857b  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x180018580  mov     ebx, eax
0x180018582  test    eax, eax
0x180018584  jns     loc_180018615
0x18001858a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180018591  test    rcx, rcx
0x180018594  jnz     short loc_1800185D7
0x180018596  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001859c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800185a3  mov     rcx, rax
0x1800185a6  test    rax, rax
0x1800185a9  jz      short loc_1800185C9
0x1800185ab  mov     rax, [rax]
0x1800185ae  mov     edx, 7F0h
0x1800185b3  mov     rax, [rax+8]
0x1800185b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185bc  test    eax, eax
0x1800185be  jz      short loc_1800185C9
0x1800185c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800185c7  jmp     short loc_1800185D7
0x1800185c9  lea     rcx, qword_180153440; this
0x1800185d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800185d7  cmp     [rcx+8], bpl
0x1800185db  jz      short loc_1800185FE
0x1800185dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800185e2  cmp     [rax+7CCh], ebx
0x1800185e8  jz      short loc_1800185FE
0x1800185ea  mov     r9d, ebx; int
0x1800185ed  mov     r8d, 3ACh; int
  ... truncated ...
```
