# JoinStatusStorage::ReadTenantKey(struct_join_status *,RegistryPath &,int)

- ea: `0x18000c680`
- end: `0x18000cec4`
- name: `?ReadTenantKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z`
- size: `2116`
- prototype: `__int64 __fastcall(struct struct_join_status *, struct RegistryPath *this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008ad0`

## callees

- `0x18000c680`
- `0x18000ced0`
- `0x18000cf10`
- `0x180027448`
- `0x18002cf08`
- `0x18004509c`

## string_xrefs

- `0x18000c6fa`: `RegistryPath::ReadStringValue`
- `0x18000c73b`: `RegistryPath::ReadStringValue`
- `0x18000c77c`: `RegistryPath::ReadStringValue`
- `0x18000c7bd`: `RegistryPath::ReadStringValue`
- `0x18000c7fe`: `RegistryPath::ReadStringValue`
- `0x18000c83f`: `RegistryPath::ReadStringValue`
- `0x18000c880`: `RegistryPath::ReadStringValue`
- `0x18000c8c1`: `RegistryPath::ReadStringValue`
- `0x18000c902`: `RegistryPath::ReadStringValue`
- `0x18000c943`: `RegistryPath::ReadStringValue`
- `0x18000c984`: `RegistryPath::ReadStringValue`
- `0x18000c9c5`: `RegistryPath::ReadStringValue`
- `0x18000ca0f`: `RegistryPath::ReadStringValue`
- `0x18000ca59`: `RegistryPath::ReadStringValue`
- `0x18000caa3`: `RegistryPath::ReadStringValue`
- `0x18000caed`: `RegistryPath::ReadStringValue`
- `0x18000cb37`: `RegistryPath::ReadStringValue`
- `0x18000cb81`: `RegistryPath::ReadStringValue`
- `0x18000cbcb`: `RegistryPath::ReadStringValue`
- `0x18000cc15`: `RegistryPath::ReadStringValue`
- `0x18000cc5f`: `RegistryPath::ReadStringValue`
- `0x18000cca9`: `RegistryPath::ReadStringValue`
- `0x18000ccf3`: `RegistryPath::ReadStringValue`
- `0x18000cd3d`: `RegistryPath::ReadStringValue`
- `0x18000cd87`: `RegistryPath::ReadStringValue`
- `0x18000cdd1`: `RegistryPath::ReadStringValue`
- `0x18000ce1b`: `RegistryPath::ReadStringValue`
- `0x18000ce6f`: `RegistryPath::ReadStringValue`
- `0x18000c6a7`: `RegistryPath::OpenSubKey`
- `0x18000cb21`: `WebAuthnServiceVersion`
- `0x18000c829`: `DrsServiceVersion`
- `0x18000c7a7`: `MdmComplianceUrl`
- `0x18000c92d`: `AccessTokenUrl`
- `0x18000cbff`: `DeviceManagementServiceVersion`
- `0x18000ca43`: `NgcServiceVersion`
- `0x18000c96e`: `CdjServiceVersion`
- `0x18000c6ae`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c701`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c742`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c783`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c7c4`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c805`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c846`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c887`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c8c8`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c909`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c94a`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c98b`: `JoinStatusStorage::ReadTenantKey`
- `0x18000c9cc`: `JoinStatusStorage::ReadTenantKey`
- `0x18000ca16`: `JoinStatusStorage::ReadTenantKey`
- `0x18000ca60`: `JoinStatusStorage::ReadTenantKey`
- `0x18000caaa`: `JoinStatusStorage::ReadTenantKey`
- `0x18000caf4`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cb3e`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cb88`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cbd2`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cc1c`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cc66`: `JoinStatusStorage::ReadTenantKey`
- `0x18000ccb0`: `JoinStatusStorage::ReadTenantKey`
- `0x18000ccfa`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cd44`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cd8e`: `JoinStatusStorage::ReadTenantKey`
- `0x18000cdd8`: `JoinStatusStorage::ReadTenantKey`
- `0x18000ce22`: `JoinStatusStorage::ReadTenantKey`
- `0x18000ce76`: `JoinStatusStorage::ReadTenantKey`
- `0x18000ce9f`: `JoinStatusStorage::ReadTenantKey`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadTenantKey(void **a1, struct RegistryPath *this, int a3)
{
  unsigned int v6; // eax
  unsigned int StringValue; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
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
  int v35; // eax

  v6 = RegistryPath::OpenSubKey(this, (unsigned int)this, a3);
  if ( v6 )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::OpenSubKey",
      v6);
  }
  else
  {
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
    v8 = RegistryPath::ReadStringValue(this, L"MdmEnrollmentUrl", (unsigned __int16 **)a1 + 5);
    if ( v8 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v8);
    SafeFree(a1[6]);
    a1[6] = 0;
    v9 = RegistryPath::ReadStringValue(this, L"MdmTermsOfUseUrl", (unsigned __int16 **)a1 + 6);
    if ( v9 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v9);
    SafeFree(a1[7]);
    a1[7] = 0;
    v10 = RegistryPath::ReadStringValue(this, L"MdmComplianceUrl", (unsigned __int16 **)a1 + 7);
    if ( v10 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v10);
    SafeFree(a1[8]);
    a1[8] = 0;
    v11 = RegistryPath::ReadStringValue(this, L"UserSettingSyncUrl", (unsigned __int16 **)a1 + 8);
    if ( v11 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v11);
    SafeFree(a1[9]);
    a1[9] = 0;
    v12 = RegistryPath::ReadStringValue(this, L"DrsServiceVersion", (unsigned __int16 **)a1 + 9);
    if ( v12 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v12);
    SafeFree(a1[10]);
    a1[10] = 0;
    v13 = RegistryPath::ReadStringValue(this, L"DrsEndpoint", (unsigned __int16 **)a1 + 10);
    if ( v13 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v13);
    SafeFree(a1[11]);
    a1[11] = 0;
    v14 = RegistryPath::ReadStringValue(this, L"DrsResourceId", (unsigned __int16 **)a1 + 11);
    if ( v14 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v14);
    SafeFree(a1[12]);
    a1[12] = 0;
    v15 = RegistryPath::ReadStringValue(this, L"AuthCodeUrl", (unsigned __int16 **)a1 + 12);
    if ( v15 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v15);
    SafeFree(a1[13]);
    a1[13] = 0;
    v16 = RegistryPath::ReadStringValue(this, L"AccessTokenUrl", (unsigned __int16 **)a1 + 13);
    if ( v16 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v16);
    SafeFree(a1[14]);
    a1[14] = 0;
    v17 = RegistryPath::ReadStringValue(this, L"CdjServiceVersion", (unsigned __int16 **)a1 + 14);
    if ( v17 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v17);
    SafeFree(a1[15]);
    a1[15] = 0;
    v18 = RegistryPath::ReadStringValue(this, L"CdjEndpoint", (unsigned __int16 **)a1 + 15);
    if ( v18 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v18);
    SafeFree(a1[16]);
    a1[16] = 0;
    v19 = RegistryPath::ReadStringValue(this, L"CdjResourceId", (unsigned __int16 **)a1 + 16);
    if ( v19 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v19);
    SafeFree(a1[17]);
    a1[17] = 0;
    v20 = RegistryPath::ReadStringValue(this, L"NgcServiceVersion", (unsigned __int16 **)a1 + 17);
    if ( v20 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v20);
    SafeFree(a1[18]);
    a1[18] = 0;
    v21 = RegistryPath::ReadStringValue(this, L"NgcEndpoint", (unsigned __int16 **)a1 + 18);
    if ( v21 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v21);
    SafeFree(a1[19]);
    a1[19] = 0;
    v22 = RegistryPath::ReadStringValue(this, L"NgcResourceId", (unsigned __int16 **)a1 + 19);
    if ( v22 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v22);
    SafeFree(a1[20]);
    a1[20] = 0;
    v23 = RegistryPath::ReadStringValue(this, L"WebAuthnServiceVersion", (unsigned __int16 **)a1 + 20);
    if ( v23 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v23);
    SafeFree(a1[21]);
    a1[21] = 0;
    v24 = RegistryPath::ReadStringValue(this, L"WebAuthnEndpoint", (unsigned __int16 **)a1 + 21);
    if ( v24 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v24);
    SafeFree(a1[22]);
    a1[22] = 0;
    v25 = RegistryPath::ReadStringValue(this, L"WebAuthnResourceId", (unsigned __int16 **)a1 + 22);
    if ( v25 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v25);
    SafeFree(a1[23]);
    a1[23] = 0;
    v26 = RegistryPath::ReadStringValue(this, L"DeviceManagementServiceVersion", (unsigned __int16 **)a1 + 23);
    if ( v26 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v26);
    SafeFree(a1[24]);
    a1[24] = 0;
    v27 = RegistryPath::ReadStringValue(this, L"DeviceManagementEndpoint", (unsigned __int16 **)a1 + 24);
    if ( v27 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v27);
    SafeFree(a1[25]);
    a1[25] = 0;
    v28 = RegistryPath::ReadStringValue(this, L"DeviceManagementResourceId", (unsigned __int16 **)a1 + 25);
    if ( v28 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v28);
    SafeFree(a1[28]);
    a1[28] = 0;
    v29 = RegistryPath::ReadStringValue(this, L"RbacPolicyEndpoint", (unsigned __int16 **)a1 + 28);
    if ( v29 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v29);
    SafeFree(a1[35]);
    a1[35] = 0;
    v30 = RegistryPath::ReadStringValue(this, L"KerbSpn", (unsigned __int16 **)a1 + 35);
    if ( v30 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v30);
    SafeFree(a1[36]);
    a1[36] = 0;
    v31 = RegistryPath::ReadStringValue(this, L"KerbEndpoint", (unsigned __int16 **)a1 + 36);
    if ( v31 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v31);
    SafeFree(a1[37]);
    a1[37] = 0;
    v32 = RegistryPath::ReadStringValue(this, L"CdjEndpointTLS", (unsigned __int16 **)a1 + 37);
    if ( v32 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v32);
    SafeFree(a1[38]);
    a1[38] = 0;
    v33 = RegistryPath::ReadStringValue(this, L"DeviceManagementEndpointTLS", (unsigned __int16 **)a1 + 38);
    if ( v33 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v33);
    SafeFree(a1[39]);
    a1[39] = 0;
    v34 = RegistryPath::ReadStringValue(this, L"DeviceJoinResourceEndpointTLS", (unsigned __int16 **)a1 + 39);
    if ( v34 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v34);
    if ( a3 )
    {
      v35 = JoinStatusStorage::SetDefaultDiscoveryMetadata(
              (struct struct_join_status *)a1,
              *(const unsigned __int16 **)this);
      if ( v35 < 0 )
        Logger::TraceError(
          L"%s: JoinStatusStorage::SetDefaultDiscoveryMetadata failed with error code: 0x%08x.",
          L"JoinStatusStorage::ReadTenantKey",
          (unsigned int)v35);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c680  mov     [rsp+arg_10], rbx
0x18000c685  mov     [rsp+arg_18], rbp
0x18000c68a  push    rsi
0x18000c68b  sub     rsp, 20h
0x18000c68f  mov     rsi, rcx
0x18000c692  mov     ebp, r8d
0x18000c695  mov     rcx, rdx; this
0x18000c698  mov     rbx, rdx
0x18000c69b  call    ?OpenSubKey@RegistryPath@@QEAAKKH@Z; RegistryPath::OpenSubKey(ulong,int)
0x18000c6a0  test    eax, eax
0x18000c6a2  jz      short loc_18000C6C6
0x18000c6a4  mov     r9d, eax
0x18000c6a7  lea     r8, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18000c6ae  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c6b5  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c6bc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c6c1  jmp     loc_18000CEB2
0x18000c6c6  mov     rcx, [rsi+20h]; lpMem
0x18000c6ca  mov     [rsp+28h+arg_0], rdi
0x18000c6cf  mov     [rsp+28h+arg_8], r14
0x18000c6d4  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c6d9  xor     r14d, r14d
0x18000c6dc  lea     r8, [rsi+20h]; unsigned __int16 **
0x18000c6e0  lea     rdx, aDisplayname; "DisplayName"
0x18000c6e7  mov     [rsi+20h], r14
0x18000c6eb  mov     rcx, rbx; this
0x18000c6ee  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c6f3  test    eax, eax
0x18000c6f5  jz      short loc_18000C714
0x18000c6f7  mov     r9d, eax
0x18000c6fa  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c701  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c708  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c70f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c714  mov     rcx, [rsi+28h]; lpMem
0x18000c718  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c71d  lea     r8, [rsi+28h]; unsigned __int16 **
0x18000c721  mov     [rsi+28h], r14
0x18000c725  lea     rdx, aMdmenrollmentu; "MdmEnrollmentUrl"
0x18000c72c  mov     rcx, rbx; this
0x18000c72f  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c734  test    eax, eax
0x18000c736  jz      short loc_18000C755
0x18000c738  mov     r9d, eax
0x18000c73b  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c742  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c749  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c750  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c755  mov     rcx, [rsi+30h]; lpMem
0x18000c759  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c75e  lea     r8, [rsi+30h]; unsigned __int16 **
0x18000c762  mov     [rsi+30h], r14
0x18000c766  lea     rdx, aMdmtermsofuseu; "MdmTermsOfUseUrl"
0x18000c76d  mov     rcx, rbx; this
0x18000c770  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c775  test    eax, eax
0x18000c777  jz      short loc_18000C796
0x18000c779  mov     r9d, eax
0x18000c77c  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c783  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c78a  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c791  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c796  mov     rcx, [rsi+38h]; lpMem
0x18000c79a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c79f  lea     r8, [rsi+38h]; unsigned __int16 **
0x18000c7a3  mov     [rsi+38h], r14
0x18000c7a7  lea     rdx, aMdmcomplianceu; "MdmComplianceUrl"
0x18000c7ae  mov     rcx, rbx; this
0x18000c7b1  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c7b6  test    eax, eax
0x18000c7b8  jz      short loc_18000C7D7
0x18000c7ba  mov     r9d, eax
0x18000c7bd  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c7c4  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c7cb  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c7d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c7d7  mov     rcx, [rsi+40h]; lpMem
0x18000c7db  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c7e0  lea     r8, [rsi+40h]; unsigned __int16 **
0x18000c7e4  mov     [rsi+40h], r14
0x18000c7e8  lea     rdx, aUsersettingsyn; "UserSettingSyncUrl"
0x18000c7ef  mov     rcx, rbx; this
0x18000c7f2  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c7f7  test    eax, eax
0x18000c7f9  jz      short loc_18000C818
0x18000c7fb  mov     r9d, eax
0x18000c7fe  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c805  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c80c  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c813  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c818  mov     rcx, [rsi+48h]; lpMem
0x18000c81c  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c821  lea     r8, [rsi+48h]; unsigned __int16 **
0x18000c825  mov     [rsi+48h], r14
0x18000c829  lea     rdx, aDrsservicevers; "DrsServiceVersion"
0x18000c830  mov     rcx, rbx; this
0x18000c833  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c838  test    eax, eax
0x18000c83a  jz      short loc_18000C859
0x18000c83c  mov     r9d, eax
0x18000c83f  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c846  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c84d  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c854  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c859  mov     rcx, [rsi+50h]; lpMem
0x18000c85d  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c862  lea     r8, [rsi+50h]; unsigned __int16 **
0x18000c866  mov     [rsi+50h], r14
0x18000c86a  lea     rdx, aDrsendpoint; "DrsEndpoint"
0x18000c871  mov     rcx, rbx; this
0x18000c874  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c879  test    eax, eax
0x18000c87b  jz      short loc_18000C89A
0x18000c87d  mov     r9d, eax
0x18000c880  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c887  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c88e  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c895  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c89a  mov     rcx, [rsi+58h]; lpMem
0x18000c89e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c8a3  lea     r8, [rsi+58h]; unsigned __int16 **
0x18000c8a7  mov     [rsi+58h], r14
0x18000c8ab  lea     rdx, aDrsresourceid; "DrsResourceId"
0x18000c8b2  mov     rcx, rbx; this
0x18000c8b5  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c8ba  test    eax, eax
0x18000c8bc  jz      short loc_18000C8DB
0x18000c8be  mov     r9d, eax
0x18000c8c1  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c8c8  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c8cf  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c8d6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c8db  mov     rcx, [rsi+60h]; lpMem
0x18000c8df  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c8e4  lea     r8, [rsi+60h]; unsigned __int16 **
0x18000c8e8  mov     [rsi+60h], r14
0x18000c8ec  lea     rdx, aAuthcodeurl; "AuthCodeUrl"
0x18000c8f3  mov     rcx, rbx; this
0x18000c8f6  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c8fb  test    eax, eax
0x18000c8fd  jz      short loc_18000C91C
0x18000c8ff  mov     r9d, eax
0x18000c902  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c909  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c910  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c917  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c91c  mov     rcx, [rsi+68h]; lpMem
0x18000c920  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c925  lea     r8, [rsi+68h]; unsigned __int16 **
0x18000c929  mov     [rsi+68h], r14
0x18000c92d  lea     rdx, aAccesstokenurl; "AccessTokenUrl"
0x18000c934  mov     rcx, rbx; this
0x18000c937  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c93c  test    eax, eax
0x18000c93e  jz      short loc_18000C95D
0x18000c940  mov     r9d, eax
0x18000c943  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c94a  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c951  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c958  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c95d  mov     rcx, [rsi+70h]; lpMem
0x18000c961  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c966  lea     r8, [rsi+70h]; unsigned __int16 **
0x18000c96a  mov     [rsi+70h], r14
0x18000c96e  lea     rdx, aCdjservicevers; "CdjServiceVersion"
0x18000c975  mov     rcx, rbx; this
0x18000c978  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c97d  test    eax, eax
0x18000c97f  jz      short loc_18000C99E
0x18000c981  mov     r9d, eax
0x18000c984  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c98b  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c992  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c999  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c99e  mov     rcx, [rsi+78h]; lpMem
0x18000c9a2  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c9a7  lea     r8, [rsi+78h]; unsigned __int16 **
0x18000c9ab  mov     [rsi+78h], r14
0x18000c9af  lea     rdx, aCdjendpoint; "CdjEndpoint"
0x18000c9b6  mov     rcx, rbx; this
0x18000c9b9  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000c9be  test    eax, eax
0x18000c9c0  jz      short loc_18000C9DF
0x18000c9c2  mov     r9d, eax
0x18000c9c5  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000c9cc  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000c9d3  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000c9da  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c9df  mov     rcx, [rsi+80h]; lpMem
0x18000c9e6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c9eb  lea     r8, [rsi+80h]; unsigned __int16 **
0x18000c9f2  mov     [rsi+80h], r14
0x18000c9f9  lea     rdx, aCdjresourceid; "CdjResourceId"
0x18000ca00  mov     rcx, rbx; this
0x18000ca03  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000ca08  test    eax, eax
0x18000ca0a  jz      short loc_18000CA29
0x18000ca0c  mov     r9d, eax
0x18000ca0f  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000ca16  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000ca1d  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000ca24  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ca29  mov     rcx, [rsi+88h]; lpMem
0x18000ca30  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000ca35  lea     r8, [rsi+88h]; unsigned __int16 **
0x18000ca3c  mov     [rsi+88h], r14
0x18000ca43  lea     rdx, aNgcservicevers; "NgcServiceVersion"
0x18000ca4a  mov     rcx, rbx; this
0x18000ca4d  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000ca52  test    eax, eax
0x18000ca54  jz      short loc_18000CA73
0x18000ca56  mov     r9d, eax
0x18000ca59  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000ca60  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000ca67  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000ca6e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ca73  mov     rcx, [rsi+90h]; lpMem
0x18000ca7a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000ca7f  lea     r8, [rsi+90h]; unsigned __int16 **
0x18000ca86  mov     [rsi+90h], r14
0x18000ca8d  lea     rdx, aNgcendpoint; "NgcEndpoint"
0x18000ca94  mov     rcx, rbx; this
0x18000ca97  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000ca9c  test    eax, eax
0x18000ca9e  jz      short loc_18000CABD
0x18000caa0  mov     r9d, eax
0x18000caa3  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000caaa  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000cab1  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000cab8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cabd  mov     rcx, [rsi+98h]; lpMem
0x18000cac4  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000cac9  lea     r8, [rsi+98h]; unsigned __int16 **
0x18000cad0  mov     [rsi+98h], r14
0x18000cad7  lea     rdx, aNgcresourceid; "NgcResourceId"
0x18000cade  mov     rcx, rbx; this
0x18000cae1  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000cae6  test    eax, eax
0x18000cae8  jz      short loc_18000CB07
0x18000caea  mov     r9d, eax
0x18000caed  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000caf4  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000cafb  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000cb02  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cb07  mov     rcx, [rsi+0A0h]; lpMem
0x18000cb0e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000cb13  lea     r8, [rsi+0A0h]; unsigned __int16 **
0x18000cb1a  mov     [rsi+0A0h], r14
0x18000cb21  lea     rdx, aWebauthnservic; "WebAuthnServiceVersion"
0x18000cb28  mov     rcx, rbx; this
0x18000cb2b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000cb30  test    eax, eax
0x18000cb32  jz      short loc_18000CB51
0x18000cb34  mov     r9d, eax
0x18000cb37  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000cb3e  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000cb45  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000cb4c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cb51  mov     rcx, [rsi+0A8h]; lpMem
0x18000cb58  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000cb5d  lea     r8, [rsi+0A8h]; unsigned __int16 **
0x18000cb64  mov     [rsi+0A8h], r14
0x18000cb6b  lea     rdx, aWebauthnendpoi; "WebAuthnEndpoint"
0x18000cb72  mov     rcx, rbx; this
0x18000cb75  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000cb7a  test    eax, eax
0x18000cb7c  jz      short loc_18000CB9B
0x18000cb7e  mov     r9d, eax
0x18000cb81  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000cb88  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000cb8f  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000cb96  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cb9b  mov     rcx, [rsi+0B0h]; lpMem
0x18000cba2  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000cba7  lea     r8, [rsi+0B0h]; unsigned __int16 **
0x18000cbae  mov     [rsi+0B0h], r14
0x18000cbb5  lea     rdx, aWebauthnresour; "WebAuthnResourceId"
0x18000cbbc  mov     rcx, rbx; this
0x18000cbbf  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000cbc4  test    eax, eax
0x18000cbc6  jz      short loc_18000CBE5
0x18000cbc8  mov     r9d, eax
0x18000cbcb  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000cbd2  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000cbd9  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000cbe0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cbe5  mov     rcx, [rsi+0B8h]; lpMem
0x18000cbec  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000cbf1  lea     r8, [rsi+0B8h]; unsigned __int16 **
0x18000cbf8  mov     [rsi+0B8h], r14
0x18000cbff  lea     rdx, aDevicemanageme_2; "DeviceManagementServiceVersion"
0x18000cc06  mov     rcx, rbx; this
0x18000cc09  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18000cc0e  test    eax, eax
0x18000cc10  jz      short loc_18000CC2F
0x18000cc12  mov     r9d, eax
0x18000cc15  lea     r8, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18000cc1c  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18000cc23  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000cc2a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
  ... truncated ...
```
