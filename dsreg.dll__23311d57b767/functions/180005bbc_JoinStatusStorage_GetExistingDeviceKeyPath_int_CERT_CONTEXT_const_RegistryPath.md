# JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)

- ea: `0x180005bbc`
- end: `0x180006189`
- name: `?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z`
- size: `1485`
- prototype: `__int64 __fastcall(int, const struct _CERT_CONTEXT *, HKEY *)`
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004218`
- `0x180009f10`
- `0x18009716c`
- `0x180097300`

## callees

- `0x18000554c`
- `0x180005894`
- `0x180005ba0`
- `0x180005bbc`
- `0x180006190`
- `0x180006450`
- `0x180006470`
- `0x1800084f4`
- `0x18000bac0`
- `0x18000cbd8`
- `0x18000cc2c`
- `0x180012948`
- `0x18003334c`
- `0x1800366c4`
- `0x180043ef8`
- `0x180044300`
- `0x180044d30`
- `0x18004654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ca`
- `ntdll!RtlGetPersistedStateLocation` at `0x180005e8c`
- `ntdll!RtlGetPersistedStateLocation` at `0x180005e8c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180005c8a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800060bc`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180005c8a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800060bc`

## string_xrefs

- `0x180005e92`: `RegistryPath::InitializePersistedStatePath`
- `0x180005d9b`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x180005e16`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x180005f20`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x180005fb5`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x180006054`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x180005e02`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x180005d58`: `RegistryPath::SubKeyExists`
- `0x18000606d`: `RegistryPath::Append`
- `0x18000616c`: `RegistryPath::Append`
- `0x18000602e`: `RegistryPath::InitializeCurrentUserPath`
- `0x180005f95`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180005f8e`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180006015`: `RegistryPath::InitializeLocalMachinePath`
- `0x180006001`: `%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = "%s", DefaultPath = "%s"`
- `0x18000603b`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x18000604d`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x180006153`: `%s: Registry key based on certificate thumbprint (%s) does not exist. Using registry key based on device ID (%s) ...`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JoinStatusStorage::GetExistingDeviceKeyPath(int a1, const struct _CERT_CONTEXT *a2, HKEY *a3)
{
  DWORD v3; // r14d
  unsigned __int16 *v5; // r12
  int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // eax
  int v9; // esi
  signed int LastError; // edi
  void *v11; // rax
  void *v12; // rsi
  const CERT_CONTEXT *v13; // r12
  int v14; // ebx
  unsigned __int64 v15; // rax
  unsigned __int16 *v16; // rax
  _BYTE *v17; // r9
  __int64 v18; // r8
  unsigned __int16 *i; // rdx
  char v20; // al
  const wchar_t *v21; // r14
  const unsigned __int16 *v22; // rax
  __int64 v23; // r9
  unsigned __int16 *v24; // rdx
  unsigned int v25; // eax
  int PersistedStateLocation; // eax
  int v28; // r9d
  const wchar_t *v29; // rsi
  unsigned int v30; // ebx
  int v31; // eax
  int v32; // edi
  int v33; // eax
  __int64 v34; // r9
  __int64 v35; // r8
  unsigned int v36; // eax
  __int64 v37; // r9
  const unsigned __int16 *v38; // r8
  void *v39; // rax
  int DeviceId; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+44h] [rbp-BCh] BYREF
  void *Block; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v44; // [rsp+50h] [rbp-B0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+58h] [rbp-A8h]
  char v46[16]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v47; // [rsp+70h] [rbp-90h]
  __int64 v48; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h]
  unsigned __int16 v51[264]; // [rsp+90h] [rbp-70h] BYREF

  v3 = 0;
  pCertContext = a2;
  v44 = 0;
  v42 = 0;
  v5 = 0;
  if ( a2 )
  {
    if ( a1 )
    {
      memset_0(v51, 0, 0x208u);
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"CloudDomainJoinRoot",
                                 0,
                                 L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin",
                                 0,
                                 v51,
                                 520,
                                 0);
      v29 = L"RegistryPath::InitializePersistedStatePath";
      v30 = PersistedStateLocation;
      if ( PersistedStateLocation < 0 )
      {
        v32 = 0;
        Logger::WriteGetPersistedStateLocationFailureEvent(
          PersistedStateLocation,
          L"CloudDomainJoinRoot",
          L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin",
          v28);
        Logger::TraceError(
          L"%s: RtlGetPersistedStateLocation failed with NT status code : 0x%08x. SourceID = \"%s\", DefaultPath = \"%s\"",
          L"RegistryPath::InitializePersistedStatePath",
          v30,
          L"CloudDomainJoinRoot",
          L"SYSTEM\\CurrentControlSet\\Control\\CloudDomainJoin");
      }
      else
      {
        v31 = RegistryPath::Initialize((RegistryPath *)a3, HKEY_LOCAL_MACHINE, (wchar_t *)L"HKEY_LOCAL_MACHINE", v51);
        v32 = v31;
        if ( v31 < 0 )
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"RegistryPath::InitializePersistedStatePath",
            L"RegistryPath::InitializeLocalMachinePath",
            (unsigned int)v31);
      }
      v33 = v30;
      v14 = v30 | 0x10000000;
      if ( v33 >= 0 )
        v14 = v32;
      Logger::TraceVerbose(
        (wchar_t *)L"%s - hr: 0x%08x",
        L"RegistryPath::InitializePersistedStatePath",
        (unsigned int)v14);
      if ( v14 >= 0 )
      {
LABEL_4:
        v8 = RegistryPath::Append((RegistryPath *)a3, L"JoinInfo");
        v9 = v8;
        if ( v8 )
        {
          v23 = v8;
          v21 = L"RegistryPath::Append";
          goto LABEL_25;
        }
        Block = 0;
        pcbData = 20;
        LastError = 0;
        v11 = operator new[](0x14u, (const struct std::nothrow_t *)&std::nothrow);
        v12 = v11;
        if ( v11 )
        {
          v13 = pCertContext;
          v14 = 0;
          if ( CertGetCertificateContextProperty(pCertContext, 3u, v11, &pcbData) )
          {
LABEL_7:
            v3 = pcbData;
            Block = v12;
            v12 = 0;
            goto LABEL_8;
          }
          LastError = GetLastError();
          if ( LastError != 234 )
            goto LABEL_52;
          operator delete(v12);
          v39 = operator new[](pcbData, (const struct std::nothrow_t *)&std::nothrow);
          v12 = v39;
          if ( v39 )
          {
            LastError = 0;
            if ( CertGetCertificateContextProperty(v13, 3u, v39, &pcbData) )
              goto LABEL_7;
            LastError = GetLastError();
LABEL_52:
            if ( !LastError )
              goto LABEL_7;
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"CertificateUtil::GetCertificateThumbprintBytes",
              L"CertGetCertificateContextProperty",
              (unsigned int)LastError);
LABEL_8:
            operator delete(v12);
            if ( LastError )
            {
              if ( LastError > 0 )
                v14 = (unsigned __int16)LastError | 0x80070000;
              else
                v14 = LastError;
            }
            if ( v14 < 0 )
            {
              v5 = 0;
              Logger::TraceError(
                L"%s: %s failed with error code: 0x%08x.",
                L"CertificateUtil::GetCertificateThumbprint",
                L"CertificateUtil::GetCertificateThumbprintBytes",
                (unsigned int)v14);
            }
            else
            {
              v15 = 2LL * (2 * v3 + 1);
              if ( !is_mul_ok(2 * v3 + 1, 2u) )
                v15 = -1;
              v16 = (unsigned __int16 *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
              v5 = v16;
              if ( v16 )
              {
                v17 = Block;
                v18 = 0;
                for ( i = v16; (unsigned int)v18 < v3; i += 2 )
                {
                  *i = a0123456789abcd[(unsigned __int64)(unsigned __int8)v17[v18] >> 4];
                  v20 = v17[v18];
                  v18 = (unsigned int)(v18 + 1);
                  i[1] = a0123456789abcd[v20 & 0xF];
                }
                *i = 0;
                goto LABEL_16;
              }
              v14 = -2147024882;
              Logger::TraceCritical(
                L"%s: Out of memory. Allocation failed.",
                L"CertificateUtil::GetCertificateThumbprint");
            }
            v17 = Block;
LABEL_16:
            operator delete(v17);
            if ( v14 < 0 )
            {
              v37 = (unsigned int)v14;
              v38 = L"CertificateUtil::GetCertificateThumbprint";
              goto LABEL_43;
            }
            v21 = L"RegistryPath::SubKeyExists";
            if ( !a3[4] || (unsigned int)IsEmptyString((const unsigned __int16 *)*a3) )
            {
              Logger::TraceError(
                L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
                L"RegistryPath::SubKeyExists");
              v9 = 87;
              v23 = 87;
            }
            else
            {
              v22 = RegistryPath::SubPath((RegistryPath *)a3);
              v9 = RegSubKeyExists(a3[4], v22, v5, &v42);
              v23 = (unsigned int)v9;
              if ( !v9 )
              {
                if ( v42 )
                {
                  v24 = v5;
LABEL_22:
                  v25 = RegistryPath::Append((RegistryPath *)a3, v24);
                  v9 = v25;
                  if ( !v25 )
                    goto LABEL_23;
                  v21 = L"RegistryPath::Append";
                  v23 = v25;
                  goto LABEL_25;
                }
                DeviceId = RegistrationCertStatus::GetDeviceId(pCertContext, &v44);
                v14 = DeviceId;
                if ( DeviceId >= 0 )
                {
                  Logger::TraceInformation(
                    L"%s: Registry key based on certificate thumbprint (%s) does not exist. Using registry key based on de"
                     "vice ID (%s) ...",
                    L"JoinStatusStorage::GetExistingDeviceKeyPath",
                    v5,
                    v44);
                  v24 = v44;
                  goto LABEL_22;
                }
                v37 = (unsigned int)DeviceId;
                v38 = L"RegistrationCertStatus::GetDeviceId";
LABEL_43:
                Logger::TraceError(
                  L"%s: %s failed with error code: 0x%08x.",
                  L"JoinStatusStorage::GetExistingDeviceKeyPath",
                  v38,
                  v37);
                goto LABEL_23;
              }
            }
LABEL_25:
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"JoinStatusStorage::GetExistingDeviceKeyPath",
              v21,
              v23);
            if ( v9 > 0 )
              v14 = (unsigned __int16)v9 | 0x80070000;
            else
              v14 = v9;
            goto LABEL_23;
          }
        }
        v14 = -2147024882;
        Logger::TraceCritical(
          L"%s: Out of memory. Allocation failed.",
          L"CertificateUtil::GetCertificateThumbprintBytes");
        goto LABEL_8;
      }
      v7 = v14;
      v34 = (unsigned int)v14;
    }
    else
    {
      v6 = RegistryPath::InitializeCurrentUserPath((RegistryPath *)a3, (unsigned int)a2, (const unsigned __int16 *)a3);
      v7 = v6;
      if ( v6 >= 0 )
        goto LABEL_4;
      v14 = v6;
      v29 = L"RegistryPath::InitializeCurrentUserPath";
      v34 = (unsigned int)v6;
    }
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"JoinStatusStorage::InitJoinStatusRegPath", v29, v34);
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::GetExistingDeviceKeyPath",
      L"JoinStatusStorage::InitJoinStatusRegPath",
      v7);
    goto LABEL_23;
  }
  v14 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::GetExistingDeviceKeyPath", L"pCert");
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v47 = L"JoinStatusStorage::GetExistingDeviceKeyPath";
    v48 = 88;
    v49 = L"pCert";
    v50 = 12;
    v36 = McGenEventWrite_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            NullOrEmptyParameterFailureEvent,
            v35,
            3,
            v46);
    if ( v36 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v36);
  }
LABEL_23:
  operator delete(v5);
  operator delete(v44);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005bbc  mov     [rsp-8+arg_0], rbx
0x180005bc1  push    rbp
0x180005bc2  push    rsi
0x180005bc3  push    rdi
0x180005bc4  push    r12
0x180005bc6  push    r13
0x180005bc8  push    r14
0x180005bca  push    r15
0x180005bcc  lea     rbp, [rsp-1B0h]
0x180005bd4  sub     rsp, 2B0h
0x180005bdb  mov     rax, cs:__security_cookie
0x180005be2  xor     rax, rsp
0x180005be5  mov     [rbp+1E0h+var_40], rax
0x180005bec  xor     r14d, r14d
0x180005bef  mov     [rsp+2E0h+pCertContext], rdx
0x180005bf4  mov     [rsp+2E0h+var_290], r14
0x180005bf9  mov     r13, r8
0x180005bfc  mov     [rsp+2E0h+var_29C], r14d
0x180005c01  mov     r12d, r14d
0x180005c04  test    rdx, rdx
0x180005c07  jz      loc_180005F14
0x180005c0d  lea     r15, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180005c14  test    ecx, ecx
0x180005c16  jnz     loc_180005E54
0x180005c1c  mov     rcx, r8; this
0x180005c1f  call    ?InitializeCurrentUserPath@RegistryPath@@QEAAJKPEBG@Z; RegistryPath::InitializeCurrentUserPath(ulong,ushort const *)
0x180005c24  mov     edi, eax
0x180005c26  test    eax, eax
0x180005c28  js      loc_18000602C
0x180005c2e  lea     rdx, aJoininfo; "JoinInfo"
0x180005c35  mov     rcx, r13; this
0x180005c38  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x180005c3d  mov     esi, eax
0x180005c3f  test    eax, eax
0x180005c41  jnz     loc_180006063
0x180005c47  lea     ecx, [rax+14h]; unsigned __int64
0x180005c4a  mov     [rsp+2E0h+Block], r14
0x180005c4f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c56  mov     [rsp+2E0h+pcbData], ecx
0x180005c5a  mov     edi, r14d
0x180005c5d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005c62  lea     r15, Str; "%s: %s failed with win32 error code: 0x"...
0x180005c69  mov     rsi, rax
0x180005c6c  test    rax, rax
0x180005c6f  jz      loc_180005E37
0x180005c75  mov     r12, [rsp+2E0h+pCertContext]
0x180005c7a  lea     r9, [rsp+2E0h+pcbData]; pcbData
0x180005c7f  xor     ebx, ebx
0x180005c81  mov     r8, rax; pvData
0x180005c84  mov     rcx, r12; pCertContext
0x180005c87  lea     edx, [rbx+3]; dwPropId
0x180005c8a  call    cs:__imp_CertGetCertificateContextProperty
0x180005c90  test    eax, eax
0x180005c92  jz      loc_180006079
0x180005c98  mov     r14d, [rsp+2E0h+pcbData]
0x180005c9d  mov     [rsp+2E0h+Block], rsi
0x180005ca2  xor     esi, esi
0x180005ca4  mov     rcx, rsi; Block
0x180005ca7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005cac  test    edi, edi
0x180005cae  jnz     loc_180005FA5
0x180005cb4  lea     rdi, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x180005cbb  test    ebx, ebx
0x180005cbd  js      loc_180006106
0x180005cc3  lea     ecx, ds:1[r14*2]
0x180005ccb  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180005cd2  mov     eax, 2
0x180005cd7  mul     rcx
0x180005cda  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005ce1  cmovb   rax, r8
0x180005ce5  mov     rcx, rax; unsigned __int64
0x180005ce8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005ced  mov     r12, rax
0x180005cf0  test    rax, rax
0x180005cf3  jz      loc_180005EF6
0x180005cf9  mov     r9, [rsp+2E0h+Block]
0x180005cfe  xor     r8d, r8d
0x180005d01  mov     rdx, rax
0x180005d04  test    r14d, r14d
0x180005d07  jz      short loc_180005D3E
0x180005d09  lea     r10, a0123456789abcd; "0123456789ABCDEF"
0x180005d10  movzx   eax, byte ptr [r8+r9]
0x180005d15  shr     rax, 4
0x180005d19  movzx   eax, word ptr [r10+rax*2]
0x180005d1e  mov     [rdx], ax
0x180005d21  movzx   eax, byte ptr [r8+r9]
0x180005d26  inc     r8d
0x180005d29  and     eax, 0Fh
0x180005d2c  movzx   eax, word ptr [r10+rax*2]
0x180005d31  mov     [rdx+2], ax
0x180005d35  add     rdx, 4
0x180005d39  cmp     r8d, r14d
0x180005d3c  jb      short loc_180005D10
0x180005d3e  xor     eax, eax
0x180005d40  mov     [rdx], ax
0x180005d43  mov     rcx, r9; Block
0x180005d46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005d4b  test    ebx, ebx
0x180005d4d  js      loc_180005FB2
0x180005d53  cmp     qword ptr [r13+20h], 0
0x180005d58  lea     r14, aRegistrypathSu_0; "RegistryPath::SubKeyExists"
0x180005d5f  jz      loc_180005DFF
0x180005d65  mov     rcx, [r13+0]; unsigned __int16 *
0x180005d69  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180005d6e  test    eax, eax
0x180005d70  jnz     loc_180005DFF
0x180005d76  mov     rcx, r13; this
0x180005d79  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x180005d7e  mov     rcx, [r13+20h]; HKEY
0x180005d82  lea     r9, [rsp+2E0h+var_29C]; int *
0x180005d87  mov     rdx, rax; unsigned __int16 *
0x180005d8a  mov     r8, r12; unsigned __int16 *
0x180005d8d  call    ?RegSubKeyExists@@YAKPEAUHKEY__@@PEBG1PEAH@Z; RegSubKeyExists(HKEY__ *,ushort const *,ushort const *,int *)
0x180005d92  mov     esi, eax
0x180005d94  mov     r9d, eax
0x180005d97  test    eax, eax
0x180005d99  jnz     short loc_180005E16
0x180005d9b  lea     rdi, aJoinstatusstor_12; "JoinStatusStorage::GetExistingDeviceKey"...
0x180005da2  cmp     [rsp+2E0h+var_29C], eax
0x180005da6  jz      loc_180006127
0x180005dac  mov     rdx, r12; unsigned __int16 *
0x180005daf  mov     rcx, r13; this
0x180005db2  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x180005db7  mov     esi, eax
0x180005db9  test    eax, eax
0x180005dbb  jnz     loc_18000616C
0x180005dc1  mov     rcx, r12; Block
0x180005dc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005dc9  mov     rcx, [rsp+2E0h+var_290]; Block
0x180005dce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005dd3  mov     eax, ebx
0x180005dd5  mov     rcx, [rbp+1E0h+var_40]
0x180005ddc  xor     rcx, rsp; StackCookie
0x180005ddf  call    __security_check_cookie
0x180005de4  mov     rbx, [rsp+2E0h+arg_0]
0x180005dec  add     rsp, 2B0h
0x180005df3  pop     r15
0x180005df5  pop     r14
0x180005df7  pop     r13
0x180005df9  pop     r12
0x180005dfb  pop     rdi
0x180005dfc  pop     rsi
0x180005dfd  pop     rbp
0x180005dfe  retn
0x180005dff  mov     rdx, r14
0x180005e02  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x180005e09  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005e0e  mov     esi, 57h ; 'W'
0x180005e13  mov     r9d, esi
0x180005e16  lea     rdi, aJoinstatusstor_12; "JoinStatusStorage::GetExistingDeviceKey"...
0x180005e1d  mov     r8, r14
0x180005e20  mov     rdx, rdi
0x180005e23  mov     rcx, r15; unsigned __int16 *
0x180005e26  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005e2b  test    esi, esi
0x180005e2d  jg      loc_18000617B
0x180005e33  mov     ebx, esi
0x180005e35  jmp     short loc_180005DC1
0x180005e37  lea     rdx, aCertificateuti_3; "CertificateUtil::GetCertificateThumbpri"...
0x180005e3e  mov     ebx, 8007000Eh
0x180005e43  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180005e4a  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180005e4f  jmp     loc_180005CA4
0x180005e54  mov     ebx, 208h
0x180005e59  lea     rcx, [rbp+1E0h+var_250]; void *
0x180005e5d  mov     r8d, ebx; Size
0x180005e60  xor     edx, edx; Val
0x180005e62  call    memset_0
0x180005e67  lea     rax, [rbp+1E0h+var_250]
0x180005e6b  mov     [rsp+2E0h+var_2B0], r14
0x180005e70  mov     [rsp+2E0h+var_2B8], ebx
0x180005e74  lea     r8, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x180005e7b  xor     r9d, r9d
0x180005e7e  mov     [rsp+2E0h+var_2C0], rax
0x180005e83  xor     edx, edx
0x180005e85  lea     rcx, aClouddomainjoi_0; "CloudDomainJoinRoot"
0x180005e8c  call    cs:__imp_RtlGetPersistedStateLocation
0x180005e92  lea     rsi, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x180005e99  mov     ebx, eax
0x180005e9b  test    eax, eax
0x180005e9d  js      loc_180005FD0
0x180005ea3  lea     r9, [rbp+1E0h+var_250]; unsigned __int16 *
0x180005ea7  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180005eae  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE"
0x180005eb5  mov     rcx, r13; this
0x180005eb8  call    ?Initialize@RegistryPath@@QEAAJPEAUHKEY__@@PEBG1@Z; RegistryPath::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180005ebd  mov     edi, eax
0x180005ebf  test    eax, eax
0x180005ec1  js      loc_180006012
0x180005ec7  mov     eax, ebx
0x180005ec9  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180005ed0  bts     ebx, 1Ch
0x180005ed4  mov     rdx, rsi
0x180005ed7  test    eax, eax
0x180005ed9  cmovns  ebx, edi
0x180005edc  mov     r8d, ebx
0x180005edf  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180005ee4  test    ebx, ebx
0x180005ee6  jns     loc_180005C2E
0x180005eec  mov     edi, ebx
0x180005eee  mov     r9d, ebx
0x180005ef1  jmp     loc_180006038
0x180005ef6  mov     rdx, rdi
0x180005ef9  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180005f00  mov     ebx, 8007000Eh
0x180005f05  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180005f0a  mov     r9, [rsp+2E0h+Block]
0x180005f0f  jmp     loc_180005D43
0x180005f14  lea     rsi, aPcert; "pCert"
0x180005f1b  mov     ebx, 80070057h
0x180005f20  lea     rdi, aJoinstatusstor_12; "JoinStatusStorage::GetExistingDeviceKey"...
0x180005f27  mov     r8, rsi
0x180005f2a  mov     rdx, rdi
0x180005f2d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180005f34  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005f39  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180005f40  jz      loc_180005DC1
0x180005f46  lea     rax, [rsp+2E0h+var_280]
0x180005f4b  mov     [rsp+2E0h+var_270], rdi
0x180005f50  mov     r9d, 3
0x180005f56  mov     [rsp+2E0h+var_2C0], rax
0x180005f5b  lea     rdx, NullOrEmptyParameterFailureEvent
0x180005f62  mov     [rsp+2E0h+var_268], 58h ; 'X'
0x180005f6b  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180005f72  mov     [rbp+1E0h+var_260], rsi
0x180005f76  mov     [rbp+1E0h+var_258], 0Ch
0x180005f7e  call    McGenEventWrite_EventWriteTransfer
0x180005f83  test    eax, eax
0x180005f85  jz      loc_180005DC1
0x180005f8b  mov     r9d, eax
0x180005f8e  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180005f95  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180005f9c  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180005fa3  jmp     short loc_180005FC6
0x180005fa5  jg      loc_1800060F8
0x180005fab  mov     ebx, edi
0x180005fad  jmp     loc_180005CB4
0x180005fb2  mov     r9d, ebx
0x180005fb5  lea     rdx, aJoinstatusstor_12; "JoinStatusStorage::GetExistingDeviceKey"...
0x180005fbc  mov     r8, rdi
0x180005fbf  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180005fc6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180005fcb  jmp     loc_180005DC1
0x180005fd0  lea     r8, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x180005fd7  mov     ecx, ebx; int
0x180005fd9  lea     rdx, aClouddomainjoi_0; "CloudDomainJoinRoot"
0x180005fe0  mov     edi, r14d
0x180005fe3  call    ?WriteGetPersistedStateLocationFailureEvent@Logger@@SAJJPEBG0H@Z; Logger::WriteGetPersistedStateLocationFailureEvent(long,ushort const *,ushort const *,int)
0x180005fe8  lea     rax, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Clo"...
0x180005fef  mov     r8d, ebx
0x180005ff2  lea     r9, aClouddomainjoi_0; "CloudDomainJoinRoot"
0x180005ff9  mov     [rsp+2E0h+var_2C0], rax
0x180005ffe  mov     rdx, rsi
0x180006001  lea     rcx, aSRtlgetpersist; "%s: RtlGetPersistedStateLocation failed"...
0x180006008  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000600d  jmp     loc_180005EC7
0x180006012  mov     r9d, eax
0x180006015  lea     r8, aRegistrypathIn; "RegistryPath::InitializeLocalMachinePat"...
0x18000601c  mov     rdx, rsi
0x18000601f  mov     rcx, r15; unsigned __int16 *
0x180006022  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006027  jmp     loc_180005EC7
0x18000602c  mov     ebx, eax
0x18000602e  lea     rsi, aRegistrypathIn_2; "RegistryPath::InitializeCurrentUserPath"
0x180006035  mov     r9d, eax
0x180006038  mov     rcx, r15; unsigned __int16 *
0x18000603b  lea     rdx, aJoinstatusstor_7; "JoinStatusStorage::InitJoinStatusRegPat"...
0x180006042  mov     r8, rsi
0x180006045  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000604a  mov     r9d, edi
0x18000604d  lea     r8, aJoinstatusstor_7; "JoinStatusStorage::InitJoinStatusRegPat"...
0x180006054  lea     rdx, aJoinstatusstor_12; "JoinStatusStorage::GetExistingDeviceKey"...
0x18000605b  mov     rcx, r15
0x18000605e  jmp     loc_180005FC6
0x180006063  lea     r15, Str; "%s: %s failed with win32 error code: 0x"...
0x18000606a  mov     r9d, eax
0x18000606d  lea     r14, aRegistrypathAp; "RegistryPath::Append"
0x180006074  jmp     loc_180005E16
0x180006079  call    cs:__imp_GetLastError
0x18000607f  mov     edi, eax
0x180006081  cmp     eax, 0EAh
0x180006086  jnz     short loc_1800060D2
0x180006088  mov     rcx, rsi; Block
0x18000608b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006090  mov     ecx, [rsp+2E0h+pcbData]; unsigned __int64
0x180006094  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000609b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800060a0  mov     rsi, rax
0x1800060a3  test    rax, rax
0x1800060a6  jz      loc_180005E37
0x1800060ac  xor     edi, edi
0x1800060ae  lea     r9, [rsp+2E0h+pcbData]; pcbData
0x1800060b3  mov     r8, rax; pvData
0x1800060b6  mov     rcx, r12; pCertContext
0x1800060b9  lea     edx, [rdi+3]; dwPropId
0x1800060bc  call    cs:__imp_CertGetCertificateContextProperty
0x1800060c2  test    eax, eax
0x1800060c4  jnz     loc_180005C98
0x1800060ca  call    cs:__imp_GetLastError
0x1800060d0  mov     edi, eax
  ... truncated ...
```
