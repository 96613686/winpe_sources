# _lambda_b48b12c279374565a5bb5f751ab6a0db_::operator()

- ea: `0x1801a3c1c`
- end: `0x1801a3fe8`
- name: `_lambda_b48b12c279374565a5bb5f751ab6a0db_::operator()`
- size: `972`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801a3478`

## callees

- `0x18005b454`
- `0x180081370`
- `0x180086714`
- `0x18008db2c`
- `0x1800c4250`
- `0x1800ea404`
- `0x180125638`
- `0x180182da4`
- `0x1801999b0`
- `0x1801a3c1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3f88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801a3f53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801a3f53`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1801a3de7`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1801a3de7`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x1801a3e90`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x1801a3e90`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801a3d2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801a3d2e`

## string_xrefs

- `0x1801a3dc2`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3e5e`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3ee6`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3f3d`: `onecore\com\combase\registrationstore\privateuserhive.cpp`
- `0x1801a3c5e`: `\REGISTRY\USER\S-1-5-18\`
- `0x1801a3db0`: `RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()`
- `0x1801a3e55`: `RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()`
- `0x1801a3edd`: `RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()`
- `0x1801a3f34`: `RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()`

## pseudocode

```c
__int64 __fastcall lambda_b48b12c279374565a5bb5f751ab6a0db_::operator()(__int64 a1)
{
  HRESULT v2; // ebx
  wchar_t *v3; // rax
  const wchar_t *v4; // rcx
  __int64 v5; // rdx
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  unsigned int v21; // r8d
  _SECURITY_ATTRIBUTES *v22; // r9
  int v23; // eax
  const wchar_t *v24; // rdx
  LSTATUS v25; // eax
  const wchar_t *StringRawBuffer; // rax
  LSTATUS v27; // eax
  TraceLevel v28; // ecx
  HRESULT v29; // edi
  TraceLevel LevelPlus1; // ecx
  signed int LastError; // eax
  unsigned int *hkeyAncestor; // [rsp+28h] [rbp-D8h]
  RegistryKey templateKey; // [rsp+40h] [rbp-C0h] BYREF
  void *pSecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  _UNICODE_STRING keyPath; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t buffer[64]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t sddl[192]; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&keyPath.Length = 0x800000;
  keyPath.Buffer = buffer;
  v2 = RegistrationStoreData::CreateUniqueMountPath(L"\\REGISTRY\\USER\\S-1-5-18\\", &keyPath);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v3 = sddl;
  v4 = L"O:BAG:BAD:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;BA)(A;CIOI;KR;;;BU)(A;CIOI;KR;;;AC)(A;CIOI;KR;;;S-1-15-3-1024-1065365936-1"
        "281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)";
  v5 = 2;
  do
  {
    v6 = *((_OWORD *)v4 + 1);
    *(_OWORD *)v3 = *(_OWORD *)v4;
    v7 = *((_OWORD *)v4 + 2);
    *((_OWORD *)v3 + 1) = v6;
    v8 = *((_OWORD *)v4 + 3);
    *((_OWORD *)v3 + 2) = v7;
    v9 = *((_OWORD *)v4 + 4);
    *((_OWORD *)v3 + 3) = v8;
    v10 = *((_OWORD *)v4 + 5);
    *((_OWORD *)v3 + 4) = v9;
    v11 = *((_OWORD *)v4 + 6);
    *((_OWORD *)v3 + 5) = v10;
    v12 = *((_OWORD *)v4 + 7);
    v4 += 64;
    *((_OWORD *)v3 + 6) = v11;
    *((_OWORD *)v3 + 7) = v12;
    v3 += 64;
    --v5;
  }
  while ( v5 );
  v13 = *(_OWORD *)v4;
  v14 = *((_OWORD *)v4 + 1);
  pSecurityDescriptor = 0;
  *(_OWORD *)v3 = v13;
  v15 = *((_OWORD *)v4 + 2);
  *((_OWORD *)v3 + 1) = v14;
  v16 = *((_OWORD *)v4 + 3);
  *((_OWORD *)v3 + 2) = v15;
  v17 = *((_OWORD *)v4 + 4);
  *((_OWORD *)v3 + 3) = v16;
  v18 = *((_OWORD *)v4 + 5);
  *((_OWORD *)v3 + 4) = v17;
  v19 = *((_OWORD *)v4 + 6);
  *((_OWORD *)v3 + 5) = v18;
  v20 = *(_OWORD *)(v4 + 53);
  *((_OWORD *)v3 + 6) = v19;
  *(_OWORD *)(v3 + 53) = v20;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(sddl, 1u, &pSecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_45;
  }
  templateKey._hkey = 0;
  v23 = RegistryKey::StaticNtCreate(0, &keyPath, v21, v22, 0, 0, (HKEY__ **)&templateKey._hkey);
  v24 = L"hr:%!HRESULT!";
  v2 = v23;
  if ( v23 >= 0 )
  {
    if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
    {
LABEL_13:
      v25 = RegSetKeySecurity(templateKey._hkey, 7u, pSecurityDescriptor);
      v2 = v25;
      if ( v25 > 0 )
        v2 = (unsigned __int16)v25 | 0x80070000;
      if ( v2 >= 0 )
      {
        if ( !gfEnableTracing || !IsWppLevelEnabled(VERBOSE) )
          goto LABEL_23;
      }
      else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
      {
LABEL_31:
        v29 = RegistryKey::NtDelete(&templateKey);
        if ( v29 >= 0 )
        {
          if ( !gfEnableTracing )
          {
LABEL_36:
            if ( v2 >= 0 )
              v2 = v29;
            goto LABEL_38;
          }
          LevelPlus1 = VERBOSE;
        }
        else
        {
          LevelPlus1 = Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1;
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
          {
LABEL_35:
            LODWORD(hkeyAncestor) = v29;
            ComTraceHr(
              v29,
              "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
              "RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()",
              627,
              L"hr:%!HRESULT!",
              hkeyAncestor);
            goto LABEL_36;
          }
          if ( !gfEnableTracing )
            goto LABEL_36;
        }
        if ( !IsWppLevelEnabled(LevelPlus1) )
          goto LABEL_36;
        goto LABEL_35;
      }
      LODWORD(hkeyAncestor) = v2;
      ComTraceHr(
        v2,
        "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
        "RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()",
        613,
        L"hr:%!HRESULT!",
        hkeyAncestor);
      if ( v2 < 0 )
        goto LABEL_31;
LABEL_23:
      StringRawBuffer = WindowsGetStringRawBuffer(**(HSTRING **)a1, 0);
      v27 = RegSaveKeyExW(templateKey._hkey, StringRawBuffer, 0, 2u);
      v2 = v27;
      if ( v27 > 0 )
        v2 = (unsigned __int16)v27 | 0x80070000;
      if ( v2 >= 0 )
      {
        if ( !gfEnableTracing )
          goto LABEL_31;
        v28 = VERBOSE;
      }
      else
      {
        if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
        {
LABEL_30:
          LODWORD(hkeyAncestor) = v2;
          ComTraceHr(
            v2,
            "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
            "RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()",
            622,
            L"hr:%!HRESULT!",
            hkeyAncestor);
          goto LABEL_31;
        }
        if ( !gfEnableTracing )
          goto LABEL_31;
        v28 = ERRORS;
      }
      if ( !IsWppLevelEnabled(v28) )
        goto LABEL_31;
      goto LABEL_30;
    }
  }
  else if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 && (!gfEnableTracing || !IsWppLevelEnabled(ERRORS)) )
  {
    goto LABEL_38;
  }
  LODWORD(hkeyAncestor) = v2;
  ComTraceHr(
    v2,
    "onecore\\com\\combase\\registrationstore\\privateuserhive.cpp",
    "RegistrationStoreData::PrivateHive::Create::<lambda_b48b12c279374565a5bb5f751ab6a0db>::operator ()",
    605,
    v24,
    hkeyAncestor);
  if ( v2 >= 0 )
    goto LABEL_13;
LABEL_38:
  LocalFree(pSecurityDescriptor);
  RegistryKey::Close(&templateKey);
LABEL_45:
  if ( v2 >= 0 )
    return (unsigned int)RegistrationStoreData::PrivateHive::LoadAppKey(
                           **(HSTRING__ ***)(a1 + 8),
                           **(HSTRING__ ***)a1,
                           0xF003Fu,
                           *(RegistryKey **)(a1 + 16));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1801a3c1c  mov     [rsp-8+arg_8], rbx
0x1801a3c21  mov     [rsp-8+arg_10], rsi
0x1801a3c26  push    rbp
0x1801a3c27  push    rdi
0x1801a3c28  push    r14
0x1801a3c2a  lea     rbp, [rsp-170h]
0x1801a3c32  sub     rsp, 270h
0x1801a3c39  mov     rax, cs:__security_cookie
0x1801a3c40  xor     rax, rsp
0x1801a3c43  mov     [rbp+180h+var_20], rax
0x1801a3c4a  mov     rsi, this
0x1801a3c4d  mov     qword ptr [rsp+280h+keyPath.Length], 800000h
0x1801a3c56  lea     rax, [rsp+280h+buffer]
0x1801a3c5b  xor     r14d, r14d
0x1801a3c5e  lea     this, aRegistryUserS1; "\\REGISTRY\\USER\\S-1-5-18\\"
0x1801a3c65  mov     [rsp+280h+keyPath.Buffer], rax
0x1801a3c6a  lea     rdx, [rsp+280h+keyPath]; mountPath
0x1801a3c6f  mov     edi, 80h
0x1801a3c74  call    ?CreateUniqueMountPath@RegistrationStoreData@@YAJPEBGAEAU_UNICODE_STRING@@@Z; RegistrationStoreData::CreateUniqueMountPath(ushort const *,_UNICODE_STRING &)
0x1801a3c79  mov     ebx, eax
0x1801a3c7b  test    eax, eax
0x1801a3c7d  js      loc_1801A3FBF
0x1801a3c83  lea     rax, [rbp+180h+sddl]
0x1801a3c87  lea     this, aOBagBadACioiKa; "O:BAG:BAD:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;"...
0x1801a3c8e  lea     edx, [rdi-7Eh]
0x1801a3c91  movups  xmm0, xmmword ptr [this]
0x1801a3c94  movups  xmm1, xmmword ptr [this+10h]
0x1801a3c98  movups  xmmword ptr [rax], xmm0
0x1801a3c9b  movups  xmm0, xmmword ptr [this+20h]
0x1801a3c9f  movups  xmmword ptr [rax+10h], xmm1
0x1801a3ca3  movups  xmm1, xmmword ptr [this+30h]
0x1801a3ca7  movups  xmmword ptr [rax+20h], xmm0
0x1801a3cab  movups  xmm0, xmmword ptr [this+40h]
0x1801a3caf  movups  xmmword ptr [rax+30h], xmm1
0x1801a3cb3  movups  xmm1, xmmword ptr [this+50h]
0x1801a3cb7  movups  xmmword ptr [rax+40h], xmm0
0x1801a3cbb  movups  xmm0, xmmword ptr [this+60h]
0x1801a3cbf  movups  xmmword ptr [rax+50h], xmm1
0x1801a3cc3  movups  xmm1, xmmword ptr [this+70h]
0x1801a3cc7  add     this, rdi
0x1801a3cca  movups  xmmword ptr [rax+60h], xmm0
0x1801a3cce  movups  xmmword ptr [rax+70h], xmm1
0x1801a3cd2  add     rax, rdi
0x1801a3cd5  sub     rdx, 1
0x1801a3cd9  jnz     short loc_1801A3C91
0x1801a3cdb  movups  xmm0, xmmword ptr [this]
0x1801a3cde  xor     r9d, r9d; SecurityDescriptorSize
0x1801a3ce1  lea     r8, [rsp+280h+pSecurityDescriptor]; SecurityDescriptor
0x1801a3ce6  movups  xmm1, xmmword ptr [this+10h]
0x1801a3cea  mov     [rsp+280h+pSecurityDescriptor], r14
0x1801a3cef  movups  xmmword ptr [rax], xmm0
0x1801a3cf2  lea     edx, [r9+1]; StringSDRevision
0x1801a3cf6  movups  xmm0, xmmword ptr [this+20h]
0x1801a3cfa  movups  xmmword ptr [rax+10h], xmm1
0x1801a3cfe  movups  xmm1, xmmword ptr [this+30h]
0x1801a3d02  movups  xmmword ptr [rax+20h], xmm0
0x1801a3d06  movups  xmm0, xmmword ptr [this+40h]
0x1801a3d0a  movups  xmmword ptr [rax+30h], xmm1
0x1801a3d0e  movups  xmm1, xmmword ptr [this+50h]
0x1801a3d12  movups  xmmword ptr [rax+40h], xmm0
0x1801a3d16  movups  xmm0, xmmword ptr [this+60h]
0x1801a3d1a  movups  xmmword ptr [rax+50h], xmm1
0x1801a3d1e  movups  xmm1, xmmword ptr [this+6Ah]
0x1801a3d22  lea     this, [rbp+180h+sddl]; StringSecurityDescriptor
0x1801a3d26  movups  xmmword ptr [rax+60h], xmm0
0x1801a3d2a  movups  xmmword ptr [rax+6Ah], xmm1
0x1801a3d2e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801a3d34  test    eax, eax
0x1801a3d36  jz      loc_1801A3F88
0x1801a3d3c  lea     rax, [rsp+280h+templateKey]
0x1801a3d41  mov     [rsp+280h+templateKey._hkey], r14
0x1801a3d46  mov     [rsp+280h+subKeyPath], rax; subKeyPath
0x1801a3d4b  lea     rdx, [rsp+280h+keyPath]; subKeyPath
0x1801a3d50  mov     [rsp+280h+hkeyAncestor], r14; hkeyAncestor
0x1801a3d55  xor     ecx, ecx; hkeyAncestor
0x1801a3d57  mov     [rsp+280h+phkey], r14d; phkey
0x1801a3d5c  call    ?StaticNtCreate@RegistryKey@@CAJPEAUHKEY__@@AEBU_UNICODE_STRING@@KPEAU_SECURITY_ATTRIBUTES@@KPEAKPEAPEAU2@@Z; RegistryKey::StaticNtCreate(HKEY__ *,_UNICODE_STRING const &,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong *,HKEY__ * *)
0x1801a3d61  lea     rdx, aHrHresult; "hr:%!HRESULT!"
0x1801a3d68  mov     ebx, eax
0x1801a3d6a  test    eax, eax
0x1801a3d6c  jns     short loc_1801A3D95
0x1801a3d6e  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a3d74  test    eax, eax
0x1801a3d76  jnz     short loc_1801A3DAC
0x1801a3d78  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3d7f  jz      loc_1801A3F4E
0x1801a3d85  xor     ecx, ecx; level
0x1801a3d87  call    IsWppLevelEnabled
0x1801a3d8c  test    al, al
0x1801a3d8e  jnz     short loc_1801A3DAC
0x1801a3d90  jmp     loc_1801A3F4E
0x1801a3d95  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3d9c  jz      short loc_1801A3DD8
0x1801a3d9e  mov     ecx, 3; level
0x1801a3da3  call    IsWppLevelEnabled
0x1801a3da8  test    al, al
0x1801a3daa  jz      short loc_1801A3DD8
0x1801a3dac  mov     dword ptr [rsp+280h+hkeyAncestor], ebx
0x1801a3db0  lea     r8, aRegistrationst_31; "RegistrationStoreData::PrivateHive::Cre"...
0x1801a3db7  mov     qword ptr [rsp+280h+phkey], rdx; format
0x1801a3dbc  mov     r9d, 25Dh; line
0x1801a3dc2  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a3dc9  mov     ecx, ebx; hr
0x1801a3dcb  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3dd0  test    ebx, ebx
0x1801a3dd2  js      loc_1801A3F4E
0x1801a3dd8  mov     r8, [rsp+280h+pSecurityDescriptor]; pSecurityDescriptor
0x1801a3ddd  mov     edx, 7; SecurityInformation
0x1801a3de2  mov     this, [rsp+280h+templateKey._hkey]; hKey
0x1801a3de7  call    cs:__imp_RegSetKeySecurity
0x1801a3ded  mov     ebx, eax
0x1801a3def  mov     edi, 80070000h
0x1801a3df4  test    eax, eax
0x1801a3df6  jle     short loc_1801A3DFD
0x1801a3df8  movzx   ebx, ax
0x1801a3dfb  or      ebx, edi
0x1801a3dfd  test    ebx, ebx
0x1801a3dff  jns     short loc_1801A3E28
0x1801a3e01  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a3e07  test    eax, eax
0x1801a3e09  jnz     short loc_1801A3E3F
0x1801a3e0b  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3e12  jz      loc_1801A3EF2
0x1801a3e18  xor     ecx, ecx; level
0x1801a3e1a  call    IsWppLevelEnabled
0x1801a3e1f  test    al, al
0x1801a3e21  jnz     short loc_1801A3E3F
0x1801a3e23  jmp     loc_1801A3EF2
0x1801a3e28  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3e2f  jz      short loc_1801A3E72
0x1801a3e31  mov     ecx, 3; level
0x1801a3e36  call    IsWppLevelEnabled
0x1801a3e3b  test    al, al
0x1801a3e3d  jz      short loc_1801A3E72
0x1801a3e3f  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x1801a3e46  mov     dword ptr [rsp+280h+hkeyAncestor], ebx
0x1801a3e4a  mov     r9d, 265h; line
0x1801a3e50  mov     qword ptr [rsp+280h+phkey], rax; format
0x1801a3e55  lea     r8, aRegistrationst_31; "RegistrationStoreData::PrivateHive::Cre"...
0x1801a3e5c  mov     ecx, ebx; hr
0x1801a3e5e  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a3e65  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3e6a  test    ebx, ebx
0x1801a3e6c  js      loc_1801A3EF2
0x1801a3e72  mov     this, [rsi]
0x1801a3e75  xor     edx, edx; length
0x1801a3e77  mov     this, [this]; string
0x1801a3e7a  call    WindowsGetStringRawBuffer
0x1801a3e7f  mov     this, [rsp+280h+templateKey._hkey]; hKey
0x1801a3e84  mov     r9d, 2; Flags
0x1801a3e8a  xor     r8d, r8d; lpSecurityAttributes
0x1801a3e8d  mov     rdx, rax; lpFile
0x1801a3e90  call    cs:__imp_RegSaveKeyExW
0x1801a3e96  mov     ebx, eax
0x1801a3e98  test    eax, eax
0x1801a3e9a  jle     short loc_1801A3EA1
0x1801a3e9c  movzx   ebx, ax
0x1801a3e9f  or      ebx, edi
0x1801a3ea1  test    ebx, ebx
0x1801a3ea3  jns     loc_1801A3F65
0x1801a3ea9  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x1801a3eaf  test    eax, eax
0x1801a3eb1  jnz     short loc_1801A3EC7
0x1801a3eb3  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3eba  jz      short loc_1801A3EF2
0x1801a3ebc  xor     ecx, ecx; level
0x1801a3ebe  call    IsWppLevelEnabled
0x1801a3ec3  test    al, al
0x1801a3ec5  jz      short loc_1801A3EF2
0x1801a3ec7  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x1801a3ece  mov     dword ptr [rsp+280h+hkeyAncestor], ebx
0x1801a3ed2  mov     r9d, 26Eh; line
0x1801a3ed8  mov     qword ptr [rsp+280h+phkey], rax; format
0x1801a3edd  lea     r8, aRegistrationst_31; "RegistrationStoreData::PrivateHive::Cre"...
0x1801a3ee4  mov     ecx, ebx; hr
0x1801a3ee6  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a3eed  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3ef2  lea     this, [rsp+280h+templateKey]; this
0x1801a3ef7  call    ?NtDelete@RegistryKey@@QEAAJXZ; RegistryKey::NtDelete(void)
0x1801a3efc  mov     edi, eax
0x1801a3efe  test    eax, eax
0x1801a3f00  jns     short loc_1801A3F78
0x1801a3f02  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x1801a3f08  test    ecx, ecx
0x1801a3f0a  jnz     short loc_1801A3F1E
0x1801a3f0c  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3f13  jz      short loc_1801A3F49
0x1801a3f15  call    IsWppLevelEnabled
0x1801a3f1a  test    al, al
0x1801a3f1c  jz      short loc_1801A3F49
0x1801a3f1e  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x1801a3f25  mov     dword ptr [rsp+280h+hkeyAncestor], edi
0x1801a3f29  mov     r9d, 273h; line
0x1801a3f2f  mov     qword ptr [rsp+280h+phkey], rax; format
0x1801a3f34  lea     r8, aRegistrationst_31; "RegistrationStoreData::PrivateHive::Cre"...
0x1801a3f3b  mov     ecx, edi; hr
0x1801a3f3d  lea     rdx, aOnecoreComComb_71; "onecore\\com\\combase\\registrationstor"...
0x1801a3f44  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x1801a3f49  test    ebx, ebx
0x1801a3f4b  cmovns  ebx, edi
0x1801a3f4e  mov     this, [rsp+280h+pSecurityDescriptor]; hMem
0x1801a3f53  call    cs:__imp_LocalFree
0x1801a3f59  lea     this, [rsp+280h+templateKey]; this
0x1801a3f5e  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x1801a3f63  jmp     short loc_1801A3F9D
0x1801a3f65  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3f6c  jz      short loc_1801A3EF2
0x1801a3f6e  mov     ecx, 3
0x1801a3f73  jmp     loc_1801A3EBE
0x1801a3f78  cmp     cs:?gfEnableTracing@@3HA, r14d; int gfEnableTracing
0x1801a3f7f  jz      short loc_1801A3F49
0x1801a3f81  mov     ecx, 3
0x1801a3f86  jmp     short loc_1801A3F15
0x1801a3f88  call    cs:__imp_GetLastError
0x1801a3f8e  mov     ebx, eax
0x1801a3f90  test    eax, eax
0x1801a3f92  jle     short loc_1801A3F9D
0x1801a3f94  movzx   ebx, ax
0x1801a3f97  or      ebx, 80070000h
0x1801a3f9d  test    ebx, ebx
0x1801a3f9f  js      short loc_1801A3FBF
0x1801a3fa1  mov     rdx, [rsi]
0x1801a3fa4  mov     r8d, 0F003Fh; samDesired
0x1801a3faa  mov     this, [rsi+8]
0x1801a3fae  mov     r9, [rsi+10h]; hiveKey
0x1801a3fb2  mov     rdx, [rdx]; privateHivePath
0x1801a3fb5  mov     this, [this]; packageId
0x1801a3fb8  call    ?LoadAppKey@PrivateHive@RegistrationStoreData@@SAJPEAUHSTRING__@@0KAEAVRegistryKey@@@Z; RegistrationStoreData::PrivateHive::LoadAppKey(HSTRING__ *,HSTRING__ *,ulong,RegistryKey &)
0x1801a3fbd  mov     ebx, eax
0x1801a3fbf  mov     eax, ebx
0x1801a3fc1  mov     this, [rbp+180h+var_20]
0x1801a3fc8  xor     this, rsp; StackCookie
0x1801a3fcb  call    __security_check_cookie
0x1801a3fd0  lea     r11, [rsp+280h+var_10]
0x1801a3fd8  mov     rbx, [r11+28h]
0x1801a3fdc  mov     rsi, [r11+30h]
0x1801a3fe0  mov     rsp, r11
0x1801a3fe3  pop     r14
0x1801a3fe5  pop     rdi
0x1801a3fe6  pop     rbp
0x1801a3fe7  retn
```
