# CONFIG_APPHOST::Initialize(void)

- ea: `0x18005a530`
- end: `0x18005a763`
- name: `?Initialize@CONFIG_APPHOST@@UEAAJXZ`
- size: `563`
- prototype: `__int64 __fastcall(CONFIG_APPHOST *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180042180`
- `0x180042250`
- `0x18005a530`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a585`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a585`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a545`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a545`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a750`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a750`
- `iisutil!PuDbgPrintError` at `0x18005a5c9`
- `iisutil!PuDbgPrintError` at `0x18005a5c9`
- `nativerd!CreateNativeConfigurationSystem` at `0x18005a6ba`
- `nativerd!CreateNativeConfigurationSystem` at `0x18005a6ba`

## string_xrefs

- `0x18005a53e`: `%systemdrive%\inetpub\temp\apppools`
- `0x18005a6cf`: `Creating config interface failed\n`
- `0x18005a5b2`: `CONFIG_APPHOST::Initialize`
- `0x18005a5be`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_apphost.cxx`
- `0x18005a66f`: `Setting TempFilePath on IAppHostProvider failed\n`

## pseudocode

```c
__int64 __fastcall CONFIG_APPHOST::Initialize(LPVOID *this)
{
  _QWORD *v2; // rbx
  OLECHAR *v3; // r14
  HRESULT Instance; // edi
  struct INativeConfigurationSystem **v5; // rsi
  LPVOID v6; // rcx

  v2 = this + 5;
  v3 = SysAllocString(L"%systemdrive%\\inetpub\\temp\\apppools");
  if ( *((_DWORD *)g_pWebAdminService + 412) )
  {
    Instance = -2147467259;
  }
  else
  {
    Instance = CoCreateInstance(
                 &GUID_0019ca4f_5c41_4fe4_bda7_8adfe5115e11,
                 0,
                 1u,
                 &GUID_81d9b25e_5ba5_4166_a69f_3f09a0fc3c65,
                 this + 5);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v2 + 192LL))(*v2, 0xFFFFFFFFLL);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v2 + 208LL))(*v2, 2);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(*(_QWORD *)*v2 + 224LL))(*v2, v3);
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 56LL))(*v2);
            if ( Instance >= 0 )
            {
              v5 = (struct INativeConfigurationSystem **)(this + 6);
              Instance = CreateNativeConfigurationSystem(0, (struct INativeConfigurationSystem **)this + 6);
              if ( Instance >= 0 )
              {
                Instance = CONFIG_CS_PATH_MAPPER::SetConfigPathMapper(*v5, 0);
                if ( Instance >= 0 )
                {
                  Instance = CONFIG_CS_PATH_MAPPER::SetConfigFileMappings(
                               *v5,
                               *((const unsigned __int16 **)g_pWebAdminService + 211),
                               0);
                  if ( Instance >= 0 )
                    goto LABEL_28;
                }
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
                  164,
                  "CONFIG_APPHOST::Initialize",
                  Instance,
                  "Creating config interface failed\n");
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
                152,
                "CONFIG_APPHOST::Initialize",
                Instance,
                "Initializing IAppHostProvider failed\n");
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
              140,
              "CONFIG_APPHOST::Initialize",
              Instance,
              "Setting TempFilePath on IAppHostProvider failed\n");
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
            128,
            "CONFIG_APPHOST::Initialize",
            Instance,
            "Setting LoadOptions on IAppHostProvider failed\n");
        }
      }
      else if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
          116,
          "CONFIG_APPHOST::Initialize",
          Instance,
          "Setting ExpandEnvironmentVariables on IAppHostProvider failed\n");
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_apphost.cxx",
        104,
        "CONFIG_APPHOST::Initialize",
        Instance,
        "Creating IAppHostProvider failed\n");
    }
  }
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  v6 = this[6];
  if ( v6 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    this[6] = 0;
  }
LABEL_28:
  if ( v3 )
    SysFreeString(v3);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18005a530  push    rbx
0x18005a532  push    rbp
0x18005a533  push    rsi
0x18005a534  push    rdi
0x18005a535  push    r14
0x18005a537  sub     rsp, 30h
0x18005a53b  mov     rbp, rcx
0x18005a53e  lea     rcx, aSystemdriveIne; "%systemdrive%\\inetpub\\temp\\apppools"
0x18005a545  call    cs:__imp_SysAllocString
0x18005a54b  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18005a552  lea     rbx, [rbp+28h]
0x18005a556  mov     r14, rax
0x18005a559  cmp     dword ptr [rdx+670h], 0
0x18005a560  jz      short loc_18005A56C
0x18005a562  mov     edi, 80004005h
0x18005a567  jmp     loc_18005A710
0x18005a56c  xor     edx, edx; pUnkOuter
0x18005a56e  mov     [rsp+58h+ppv], rbx; ppv
0x18005a573  lea     r9, _GUID_81d9b25e_5ba5_4166_a69f_3f09a0fc3c65; riid
0x18005a57a  lea     rcx, _GUID_0019ca4f_5c41_4fe4_bda7_8adfe5115e11; rclsid
0x18005a581  lea     r8d, [rdx+1]; dwClsContext
0x18005a585  call    cs:__imp_CoCreateInstance
0x18005a58b  mov     edi, eax
0x18005a58d  test    eax, eax
0x18005a58f  jns     short loc_18005A5D4
0x18005a591  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005a598  jz      loc_18005A710
0x18005a59e  lea     rax, aCreatingIappho; "Creating IAppHostProvider failed\n"
0x18005a5a5  mov     r8d, 68h ; 'h'
0x18005a5ab  mov     rcx, cs:g_pDebug
0x18005a5b2  lea     r9, aConfigApphostI; "CONFIG_APPHOST::Initialize"
0x18005a5b9  mov     [rsp+58h+var_30], rax
0x18005a5be  lea     rdx, aServercommonIn_11; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005a5c5  mov     dword ptr [rsp+58h+ppv], edi
0x18005a5c9  call    cs:__imp_PuDbgPrintError
0x18005a5cf  jmp     loc_18005A710
0x18005a5d4  mov     rcx, [rbx]
0x18005a5d7  or      edx, 0FFFFFFFFh
0x18005a5da  mov     rax, [rcx]
0x18005a5dd  mov     rax, [rax+0C0h]
0x18005a5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5e9  mov     edi, eax
0x18005a5eb  test    eax, eax
0x18005a5ed  jns     short loc_18005A60B
0x18005a5ef  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005a5f6  jz      loc_18005A710
0x18005a5fc  lea     rax, aSettingExpande; "Setting ExpandEnvironmentVariables on I"...
0x18005a603  mov     r8d, 74h ; 't'
0x18005a609  jmp     short loc_18005A5AB
0x18005a60b  mov     rcx, [rbx]
0x18005a60e  mov     edx, 2
0x18005a613  mov     rax, [rcx]
0x18005a616  mov     rax, [rax+0D0h]
0x18005a61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a622  mov     edi, eax
0x18005a624  test    eax, eax
0x18005a626  jns     short loc_18005A647
0x18005a628  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005a62f  jz      loc_18005A710
0x18005a635  lea     rax, aSettingLoadopt; "Setting LoadOptions on IAppHostProvider"...
0x18005a63c  mov     r8d, 80h
0x18005a642  jmp     loc_18005A5AB
0x18005a647  mov     rcx, [rbx]
0x18005a64a  mov     rdx, r14
0x18005a64d  mov     rax, [rcx]
0x18005a650  mov     rax, [rax+0E0h]
0x18005a657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a65c  mov     edi, eax
0x18005a65e  test    eax, eax
0x18005a660  jns     short loc_18005A681
0x18005a662  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005a669  jz      loc_18005A710
0x18005a66f  lea     rax, aSettingTempfil; "Setting TempFilePath on IAppHostProvide"...
0x18005a676  mov     r8d, 8Ch
0x18005a67c  jmp     loc_18005A5AB
0x18005a681  mov     rcx, [rbx]
0x18005a684  mov     rax, [rcx]
0x18005a687  mov     rax, [rax+38h]
0x18005a68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a690  mov     edi, eax
0x18005a692  test    eax, eax
0x18005a694  jns     short loc_18005A6B1
0x18005a696  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005a69d  jz      short loc_18005A710
0x18005a69f  lea     rax, aInitializingIa; "Initializing IAppHostProvider failed\n"
0x18005a6a6  mov     r8d, 98h
0x18005a6ac  jmp     loc_18005A5AB
0x18005a6b1  lea     rsi, [rbp+30h]
0x18005a6b5  xor     ecx, ecx
0x18005a6b7  mov     rdx, rsi
0x18005a6ba  call    cs:__imp_?CreateNativeConfigurationSystem@@YAJPEBGPEAPEAVINativeConfigurationSystem@@@Z; CreateNativeConfigurationSystem(ushort const *,INativeConfigurationSystem * *)
0x18005a6c0  mov     edi, eax
0x18005a6c2  test    eax, eax
0x18005a6c4  jns     short loc_18005A6E1
0x18005a6c6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005a6cd  jz      short loc_18005A710
0x18005a6cf  lea     rax, aCreatingConfig_0; "Creating config interface failed\n"
0x18005a6d6  mov     r8d, 0A4h
0x18005a6dc  jmp     loc_18005A5AB
0x18005a6e1  mov     rcx, [rsi]; struct INativeConfigurationSystem *
0x18005a6e4  xor     edx, edx; int
0x18005a6e6  call    ?SetConfigPathMapper@CONFIG_CS_PATH_MAPPER@@SAJPEAVINativeConfigurationSystem@@H@Z; CONFIG_CS_PATH_MAPPER::SetConfigPathMapper(INativeConfigurationSystem *,int)
0x18005a6eb  mov     edi, eax
0x18005a6ed  test    eax, eax
0x18005a6ef  js      short loc_18005A710
0x18005a6f1  mov     rdx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18005a6f8  xor     r8d, r8d; unsigned __int16 *
0x18005a6fb  mov     rcx, [rsi]; struct INativeConfigurationSystem *
0x18005a6fe  mov     rdx, [rdx+698h]; unsigned __int16 *
0x18005a705  call    ?SetConfigFileMappings@CONFIG_CS_PATH_MAPPER@@SAJPEAVINativeConfigurationSystem@@PEBG1@Z; CONFIG_CS_PATH_MAPPER::SetConfigFileMappings(INativeConfigurationSystem *,ushort const *,ushort const *)
0x18005a70a  mov     edi, eax
0x18005a70c  test    eax, eax
0x18005a70e  jns     short loc_18005A748
0x18005a710  mov     rcx, [rbx]
0x18005a713  test    rcx, rcx
0x18005a716  jz      short loc_18005A72B
0x18005a718  mov     rax, [rcx]
0x18005a71b  mov     rax, [rax+10h]
0x18005a71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a724  mov     qword ptr [rbx], 0
0x18005a72b  mov     rcx, [rbp+30h]
0x18005a72f  test    rcx, rcx
0x18005a732  jz      short loc_18005A748
0x18005a734  mov     rax, [rcx]
0x18005a737  mov     rax, [rax+10h]
0x18005a73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a740  mov     qword ptr [rbp+30h], 0
0x18005a748  test    r14, r14
0x18005a74b  jz      short loc_18005A756
0x18005a74d  mov     rcx, r14; bstrString
0x18005a750  call    cs:__imp_SysFreeString
0x18005a756  mov     eax, edi
0x18005a758  add     rsp, 30h
0x18005a75c  pop     r14
0x18005a75e  pop     rdi
0x18005a75f  pop     rsi
0x18005a760  pop     rbp
0x18005a761  pop     rbx
0x18005a762  retn
```
