# CreateServerSecurityDescriptor(void)

- ea: `0x180098628`
- end: `0x180098bc3`
- name: `?CreateServerSecurityDescriptor@@YAPEAXXZ`
- size: `1435`
- prototype: `void *(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180078b74`
- `0x1800990c0`

## callees

- `0x1800239a0`
- `0x180029dd8`
- `0x18003ea2c`
- `0x180046650`
- `0x180046ac0`
- `0x180047330`
- `0x1800547e0`
- `0x180098628`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x180098997`
- `ntdll!RtlGetNtProductType` at `0x180098997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800989a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800989fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800989a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800989fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098b34`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800986e4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009875e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800987a0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800989f3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098a85`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800986e4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18009875e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800987a0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800989f3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098a85`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b59`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b68`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b86`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b95`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b59`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b68`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b77`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b86`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180098b95`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098702`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098720`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098702`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098720`

## string_xrefs

- `0x180098a03`: `Couldn't allocate and init Print Operators SID.  Error %d`
- `0x180098a95`: `Couldn't allocate and init System Operator SID.  Error %d`
- `0x180098b44`: `CreateServerSecurityDescriptor`
- `0x180098af2`: `ACE count exceeded while creating SIDs.  Error %d`

## pseudocode

```c
__int64 CreateServerSecurityDescriptor(void)
{
  unsigned int v0; // edx
  PSID v1; // r8
  PSID v2; // rax
  __int64 v3; // rcx
  PSID v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rbx
  DWORD LastError; // eax
  DWORD v14; // eax
  __int64 v15; // rbx
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD nSubAuthority5; // [rsp+38h] [rbp-C8h]
  __int64 v21[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v22[6]; // [rsp+78h] [rbp-88h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+90h] [rbp-70h] BYREF
  PSID pOwner; // [rsp+98h] [rbp-68h] BYREF
  DWORD cbSid; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v26; // [rsp+A4h] [rbp-5Ch] BYREF
  PSID v27; // [rsp+A8h] [rbp-58h] BYREF
  PSID pSid; // [rsp+B0h] [rbp-50h] BYREF
  PSID v29; // [rsp+B8h] [rbp-48h] BYREF
  PSID v30; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+C8h] [rbp-38h] BYREF
  int v32[20]; // [rsp+D0h] [rbp-30h] BYREF
  int v33[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE *v34; // [rsp+128h] [rbp+28h]
  struct _SID_IDENTIFIER_AUTHORITY v35; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+1C8h] [rbp+C8h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v37; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v38[80]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v39[80]; // [rsp+230h] [rbp+130h] BYREF

  cbSid = 68;
  v26 = 68;
  ProductType = 0;
  memset_0(v33, 0, 0xA0u);
  *(_DWORD *)v35.Value = 0;
  *(_WORD *)&v35.Value[4] = 1280;
  *(_DWORD *)v37.Value = 0;
  *(_WORD *)&v37.Value[4] = 256;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 768;
  v27 = 0;
  pOwner = 0;
  v29 = 0;
  v30 = 0;
  pSid = 0;
  v31 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || !CreateWellKnownSid(WinInteractiveSid, 0, v39, &cbSid)
    || !CreateWellKnownSid(WinBuiltinGuestsSid, 0, v38, &v26)
    || !AllocateAndInitializeSid(&v37, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v27)
    || !AllocateAndInitializeSid(&v35, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner) )
  {
    goto LABEL_33;
  }
  if ( !(unsigned int)ServerSku() )
  {
    LOWORD(v22[0]) = 1;
    *(_QWORD *)v33 = v38;
    v0 = 2;
    v32[0] = 1;
    v34 = v39;
    LOWORD(v21[0]) = 0;
    v32[1] = 983043;
  }
  v1 = gAppContainerAllAppsSid;
  v2 = pSid;
  *((_BYTE *)v22 + v0) = 0;
  *(_QWORD *)&v33[2 * v0] = v2;
  v32[v0] = 0x10000000;
  *((_BYTE *)v21 + v0) = 9;
  v3 = v0 + 1;
  v4 = v27;
  *((_BYTE *)v22 + v3) = 0;
  *(_QWORD *)&v33[2 * v3] = v1;
  v32[v3] = 0x10000000;
  *((_BYTE *)v21 + v3) = 9;
  v5 = (unsigned int)(v3 + 1);
  *((_BYTE *)v22 + v5) = 0;
  *(_QWORD *)&v33[2 * v5] = v4;
  v32[v5] = 131074;
  *((_BYTE *)v21 + v5) = 0;
  v6 = (unsigned int)(v5 + 1);
  *((_BYTE *)v22 + v6) = 0;
  *(_QWORD *)&v33[2 * v6] = v4;
  v32[v6] = 0x20000000;
  *((_BYTE *)v21 + v6) = 10;
  v7 = (unsigned int)(v6 + 1);
  *((_BYTE *)v22 + v7) = 0;
  *(_QWORD *)&v33[2 * v7] = v1;
  v32[v7] = 131074;
  *((_BYTE *)v21 + v7) = 0;
  v8 = (unsigned int)(v7 + 1);
  *((_BYTE *)v22 + v8) = 0;
  *(_QWORD *)&v33[2 * v8] = v1;
  v32[v8] = 0x20000000;
  *((_BYTE *)v21 + v8) = 10;
  v9 = (unsigned int)(v8 + 1);
  if ( (unsigned int)v9 >= 0x14 )
    goto LABEL_44;
  v4 = pOwner;
  *(_QWORD *)&v33[2 * v9] = pOwner;
  *((_BYTE *)v22 + v9) = 0;
  v32[v9] = 983043;
  *((_BYTE *)v21 + v9) = 0;
  v9 = (unsigned int)(v9 + 1);
  if ( (unsigned int)v9 >= 0x14 )
    goto LABEL_44;
  *((_BYTE *)v22 + v9) = 0;
  *(_QWORD *)&v33[2 * v9] = v4;
  v32[v9] = 0x10000000;
  *((_BYTE *)v21 + v9) = 11;
  v9 = (unsigned int)(v9 + 1);
  if ( (unsigned int)v9 >= 0x14 )
    goto LABEL_44;
  v4 = gLPACCapabilitySid;
  *(_QWORD *)&v33[2 * v9] = gLPACCapabilitySid;
  *((_BYTE *)v22 + v9) = 0;
  v32[v9] = 0x10000000;
  *((_BYTE *)v21 + v9) = 9;
  v9 = (unsigned int)(v9 + 1);
  if ( (unsigned int)v9 >= 0x14 )
    goto LABEL_44;
  v10 = (unsigned int)(v9 + 1);
  *((_BYTE *)v22 + v9) = 0;
  *(_QWORD *)&v33[2 * v9] = v4;
  v32[v9] = 131074;
  *((_BYTE *)v21 + v9) = 0;
  if ( (unsigned int)v10 >= 0x14 )
    goto LABEL_44;
  *((_BYTE *)v22 + v10) = 0;
  *(_QWORD *)&v33[2 * v10] = v4;
  v32[v10] = 0x20000000;
  *((_BYTE *)v21 + v10) = 10;
  v11 = (unsigned int)(v9 + 2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)v11 >= 0x14 )
      goto LABEL_44;
    v9 = (unsigned __int64)gRestrictedSpoolerServiceSid;
    *(_QWORD *)&v33[2 * (unsigned int)v11] = gRestrictedSpoolerServiceSid;
    *((_BYTE *)v22 + (unsigned int)v11) = 0;
    v32[(unsigned int)v11] = 983043;
    *((_BYTE *)v21 + (unsigned int)v11) = 0;
    v12 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v12 >= 0x14 )
      goto LABEL_44;
    *((_BYTE *)v22 + v12) = 0;
    *(_QWORD *)&v33[2 * v12] = v9;
    v32[v12] = 0x10000000;
    *((_BYTE *)v21 + v12) = 11;
    v11 = (unsigned int)(v12 + 1);
  }
  if ( !RtlGetNtProductType(&ProductType) )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateServerSecurityDescriptor",
      L"Couldn't get NT Product Type.  Error %d",
      LastError);
    goto LABEL_33;
  }
  if ( ProductType != NtProductLanManNt )
    goto LABEL_29;
  if ( !AllocateAndInitializeSid(&v35, 2u, 0x20u, 0x226u, 0, 0, 0, 0, 0, 0, &v29) )
  {
    v14 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateServerSecurityDescriptor",
      L"Couldn't allocate and init Print Operators SID.  Error %d",
      v14);
    goto LABEL_33;
  }
  if ( (unsigned int)v11 >= 0x14 )
    goto LABEL_44;
  v9 = (unsigned __int64)v29;
  *(_QWORD *)&v33[2 * v11] = v29;
  *((_BYTE *)v22 + v11) = 0;
  v32[v11] = 983043;
  *((_BYTE *)v21 + v11) = 0;
  v15 = (unsigned int)(v11 + 1);
  if ( (unsigned int)v15 >= 0x14 )
    goto LABEL_44;
  *(_QWORD *)&v33[2 * v15] = v9;
  *((_BYTE *)v22 + v15) = 0;
  v32[v15] = 0x10000000;
  *((_BYTE *)v21 + v15) = 11;
  if ( !AllocateAndInitializeSid(&v35, 2u, 0x20u, 0x225u, 0, 0, 0, 0, 0, 0, &v30) )
  {
    v16 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateServerSecurityDescriptor",
      L"Couldn't allocate and init System Operator SID.  Error %d",
      v16);
    goto LABEL_33;
  }
  v9 = (unsigned int)(v15 + 1);
  if ( (unsigned int)v9 >= 0x14
    || (v4 = v30,
        v11 = (unsigned int)(v15 + 2),
        *((_BYTE *)v22 + v9) = 0,
        *(_QWORD *)&v33[2 * v9] = v4,
        v32[v9] = 983043,
        *((_BYTE *)v21 + v9) = 0,
        (unsigned int)v11 >= 0x14) )
  {
LABEL_44:
    _report_rangecheckfailure(v9, v4);
  }
  *((_BYTE *)v22 + v11) = 0;
  *(_QWORD *)&v33[2 * v11] = v4;
  v32[v11] = 0x10000000;
  *((_BYTE *)v21 + v11) = 11;
  LODWORD(v11) = v9 + 2;
LABEL_29:
  if ( (unsigned int)v11 <= 0x14 )
  {
    if ( !(unsigned int)BuildPrintObjectProtection(
                          (int)v22,
                          v11,
                          (int)v33,
                          (int)v32,
                          (__int64)v21,
                          pOwner,
                          pOwner,
                          nSubAuthority5,
                          (__int64)&v31) )
    {
      v18 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError("CreateServerSecurityDescriptor", L"Failed.  Error %d", v18);
    }
  }
  else
  {
    v17 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateServerSecurityDescriptor",
      L"ACE count exceeded while creating SIDs.  Error %d",
      v17);
  }
LABEL_33:
  if ( v27 )
    FreeSid(v27);
  if ( pOwner )
    FreeSid(pOwner);
  if ( pSid )
    FreeSid(pSid);
  if ( v29 )
    FreeSid(v29);
  if ( v30 )
    FreeSid(v30);
  return v31;
}

```

## disassembly

```asm
0x180098628  push    rbp
0x18009862a  push    rbx
0x18009862b  push    rdi
0x18009862c  push    r14
0x18009862e  push    r15
0x180098630  lea     rbp, [rsp-190h]
0x180098638  sub     rsp, 290h
0x18009863f  mov     rax, cs:__security_cookie
0x180098646  xor     rax, rsp
0x180098649  mov     [rbp+1B0h+var_30], rax
0x180098650  mov     eax, 44h ; 'D'
0x180098655  lea     rcx, [rbp+1B0h+var_190]; void *
0x180098659  xor     edi, edi
0x18009865b  mov     [rbp+1B0h+cbSid], eax
0x18009865e  xor     edx, edx; Val
0x180098660  mov     [rbp+1B0h+var_20C], eax
0x180098663  mov     [rbp+1B0h+ProductType], edi
0x180098666  lea     r8d, [rax+5Ch]; Size
0x18009866a  call    memset_0
0x18009866f  lea     rax, [rbp+1B0h+var_200]
0x180098673  mov     dword ptr [rbp+1B0h+var_F0.Value], edi
0x180098679  mov     [rsp+2B0h+pSid], rax; pSid
0x18009867e  lea     rcx, [rbp+1B0h+pIdentifierAuthority]; pIdentifierAuthority
0x180098685  mov     [rsp+2B0h+nSubAuthority7], edi; nSubAuthority7
0x180098689  xor     r9d, r9d; nSubAuthority1
0x18009868c  mov     [rsp+2B0h+nSubAuthority6], edi; nSubAuthority6
0x180098690  xor     r8d, r8d; nSubAuthority0
0x180098693  mov     [rsp+2B0h+nSubAuthority5], edi; nSubAuthority5
0x180098697  mov     dl, 1; nSubAuthorityCount
0x180098699  mov     [rsp+2B0h+nSubAuthority4], edi; nSubAuthority4
0x18009869d  mov     [rsp+2B0h+nSubAuthority3], edi; nSubAuthority3
0x1800986a1  mov     [rsp+2B0h+nSubAuthority2], edi; nSubAuthority2
0x1800986a5  mov     word ptr [rbp+1B0h+var_F0.Value+4], 500h
0x1800986ae  mov     dword ptr [rbp+1B0h+var_E0.Value], edi
0x1800986b4  mov     word ptr [rbp+1B0h+var_E0.Value+4], 100h
0x1800986bd  mov     dword ptr [rbp+1B0h+pIdentifierAuthority.Value], edi
0x1800986c3  mov     word ptr [rbp+1B0h+pIdentifierAuthority.Value+4], 300h
0x1800986cc  mov     [rbp+1B0h+var_208], rdi
0x1800986d0  mov     [rbp+1B0h+pOwner], rdi
0x1800986d4  mov     [rbp+1B0h+var_1F8], rdi
0x1800986d8  mov     [rbp+1B0h+var_1F0], rdi
0x1800986dc  mov     [rbp+1B0h+var_200], rdi
0x1800986e0  mov     [rbp+1B0h+var_1E8], rdi
0x1800986e4  call    cs:__imp_AllocateAndInitializeSid
0x1800986ea  test    eax, eax
0x1800986ec  jz      loc_180098B50
0x1800986f2  lea     r9, [rbp+1B0h+cbSid]; cbSid
0x1800986f6  xor     edx, edx; DomainSid
0x1800986f8  lea     r8, [rbp+1B0h+var_80]; pSid
0x1800986ff  lea     ecx, [rdi+0Bh]; WellKnownSidType
0x180098702  call    cs:__imp_CreateWellKnownSid
0x180098708  test    eax, eax
0x18009870a  jz      loc_180098B50
0x180098710  lea     r9, [rbp+1B0h+var_20C]; cbSid
0x180098714  xor     edx, edx; DomainSid
0x180098716  lea     r8, [rbp+1B0h+var_D0]; pSid
0x18009871d  lea     ecx, [rdi+1Ch]; WellKnownSidType
0x180098720  call    cs:__imp_CreateWellKnownSid
0x180098726  test    eax, eax
0x180098728  jz      loc_180098B50
0x18009872e  lea     rax, [rbp+1B0h+var_208]
0x180098732  xor     r9d, r9d; nSubAuthority1
0x180098735  mov     [rsp+2B0h+pSid], rax; pSid
0x18009873a  lea     rcx, [rbp+1B0h+var_E0]; pIdentifierAuthority
0x180098741  mov     [rsp+2B0h+nSubAuthority7], edi; nSubAuthority7
0x180098745  xor     r8d, r8d; nSubAuthority0
0x180098748  mov     [rsp+2B0h+nSubAuthority6], edi; nSubAuthority6
0x18009874c  mov     dl, 1; nSubAuthorityCount
0x18009874e  mov     [rsp+2B0h+nSubAuthority5], edi; nSubAuthority5
0x180098752  mov     [rsp+2B0h+nSubAuthority4], edi; nSubAuthority4
0x180098756  mov     [rsp+2B0h+nSubAuthority3], edi; nSubAuthority3
0x18009875a  mov     [rsp+2B0h+nSubAuthority2], edi; nSubAuthority2
0x18009875e  call    cs:__imp_AllocateAndInitializeSid
0x180098764  test    eax, eax
0x180098766  jz      loc_180098B50
0x18009876c  lea     rax, [rbp+1B0h+pOwner]
0x180098770  mov     r9d, 220h; nSubAuthority1
0x180098776  mov     [rsp+2B0h+pSid], rax; pSid
0x18009877b  lea     r8d, [rdi+20h]; nSubAuthority0
0x18009877f  mov     [rsp+2B0h+nSubAuthority7], edi; nSubAuthority7
0x180098783  lea     rcx, [rbp+1B0h+var_F0]; pIdentifierAuthority
0x18009878a  mov     [rsp+2B0h+nSubAuthority6], edi; nSubAuthority6
0x18009878e  mov     dl, 2; nSubAuthorityCount
0x180098790  mov     [rsp+2B0h+nSubAuthority5], edi; nSubAuthority5
0x180098794  mov     [rsp+2B0h+nSubAuthority4], edi; nSubAuthority4
0x180098798  mov     [rsp+2B0h+nSubAuthority3], edi; nSubAuthority3
0x18009879c  mov     [rsp+2B0h+nSubAuthority2], edi; nSubAuthority2
0x1800987a0  call    cs:__imp_AllocateAndInitializeSid
0x1800987a6  test    eax, eax
0x1800987a8  jz      loc_180098B50
0x1800987ae  mov     edx, edi
0x1800987b0  call    ?ServerSku@@YAHXZ; ServerSku(void)
0x1800987b5  mov     r14d, 0F0003h
0x1800987bb  test    eax, eax
0x1800987bd  jnz     short loc_1800987EF
0x1800987bf  lea     rax, [rbp+1B0h+var_D0]
0x1800987c6  mov     word ptr [rsp+2B0h+var_238], 1
0x1800987cd  mov     qword ptr [rbp+1B0h+var_190], rax
0x1800987d1  lea     edx, [rdi+2]
0x1800987d4  lea     rax, [rbp+1B0h+var_80]
0x1800987db  mov     [rbp+1B0h+var_1E0], 1
0x1800987e2  mov     [rbp+1B0h+var_188], rax
0x1800987e6  mov     word ptr [rsp+2B0h+var_250], di
0x1800987eb  mov     [rbp+1B0h+var_1DC], r14d
0x1800987ef  mov     r8, cs:?gAppContainerAllAppsSid@@3PEAXEA; void * gAppContainerAllAppsSid
0x1800987f6  mov     r15d, 10000000h
0x1800987fc  mov     rax, [rbp+1B0h+var_200]
0x180098800  mov     r9d, 20002h
0x180098806  mov     ecx, edx
0x180098808  mov     r10d, 20000000h
0x18009880e  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x180098813  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rax
0x180098818  mov     [rbp+rcx*4+1B0h+var_1E0], r15d
0x18009881d  mov     byte ptr [rsp+rcx+2B0h+var_250], 9
0x180098822  lea     ecx, [rdx+1]
0x180098825  mov     rdx, [rbp+1B0h+var_208]
0x180098829  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x18009882e  mov     qword ptr [rbp+rcx*8+1B0h+var_190], r8
0x180098833  mov     [rbp+rcx*4+1B0h+var_1E0], r15d
0x180098838  mov     byte ptr [rsp+rcx+2B0h+var_250], 9
0x18009883d  inc     ecx
0x18009883f  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x180098844  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rdx
0x180098849  mov     [rbp+rcx*4+1B0h+var_1E0], r9d
0x18009884e  mov     byte ptr [rsp+rcx+2B0h+var_250], dil
0x180098853  inc     ecx
0x180098855  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x18009885a  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rdx
0x18009885f  mov     [rbp+rcx*4+1B0h+var_1E0], r10d
0x180098864  mov     byte ptr [rsp+rcx+2B0h+var_250], 0Ah
0x180098869  inc     ecx
0x18009886b  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x180098870  mov     qword ptr [rbp+rcx*8+1B0h+var_190], r8
0x180098875  mov     [rbp+rcx*4+1B0h+var_1E0], r9d
0x18009887a  mov     byte ptr [rsp+rcx+2B0h+var_250], dil
0x18009887f  inc     ecx
0x180098881  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x180098886  mov     qword ptr [rbp+rcx*8+1B0h+var_190], r8
0x18009888b  mov     [rbp+rcx*4+1B0h+var_1E0], r10d
0x180098890  mov     byte ptr [rsp+rcx+2B0h+var_250], 0Ah
0x180098895  inc     ecx
0x180098897  cmp     ecx, 14h
0x18009889a  jnb     loc_180098BBD
0x1800988a0  mov     rdx, [rbp+1B0h+pOwner]
0x1800988a4  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rdx
0x1800988a9  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x1800988ae  mov     [rbp+rcx*4+1B0h+var_1E0], r14d
0x1800988b3  mov     byte ptr [rsp+rcx+2B0h+var_250], dil
0x1800988b8  inc     ecx
0x1800988ba  cmp     ecx, 14h
0x1800988bd  jnb     loc_180098BBD
0x1800988c3  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x1800988c8  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rdx
0x1800988cd  mov     [rbp+rcx*4+1B0h+var_1E0], r15d
0x1800988d2  mov     byte ptr [rsp+rcx+2B0h+var_250], 0Bh
0x1800988d7  inc     ecx
0x1800988d9  cmp     ecx, 14h
0x1800988dc  jnb     loc_180098BBD
0x1800988e2  mov     rdx, cs:?gLPACCapabilitySid@@3PEAXEA; void * gLPACCapabilitySid
0x1800988e9  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rdx
0x1800988ee  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x1800988f3  mov     [rbp+rcx*4+1B0h+var_1E0], r15d
0x1800988f8  mov     byte ptr [rsp+rcx+2B0h+var_250], 9
0x1800988fd  inc     ecx
0x1800988ff  cmp     ecx, 14h
0x180098902  jnb     loc_180098BBD
0x180098908  lea     ebx, [rcx+1]
0x18009890b  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x180098910  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rdx
0x180098915  mov     [rbp+rcx*4+1B0h+var_1E0], r9d
0x18009891a  mov     byte ptr [rsp+rcx+2B0h+var_250], dil
0x18009891f  cmp     ebx, 14h
0x180098922  jnb     loc_180098BBD
0x180098928  mov     byte ptr [rsp+rbx+2B0h+var_238], dil
0x18009892d  mov     qword ptr [rbp+rbx*8+1B0h+var_190], rdx
0x180098932  mov     [rbp+rbx*4+1B0h+var_1E0], r10d
0x180098937  mov     byte ptr [rsp+rbx+2B0h+var_250], 0Ah
0x18009893c  inc     ebx
0x18009893e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180098945  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x18009894a  test    al, al
0x18009894c  jz      short loc_180098993
0x18009894e  cmp     ebx, 14h
0x180098951  jnb     loc_180098BBD
0x180098957  mov     rcx, cs:?gRestrictedSpoolerServiceSid@@3PEAXEA; void * gRestrictedSpoolerServiceSid
0x18009895e  mov     qword ptr [rbp+rbx*8+1B0h+var_190], rcx
0x180098963  mov     byte ptr [rsp+rbx+2B0h+var_238], dil
0x180098968  mov     [rbp+rbx*4+1B0h+var_1E0], r14d
0x18009896d  mov     byte ptr [rsp+rbx+2B0h+var_250], dil
0x180098972  inc     ebx
0x180098974  cmp     ebx, 14h
0x180098977  jnb     loc_180098BBD
0x18009897d  mov     byte ptr [rsp+rbx+2B0h+var_238], dil
0x180098982  mov     qword ptr [rbp+rbx*8+1B0h+var_190], rcx
0x180098987  mov     [rbp+rbx*4+1B0h+var_1E0], r15d
0x18009898c  mov     byte ptr [rsp+rbx+2B0h+var_250], 0Bh
0x180098991  inc     ebx
0x180098993  lea     rcx, [rbp+1B0h+ProductType]; ProductType
0x180098997  call    cs:__imp_RtlGetNtProductType
0x18009899d  test    al, al
0x18009899f  jnz     short loc_1800989B3
0x1800989a1  call    cs:__imp_GetLastError
0x1800989a7  lea     rdx, aCouldnTGetNtPr; "Couldn't get NT Product Type.  Error %d"
0x1800989ae  jmp     loc_180098B41
0x1800989b3  cmp     [rbp+1B0h+ProductType], 2
0x1800989b7  jnz     loc_180098AE7
0x1800989bd  lea     rax, [rbp+1B0h+var_1F8]
0x1800989c1  mov     r9d, 226h; nSubAuthority1
0x1800989c7  mov     [rsp+2B0h+pSid], rax; pSid
0x1800989cc  lea     rcx, [rbp+1B0h+var_F0]; pIdentifierAuthority
0x1800989d3  mov     [rsp+2B0h+nSubAuthority7], edi; nSubAuthority7
0x1800989d7  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800989dd  mov     [rsp+2B0h+nSubAuthority6], edi; nSubAuthority6
0x1800989e1  mov     dl, 2; nSubAuthorityCount
0x1800989e3  mov     [rsp+2B0h+nSubAuthority5], edi; nSubAuthority5
0x1800989e7  mov     [rsp+2B0h+nSubAuthority4], edi; nSubAuthority4
0x1800989eb  mov     [rsp+2B0h+nSubAuthority3], edi; nSubAuthority3
0x1800989ef  mov     [rsp+2B0h+nSubAuthority2], edi; nSubAuthority2
0x1800989f3  call    cs:__imp_AllocateAndInitializeSid
0x1800989f9  test    eax, eax
0x1800989fb  jnz     short loc_180098A0F
0x1800989fd  call    cs:__imp_GetLastError
0x180098a03  lea     rdx, aCouldnTAllocat_1; "Couldn't allocate and init Print Operat"...
0x180098a0a  jmp     loc_180098B41
0x180098a0f  cmp     ebx, 14h
0x180098a12  jnb     loc_180098BBD
0x180098a18  mov     rcx, [rbp+1B0h+var_1F8]
0x180098a1c  mov     qword ptr [rbp+rbx*8+1B0h+var_190], rcx
0x180098a21  mov     byte ptr [rsp+rbx+2B0h+var_238], dil
0x180098a26  mov     [rbp+rbx*4+1B0h+var_1E0], r14d
0x180098a2b  mov     byte ptr [rsp+rbx+2B0h+var_250], dil
0x180098a30  inc     ebx
0x180098a32  cmp     ebx, 14h
0x180098a35  jnb     loc_180098BBD
0x180098a3b  lea     rax, [rbp+1B0h+var_1F0]
0x180098a3f  mov     qword ptr [rbp+rbx*8+1B0h+var_190], rcx
0x180098a44  mov     [rsp+2B0h+pSid], rax; pSid
0x180098a49  lea     rcx, [rbp+1B0h+var_F0]; pIdentifierAuthority
0x180098a50  mov     [rsp+2B0h+nSubAuthority7], edi; nSubAuthority7
0x180098a54  mov     r9d, 225h; nSubAuthority1
0x180098a5a  mov     [rsp+2B0h+nSubAuthority6], edi; nSubAuthority6
0x180098a5e  mov     r8d, 20h ; ' '; nSubAuthority0
0x180098a64  mov     [rsp+2B0h+nSubAuthority5], edi; dwBufferLength
0x180098a68  mov     dl, 2; nSubAuthorityCount
0x180098a6a  mov     [rsp+2B0h+nSubAuthority4], edi; nSubAuthority4
0x180098a6e  mov     [rsp+2B0h+nSubAuthority3], edi; nSubAuthority3
0x180098a72  mov     [rsp+2B0h+nSubAuthority2], edi; nSubAuthority2
0x180098a76  mov     byte ptr [rsp+rbx+2B0h+var_238], dil
0x180098a7b  mov     [rbp+rbx*4+1B0h+var_1E0], r15d
0x180098a80  mov     byte ptr [rsp+rbx+2B0h+var_250], 0Bh
0x180098a85  call    cs:__imp_AllocateAndInitializeSid
0x180098a8b  test    eax, eax
0x180098a8d  jnz     short loc_180098AA1
0x180098a8f  call    cs:__imp_GetLastError
0x180098a95  lea     rdx, aCouldnTAllocat_2; "Couldn't allocate and init System Opera"...
0x180098a9c  jmp     loc_180098B41
0x180098aa1  lea     ecx, [rbx+1]
0x180098aa4  cmp     ecx, 14h
0x180098aa7  jnb     loc_180098BBD
0x180098aad  mov     rdx, [rbp+1B0h+var_1F0]
0x180098ab1  lea     ebx, [rcx+1]
0x180098ab4  mov     byte ptr [rsp+rcx+2B0h+var_238], dil
0x180098ab9  mov     qword ptr [rbp+rcx*8+1B0h+var_190], rdx
0x180098abe  mov     [rbp+rcx*4+1B0h+var_1E0], r14d
0x180098ac3  mov     byte ptr [rsp+rcx+2B0h+var_250], dil
0x180098ac8  cmp     ebx, 14h
0x180098acb  jnb     loc_180098BBD
0x180098ad1  mov     byte ptr [rsp+rbx+2B0h+var_238], dil
0x180098ad6  mov     qword ptr [rbp+rbx*8+1B0h+var_190], rdx
0x180098adb  mov     [rbp+rbx*4+1B0h+var_1E0], r15d
0x180098ae0  mov     byte ptr [rsp+rbx+2B0h+var_250], 0Bh
0x180098ae5  inc     ebx
0x180098ae7  cmp     ebx, 14h
0x180098aea  jbe     short loc_180098AFB
0x180098aec  call    cs:__imp_GetLastError
0x180098af2  lea     rdx, aAceCountExceed; "ACE count exceeded while creating SIDs."...
0x180098af9  jmp     short loc_180098B41
0x180098afb  lea     rax, [rbp+1B0h+var_1E8]
0x180098aff  mov     edx, ebx; int
0x180098b01  mov     qword ptr [rsp+2B0h+nSubAuthority6], rax; __int64
0x180098b06  lea     r9, [rbp+1B0h+var_1E0]; int
0x180098b0a  mov     rax, [rbp+1B0h+pOwner]
0x180098b0e  lea     r8, [rbp+1B0h+var_190]; int
0x180098b12  mov     qword ptr [rsp+2B0h+nSubAuthority4], rax; pGroup
0x180098b17  lea     rcx, [rsp+2B0h+var_238]; int
0x180098b1c  mov     qword ptr [rsp+2B0h+nSubAuthority3], rax; pOwner
0x180098b21  lea     rax, [rsp+2B0h+var_250]
0x180098b26  mov     qword ptr [rsp+2B0h+nSubAuthority2], rax; __int64
0x180098b2b  call    BuildPrintObjectProtection
0x180098b30  test    eax, eax
0x180098b32  jnz     short loc_180098B50
0x180098b34  call    cs:__imp_GetLastError
0x180098b3a  lea     rdx, aFailedErrorD; "Failed.  Error %d"
0x180098b41  mov     r8d, eax
0x180098b44  lea     rcx, aCreateserverse; "CreateServerSecurityDescriptor"
0x180098b4b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180098b50  mov     rcx, [rbp+1B0h+var_208]; pSid
0x180098b54  test    rcx, rcx
0x180098b57  jz      short loc_180098B5F
0x180098b59  call    cs:__imp_FreeSid
  ... truncated ...
```
