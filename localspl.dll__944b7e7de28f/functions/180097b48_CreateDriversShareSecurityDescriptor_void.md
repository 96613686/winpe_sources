# CreateDriversShareSecurityDescriptor(void)

- ea: `0x180097b48`
- end: `0x180097f08`
- name: `?CreateDriversShareSecurityDescriptor@@YAPEAXXZ`
- size: `960`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180075f58`

## callees

- `0x1800239a0`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x1800547e0`
- `0x180097b48`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x180097d2f`
- `ntdll!RtlGetNtProductType` at `0x180097d2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e7c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097bfe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097c5a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097cc2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097d97`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097e07`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097bfe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097c5a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097cc2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097d97`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180097e07`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ea6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097eb6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ec5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ed5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ee4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ea6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097eb6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ec5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ed5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180097ee4`

## string_xrefs

- `0x180097c0e`: `Couldn't allocate and initialize Creator-Owner SID.  Error %d`
- `0x180097c18`: `CreateDriversShareSecurityDescriptor`
- `0x180097d49`: `CreateDriversShareSecurityDescriptor`
- `0x180097e8c`: `CreateDriversShareSecurityDescriptor`
- `0x180097cd2`: `Couldn't allocate and initialize Admin SID.  Error %d`
- `0x180097e17`: `Couldn't allocate and initialize System Operators SID.  Error %d`
- `0x180097c6a`: `Couldn't allocate and initialize World SID.  Error %d`
- `0x180097da7`: `Couldn't allocate and initialize Printer Operators SID.  Error %d`

## pseudocode

```c
__int64 CreateDriversShareSecurityDescriptor(void)
{
  __int64 v0; // rdi
  DWORD v1; // eax
  DWORD LastError; // eax
  DWORD v3; // eax
  int v4; // ebx
  DWORD v5; // eax
  DWORD v6; // eax
  DWORD v7; // eax
  PSID v8; // rax
  __int64 v9; // rdx
  DWORD v10; // eax
  DWORD nSubAuthority5; // [rsp+38h] [rbp-C8h]
  _NT_PRODUCT_TYPE ProductType; // [rsp+60h] [rbp-A0h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-98h] BYREF
  PSID v15; // [rsp+70h] [rbp-90h] BYREF
  PSID v16; // [rsp+78h] [rbp-88h] BYREF
  PSID v17; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  PSID pSid; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v20[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v21[32]; // [rsp+B0h] [rbp-50h] BYREF
  int v22[20]; // [rsp+D0h] [rbp-30h] BYREF
  int v23[2]; // [rsp+120h] [rbp+20h] BYREF
  PSID v24; // [rsp+128h] [rbp+28h]
  PSID v25[18]; // [rsp+130h] [rbp+30h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v26; // [rsp+1C0h] [rbp+C0h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+1C8h] [rbp+C8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v28; // [rsp+1D0h] [rbp+D0h] BYREF

  ProductType = 0;
  memset_0(v25, 0, sizeof(v25));
  *(_DWORD *)v26.Value = 0;
  v0 = 0;
  *(_WORD *)&v26.Value[4] = 1280;
  *(_DWORD *)v28.Value = 0;
  *(_WORD *)&v28.Value[4] = 256;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 768;
  v15 = 0;
  pOwner = 0;
  v16 = 0;
  v17 = 0;
  pSid = 0;
  v18 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    if ( !AllocateAndInitializeSid(&v28, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v15) )
    {
      LastError = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateDriversShareSecurityDescriptor",
        L"Couldn't allocate and initialize World SID.  Error %d",
        LastError);
      goto LABEL_21;
    }
    *(_QWORD *)v23 = v15;
    v21[0] = 0;
    v22[0] = -1610612736;
    v20[0] = 0;
    if ( !AllocateAndInitializeSid(&v26, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner) )
    {
      v3 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateDriversShareSecurityDescriptor",
        L"Couldn't allocate and initialize Admin SID.  Error %d",
        v3);
      goto LABEL_21;
    }
    v4 = 2;
    v24 = pOwner;
    v21[1] = 0;
    v22[1] = 0x10000000;
    v20[1] = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    {
      v4 = 3;
      v25[0] = gRestrictedSpoolerServiceSid;
      v21[2] = 0;
      v22[2] = 0x10000000;
      v20[2] = 0;
    }
    if ( !RtlGetNtProductType(&ProductType) )
    {
      v5 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateDriversShareSecurityDescriptor",
        L"Couldn't get NT Product Type.  Error %d",
        v5);
    }
    if ( ProductType == NtProductLanManNt )
    {
      if ( !AllocateAndInitializeSid(&v26, 2u, 0x20u, 0x226u, 0, 0, 0, 0, 0, 0, &v16) )
      {
        v6 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "CreateDriversShareSecurityDescriptor",
          L"Couldn't allocate and initialize Printer Operators SID.  Error %d",
          v6);
        goto LABEL_21;
      }
      *(_QWORD *)&v23[2 * v4] = v16;
      v21[v4] = 0;
      v22[v4] = 0x10000000;
      v20[v4] = 0;
      if ( !AllocateAndInitializeSid(&v26, 2u, 0x20u, 0x225u, 0, 0, 0, 0, 0, 0, &v17) )
      {
        v7 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "CreateDriversShareSecurityDescriptor",
          L"Couldn't allocate and initialize System Operators SID.  Error %d",
          v7);
        goto LABEL_21;
      }
      v8 = v17;
      v9 = (unsigned int)(v4 + 1);
      v21[v9] = 0;
      v4 += 2;
      *(_QWORD *)&v23[2 * v9] = v8;
      v22[v9] = 0x10000000;
      v20[v9] = 0;
    }
    if ( !(unsigned int)BuildPrintObjectProtection(
                          (int)v21,
                          v4,
                          (int)v23,
                          (int)v22,
                          (__int64)v20,
                          pOwner,
                          pOwner,
                          nSubAuthority5,
                          (__int64)&v18) )
    {
      v10 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreateDriversShareSecurityDescriptor",
        L"BuildPrintObjectProtection failed.  Error %d",
        v10);
    }
    v0 = v18;
  }
  else
  {
    v1 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateDriversShareSecurityDescriptor",
      L"Couldn't allocate and initialize Creator-Owner SID.  Error %d",
      v1);
  }
LABEL_21:
  if ( v15 )
    FreeSid(v15);
  if ( pOwner )
    FreeSid(pOwner);
  if ( pSid )
    FreeSid(pSid);
  if ( v16 )
    FreeSid(v16);
  if ( v17 )
    FreeSid(v17);
  return v0;
}

```

## disassembly

```asm
0x180097b48  push    rbp
0x180097b4a  push    rbx
0x180097b4b  push    rsi
0x180097b4c  push    rdi
0x180097b4d  lea     rbp, [rsp-0E8h]
0x180097b55  sub     rsp, 1E8h
0x180097b5c  mov     rax, cs:__security_cookie
0x180097b63  xor     rax, rsp
0x180097b66  mov     [rbp+100h+var_28], rax
0x180097b6d  xor     esi, esi
0x180097b6f  lea     rcx, [rbp+100h+var_D0]; void *
0x180097b73  xor     edx, edx; Val
0x180097b75  mov     [rsp+200h+ProductType], esi
0x180097b79  mov     r8d, 90h; Size
0x180097b7f  call    memset_0
0x180097b84  lea     rax, [rbp+100h+var_170]
0x180097b88  mov     dword ptr [rbp+100h+var_40.Value], esi
0x180097b8e  mov     [rsp+200h+pSid], rax; pSid
0x180097b93  lea     rcx, [rbp+100h+pIdentifierAuthority]; pIdentifierAuthority
0x180097b9a  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180097b9e  xor     r9d, r9d; nSubAuthority1
0x180097ba1  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180097ba5  xor     r8d, r8d; nSubAuthority0
0x180097ba8  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x180097bac  mov     dl, 1; nSubAuthorityCount
0x180097bae  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x180097bb2  mov     edi, esi
0x180097bb4  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x180097bb8  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x180097bbc  mov     word ptr [rbp+100h+var_40.Value+4], 500h
0x180097bc5  mov     dword ptr [rbp+100h+var_30.Value], esi
0x180097bcb  mov     word ptr [rbp+100h+var_30.Value+4], 100h
0x180097bd4  mov     dword ptr [rbp+100h+pIdentifierAuthority.Value], esi
0x180097bda  mov     word ptr [rbp+100h+pIdentifierAuthority.Value+4], 300h
0x180097be3  mov     [rsp+200h+var_190], rsi
0x180097be8  mov     [rsp+200h+pOwner], rsi
0x180097bed  mov     [rsp+200h+var_188], rsi
0x180097bf2  mov     [rbp+100h+var_180], rsi
0x180097bf6  mov     [rbp+100h+var_170], rsi
0x180097bfa  mov     [rbp+100h+var_178], rsi
0x180097bfe  call    cs:__imp_AllocateAndInitializeSid
0x180097c04  test    eax, eax
0x180097c06  jnz     short loc_180097C29
0x180097c08  call    cs:__imp_GetLastError
0x180097c0e  lea     rdx, aCouldnTAllocat_7; "Couldn't allocate and initialize Creato"...
0x180097c15  mov     r8d, eax
0x180097c18  lea     rcx, aCreatedriverss; "CreateDriversShareSecurityDescriptor"
0x180097c1f  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180097c24  jmp     loc_180097E9C
0x180097c29  lea     rax, [rsp+200h+var_190]
0x180097c2e  xor     r9d, r9d; nSubAuthority1
0x180097c31  mov     [rsp+200h+pSid], rax; pSid
0x180097c36  lea     rcx, [rbp+100h+var_30]; pIdentifierAuthority
0x180097c3d  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180097c41  xor     r8d, r8d; nSubAuthority0
0x180097c44  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180097c48  mov     dl, 1; nSubAuthorityCount
0x180097c4a  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x180097c4e  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x180097c52  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x180097c56  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x180097c5a  call    cs:__imp_AllocateAndInitializeSid
0x180097c60  test    eax, eax
0x180097c62  jnz     short loc_180097C73
0x180097c64  call    cs:__imp_GetLastError
0x180097c6a  lea     rdx, aCouldnTAllocat_8; "Couldn't allocate and initialize World "...
0x180097c71  jmp     short loc_180097C15
0x180097c73  mov     rax, [rsp+200h+var_190]
0x180097c78  lea     rcx, [rbp+100h+var_40]; pIdentifierAuthority
0x180097c7f  mov     qword ptr [rbp+100h+var_E0], rax
0x180097c83  mov     r9d, 220h; nSubAuthority1
0x180097c89  lea     rax, [rsp+200h+pOwner]
0x180097c8e  mov     [rbp+100h+var_150], sil
0x180097c92  mov     [rsp+200h+pSid], rax; pSid
0x180097c97  mov     r8d, 20h ; ' '; nSubAuthority0
0x180097c9d  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180097ca1  mov     dl, 2; nSubAuthorityCount
0x180097ca3  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180097ca7  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x180097cab  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x180097caf  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x180097cb3  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x180097cb7  mov     [rbp+100h+var_130], 0A0000000h
0x180097cbe  mov     [rbp+100h+var_168], sil
0x180097cc2  call    cs:__imp_AllocateAndInitializeSid
0x180097cc8  test    eax, eax
0x180097cca  jnz     short loc_180097CDE
0x180097ccc  call    cs:__imp_GetLastError
0x180097cd2  lea     rdx, aCouldnTAllocat_6; "Couldn't allocate and initialize Admin "...
0x180097cd9  jmp     loc_180097C15
0x180097cde  mov     rax, [rsp+200h+pOwner]
0x180097ce3  mov     ebx, 2
0x180097ce8  mov     [rbp+100h+var_D8], rax
0x180097cec  mov     [rbp+100h+var_150+1], sil
0x180097cf0  mov     [rbp+100h+var_12C], 10000000h
0x180097cf7  mov     [rbp+100h+var_168+1], sil
0x180097cfb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180097d02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180097d07  test    al, al
0x180097d09  jz      short loc_180097D2A
0x180097d0b  mov     rax, cs:?gRestrictedSpoolerServiceSid@@3PEAXEA; void * gRestrictedSpoolerServiceSid
0x180097d12  mov     ebx, 3
0x180097d17  mov     [rbp+100h+var_D0], rax
0x180097d1b  mov     [rbp+100h+var_150+2], sil
0x180097d1f  mov     [rbp+100h+var_128], 10000000h
0x180097d26  mov     [rbp+100h+var_168+2], sil
0x180097d2a  lea     rcx, [rsp+200h+ProductType]; ProductType
0x180097d2f  call    cs:__imp_RtlGetNtProductType
0x180097d35  test    al, al
0x180097d37  jnz     short loc_180097D55
0x180097d39  call    cs:__imp_GetLastError
0x180097d3f  mov     r8d, eax
0x180097d42  lea     rdx, aCouldnTGetNtPr; "Couldn't get NT Product Type.  Error %d"
0x180097d49  lea     rcx, aCreatedriverss; "CreateDriversShareSecurityDescriptor"
0x180097d50  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180097d55  cmp     [rsp+200h+ProductType], 2
0x180097d5a  jnz     loc_180097E44
0x180097d60  lea     rax, [rsp+200h+var_188]
0x180097d65  mov     r9d, 226h; nSubAuthority1
0x180097d6b  mov     [rsp+200h+pSid], rax; pSid
0x180097d70  lea     rcx, [rbp+100h+var_40]; pIdentifierAuthority
0x180097d77  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180097d7b  mov     r8d, 20h ; ' '; nSubAuthority0
0x180097d81  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180097d85  mov     dl, 2; nSubAuthorityCount
0x180097d87  mov     [rsp+200h+nSubAuthority5], esi; nSubAuthority5
0x180097d8b  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x180097d8f  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x180097d93  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x180097d97  call    cs:__imp_AllocateAndInitializeSid
0x180097d9d  test    eax, eax
0x180097d9f  jnz     short loc_180097DB3
0x180097da1  call    cs:__imp_GetLastError
0x180097da7  lea     rdx, aCouldnTAllocat_4; "Couldn't allocate and initialize Printe"...
0x180097dae  jmp     loc_180097C15
0x180097db3  mov     rax, [rsp+200h+var_188]
0x180097db8  mov     r9d, 225h; nSubAuthority1
0x180097dbe  mov     ecx, ebx
0x180097dc0  mov     r8d, 20h ; ' '; nSubAuthority0
0x180097dc6  mov     dl, 2; nSubAuthorityCount
0x180097dc8  mov     qword ptr [rbp+rcx*8+100h+var_E0], rax
0x180097dcd  lea     rax, [rbp+100h+var_180]
0x180097dd1  mov     [rsp+200h+pSid], rax; pSid
0x180097dd6  mov     [rsp+200h+nSubAuthority7], esi; nSubAuthority7
0x180097dda  mov     [rsp+200h+nSubAuthority6], esi; nSubAuthority6
0x180097dde  mov     [rsp+200h+nSubAuthority5], esi; dwBufferLength
0x180097de2  mov     [rsp+200h+nSubAuthority4], esi; nSubAuthority4
0x180097de6  mov     [rbp+rcx+100h+var_150], sil
0x180097deb  mov     [rbp+rcx*4+100h+var_130], 10000000h
0x180097df3  mov     [rbp+rcx+100h+var_168], sil
0x180097df8  lea     rcx, [rbp+100h+var_40]; pIdentifierAuthority
0x180097dff  mov     [rsp+200h+nSubAuthority3], esi; nSubAuthority3
0x180097e03  mov     [rsp+200h+nSubAuthority2], esi; nSubAuthority2
0x180097e07  call    cs:__imp_AllocateAndInitializeSid
0x180097e0d  test    eax, eax
0x180097e0f  jnz     short loc_180097E23
0x180097e11  call    cs:__imp_GetLastError
0x180097e17  lea     rdx, aCouldnTAllocat_0; "Couldn't allocate and initialize System"...
0x180097e1e  jmp     loc_180097C15
0x180097e23  mov     rax, [rbp+100h+var_180]
0x180097e27  lea     edx, [rbx+1]
0x180097e2a  mov     [rbp+rdx+100h+var_150], sil
0x180097e2f  lea     ebx, [rdx+1]
0x180097e32  mov     qword ptr [rbp+rdx*8+100h+var_E0], rax
0x180097e37  mov     [rbp+rdx*4+100h+var_130], 10000000h
0x180097e3f  mov     [rbp+rdx+100h+var_168], sil
0x180097e44  lea     rax, [rbp+100h+var_178]
0x180097e48  mov     edx, ebx; int
0x180097e4a  mov     qword ptr [rsp+200h+nSubAuthority6], rax; __int64
0x180097e4f  lea     r9, [rbp+100h+var_130]; int
0x180097e53  mov     rax, [rsp+200h+pOwner]
0x180097e58  lea     r8, [rbp+100h+var_E0]; int
0x180097e5c  mov     qword ptr [rsp+200h+nSubAuthority4], rax; pGroup
0x180097e61  lea     rcx, [rbp+100h+var_150]; int
0x180097e65  mov     qword ptr [rsp+200h+nSubAuthority3], rax; pOwner
0x180097e6a  lea     rax, [rbp+100h+var_168]
0x180097e6e  mov     qword ptr [rsp+200h+nSubAuthority2], rax; __int64
0x180097e73  call    BuildPrintObjectProtection
0x180097e78  test    eax, eax
0x180097e7a  jnz     short loc_180097E98
0x180097e7c  call    cs:__imp_GetLastError
0x180097e82  mov     r8d, eax
0x180097e85  lea     rdx, aBuildprintobje; "BuildPrintObjectProtection failed.  Err"...
0x180097e8c  lea     rcx, aCreatedriverss; "CreateDriversShareSecurityDescriptor"
0x180097e93  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180097e98  mov     rdi, [rbp+100h+var_178]
0x180097e9c  mov     rcx, [rsp+200h+var_190]; pSid
0x180097ea1  test    rcx, rcx
0x180097ea4  jz      short loc_180097EAC
0x180097ea6  call    cs:__imp_FreeSid
0x180097eac  mov     rcx, [rsp+200h+pOwner]; pSid
0x180097eb1  test    rcx, rcx
0x180097eb4  jz      short loc_180097EBC
0x180097eb6  call    cs:__imp_FreeSid
0x180097ebc  mov     rcx, [rbp+100h+var_170]; pSid
0x180097ec0  test    rcx, rcx
0x180097ec3  jz      short loc_180097ECB
0x180097ec5  call    cs:__imp_FreeSid
0x180097ecb  mov     rcx, [rsp+200h+var_188]; pSid
0x180097ed0  test    rcx, rcx
0x180097ed3  jz      short loc_180097EDB
0x180097ed5  call    cs:__imp_FreeSid
0x180097edb  mov     rcx, [rbp+100h+var_180]; pSid
0x180097edf  test    rcx, rcx
0x180097ee2  jz      short loc_180097EEA
0x180097ee4  call    cs:__imp_FreeSid
0x180097eea  mov     rax, rdi
0x180097eed  mov     rcx, [rbp+100h+var_28]
0x180097ef4  xor     rcx, rsp; StackCookie
0x180097ef7  call    __security_check_cookie
0x180097efc  add     rsp, 1E8h
0x180097f03  pop     rdi
0x180097f04  pop     rsi
0x180097f05  pop     rbx
0x180097f06  pop     rbp
0x180097f07  retn
```
