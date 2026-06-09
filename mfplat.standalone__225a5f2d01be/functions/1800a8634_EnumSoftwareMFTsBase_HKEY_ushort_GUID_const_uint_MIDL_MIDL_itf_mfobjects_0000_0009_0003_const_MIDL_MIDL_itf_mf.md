# EnumSoftwareMFTsBase(HKEY__ *,ushort *,_GUID const &,uint,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFActivate * * *,uint *)

- ea: `0x1800a8634`
- end: `0x1800a8f18`
- name: `?EnumSoftwareMFTsBase@@YAJPEAUHKEY__@@PEAGAEBU_GUID@@IPEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@3PEAPEAPEAUIMFActivate@@PEAI@Z`
- size: `2276`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, unsigned __int16 *@<rdx>, const struct _GUID *@<r8>, unsigned int@<r9d>, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFActivate ***, unsigned int *)`
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800afd58`
- `0x1800b1484`

## callees

- `0x180015b20`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18004ee70`
- `0x180056284`
- `0x180056f9c`
- `0x1800571bc`
- `0x18005735c`
- `0x180057d78`
- `0x180057e90`
- `0x18005ece0`
- `0x18007bd84`
- `0x180094cb8`
- `0x1800a8634`
- `0x1800a8f20`
- `0x1801200d0`
- `0x180120ecc`
- `0x180121300`
- `0x180121368`
- `0x180136918`
- `0x180144a5c`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a8777`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a8777`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8e8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8e9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8745`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8e8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a8e9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8837`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a8837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a88d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8981`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a88d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8977`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8981`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a8b10`

## pseudocode

```c
__int64 __fastcall EnumSoftwareMFTsBase(
        HKEY hKey,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        int a4,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a5,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a6,
        struct IMFActivate ***a7,
        unsigned int *a8)
{
  HKEY v8; // rbx
  unsigned __int8 v9; // r14
  void **v10; // rsi
  bool v13; // zf
  __int64 v14; // rax
  char v15; // di
  int v16; // eax
  DWORD i; // esi
  LSTATUS v18; // eax
  DWORD v19; // ebx
  int Value; // eax
  struct IMFAttributes *v21; // r9
  bool v22; // sf
  BYTE v23; // dl
  void *v24; // rcx
  IMFAttributes *v25; // r14
  IMFAttributes_vtbl *v26; // rax
  IMFAttributes_vtbl *v27; // rax
  void **v28; // r9
  unsigned __int64 v29; // rcx
  unsigned __int128 v30; // rax
  void *v31; // r8
  int v32; // esi
  IMFActivate *v33; // rsi
  CMFEventTraceClassName *v34; // rax
  __int64 v35; // rcx
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  struct CallStackContext *v42; // rax
  CallStackTracing *v43; // rcx
  struct CallStackContext *v44; // rax
  CallStackTracing *v45; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v47; // r12d
  unsigned int v48; // edi
  void **v49; // r14
  __int64 v50; // rcx
  CallStackScopeTrace v52; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  int v54; // [rsp+48h] [rbp-B8h]
  void **v55; // [rsp+50h] [rbp-B0h]
  IMFActivate *ppActivate; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v57; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v58; // [rsp+68h] [rbp-98h]
  DWORD cbData[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v60; // [rsp+78h] [rbp-88h]
  HKEY hKeya; // [rsp+80h] [rbp-80h] BYREF
  HKEY v62; // [rsp+88h] [rbp-78h] BYREF
  __int16 v63; // [rsp+90h] [rbp-70h]
  __int64 v64; // [rsp+94h] [rbp-6Ch]
  LPVOID pv[2]; // [rsp+A0h] [rbp-60h]
  IMFAttributes *ppMFAttributes[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v67; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cchName; // [rsp+D0h] [rbp-30h] BYREF
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v69; // [rsp+D8h] [rbp-28h]
  struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *v70; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v71; // [rsp+E8h] [rbp-18h]
  GUID rguid; // [rsp+F0h] [rbp-10h] BYREF
  char v73[208]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Name[40]; // [rsp+1D0h] [rbp+D0h] BYREF

  v8 = 0;
  v9 = a4;
  v10 = (void **)a7;
  v70 = a5;
  v69 = a6;
  v60 = *a8;
  v14 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  v13 = *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  v54 = a4;
  v71 = a2;
  v55 = (void **)a7;
  hKeya = 0;
  v57 = 0;
  *(_DWORD *)Data = 0;
  if ( v13 )
    v14 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v14 )
  {
    rguid = *a3;
    v16 = OpenCategoryKey(hKey, &rguid, &hKeya);
    v15 = 1;
    if ( v16 < 0 )
    {
      if ( v16 != -2147024894 )
        LODWORD(v8) = v16;
      goto LABEL_116;
    }
    v8 = v57;
  }
  else
  {
    v15 = 0;
    hKeya = hKey;
  }
  for ( i = 0; ; ++i )
  {
    v58 = i;
    LODWORD(ppActivate) = 0;
    rguid = 0;
    memset_0(Name, 0, 0x4Au);
    cchName = 37;
    if ( v8 )
    {
      RegCloseKey(v8);
      v57 = 0;
    }
    v18 = RegEnumKeyExW(hKeya, i, Name, &cchName, 0, 0, 0, 0);
    LODWORD(v8) = v18;
    if ( v18 > 0 )
      LODWORD(v8) = (unsigned __int16)v18 | 0x80070000;
    if ( (_DWORD)v8 != -2147024662 )
      break;
LABEL_63:
    v8 = v57;
  }
  if ( (_DWORD)v8 != -2147024637 )
  {
    CallStackScopeTrace::CallStackScopeTrace(&v52, "EnumSoftwareMFTsBase", 1953);
    if ( (int)v8 < 0 )
    {
      v45 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v45 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v45 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v45->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v45);
        if ( ThreadRelativeContext->m_result != (_DWORD)v8 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "EnumSoftwareMFTsBase", 1953, (int)v8);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
          0,
          (_DWORD)v8);
      goto LABEL_74;
    }
    v19 = 0;
    if ( (int)GUIDFromString(Name, &rguid) < 0 )
      goto LABEL_62;
    v67 = rguid;
    if ( (int)OpenMFTKey(hKey, &v67, &v57) < 0 )
    {
      v57 = 0;
LABEL_62:
      CallStackScopeTrace::~CallStackScopeTrace(&v52);
      goto LABEL_63;
    }
    cbData[0] = 4;
    *(_DWORD *)Data = 0;
    Value = RegQueryValueExW(v57, L"MFTFlags", 0, 0, Data, cbData);
    v22 = Value < 0;
    if ( Value > 0 )
    {
      Value = (unsigned __int16)Value | 0x80070000;
      v22 = Value < 0;
    }
    if ( v22 )
    {
      if ( Value != -2147024894 )
        goto LABEL_62;
      v23 = Data[0] | 1;
      *(_DWORD *)Data |= 1u;
    }
    else
    {
      if ( cbData[0] != 4 )
        goto LABEL_62;
      v23 = Data[0];
    }
    v62 = v57;
    v63 = 0;
    v64 = 0;
    ppMFAttributes[0] = 0;
    *(_OWORD *)pv = 0;
    if ( (v23 & (unsigned __int8)~v9 & 0x3C) == 0 && (v9 & v23 & 7) != 0 )
    {
      if ( (int)CheckForMFTMatch((struct CMFTRegistrationInfo *)&v62, v70, v69, v21, (int *)&ppActivate) >= 0 )
      {
        v25 = ppMFAttributes[0];
        *(_QWORD *)&v67.Data1 = 0;
        if ( !ppMFAttributes[0] )
        {
          LODWORD(v8) = MFCreateAttributes(ppMFAttributes, 0);
          if ( (int)v8 < 0
            || (v25 = ppMFAttributes[0], LODWORD(v8) = GetAttributesFromRegistry(v62, ppMFAttributes[0]), (int)v8 < 0) )
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
              v37 = CallStackTracing::GetThreadRelativeContext(v36);
              if ( v37->m_result != (_DWORD)v8 )
                CallStackContext::TraceFailure(v37, "EnumSoftwareMFTsBase", 2024, (int)v8);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                40,
                &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
                0,
                (_DWORD)v8);
            goto LABEL_73;
          }
          v19 = 0;
        }
        v26 = v25->__vftable;
        *(_QWORD *)&v67.Data1 = v25;
        v26->AddRef(v25);
        v27 = v25->__vftable;
        cbData[0] = 0;
        if ( v27->GetUINT32(v25, &MFT_CODEC_MERIT_Attribute, cbData) >= 0 )
          v19 = cbData[0];
        if ( v19 && (v54 & 4) == 0 )
          goto LABEL_39;
        if ( dword_1801FDA20 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                           + (unsigned int)tls_index)
                                         + 4LL) )
        {
          Init_thread_header(&dword_1801FDA20);
          if ( dword_1801FDA20 == -1 )
          {
            byte_1801FDAE0 = IsWindowsToGo();
            Init_thread_footer(&dword_1801FDA20);
          }
        }
        if ( byte_1801FDAE0 && (v54 & 0x10000) == 0 && ((Data[0] & 4) != 0 || v19) )
        {
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v67);
          CMFTRegistrationInfo::~CMFTRegistrationInfo((CMFTRegistrationInfo *)&v62);
        }
        else
        {
          if ( (_DWORD)ppActivate )
          {
            ppActivate = 0;
            LODWORD(v8) = MFCreateTransformActivate(&ppActivate);
            if ( (int)v8 < 0 )
            {
              v43 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v43 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v43 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v43->m_fEnabled )
              {
                v44 = CallStackTracing::GetThreadRelativeContext(v43);
                if ( v44->m_result != (_DWORD)v8 )
                  CallStackContext::TraceFailure(v44, "EnumSoftwareMFTsBase", 2051, (int)v8);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v40 = 41;
LABEL_84:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v40,
                  &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
                  0,
                  (_DWORD)v8);
              }
LABEL_85:
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppActivate);
LABEL_73:
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v67);
              CMFTRegistrationInfo::~CMFTRegistrationInfo((CMFTRegistrationInfo *)&v62);
LABEL_74:
              CallStackScopeTrace::~CallStackScopeTrace(&v52);
              goto LABEL_115;
            }
            v28 = v55;
            v29 = *a8 + 1;
            v30 = (*a8 + 1) * (unsigned __int128)8u;
            v31 = *v55;
            *v55 = 0;
            *(_QWORD *)cbData = 0;
            if ( !is_mul_ok(v29, 8u) )
            {
              LODWORD(v8) = -2147024362;
              v32 = -2147024362;
LABEL_87:
              v41 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v41 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v41 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v41->m_fEnabled )
              {
                v42 = CallStackTracing::GetThreadRelativeContext(v41);
                if ( v42->m_result != v32 )
                  CallStackContext::TraceFailure(v42, "EnumSoftwareMFTsBase", 2054, v32);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  42,
                  &WPP_aba25f5d0023316200c116552e7e9732_Traceguids,
                  0,
                  v32);
              goto LABEL_85;
            }
            LODWORD(v8) = CTCoAllocPolicy::Realloc((void *)v29, *((__int64 *)&v30 + 1), v31, v30, v28);
            v32 = (int)v8;
            if ( (int)v8 < 0 )
              goto LABEL_87;
            v33 = ppActivate;
            LODWORD(v8) = SetSwTransformActivateAttributes(
                            (struct CMFTRegistrationInfo *)&v62,
                            ppActivate,
                            *(unsigned int *)Data,
                            &rguid,
                            a3,
                            v71);
            if ( (int)v8 < 0 )
            {
              v38 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                CallStackTracing::s_wpInstance = &stru_1801FC290;
                if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                {
                  v38 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v38 = &stru_1801F8A30;
                  CallStackTracing::s_wpInstance = &stru_1801F8A30;
                }
              }
              if ( v38->m_fEnabled )
              {
                v39 = CallStackTracing::GetThreadRelativeContext(v38);
                if ( v39->m_result != (_DWORD)v8 )
                  CallStackContext::TraceFailure(v39, "EnumSoftwareMFTsBase", 2065, (int)v8);
              }
              if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              {
                v40 = 43;
                goto LABEL_84;
              }
              goto LABEL_85;
            }
            *((_QWORD *)*v55 + (*a8)++) = v33;
            if ( (Microsoft_Windows_MediaFoundation_PlatformEnableBits & 2) != 0 )
            {
              v34 = CMFEventTraceClassName::CMFEventTraceClassName((CMFEventTraceClassName *)v73, &rguid);
              McTemplateU0z_EventWriteTransfer(v35, FoundSoftwareMFTEventDesc, v34);
            }
            i = v58;
          }
          if ( v25 )
LABEL_39:
            v25->Release(v25);
          CoTaskMemFree(pv[0]);
          CoTaskMemFree(pv[1]);
          ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(ppMFAttributes);
        }
        CallStackScopeTrace::~CallStackScopeTrace(&v52);
        v9 = v54;
        goto LABEL_63;
      }
      CoTaskMemFree(pv[0]);
      v24 = pv[1];
    }
    else
    {
      CoTaskMemFree(0);
      v24 = 0;
    }
    CoTaskMemFree(v24);
    ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(ppMFAttributes);
    goto LABEL_62;
  }
  LODWORD(v8) = 0;
LABEL_115:
  v10 = v55;
LABEL_116:
  if ( hKeya && v15 )
    RegCloseKey(hKeya);
  if ( v57 )
    RegCloseKey(v57);
  if ( (int)v8 < 0 )
  {
    v47 = v60;
    if ( *v10 )
    {
      v48 = v60;
      if ( v60 < *a8 )
      {
        v49 = v55;
        do
        {
          v50 = *((_QWORD *)*v49 + v48);
          if ( v50 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
            *((_QWORD *)*v49 + v48) = 0;
          }
          ++v48;
        }
        while ( v48 < *a8 );
      }
    }
    *a8 = v47;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800a8634  mov     [rsp-8+arg_18], rbx
0x1800a8639  push    rbp
0x1800a863a  push    rsi
0x1800a863b  push    rdi
0x1800a863c  push    r12
0x1800a863e  push    r13
0x1800a8640  push    r14
0x1800a8642  push    r15
0x1800a8644  lea     rbp, [rsp-130h]
0x1800a864c  sub     rsp, 230h
0x1800a8653  mov     rax, cs:__security_cookie
0x1800a865a  xor     rax, rsp
0x1800a865d  mov     [rbp+160h+var_40], rax
0x1800a8664  mov     rax, [rbp+160h+arg_20]
0x1800a866b  xor     ebx, ebx
0x1800a866d  mov     r15, [rbp+160h+arg_38]
0x1800a8674  mov     r14d, r9d
0x1800a8677  mov     rsi, [rbp+160h+arg_30]
0x1800a867e  mov     r12, r8
0x1800a8681  mov     [rbp+160h+var_180], rax
0x1800a8685  mov     r13, rcx
0x1800a8688  mov     rax, [rbp+160h+arg_28]
0x1800a868f  mov     [rbp+160h+var_188], rax
0x1800a8693  mov     eax, [r15]
0x1800a8696  mov     [rsp+260h+var_1E8], eax
0x1800a869a  mov     rax, [r8]
0x1800a869d  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800a86a4  mov     [rsp+260h+var_218], r9d
0x1800a86a9  mov     [rbp+160h+var_178], rdx
0x1800a86ad  mov     [rsp+260h+var_210], rsi
0x1800a86b2  mov     [rbp+160h+hKey], 0
0x1800a86ba  mov     [rsp+260h+var_200], rbx
0x1800a86bf  mov     dword ptr [rsp+260h+Data], ebx
0x1800a86c3  jnz     short loc_1800A86D0
0x1800a86c5  mov     rax, [r8+8]
0x1800a86c9  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800a86d0  test    rax, rax
0x1800a86d3  jnz     short loc_1800A86DE
0x1800a86d5  xor     dil, dil
0x1800a86d8  mov     [rbp+160h+hKey], r13
0x1800a86dc  jmp     short loc_1800A870D
0x1800a86de  movups  xmm0, xmmword ptr [r8]
0x1800a86e2  lea     r8, [rbp+160h+hKey]; HKEY *
0x1800a86e6  lea     rdx, [rbp+160h+rguid]; struct _GUID
0x1800a86ea  movdqu  xmmword ptr [rbp+160h+rguid.Data1], xmm0
0x1800a86ef  call    ?OpenCategoryKey@@YAJPEAUHKEY__@@U_GUID@@PEAPEAU1@@Z; OpenCategoryKey(HKEY__ *,_GUID,HKEY__ * *)
0x1800a86f4  mov     dil, 1
0x1800a86f7  test    eax, eax
0x1800a86f9  jns     short loc_1800A8708
0x1800a86fb  cmp     eax, 80070002h
0x1800a8700  cmovnz  ebx, eax
0x1800a8703  jmp     loc_1800A8E7D
0x1800a8708  mov     rbx, [rsp+260h+var_200]
0x1800a870d  xor     esi, esi
0x1800a870f  xor     edx, edx; Val
0x1800a8711  mov     [rsp+260h+var_1F8], esi
0x1800a8715  xorps   xmm0, xmm0
0x1800a8718  mov     dword ptr [rsp+260h+ppActivate], 0
0x1800a8720  lea     rcx, [rbp+160h+Name]; void *
0x1800a8727  movups  xmmword ptr [rbp+160h+rguid.Data1], xmm0
0x1800a872b  lea     r8d, [rdx+4Ah]; Size
0x1800a872f  call    memset_0
0x1800a8734  xor     eax, eax
0x1800a8736  mov     [rbp+160h+cchName], 25h ; '%'
0x1800a873d  test    rbx, rbx
0x1800a8740  jz      short loc_1800A8752
0x1800a8742  mov     rcx, rbx; hKey
0x1800a8745  call    cs:__imp_RegCloseKey
0x1800a874b  xor     eax, eax
0x1800a874d  mov     [rsp+260h+var_200], rax
0x1800a8752  mov     rcx, [rbp+160h+hKey]; hKey
0x1800a8756  lea     r9, [rbp+160h+cchName]; lpcchName
0x1800a875a  mov     [rsp+260h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800a875f  lea     r8, [rbp+160h+Name]; lpName
0x1800a8766  mov     [rsp+260h+lpcchClass], rax; lpcchClass
0x1800a876b  mov     edx, esi; dwIndex
0x1800a876d  mov     [rsp+260h+lpClass], rax; lpClass
0x1800a8772  mov     [rsp+260h+lpReserved], rax; lpReserved
0x1800a8777  call    cs:__imp_RegEnumKeyExW
0x1800a877d  mov     ebx, eax
0x1800a877f  test    eax, eax
0x1800a8781  jle     short loc_1800A878C
0x1800a8783  movzx   ebx, ax
0x1800a8786  or      ebx, 80070000h
0x1800a878c  cmp     ebx, 800700EAh
0x1800a8792  jz      loc_1800A8B29
0x1800a8798  cmp     ebx, 80070103h
0x1800a879e  jz      loc_1800A8E76
0x1800a87a4  mov     r8d, 7A1h; int
0x1800a87aa  lea     rdx, aEnumsoftwaremf; "EnumSoftwareMFTsBase"
0x1800a87b1  lea     rcx, [rsp+260h+var_220]; this
0x1800a87b6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a87bb  test    ebx, ebx
0x1800a87bd  js      loc_1800A8DCC
0x1800a87c3  lea     rdx, [rbp+160h+rguid]; struct _GUID *
0x1800a87c7  lea     rcx, [rbp+160h+Name]; unsigned __int16 *
0x1800a87ce  call    ?GUIDFromString@@YAJPEAGPEAU_GUID@@@Z; GUIDFromString(ushort *,_GUID *)
0x1800a87d3  xor     ebx, ebx
0x1800a87d5  test    eax, eax
0x1800a87d7  js      loc_1800A8B1F
0x1800a87dd  movaps  xmm0, xmmword ptr [rbp+160h+rguid.Data1]
0x1800a87e1  lea     r8, [rsp+260h+var_200]; HKEY *
0x1800a87e6  lea     rdx, [rbp+160h+var_1A0]; struct _GUID
0x1800a87ea  movdqa  xmmword ptr [rbp+160h+var_1A0.Data1], xmm0
0x1800a87ef  mov     rcx, r13; hKey
0x1800a87f2  call    ?OpenMFTKey@@YAJPEAUHKEY__@@U_GUID@@PEAPEAU1@@Z; OpenMFTKey(HKEY__ *,_GUID,HKEY__ * *)
0x1800a87f7  test    eax, eax
0x1800a87f9  jns     short loc_1800A8805
0x1800a87fb  mov     [rsp+260h+var_200], rbx
0x1800a8800  jmp     loc_1800A8B1F
0x1800a8805  mov     rcx, [rsp+260h+var_200]; hKey
0x1800a880a  lea     rax, [rsp+260h+cbData]
0x1800a880f  mov     [rsp+260h+lpClass], rax; lpcbData
0x1800a8814  lea     rdx, aMftflags; "MFTFlags"
0x1800a881b  lea     rax, [rsp+260h+Data]
0x1800a8820  mov     [rsp+260h+cbData], 4
0x1800a8828  xor     r9d, r9d; lpType
0x1800a882b  mov     [rsp+260h+lpReserved], rax; lpData
0x1800a8830  xor     r8d, r8d; lpReserved
0x1800a8833  mov     dword ptr [rsp+260h+Data], ebx
0x1800a8837  call    cs:__imp_RegQueryValueExW
0x1800a883d  test    eax, eax
0x1800a883f  jle     short loc_1800A884B
0x1800a8841  movzx   eax, ax
0x1800a8844  or      eax, 80070000h
0x1800a8849  test    eax, eax
0x1800a884b  js      short loc_1800A885E
0x1800a884d  cmp     [rsp+260h+cbData], 4
0x1800a8852  jnz     loc_1800A8B1F
0x1800a8858  mov     edx, dword ptr [rsp+260h+Data]
0x1800a885c  jmp     short loc_1800A8874
0x1800a885e  cmp     eax, 80070002h
0x1800a8863  jnz     loc_1800A8B1F
0x1800a8869  mov     edx, dword ptr [rsp+260h+Data]
0x1800a886d  or      edx, 1
0x1800a8870  mov     dword ptr [rsp+260h+Data], edx
0x1800a8874  mov     rax, [rsp+260h+var_200]
0x1800a8879  xorps   xmm0, xmm0
0x1800a887c  mov     [rbp+160h+var_1D8], rax
0x1800a8880  mov     eax, r14d
0x1800a8883  not     eax
0x1800a8885  mov     [rbp+160h+var_1D0], bx
0x1800a8889  and     eax, edx
0x1800a888b  mov     [rbp+160h+var_1CC], rbx
0x1800a888f  test    al, 3Ch
0x1800a8891  mov     [rbp+160h+ppMFAttributes], rbx
0x1800a8895  movdqu  xmmword ptr [rbp+160h+pv], xmm0
0x1800a889a  setz    cl
0x1800a889d  and     edx, r14d
0x1800a88a0  test    dl, 7
0x1800a88a3  setnz   al
0x1800a88a6  test    al, cl
0x1800a88a8  jz      loc_1800A8B06
0x1800a88ae  mov     r8, [rbp+160h+var_188]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x1800a88b2  lea     rax, [rsp+260h+ppActivate]
0x1800a88b7  mov     rdx, [rbp+160h+var_180]; struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *
0x1800a88bb  lea     rcx, [rbp+160h+var_1D8]; struct CMFTRegistrationInfo *
0x1800a88bf  mov     [rsp+260h+lpReserved], rax; int *
0x1800a88c4  call    ?CheckForMFTMatch@@YAJPEAVCMFTRegistrationInfo@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAUIMFAttributes@@PEAH@Z; CheckForMFTMatch(CMFTRegistrationInfo *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFAttributes *,int *)
0x1800a88c9  test    eax, eax
0x1800a88cb  jns     short loc_1800A88E0
0x1800a88cd  mov     rcx, [rbp+160h+pv]; pv
0x1800a88d1  call    cs:__imp_CoTaskMemFree
0x1800a88d7  mov     rcx, [rbp+160h+pv+8]
0x1800a88db  jmp     loc_1800A8B10
0x1800a88e0  mov     r14, [rbp+160h+ppMFAttributes]
0x1800a88e4  mov     qword ptr [rbp+160h+var_1A0.Data1], rbx
0x1800a88e8  test    r14, r14
0x1800a88eb  jnz     short loc_1800A891E
0x1800a88ed  xor     edx, edx; cInitialSize
0x1800a88ef  lea     rcx, [rbp+160h+ppMFAttributes]; ppMFAttributes
0x1800a88f3  call    MFCreateAttributes
0x1800a88f8  mov     ebx, eax
0x1800a88fa  test    eax, eax
0x1800a88fc  js      loc_1800A8B35
0x1800a8902  mov     r14, [rbp+160h+ppMFAttributes]
0x1800a8906  mov     rcx, [rbp+160h+var_1D8]; hKey
0x1800a890a  mov     rdx, r14; pAttributes
0x1800a890d  call    ?GetAttributesFromRegistry@@YAJPEAUHKEY__@@PEAUIMFAttributes@@@Z; GetAttributesFromRegistry(HKEY__ *,IMFAttributes *)
0x1800a8912  mov     ebx, eax
0x1800a8914  test    eax, eax
0x1800a8916  js      loc_1800A8B35
0x1800a891c  xor     ebx, ebx
0x1800a891e  mov     rax, [r14]
0x1800a8921  mov     rcx, r14
0x1800a8924  mov     qword ptr [rbp+160h+var_1A0.Data1], r14
0x1800a8928  mov     rax, [rax+8]
0x1800a892c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8931  mov     rax, [r14]
0x1800a8934  lea     r8, [rsp+260h+cbData]
0x1800a8939  lea     rdx, MFT_CODEC_MERIT_Attribute
0x1800a8940  mov     [rsp+260h+cbData], ebx
0x1800a8944  mov     rcx, r14
0x1800a8947  mov     rax, [rax+38h]
0x1800a894b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8950  test    eax, eax
0x1800a8952  js      short loc_1800A8958
0x1800a8954  mov     ebx, [rsp+260h+cbData]
0x1800a8958  test    ebx, ebx
0x1800a895a  jz      short loc_1800A89A4
0x1800a895c  mov     eax, [rsp+260h+var_218]
0x1800a8960  test    al, 4
0x1800a8962  jnz     short loc_1800A89A4
0x1800a8964  mov     rax, [r14]
0x1800a8967  mov     rcx, r14
0x1800a896a  mov     rax, [rax+10h]
0x1800a896e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8973  mov     rcx, [rbp+160h+pv]; pv
0x1800a8977  call    cs:__imp_CoTaskMemFree
0x1800a897d  mov     rcx, [rbp+160h+pv+8]; pv
0x1800a8981  call    cs:__imp_CoTaskMemFree
0x1800a8987  lea     rcx, [rbp+160h+ppMFAttributes]; void *
0x1800a898b  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800a8990  lea     rcx, [rsp+260h+var_220]; this
0x1800a8995  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a899a  mov     r14d, [rsp+260h+var_218]
0x1800a899f  jmp     loc_1800A8B29
0x1800a89a4  mov     rcx, gs:58h
0x1800a89ad  mov     eax, cs:_tls_index
0x1800a89b3  mov     edx, 4
0x1800a89b8  mov     rax, [rcx+rax*8]
0x1800a89bc  mov     ecx, [rdx+rax]
0x1800a89bf  cmp     cs:dword_1801FDA20, ecx
0x1800a89c5  jle     short loc_1800A89F3
0x1800a89c7  lea     rcx, dword_1801FDA20
0x1800a89ce  call    _Init_thread_header
0x1800a89d3  cmp     cs:dword_1801FDA20, 0FFFFFFFFh
0x1800a89da  jnz     short loc_1800A89F3
0x1800a89dc  call    ?IsWindowsToGo@@YA_NXZ; IsWindowsToGo(void)
0x1800a89e1  lea     rcx, dword_1801FDA20
0x1800a89e8  mov     cs:byte_1801FDAE0, al
0x1800a89ee  call    _Init_thread_footer
0x1800a89f3  cmp     cs:byte_1801FDAE0, 0
0x1800a89fa  jz      short loc_1800A8A28
0x1800a89fc  test    [rsp+260h+var_218], 10000h
0x1800a8a04  jnz     short loc_1800A8A28
0x1800a8a06  test    [rsp+260h+Data], 4
0x1800a8a0b  jnz     short loc_1800A8A11
0x1800a8a0d  test    ebx, ebx
0x1800a8a0f  jz      short loc_1800A8A28
0x1800a8a11  lea     rcx, [rbp+160h+var_1A0]; void *
0x1800a8a15  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800a8a1a  lea     rcx, [rbp+160h+var_1D8]; this
0x1800a8a1e  call    ??1CMFTRegistrationInfo@@QEAA@XZ; CMFTRegistrationInfo::~CMFTRegistrationInfo(void)
0x1800a8a23  jmp     loc_1800A8990
0x1800a8a28  cmp     dword ptr [rsp+260h+ppActivate], 0
0x1800a8a2d  jz      loc_1800A8AF8
0x1800a8a33  xor     esi, esi
0x1800a8a35  lea     rcx, [rsp+260h+ppActivate]; ppActivate
0x1800a8a3a  mov     [rsp+260h+ppActivate], rsi
0x1800a8a3f  call    MFCreateTransformActivate
0x1800a8a44  mov     ebx, eax
0x1800a8a46  test    eax, eax
0x1800a8a48  js      loc_1800A8D40
0x1800a8a4e  mov     ecx, [r15]
0x1800a8a51  lea     eax, [rsi+8]
0x1800a8a54  mov     r9, [rsp+260h+var_210]
0x1800a8a59  inc     ecx; void *
0x1800a8a5b  mul     rcx
0x1800a8a5e  mov     r8, [r9]; void *
0x1800a8a61  mov     [r9], rsi
0x1800a8a64  mov     qword ptr [rsp+260h+cbData], rsi
0x1800a8a69  test    rdx, rdx
0x1800a8a6c  jnz     loc_1800A8CA9
0x1800a8a72  mov     [rsp+260h+lpReserved], r9; void **
0x1800a8a77  mov     r9, rax; unsigned __int64
0x1800a8a7a  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1800a8a7f  mov     ebx, eax
0x1800a8a81  mov     esi, eax
0x1800a8a83  test    eax, eax
0x1800a8a85  js      loc_1800A8CB0
0x1800a8a8b  mov     rax, [rbp+160h+var_178]
0x1800a8a8f  lea     r9, [rbp+160h+rguid]; struct _GUID *
0x1800a8a93  mov     rsi, [rsp+260h+ppActivate]
0x1800a8a98  lea     rcx, [rbp+160h+var_1D8]; struct CMFTRegistrationInfo *
0x1800a8a9c  mov     r8d, dword ptr [rsp+260h+Data]; unsigned int
0x1800a8aa1  mov     rdx, rsi; struct IMFActivate *
0x1800a8aa4  mov     [rsp+260h+lpClass], rax; unsigned __int16 *
0x1800a8aa9  mov     [rsp+260h+lpReserved], r12; struct _GUID *
0x1800a8aae  call    ?SetSwTransformActivateAttributes@@YAJPEAVCMFTRegistrationInfo@@PEAUIMFActivate@@IAEBU_GUID@@2PEAG@Z; SetSwTransformActivateAttributes(CMFTRegistrationInfo *,IMFActivate *,uint,_GUID const &,_GUID const &,ushort *)
0x1800a8ab3  mov     ebx, eax
0x1800a8ab5  test    eax, eax
0x1800a8ab7  js      loc_1800A8BF9
0x1800a8abd  mov     ecx, [r15]
0x1800a8ac0  mov     rax, [rsp+260h+var_210]
0x1800a8ac5  mov     rax, [rax]
0x1800a8ac8  mov     [rax+rcx*8], rsi
0x1800a8acc  inc     dword ptr [r15]
0x1800a8acf  test    cs:Microsoft_Windows_MediaFoundation_PlatformEnableBits, 2
0x1800a8ad6  jz      short loc_1800A8AF4
0x1800a8ad8  lea     rdx, [rbp+160h+rguid]; rguid
0x1800a8adc  lea     rcx, [rbp+160h+var_160]; this
0x1800a8ae0  call    ??0CMFEventTraceClassName@@QEAA@AEBU_GUID@@@Z; CMFEventTraceClassName::CMFEventTraceClassName(_GUID const &)
0x1800a8ae5  mov     r8, rax
0x1800a8ae8  lea     rdx, FoundSoftwareMFTEventDesc
0x1800a8aef  call    McTemplateU0z_EventWriteTransfer
0x1800a8af4  mov     esi, [rsp+260h+var_1F8]
0x1800a8af8  test    r14, r14
0x1800a8afb  jnz     loc_1800A8964
0x1800a8b01  jmp     loc_1800A8973
  ... truncated ...
```
