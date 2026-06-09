# CRdpPipeGfxPlugin::Initialize(IUnknown *,int)

- ea: `0x180024390`
- end: `0x180024c4c`
- name: `?Initialize@CRdpPipeGfxPlugin@@UEAAJPEAUIUnknown@@H@Z`
- size: `2236`
- prototype: `__int64 __fastcall(CRdpPipeGfxPlugin *__hidden this, struct IUnknown *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024170`
- `0x180024eb4`

## callees

- `0x1800015f0`
- `0x180002d8c`
- `0x18000bef4`
- `0x180010908`
- `0x18001e49c`
- `0x180024390`
- `0x180033da0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800249f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800249f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800248b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800248b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024c1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024c1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002440b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002440b`

## string_xrefs

- `0x180024458`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x180024516`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x1800245cf`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x180024681`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x180024746`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x1800247ef`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x180024994`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x180024a61`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x180024b99`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18002442d`: `Failed to open regkey`
- `0x180024656`: `Failed to create RDP PipeLine `
- `0x18002471b`: `Failed to create GFX Provider `
- `0x1800247c8`: `Failed to create playback GFX Provider `
- `0x180024b72`: `Failed to read playback file name`
- `0x180024a36`: `Failed CreateEvent call for m_hReadyEvent Event`
- `0x180024afe`: `GfxPlugin`

## pseudocode

```c
__int64 __fastcall CRdpPipeGfxPlugin::Initialize(CRdpPipeGfxPlugin *this, struct IUnknown *a2, int a3)
{
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  signed int Instance; // ebx
  struct IUnknown **v10; // rsi
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  struct IUnknown *v19; // rcx
  _QWORD *v20; // r14
  void **v21; // r9
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int64 *v28; // rdx
  const char **v29; // rax
  const char *v30; // rax
  const char *v31; // rcx
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  const char *v43; // rcx
  const char **v45; // [rsp+30h] [rbp-D0h]
  const char **v46; // [rsp+40h] [rbp-C0h]
  const char **v47; // [rsp+48h] [rbp-B8h]
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+54h] [rbp-ACh] BYREF
  const char *v50; // [rsp+58h] [rbp-A8h] BYREF
  const char *v51; // [rsp+60h] [rbp-A0h] BYREF
  const char *v52; // [rsp+68h] [rbp-98h] BYREF
  const char *v53; // [rsp+70h] [rbp-90h] BYREF
  const char *v54; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  BYTE Data[528]; // [rsp+90h] [rbp-70h] BYREF

  Type = 0;
  cbData = 0;
  hKey = 0;
  CTSCriticalSection::Initialize((CRdpPipeGfxPlugin *)((char *)this + 160));
  *((_DWORD *)this + 13) |= 2u;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0,
         0x20019u,
         &hKey) )
  {
    Instance = -2147418113;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v48 = 139;
      v50 = "Failed to open regkey";
      v49 = -2147418113;
      v51 = "Initialize";
      v52 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v53 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)qword_18019B8D8,
        v7,
        v8,
        (__int64)&v53,
        (__int64)&v49,
        (__int64)&v52,
        (__int64)&v48,
        (__int64)&v51,
        (__int64)&v50);
    }
    goto LABEL_49;
  }
  v10 = (struct IUnknown **)((char *)this + 104);
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_IRDPENCPlatformContext,
               (char *)this + 104);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v49 = 146;
      v53 = "Failed to QI for platformContext";
      v48 = Instance;
      v52 = "Initialize";
      v51 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v50 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)qword_18019B888,
        v11,
        v12,
        (__int64)&v50,
        (__int64)&v48,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&v52,
        (__int64)&v53);
    }
    goto LABEL_49;
  }
  Instance = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, GUID *, char *))(*v10)->lpVtbl[2].QueryInterface)(
               *v10,
               L"RDP::EventLog::Session",
               &IID_IUMRDPGFXPluginCallback,
               (char *)this + 72);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v49 = 151;
      v53 = "Failed to retrieve the event log callback interface";
      v48 = Instance;
      v52 = "Initialize";
      v51 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v50 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)qword_18019B838,
        v14,
        v15,
        (__int64)&v50,
        (__int64)&v48,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&v52,
        (__int64)&v53);
    }
    goto LABEL_49;
  }
  Instance = __RDPAPIDLL__CreateInstance(*v10, &CLSID_RdpGfxPipeManager, &IID_IRdpGfxPipeLine, (void **)this + 10);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v49 = 160;
      v53 = "Failed to create RDP PipeLine ";
      v48 = Instance;
      v52 = "Initialize";
      v51 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v50 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)qword_18019B7E8,
        v17,
        v18,
        (__int64)&v50,
        (__int64)&v48,
        (__int64)&v51,
        (__int64)&v49,
        (__int64)&v52,
        (__int64)&v53);
    }
    goto LABEL_49;
  }
  v19 = *v10;
  v20 = (_QWORD *)((char *)this + 88);
  *((_DWORD *)this + 55) = a3;
  v21 = (void **)((char *)this + 88);
  if ( !a3 )
  {
    Instance = __RDPAPIDLL__CreateInstance(v19, &CLSID_RdpPipeGfxProvider, &IID_IRdpGFXSource, v21);
    if ( Instance < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v49 = 173;
        v53 = "Failed to create GFX Provider ";
        v48 = Instance;
        v52 = "Initialize";
        v51 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
        v50 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)qword_18019B798,
          v23,
          v24,
          (__int64)&v50,
          (__int64)&v48,
          (__int64)&v51,
          (__int64)&v49,
          (__int64)&v52,
          (__int64)&v53);
      }
      goto LABEL_49;
    }
    goto LABEL_31;
  }
  v50 = 0;
  Instance = __RDPAPIDLL__CreateInstance(v19, &CLSID_RdpPlayBackGfxProvider, &IID_IRdpGFXSource, v21);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_47;
    v49 = 187;
    v53 = "Failed to create playback GFX Provider ";
    v28 = qword_18019B748;
    v52 = "Initialize";
    v51 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
    v54 = "Error HResult failed";
    v47 = &v53;
    v46 = &v52;
    v45 = &v51;
    v29 = &v54;
    goto LABEL_46;
  }
  Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, const char **))*v20)(*v20, &IID_IRdpGFXRawFileSource, &v50);
  if ( Instance < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_47;
    v30 = "Failed to QI for IID_IRdpGFXRawFileSource";
    v49 = 193;
    v28 = qword_18019B6F8;
    goto LABEL_45;
  }
  cbData = 520;
  if ( RegQueryValueExW(hKey, L"RDPPlayBackFileName", 0, &Type, Data, &cbData) || Type != 1 )
  {
    Instance = -2147024809;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_47;
    v30 = "Failed to read playback file name";
    v49 = 210;
    v28 = qword_18019B658;
    goto LABEL_45;
  }
  Instance = (*(__int64 (__fastcall **)(const char *, BYTE *, _QWORD))(*(_QWORD *)v50 + 24LL))(v50, Data, 0);
  if ( Instance >= 0 )
  {
    v31 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v31 + 16LL))(v31);
    }
LABEL_31:
    Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v20)(
                 *v20,
                 &IID_IUMRDPGFXProvider,
                 (char *)this + 96);
    if ( Instance >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 22) = EventW;
      if ( EventW )
        goto LABEL_54;
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
      if ( Instance >= 0 )
      {
LABEL_54:
        if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
        {
          v51 = (const char *)0x1000000;
          v54 = (char *)this + 204;
          v53 = "GfxPlugin";
          v52 = "Stack";
          v50 = "Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
            v40,
            (unsigned int)&word_18019B556,
            v41,
            v42,
            (__int64)&v50,
            (__int64)&v51,
            (__int64)&v52,
            (__int64)&v53,
            (__int64)&v54);
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v49 = 224;
        v54 = "Failed CreateEvent call for m_hReadyEvent Event";
        v48 = Instance;
        v53 = "Initialize";
        v52 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
        v51 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v37,
          (unsigned int)qword_18019B5B8,
          v38,
          v39,
          (__int64)&v51,
          (__int64)&v48,
          (__int64)&v52,
          (__int64)&v49,
          (__int64)&v53,
          (__int64)&v54);
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v49 = 218;
      v54 = "Failed to QI for UMRDP Gfx provider ";
      v48 = Instance;
      v53 = "Initialize";
      v52 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v51 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v32,
        (unsigned int)qword_18019B608,
        v33,
        v34,
        (__int64)&v51,
        (__int64)&v48,
        (__int64)&v52,
        (__int64)&v49,
        (__int64)&v53,
        (__int64)&v54);
    }
    goto LABEL_49;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v30 = "Failed to start playback gfx source";
    v49 = 205;
    v28 = qword_18019B6A8;
LABEL_45:
    v54 = v30;
    v53 = "Initialize";
    v52 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
    v51 = "Error HResult failed";
    v47 = &v54;
    v46 = &v53;
    v45 = &v52;
    v29 = &v51;
LABEL_46:
    v48 = Instance;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v25,
      (_DWORD)v28,
      v26,
      v27,
      (__int64)v29,
      (__int64)&v48,
      (__int64)v45,
      (__int64)&v49,
      (__int64)v46,
      (__int64)v47);
  }
LABEL_47:
  v43 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v43 + 16LL))(v43);
  }
LABEL_49:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180024390  mov     [rsp-8+arg_10], rbx
0x180024395  push    rbp
0x180024396  push    rsi
0x180024397  push    rdi
0x180024398  push    r14
0x18002439a  push    r15
0x18002439c  lea     rbp, [rsp-1B0h]
0x1800243a4  sub     rsp, 2B0h
0x1800243ab  mov     rax, cs:__security_cookie
0x1800243b2  xor     rax, rsp
0x1800243b5  mov     [rbp+1D0h+var_30], rax
0x1800243bc  mov     rdi, rcx
0x1800243bf  mov     [rbp+1D0h+Type], 0
0x1800243c6  add     rcx, 0A0h; this
0x1800243cd  mov     [rbp+1D0h+cbData], 0
0x1800243d4  mov     r15d, r8d
0x1800243d7  mov     [rbp+1D0h+hKey], 0
0x1800243df  mov     rbx, rdx
0x1800243e2  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800243e7  or      dword ptr [rdi+34h], 2
0x1800243eb  lea     rax, [rbp+1D0h+hKey]
0x1800243ef  mov     r9d, 20019h; samDesired
0x1800243f5  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800243fa  xor     r8d, r8d; ulOptions
0x1800243fd  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x180024404  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002440b  call    cs:__imp_RegOpenKeyExW
0x180024411  test    eax, eax
0x180024413  jz      loc_1800244B6
0x180024419  mov     eax, cs:dword_1801B76C8
0x18002441f  mov     ebx, 8000FFFFh
0x180024424  cmp     eax, 2
0x180024427  jbe     loc_180024C15
0x18002442d  lea     rax, aFailedToOpenRe; "Failed to open regkey"
0x180024434  mov     [rsp+2D0h+var_280], 8Bh
0x18002443c  mov     [rsp+2D0h+var_278], rax
0x180024441  lea     rdx, qword_18019B8D8
0x180024448  lea     rax, aInitialize; "Initialize"
0x18002444f  mov     [rsp+2D0h+var_27C], ebx
0x180024453  mov     [rsp+2D0h+var_270], rax
0x180024458  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18002445f  mov     [rsp+2D0h+var_268], rax
0x180024464  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18002446b  mov     [rsp+2D0h+var_260], rax
0x180024470  lea     rax, [rsp+2D0h+var_278]
0x180024475  mov     [rsp+2D0h+var_288], rax
0x18002447a  lea     rax, [rsp+2D0h+var_270]
0x18002447f  mov     [rsp+2D0h+var_290], rax
0x180024484  lea     rax, [rsp+2D0h+var_280]
0x180024489  mov     [rsp+2D0h+var_298], rax
0x18002448e  lea     rax, [rsp+2D0h+var_268]
0x180024493  mov     [rsp+2D0h+var_2A0], rax
0x180024498  lea     rax, [rsp+2D0h+var_27C]
0x18002449d  mov     [rsp+2D0h+lpcbData], rax
0x1800244a2  lea     rax, [rsp+2D0h+var_260]
0x1800244a7  mov     [rsp+2D0h+phkResult], rax
0x1800244ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800244b1  jmp     loc_180024C15
0x1800244b6  mov     rax, [rbx]
0x1800244b9  lea     rsi, [rdi+68h]
0x1800244bd  mov     r8, rsi
0x1800244c0  lea     rdx, IID_IRDPENCPlatformContext
0x1800244c7  mov     rcx, rbx
0x1800244ca  mov     rax, [rax]
0x1800244cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244d2  mov     ebx, eax
0x1800244d4  test    eax, eax
0x1800244d6  jns     loc_18002456A
0x1800244dc  mov     ecx, cs:dword_1801B76C8
0x1800244e2  cmp     ecx, 2
0x1800244e5  jbe     loc_180024C15
0x1800244eb  lea     rax, aFailedToQiForP; "Failed to QI for platformContext"
0x1800244f2  mov     [rsp+2D0h+var_27C], 92h
0x1800244fa  mov     [rsp+2D0h+var_260], rax
0x1800244ff  lea     rdx, qword_18019B888
0x180024506  lea     rax, aInitialize; "Initialize"
0x18002450d  mov     [rsp+2D0h+var_280], ebx
0x180024511  mov     [rsp+2D0h+var_268], rax
0x180024516  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18002451d  mov     [rsp+2D0h+var_270], rax
0x180024522  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180024529  mov     [rsp+2D0h+var_278], rax
0x18002452e  lea     rax, [rsp+2D0h+var_260]
0x180024533  mov     [rsp+2D0h+var_288], rax
0x180024538  lea     rax, [rsp+2D0h+var_268]
0x18002453d  mov     [rsp+2D0h+var_290], rax
0x180024542  lea     rax, [rsp+2D0h+var_27C]
0x180024547  mov     [rsp+2D0h+var_298], rax
0x18002454c  lea     rax, [rsp+2D0h+var_270]
0x180024551  mov     [rsp+2D0h+var_2A0], rax
0x180024556  lea     rax, [rsp+2D0h+var_280]
0x18002455b  mov     [rsp+2D0h+lpcbData], rax
0x180024560  lea     rax, [rsp+2D0h+var_278]
0x180024565  jmp     loc_1800244A7
0x18002456a  mov     rcx, [rsi]
0x18002456d  lea     r9, [rdi+48h]
0x180024571  lea     r8, IID_IUMRDPGFXPluginCallback
0x180024578  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x18002457f  mov     rax, [rcx]
0x180024582  mov     rax, [rax+30h]
0x180024586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002458b  mov     ebx, eax
0x18002458d  test    eax, eax
0x18002458f  jns     loc_180024623
0x180024595  mov     eax, cs:dword_1801B76C8
0x18002459b  cmp     eax, 2
0x18002459e  jbe     loc_180024C15
0x1800245a4  lea     rax, aFailedToRetrie_1; "Failed to retrieve the event log callba"...
0x1800245ab  mov     [rsp+2D0h+var_27C], 97h
0x1800245b3  mov     [rsp+2D0h+var_260], rax
0x1800245b8  lea     rdx, qword_18019B838
0x1800245bf  lea     rax, aInitialize; "Initialize"
0x1800245c6  mov     [rsp+2D0h+var_280], ebx
0x1800245ca  mov     [rsp+2D0h+var_268], rax
0x1800245cf  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800245d6  mov     [rsp+2D0h+var_270], rax
0x1800245db  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800245e2  mov     [rsp+2D0h+var_278], rax
0x1800245e7  lea     rax, [rsp+2D0h+var_260]
0x1800245ec  mov     [rsp+2D0h+var_288], rax
0x1800245f1  lea     rax, [rsp+2D0h+var_268]
0x1800245f6  mov     [rsp+2D0h+var_290], rax
0x1800245fb  lea     rax, [rsp+2D0h+var_27C]
0x180024600  mov     [rsp+2D0h+var_298], rax
0x180024605  lea     rax, [rsp+2D0h+var_270]
0x18002460a  mov     [rsp+2D0h+var_2A0], rax
0x18002460f  lea     rax, [rsp+2D0h+var_280]
0x180024614  mov     [rsp+2D0h+lpcbData], rax
0x180024619  lea     rax, [rsp+2D0h+var_278]
0x18002461e  jmp     loc_1800244A7
0x180024623  mov     rcx, [rsi]; struct IUnknown *
0x180024626  lea     r9, [rdi+50h]; void **
0x18002462a  lea     r8, IID_IRdpGfxPipeLine; struct _GUID *
0x180024631  lea     rdx, CLSID_RdpGfxPipeManager; struct _GUID *
0x180024638  call    ?__RDPAPIDLL__CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; __RDPAPIDLL__CreateInstance(IUnknown *,_GUID const &,_GUID const &,void * *)
0x18002463d  mov     ebx, eax
0x18002463f  test    eax, eax
0x180024641  jns     loc_1800246D5
0x180024647  mov     eax, cs:dword_1801B76C8
0x18002464d  cmp     eax, 2
0x180024650  jbe     loc_180024C15
0x180024656  lea     rax, aFailedToCreate_62; "Failed to create RDP PipeLine "
0x18002465d  mov     [rsp+2D0h+var_27C], 0A0h
0x180024665  mov     [rsp+2D0h+var_260], rax
0x18002466a  lea     rdx, qword_18019B7E8
0x180024671  lea     rax, aInitialize; "Initialize"
0x180024678  mov     [rsp+2D0h+var_280], ebx
0x18002467c  mov     [rsp+2D0h+var_268], rax
0x180024681  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180024688  mov     [rsp+2D0h+var_270], rax
0x18002468d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180024694  mov     [rsp+2D0h+var_278], rax
0x180024699  lea     rax, [rsp+2D0h+var_260]
0x18002469e  mov     [rsp+2D0h+var_288], rax
0x1800246a3  lea     rax, [rsp+2D0h+var_268]
0x1800246a8  mov     [rsp+2D0h+var_290], rax
0x1800246ad  lea     rax, [rsp+2D0h+var_27C]
0x1800246b2  mov     [rsp+2D0h+var_298], rax
0x1800246b7  lea     rax, [rsp+2D0h+var_270]
0x1800246bc  mov     [rsp+2D0h+var_2A0], rax
0x1800246c1  lea     rax, [rsp+2D0h+var_280]
0x1800246c6  mov     [rsp+2D0h+lpcbData], rax
0x1800246cb  lea     rax, [rsp+2D0h+var_278]
0x1800246d0  jmp     loc_1800244A7
0x1800246d5  mov     rcx, [rsi]; struct IUnknown *
0x1800246d8  lea     r14, [rdi+58h]
0x1800246dc  mov     [rdi+0DCh], r15d
0x1800246e3  mov     r9, r14; void **
0x1800246e6  lea     r8, IID_IRdpGFXSource; struct _GUID *
0x1800246ed  test    r15d, r15d
0x1800246f0  jnz     loc_18002479A
0x1800246f6  lea     rdx, CLSID_RdpPipeGfxProvider; struct _GUID *
0x1800246fd  call    ?__RDPAPIDLL__CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; __RDPAPIDLL__CreateInstance(IUnknown *,_GUID const &,_GUID const &,void * *)
0x180024702  mov     ebx, eax
0x180024704  test    eax, eax
0x180024706  jns     loc_180024937
0x18002470c  mov     eax, cs:dword_1801B76C8
0x180024712  cmp     eax, 2
0x180024715  jbe     loc_180024C15
0x18002471b  lea     rax, aFailedToCreate_72; "Failed to create GFX Provider "
0x180024722  mov     [rsp+2D0h+var_27C], 0ADh
0x18002472a  mov     [rsp+2D0h+var_260], rax
0x18002472f  lea     rdx, qword_18019B798
0x180024736  lea     rax, aInitialize; "Initialize"
0x18002473d  mov     [rsp+2D0h+var_280], ebx
0x180024741  mov     [rsp+2D0h+var_268], rax
0x180024746  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18002474d  mov     [rsp+2D0h+var_270], rax
0x180024752  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180024759  mov     [rsp+2D0h+var_278], rax
0x18002475e  lea     rax, [rsp+2D0h+var_260]
0x180024763  mov     [rsp+2D0h+var_288], rax
0x180024768  lea     rax, [rsp+2D0h+var_268]
0x18002476d  mov     [rsp+2D0h+var_290], rax
0x180024772  lea     rax, [rsp+2D0h+var_27C]
0x180024777  mov     [rsp+2D0h+var_298], rax
0x18002477c  lea     rax, [rsp+2D0h+var_270]
0x180024781  mov     [rsp+2D0h+var_2A0], rax
0x180024786  lea     rax, [rsp+2D0h+var_280]
0x18002478b  mov     [rsp+2D0h+lpcbData], rax
0x180024790  lea     rax, [rsp+2D0h+var_278]
0x180024795  jmp     loc_1800244A7
0x18002479a  lea     rdx, CLSID_RdpPlayBackGfxProvider; struct _GUID *
0x1800247a1  mov     [rsp+2D0h+var_278], 0
0x1800247aa  call    ?__RDPAPIDLL__CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; __RDPAPIDLL__CreateInstance(IUnknown *,_GUID const &,_GUID const &,void * *)
0x1800247af  mov     ebx, eax
0x1800247b1  test    eax, eax
0x1800247b3  jns     loc_180024843
0x1800247b9  mov     eax, cs:dword_1801B76C8
0x1800247bf  cmp     eax, 2
0x1800247c2  jbe     loc_180024BF6
0x1800247c8  lea     rax, aFailedToCreate_5; "Failed to create playback GFX Provider "
0x1800247cf  mov     [rsp+2D0h+var_27C], 0BBh
0x1800247d7  mov     [rsp+2D0h+var_260], rax
0x1800247dc  lea     rdx, qword_18019B748
0x1800247e3  lea     rax, aInitialize; "Initialize"
0x1800247ea  mov     [rsp+2D0h+var_268], rax
0x1800247ef  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800247f6  mov     [rsp+2D0h+var_270], rax
0x1800247fb  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180024802  mov     [rsp+2D0h+var_258], rax
0x180024807  lea     rax, [rsp+2D0h+var_260]
0x18002480c  mov     [rsp+2D0h+var_288], rax
0x180024811  lea     rax, [rsp+2D0h+var_268]
0x180024816  mov     [rsp+2D0h+var_290], rax
0x18002481b  lea     rax, [rsp+2D0h+var_27C]
0x180024820  mov     [rsp+2D0h+var_298], rax
0x180024825  lea     rax, [rsp+2D0h+var_270]
0x18002482a  mov     [rsp+2D0h+var_2A0], rax
0x18002482f  lea     rax, [rsp+2D0h+var_280]
0x180024834  mov     [rsp+2D0h+lpcbData], rax
0x180024839  lea     rax, [rsp+2D0h+var_258]
0x18002483e  jmp     loc_180024BE8
0x180024843  mov     rcx, [r14]
0x180024846  lea     r8, [rsp+2D0h+var_278]
0x18002484b  lea     rdx, IID_IRdpGFXRawFileSource
0x180024852  mov     rax, [rcx]
0x180024855  mov     rax, [rax]
0x180024858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002485d  mov     ebx, eax
0x18002485f  test    eax, eax
0x180024861  jns     short loc_18002488D
0x180024863  mov     eax, cs:dword_1801B76C8
0x180024869  cmp     eax, 2
0x18002486c  jbe     loc_180024BF6
0x180024872  lea     rax, aFailedToQiForI_3; "Failed to QI for IID_IRdpGFXRawFileSour"...
0x180024879  mov     [rsp+2D0h+var_27C], 0C1h
0x180024881  lea     rdx, qword_18019B6F8
0x180024888  jmp     loc_180024B88
0x18002488d  mov     rcx, [rbp+1D0h+hKey]; hKey
0x180024891  lea     rax, [rbp+1D0h+cbData]
0x180024895  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18002489a  lea     r9, [rbp+1D0h+Type]; lpType
0x18002489e  lea     rax, [rbp+1D0h+Data]
0x1800248a2  mov     [rbp+1D0h+cbData], 208h
0x1800248a9  xor     r8d, r8d; lpReserved
0x1800248ac  mov     [rsp+2D0h+phkResult], rax; lpData
0x1800248b1  lea     rdx, aRdpplaybackfil; "RDPPlayBackFileName"
0x1800248b8  call    cs:__imp_RegQueryValueExW
0x1800248be  test    eax, eax
0x1800248c0  jnz     loc_180024B5E
0x1800248c6  cmp     [rbp+1D0h+Type], 1
0x1800248ca  jnz     loc_180024B5E
0x1800248d0  mov     rcx, [rsp+2D0h+var_278]
0x1800248d5  lea     rdx, [rbp+1D0h+Data]
0x1800248d9  xor     r8d, r8d
0x1800248dc  mov     rax, [rcx]
0x1800248df  mov     rax, [rax+18h]
0x1800248e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248e8  mov     ebx, eax
0x1800248ea  test    eax, eax
0x1800248ec  jns     short loc_180024918
0x1800248ee  mov     eax, cs:dword_1801B76C8
0x1800248f4  cmp     eax, 2
0x1800248f7  jbe     loc_180024BF6
0x1800248fd  lea     rax, aFailedToStartP_1; "Failed to start playback gfx source"
0x180024904  mov     [rsp+2D0h+var_27C], 0CDh
0x18002490c  lea     rdx, qword_18019B6A8
0x180024913  jmp     loc_180024B88
0x180024918  mov     rcx, [rsp+2D0h+var_278]
0x18002491d  test    rcx, rcx
0x180024920  jz      short loc_180024937
0x180024922  mov     [rsp+2D0h+var_278], 0
0x18002492b  mov     rax, [rcx]
0x18002492e  mov     rax, [rax+10h]
0x180024932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024937  mov     rcx, [r14]
0x18002493a  lea     r8, [rdi+60h]
0x18002493e  lea     rdx, IID_IUMRDPGFXProvider
0x180024945  mov     rax, [rcx]
0x180024948  mov     rax, [rax]
0x18002494b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024950  mov     ebx, eax
0x180024952  test    eax, eax
0x180024954  jns     loc_1800249E8
0x18002495a  mov     eax, cs:dword_1801B76C8
0x180024960  cmp     eax, 2
0x180024963  jbe     loc_180024C15
0x180024969  lea     rax, aFailedToQiForU; "Failed to QI for UMRDP Gfx provider "
0x180024970  mov     [rsp+2D0h+var_27C], 0DAh
  ... truncated ...
```
