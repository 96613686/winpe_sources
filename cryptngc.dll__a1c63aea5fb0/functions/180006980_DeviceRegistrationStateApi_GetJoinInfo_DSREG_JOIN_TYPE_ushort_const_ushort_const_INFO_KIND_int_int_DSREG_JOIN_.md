# DeviceRegistrationStateApi::GetJoinInfo(_DSREG_JOIN_TYPE,ushort const *,ushort const *,INFO_KIND,int,int,_DSREG_JOIN_INFO_2 * *)

- ea: `0x180006980`
- end: `0x18000705f`
- name: `?GetJoinInfo@DeviceRegistrationStateApi@@SAJW4_DSREG_JOIN_TYPE@@PEBG1W4INFO_KIND@@HHPEAPEAU_DSREG_JOIN_INFO_2@@@Z`
- size: `1759`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007070`

## callees

- `0x180006980`
- `0x1800073c0`
- `0x180025788`
- `0x180027448`
- `0x1800274cc`
- `0x18002b340`
- `0x18002bc58`
- `0x18002c23c`
- `0x18002e664`
- `0x18002e850`
- `0x18002f6ec`
- `0x18002f710`
- `0x1800461d8`
- `0x180046ce0`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x180006b08`
- `CRYPT32!CertFreeCertificateContext` at `0x180006b3a`
- `CRYPT32!CertFreeCertificateContext` at `0x180006b08`
- `CRYPT32!CertFreeCertificateContext` at `0x180006b3a`

## string_xrefs

- `0x180006d5d`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180006d56`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x180007022`: `%s: Successfully read %lu accounts out of a total of %lu certificate(s).`
- `0x18000704e`: `%s: Cannot read any accounts out of a total of %lu certificate(s).`

## pseudocode

```c
__int64 __fastcall DeviceRegistrationStateApi::GetJoinInfo(
        unsigned int a1,
        const unsigned __int16 *a2,
        wchar_t *a3,
        unsigned int a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  const wchar_t *v7; // r11
  unsigned int v8; // esi
  struct _CERT_CONTEXT **v9; // r12
  struct _CERT_CONTEXT **v10; // r14
  unsigned int v11; // r15d
  const wchar_t *v12; // rdi
  const wchar_t *v15; // r9
  const wchar_t *v17; // r8
  const wchar_t *v18; // rcx
  const wchar_t *v19; // rdx
  __int64 v20; // rdx
  unsigned int v21; // r13d
  __int64 v22; // r8
  ULONG v23; // eax
  __int64 j; // rdi
  PCCERT_CONTEXT *v25; // rbx
  unsigned int k; // ebx
  PCCERT_CONTEXT *v27; // rdi
  const unsigned __int16 *v29; // rdi
  int Certificates; // eax
  __int64 v31; // r8
  _QWORD *v32; // rax
  _QWORD *v33; // rdi
  int v34; // eax
  unsigned int v35; // r13d
  unsigned __int64 v36; // rax
  void *v37; // rax
  _QWORD *v38; // rdx
  unsigned __int16 *v39; // rbx
  __int64 i; // rdi
  __int64 v41; // r8
  __int64 v42; // r8
  const struct _CERT_CONTEXT *v43; // rdx
  unsigned int v44; // ecx
  int v45; // eax
  void *v46; // rcx
  __int64 v47; // [rsp+20h] [rbp-B1h]
  int v48; // [rsp+50h] [rbp-81h]
  unsigned int v49; // [rsp+54h] [rbp-7Dh] BYREF
  unsigned int v50; // [rsp+58h] [rbp-79h] BYREF
  void *Block; // [rsp+60h] [rbp-71h]
  struct _CERT_CONTEXT **v52; // [rsp+68h] [rbp-69h] BYREF
  struct _CERT_CONTEXT **v53; // [rsp+70h] [rbp-61h] BYREF
  const unsigned __int16 *v54; // [rsp+78h] [rbp-59h]
  wchar_t *v55; // [rsp+80h] [rbp-51h]
  _QWORD *v56; // [rsp+88h] [rbp-49h]
  struct _EVENT_DATA_DESCRIPTOR v57; // [rsp+90h] [rbp-41h] BYREF
  const wchar_t *v58; // [rsp+A0h] [rbp-31h]
  __int64 v59; // [rsp+A8h] [rbp-29h]
  const unsigned __int16 *v60; // [rsp+B0h] [rbp-21h]
  __int64 v61; // [rsp+B8h] [rbp-19h]

  v7 = L"TRUE";
  v8 = 0;
  v56 = a7;
  v9 = 0;
  v55 = a3;
  v10 = 0;
  v54 = a2;
  v11 = 0;
  v52 = 0;
  v12 = L"TRUE";
  v53 = 0;
  if ( !a6 )
    v12 = L"FALSE";
  v49 = 0;
  v50 = 0;
  if ( !a5 )
    v7 = L"FALSE";
  Block = 0;
  v15 = L"Unknown";
  if ( a4 )
  {
    switch ( a4 )
    {
      case 1u:
        v17 = L"RECOVERY";
        break;
      case 2u:
        v17 = L"RECOVERY_ALL";
        break;
      case 3u:
        v17 = L"OLDEST_NORMAL";
        break;
      case 4u:
        v17 = L"ALL";
        break;
      default:
        v17 = L"Unknown";
        break;
    }
  }
  else
  {
    v17 = L"NORMAL";
  }
  v18 = L"<NULL>";
  v19 = L"<NULL>";
  if ( v55 )
    v19 = v55;
  if ( a2 )
    v18 = a2;
  if ( a1 == 1 )
  {
    v15 = L"DEVICE";
  }
  else if ( a1 == 2 )
  {
    v15 = L"WORKPLACE";
  }
  Logger::TraceVerbose(
    L"%s started. joinType = %d (%s), tenantId = \"%s\", userEmail = \"%s\", infoKind = %d (%s), ignoreMetadataFailure = %"
     "s, useDefaultIfValueIsMissing = %s.",
    L"DeviceRegistrationStateApi::GetJoinInfo",
    a1,
    v15,
    v18,
    v19,
    a4,
    v17,
    v7,
    v12);
  if ( v56 )
  {
    *v56 = 0;
    if ( a1 == 1 || (v48 = 0, !a1) )
    {
      v29 = v54;
      Certificates = RegistrationCertStatus::GetCertificates(1, v20, (__int64)L"1", v54, v47, a4, &v52, &v49);
      v48 = Certificates;
      if ( Certificates == -2146885628 )
      {
        Logger::TraceVerbose(
          L"%s: RegistrationCertStatus::GetCertificates returned CRYPT_E_NOT_FOUND. Returning S_FALSE.",
          L"RegistrationCertStatus::GetJoinCertificates");
        v48 = 1;
        v31 = 1;
      }
      else
      {
        if ( Certificates < 0 )
        {
          v21 = Certificates;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"RegistrationCertStatus::GetJoinCertificates",
            L"RegistrationCertStatus::GetCertificates",
            (unsigned int)Certificates);
          Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetJoinCertificates", v21);
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"DeviceRegistrationStateApi::GetJoinInfo",
            L"RegistrationCertStatus::GetDeviceCertificates",
            v21);
          v9 = v52;
          v8 = v49;
          goto LABEL_17;
        }
        v31 = (unsigned int)Certificates;
      }
      Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetJoinCertificates", v31);
      v8 = v49;
      v9 = v52;
      if ( !v49 || !v52 )
        Logger::TraceVerbose(
          L"%s: RegistrationCertStatus::GetDeviceCertificates returned NO certificate.",
          L"DeviceRegistrationStateApi::GetJoinInfo");
    }
    else
    {
      v29 = v54;
    }
    if ( (a1 & 0xFFFFFFFD) == 0 )
    {
      v34 = RegistrationCertStatus::GetCertificates(0, v20, (__int64)L"0", v29, v47, a4, &v53, &v50);
      v48 = v34;
      v21 = v34;
      if ( v34 == -2146885628 )
      {
        Logger::TraceVerbose(
          L"%s: RegistrationCertStatus::GetCertificates returned CRYPT_E_NOT_FOUND. Returning S_FALSE.",
          L"RegistrationCertStatus::GetJoinCertificates");
        v48 = 1;
      }
      else if ( v34 < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationCertStatus::GetJoinCertificates",
          L"RegistrationCertStatus::GetCertificates",
          (unsigned int)v34);
        Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetJoinCertificates", v21);
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"DeviceRegistrationStateApi::GetJoinInfo",
          L"RegistrationCertStatus::GetWorkplaceCertificates",
          v21);
        v10 = v53;
        v11 = v50;
        goto LABEL_17;
      }
      Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetJoinCertificates");
      v11 = v50;
      v10 = v53;
      if ( !v50 || !v53 )
        Logger::TraceVerbose(
          L"%s: RegistrationCertStatus::GetWorkplaceCertificates returned NO certificate.",
          L"DeviceRegistrationStateApi::GetJoinInfo");
    }
    if ( v8 || v11 )
    {
      v32 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      Block = v32;
      v33 = v32;
      if ( !v32 )
        goto LABEL_32;
      v35 = v11 + v8;
      *(_OWORD *)v32 = 0;
      v32[2] = 0;
      *(_DWORD *)v32 = 2;
      v36 = 336LL * (v11 + v8);
      if ( !is_mul_ok(v11 + v8, 0x150u) )
        v36 = -1;
      v37 = operator new[](v36, (const struct std::nothrow_t *)&std::nothrow);
      v33[1] = v37;
      if ( !v37 )
      {
LABEL_32:
        v21 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::GetJoinInfo");
        goto LABEL_17;
      }
      memset_0(v37, 0, 336LL * (v11 + v8));
      v38 = Block;
      v39 = v55;
      *((_DWORD *)v33 + 4) = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v41 = *((unsigned int *)v38 + 4);
        if ( (unsigned int)i >= v35 )
          break;
        v42 = v38[1] + 336 * v41;
        if ( (unsigned int)i >= v8 )
          v43 = v10[(unsigned int)i - v8];
        else
          v43 = v9[i];
        v44 = 5;
        if ( (unsigned int)i < v8 )
          v44 = 1;
        v45 = DeviceRegistrationStateApi::PopulateJoinInfo(v44, v43, v39, a5, a6, v42);
        v48 = v45;
        if ( v45 < 0 )
        {
          if ( v45 != -2145648618 )
          {
            v21 = v45;
            Logger::TraceError(
              L"%s: DeviceRegistrationStateApi::PopulateJoinInfo failed with error code: 0x%08x.",
              L"DeviceRegistrationStateApi::GetJoinInfo",
              (unsigned int)v45);
            goto LABEL_17;
          }
          Logger::TraceError(
            L"%s: DeviceRegistrationStateApi::PopulateJoinInfo failed with error code: 0x%08x. Some join infor is missing."
             " Skip this certificate.",
            L"DeviceRegistrationStateApi::GetJoinInfo",
            2149318678LL);
          v38 = Block;
          v48 = 0;
        }
        else
        {
          v38 = Block;
          ++*((_DWORD *)Block + 4);
        }
      }
      if ( (_DWORD)v41 )
      {
        Logger::TraceVerbose(
          L"%s: Successfully read %lu accounts out of a total of %lu certificate(s).",
          L"DeviceRegistrationStateApi::GetJoinInfo",
          v41,
          v35);
        v46 = Block;
        v21 = v48;
        Block = 0;
        *v56 = v46;
        goto LABEL_17;
      }
      Logger::TraceWarning(
        L"%s: Cannot read any accounts out of a total of %lu certificate(s).",
        L"DeviceRegistrationStateApi::GetJoinInfo",
        v35);
    }
    else
    {
      Logger::TraceVerbose(L"%s: Found NO certificate.", L"DeviceRegistrationStateApi::GetJoinInfo");
    }
    v21 = 1;
    goto LABEL_17;
  }
  v21 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceRegistrationStateApi::GetJoinInfo", L"ppJoinInfo");
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v58 = L"DeviceRegistrationStateApi::GetJoinInfo";
    v59 = 80;
    v60 = L"ppJoinInfo";
    v61 = 22;
    v23 = McGenEventWrite_EventWriteTransfer(
            (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
            (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
            v22,
            3u,
            &v57);
    if ( v23 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v23);
  }
LABEL_17:
  if ( v9 )
  {
    for ( j = 0; (unsigned int)j < v8; *v25 = 0 )
    {
      v25 = (PCCERT_CONTEXT *)&v9[j];
      CertFreeCertificateContext(*v25);
      j = (unsigned int)(j + 1);
    }
  }
  if ( v10 )
  {
    for ( k = 0; k < v11; *v27 = 0 )
    {
      v27 = (PCCERT_CONTEXT *)&v10[k];
      CertFreeCertificateContext(*v27);
      ++k;
    }
  }
  operator delete(v9);
  operator delete(v10);
  DsrFreeJoinInfoEx(Block);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"DeviceRegistrationStateApi::GetJoinInfo", v21);
  return v21;
}

```

## disassembly

```asm
0x180006980  push    rbp
0x180006982  push    rbx
0x180006983  push    rsi
0x180006984  push    rdi
0x180006985  push    r12
0x180006987  push    r13
0x180006989  push    r14
0x18000698b  push    r15
0x18000698d  lea     rbp, [rsp-7]
0x180006992  sub     rsp, 0D8h
0x180006999  mov     rax, cs:__security_cookie
0x1800069a0  xor     rax, rsp
0x1800069a3  mov     [rbp+3Fh+var_50], rax
0x1800069a7  mov     rax, [rbp+3Fh+arg_30]
0x1800069ab  lea     r11, aTrue; "TRUE"
0x1800069b2  xor     esi, esi
0x1800069b4  mov     [rbp+3Fh+var_88], rax
0x1800069b8  xor     r12d, r12d
0x1800069bb  mov     [rbp+3Fh+var_90], r8
0x1800069bf  xor     r14d, r14d
0x1800069c2  mov     [rbp+3Fh+var_98], rdx
0x1800069c6  xor     r15d, r15d
0x1800069c9  mov     [rbp+3Fh+var_A8], r12
0x1800069cd  cmp     [rbp+3Fh+arg_28], esi
0x1800069d0  lea     rax, aFalse; "FALSE"
0x1800069d7  mov     rdi, r11
0x1800069da  mov     [rbp+3Fh+var_A0], r14
0x1800069de  cmovz   rdi, rax
0x1800069e2  mov     [rbp+3Fh+var_BC], esi
0x1800069e5  cmp     [rbp+3Fh+arg_20], esi
0x1800069e8  mov     r13d, r9d
0x1800069eb  mov     r10, rdx
0x1800069ee  mov     [rbp+3Fh+var_B8], r15d
0x1800069f2  cmovz   r11, rax
0x1800069f6  mov     [rbp+3Fh+Block], rsi
0x1800069fa  lea     r9, aUnknown; "Unknown"
0x180006a01  mov     ebx, ecx
0x180006a03  test    r13d, r13d
0x180006a06  jnz     loc_180006C85
0x180006a0c  lea     r8, aNormal; "NORMAL"
0x180006a13  mov     rax, [rbp+3Fh+var_90]
0x180006a17  lea     rcx, aNull_0; "<NULL>"
0x180006a1e  test    rax, rax
0x180006a21  mov     rdx, rcx
0x180006a24  cmovnz  rdx, rax
0x180006a28  test    r10, r10
0x180006a2b  cmovnz  rcx, r10
0x180006a2f  mov     r10d, ebx
0x180006a32  sub     r10d, 1
0x180006a36  jnz     loc_180006D3D
0x180006a3c  lea     r9, aDevice; "DEVICE"
0x180006a43  mov     [rsp+110h+var_C8], rdi
0x180006a48  lea     rdi, aDeviceregistra; "DeviceRegistrationStateApi::GetJoinInfo"
0x180006a4f  mov     [rsp+110h+var_D0], r11
0x180006a54  mov     [rsp+110h+var_D8], r8
0x180006a59  mov     r8d, ebx
0x180006a5c  mov     dword ptr [rsp+110h+var_E0], r13d
0x180006a61  mov     [rsp+110h+var_E8], rdx
0x180006a66  mov     rdx, rdi
0x180006a69  mov     [rsp+110h+var_F0], rcx
0x180006a6e  lea     rcx, aSStartedJointy; "%s started. joinType = %d (%s), tenantI"...
0x180006a75  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006a7a  mov     rax, [rbp+3Fh+var_88]
0x180006a7e  test    rax, rax
0x180006a81  jnz     loc_180006B9C
0x180006a87  lea     rbx, aPpjoininfo; "ppJoinInfo"
0x180006a8e  mov     rdx, rdi
0x180006a91  mov     r8, rbx
0x180006a94  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180006a9b  mov     r13d, 80070057h
0x180006aa1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006aa6  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180006aad  jz      short loc_180006AF1
0x180006aaf  lea     rax, [rbp+3Fh+var_80]
0x180006ab3  mov     [rbp+3Fh+var_70], rdi
0x180006ab7  mov     r9d, 3
0x180006abd  mov     [rsp+110h+var_F0], rax
0x180006ac2  lea     rdx, NullOrEmptyParameterFailureEvent
0x180006ac9  mov     [rbp+3Fh+var_68], 50h ; 'P'
0x180006ad1  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180006ad8  mov     [rbp+3Fh+var_60], rbx
0x180006adc  mov     [rbp+3Fh+var_58], 16h
0x180006ae4  call    McGenEventWrite_EventWriteTransfer
0x180006ae9  test    eax, eax
0x180006aeb  jnz     loc_180006D53
0x180006af1  test    r12, r12
0x180006af4  jz      short loc_180006B1B
0x180006af6  xor     edi, edi
0x180006af8  test    esi, esi
0x180006afa  jz      short loc_180006B1B
0x180006afc  nop     dword ptr [rax+00h]
0x180006b00  mov     rcx, [r12+rdi*8]; pCertContext
0x180006b04  lea     rbx, [r12+rdi*8]
0x180006b08  call    cs:__imp_CertFreeCertificateContext
0x180006b0e  inc     edi
0x180006b10  mov     qword ptr [rbx], 0
0x180006b17  cmp     edi, esi
0x180006b19  jb      short loc_180006B00
0x180006b1b  test    r14, r14
0x180006b1e  jz      short loc_180006B4A
0x180006b20  xor     esi, esi
0x180006b22  mov     ebx, esi
0x180006b24  test    r15d, r15d
0x180006b27  jz      short loc_180006B4A
0x180006b29  nop     dword ptr [rax+00000000h]
0x180006b30  mov     eax, ebx
0x180006b32  mov     rcx, [r14+rax*8]; pCertContext
0x180006b36  lea     rdi, [r14+rax*8]
0x180006b3a  call    cs:__imp_CertFreeCertificateContext
0x180006b40  inc     ebx
0x180006b42  mov     [rdi], rsi
0x180006b45  cmp     ebx, r15d
0x180006b48  jb      short loc_180006B30
0x180006b4a  mov     rcx, r12; Block
0x180006b4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b52  mov     rcx, r14; Block
0x180006b55  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b5a  mov     rcx, [rbp+3Fh+Block]; Block
0x180006b5e  call    DsrFreeJoinInfoEx
0x180006b63  mov     r8d, r13d
0x180006b66  lea     rdx, aDeviceregistra; "DeviceRegistrationStateApi::GetJoinInfo"
0x180006b6d  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180006b74  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006b79  mov     eax, r13d
0x180006b7c  mov     rcx, [rbp+3Fh+var_50]
0x180006b80  xor     rcx, rsp; StackCookie
0x180006b83  call    __security_check_cookie
0x180006b88  add     rsp, 0D8h
0x180006b8f  pop     r15
0x180006b91  pop     r14
0x180006b93  pop     r13
0x180006b95  pop     r12
0x180006b97  pop     rdi
0x180006b98  pop     rsi
0x180006b99  pop     rbx
0x180006b9a  pop     rbp
0x180006b9b  retn
0x180006b9c  mov     [rax], rsi
0x180006b9f  cmp     ebx, 1
0x180006ba2  jnz     loc_180006D75
0x180006ba8  mov     rdi, [rbp+3Fh+var_98]
0x180006bac  lea     rax, [rbp+3Fh+var_BC]
0x180006bb0  mov     [rsp+110h+var_D8], rax
0x180006bb5  lea     r8, a1; "1"
0x180006bbc  lea     rax, [rbp+3Fh+var_A8]
0x180006bc0  mov     r9, rdi
0x180006bc3  mov     [rsp+110h+var_E0], rax
0x180006bc8  mov     ecx, 1
0x180006bcd  mov     dword ptr [rsp+110h+var_E8], r13d
0x180006bd2  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * * *,ulong *)
0x180006bd7  mov     [rsp+110h+var_C0], eax
0x180006bdb  cmp     eax, 80092004h
0x180006be0  jnz     loc_180006D8C
0x180006be6  lea     rsi, aRegistrationce; "RegistrationCertStatus::GetJoinCertific"...
0x180006bed  mov     rdx, rsi
0x180006bf0  lea     rcx, aSRegistrationc_1; "%s: RegistrationCertStatus::GetCertific"...
0x180006bf7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006bfc  mov     edx, 1
0x180006c01  mov     [rsp+110h+var_C0], edx
0x180006c05  mov     r8d, edx
0x180006c08  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180006c0f  mov     rdx, rsi
0x180006c12  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006c17  mov     esi, [rbp+3Fh+var_BC]
0x180006c1a  mov     r12, [rbp+3Fh+var_A8]
0x180006c1e  test    esi, esi
0x180006c20  jz      loc_180006DFD
0x180006c26  test    r12, r12
0x180006c29  jz      loc_180006DFD
0x180006c2f  test    ebx, 0FFFFFFFDh
0x180006c35  jz      loc_180006E15
0x180006c3b  lea     rdi, aDeviceregistra; "DeviceRegistrationStateApi::GetJoinInfo"
0x180006c42  test    esi, esi
0x180006c44  jz      short loc_180006CAB
0x180006c46  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006c4d  mov     ecx, 18h; unsigned __int64
0x180006c52  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006c57  mov     [rbp+3Fh+Block], rax
0x180006c5b  mov     rdi, rax
0x180006c5e  test    rax, rax
0x180006c61  jnz     loc_180006EE8
0x180006c67  lea     rdx, aDeviceregistra; "DeviceRegistrationStateApi::GetJoinInfo"
0x180006c6e  mov     r13d, 8007000Eh
0x180006c74  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180006c7b  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180006c80  jmp     loc_180006AF1
0x180006c85  mov     ecx, r13d
0x180006c88  sub     ecx, 1
0x180006c8b  jz      loc_180006D31
0x180006c91  sub     ecx, 1
0x180006c94  jz      loc_180006D25
0x180006c9a  sub     ecx, 1
0x180006c9d  jnz     short loc_180006D0C
0x180006c9f  lea     r8, aOldestNormal; "OLDEST_NORMAL"
0x180006ca6  jmp     loc_180006A13
0x180006cab  test    r15d, r15d
0x180006cae  jnz     short loc_180006C46
0x180006cb0  mov     rdx, rdi
0x180006cb3  lea     rcx, aSFoundNoCertif; "%s: Found NO certificate."
0x180006cba  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006cbf  mov     r13d, 1
0x180006cc5  jmp     loc_180006AF1
0x180006cca  lea     rax, aRegistrationce; "RegistrationCertStatus::GetJoinCertific"...
0x180006cd1  mov     rdx, rax
0x180006cd4  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180006cdb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006ce0  mov     r15d, [rbp+3Fh+var_B8]
0x180006ce4  mov     r14, [rbp+3Fh+var_A0]
0x180006ce8  test    r15d, r15d
0x180006ceb  jnz     loc_180006EDA
0x180006cf1  lea     rdi, aDeviceregistra; "DeviceRegistrationStateApi::GetJoinInfo"
0x180006cf8  mov     rdx, rdi
0x180006cfb  lea     rcx, aSRegistrationc_0; "%s: RegistrationCertStatus::GetWorkplac"...
0x180006d02  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006d07  jmp     loc_180006C42
0x180006d0c  cmp     ecx, 1
0x180006d0f  jz      short loc_180006D19
0x180006d11  mov     r8, r9
0x180006d14  jmp     loc_180006A13
0x180006d19  lea     r8, aAll; "ALL"
0x180006d20  jmp     loc_180006A13
0x180006d25  lea     r8, aRecoveryAll; "RECOVERY_ALL"
0x180006d2c  jmp     loc_180006A13
0x180006d31  lea     r8, aRecovery; "RECOVERY"
0x180006d38  jmp     loc_180006A13
0x180006d3d  cmp     r10d, 1
0x180006d41  jnz     loc_180006A43
0x180006d47  lea     r9, aWorkplace; "WORKPLACE"
0x180006d4e  jmp     loc_180006A43
0x180006d53  mov     r9d, eax
0x180006d56  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180006d5d  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180006d64  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180006d6b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006d70  jmp     loc_180006AF1
0x180006d75  xor     eax, eax
0x180006d77  mov     [rsp+110h+var_C0], eax
0x180006d7b  test    ebx, ebx
0x180006d7d  jz      loc_180006BA8
0x180006d83  mov     rdi, [rbp+3Fh+var_98]
0x180006d87  jmp     loc_180006C2F
0x180006d8c  test    eax, eax
0x180006d8e  jns     short loc_180006DEE
0x180006d90  lea     rbx, aRegistrationce; "RegistrationCertStatus::GetJoinCertific"...
0x180006d97  mov     r9d, eax
0x180006d9a  mov     rdx, rbx
0x180006d9d  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180006da4  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180006dab  mov     r13d, eax
0x180006dae  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006db3  mov     r8d, r13d
0x180006db6  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180006dbd  mov     rdx, rbx
0x180006dc0  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006dc5  mov     r9d, r13d
0x180006dc8  lea     r8, aRegistrationce_5; "RegistrationCertStatus::GetDeviceCertif"...
0x180006dcf  lea     rdx, aDeviceregistra; "DeviceRegistrationStateApi::GetJoinInfo"
0x180006dd6  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180006ddd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006de2  mov     r12, [rbp+3Fh+var_A8]
0x180006de6  mov     esi, [rbp+3Fh+var_BC]
0x180006de9  jmp     loc_180006AF1
0x180006dee  lea     rsi, aRegistrationce; "RegistrationCertStatus::GetJoinCertific"...
0x180006df5  mov     r8d, eax
0x180006df8  jmp     loc_180006C08
0x180006dfd  lea     rdx, aDeviceregistra; "DeviceRegistrationStateApi::GetJoinInfo"
0x180006e04  lea     rcx, aSRegistrationc; "%s: RegistrationCertStatus::GetDeviceCe"...
0x180006e0b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006e10  jmp     loc_180006C2F
0x180006e15  lea     rax, [rbp+3Fh+var_B8]
0x180006e19  mov     r9, rdi
0x180006e1c  mov     [rsp+110h+var_D8], rax
0x180006e21  lea     r8, a0; "0"
0x180006e28  lea     rax, [rbp+3Fh+var_A0]
0x180006e2c  xor     ecx, ecx
0x180006e2e  mov     [rsp+110h+var_E0], rax
0x180006e33  mov     dword ptr [rsp+110h+var_E8], r13d
0x180006e38  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * * *,ulong *)
0x180006e3d  mov     [rsp+110h+var_C0], eax
0x180006e41  mov     r13d, eax
0x180006e44  cmp     eax, 80092004h
0x180006e49  jnz     short loc_180006E71
0x180006e4b  lea     rdx, aRegistrationce; "RegistrationCertStatus::GetJoinCertific"...
0x180006e52  lea     rcx, aSRegistrationc_1; "%s: RegistrationCertStatus::GetCertific"...
0x180006e59  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180006e5e  mov     r8d, 1
0x180006e64  mov     [rsp+110h+var_C0], 1
0x180006e6c  jmp     loc_180006CCA
0x180006e71  test    r13d, r13d
0x180006e74  jns     short loc_180006ED2
0x180006e76  lea     rbx, aRegistrationce; "RegistrationCertStatus::GetJoinCertific"...
0x180006e7d  mov     r9d, r13d
0x180006e80  mov     rdx, rbx
0x180006e83  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x180006e8a  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180006e91  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180006e96  mov     r8d, r13d
0x180006e99  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180006ea0  mov     rdx, rbx
0x180006ea3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
  ... truncated ...
```
