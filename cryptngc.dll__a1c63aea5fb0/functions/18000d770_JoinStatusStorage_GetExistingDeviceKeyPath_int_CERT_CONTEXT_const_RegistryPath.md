# JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)

- ea: `0x18000d770`
- end: `0x18000db4c`
- name: `?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z`
- size: `988`
- prototype: `static int(int, const struct _CERT_CONTEXT *, struct RegistryPath *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008ad0`

## callees

- `0x180009f5c`
- `0x18000c190`
- `0x18000d770`
- `0x18000db54`
- `0x18000dde0`
- `0x18000e100`
- `0x18000e4e0`
- `0x180027448`
- `0x1800274cc`
- `0x18002b1a0`
- `0x18002bc58`
- `0x18002cb00`
- `0x18002cd24`
- `0x18002e664`
- `0x18002f710`
- `0x180046ce0`

## string_xrefs

- `0x18000dace`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18000d7be`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18000d8a4`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18000d99b`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18000da4f`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18000dae2`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18000da07`: `RegistryPath::SubKeyExists`
- `0x18000d8d9`: `RegistryPath::Append`
- `0x18000dabf`: `RegistryPath::Append`
- `0x18000d87b`: `RegistryPath::InitializeCurrentUserPath`
- `0x18000d835`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000d82e`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18000d867`: `RegistryPath::InitializePersistedStatePath`
- `0x18000d885`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x18000d89d`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x18000da9c`: `%s: Registry key based on certificate thumbprint (%s) does not exist. Using registry key based on device ID (%s) ...`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::GetExistingDeviceKeyPath(
        int a1,
        const struct _CERT_CONTEXT *a2,
        struct RegistryPath *a3,
        const unsigned __int16 *a4)
{
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // r8
  unsigned int v10; // eax
  int v11; // edi
  const wchar_t *v12; // r8
  unsigned int v13; // eax
  int v14; // edi
  const wchar_t *v15; // r13
  __int64 v16; // r9
  int CertificateThumbprintBytes; // eax
  unsigned int v18; // r12d
  unsigned int v19; // edi
  unsigned __int64 v20; // rax
  unsigned __int16 *v21; // rax
  _BYTE *v22; // rcx
  unsigned __int16 *v23; // r8
  unsigned int i; // r9d
  __int64 v25; // rdx
  const unsigned __int16 *v26; // rax
  HKEY v27; // r10
  const unsigned __int16 *v28; // rdx
  int DeviceId; // eax
  unsigned int v30; // eax
  unsigned int v32; // [rsp+30h] [rbp-88h] BYREF
  int v33; // [rsp+34h] [rbp-84h] BYREF
  void *Block; // [rsp+38h] [rbp-80h] BYREF
  unsigned __int16 *v35; // [rsp+40h] [rbp-78h] BYREF
  char v36[16]; // [rsp+48h] [rbp-70h] BYREF
  const wchar_t *v37; // [rsp+58h] [rbp-60h]
  __int64 v38; // [rsp+60h] [rbp-58h]
  const unsigned __int16 *v39; // [rsp+68h] [rbp-50h]
  __int64 v40; // [rsp+70h] [rbp-48h]

  v35 = 0;
  v33 = 0;
  v6 = 0;
  v7 = 0;
  if ( a2 )
  {
    if ( a1 )
    {
      v11 = RegistryPath::InitializePersistedStatePath(
              a3,
              (const unsigned __int16 *)a2,
              (const unsigned __int16 *)a3,
              a4);
      if ( v11 < 0 )
      {
        v12 = L"RegistryPath::InitializePersistedStatePath";
LABEL_10:
        v8 = v11;
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"JoinStatusStorage::InitJoinStatusRegPath",
          v12,
          (unsigned int)v11);
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"JoinStatusStorage::GetExistingDeviceKeyPath",
          L"JoinStatusStorage::InitJoinStatusRegPath",
          (unsigned int)v11);
        goto LABEL_36;
      }
    }
    else
    {
      v11 = RegistryPath::InitializeCurrentUserPath(a3, (unsigned int)a2, (const unsigned __int16 *)a3);
      if ( v11 < 0 )
      {
        v12 = L"RegistryPath::InitializeCurrentUserPath";
        goto LABEL_10;
      }
    }
    v13 = RegistryPath::Append(a3, L"JoinInfo");
    v14 = v13;
    if ( v13 )
    {
      v15 = L"RegistryPath::Append";
      v16 = v13;
LABEL_33:
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::GetExistingDeviceKeyPath",
        v15,
        v16);
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      else
        v8 = v14;
      goto LABEL_36;
    }
    Block = 0;
    v32 = 0;
    CertificateThumbprintBytes = CertificateUtil::GetCertificateThumbprintBytes(a2, (unsigned __int8 **)&Block, &v32);
    v18 = CertificateThumbprintBytes;
    if ( CertificateThumbprintBytes >= 0 )
    {
      v19 = v32;
      v20 = 2LL * (2 * v32 + 1);
      if ( !is_mul_ok(2 * v32 + 1, 2u) )
        v20 = -1;
      v21 = (unsigned __int16 *)operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
      v6 = v21;
      if ( v21 )
      {
        v22 = Block;
        v23 = v21;
        for ( i = 0; i < v19; v23 += 2 )
        {
          v25 = i++;
          *v23 = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)v22[v25] >> 4];
          v23[1] = a0123456789abcd_0[v22[v25] & 0xF];
        }
        *v23 = 0;
        operator delete(v22);
        v15 = L"RegistryPath::SubKeyExists";
        if ( !*((_QWORD *)a3 + 4) || (unsigned int)IsEmptyString(*(const unsigned __int16 **)a3) )
        {
          Logger::TraceError(
            L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
            L"RegistryPath::SubKeyExists");
          v14 = 87;
          v16 = 87;
        }
        else
        {
          v26 = RegistryPath::SubPath(a3);
          v14 = RegSubKeyExists(v27, v26, v6, &v33);
          v16 = (unsigned int)v14;
          if ( !v14 )
          {
            if ( v33 )
            {
              v28 = v6;
              v8 = v18;
            }
            else
            {
              DeviceId = RegistrationCertStatus::GetDeviceId(a2, &v35);
              v8 = DeviceId;
              if ( DeviceId < 0 )
              {
                Logger::TraceError(
                  L"%s: %s failed with error code: 0x%08x.",
                  L"JoinStatusStorage::GetExistingDeviceKeyPath",
                  L"RegistrationCertStatus::GetDeviceId",
                  (unsigned int)DeviceId);
                v7 = v35;
                goto LABEL_36;
              }
              v7 = v35;
              Logger::TraceInformation(
                L"%s: Registry key based on certificate thumbprint (%s) does not exist. Using registry key based on device ID (%s) ...",
                L"JoinStatusStorage::GetExistingDeviceKeyPath",
                v6,
                v35);
              v28 = v7;
            }
            v30 = RegistryPath::Append(a3, v28);
            v14 = v30;
            if ( !v30 )
              goto LABEL_36;
            v15 = L"RegistryPath::Append";
            v16 = v30;
          }
        }
        goto LABEL_33;
      }
      v8 = -2147024882;
      v18 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CertificateUtil::GetCertificateThumbprint");
      operator delete(Block);
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"CertificateUtil::GetCertificateThumbprint",
        L"CertificateUtil::GetCertificateThumbprintBytes",
        (unsigned int)CertificateThumbprintBytes);
      operator delete(Block);
      v8 = v18;
    }
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::GetExistingDeviceKeyPath",
      L"CertificateUtil::GetCertificateThumbprint",
      v18);
    goto LABEL_36;
  }
  v8 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::GetExistingDeviceKeyPath", L"pCert");
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v37 = L"JoinStatusStorage::GetExistingDeviceKeyPath";
    v38 = 88;
    v39 = L"pCert";
    v40 = 12;
    v10 = McGenEventWrite_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            NullOrEmptyParameterFailureEvent,
            v9,
            3,
            v36);
    if ( v10 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v10);
  }
LABEL_36:
  operator delete(v6);
  operator delete(v7);
  return v8;
}

```

## disassembly

```asm
0x18000d770  push    rbx
0x18000d772  push    rbp
0x18000d773  push    rsi
0x18000d774  push    r13
0x18000d776  push    r14
0x18000d778  push    r15
0x18000d77a  sub     rsp, 88h
0x18000d781  mov     rax, cs:__security_cookie
0x18000d788  xor     rax, rsp
0x18000d78b  mov     [rsp+0B8h+var_40], rax
0x18000d790  xor     r13d, r13d
0x18000d793  mov     rbx, r8
0x18000d796  mov     [rsp+0B8h+var_78], r13
0x18000d79b  mov     rsi, rdx
0x18000d79e  mov     [rsp+0B8h+var_84], r13d
0x18000d7a3  mov     r14d, r13d
0x18000d7a6  mov     ebp, r13d
0x18000d7a9  test    rdx, rdx
0x18000d7ac  jnz     loc_18000D84D
0x18000d7b2  lea     rbx, aPcert; "pCert"
0x18000d7b9  mov     esi, 80070057h
0x18000d7be  lea     r15, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18000d7c5  mov     r8, rbx
0x18000d7c8  mov     rdx, r15
0x18000d7cb  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000d7d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d7d7  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000d7de  jz      loc_18000DB1C
0x18000d7e4  lea     rax, [rsp+0B8h+var_70]
0x18000d7e9  mov     [rsp+0B8h+var_60], r15
0x18000d7ee  mov     r9d, 3
0x18000d7f4  mov     [rsp+0B8h+var_98], rax
0x18000d7f9  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000d800  mov     [rsp+0B8h+var_58], 58h ; 'X'
0x18000d809  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000d810  mov     [rsp+0B8h+var_50], rbx
0x18000d815  mov     [rsp+0B8h+var_48], 0Ch
0x18000d81e  call    McGenEventWrite_EventWriteTransfer
0x18000d823  test    eax, eax
0x18000d825  jz      loc_18000DB1C
0x18000d82b  mov     r9d, eax
0x18000d82e  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000d835  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000d83c  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000d843  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d848  jmp     loc_18000DB1C
0x18000d84d  test    ecx, ecx
0x18000d84f  mov     [rsp+0B8h+arg_0], rdi
0x18000d857  mov     rcx, rbx; this
0x18000d85a  jz      short loc_18000D870
0x18000d85c  call    ?InitializePersistedStatePath@RegistryPath@@QEAAJPEBG00@Z; RegistryPath::InitializePersistedStatePath(ushort const *,ushort const *,ushort const *)
0x18000d861  mov     edi, eax
0x18000d863  test    eax, eax
0x18000d865  jns     short loc_18000D8BC
0x18000d867  lea     r8, aRegistrypathIn_1; "RegistryPath::InitializePersistedStateP"...
0x18000d86e  jmp     short loc_18000D882
0x18000d870  call    ?InitializeCurrentUserPath@RegistryPath@@QEAAJKPEBG@Z; RegistryPath::InitializeCurrentUserPath(ulong,ushort const *)
0x18000d875  mov     edi, eax
0x18000d877  test    eax, eax
0x18000d879  jns     short loc_18000D8BC
0x18000d87b  lea     r8, aRegistrypathIn_2; "RegistryPath::InitializeCurrentUserPath"
0x18000d882  mov     r9d, edi
0x18000d885  lea     rdx, aJoinstatusstor_0; "JoinStatusStorage::InitJoinStatusRegPat"...
0x18000d88c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000d893  mov     esi, edi
0x18000d895  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d89a  mov     r9d, edi
0x18000d89d  lea     r8, aJoinstatusstor_0; "JoinStatusStorage::InitJoinStatusRegPat"...
0x18000d8a4  lea     rdx, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18000d8ab  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000d8b2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d8b7  jmp     loc_18000DB14
0x18000d8bc  mov     [rsp+0B8h+var_38], r12
0x18000d8c4  lea     rdx, aJoininfo; "JoinInfo"
0x18000d8cb  mov     rcx, rbx; this
0x18000d8ce  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18000d8d3  mov     edi, eax
0x18000d8d5  test    eax, eax
0x18000d8d7  jz      short loc_18000D8E8
0x18000d8d9  lea     r13, aRegistrypathAp; "RegistryPath::Append"
0x18000d8e0  mov     r9d, eax
0x18000d8e3  jmp     loc_18000DAE2
0x18000d8e8  lea     r8, [rsp+0B8h+var_88]; unsigned int *
0x18000d8ed  mov     [rsp+0B8h+Block], r13
0x18000d8f2  lea     rdx, [rsp+0B8h+Block]; unsigned __int8 **
0x18000d8f7  mov     [rsp+0B8h+var_88], r13d
0x18000d8fc  mov     rcx, rsi; pCertContext
0x18000d8ff  call    ?GetCertificateThumbprintBytes@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; CertificateUtil::GetCertificateThumbprintBytes(_CERT_CONTEXT const *,uchar * *,ulong *)
0x18000d904  mov     r12d, eax
0x18000d907  test    eax, eax
0x18000d909  jns     short loc_18000D937
0x18000d90b  mov     r9d, eax
0x18000d90e  lea     r8, aCertificateuti_2; "CertificateUtil::GetCertificateThumbpri"...
0x18000d915  lea     rdx, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x18000d91c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000d923  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d928  mov     rcx, [rsp+0B8h+Block]; Block
0x18000d92d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d932  mov     esi, r12d
0x18000d935  jmp     short loc_18000D991
0x18000d937  mov     edi, [rsp+0B8h+var_88]
0x18000d93b  mov     eax, 2
0x18000d940  lea     ecx, ds:1[rdi*2]
0x18000d947  mul     rcx
0x18000d94a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d951  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d958  cmovb   rax, rcx
0x18000d95c  mov     rcx, rax; unsigned __int64
0x18000d95f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d964  mov     r14, rax
0x18000d967  test    rax, rax
0x18000d96a  jnz     short loc_18000D9B3
0x18000d96c  mov     esi, 8007000Eh
0x18000d971  lea     rdx, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x18000d978  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000d97f  mov     r12d, esi
0x18000d982  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000d987  mov     rcx, [rsp+0B8h+Block]; Block
0x18000d98c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d991  mov     r9d, r12d
0x18000d994  lea     r8, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x18000d99b  lea     rdx, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18000d9a2  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000d9a9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d9ae  jmp     loc_18000DB0C
0x18000d9b3  mov     rcx, [rsp+0B8h+Block]; Block
0x18000d9b8  mov     r8, r14
0x18000d9bb  mov     r9d, r13d
0x18000d9be  test    edi, edi
0x18000d9c0  jz      short loc_18000D9FA
0x18000d9c2  lea     r10, a0123456789abcd_0; "0123456789ABCDEF"
0x18000d9c9  mov     edx, r9d
0x18000d9cc  inc     r9d
0x18000d9cf  movzx   eax, byte ptr [rdx+rcx]
0x18000d9d3  shr     rax, 4
0x18000d9d7  movzx   eax, word ptr [r10+rax*2]
0x18000d9dc  mov     [r8], ax
0x18000d9e0  movzx   eax, byte ptr [rdx+rcx]
0x18000d9e4  and     eax, 0Fh
0x18000d9e7  movzx   eax, word ptr [r10+rax*2]
0x18000d9ec  mov     [r8+2], ax
0x18000d9f1  add     r8, 4
0x18000d9f5  cmp     r9d, edi
0x18000d9f8  jb      short loc_18000D9C9
0x18000d9fa  mov     [r8], r13w
0x18000d9fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000da03  mov     r10, [rbx+20h]
0x18000da07  lea     r13, aRegistrypathSu; "RegistryPath::SubKeyExists"
0x18000da0e  test    r10, r10
0x18000da11  jz      loc_18000DACB
0x18000da17  mov     rcx, [rbx]; unsigned __int16 *
0x18000da1a  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000da1f  test    eax, eax
0x18000da21  jnz     loc_18000DACB
0x18000da27  mov     rcx, rbx; this
0x18000da2a  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18000da2f  mov     rdx, rax; unsigned __int16 *
0x18000da32  lea     r9, [rsp+0B8h+var_84]; int *
0x18000da37  mov     r8, r14; unsigned __int16 *
0x18000da3a  mov     rcx, r10; HKEY
0x18000da3d  call    ?RegSubKeyExists@@YAKPEAUHKEY__@@PEBG1PEAH@Z; RegSubKeyExists(HKEY__ *,ushort const *,ushort const *,int *)
0x18000da42  mov     edi, eax
0x18000da44  mov     r9d, eax
0x18000da47  test    eax, eax
0x18000da49  jnz     loc_18000DAE2
0x18000da4f  lea     r15, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18000da56  cmp     [rsp+0B8h+var_84], ebp
0x18000da5a  jz      short loc_18000DA64
0x18000da5c  mov     rdx, r14
0x18000da5f  mov     esi, r12d
0x18000da62  jmp     short loc_18000DAB1
0x18000da64  lea     rdx, [rsp+0B8h+var_78]; unsigned __int16 **
0x18000da69  mov     rcx, rsi; struct _CERT_CONTEXT *
0x18000da6c  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x18000da71  mov     esi, eax
0x18000da73  mov     rdx, r15
0x18000da76  test    eax, eax
0x18000da78  jns     short loc_18000DA97
0x18000da7a  mov     r9d, eax
0x18000da7d  lea     r8, aRegistrationce_4; "RegistrationCertStatus::GetDeviceId"
0x18000da84  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000da8b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000da90  mov     rbp, [rsp+0B8h+var_78]
0x18000da95  jmp     short loc_18000DB0C
0x18000da97  mov     rbp, [rsp+0B8h+var_78]
0x18000da9c  lea     rcx, aSRegistryKeyBa; "%s: Registry key based on certificate t"...
0x18000daa3  mov     r9, rbp
0x18000daa6  mov     r8, r14
0x18000daa9  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18000daae  mov     rdx, rbp; unsigned __int16 *
0x18000dab1  mov     rcx, rbx; this
0x18000dab4  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18000dab9  mov     edi, eax
0x18000dabb  test    eax, eax
0x18000dabd  jz      short loc_18000DB0C
0x18000dabf  lea     r13, aRegistrypathAp; "RegistryPath::Append"
0x18000dac6  mov     r9d, eax
0x18000dac9  jmp     short loc_18000DAE9
0x18000dacb  mov     rdx, r13
0x18000dace  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18000dad5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000dada  mov     edi, 57h ; 'W'
0x18000dadf  mov     r9d, edi
0x18000dae2  lea     r15, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18000dae9  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000daf0  mov     r8, r13
0x18000daf3  mov     rdx, r15
0x18000daf6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000dafb  test    edi, edi
0x18000dafd  jg      short loc_18000DB03
0x18000daff  mov     esi, edi
0x18000db01  jmp     short loc_18000DB0C
0x18000db03  movzx   esi, di
0x18000db06  or      esi, 80070000h
0x18000db0c  mov     r12, [rsp+0B8h+var_38]
0x18000db14  mov     rdi, [rsp+0B8h+arg_0]
0x18000db1c  mov     rcx, r14; Block
0x18000db1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000db24  mov     rcx, rbp; Block
0x18000db27  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000db2c  mov     eax, esi
0x18000db2e  mov     rcx, [rsp+0B8h+var_40]
0x18000db33  xor     rcx, rsp; StackCookie
0x18000db36  call    __security_check_cookie
0x18000db3b  add     rsp, 88h
0x18000db42  pop     r15
0x18000db44  pop     r14
0x18000db46  pop     r13
0x18000db48  pop     rsi
0x18000db49  pop     rbp
0x18000db4a  pop     rbx
0x18000db4b  retn
```
