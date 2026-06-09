# CreateExtensionInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ExtensionInfo &)

- ea: `0x18001fda0`
- end: `0x180020452`
- name: `?CreateExtensionInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@0AEAUExtensionInfo@@@Z`
- size: `1714`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x1800aa7b0`

## callees

- `0x18001fda0`
- `0x180020b80`
- `0x180020e54`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002044b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002044b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fdec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ff08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800200ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fdec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ff08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800200ae`

## string_xrefs

- `0x18001fdc2`: `CreateExtensionInfoFromMediaExtensionMap`
- `0x18001fec1`: `@AppServiceName`
- `0x1800200ba`: `@AppServiceName`
- `0x18001ff34`: `inProcessMediaExtension`
- `0x18001ff51`: `webPlatformMediaExtension`

## pseudocode

```c
__int64 __fastcall CreateExtensionInfoFromMediaExtensionMap(__int64 a1, __int64 *a2, HSTRING *a3)
{
  int StringFromMap; // ebx
  CallStackTracing *v7; // rcx
  __int64 v9; // rbx
  HRESULT v10; // eax
  CallStackTracing *v11; // rcx
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v16; // rcx
  struct CallStackContext *v17; // rax
  CallStackTracing *v18; // rcx
  struct CallStackContext *v19; // rax
  struct CallStackContext *v20; // rax
  struct CallStackContext *v21; // rax
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  struct CallStackContext *v26; // rax
  char v27; // [rsp+30h] [rbp-58h] BYREF
  CallStackScopeTrace v28; // [rsp+31h] [rbp-57h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-50h] BYREF
  HSTRING string; // [rsp+50h] [rbp-38h] BYREF

  v27 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v28, "CreateExtensionInfoFromMediaExtensionMap", 927);
  WindowsDeleteString(*a3);
  *a3 = 0;
  StringFromMap = CreateStringFromMap(a1, L"@PackageFamilyName", a3);
  if ( StringFromMap < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v7 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v7->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v7);
      if ( ThreadRelativeContext->m_result != StringFromMap )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CreateExtensionInfoFromMediaExtensionMap",
          927,
          StringFromMap);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_5;
    v12 = 115;
LABEL_20:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids,
      0,
      StringFromMap);
    goto LABEL_5;
  }
  WindowsDeleteString(a3[1]);
  a3[1] = 0;
  StringFromMap = CreateStringFromMap(a1, L"@PackageFullName", a3 + 1);
  if ( StringFromMap < 0 )
  {
    v16 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v16 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v16 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v16->m_fEnabled )
    {
      v17 = CallStackTracing::GetThreadRelativeContext(v16);
      if ( v17->m_result != StringFromMap )
        CallStackContext::TraceFailure(v17, "CreateExtensionInfoFromMediaExtensionMap", 928, StringFromMap);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v12 = 116;
      goto LABEL_20;
    }
  }
  else
  {
    StringFromMap = CreateBOOLFromMap(a1, L"@PackageRequiresRegistration", a3 + 4);
    if ( StringFromMap < 0 )
    {
      v18 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v18 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v18->m_fEnabled )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v18);
        if ( v19->m_result != StringFromMap )
          CallStackContext::TraceFailure(v19, "CreateExtensionInfoFromMediaExtensionMap", 929, StringFromMap);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v12 = 117;
        goto LABEL_20;
      }
    }
    else
    {
      v9 = *a2;
      string = 0;
      v10 = WindowsCreateStringReference(L"@AppServiceName", 0xFu, &hstringHeader, &string);
      if ( v10 < 0 )
      {
        RaiseException(v10, 1u, 0, 0);
        JUMPOUT(0x180020451LL);
      }
      StringFromMap = (*(__int64 (__fastcall **)(__int64 *, HSTRING, char *))(v9 + 64))(a2, string, &v27);
      if ( StringFromMap < 0 )
      {
        v13 = CallStackTracing::s_wpInstance;
        string = 0;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v13->m_fEnabled )
        {
          v20 = CallStackTracing::GetThreadRelativeContext(v13);
          if ( v20->m_result != StringFromMap )
            CallStackContext::TraceFailure(v20, "CreateExtensionInfoFromMediaExtensionMap", 931, StringFromMap);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v12 = 118;
          goto LABEL_20;
        }
      }
      else if ( v27
             && (WindowsDeleteString(a3[2]),
                 a3[2] = 0,
                 StringFromMap = CreateStringFromMap(a2, L"@AppServiceName", a3 + 2),
                 StringFromMap < 0) )
      {
        v14 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v14 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v14->m_fEnabled )
        {
          v21 = CallStackTracing::GetThreadRelativeContext(v14);
          if ( v21->m_result != StringFromMap )
            CallStackContext::TraceFailure(v21, "CreateExtensionInfoFromMediaExtensionMap", 935, StringFromMap);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v12 = 119;
          goto LABEL_20;
        }
      }
      else
      {
        WindowsDeleteString(a3[3]);
        a3[3] = 0;
        StringFromMap = CreateStringFromMap(a2, L"@DisplayName", a3 + 3);
        if ( StringFromMap < 0 )
        {
          v22 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v22 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v22->m_fEnabled )
          {
            v23 = CallStackTracing::GetThreadRelativeContext(v22);
            if ( v23->m_result != StringFromMap )
              CallStackContext::TraceFailure(v23, "CreateExtensionInfoFromMediaExtensionMap", 938, StringFromMap);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v12 = 120;
            goto LABEL_20;
          }
        }
        else
        {
          StringFromMap = CreateBOOLFromMap(a1, L"inProcessMediaExtension", (char *)a3 + 33);
          if ( StringFromMap < 0 )
          {
            v24 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v24 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v24->m_fEnabled )
            {
              v25 = CallStackTracing::GetThreadRelativeContext(v24);
              if ( v25->m_result != StringFromMap )
                CallStackContext::TraceFailure(v25, "CreateExtensionInfoFromMediaExtensionMap", 940, StringFromMap);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v12 = 121;
              goto LABEL_20;
            }
          }
          else
          {
            StringFromMap = CreateBOOLFromMap(a1, L"webPlatformMediaExtension", (char *)a3 + 34);
            if ( StringFromMap < 0 )
            {
              v11 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v11 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v11 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v11->m_fEnabled )
              {
                v26 = CallStackTracing::GetThreadRelativeContext(v11);
                if ( v26->m_result != StringFromMap )
                  CallStackContext::TraceFailure(v26, "CreateExtensionInfoFromMediaExtensionMap", 941, StringFromMap);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v12 = 122;
                goto LABEL_20;
              }
            }
          }
        }
      }
    }
  }
LABEL_5:
  CallStackScopeTrace::~CallStackScopeTrace(&v28);
  return (unsigned int)StringFromMap;
}

```

## disassembly

```asm
0x18001fda0  mov     [rsp+arg_18], rbx
0x18001fda5  push    rbp
0x18001fda6  push    rsi
0x18001fda7  push    rdi
0x18001fda8  push    r14
0x18001fdaa  push    r15
0x18001fdac  sub     rsp, 60h
0x18001fdb0  mov     rax, cs:__security_cookie
0x18001fdb7  xor     rax, rsp
0x18001fdba  mov     [rsp+88h+var_30], rax
0x18001fdbf  mov     rdi, r8
0x18001fdc2  lea     r15, aCreateextensio_0; "CreateExtensionInfoFromMediaExtensionMa"...
0x18001fdc9  mov     r14, rdx
0x18001fdcc  mov     rsi, rcx
0x18001fdcf  xor     ebp, ebp
0x18001fdd1  lea     rcx, [rsp+88h+var_57]; this
0x18001fdd6  mov     rdx, r15; char *
0x18001fdd9  mov     [rsp+88h+var_58], bpl
0x18001fdde  mov     r8d, 39Fh; int
0x18001fde4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001fde9  mov     rcx, [rdi]; string
0x18001fdec  call    cs:__imp_WindowsDeleteString
0x18001fdf2  mov     r8, rdi
0x18001fdf5  mov     [rdi], rbp
0x18001fdf8  lea     rdx, aPackagefamilyn; "@PackageFamilyName"
0x18001fdff  mov     rcx, rsi
0x18001fe02  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18001fe07  mov     ebx, eax
0x18001fe09  test    eax, eax
0x18001fe0b  jns     short loc_18001FE61
0x18001fe0d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001fe14  test    rcx, rcx
0x18001fe17  jz      loc_18001FFEE
0x18001fe1d  cmp     [rcx+8], bpl
0x18001fe21  jnz     loc_18002014D
0x18001fe27  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fe2e  jnb     loc_180020435
0x18001fe34  lea     rcx, [rsp+88h+var_57]; this
0x18001fe39  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001fe3e  mov     eax, ebx
0x18001fe40  mov     rcx, [rsp+88h+var_30]
0x18001fe45  xor     rcx, rsp; StackCookie
0x18001fe48  call    __security_check_cookie
0x18001fe4d  mov     rbx, [rsp+88h+arg_18]
0x18001fe55  add     rsp, 60h
0x18001fe59  pop     r15
0x18001fe5b  pop     r14
0x18001fe5d  pop     rdi
0x18001fe5e  pop     rsi
0x18001fe5f  pop     rbp
0x18001fe60  retn
0x18001fe61  lea     rbx, [rdi+8]
0x18001fe65  mov     rcx, [rbx]; string
0x18001fe68  call    cs:__imp_WindowsDeleteString
0x18001fe6e  mov     r8, rbx
0x18001fe71  mov     [rbx], rbp
0x18001fe74  lea     rdx, aPackagefullnam; "@PackageFullName"
0x18001fe7b  mov     rcx, rsi
0x18001fe7e  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18001fe83  mov     ebx, eax
0x18001fe85  test    eax, eax
0x18001fe87  js      loc_180020177
0x18001fe8d  lea     r8, [rdi+20h]
0x18001fe91  mov     rcx, rsi
0x18001fe94  lea     rdx, aPackagerequire; "@PackageRequiresRegistration"
0x18001fe9b  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x18001fea0  mov     ebx, eax
0x18001fea2  test    eax, eax
0x18001fea4  js      loc_180020204
0x18001feaa  mov     rbx, [r14]
0x18001fead  lea     r9, [rsp+88h+string]; string
0x18001feb2  lea     r8, [rsp+88h+hstringHeader]; hstringHeader
0x18001feb7  mov     [rsp+88h+string], rbp
0x18001febc  mov     edx, 0Fh; length
0x18001fec1  lea     rcx, aAppservicename; "@AppServiceName"
0x18001fec8  call    cs:__imp_WindowsCreateStringReference
0x18001fece  test    eax, eax
0x18001fed0  js      loc_18002043F
0x18001fed6  mov     rdx, [rsp+88h+string]
0x18001fedb  lea     r8, [rsp+88h+var_58]
0x18001fee0  mov     rax, [rbx+40h]
0x18001fee4  mov     rcx, r14
0x18001fee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feec  mov     ebx, eax
0x18001feee  test    eax, eax
0x18001fef0  js      loc_180020037
0x18001fef6  cmp     [rsp+88h+var_58], bpl
0x18001fefb  jnz     loc_1800200A7
0x18001ff01  lea     rbx, [rdi+18h]
0x18001ff05  mov     rcx, [rbx]; string
0x18001ff08  call    cs:__imp_WindowsDeleteString
0x18001ff0e  mov     r8, rbx
0x18001ff11  mov     [rbx], rbp
0x18001ff14  lea     rdx, aDisplayname; "@DisplayName"
0x18001ff1b  mov     rcx, r14
0x18001ff1e  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x18001ff23  mov     ebx, eax
0x18001ff25  test    eax, eax
0x18001ff27  js      loc_1800202E5
0x18001ff2d  lea     r8, [rdi+21h]
0x18001ff31  mov     rcx, rsi
0x18001ff34  lea     rdx, aInprocessmedia; "inProcessMediaExtension"
0x18001ff3b  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x18001ff40  mov     ebx, eax
0x18001ff42  test    eax, eax
0x18001ff44  js      loc_180020372
0x18001ff4a  lea     r8, [rdi+22h]
0x18001ff4e  mov     rcx, rsi
0x18001ff51  lea     rdx, aWebplatformmed; "webPlatformMediaExtension"
0x18001ff58  call    ?CreateBOOLFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEA_N@Z; CreateBOOLFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,bool *)
0x18001ff5d  mov     ebx, eax
0x18001ff5f  test    eax, eax
0x18001ff61  jns     loc_18001FE34
0x18001ff67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ff6e  test    rcx, rcx
0x18001ff71  jnz     short loc_18001FFAF
0x18001ff73  mov     rax, cs:stru_1801FC290.__vftable
0x18001ff7a  lea     r8, stru_1801FC290
0x18001ff81  mov     edx, 7F0h
0x18001ff86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ff8d  mov     rcx, r8
0x18001ff90  mov     rax, [rax+8]
0x18001ff94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff99  test    eax, eax
0x18001ff9b  jnz     loc_1800203FF
0x18001ffa1  lea     rcx, stru_1801F8A30; this
0x18001ffa8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ffaf  cmp     [rcx+8], bpl
0x18001ffb3  jnz     loc_18002040B
0x18001ffb9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ffc0  jb      loc_18001FE34
0x18001ffc6  mov     edx, 7Ah ; 'z'
0x18001ffcb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffd2  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18001ffd9  xor     r9d, r9d
0x18001ffdc  mov     [rsp+88h+var_68], ebx
0x18001ffe0  mov     rcx, [rcx+10h]
0x18001ffe4  call    WPP_SF_qD
0x18001ffe9  jmp     loc_18001FE34
0x18001ffee  mov     rcx, cs:stru_1801FC290.__vftable
0x18001fff5  lea     r8, stru_1801FC290
0x18001fffc  mov     edx, 7F0h
0x180020001  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180020008  mov     rax, [rcx+8]
0x18002000c  mov     rcx, r8
0x18002000f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020014  test    eax, eax
0x180020016  jnz     short loc_18002002B
0x180020018  lea     rcx, stru_1801F8A30
0x18002001f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020026  jmp     loc_18001FE1D
0x18002002b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180020032  jmp     loc_18001FE1D
0x180020037  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002003e  mov     [rsp+88h+string], rbp
0x180020043  test    rcx, rcx
0x180020046  jz      short loc_180020069
0x180020048  cmp     [rcx+8], bpl
0x18002004c  jnz     loc_180020291
0x180020052  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020059  jb      loc_18001FE34
0x18002005f  mov     edx, 76h ; 'v'
0x180020064  jmp     loc_18001FFCB
0x180020069  mov     rax, cs:stru_1801FC290.__vftable
0x180020070  lea     r8, stru_1801FC290
0x180020077  mov     edx, 7F0h
0x18002007c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180020083  mov     rcx, r8
0x180020086  mov     rax, [rax+8]
0x18002008a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002008f  test    eax, eax
0x180020091  jnz     loc_180020138
0x180020097  lea     rcx, stru_1801F8A30
0x18002009e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800200a5  jmp     short loc_180020048
0x1800200a7  lea     rbx, [rdi+10h]
0x1800200ab  mov     rcx, [rbx]; string
0x1800200ae  call    cs:__imp_WindowsDeleteString
0x1800200b4  mov     r8, rbx
0x1800200b7  mov     [rbx], rbp
0x1800200ba  lea     rdx, aAppservicename; "@AppServiceName"
0x1800200c1  mov     rcx, r14
0x1800200c4  call    ?CreateStringFromMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; CreateStringFromMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,HSTRING__ * *)
0x1800200c9  mov     ebx, eax
0x1800200cb  test    eax, eax
0x1800200cd  jns     loc_18001FF01
0x1800200d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800200da  test    rcx, rcx
0x1800200dd  jnz     short loc_180020117
0x1800200df  mov     rax, cs:stru_1801FC290.__vftable
0x1800200e6  lea     r8, stru_1801FC290
0x1800200ed  mov     edx, 7F0h
0x1800200f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800200f9  mov     rcx, r8
0x1800200fc  mov     rax, [rax+8]
0x180020100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020105  test    eax, eax
0x180020107  jnz     short loc_180020144
0x180020109  lea     rcx, stru_1801F8A30; this
0x180020110  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020117  cmp     [rcx+8], bpl
0x18002011b  jnz     loc_1800202BB
0x180020121  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020128  jb      loc_18001FE34
0x18002012e  mov     edx, 77h ; 'w'
0x180020133  jmp     loc_18001FFCB
0x180020138  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002013f  jmp     loc_180020048
0x180020144  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002014b  jmp     short loc_180020117
0x18002014d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180020152  cmp     [rax+7CCh], ebx
0x180020158  jz      loc_18001FE27
0x18002015e  mov     r9d, ebx; int
0x180020161  mov     r8d, 39Fh; int
0x180020167  mov     rdx, r15; char *
0x18002016a  mov     rcx, rax; this
0x18002016d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180020172  jmp     loc_18001FE27
0x180020177  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002017e  test    rcx, rcx
0x180020181  jnz     short loc_1800201BB
0x180020183  mov     rax, cs:stru_1801FC290.__vftable
0x18002018a  lea     r8, stru_1801FC290
0x180020191  mov     edx, 7F0h
0x180020196  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18002019d  mov     rcx, r8
0x1800201a0  mov     rax, [rax+8]
0x1800201a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201a9  test    eax, eax
0x1800201ab  jnz     short loc_1800201D8
0x1800201ad  lea     rcx, stru_1801F8A30; this
0x1800201b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800201bb  cmp     [rcx+8], bpl
0x1800201bf  jnz     short loc_1800201E1
0x1800201c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800201c8  jb      loc_18001FE34
0x1800201ce  mov     edx, 74h ; 't'
0x1800201d3  jmp     loc_18001FFCB
0x1800201d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800201df  jmp     short loc_1800201BB
0x1800201e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800201e6  cmp     [rax+7CCh], ebx
0x1800201ec  jz      short loc_1800201C1
0x1800201ee  mov     r9d, ebx; int
0x1800201f1  mov     r8d, 3A0h; int
0x1800201f7  mov     rdx, r15; char *
0x1800201fa  mov     rcx, rax; this
0x1800201fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180020202  jmp     short loc_1800201C1
0x180020204  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002020b  test    rcx, rcx
0x18002020e  jnz     short loc_180020248
0x180020210  mov     rax, cs:stru_1801FC290.__vftable
0x180020217  lea     r8, stru_1801FC290
0x18002021e  mov     edx, 7F0h
0x180020223  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18002022a  mov     rcx, r8
0x18002022d  mov     rax, [rax+8]
0x180020231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020236  test    eax, eax
0x180020238  jnz     short loc_180020265
0x18002023a  lea     rcx, stru_1801F8A30; this
0x180020241  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180020248  cmp     [rcx+8], bpl
0x18002024c  jnz     short loc_18002026E
0x18002024e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020255  jb      loc_18001FE34
0x18002025b  mov     edx, 75h ; 'u'
0x180020260  jmp     loc_18001FFCB
0x180020265  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002026c  jmp     short loc_180020248
0x18002026e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180020273  cmp     [rax+7CCh], ebx
0x180020279  jz      short loc_18002024E
0x18002027b  mov     r9d, ebx; int
0x18002027e  mov     r8d, 3A1h; int
0x180020284  mov     rdx, r15; char *
0x180020287  mov     rcx, rax; this
0x18002028a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002028f  jmp     short loc_18002024E
0x180020291  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180020296  cmp     [rax+7CCh], ebx
0x18002029c  jz      loc_180020052
0x1800202a2  mov     r9d, ebx; int
0x1800202a5  mov     r8d, 3A3h; int
0x1800202ab  mov     rdx, r15; char *
0x1800202ae  mov     rcx, rax; this
0x1800202b1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800202b6  jmp     loc_180020052
0x1800202bb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800202c0  cmp     [rax+7CCh], ebx
0x1800202c6  jz      loc_180020121
0x1800202cc  mov     r9d, ebx; int
0x1800202cf  mov     r8d, 3A7h; int
0x1800202d5  mov     rdx, r15; char *
0x1800202d8  mov     rcx, rax; this
0x1800202db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800202e0  jmp     loc_180020121
0x1800202e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
