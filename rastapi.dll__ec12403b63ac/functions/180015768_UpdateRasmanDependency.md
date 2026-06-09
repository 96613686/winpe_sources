# UpdateRasmanDependency

- ea: `0x180015768`
- end: `0x1800158b0`
- name: `UpdateRasmanDependency`
- size: `328`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800022a0`
- `0x18000f7a0`
- `0x1800154f0`
- `0x1800158c0`

## callees

- `0x18000d92c`
- `0x180010ee4`
- `0x180015768`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001587b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001587b`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800157e3`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800157e3`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfigA` at `0x180015871`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfigA` at `0x180015871`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800157aa`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800157aa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015894`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001589d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180015894`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001589d`

## string_xrefs

- `0x180015777`: `UpdateRasmanDependency: Called with fAddDependency = %d`
- `0x18001578f`: `UpdateRasmanDependency: Ignoring this call for mobile core sku`
- `0x1800157c0`: `UpdateRasmanDependency: OpenSCManager failed (0x%x)`
- `0x1800157f9`: `UpdateRasmanDependency: OpenService failed (0x%x)`
- `0x180015883`: `UpdateRasmanDependency: Rasman service dependency could not be updated. Error 0x%x`

## pseudocode

```c
__int64 __fastcall UpdateRasmanDependency(int a1)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi
  DWORD LastError; // ebx
  SC_HANDLE v6; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  const char *v8; // rcx
  bool v9; // zf
  const CHAR *lpDependencies; // rax

  RasTapiTrace("UpdateRasmanDependency: Called with fAddDependency = %d");
  if ( g_RasMobileCore )
  {
    RasTapiTrace("UpdateRasmanDependency: Ignoring this call for mobile core sku");
    return 0;
  }
  else
  {
    v3 = OpenSCManagerA(0, 0, 1u);
    v4 = v3;
    if ( v3 )
    {
      v6 = OpenServiceA(v3, "RASMAN", 2u);
      if ( v6 )
      {
        LastError = 0;
        if ( (Feature_VPN_BugFixes_25C_RasmansDependency__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25C_RasmansDependency__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25C_RasmansDependency__private_IsEnabledDeviceUsageNoInline();
        v8 = "WANARP";
        v9 = IsEnabledDeviceUsageNoInline == 0;
        lpDependencies = "TapiSrv";
        if ( v9 )
          v8 = "SstpSvc";
        if ( !a1 )
          lpDependencies = v8;
        if ( !ChangeServiceConfigA(v6, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 0, lpDependencies, 0, 0, 0) )
        {
          LastError = GetLastError();
          RasTapiTrace("UpdateRasmanDependency: Rasman service dependency could not be updated. Error 0x%x");
        }
        CloseServiceHandle(v6);
      }
      else
      {
        LastError = GetLastError();
        RasTapiTrace("UpdateRasmanDependency: OpenService failed (0x%x)");
      }
      CloseServiceHandle(v4);
    }
    else
    {
      LastError = GetLastError();
      RasTapiTrace("UpdateRasmanDependency: OpenSCManager failed (0x%x)");
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x180015768  push    rbx
0x18001576a  push    rbp
0x18001576b  push    rsi
0x18001576c  push    rdi
0x18001576d  push    r14
0x18001576f  sub     rsp, 60h
0x180015773  mov     ebp, ecx
0x180015775  mov     edx, ecx
0x180015777  lea     rcx, aUpdaterasmande_3; "UpdateRasmanDependency: Called with fAd"...
0x18001577e  call    RasTapiTrace
0x180015783  xor     r14d, r14d
0x180015786  cmp     cs:g_RasMobileCore, r14d
0x18001578d  jz      short loc_1800157A2
0x18001578f  lea     rcx, aUpdaterasmande; "UpdateRasmanDependency: Ignoring this c"...
0x180015796  call    RasTapiTrace
0x18001579b  xor     eax, eax
0x18001579d  jmp     loc_1800158A5
0x1800157a2  xor     edx, edx; lpDatabaseName
0x1800157a4  xor     ecx, ecx; lpMachineName
0x1800157a6  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800157aa  call    cs:__imp_OpenSCManagerA
0x1800157b0  mov     rdi, rax
0x1800157b3  test    rax, rax
0x1800157b6  jnz     short loc_1800157D3
0x1800157b8  call    cs:__imp_GetLastError
0x1800157be  mov     edx, eax
0x1800157c0  lea     rcx, aUpdaterasmande_1; "UpdateRasmanDependency: OpenSCManager f"...
0x1800157c7  mov     ebx, eax
0x1800157c9  call    RasTapiTrace
0x1800157ce  jmp     loc_1800158A3
0x1800157d3  mov     r8d, 2; dwDesiredAccess
0x1800157d9  lea     rdx, aRasman; "RASMAN"
0x1800157e0  mov     rcx, rdi; hSCManager
0x1800157e3  call    cs:__imp_OpenServiceA
0x1800157e9  mov     rsi, rax
0x1800157ec  test    rax, rax
0x1800157ef  jnz     short loc_18001580C
0x1800157f1  call    cs:__imp_GetLastError
0x1800157f7  mov     edx, eax
0x1800157f9  lea     rcx, aUpdaterasmande_2; "UpdateRasmanDependency: OpenService fai"...
0x180015800  mov     ebx, eax
0x180015802  call    RasTapiTrace
0x180015807  jmp     loc_18001589A
0x18001580c  mov     eax, cs:Feature_VPN_BugFixes_25C_RasmansDependency__private_featureState
0x180015812  mov     ebx, r14d
0x180015815  test    al, 10h
0x180015817  jz      short loc_18001581E
0x180015819  and     eax, 1
0x18001581c  jmp     short loc_180015823
0x18001581e  call    Feature_VPN_BugFixes_25C_RasmansDependency__private_IsEnabledDeviceUsageNoInline
0x180015823  mov     [rsp+88h+lpDisplayName], r14; lpDisplayName
0x180015828  lea     rcx, Dependencies; "WANARP"
0x18001582f  mov     [rsp+88h+lpPassword], r14; lpPassword
0x180015834  test    eax, eax
0x180015836  mov     [rsp+88h+lpServiceStartName], r14; lpServiceStartName
0x18001583b  lea     rax, aTapisrv; "TapiSrv"
0x180015842  jnz     short loc_18001584B
0x180015844  lea     rcx, aSstpsvc; "SstpSvc"
0x18001584b  test    ebp, ebp
0x18001584d  cmovz   rax, rcx
0x180015851  or      edx, 0FFFFFFFFh; dwServiceType
0x180015854  mov     [rsp+88h+lpDependencies], rax; lpDependencies
0x180015859  mov     r9d, edx; dwErrorControl
0x18001585c  mov     [rsp+88h+lpdwTagId], r14; lpdwTagId
0x180015861  mov     r8d, edx; dwStartType
0x180015864  mov     [rsp+88h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x180015869  mov     rcx, rsi; hService
0x18001586c  mov     [rsp+88h+lpBinaryPathName], r14; lpBinaryPathName
0x180015871  call    cs:__imp_ChangeServiceConfigA
0x180015877  test    eax, eax
0x180015879  jnz     short loc_180015891
0x18001587b  call    cs:__imp_GetLastError
0x180015881  mov     edx, eax
0x180015883  lea     rcx, aUpdaterasmande_0; "UpdateRasmanDependency: Rasman service "...
0x18001588a  mov     ebx, eax
0x18001588c  call    RasTapiTrace
0x180015891  mov     rcx, rsi; hSCObject
0x180015894  call    cs:__imp_CloseServiceHandle
0x18001589a  mov     rcx, rdi; hSCObject
0x18001589d  call    cs:__imp_CloseServiceHandle
0x1800158a3  mov     eax, ebx
0x1800158a5  add     rsp, 60h
0x1800158a9  pop     r14
0x1800158ab  pop     rdi
0x1800158ac  pop     rsi
0x1800158ad  pop     rbp
0x1800158ae  pop     rbx
0x1800158af  retn
```
