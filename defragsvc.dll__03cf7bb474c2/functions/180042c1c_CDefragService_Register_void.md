# CDefragService::Register(void)

- ea: `0x180042c1c`
- end: `0x180043084`
- name: `?Register@CDefragService@@QEAAJXZ`
- size: `1128`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a710`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x18001a630`
- `0x18002b114`
- `0x180042c1c`
- `0x180049358`
- `0x180049fdc`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d80`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180042d9d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180042d9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042ebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042f72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042ebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042f72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004301a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004301a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042f34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042fb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042f34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042fb8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180042de3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180042de3`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x180042d61`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x180042d61`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042cd1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180042cd1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042d72`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004303e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043051`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042d72`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004303e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180043051`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180042e23`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x180042e23`

## string_xrefs

- `0x180042f59`: `System\CurrentControlSet\Services\DEFRAGSVC\Parameters`
- `0x180042f92`: `ServiceDll`
- `0x180042fa1`: `%Systemroot%\System32\defragsvc.dll`
- `0x180042c4d`: `CDefragService::Register`
- `0x180042d35`: `%SystemRoot%\System32\svchost.exe -k DEFRAGSVC`

## pseudocode

```c
__int64 __fastcall CDefragService::Register(CDefragService *this)
{
  SC_HANDLE v1; // rbx
  __int16 v2; // ax
  SC_HANDLE v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int i; // esi
  SC_HANDLE ServiceW; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  int v22; // edx
  ATL::CComModule *v23; // rcx
  const struct _GUID *v24; // r8
  int v25; // eax
  bool v26; // sf
  const BYTE *v27; // rcx
  int v28; // r8d
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  unsigned int v34; // esi
  int StringResource; // [rsp+70h] [rbp-90h] BYREF
  __int16 v37; // [rsp+74h] [rbp-8Ch]
  __int16 v38; // [rsp+76h] [rbp-8Ah]
  HKEY phkResult; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR *Info; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpDisplayName[2]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v44[206]; // [rsp+D2h] [rbp-2Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&StringResource, "CDefragService::Register", 617, 1);
  Buffer = 0;
  v1 = 0;
  memset_0(v44, 0, 0xC6u);
  lpDisplayName[0] = &qword_18006F470;
  Info = 0;
  phkResult = 0;
  hKey = 0;
  lpDisplayName[1] = 0;
  StringResource = CBsString::LoadStringResource((CBsString *)lpDisplayName, hInstance, 0x65u);
  v2 = 633;
  if ( StringResource >= 0 )
  {
    v37 = 633;
    v3 = OpenSCManagerW(0, 0, 2u);
    if ( v3 )
    {
      StringResource = 0;
      v37 = 637;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0x3C )
        {
          StringResource = GetLastFailureAsHRESULT(v5, v4, v6, v7);
          v2 = 669;
          goto LABEL_35;
        }
        ServiceW = CreateServiceW(
                     v3,
                     L"DEFRAGSVC",
                     lpDisplayName[0],
                     2u,
                     0x10u,
                     3u,
                     1u,
                     L"%SystemRoot%\\System32\\svchost.exe -k DEFRAGSVC",
                     0,
                     0,
                     L"RPCSS",
                     0,
                     &Password);
        v1 = ServiceW;
        if ( ServiceW )
          break;
        if ( GetLastError() != 1072 )
        {
          StringResource = GetLastFailureAsHRESULT(v11, v10, v12, v13);
          v38 = 664;
          goto LABEL_36;
        }
        StringResource = 0;
        v37 = 664;
        Sleep(0x1388u);
      }
      StringResource = 0;
      v37 = 669;
      if ( !LoadStringW(hInstance, 0x66u, &Buffer, 100) )
      {
        StringResource = GetLastFailureAsHRESULT(v15, v14, v16, v17);
        v2 = 671;
        goto LABEL_35;
      }
      StringResource = 0;
      v37 = 671;
      Info = &Buffer;
      if ( !ChangeServiceConfig2W(ServiceW, 1u, &Info) )
      {
        StringResource = GetLastFailureAsHRESULT(v19, v18, v20, v21);
        v2 = 675;
        goto LABEL_35;
      }
      StringResource = 0;
      v37 = 675;
      StringResource = ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x64u, 1, 0);
      v2 = 678;
      if ( StringResource >= 0 )
      {
        v37 = 678;
        StringResource = ATL::CComModule::RegisterServer(v23, v22, v24);
        v2 = 685;
        if ( StringResource >= 0 )
        {
          v37 = 685;
          v25 = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SvcHost",
                  0,
                  2u,
                  &phkResult);
          if ( v25 > 0 )
            v25 = (unsigned __int16)v25 | 0x80070000;
          StringResource = v25;
          v26 = v25 < 0;
          v2 = 692;
          if ( !v26 )
          {
            v37 = 692;
            v27 = L"DEFRAGSVC";
            v28 = 0;
            do
            {
              v29 = -1;
              do
                ++v29;
              while ( *(_WORD *)&v27[2 * v29] );
              v30 = (unsigned int)(v29 + 1);
              v28 += v30;
              v27 += 2 * v30;
            }
            while ( *(_WORD *)v27 );
            v31 = RegSetValueExW(phkResult, L"DEFRAGSVC", 0, 7u, L"DEFRAGSVC", 2 * v28 + 2);
            if ( v31 > 0 )
              v31 = (unsigned __int16)v31 | 0x80070000;
            StringResource = v31;
            v26 = v31 < 0;
            v2 = 707;
            if ( !v26 )
            {
              v37 = 707;
              v32 = RegOpenKeyExW(
                      HKEY_LOCAL_MACHINE,
                      L"System\\CurrentControlSet\\Services\\DEFRAGSVC\\Parameters",
                      0,
                      2u,
                      &hKey);
              if ( v32 > 0 )
                v32 = (unsigned __int16)v32 | 0x80070000;
              StringResource = v32;
              v26 = v32 < 0;
              v2 = 716;
              if ( !v26 )
              {
                v37 = 716;
                v33 = RegSetValueExW(hKey, L"ServiceDll", 0, 2u, L"%Systemroot%\\System32\\defragsvc.dll", 0x48u);
                if ( v33 > 0 )
                  v33 = (unsigned __int16)v33 | 0x80070000;
                StringResource = v33;
                v26 = v33 < 0;
                v2 = 721;
                if ( !v26 )
                {
                  v37 = 721;
                  goto LABEL_36;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      StringResource = GetLastFailureAsHRESULT(v5, v4, v6, v7);
      v2 = 637;
    }
  }
  else
  {
    v3 = 0;
  }
LABEL_35:
  v38 = v2;
LABEL_36:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v34 = StringResource;
  CBsString::_Release((LPVOID *)lpDisplayName);
  if ( (unsigned __int64)v1 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseServiceHandle(v1);
  if ( (unsigned __int64)v3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseServiceHandle(v3);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StringResource);
  return v34;
}

```

## disassembly

```asm
0x180042c1c  push    rbp
0x180042c1e  push    rbx
0x180042c1f  push    rsi
0x180042c20  push    rdi
0x180042c21  push    r12
0x180042c23  push    r14
0x180042c25  push    r15
0x180042c27  lea     rbp, [rsp-0B0h]
0x180042c2f  sub     rsp, 1B0h
0x180042c36  mov     rax, cs:__security_cookie
0x180042c3d  xor     rax, rsp
0x180042c40  mov     [rbp+0E0h+var_40], rax
0x180042c47  mov     r9d, 1; unsigned __int16
0x180042c4d  lea     rdx, aCdefragservice_5; "CDefragService::Register"
0x180042c54  mov     r8d, 269h; unsigned __int16
0x180042c5a  lea     rcx, [rsp+1E0h+var_170]; this
0x180042c5f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180042c64  xor     r15d, r15d
0x180042c67  lea     rcx, [rbp+0E0h+var_10E]; void *
0x180042c6b  xor     edx, edx; Val
0x180042c6d  mov     [rbp+0E0h+Buffer], r15w
0x180042c72  mov     r8d, 0C6h; Size
0x180042c78  mov     ebx, r15d
0x180042c7b  call    memset_0
0x180042c80  mov     rdx, cs:hInstance; hInstance
0x180042c87  lea     rax, qword_18006F470
0x180042c8e  lea     r8d, [r15+65h]; uID
0x180042c92  mov     [rbp+0E0h+lpDisplayName], rax
0x180042c96  lea     rcx, [rbp+0E0h+lpDisplayName]; this
0x180042c9a  mov     [rbp+0E0h+Info], r15
0x180042c9e  mov     [rbp+0E0h+phkResult], r15
0x180042ca2  mov     [rbp+0E0h+hKey], r15
0x180042ca6  mov     [rbp+0E0h+var_118], r15
0x180042caa  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x180042caf  mov     [rsp+1E0h+var_170], eax
0x180042cb3  test    eax, eax
0x180042cb5  mov     eax, 279h
0x180042cba  jns     short loc_180042CC4
0x180042cbc  mov     edi, r15d
0x180042cbf  jmp     loc_180042FF9
0x180042cc4  xor     edx, edx; lpDatabaseName
0x180042cc6  mov     [rsp+1E0h+var_16C], ax
0x180042ccb  xor     ecx, ecx; lpMachineName
0x180042ccd  lea     r8d, [rdx+2]; dwDesiredAccess
0x180042cd1  call    cs:__imp_OpenSCManagerW
0x180042cd7  mov     rdi, rax
0x180042cda  test    rax, rax
0x180042cdd  jz      loc_180042FEB
0x180042ce3  mov     eax, 27Dh
0x180042ce8  mov     [rsp+1E0h+var_170], r15d
0x180042ced  mov     [rsp+1E0h+var_16C], ax
0x180042cf2  mov     esi, r15d
0x180042cf5  lea     r12d, [rax+1Bh]
0x180042cf9  cmp     esi, 3Ch ; '<'
0x180042cfc  jnb     loc_180042FDB
0x180042d02  mov     r8, [rbp+0E0h+lpDisplayName]; lpDisplayName
0x180042d06  lea     rax, Password
0x180042d0d  mov     [rsp+1E0h+lpPassword], rax; lpPassword
0x180042d12  lea     rdx, ?s_wszSvcName@CDefragService@@0QBGB; "DEFRAGSVC"
0x180042d19  mov     [rsp+1E0h+lpServiceStartName], r15; lpServiceStartName
0x180042d1e  lea     rax, ?s_wszSvcDependencies@CDefragService@@0QBGB; "RPCSS"
0x180042d25  mov     [rsp+1E0h+lpDependencies], rax; lpDependencies
0x180042d2a  mov     r9d, 2; dwDesiredAccess
0x180042d30  mov     [rsp+1E0h+lpdwTagId], r15; lpdwTagId
0x180042d35  lea     rax, ?s_wszSvcBinaryPath@CDefragService@@0QBGB; "%SystemRoot%\\System32\\svchost.exe -k "...
0x180042d3c  mov     [rsp+1E0h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x180042d41  mov     rcx, rdi; hSCManager
0x180042d44  mov     [rsp+1E0h+lpBinaryPathName], rax; lpBinaryPathName
0x180042d49  mov     [rsp+1E0h+dwErrorControl], 1; dwErrorControl
0x180042d51  mov     [rsp+1E0h+dwStartType], 3; dwStartType
0x180042d59  mov     [rsp+1E0h+dwServiceType], 10h; dwServiceType
0x180042d61  call    cs:__imp_CreateServiceW
0x180042d67  mov     r14, rax
0x180042d6a  test    rbx, rbx
0x180042d6d  jz      short loc_180042D78
0x180042d6f  mov     rcx, rbx; hSCObject
0x180042d72  call    cs:__imp_CloseServiceHandle
0x180042d78  mov     rbx, r14
0x180042d7b  test    r14, r14
0x180042d7e  jnz     short loc_180042DBE
0x180042d80  call    cs:__imp_GetLastError
0x180042d86  cmp     eax, 430h
0x180042d8b  jnz     short loc_180042DAA
0x180042d8d  mov     ecx, 1388h; dwMilliseconds
0x180042d92  mov     [rsp+1E0h+var_170], r15d
0x180042d97  mov     [rsp+1E0h+var_16C], r12w
0x180042d9d  call    cs:__imp_Sleep
0x180042da3  inc     esi
0x180042da5  jmp     loc_180042CF9
0x180042daa  call    GetLastFailureAsHRESULT
0x180042daf  mov     [rsp+1E0h+var_170], eax
0x180042db3  mov     [rsp+1E0h+var_16A], r12w
0x180042db9  jmp     loc_180042FFE
0x180042dbe  mov     rcx, cs:hInstance; hInstance
0x180042dc5  lea     r8, [rbp+0E0h+Buffer]; lpBuffer
0x180042dc9  mov     esi, 64h ; 'd'
0x180042dce  mov     [rsp+1E0h+var_170], r15d
0x180042dd3  mov     eax, 29Dh
0x180042dd8  mov     r9d, esi; cchBufferMax
0x180042ddb  mov     [rsp+1E0h+var_16C], ax
0x180042de0  lea     edx, [rsi+2]; uID
0x180042de3  call    cs:__imp_LoadStringW
0x180042de9  test    eax, eax
0x180042deb  jnz     short loc_180042E00
0x180042ded  call    GetLastFailureAsHRESULT
0x180042df2  mov     [rsp+1E0h+var_170], eax
0x180042df6  mov     eax, 29Fh
0x180042dfb  jmp     loc_180042FF9
0x180042e00  mov     eax, 29Fh
0x180042e05  mov     [rsp+1E0h+var_170], r15d
0x180042e0a  mov     [rsp+1E0h+var_16C], ax
0x180042e0f  lea     r8, [rbp+0E0h+Info]; lpInfo
0x180042e13  lea     rax, [rbp+0E0h+Buffer]
0x180042e17  mov     edx, 1; dwInfoLevel
0x180042e1c  mov     rcx, rbx; hService
0x180042e1f  mov     [rbp+0E0h+Info], rax
0x180042e23  call    cs:__imp_ChangeServiceConfig2W
0x180042e29  test    eax, eax
0x180042e2b  jnz     short loc_180042E40
0x180042e2d  call    GetLastFailureAsHRESULT
0x180042e32  mov     [rsp+1E0h+var_170], eax
0x180042e36  mov     eax, 2A3h
0x180042e3b  jmp     loc_180042FF9
0x180042e40  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180042e43  mov     [rsp+1E0h+var_170], r15d
0x180042e48  mov     eax, 2A3h
0x180042e4d  lea     rcx, ?_Module@@3VCDefragService@@A; this
0x180042e54  mov     edx, esi; unsigned int
0x180042e56  mov     [rsp+1E0h+var_16C], ax
0x180042e5b  lea     r8d, [r9+1]; int
0x180042e5f  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180042e64  mov     [rsp+1E0h+var_170], eax
0x180042e68  test    eax, eax
0x180042e6a  mov     eax, 2A6h
0x180042e6f  js      loc_180042FF9
0x180042e75  mov     [rsp+1E0h+var_16C], ax
0x180042e7a  call    ?RegisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::RegisterServer(int,_GUID const *)
0x180042e7f  mov     [rsp+1E0h+var_170], eax
0x180042e83  test    eax, eax
0x180042e85  mov     eax, 2ADh
0x180042e8a  js      loc_180042FF9
0x180042e90  mov     [rsp+1E0h+var_16C], ax
0x180042e95  lea     rdx, ?s_wszSvchostKey@CDefragService@@0QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180042e9c  lea     rax, [rbp+0E0h+phkResult]
0x180042ea0  mov     r14d, 2
0x180042ea6  mov     r12, 0FFFFFFFF80000002h
0x180042ead  mov     qword ptr [rsp+1E0h+dwServiceType], rax; phkResult
0x180042eb2  mov     r9d, r14d; samDesired
0x180042eb5  mov     rcx, r12; hKey
0x180042eb8  xor     r8d, r8d; ulOptions
0x180042ebb  call    cs:__imp_RegOpenKeyExW
0x180042ec1  mov     esi, 80070000h
0x180042ec6  test    eax, eax
0x180042ec8  jle     short loc_180042ECF
0x180042eca  movzx   eax, ax
0x180042ecd  or      eax, esi
0x180042ecf  mov     [rsp+1E0h+var_170], eax
0x180042ed3  test    eax, eax
0x180042ed5  mov     eax, 2B4h
0x180042eda  js      loc_180042FF9
0x180042ee0  lea     r9, ?s_wszMultiszSvcName@CDefragService@@0QBGB; "DEFRAGSVC"
0x180042ee7  mov     [rsp+1E0h+var_16C], ax
0x180042eec  mov     rcx, r9
0x180042eef  mov     r8d, r15d
0x180042ef2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042ef6  inc     rax
0x180042ef9  cmp     [rcx+rax*2], r15w
0x180042efe  jnz     short loc_180042EF6
0x180042f00  inc     eax
0x180042f02  add     r8d, eax
0x180042f05  lea     rcx, [rcx+rax*2]
0x180042f09  cmp     [rcx], r15w
0x180042f0d  jnz     short loc_180042EF2
0x180042f0f  mov     rcx, [rbp+0E0h+phkResult]; hKey
0x180042f13  lea     eax, ds:2[r8*2]
0x180042f1b  mov     [rsp+1E0h+dwStartType], eax; cbData
0x180042f1f  lea     rdx, ?s_wszSvcName@CDefragService@@0QBGB; "DEFRAGSVC"
0x180042f26  mov     qword ptr [rsp+1E0h+dwServiceType], r9; lpData
0x180042f2b  xor     r8d, r8d; Reserved
0x180042f2e  mov     r9d, 7; dwType
0x180042f34  call    cs:__imp_RegSetValueExW
0x180042f3a  test    eax, eax
0x180042f3c  jle     short loc_180042F43
0x180042f3e  movzx   eax, ax
0x180042f41  or      eax, esi
0x180042f43  mov     [rsp+1E0h+var_170], eax
0x180042f47  test    eax, eax
0x180042f49  mov     eax, 2C3h
0x180042f4e  js      loc_180042FF9
0x180042f54  mov     [rsp+1E0h+var_16C], ax
0x180042f59  lea     rdx, ?s_wszServiceDllKey@CDefragService@@0QBGB; "System\\CurrentControlSet\\Services\\DE"...
0x180042f60  lea     rax, [rbp+0E0h+hKey]
0x180042f64  mov     r9d, r14d; samDesired
0x180042f67  xor     r8d, r8d; ulOptions
0x180042f6a  mov     qword ptr [rsp+1E0h+dwServiceType], rax; phkResult
0x180042f6f  mov     rcx, r12; hKey
0x180042f72  call    cs:__imp_RegOpenKeyExW
0x180042f78  test    eax, eax
0x180042f7a  jle     short loc_180042F81
0x180042f7c  movzx   eax, ax
0x180042f7f  or      eax, esi
0x180042f81  mov     [rsp+1E0h+var_170], eax
0x180042f85  test    eax, eax
0x180042f87  mov     eax, 2CCh
0x180042f8c  js      short loc_180042FF9
0x180042f8e  mov     rcx, [rbp+0E0h+hKey]; hKey
0x180042f92  lea     rdx, ?s_wszServiceDllValName@CDefragService@@0QBGB; "ServiceDll"
0x180042f99  mov     [rsp+1E0h+var_16C], ax
0x180042f9e  mov     r9d, r14d; dwType
0x180042fa1  lea     rax, ?s_wszServiceDllValue@CDefragService@@0QBGB; "%Systemroot%\\System32\\defragsvc.dll"
0x180042fa8  mov     [rsp+1E0h+dwStartType], 48h ; 'H'; cbData
0x180042fb0  xor     r8d, r8d; Reserved
0x180042fb3  mov     qword ptr [rsp+1E0h+dwServiceType], rax; lpData
0x180042fb8  call    cs:__imp_RegSetValueExW
0x180042fbe  test    eax, eax
0x180042fc0  jle     short loc_180042FC7
0x180042fc2  movzx   eax, ax
0x180042fc5  or      eax, esi
0x180042fc7  mov     [rsp+1E0h+var_170], eax
0x180042fcb  test    eax, eax
0x180042fcd  mov     eax, 2D1h
0x180042fd2  js      short loc_180042FF9
0x180042fd4  mov     [rsp+1E0h+var_16C], ax
0x180042fd9  jmp     short loc_180042FFE
0x180042fdb  call    GetLastFailureAsHRESULT
0x180042fe0  mov     [rsp+1E0h+var_170], eax
0x180042fe4  mov     eax, 29Dh
0x180042fe9  jmp     short loc_180042FF9
0x180042feb  call    GetLastFailureAsHRESULT
0x180042ff0  mov     [rsp+1E0h+var_170], eax
0x180042ff4  mov     eax, 27Dh
0x180042ff9  mov     [rsp+1E0h+var_16A], ax
0x180042ffe  mov     rcx, [rbp+0E0h+phkResult]; hKey
0x180043002  test    rcx, rcx
0x180043005  jz      short loc_180043011
0x180043007  call    cs:__imp_RegCloseKey
0x18004300d  mov     [rbp+0E0h+phkResult], r15
0x180043011  mov     rcx, [rbp+0E0h+hKey]; hKey
0x180043015  test    rcx, rcx
0x180043018  jz      short loc_180043024
0x18004301a  call    cs:__imp_RegCloseKey
0x180043020  mov     [rbp+0E0h+hKey], r15
0x180043024  mov     esi, [rsp+1E0h+var_170]
0x180043028  lea     rcx, [rbp+0E0h+lpDisplayName]; this
0x18004302c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180043031  lea     rax, [rbx-1]
0x180043035  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180043039  ja      short loc_180043044
0x18004303b  mov     rcx, rbx; hSCObject
0x18004303e  call    cs:__imp_CloseServiceHandle
0x180043044  lea     rcx, [rdi-1]
0x180043048  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18004304c  ja      short loc_180043057
0x18004304e  mov     rcx, rdi; hSCObject
0x180043051  call    cs:__imp_CloseServiceHandle
0x180043057  lea     rcx, [rsp+1E0h+var_170]; this
0x18004305c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180043061  mov     eax, esi
0x180043063  mov     rcx, [rbp+0E0h+var_40]
0x18004306a  xor     rcx, rsp; StackCookie
0x18004306d  call    __security_check_cookie
0x180043072  add     rsp, 1B0h
0x180043079  pop     r15
0x18004307b  pop     r14
0x18004307d  pop     r12
0x18004307f  pop     rdi
0x180043080  pop     rsi
0x180043081  pop     rbx
0x180043082  pop     rbp
0x180043083  retn
```
