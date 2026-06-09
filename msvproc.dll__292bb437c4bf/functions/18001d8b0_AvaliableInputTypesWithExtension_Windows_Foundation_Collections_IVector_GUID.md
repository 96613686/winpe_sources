# AvaliableInputTypesWithExtension(Windows::Foundation::Collections::IVector<_GUID> *)

- ea: `0x18001d8b0`
- end: `0x18001e007`
- name: `?AvaliableInputTypesWithExtension@@YAJPEAU?$IVector@U_GUID@@@Collections@Foundation@Windows@@@Z`
- size: `1879`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e960`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180018708`
- `0x18001d8b0`
- `0x18003639c`
- `0x180054140`
- `0x180066a98`
- `0x1800b33dc`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d94a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d94a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d935`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18001d95d`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18001d95d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001da0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dc8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dd22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ddb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001de40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001decf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001da0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dc8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001dd22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ddb1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001de40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001decf`

## string_xrefs

- `0x18001d8ea`: `AvaliableInputTypesWithExtension`
- `0x18001dce5`: `AvaliableInputTypesWithExtension`
- `0x18001dd79`: `AvaliableInputTypesWithExtension`
- `0x18001de08`: `AvaliableInputTypesWithExtension`
- `0x18001de97`: `AvaliableInputTypesWithExtension`
- `0x18001df26`: `AvaliableInputTypesWithExtension`

## pseudocode

```c
__int64 __fastcall AvaliableInputTypesWithExtension(__int64 *a1)
{
  HRESULT v2; // eax
  __int64 v3; // rcx
  int MediaComponentPackageInfo; // ebx
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v7; // rdx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  unsigned int v11; // r14d
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD); // rbx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // r15d
  void ***i; // rdx
  unsigned int v20; // ecx
  unsigned __int64 v21; // r8
  __int128 v22; // xmm6
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rcx
  __int64 v43; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v47; // [rsp+58h] [rbp-B0h] BYREF
  int v48; // [rsp+5Ch] [rbp-ACh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+80h] [rbp-88h] BYREF
  _OWORD v51[2]; // [rsp+88h] [rbp-80h] BYREF
  __int16 v52; // [rsp+A8h] [rbp-60h]
  char v53; // [rsp+AAh] [rbp-5Eh]
  __int128 v54; // [rsp+B8h] [rbp-50h]
  int v55; // [rsp+C8h] [rbp-40h]
  void **v56; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-30h]
  __int128 v58; // [rsp+E0h] [rbp-28h]
  __int16 v59; // [rsp+F0h] [rbp-18h]
  char v60; // [rsp+F2h] [rbp-16h]
  __int64 v61; // [rsp+238h] [rbp+130h]
  unsigned int v62; // [rsp+240h] [rbp+138h]
  __int64 v63; // [rsp+248h] [rbp+140h]

  v47 = 0;
  v46 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "AvaliableInputTypesWithExtension", 72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  string = 0;
  v2 = WindowsCreateStringReference(
         L"windows.videoRendererEffect",
         0x1Bu,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  LOBYTE(v3) = 1;
  MediaComponentPackageInfo = GetMediaComponentPackageInfo(v3, string, &v46);
  if ( MediaComponentPackageInfo < 0 )
  {
    v5 = CallStackTracing::s_wpInstance;
    string = 0;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v5 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "AvaliableInputTypesWithExtension",
          72,
          MediaComponentPackageInfo);
    }
    if ( g_wppLevels )
    {
      v7 = 10;
LABEL_11:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
        0,
        MediaComponentPackageInfo);
      goto LABEL_97;
    }
    goto LABEL_97;
  }
  MediaComponentPackageInfo = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v47);
  if ( MediaComponentPackageInfo >= 0 )
  {
    v11 = 0;
LABEL_24:
    if ( v11 >= v47 )
      goto LABEL_97;
    v12 = v46;
    v45 = 0;
    v59 = 0;
    v60 = 0;
    v44 = 0;
    v56 = &CTDynArray<_GUID,20>::`vftable';
    memset(v51, 0, sizeof(v51));
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v57 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v46 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    MediaComponentPackageInfo = v13(v12, v11, &v45);
    if ( MediaComponentPackageInfo < 0 )
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
        if ( *((_DWORD *)v40 + 499) != MediaComponentPackageInfo )
          CallStackContext::TraceFailure(v40, "AvaliableInputTypesWithExtension", 82, MediaComponentPackageInfo);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v28 = 12;
    }
    else
    {
      v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
      v15 = **v45;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      MediaComponentPackageInfo = v15(v14, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v44);
      if ( MediaComponentPackageInfo < 0 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != MediaComponentPackageInfo )
            CallStackContext::TraceFailure(v37, "AvaliableInputTypesWithExtension", 83, MediaComponentPackageInfo);
        }
        if ( !g_wppLevels )
          goto LABEL_96;
        v28 = 13;
      }
      else
      {
        MediaComponentPackageInfo = CreateVideoRendererInfoFromMediaExtensionMap(v44, v51);
        if ( MediaComponentPackageInfo >= 0 )
        {
          v16 = v62;
          v17 = 0;
          v18 = v62;
          while ( 1 )
          {
            if ( v17 >= v18 )
            {
              VideoRendererPackInfo::~VideoRendererPackInfo((VideoRendererPackInfo *)v51);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              ++v11;
              goto LABEL_24;
            }
            v48 = 0;
            LOBYTE(v43) = 0;
            *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
            if ( v17 >= v16 )
              break;
            for ( i = &v56; i; i = (void ***)i[45] )
            {
              v20 = *((_DWORD *)i + 2);
              if ( v17 >= v20 && v17 < v20 + 20 )
              {
                v21 = v17 - v20;
                if ( (*((_BYTE *)&CTSparseBlock<unsigned long,_GUID,20,0>::s_bSingleBitMasks + (v21 & 7))
                    & *((_BYTE *)i + (v21 >> 3) + 32)) != 0 )
                {
                  v22 = *(_OWORD *)((char *)&i[2 * v21 + 4] + 4);
                  goto LABEL_40;
                }
                break;
              }
            }
            if ( (v57 & 0x100000000LL) == 0 )
              break;
            v22 = v58;
LABEL_40:
            v23 = *a1;
            *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = v22;
            MediaComponentPackageInfo = 0;
            if ( (*(int (__fastcall **)(__int64 *, char *, int *, __int64 *))(v23 + 72))(
                   a1,
                   &hstringHeader.Reserved.Reserved2[8],
                   &v48,
                   &v43) >= 0
              && !(_BYTE)v43 )
            {
              v24 = *a1;
              *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = v22;
              MediaComponentPackageInfo = (*(__int64 (__fastcall **)(__int64 *, char *))(v24 + 104))(
                                            a1,
                                            &hstringHeader.Reserved.Reserved2[8]);
              if ( MediaComponentPackageInfo < 0 )
              {
                v25 = (__int64 *)CallStackTracing::s_wpInstance;
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
                  if ( *((_DWORD *)v27 + 499) != MediaComponentPackageInfo )
                    CallStackContext::TraceFailure(
                      v27,
                      "AvaliableInputTypesWithExtension",
                      95,
                      MediaComponentPackageInfo);
                }
                if ( g_wppLevels )
                {
                  v28 = 16;
                  goto LABEL_95;
                }
                goto LABEL_96;
              }
            }
            v16 = v62;
            ++v17;
          }
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          MediaComponentPackageInfo = -1072875845;
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
            if ( *((_DWORD *)v31 + 499) != -1072875845 )
              CallStackContext::TraceFailure(v31, "AvaliableInputTypesWithExtension", 92, -1072875845);
          }
          if ( g_wppLevels )
          {
            v28 = 15;
            goto LABEL_95;
          }
          goto LABEL_96;
        }
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != MediaComponentPackageInfo )
            CallStackContext::TraceFailure(v34, "AvaliableInputTypesWithExtension", 85, MediaComponentPackageInfo);
        }
        if ( !g_wppLevels )
        {
LABEL_96:
          VideoRendererPackInfo::~VideoRendererPackInfo((VideoRendererPackInfo *)v51);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
          goto LABEL_97;
        }
        v28 = 14;
      }
    }
LABEL_95:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v28,
      &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
      0,
      MediaComponentPackageInfo);
    goto LABEL_96;
  }
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v9;
    if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( *((_DWORD *)v10 + 499) != MediaComponentPackageInfo )
      CallStackContext::TraceFailure(v10, "AvaliableInputTypesWithExtension", 73, MediaComponentPackageInfo);
  }
  if ( g_wppLevels )
  {
    v7 = 11;
    goto LABEL_11;
  }
LABEL_97:
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      17,
      &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
      (unsigned int)MediaComponentPackageInfo);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
  v41 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d8b0  mov     rax, rsp
0x18001d8b3  mov     [rax+10h], rbx
0x18001d8b7  mov     [rax+18h], rdi
0x18001d8bb  push    rbp
0x18001d8bc  push    r12
0x18001d8be  push    r13
0x18001d8c0  push    r14
0x18001d8c2  push    r15
0x18001d8c4  lea     rbp, [rax-198h]
0x18001d8cb  sub     rsp, 270h
0x18001d8d2  movaps  xmmword ptr [rax-38h], xmm6
0x18001d8d6  mov     rax, cs:__security_cookie
0x18001d8dd  xor     rax, rsp
0x18001d8e0  mov     [rbp+190h+var_40], rax
0x18001d8e7  xor     r13d, r13d
0x18001d8ea  lea     r15, aAvaliableinput; "AvaliableInputTypesWithExtension"
0x18001d8f1  mov     r12, rcx
0x18001d8f4  mov     [rsp+290h+var_240], r13d
0x18001d8f9  mov     rdx, r15; char *
0x18001d8fc  mov     [rsp+290h+var_248], r13
0x18001d901  lea     rcx, [rsp+290h+var_260]; this
0x18001d906  lea     edi, [r13+48h]
0x18001d90a  mov     r8d, edi; int
0x18001d90d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001d912  lea     rcx, [rsp+290h+var_248]
0x18001d917  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001d91c  lea     r9, [rsp+290h+string]; string
0x18001d921  mov     [rsp+290h+string], r13
0x18001d926  lea     r8, [rsp+290h+hstringHeader.Reserved+8]; hstringHeader
0x18001d92b  lea     edx, [rdi-2Dh]; length
0x18001d92e  lea     rcx, aWindowsVideore; "windows.videoRendererEffect"
0x18001d935  call    cs:__imp_WindowsCreateStringReference
0x18001d93b  test    eax, eax
0x18001d93d  jns     short loc_18001D951
0x18001d93f  xor     r9d, r9d; lpArguments
0x18001d942  lea     edx, [rdi-47h]; dwExceptionFlags
0x18001d945  xor     r8d, r8d; nNumberOfArguments
0x18001d948  mov     ecx, eax; dwExceptionCode
0x18001d94a  call    cs:__imp_RaiseException
0x18001d950  int     3; Trap to Debugger
0x18001d951  mov     rdx, [rsp+290h+string]
0x18001d956  lea     r8, [rsp+290h+var_248]
0x18001d95b  mov     cl, 1
0x18001d95d  call    cs:__imp_GetMediaComponentPackageInfo
0x18001d963  mov     ebx, eax
0x18001d965  test    eax, eax
0x18001d967  jns     short loc_18001D9DF
0x18001d969  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001d970  mov     [rsp+290h+string], r13
0x18001d975  test    rcx, rcx
0x18001d978  jnz     short loc_18001D986
0x18001d97a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001d97f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001d986  cmp     [rcx+8], r13b
0x18001d98a  jz      short loc_18001D9AA
0x18001d98c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001d991  cmp     [rax+7CCh], ebx
0x18001d997  jz      short loc_18001D9AA
0x18001d999  mov     r9d, ebx; int
0x18001d99c  mov     r8d, edi; int
0x18001d99f  mov     rdx, r15; char *
0x18001d9a2  mov     rcx, rax; this
0x18001d9a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001d9aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d9b1  jb      loc_18001DF84
0x18001d9b7  mov     edx, 0Ah
0x18001d9bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9c3  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x18001d9ca  xor     r9d, r9d
0x18001d9cd  mov     [rsp+290h+var_270], ebx
0x18001d9d1  mov     rcx, [rcx+10h]
0x18001d9d5  call    WPP_SF_qD
0x18001d9da  jmp     loc_18001DF84
0x18001d9df  mov     rcx, [rsp+290h+var_248]
0x18001d9e4  lea     rdx, [rsp+290h+var_240]
0x18001d9e9  mov     rax, [rcx]
0x18001d9ec  mov     rax, [rax+38h]
0x18001d9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f5  mov     ebx, eax
0x18001d9f7  test    eax, eax
0x18001d9f9  jns     loc_18001DA8A
0x18001d9ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da06  test    rcx, rcx
0x18001da09  jnz     short loc_18001DA4C
0x18001da0b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001da11  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da18  mov     rcx, rax
0x18001da1b  test    rax, rax
0x18001da1e  jz      short loc_18001DA3E
0x18001da20  mov     rax, [rax]
0x18001da23  mov     edx, 7F0h
0x18001da28  mov     rax, [rax+8]
0x18001da2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da31  test    eax, eax
0x18001da33  jz      short loc_18001DA3E
0x18001da35  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da3c  jmp     short loc_18001DA4C
0x18001da3e  lea     rcx, qword_180153440; this
0x18001da45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001da4c  cmp     [rcx+8], r13b
0x18001da50  jz      short loc_18001DA73
0x18001da52  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001da57  cmp     [rax+7CCh], ebx
0x18001da5d  jz      short loc_18001DA73
0x18001da5f  mov     r9d, ebx; int
0x18001da62  mov     r8d, 49h ; 'I'; int
0x18001da68  mov     rdx, r15; char *
0x18001da6b  mov     rcx, rax; this
0x18001da6e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001da73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001da7a  jb      loc_18001DF84
0x18001da80  mov     edx, 0Bh
0x18001da85  jmp     loc_18001D9BC
0x18001da8a  mov     r14d, r13d
0x18001da8d  cmp     r14d, [rsp+290h+var_240]
0x18001da92  jnb     loc_18001DF84
0x18001da98  mov     rdi, [rsp+290h+var_248]
0x18001da9d  lea     rcx, [rsp+290h+var_250]
0x18001daa2  xor     eax, eax
0x18001daa4  mov     [rsp+290h+var_250], r13
0x18001daa9  mov     [rbp+190h+var_1A8], ax
0x18001daad  xorps   xmm0, xmm0
0x18001dab0  mov     [rbp+190h+var_1A6], al
0x18001dab3  xorps   xmm1, xmm1
0x18001dab6  lea     rax, ??_7?$CTDynArray@U_GUID@@$0BE@@@6B@; const CTDynArray<_GUID,20>::`vftable'
0x18001dabd  mov     [rsp+290h+var_258], r13
0x18001dac2  mov     [rbp+190h+var_1C8], rax
0x18001dac6  movdqa  [rbp+190h+var_210], xmm0
0x18001dacb  movdqa  [rbp+190h+var_200], xmm1
0x18001dad0  mov     [rbp+190h+var_1F0], r13w
0x18001dad5  mov     [rbp+190h+var_1EE], r13b
0x18001dad9  movdqa  [rbp+190h+var_1E0], xmm0
0x18001dade  mov     [rbp+190h+var_1D0], r13d
0x18001dae2  mov     [rbp+190h+var_1C0], r13
0x18001dae6  mov     [rbp+190h+var_60], r13
0x18001daed  mov     [rbp+190h+var_58], r13d
0x18001daf4  mov     [rbp+190h+var_50], r13
0x18001dafb  mov     rax, [rdi]
0x18001dafe  mov     rbx, [rax+30h]
0x18001db02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001db07  lea     r8, [rsp+290h+var_250]
0x18001db0c  mov     edx, r14d
0x18001db0f  mov     rcx, rdi
0x18001db12  mov     rax, rbx
0x18001db15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db1a  mov     ebx, eax
0x18001db1c  test    eax, eax
0x18001db1e  js      loc_18001DEC3
0x18001db24  mov     rdi, [rsp+290h+var_250]
0x18001db29  lea     rcx, [rsp+290h+var_258]
0x18001db2e  mov     rax, [rdi]
0x18001db31  mov     rbx, [rax]
0x18001db34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001db39  lea     r8, [rsp+290h+var_258]
0x18001db3e  mov     rcx, rdi
0x18001db41  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18001db48  mov     rax, rbx
0x18001db4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db50  mov     ebx, eax
0x18001db52  test    eax, eax
0x18001db54  js      loc_18001DE34
0x18001db5a  mov     rcx, [rsp+290h+var_258]
0x18001db5f  lea     rdx, [rbp+190h+var_210]
0x18001db63  call    ?CreateVideoRendererInfoFromMediaExtensionMap@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUVideoRendererPackInfo@@@Z; CreateVideoRendererInfoFromMediaExtensionMap(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,VideoRendererPackInfo &)
0x18001db68  mov     ebx, eax
0x18001db6a  test    eax, eax
0x18001db6c  js      loc_18001DDA5
0x18001db72  mov     eax, [rbp+190h+var_58]
0x18001db78  mov     edi, r13d
0x18001db7b  mov     r15d, eax
0x18001db7e  cmp     edi, r15d
0x18001db81  jnb     loc_18001DC5D
0x18001db87  mov     [rsp+290h+var_23C], r13d
0x18001db8c  xorps   xmm0, xmm0
0x18001db8f  mov     byte ptr [rsp+290h+var_260], r13b
0x18001db94  movups  xmmword ptr [rsp+290h+hstringHeader.Reserved+8], xmm0
0x18001db99  cmp     edi, eax
0x18001db9b  jnb     loc_18001DD11
0x18001dba1  lea     rdx, [rbp+190h+var_1C8]
0x18001dba5  test    rdx, rdx
0x18001dba8  jz      short loc_18001DBEE
0x18001dbaa  mov     ecx, [rdx+8]
0x18001dbad  cmp     edi, ecx
0x18001dbaf  jb      short loc_18001DBB8
0x18001dbb1  lea     eax, [rcx+14h]
0x18001dbb4  cmp     edi, eax
0x18001dbb6  jb      short loc_18001DBC1
0x18001dbb8  mov     rdx, [rdx+168h]
0x18001dbbf  jmp     short loc_18001DBA5
0x18001dbc1  mov     eax, edi
0x18001dbc3  lea     r9, ?s_bSingleBitMasks@?$CTSparseBlock@KU_GUID@@$0BE@$0A@@@0QBEB; uchar const near * const CTSparseBlock<ulong,_GUID,20,0>::s_bSingleBitMasks
0x18001dbca  sub     eax, ecx
0x18001dbcc  mov     r8d, eax
0x18001dbcf  and     eax, 7
0x18001dbd2  mov     ecx, r8d
0x18001dbd5  shr     rcx, 3
0x18001dbd9  mov     al, [rax+r9]
0x18001dbdd  test    [rcx+rdx+20h], al
0x18001dbe1  jz      short loc_18001DBEE
0x18001dbe3  add     r8, r8
0x18001dbe6  movups  xmm6, xmmword ptr [rdx+r8*8+24h]
0x18001dbec  jmp     short loc_18001DBFC
0x18001dbee  test    byte ptr [rbp+190h+var_1C0+4], 1
0x18001dbf2  jz      loc_18001DD11
0x18001dbf8  movups  xmm6, [rbp+190h+var_1B8]
0x18001dbfc  mov     rax, [r12]
0x18001dc00  lea     r9, [rsp+290h+var_260]
0x18001dc05  lea     r8, [rsp+290h+var_23C]
0x18001dc0a  movdqa  xmmword ptr [rsp+290h+hstringHeader.Reserved+8], xmm6
0x18001dc10  lea     rdx, [rsp+290h+hstringHeader.Reserved+8]
0x18001dc15  mov     rcx, r12
0x18001dc18  mov     ebx, r13d
0x18001dc1b  mov     rax, [rax+48h]
0x18001dc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc24  test    eax, eax
0x18001dc26  js      short loc_18001DC50
0x18001dc28  cmp     byte ptr [rsp+290h+var_260], r13b
0x18001dc2d  jnz     short loc_18001DC50
0x18001dc2f  mov     rax, [r12]
0x18001dc33  lea     rdx, [rsp+290h+hstringHeader.Reserved+8]
0x18001dc38  mov     rcx, r12
0x18001dc3b  movdqa  xmmword ptr [rsp+290h+hstringHeader.Reserved+8], xmm6
0x18001dc41  mov     rax, [rax+68h]
0x18001dc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc4a  mov     ebx, eax
0x18001dc4c  test    eax, eax
0x18001dc4e  js      short loc_18001DC82
0x18001dc50  mov     eax, [rbp+190h+var_58]
0x18001dc56  inc     edi
0x18001dc58  jmp     loc_18001DB7E
0x18001dc5d  lea     rcx, [rbp+190h+var_210]; this
0x18001dc61  call    ??1VideoRendererPackInfo@@QEAA@XZ; VideoRendererPackInfo::~VideoRendererPackInfo(void)
0x18001dc66  lea     rcx, [rsp+290h+var_258]
0x18001dc6b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dc70  lea     rcx, [rsp+290h+var_250]
0x18001dc75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001dc7a  inc     r14d
0x18001dc7d  jmp     loc_18001DA8D
0x18001dc82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dc89  test    rcx, rcx
0x18001dc8c  jnz     short loc_18001DCCF
0x18001dc8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001dc94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dc9b  mov     rcx, rax
0x18001dc9e  test    rax, rax
0x18001dca1  jz      short loc_18001DCC1
0x18001dca3  mov     rax, [rax]
0x18001dca6  mov     edx, 7F0h
0x18001dcab  mov     rax, [rax+8]
0x18001dcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcb4  test    eax, eax
0x18001dcb6  jz      short loc_18001DCC1
0x18001dcb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dcbf  jmp     short loc_18001DCCF
0x18001dcc1  lea     rcx, qword_180153440; this
0x18001dcc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dccf  cmp     [rcx+8], r13b
0x18001dcd3  jz      short loc_18001DCFA
0x18001dcd5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001dcda  cmp     [rax+7CCh], ebx
0x18001dce0  jz      short loc_18001DCFA
0x18001dce2  mov     r9d, ebx; int
0x18001dce5  lea     rdx, aAvaliableinput; "AvaliableInputTypesWithExtension"
0x18001dcec  mov     r8d, 5Fh ; '_'; int
0x18001dcf2  mov     rcx, rax; this
0x18001dcf5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001dcfa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001dd01  jb      loc_18001DF67
0x18001dd07  mov     edx, 10h
0x18001dd0c  jmp     loc_18001DF49
0x18001dd11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dd18  mov     ebx, 0C00D36BBh
0x18001dd1d  test    rcx, rcx
0x18001dd20  jnz     short loc_18001DD63
0x18001dd22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001dd28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dd2f  mov     rcx, rax
0x18001dd32  test    rax, rax
0x18001dd35  jz      short loc_18001DD55
0x18001dd37  mov     rax, [rax]
0x18001dd3a  mov     edx, 7F0h
0x18001dd3f  mov     rax, [rax+8]
0x18001dd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd48  test    eax, eax
0x18001dd4a  jz      short loc_18001DD55
0x18001dd4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dd53  jmp     short loc_18001DD63
0x18001dd55  lea     rcx, qword_180153440; this
0x18001dd5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001dd63  cmp     [rcx+8], r13b
0x18001dd67  jz      short loc_18001DD8E
0x18001dd69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001dd6e  cmp     [rax+7CCh], ebx
0x18001dd74  jz      short loc_18001DD8E
0x18001dd76  mov     r9d, ebx; int
0x18001dd79  lea     rdx, aAvaliableinput; "AvaliableInputTypesWithExtension"
0x18001dd80  mov     r8d, 5Ch ; '\'; int
0x18001dd86  mov     rcx, rax; this
0x18001dd89  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001dd8e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
