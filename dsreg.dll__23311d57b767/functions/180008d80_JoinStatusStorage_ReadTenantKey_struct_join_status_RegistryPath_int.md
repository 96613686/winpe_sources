# JoinStatusStorage::ReadTenantKey(struct_join_status *,RegistryPath &,int)

- ea: `0x180008d80`
- end: `0x180009774`
- name: `?ReadTenantKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z`
- size: `2548`
- prototype: `__int64 __fastcall(struct struct_join_status *, struct RegistryPath *this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009f10`

## callees

- `0x1800084f4`
- `0x180008d80`
- `0x180009780`
- `0x1800097c0`
- `0x180020940`
- `0x180043e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008df2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008df2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008da8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008da8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093ae`

## string_xrefs

- `0x180009321`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x1800093bf`: `RegistryPath::ReadStringValue`
- `0x1800093e1`: `RegistryPath::ReadStringValue`
- `0x180009403`: `RegistryPath::ReadStringValue`
- `0x180009425`: `RegistryPath::ReadStringValue`
- `0x180009447`: `RegistryPath::ReadStringValue`
- `0x180009469`: `RegistryPath::ReadStringValue`
- `0x18000948b`: `RegistryPath::ReadStringValue`
- `0x1800094ad`: `RegistryPath::ReadStringValue`
- `0x1800094cf`: `RegistryPath::ReadStringValue`
- `0x1800094f1`: `RegistryPath::ReadStringValue`
- `0x180009513`: `RegistryPath::ReadStringValue`
- `0x180009535`: `RegistryPath::ReadStringValue`
- `0x180009557`: `RegistryPath::ReadStringValue`
- `0x180009579`: `RegistryPath::ReadStringValue`
- `0x18000959b`: `RegistryPath::ReadStringValue`
- `0x1800095bd`: `RegistryPath::ReadStringValue`
- `0x1800095df`: `RegistryPath::ReadStringValue`
- `0x180009601`: `RegistryPath::ReadStringValue`
- `0x180009623`: `RegistryPath::ReadStringValue`
- `0x180009645`: `RegistryPath::ReadStringValue`
- `0x180009667`: `RegistryPath::ReadStringValue`
- `0x180009689`: `RegistryPath::ReadStringValue`
- `0x1800096ab`: `RegistryPath::ReadStringValue`
- `0x1800096cd`: `RegistryPath::ReadStringValue`
- `0x1800096ef`: `RegistryPath::ReadStringValue`
- `0x180009711`: `RegistryPath::ReadStringValue`
- `0x180009733`: `RegistryPath::ReadStringValue`
- `0x180009755`: `RegistryPath::ReadStringValue`
- `0x18000931a`: `RegistryPath::OpenSubKey`
- `0x180009335`: `RegistryPath::OpenSubKey`
- `0x18000938c`: `RegistryPath::OpenSubKey`
- `0x1800090c8`: `WebAuthnServiceVersion`
- `0x180008ee3`: `DrsServiceVersion`
- `0x180008e93`: `MdmComplianceUrl`
- `0x180008f83`: `AccessTokenUrl`
- `0x18000915b`: `DeviceManagementServiceVersion`
- `0x180009035`: `NgcServiceVersion`
- `0x180008fab`: `CdjServiceVersion`
- `0x18000937b`: `RegOpenKeyExW`
- `0x18000933c`: `JoinStatusStorage::ReadTenantKey`
- `0x180009363`: `JoinStatusStorage::ReadTenantKey`
- `0x1800093c6`: `JoinStatusStorage::ReadTenantKey`
- `0x1800093e8`: `JoinStatusStorage::ReadTenantKey`
- `0x18000940a`: `JoinStatusStorage::ReadTenantKey`
- `0x18000942c`: `JoinStatusStorage::ReadTenantKey`
- `0x18000944e`: `JoinStatusStorage::ReadTenantKey`
- `0x180009470`: `JoinStatusStorage::ReadTenantKey`
- `0x180009492`: `JoinStatusStorage::ReadTenantKey`
- `0x1800094b4`: `JoinStatusStorage::ReadTenantKey`
- `0x1800094d6`: `JoinStatusStorage::ReadTenantKey`
- `0x1800094f8`: `JoinStatusStorage::ReadTenantKey`
- `0x18000951a`: `JoinStatusStorage::ReadTenantKey`
- `0x18000953c`: `JoinStatusStorage::ReadTenantKey`
- `0x18000955e`: `JoinStatusStorage::ReadTenantKey`
- `0x180009580`: `JoinStatusStorage::ReadTenantKey`
- `0x1800095a2`: `JoinStatusStorage::ReadTenantKey`
- `0x1800095c4`: `JoinStatusStorage::ReadTenantKey`
- `0x1800095e6`: `JoinStatusStorage::ReadTenantKey`
- `0x180009608`: `JoinStatusStorage::ReadTenantKey`
- `0x18000962a`: `JoinStatusStorage::ReadTenantKey`
- `0x18000964c`: `JoinStatusStorage::ReadTenantKey`
- `0x18000966e`: `JoinStatusStorage::ReadTenantKey`
- `0x180009690`: `JoinStatusStorage::ReadTenantKey`
- `0x1800096b2`: `JoinStatusStorage::ReadTenantKey`
- `0x1800096d4`: `JoinStatusStorage::ReadTenantKey`
- `0x1800096f6`: `JoinStatusStorage::ReadTenantKey`
- `0x180009718`: `JoinStatusStorage::ReadTenantKey`
- `0x18000973a`: `JoinStatusStorage::ReadTenantKey`
- `0x18000975c`: `JoinStatusStorage::ReadTenantKey`
- `0x180009396`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadTenantKey(void **a1, struct RegistryPath *this, int a3)
{
  HKEY *phkResult; // rdi
  HKEY v5; // rcx
  HKEY v8; // rcx
  _WORD *v9; // rdx
  LSTATUS v10; // eax
  unsigned int v11; // ebp
  unsigned int StringValue; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  int v41; // eax

  phkResult = (HKEY *)((char *)this + 40);
  v5 = (HKEY)*((_QWORD *)this + 5);
  if ( v5 )
    RegCloseKey(v5);
  *phkResult = 0;
  v8 = (HKEY)*((_QWORD *)this + 4);
  if ( !v8 || (v9 = *(_WORD **)this) == 0 || !*v9 )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::OpenSubKey");
    v11 = 87;
LABEL_67:
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::OpenSubKey",
      v11);
    return 0;
  }
  v10 = RegOpenKeyExW(v8, &v9[*((_QWORD *)this + 3)], 0, 1u, phkResult);
  v11 = v10;
  if ( v10 )
  {
    Logger::WriteRegistryFailureEvent(v10, L"RegOpenKeyExW", *(const unsigned __int16 **)this);
    Logger::TraceError(
      L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.",
      L"RegistryPath::OpenSubKey",
      *(_QWORD *)this,
      v11);
    if ( *phkResult )
    {
      RegCloseKey(*phkResult);
      *phkResult = 0;
    }
  }
  if ( v11 )
    goto LABEL_67;
  SafeFree(a1[4]);
  a1[4] = 0;
  StringValue = RegistryPath::ReadStringValue(this, L"DisplayName", (unsigned __int16 **)a1 + 4);
  if ( StringValue )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      StringValue);
  SafeFree(a1[5]);
  a1[5] = 0;
  v13 = RegistryPath::ReadStringValue(this, L"MdmEnrollmentUrl", (unsigned __int16 **)a1 + 5);
  if ( v13 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v13);
  SafeFree(a1[6]);
  a1[6] = 0;
  v14 = RegistryPath::ReadStringValue(this, L"MdmTermsOfUseUrl", (unsigned __int16 **)a1 + 6);
  if ( v14 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v14);
  SafeFree(a1[7]);
  a1[7] = 0;
  v15 = RegistryPath::ReadStringValue(this, L"MdmComplianceUrl", (unsigned __int16 **)a1 + 7);
  if ( v15 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v15);
  SafeFree(a1[8]);
  a1[8] = 0;
  v16 = RegistryPath::ReadStringValue(this, L"UserSettingSyncUrl", (unsigned __int16 **)a1 + 8);
  if ( v16 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v16);
  SafeFree(a1[9]);
  a1[9] = 0;
  v17 = RegistryPath::ReadStringValue(this, L"DrsServiceVersion", (unsigned __int16 **)a1 + 9);
  if ( v17 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v17);
  SafeFree(a1[10]);
  a1[10] = 0;
  v18 = RegistryPath::ReadStringValue(this, L"DrsEndpoint", (unsigned __int16 **)a1 + 10);
  if ( v18 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v18);
  SafeFree(a1[11]);
  a1[11] = 0;
  v19 = RegistryPath::ReadStringValue(this, L"DrsResourceId", (unsigned __int16 **)a1 + 11);
  if ( v19 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v19);
  SafeFree(a1[12]);
  a1[12] = 0;
  v20 = RegistryPath::ReadStringValue(this, L"AuthCodeUrl", (unsigned __int16 **)a1 + 12);
  if ( v20 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v20);
  SafeFree(a1[13]);
  a1[13] = 0;
  v21 = RegistryPath::ReadStringValue(this, L"AccessTokenUrl", (unsigned __int16 **)a1 + 13);
  if ( v21 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v21);
  SafeFree(a1[14]);
  a1[14] = 0;
  v22 = RegistryPath::ReadStringValue(this, L"CdjServiceVersion", (unsigned __int16 **)a1 + 14);
  if ( v22 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v22);
  SafeFree(a1[15]);
  a1[15] = 0;
  v23 = RegistryPath::ReadStringValue(this, L"CdjEndpoint", (unsigned __int16 **)a1 + 15);
  if ( v23 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v23);
  SafeFree(a1[16]);
  a1[16] = 0;
  v24 = RegistryPath::ReadStringValue(this, L"CdjResourceId", (unsigned __int16 **)a1 + 16);
  if ( v24 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v24);
  SafeFree(a1[17]);
  a1[17] = 0;
  v25 = RegistryPath::ReadStringValue(this, L"NgcServiceVersion", (unsigned __int16 **)a1 + 17);
  if ( v25 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v25);
  SafeFree(a1[18]);
  a1[18] = 0;
  v26 = RegistryPath::ReadStringValue(this, L"NgcEndpoint", (unsigned __int16 **)a1 + 18);
  if ( v26 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v26);
  SafeFree(a1[19]);
  a1[19] = 0;
  v27 = RegistryPath::ReadStringValue(this, L"NgcResourceId", (unsigned __int16 **)a1 + 19);
  if ( v27 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v27);
  SafeFree(a1[20]);
  a1[20] = 0;
  v28 = RegistryPath::ReadStringValue(this, L"WebAuthnServiceVersion", (unsigned __int16 **)a1 + 20);
  if ( v28 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v28);
  SafeFree(a1[21]);
  a1[21] = 0;
  v29 = RegistryPath::ReadStringValue(this, L"WebAuthnEndpoint", (unsigned __int16 **)a1 + 21);
  if ( v29 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v29);
  SafeFree(a1[22]);
  a1[22] = 0;
  v30 = RegistryPath::ReadStringValue(this, L"WebAuthnResourceId", (unsigned __int16 **)a1 + 22);
  if ( v30 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v30);
  SafeFree(a1[23]);
  a1[23] = 0;
  v31 = RegistryPath::ReadStringValue(this, L"DeviceManagementServiceVersion", (unsigned __int16 **)a1 + 23);
  if ( v31 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v31);
  SafeFree(a1[24]);
  a1[24] = 0;
  v32 = RegistryPath::ReadStringValue(this, L"DeviceManagementEndpoint", (unsigned __int16 **)a1 + 24);
  if ( v32 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v32);
  SafeFree(a1[25]);
  a1[25] = 0;
  v33 = RegistryPath::ReadStringValue(this, L"DeviceManagementResourceId", (unsigned __int16 **)a1 + 25);
  if ( v33 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v33);
  SafeFree(a1[28]);
  a1[28] = 0;
  v34 = RegistryPath::ReadStringValue(this, L"RbacPolicyEndpoint", (unsigned __int16 **)a1 + 28);
  if ( v34 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v34);
  SafeFree(a1[35]);
  a1[35] = 0;
  v35 = RegistryPath::ReadStringValue(this, L"KerbSpn", (unsigned __int16 **)a1 + 35);
  if ( v35 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v35);
  SafeFree(a1[36]);
  a1[36] = 0;
  v36 = RegistryPath::ReadStringValue(this, L"KerbEndpoint", (unsigned __int16 **)a1 + 36);
  if ( v36 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v36);
  SafeFree(a1[37]);
  a1[37] = 0;
  v37 = RegistryPath::ReadStringValue(this, L"CdjEndpointTLS", (unsigned __int16 **)a1 + 37);
  if ( v37 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v37);
  SafeFree(a1[38]);
  a1[38] = 0;
  v38 = RegistryPath::ReadStringValue(this, L"DeviceManagementEndpointTLS", (unsigned __int16 **)a1 + 38);
  if ( v38 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v38);
  SafeFree(a1[39]);
  a1[39] = 0;
  v39 = RegistryPath::ReadStringValue(this, L"DeviceJoinResourceEndpointTLS", (unsigned __int16 **)a1 + 39);
  if ( v39 )
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::ReadStringValue",
      v39);
  if ( a3 )
  {
    v41 = JoinStatusStorage::SetDefaultDiscoveryMetadata(
            (struct struct_join_status *)a1,
            *(const unsigned __int16 **)this);
    if ( v41 < 0 )
      Logger::TraceError(
        L"%s: JoinStatusStorage::SetDefaultDiscoveryMetadata failed with error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        (unsigned int)v41);
  }
  return 0;
}

```

## disassembly

```asm
0x180008d80  mov     [rsp+arg_8], rbx
0x180008d85  mov     [rsp+arg_10], rsi
0x180008d8a  push    rdi
0x180008d8b  push    r14
0x180008d8d  push    r15
0x180008d8f  sub     rsp, 30h
0x180008d93  lea     rdi, [rdx+28h]
0x180008d97  mov     rsi, rcx
0x180008d9a  mov     rcx, [rdi]; hKey
0x180008d9d  mov     r14d, r8d
0x180008da0  mov     rbx, rdx
0x180008da3  test    rcx, rcx
0x180008da6  jz      short loc_180008DAE
0x180008da8  call    cs:__imp_RegCloseKey
0x180008dae  xor     r15d, r15d
0x180008db1  mov     [rsp+48h+arg_0], rbp
0x180008db6  mov     [rdi], r15
0x180008db9  mov     rcx, [rbx+20h]; hKey
0x180008dbd  test    rcx, rcx
0x180008dc0  jz      loc_18000931A
0x180008dc6  mov     rdx, [rbx]
0x180008dc9  test    rdx, rdx
0x180008dcc  jz      loc_18000931A
0x180008dd2  cmp     [rdx], r15w
0x180008dd6  jz      loc_18000931A
0x180008ddc  mov     rax, [rbx+18h]
0x180008de0  mov     r9d, 1; samDesired
0x180008de6  xor     r8d, r8d; ulOptions
0x180008de9  mov     [rsp+48h+phkResult], rdi; phkResult
0x180008dee  lea     rdx, [rdx+rax*2]; lpSubKey
0x180008df2  call    cs:__imp_RegOpenKeyExW
0x180008df8  mov     ebp, eax
0x180008dfa  test    eax, eax
0x180008dfc  jnz     loc_180009378
0x180008e02  test    ebp, ebp
0x180008e04  jnz     loc_180009332
0x180008e0a  mov     rcx, [rsi+20h]; lpMem
0x180008e0e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008e13  lea     r8, [rsi+20h]; unsigned __int16 **
0x180008e17  mov     [rsi+20h], r15
0x180008e1b  lea     rdx, aDisplayname; "DisplayName"
0x180008e22  mov     rcx, rbx; this
0x180008e25  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008e2a  test    eax, eax
0x180008e2c  jnz     loc_1800093BC
0x180008e32  mov     rcx, [rsi+28h]; lpMem
0x180008e36  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008e3b  lea     r8, [rsi+28h]; unsigned __int16 **
0x180008e3f  mov     [rsi+28h], r15
0x180008e43  lea     rdx, aMdmenrollmentu_0; "MdmEnrollmentUrl"
0x180008e4a  mov     rcx, rbx; this
0x180008e4d  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008e52  test    eax, eax
0x180008e54  jnz     loc_1800093DE
0x180008e5a  mov     rcx, [rsi+30h]; lpMem
0x180008e5e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008e63  lea     r8, [rsi+30h]; unsigned __int16 **
0x180008e67  mov     [rsi+30h], r15
0x180008e6b  lea     rdx, aMdmtermsofuseu; "MdmTermsOfUseUrl"
0x180008e72  mov     rcx, rbx; this
0x180008e75  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008e7a  test    eax, eax
0x180008e7c  jnz     loc_180009400
0x180008e82  mov     rcx, [rsi+38h]; lpMem
0x180008e86  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008e8b  lea     r8, [rsi+38h]; unsigned __int16 **
0x180008e8f  mov     [rsi+38h], r15
0x180008e93  lea     rdx, aMdmcomplianceu; "MdmComplianceUrl"
0x180008e9a  mov     rcx, rbx; this
0x180008e9d  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008ea2  test    eax, eax
0x180008ea4  jnz     loc_180009422
0x180008eaa  mov     rcx, [rsi+40h]; lpMem
0x180008eae  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008eb3  lea     r8, [rsi+40h]; unsigned __int16 **
0x180008eb7  mov     [rsi+40h], r15
0x180008ebb  lea     rdx, aUsersettingsyn; "UserSettingSyncUrl"
0x180008ec2  mov     rcx, rbx; this
0x180008ec5  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008eca  test    eax, eax
0x180008ecc  jnz     loc_180009444
0x180008ed2  mov     rcx, [rsi+48h]; lpMem
0x180008ed6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008edb  lea     r8, [rsi+48h]; unsigned __int16 **
0x180008edf  mov     [rsi+48h], r15
0x180008ee3  lea     rdx, aDrsservicevers; "DrsServiceVersion"
0x180008eea  mov     rcx, rbx; this
0x180008eed  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008ef2  test    eax, eax
0x180008ef4  jnz     loc_180009466
0x180008efa  mov     rcx, [rsi+50h]; lpMem
0x180008efe  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008f03  lea     r8, [rsi+50h]; unsigned __int16 **
0x180008f07  mov     [rsi+50h], r15
0x180008f0b  lea     rdx, aDrsendpoint; "DrsEndpoint"
0x180008f12  mov     rcx, rbx; this
0x180008f15  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008f1a  test    eax, eax
0x180008f1c  jnz     loc_180009488
0x180008f22  mov     rcx, [rsi+58h]; lpMem
0x180008f26  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008f2b  lea     r8, [rsi+58h]; unsigned __int16 **
0x180008f2f  mov     [rsi+58h], r15
0x180008f33  lea     rdx, aDrsresourceid; "DrsResourceId"
0x180008f3a  mov     rcx, rbx; this
0x180008f3d  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008f42  test    eax, eax
0x180008f44  jnz     loc_1800094AA
0x180008f4a  mov     rcx, [rsi+60h]; lpMem
0x180008f4e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008f53  lea     r8, [rsi+60h]; unsigned __int16 **
0x180008f57  mov     [rsi+60h], r15
0x180008f5b  lea     rdx, aAuthcodeurl; "AuthCodeUrl"
0x180008f62  mov     rcx, rbx; this
0x180008f65  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008f6a  test    eax, eax
0x180008f6c  jnz     loc_1800094CC
0x180008f72  mov     rcx, [rsi+68h]; lpMem
0x180008f76  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008f7b  lea     r8, [rsi+68h]; unsigned __int16 **
0x180008f7f  mov     [rsi+68h], r15
0x180008f83  lea     rdx, aAccesstokenurl; "AccessTokenUrl"
0x180008f8a  mov     rcx, rbx; this
0x180008f8d  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008f92  test    eax, eax
0x180008f94  jnz     loc_1800094EE
0x180008f9a  mov     rcx, [rsi+70h]; lpMem
0x180008f9e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008fa3  lea     r8, [rsi+70h]; unsigned __int16 **
0x180008fa7  mov     [rsi+70h], r15
0x180008fab  lea     rdx, aCdjservicevers; "CdjServiceVersion"
0x180008fb2  mov     rcx, rbx; this
0x180008fb5  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008fba  test    eax, eax
0x180008fbc  jnz     loc_180009510
0x180008fc2  mov     rcx, [rsi+78h]; lpMem
0x180008fc6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008fcb  lea     r8, [rsi+78h]; unsigned __int16 **
0x180008fcf  mov     [rsi+78h], r15
0x180008fd3  lea     rdx, aCdjendpoint; "CdjEndpoint"
0x180008fda  mov     rcx, rbx; this
0x180008fdd  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180008fe2  test    eax, eax
0x180008fe4  jnz     loc_180009532
0x180008fea  mov     rcx, [rsi+80h]; lpMem
0x180008ff1  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008ff6  lea     r8, [rsi+80h]; unsigned __int16 **
0x180008ffd  mov     [rsi+80h], r15
0x180009004  lea     rdx, aCdjresourceid; "CdjResourceId"
0x18000900b  mov     rcx, rbx; this
0x18000900e  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180009013  test    eax, eax
0x180009015  jnz     loc_180009554
0x18000901b  mov     rcx, [rsi+88h]; lpMem
0x180009022  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180009027  lea     r8, [rsi+88h]; unsigned __int16 **
0x18000902e  mov     [rsi+88h], r15
0x180009035  lea     rdx, aNgcservicevers; "NgcServiceVersion"
0x18000903c  mov     rcx, rbx; this
0x18000903f  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180009044  test    eax, eax
0x180009046  jnz     loc_180009576
0x18000904c  mov     rcx, [rsi+90h]; lpMem
0x180009053  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180009058  lea     r8, [rsi+90h]; unsigned __int16 **
0x18000905f  mov     [rsi+90h], r15
0x180009066  lea     rdx, aNgcendpoint; "NgcEndpoint"
0x18000906d  mov     rcx, rbx; this
0x180009070  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180009075  test    eax, eax
0x180009077  jnz     loc_180009598
0x18000907d  mov     rcx, [rsi+98h]; lpMem
0x180009084  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180009089  lea     r8, [rsi+98h]; unsigned __int16 **
0x180009090  mov     [rsi+98h], r15
0x180009097  lea     rdx, aNgcresourceid; "NgcResourceId"
0x18000909e  mov     rcx, rbx; this
0x1800090a1  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x1800090a6  test    eax, eax
0x1800090a8  jnz     loc_1800095BA
0x1800090ae  mov     rcx, [rsi+0A0h]; lpMem
0x1800090b5  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800090ba  lea     r8, [rsi+0A0h]; unsigned __int16 **
0x1800090c1  mov     [rsi+0A0h], r15
0x1800090c8  lea     rdx, aWebauthnservic_0; "WebAuthnServiceVersion"
0x1800090cf  mov     rcx, rbx; this
0x1800090d2  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x1800090d7  test    eax, eax
0x1800090d9  jnz     loc_1800095DC
0x1800090df  mov     rcx, [rsi+0A8h]; lpMem
0x1800090e6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800090eb  lea     r8, [rsi+0A8h]; unsigned __int16 **
0x1800090f2  mov     [rsi+0A8h], r15
0x1800090f9  lea     rdx, aWebauthnendpoi; "WebAuthnEndpoint"
0x180009100  mov     rcx, rbx; this
0x180009103  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180009108  test    eax, eax
0x18000910a  jnz     loc_1800095FE
0x180009110  mov     rcx, [rsi+0B0h]; lpMem
0x180009117  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000911c  lea     r8, [rsi+0B0h]; unsigned __int16 **
0x180009123  mov     [rsi+0B0h], r15
0x18000912a  lea     rdx, aWebauthnresour; "WebAuthnResourceId"
0x180009131  mov     rcx, rbx; this
0x180009134  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180009139  test    eax, eax
0x18000913b  jnz     loc_180009620
0x180009141  mov     rcx, [rsi+0B8h]; lpMem
0x180009148  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000914d  lea     r8, [rsi+0B8h]; unsigned __int16 **
0x180009154  mov     [rsi+0B8h], r15
0x18000915b  lea     rdx, aDevicemanageme_7; "DeviceManagementServiceVersion"
0x180009162  mov     rcx, rbx; this
0x180009165  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000916a  test    eax, eax
0x18000916c  jnz     loc_180009642
0x180009172  mov     rcx, [rsi+0C0h]; lpMem
0x180009179  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000917e  lea     r8, [rsi+0C0h]; unsigned __int16 **
0x180009185  mov     [rsi+0C0h], r15
0x18000918c  lea     rdx, aDevicemanageme_6; "DeviceManagementEndpoint"
0x180009193  mov     rcx, rbx; this
0x180009196  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000919b  test    eax, eax
0x18000919d  jnz     loc_180009664
0x1800091a3  mov     rcx, [rsi+0C8h]; lpMem
0x1800091aa  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800091af  lea     r8, [rsi+0C8h]; unsigned __int16 **
0x1800091b6  mov     [rsi+0C8h], r15
0x1800091bd  lea     rdx, aDevicemanageme; "DeviceManagementResourceId"
0x1800091c4  mov     rcx, rbx; this
0x1800091c7  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x1800091cc  test    eax, eax
0x1800091ce  jnz     loc_180009686
0x1800091d4  mov     rcx, [rsi+0E0h]; lpMem
0x1800091db  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800091e0  lea     r8, [rsi+0E0h]; unsigned __int16 **
0x1800091e7  mov     [rsi+0E0h], r15
0x1800091ee  lea     rdx, aRbacpolicyendp; "RbacPolicyEndpoint"
0x1800091f5  mov     rcx, rbx; this
0x1800091f8  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x1800091fd  test    eax, eax
0x1800091ff  jnz     loc_1800096A8
0x180009205  mov     rcx, [rsi+118h]; lpMem
0x18000920c  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180009211  lea     r8, [rsi+118h]; unsigned __int16 **
0x180009218  mov     [rsi+118h], r15
0x18000921f  lea     rdx, aKerbspn; "KerbSpn"
0x180009226  mov     rcx, rbx; this
0x180009229  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000922e  test    eax, eax
0x180009230  jnz     loc_1800096CA
0x180009236  mov     rcx, [rsi+120h]; lpMem
0x18000923d  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180009242  lea     r8, [rsi+120h]; unsigned __int16 **
0x180009249  mov     [rsi+120h], r15
0x180009250  lea     rdx, aKerbendpoint_0; "KerbEndpoint"
0x180009257  mov     rcx, rbx; this
0x18000925a  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000925f  test    eax, eax
0x180009261  jnz     loc_1800096EC
0x180009267  mov     rcx, [rsi+128h]; lpMem
0x18000926e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180009273  lea     r8, [rsi+128h]; unsigned __int16 **
0x18000927a  mov     [rsi+128h], r15
0x180009281  lea     rdx, aCdjendpointtls; "CdjEndpointTLS"
0x180009288  mov     rcx, rbx; this
0x18000928b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x180009290  test    eax, eax
0x180009292  jnz     loc_18000970E
0x180009298  mov     rcx, [rsi+130h]; lpMem
0x18000929f  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800092a4  lea     r8, [rsi+130h]; unsigned __int16 **
0x1800092ab  mov     [rsi+130h], r15
0x1800092b2  lea     rdx, aDevicemanageme_0; "DeviceManagementEndpointTLS"
0x1800092b9  mov     rcx, rbx; this
0x1800092bc  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x1800092c1  test    eax, eax
0x1800092c3  jnz     loc_180009730
0x1800092c9  mov     rcx, [rsi+138h]; lpMem
0x1800092d0  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800092d5  lea     r8, [rsi+138h]; unsigned __int16 **
0x1800092dc  mov     [rsi+138h], r15
0x1800092e3  lea     rdx, aDevicejoinreso; "DeviceJoinResourceEndpointTLS"
0x1800092ea  mov     rcx, rbx; this
0x1800092ed  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x1800092f2  test    eax, eax
0x1800092f4  jnz     loc_180009752
0x1800092fa  test    r14d, r14d
0x1800092fd  jnz     short loc_180009351
0x1800092ff  xor     eax, eax
0x180009301  mov     rbp, [rsp+48h+arg_0]
0x180009306  mov     rbx, [rsp+48h+arg_8]
0x18000930b  mov     rsi, [rsp+48h+arg_10]
0x180009310  add     rsp, 30h
0x180009314  pop     r15
0x180009316  pop     r14
0x180009318  pop     rdi
0x180009319  retn
0x18000931a  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
  ... truncated ...
```
