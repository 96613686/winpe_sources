# CDefragService::Unregister(void)

- ea: `0x180049da4`
- end: `0x180049ed1`
- name: `?Unregister@CDefragService@@QEAAJXZ`
- size: `301`
- prototype: `__int64 __fastcall(CDefragService *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a710`
- `0x18004a7a0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180049da4`
- `0x180049ed8`
- `0x180049fdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049e02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180049e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049e85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049e85`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180049e1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180049e1b`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x180049e72`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x180049e72`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180049e61`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180049e61`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180049e43`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180049e43`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180049e9f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180049ead`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180049e9f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180049ead`

## string_xrefs

- `0x180049db9`: `CDefragService::Unregister`

## pseudocode

```c
__int64 __fastcall CDefragService::Unregister(CDefragService *this)
{
  SC_HANDLE v1; // rbx
  int v2; // edx
  ATL::CComModule *v3; // rcx
  const struct _GUID *v4; // r8
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  SC_HANDLE v7; // rax
  unsigned int v8; // ebx
  _DWORD v10[18]; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v10, "CDefragService::Unregister", 745, 1);
  hKey = 0;
  v1 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\SvcHost", 0, 2u, &hKey) )
    RegDeleteValueW(hKey, L"DEFRAGSVC");
  ATL::CAtlModule::UpdateRegistryFromResourceS((ATL::CAtlModule *)&_Module, 0x64u, 0, 0);
  ATL::CComModule::UnregisterServer(v3, v2, v4);
  v5 = OpenSCManagerW(0, 0, 2u);
  v6 = v5;
  if ( v5 )
  {
    v7 = OpenServiceW(v5, L"DEFRAGSVC", 0x10000u);
    v1 = v7;
    if ( v7 )
      DeleteService(v7);
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v1 )
    CloseServiceHandle(v1);
  if ( v6 )
    CloseServiceHandle(v6);
  v8 = v10[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v10);
  return v8;
}

```

## disassembly

```asm
0x180049da4  mov     [rsp+arg_8], rbx
0x180049da9  mov     [rsp+hKey], rcx
0x180049dae  push    rdi
0x180049daf  sub     rsp, 70h
0x180049db3  mov     r9d, 1; unsigned __int16
0x180049db9  lea     rdx, aCdefragservice_3; "CDefragService::Unregister"
0x180049dc0  mov     r8d, 2E9h; unsigned __int16
0x180049dc6  lea     rcx, [rsp+78h+var_48]; this
0x180049dcb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180049dd0  lea     rax, [rsp+78h+hKey]
0x180049dd8  mov     [rsp+78h+hKey], 0
0x180049de4  xor     ebx, ebx
0x180049de6  mov     [rsp+78h+phkResult], rax; phkResult
0x180049deb  xor     r8d, r8d; ulOptions
0x180049dee  lea     rdx, ?s_wszSvchostKey@CDefragService@@0QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180049df5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049dfc  lea     edi, [rbx+2]
0x180049dff  mov     r9d, edi; samDesired
0x180049e02  call    cs:__imp_RegOpenKeyExW
0x180049e08  test    eax, eax
0x180049e0a  jnz     short loc_180049E21
0x180049e0c  mov     rcx, [rsp+78h+hKey]; hKey
0x180049e14  lea     rdx, ?s_wszSvcName@CDefragService@@0QBGB; "DEFRAGSVC"
0x180049e1b  call    cs:__imp_RegDeleteValueW
0x180049e21  xor     r9d, r9d; struct ATL::_ATL_REGMAP_ENTRY *
0x180049e24  lea     rcx, ?_Module@@3VCDefragService@@A; this
0x180049e2b  xor     r8d, r8d; int
0x180049e2e  lea     edx, [r9+64h]; unsigned int
0x180049e32  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180049e37  call    ?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::UnregisterServer(int,_GUID const *)
0x180049e3c  mov     r8d, edi; dwDesiredAccess
0x180049e3f  xor     edx, edx; lpDatabaseName
0x180049e41  xor     ecx, ecx; lpMachineName
0x180049e43  call    cs:__imp_OpenSCManagerW
0x180049e49  mov     rdi, rax
0x180049e4c  test    rax, rax
0x180049e4f  jz      short loc_180049E78
0x180049e51  mov     r8d, 10000h; dwDesiredAccess
0x180049e57  lea     rdx, ?s_wszSvcName@CDefragService@@0QBGB; "DEFRAGSVC"
0x180049e5e  mov     rcx, rax; hSCManager
0x180049e61  call    cs:__imp_OpenServiceW
0x180049e67  mov     rbx, rax
0x180049e6a  test    rax, rax
0x180049e6d  jz      short loc_180049E78
0x180049e6f  mov     rcx, rax; hService
0x180049e72  call    cs:__imp_DeleteService
0x180049e78  mov     rcx, [rsp+78h+hKey]; hKey
0x180049e80  test    rcx, rcx
0x180049e83  jz      short loc_180049E97
0x180049e85  call    cs:__imp_RegCloseKey
0x180049e8b  mov     [rsp+78h+hKey], 0
0x180049e97  test    rbx, rbx
0x180049e9a  jz      short loc_180049EA5
0x180049e9c  mov     rcx, rbx; hSCObject
0x180049e9f  call    cs:__imp_CloseServiceHandle
0x180049ea5  test    rdi, rdi
0x180049ea8  jz      short loc_180049EB3
0x180049eaa  mov     rcx, rdi; hSCObject
0x180049ead  call    cs:__imp_CloseServiceHandle
0x180049eb3  mov     ebx, [rsp+78h+var_48]
0x180049eb7  lea     rcx, [rsp+78h+var_48]; this
0x180049ebc  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180049ec1  mov     eax, ebx
0x180049ec3  mov     rbx, [rsp+78h+arg_8]
0x180049ecb  add     rsp, 70h
0x180049ecf  pop     rdi
0x180049ed0  retn
```
