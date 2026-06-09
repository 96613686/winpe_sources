# JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)

- ea: `0x180008ad0`
- end: `0x180008edc`
- name: `?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z`
- size: `1036`
- prototype: `static int(int, const struct _CERT_CONTEXT *, int, struct struct_join_status *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180025788`

## callees

- `0x1800073c0`
- `0x180008ad0`
- `0x180009a70`
- `0x18000a178`
- `0x18000a2a0`
- `0x18000bfc0`
- `0x18000c680`
- `0x18000ced0`
- `0x18000d770`
- `0x180010dd0`
- `0x180027278`
- `0x180027448`
- `0x18002e664`
- `0x180044c94`
- `0x180046a4c`

## string_xrefs

- `0x180008b44`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008b6b`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008b85`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008ba7`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008bfc`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008cf7`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008d3e`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008d8e`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008de1`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008e29`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008e6d`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008ea3`: `JoinStatusStorage::ReadJoinStatus`
- `0x180008c27`: `RegistrationCertStatus::GetTenantIdExtensionValue`
- `0x180008d34`: `JoinStatusStorage::ReadDeviceKey`
- `0x180008cf0`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x180008e22`: `RegistryPath::Append`
- `0x180008c76`: `CopyStringW`
- `0x180008e63`: `JoinStatusStorage::ReadTenantKey`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadJoinStatus(int a1, const struct _CERT_CONTEXT *a2, int a3, void **a4, int a5)
{
  const wchar_t *v5; // r14
  const wchar_t *v9; // r13
  unsigned __int16 *v10; // r15
  __int64 ExtensionGuidValueByOid; // rbx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // r8
  const wchar_t *v14; // r15
  int ExistingDeviceKeyPath; // eax
  const wchar_t *v16; // rax
  unsigned __int16 *v17; // rcx
  int v18; // r8d
  const wchar_t *v19; // rax
  int v20; // r8d
  int v21; // edx
  const wchar_t *v22; // rax
  const unsigned __int16 *v23; // rdx
  unsigned int v24; // eax
  int TenantKey; // eax
  unsigned __int16 *v27; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v28[4]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v29; // [rsp+60h] [rbp-20h]
  __int64 v30; // [rsp+70h] [rbp-10h]
  __int64 v31; // [rsp+78h] [rbp-8h]
  void *Block; // [rsp+C8h] [rbp+48h] BYREF

  v5 = L"TRUE";
  v27 = 0;
  Block = 0;
  memset(v28, 0, sizeof(v28));
  v30 = 0;
  v9 = L"TRUE";
  v29 = 0;
  if ( !a1 )
    v9 = L"FALSE";
  v31 = 0;
  v10 = 0;
  Logger::TraceVerbose(L"%s started. %s: %s.", L"JoinStatusStorage::ReadJoinStatus", L"isDevice", v9);
  if ( !a2 )
  {
    LODWORD(ExtensionGuidValueByOid) = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::ReadJoinStatus", L"pCert");
    v12 = L"pCert";
LABEL_5:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"JoinStatusStorage::ReadJoinStatus", v12);
    goto LABEL_42;
  }
  if ( !a4 )
  {
    LODWORD(ExtensionGuidValueByOid) = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::ReadJoinStatus", L"pJoinStatus");
    v12 = L"pJoinStatus";
    goto LABEL_5;
  }
  ExtensionGuidValueByOid = (unsigned int)CertificateUtil::FindExtensionGuidValueByOid(
                                            "1.2.840.113556.1.5.284.2",
                                            a2,
                                            &v27);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetDeviceId", ExtensionGuidValueByOid);
  if ( (int)ExtensionGuidValueByOid < 0 )
  {
    v13 = L"RegistrationCertStatus::GetDeviceId";
LABEL_10:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::ReadJoinStatus",
      v13,
      (unsigned int)ExtensionGuidValueByOid);
    goto LABEL_42;
  }
  v14 = L"RegistrationCertStatus::GetTenantIdExtensionValue";
  ExtensionGuidValueByOid = (unsigned int)CertificateUtil::FindExtensionGuidValueByOid(
                                            "1.2.840.113556.1.5.284.5",
                                            a2,
                                            (unsigned __int16 **)&Block);
  Logger::TraceVerbose(
    L"%s - hr: 0x%08x",
    L"RegistrationCertStatus::GetTenantIdExtensionValue",
    ExtensionGuidValueByOid);
  if ( (_DWORD)ExtensionGuidValueByOid == -2146885628 )
  {
    operator delete(Block);
    Block = 0;
    LODWORD(ExtensionGuidValueByOid) = CopyStringW(
                                         L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e",
                                         0x24u,
                                         (unsigned __int16 **)&Block);
    if ( (int)ExtensionGuidValueByOid < 0 )
    {
      v14 = L"CopyStringW";
LABEL_15:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationCertStatus::GetTenantId",
        v14,
        (unsigned int)ExtensionGuidValueByOid);
      operator delete(Block);
      v10 = 0;
      goto LABEL_17;
    }
  }
  else if ( (int)ExtensionGuidValueByOid < 0 )
  {
    goto LABEL_15;
  }
  v10 = (unsigned __int16 *)Block;
LABEL_17:
  Logger::TraceVerbose(
    L"%s - hr: 0x%08x",
    L"RegistrationCertStatus::GetTenantId",
    (unsigned int)ExtensionGuidValueByOid);
  if ( (int)ExtensionGuidValueByOid < 0 )
  {
    v13 = L"RegistrationCertStatus::GetTenantId";
    goto LABEL_10;
  }
  ExistingDeviceKeyPath = JoinStatusStorage::GetExistingDeviceKeyPath(a1, a2, (struct RegistryPath *)v28);
  LODWORD(ExtensionGuidValueByOid) = ExistingDeviceKeyPath;
  if ( ExistingDeviceKeyPath >= 0 )
  {
    LODWORD(ExtensionGuidValueByOid) = JoinStatusStorage::ReadDeviceKey(
                                         (struct struct_join_status *)a4,
                                         (struct RegistryPath *)v28,
                                         a3);
    if ( (int)ExtensionGuidValueByOid >= 0 )
      goto LABEL_25;
    v16 = L"TRUE";
    if ( !a3 )
      v16 = L"FALSE";
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
      L"JoinStatusStorage::ReadJoinStatus",
      L"JoinStatusStorage::ReadDeviceKey",
      (unsigned int)ExtensionGuidValueByOid,
      v16);
    if ( a3 )
    {
LABEL_25:
      SafeFree(*a4);
      v17 = v27;
      *a4 = 0;
      LODWORD(ExtensionGuidValueByOid) = StringDup(v17, (unsigned __int16 **)a4, v18);
      if ( (int)ExtensionGuidValueByOid >= 0 )
        goto LABEL_29;
      v19 = L"TRUE";
      if ( !a3 )
        v19 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"JoinStatusStorage::ReadJoinStatus",
        L"StringDup",
        (unsigned int)ExtensionGuidValueByOid,
        v19);
      if ( a3 )
      {
LABEL_29:
        SafeFree(a4[2]);
        a4[2] = 0;
        LODWORD(ExtensionGuidValueByOid) = StringDup(v10, (unsigned __int16 **)a4 + 2, v20);
        if ( (int)ExtensionGuidValueByOid >= 0 )
          goto LABEL_33;
        v22 = L"TRUE";
        if ( !a3 )
          v22 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"JoinStatusStorage::ReadJoinStatus",
          L"StringDup",
          (unsigned int)ExtensionGuidValueByOid,
          v22);
        if ( a3 )
        {
LABEL_33:
          RegistryPath::Pop((RegistryPath *)v28, v21);
          v24 = RegistryPath::Append((RegistryPath *)v28, v23, v10);
          LODWORD(ExtensionGuidValueByOid) = v24;
          if ( v24 )
          {
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"JoinStatusStorage::ReadJoinStatus",
              L"RegistryPath::Append",
              v24);
            if ( (int)ExtensionGuidValueByOid > 0 )
              LODWORD(ExtensionGuidValueByOid) = (unsigned __int16)ExtensionGuidValueByOid | 0x80070000;
          }
          else
          {
            TenantKey = JoinStatusStorage::ReadTenantKey(a4, (struct RegistryPath *)v28, a5);
            LODWORD(ExtensionGuidValueByOid) = TenantKey;
            if ( TenantKey >= 0 )
              goto LABEL_40;
            if ( !a3 )
              v5 = L"FALSE";
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
              L"JoinStatusStorage::ReadJoinStatus",
              L"JoinStatusStorage::ReadTenantKey",
              (unsigned int)TenantKey,
              v5);
            if ( a3 )
            {
LABEL_40:
              if ( a3 )
                LODWORD(ExtensionGuidValueByOid) = 0;
            }
          }
        }
      }
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s(%s) failed with error code: 0x%08x.",
      L"JoinStatusStorage::ReadJoinStatus",
      L"JoinStatusStorage::GetExistingDeviceKeyPath",
      v9,
      ExistingDeviceKeyPath);
  }
LABEL_42:
  operator delete(v27);
  operator delete(v10);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"JoinStatusStorage::ReadJoinStatus", (unsigned int)ExtensionGuidValueByOid);
  RegistryPath::Reset((RegistryPath *)v28);
  return (unsigned int)ExtensionGuidValueByOid;
}

```

## disassembly

```asm
0x180008ad0  mov     [rsp-38h+arg_10], rbx
0x180008ad5  mov     [rsp-38h+arg_0], ecx
0x180008ad9  push    rbp
0x180008ada  push    rsi
0x180008adb  push    rdi
0x180008adc  push    r12
0x180008ade  push    r13
0x180008ae0  push    r14
0x180008ae2  push    r15
0x180008ae4  mov     rbp, rsp
0x180008ae7  sub     rsp, 80h
0x180008aee  xor     ebx, ebx
0x180008af0  lea     r14, aTrue; "TRUE"
0x180008af7  mov     eax, ecx
0x180008af9  mov     [rbp+var_50], rbx
0x180008afd  test    eax, eax
0x180008aff  mov     [rbp+Block], rbx
0x180008b03  lea     rcx, aFalse; "FALSE"
0x180008b0a  mov     [rbp+var_40], rbx
0x180008b0e  mov     rsi, r9
0x180008b11  mov     [rbp+var_38], rbx
0x180008b15  mov     edi, r8d
0x180008b18  mov     [rbp+var_30], rbx
0x180008b1c  mov     r12, rdx
0x180008b1f  mov     [rbp+var_28], rbx
0x180008b23  xorps   xmm0, xmm0
0x180008b26  mov     [rbp+var_10], rbx
0x180008b2a  mov     r13, r14
0x180008b2d  movdqa  [rbp+var_20], xmm0
0x180008b32  cmovz   r13, rcx
0x180008b36  mov     [rbp+var_8], rbx
0x180008b3a  mov     r9, r13
0x180008b3d  lea     r8, aIsdevice; "isDevice"
0x180008b44  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008b4b  mov     r15d, ebx
0x180008b4e  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x180008b55  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008b5a  test    r12, r12
0x180008b5d  jnz     short loc_180008B96
0x180008b5f  lea     r8, aPcert; "pCert"
0x180008b66  mov     ebx, 80070057h
0x180008b6b  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008b72  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180008b79  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008b7e  lea     rdx, aPcert; "pCert"
0x180008b85  lea     rcx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008b8c  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180008b91  jmp     loc_180008E8F
0x180008b96  test    rsi, rsi
0x180008b99  jnz     short loc_180008BC3
0x180008b9b  lea     r8, aPjoinstatus; "pJoinStatus"
0x180008ba2  mov     ebx, 80070057h
0x180008ba7  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008bae  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180008bb5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008bba  lea     rdx, aPjoinstatus; "pJoinStatus"
0x180008bc1  jmp     short loc_180008B85
0x180008bc3  lea     r8, [rbp+var_50]; unsigned __int16 **
0x180008bc7  mov     rdx, r12; struct _CERT_CONTEXT *
0x180008bca  lea     rcx, a12840113556152_0; "1.2.840.113556.1.5.284.2"
0x180008bd1  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180008bd6  mov     ebx, eax
0x180008bd8  mov     r8d, eax
0x180008bdb  lea     rdx, aRegistrationce_4; "RegistrationCertStatus::GetDeviceId"
0x180008be2  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180008be9  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008bee  test    ebx, ebx
0x180008bf0  jns     short loc_180008C14
0x180008bf2  lea     r8, aRegistrationce_4; "RegistrationCertStatus::GetDeviceId"
0x180008bf9  mov     r9d, ebx
0x180008bfc  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008c03  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180008c0a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008c0f  jmp     loc_180008E8F
0x180008c14  lea     r8, [rbp+Block]; unsigned __int16 **
0x180008c18  mov     rdx, r12; struct _CERT_CONTEXT *
0x180008c1b  lea     rcx, a12840113556152; "1.2.840.113556.1.5.284.5"
0x180008c22  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180008c27  lea     r15, aRegistrationce_0; "RegistrationCertStatus::GetTenantIdExte"...
0x180008c2e  mov     r8d, eax
0x180008c31  mov     rdx, r15
0x180008c34  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180008c3b  mov     ebx, eax
0x180008c3d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008c42  cmp     ebx, 80092004h
0x180008c48  jnz     short loc_180008C7F
0x180008c4a  mov     rcx, [rbp+Block]; Block
0x180008c4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008c53  lea     r8, [rbp+Block]; unsigned __int16 **
0x180008c57  mov     [rbp+Block], 0
0x180008c5f  mov     edx, 24h ; '$'; unsigned __int64
0x180008c64  lea     rcx, Source; "383a3889-5bc9-47a3-846c-2b70f0b7fe0e"
0x180008c6b  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x180008c70  mov     ebx, eax
0x180008c72  test    eax, eax
0x180008c74  jns     short loc_180008CAA
0x180008c76  lea     r15, aCopystringw; "CopyStringW"
0x180008c7d  jmp     short loc_180008C83
0x180008c7f  test    ebx, ebx
0x180008c81  jns     short loc_180008CAA
0x180008c83  lea     rdx, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x180008c8a  mov     r9d, ebx
0x180008c8d  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180008c94  mov     r8, r15
0x180008c97  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008c9c  mov     rcx, [rbp+Block]; Block
0x180008ca0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008ca5  xor     r15d, r15d
0x180008ca8  jmp     short loc_180008CAE
0x180008caa  mov     r15, [rbp+Block]
0x180008cae  mov     r8d, ebx
0x180008cb1  lea     rdx, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x180008cb8  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180008cbf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008cc4  test    ebx, ebx
0x180008cc6  jns     short loc_180008CD4
0x180008cc8  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x180008ccf  jmp     loc_180008BF9
0x180008cd4  mov     ecx, [rbp+arg_0]; int
0x180008cd7  lea     r8, [rbp+var_40]; struct RegistryPath *
0x180008cdb  mov     rdx, r12; struct _CERT_CONTEXT *
0x180008cde  call    ?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z; JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)
0x180008ce3  mov     ebx, eax
0x180008ce5  test    eax, eax
0x180008ce7  jns     short loc_180008D0F
0x180008ce9  mov     r9, r13
0x180008cec  mov     dword ptr [rsp+80h+var_60], eax
0x180008cf0  lea     r8, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x180008cf7  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008cfe  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x180008d05  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008d0a  jmp     loc_180008E8F
0x180008d0f  mov     r8d, edi; int
0x180008d12  lea     rdx, [rbp+var_40]; struct RegistryPath *
0x180008d16  mov     rcx, rsi; struct struct_join_status *
0x180008d19  call    ?ReadDeviceKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z; JoinStatusStorage::ReadDeviceKey(struct_join_status *,RegistryPath &,int)
0x180008d1e  lea     r12, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180008d25  mov     ebx, eax
0x180008d27  lea     r13, aFalse; "FALSE"
0x180008d2e  test    eax, eax
0x180008d30  jns     short loc_180008D61
0x180008d32  test    edi, edi
0x180008d34  lea     r8, aJoinstatusstor; "JoinStatusStorage::ReadDeviceKey"
0x180008d3b  mov     rax, r14
0x180008d3e  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008d45  cmovz   rax, r13
0x180008d49  mov     r9d, ebx
0x180008d4c  mov     rcx, r12; unsigned __int16 *
0x180008d4f  mov     [rsp+80h+var_60], rax
0x180008d54  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008d59  test    edi, edi
0x180008d5b  jz      loc_180008E8F
0x180008d61  mov     rcx, [rsi]; lpMem
0x180008d64  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008d69  mov     rcx, [rbp+var_50]; unsigned __int16 *
0x180008d6d  mov     rdx, rsi; unsigned __int16 **
0x180008d70  mov     qword ptr [rsi], 0
0x180008d77  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180008d7c  mov     ebx, eax
0x180008d7e  test    eax, eax
0x180008d80  jns     short loc_180008DB1
0x180008d82  test    edi, edi
0x180008d84  lea     r8, aStringdup; "StringDup"
0x180008d8b  mov     rax, r14
0x180008d8e  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008d95  cmovz   rax, r13
0x180008d99  mov     r9d, ebx
0x180008d9c  mov     rcx, r12; unsigned __int16 *
0x180008d9f  mov     [rsp+80h+var_60], rax
0x180008da4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008da9  test    edi, edi
0x180008dab  jz      loc_180008E8F
0x180008db1  lea     rbx, [rsi+10h]
0x180008db5  mov     rcx, [rbx]; lpMem
0x180008db8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180008dbd  mov     rdx, rbx; unsigned __int16 **
0x180008dc0  mov     qword ptr [rbx], 0
0x180008dc7  mov     rcx, r15; unsigned __int16 *
0x180008dca  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x180008dcf  mov     ebx, eax
0x180008dd1  test    eax, eax
0x180008dd3  jns     short loc_180008E04
0x180008dd5  test    edi, edi
0x180008dd7  lea     r8, aStringdup; "StringDup"
0x180008dde  mov     rax, r14
0x180008de1  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008de8  cmovz   rax, r13
0x180008dec  mov     r9d, ebx
0x180008def  mov     rcx, r12; unsigned __int16 *
0x180008df2  mov     [rsp+80h+var_60], rax
0x180008df7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008dfc  test    edi, edi
0x180008dfe  jz      loc_180008E8F
0x180008e04  lea     rcx, [rbp+var_40]; this
0x180008e08  call    ?Pop@RegistryPath@@QEAAHH@Z; RegistryPath::Pop(int)
0x180008e0d  mov     r8, r15; unsigned __int16 *
0x180008e10  lea     rcx, [rbp+var_40]; this
0x180008e14  call    ?Append@RegistryPath@@QEAAKPEBG0@Z; RegistryPath::Append(ushort const *,ushort const *)
0x180008e19  mov     ebx, eax
0x180008e1b  test    eax, eax
0x180008e1d  jz      short loc_180008E4B
0x180008e1f  mov     r9d, eax
0x180008e22  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x180008e29  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008e30  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180008e37  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008e3c  test    ebx, ebx
0x180008e3e  jle     short loc_180008E8F
0x180008e40  movzx   ebx, bx
0x180008e43  or      ebx, 80070000h
0x180008e49  jmp     short loc_180008E8F
0x180008e4b  mov     r8d, [rbp+arg_20]; int
0x180008e4f  lea     rdx, [rbp+var_40]; this
0x180008e53  mov     rcx, rsi; struct struct_join_status *
0x180008e56  call    ?ReadTenantKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z; JoinStatusStorage::ReadTenantKey(struct_join_status *,RegistryPath &,int)
0x180008e5b  mov     ebx, eax
0x180008e5d  test    eax, eax
0x180008e5f  jns     short loc_180008E89
0x180008e61  test    edi, edi
0x180008e63  lea     r8, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x180008e6a  mov     r9d, eax
0x180008e6d  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008e74  cmovz   r14, r13
0x180008e78  mov     rcx, r12; unsigned __int16 *
0x180008e7b  mov     [rsp+80h+var_60], r14
0x180008e80  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008e85  test    edi, edi
0x180008e87  jz      short loc_180008E8F
0x180008e89  test    edi, edi
0x180008e8b  jz      short loc_180008E8F
0x180008e8d  xor     ebx, ebx
0x180008e8f  mov     rcx, [rbp+var_50]; Block
0x180008e93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008e98  mov     rcx, r15; Block
0x180008e9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008ea0  mov     r8d, ebx
0x180008ea3  lea     rdx, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x180008eaa  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180008eb1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180008eb6  lea     rcx, [rbp+var_40]; this
0x180008eba  call    ?Reset@RegistryPath@@AEAAXXZ; RegistryPath::Reset(void)
0x180008ebf  mov     eax, ebx
0x180008ec1  mov     rbx, [rsp+80h+arg_10]
0x180008ec9  add     rsp, 80h
0x180008ed0  pop     r15
0x180008ed2  pop     r14
0x180008ed4  pop     r13
0x180008ed6  pop     r12
0x180008ed8  pop     rdi
0x180008ed9  pop     rsi
0x180008eda  pop     rbp
0x180008edb  retn
```
