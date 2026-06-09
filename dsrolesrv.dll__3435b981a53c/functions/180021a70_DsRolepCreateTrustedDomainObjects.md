# DsRolepCreateTrustedDomainObjects

- ea: `0x180021a70`
- end: `0x180021e92`
- name: `DsRolepCreateTrustedDomainObjects`
- size: `1058`
- prototype: `ULONG __fastcall(HANDLE hToken, PCWSTR SourceString, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011240`

## callees

- `0x180016374`
- `0x180016538`
- `0x18001f618`
- `0x1800203d0`
- `0x1800204c4`
- `0x180020530`
- `0x180020dbc`
- `0x18002139c`
- `0x1800217f0`
- `0x180021a70`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `LSASRV!LsapDsInitializeDsStateInfo` at `0x180021b10`
- `LSASRV!LsapDsInitializeDsStateInfo` at `0x180021b10`
- `ntdll!NtQuerySystemTime` at `0x180021b78`
- `ntdll!NtQuerySystemTime` at `0x180021b78`
- `ntdll!RtlNtStatusToDosError` at `0x180021cbd`
- `ntdll!RtlNtStatusToDosError` at `0x180021ccd`
- `ntdll!RtlNtStatusToDosError` at `0x180021cf7`
- `ntdll!RtlNtStatusToDosError` at `0x180021d03`
- `ntdll!RtlNtStatusToDosError` at `0x180021e69`
- `ntdll!RtlNtStatusToDosError` at `0x180021cbd`
- `ntdll!RtlNtStatusToDosError` at `0x180021ccd`
- `ntdll!RtlNtStatusToDosError` at `0x180021cf7`
- `ntdll!RtlNtStatusToDosError` at `0x180021d03`
- `ntdll!RtlNtStatusToDosError` at `0x180021e69`
- `ntdll!RtlInitUnicodeString` at `0x180021bd0`
- `ntdll!RtlInitUnicodeString` at `0x180021bd0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180021e14`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180021e14`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180021c4e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x180021c4e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180021e04`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180021e04`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180021c2f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180021c2f`

## string_xrefs

- `0x180021dd2`: `OpenPolicy on %ws failed with 0x%lx\n`
- `0x180021d83`: `DsRolepCreateChildTrustObject failed: 0x%lx\n`
- `0x180021dac`: `LsaDelete of ParentTrustedDomain failed: 0x%lx\n`

## pseudocode

```c
ULONG __fastcall DsRolepCreateTrustedDomainObjects(HANDLE hToken, PCWSTR SourceString, __int64 a3, __int64 a4, char a5)
{
  __int64 v6; // rdi
  int v9; // eax
  int v10; // ebx
  __int64 v11; // r13
  __int64 v12; // rcx
  int RandomPassword; // eax
  int v14; // eax
  NTSTATUS v15; // eax
  ULONG v16; // eax
  ULONG v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  struct _TRUSTED_DOMAIN_AUTH_INFORMATION *v21; // rax
  __int64 v22; // rcx
  union _LARGE_INTEGER *v23; // rax
  _BYTE *v24; // rax
  PVOID Buffer; // [rsp+40h] [rbp-C0h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-B8h] BYREF
  LSA_HANDLE v28; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER SystemTime[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  struct _TRUSTED_DOMAIN_AUTH_INFORMATION v33; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-50h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v37[528]; // [rsp+100h] [rbp+0h] BYREF

  v31 = a3;
  v34 = a4;
  PolicyHandle = 0;
  v6 = 0;
  v28 = 0;
  Buffer = 0;
  DestinationString = 0;
  v32 = 0;
  memset(&ObjectAttributes, 0, 44);
  v30 = 0;
  *(_OWORD *)&SystemTime[0].LowPart = 0;
  memset(&v33, 0, 44);
  DsRolepSetCurrentOperationStatus(28681, SourceString, 0);
  v9 = LsapDsInitializeDsStateInfo(4);
  v10 = v9;
  if ( v9 < 0 )
  {
    DsRolepLogPrintRoutine(4, "Failed to convince Lsa to reinitialize: 0x%lx\n", v9);
    return RtlNtStatusToDosError(v10);
  }
  v11 = 514;
  v30 = 0;
  memset(&v33, 0, sizeof(v33));
  *(_OWORD *)&SystemTime[0].LowPart = 0;
  memset_0(v37, 0, 0x202u);
  RandomPassword = DsRolepGenerateRandomPassword(v12, v37);
  if ( RandomPassword )
  {
    DsRolepLogPrintRoutine(1, "Failed to generate a trust password: %lu\n", RandomPassword);
    v10 = -1073741823;
  }
  else
  {
    v10 = NtQuerySystemTime(SystemTime);
    if ( v10 >= 0 )
    {
      SystemTime[1].QuadPart = 0x10000000002LL;
      v30 = v37;
      v33.IncomingAuthenticationInformation = (PLSA_AUTH_INFORMATION)SystemTime;
      v33.IncomingAuthInfos = 1;
      v33.OutgoingAuthenticationInformation = (PLSA_AUTH_INFORMATION)SystemTime;
      v33.IncomingPreviousAuthenticationInformation = 0;
      v33.OutgoingAuthInfos = 1;
      v33.OutgoingPreviousAuthenticationInformation = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v14 = ImpLsaOpenPolicy(hToken, &DestinationString, &ObjectAttributes, 9, &v28);
      v10 = v14;
      if ( v14 < 0 )
      {
        DsRolepLogPrintRoutine(4, "OpenPolicy on %ws failed with 0x%lx\n", SourceString, (unsigned int)v14);
      }
      else
      {
        memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
        v10 = LsaOpenPolicy(0, &ObjectAttributes, 9u, &PolicyHandle);
        if ( v10 >= 0 )
        {
          v10 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
          if ( v10 >= 0 )
          {
            DsRolepSetCurrentOperationStatus(28697, *(_QWORD *)(a4 + 24), 0);
            if ( (a5 & 1) == 0 || a5 < 0 )
            {
              v15 = DsRolepCreateParentTrustObject(hToken, v28, (__int64)Buffer, a5, (__int64)&v33, &v32);
              v10 = v15;
              if ( v15 == -1073741771 )
              {
                if ( RtlNtStatusToDosError(-1073741771) )
                {
                  v16 = RtlNtStatusToDosError(-1073741771);
                  DsRolepSetFailureMessage(v16, 3221254683LL, SourceString, v31, 0);
                }
                goto LABEL_25;
              }
              if ( RtlNtStatusToDosError(v15) )
              {
                v17 = RtlNtStatusToDosError(v10);
                DsRolepSetFailureMessage(v17, 3221254684LL, v31, SourceString, 0);
              }
              if ( v10 < 0 )
                goto LABEL_25;
              v6 = v32;
            }
            DsRolepSetCurrentOperationStatus(28688, *((_QWORD *)Buffer + 3), 0);
            v18 = DsRolepCreateChildTrustObject(hToken, v28, PolicyHandle, v34, (PCUNICODE_STRING)Buffer, &v33, a5);
            v10 = v18;
            if ( v18 >= 0
              || (DsRolepLogPrintRoutine(4, "DsRolepCreateChildTrustObject failed: 0x%lx\n", v18), (a5 & 1) != 0) )
            {
              if ( v6 )
                ImpLsaClose(hToken, v6);
            }
            else
            {
              v19 = ImpLsaDelete(hToken, v6);
              if ( v19 < 0 )
                DsRolepLogPrintRoutine(4, "LsaDelete of ParentTrustedDomain failed: 0x%lx\n", v19);
            }
          }
        }
      }
    }
  }
LABEL_25:
  LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v28 )
    ImpLsaClose(hToken, v28);
  v20 = 48;
  v21 = &v33;
  do
  {
    LOBYTE(v21->IncomingAuthInfos) = 0;
    v21 = (struct _TRUSTED_DOMAIN_AUTH_INFORMATION *)((char *)v21 + 1);
    --v20;
  }
  while ( v20 );
  v22 = 24;
  v23 = SystemTime;
  do
  {
    LOBYTE(v23->LowPart) = 0;
    v23 = (union _LARGE_INTEGER *)((char *)v23 + 1);
    --v22;
  }
  while ( v22 );
  v24 = v37;
  do
  {
    *v24++ = 0;
    --v11;
  }
  while ( v11 );
  return RtlNtStatusToDosError(v10);
}

```

## disassembly

```asm
0x180021a70  push    rbp
0x180021a72  push    rbx
0x180021a73  push    rsi
0x180021a74  push    rdi
0x180021a75  push    r12
0x180021a77  push    r13
0x180021a79  push    r14
0x180021a7b  push    r15
0x180021a7d  lea     rbp, [rsp-228h]
0x180021a85  sub     rsp, 328h
0x180021a8c  mov     rax, cs:__security_cookie
0x180021a93  xor     rax, rsp
0x180021a96  mov     [rbp+260h+var_50], rax
0x180021a9d  xorps   xmm0, xmm0
0x180021aa0  mov     [rsp+360h+var_2F0], r8
0x180021aa5  mov     rsi, rcx
0x180021aa8  mov     [rbp+260h+var_2B0], r9
0x180021aac  xor     eax, eax
0x180021aae  mov     [rsp+360h+PolicyHandle], 0
0x180021ab7  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x180021abb  xor     edi, edi
0x180021abd  xor     r8d, r8d
0x180021ac0  movups  [rbp+260h+var_2D0], xmm0
0x180021ac4  mov     ecx, 7009h
0x180021ac9  mov     [rsp+360h+var_310], 0
0x180021ad2  movups  xmmword ptr [rbp+260h+ObjectAttributes+1Ch], xmm0
0x180021ad6  mov     r14, r9
0x180021ad9  mov     r12, rdx
0x180021adc  movups  [rbp+260h+var_2D0+0Ch], xmm0
0x180021ae0  mov     [rsp+360h+Buffer], 0
0x180021ae9  movups  xmmword ptr [rbp+260h+DestinationString.Length], xmm0
0x180021aed  mov     [rsp+360h+var_2E8], rdi
0x180021af2  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x180021af6  mov     [rsp+360h+var_2F8], rax
0x180021afb  movups  xmmword ptr [rsp+360h+SystemTime], xmm0
0x180021b00  movups  xmmword ptr [rbp+260h+var_2E0], xmm0
0x180021b04  call    DsRolepSetCurrentOperationStatus
0x180021b09  lea     r15d, [rdi+4]
0x180021b0d  mov     ecx, r15d
0x180021b10  call    cs:__imp_LsapDsInitializeDsStateInfo
0x180021b16  mov     ebx, eax
0x180021b18  test    eax, eax
0x180021b1a  jns     short loc_180021B33
0x180021b1c  mov     r8d, eax
0x180021b1f  lea     rdx, aFailedToConvin; "Failed to convince Lsa to reinitialize:"...
0x180021b26  mov     ecx, r15d
0x180021b29  call    DsRolepLogPrintRoutine
0x180021b2e  jmp     loc_180021E67
0x180021b33  xorps   xmm0, xmm0
0x180021b36  lea     rcx, [rbp+260h+var_260]; void *
0x180021b3a  xor     eax, eax
0x180021b3c  mov     r13d, 202h
0x180021b42  mov     r8d, r13d; Size
0x180021b45  mov     [rsp+360h+var_2F8], rax
0x180021b4a  xor     edx, edx; Val
0x180021b4c  movups  xmmword ptr [rbp+260h+var_2E0], xmm0
0x180021b50  movups  [rbp+260h+var_2D0], xmm0
0x180021b54  movups  [rbp+260h+var_2C0], xmm0
0x180021b58  movups  xmmword ptr [rsp+360h+SystemTime], xmm0
0x180021b5d  call    memset_0
0x180021b62  lea     rdx, [rbp+260h+var_260]
0x180021b66  call    DsRolepGenerateRandomPassword
0x180021b6b  test    eax, eax
0x180021b6d  jnz     loc_180021DE6
0x180021b73  lea     rcx, [rsp+360h+SystemTime]; SystemTime
0x180021b78  call    cs:__imp_NtQuerySystemTime
0x180021b7e  mov     ebx, eax
0x180021b80  test    eax, eax
0x180021b82  js      loc_180021DFF
0x180021b88  lea     rax, [rbp+260h+var_260]
0x180021b8c  mov     dword ptr [rsp+360h+SystemTime+8], 2
0x180021b94  mov     [rsp+360h+var_2F8], rax
0x180021b99  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x180021b9d  lea     rax, [rsp+360h+SystemTime]
0x180021ba2  mov     dword ptr [rsp+360h+SystemTime+0Ch], 100h
0x180021baa  mov     [rbp+260h+var_2E0+8], rax
0x180021bae  mov     rdx, r12; SourceString
0x180021bb1  lea     rax, [rsp+360h+SystemTime]
0x180021bb6  mov     dword ptr [rbp+260h+var_2E0], 1
0x180021bbd  mov     qword ptr [rbp+260h+var_2C0], rax
0x180021bc1  mov     qword ptr [rbp+260h+var_2D0], rdi
0x180021bc5  mov     dword ptr [rbp+260h+var_2D0+8], 1
0x180021bcc  mov     qword ptr [rbp+260h+var_2C0+8], rdi
0x180021bd0  call    cs:__imp_RtlInitUnicodeString
0x180021bd6  xorps   xmm0, xmm0
0x180021bd9  lea     rax, [rsp+360h+var_310]
0x180021bde  mov     r9d, 9
0x180021be4  mov     [rsp+360h+var_340], rax
0x180021be9  lea     r8, [rbp+260h+ObjectAttributes]
0x180021bed  mov     rcx, rsi
0x180021bf0  lea     rdx, [rbp+260h+DestinationString]
0x180021bf4  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x180021bf8  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x180021bfc  movups  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x180021c00  call    ImpLsaOpenPolicy
0x180021c05  mov     ebx, eax
0x180021c07  test    eax, eax
0x180021c09  js      loc_180021DCF
0x180021c0f  xorps   xmm0, xmm0
0x180021c12  lea     r9, [rsp+360h+PolicyHandle]; PolicyHandle
0x180021c17  mov     r8d, 9; DesiredAccess
0x180021c1d  lea     rdx, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x180021c21  xor     ecx, ecx; SystemName
0x180021c23  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x180021c27  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x180021c2b  movups  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x180021c2f  call    cs:__imp_LsaOpenPolicy
0x180021c35  mov     ebx, eax
0x180021c37  test    eax, eax
0x180021c39  js      loc_180021DFF
0x180021c3f  mov     rcx, [rsp+360h+PolicyHandle]; PolicyHandle
0x180021c44  lea     r8, [rsp+360h+Buffer]; Buffer
0x180021c49  mov     edx, 0Ch; InformationClass
0x180021c4e  call    cs:__imp_LsaQueryInformationPolicy
0x180021c54  mov     ebx, eax
0x180021c56  test    eax, eax
0x180021c58  js      loc_180021DFF
0x180021c5e  mov     rdx, [r14+18h]
0x180021c62  xor     r8d, r8d
0x180021c65  mov     ecx, 7019h
0x180021c6a  call    DsRolepSetCurrentOperationStatus
0x180021c6f  mov     r14d, [rbp+260h+arg_20]
0x180021c76  mov     r15d, r14d
0x180021c79  and     r15d, 1
0x180021c7d  jz      short loc_180021C88
0x180021c7f  test    r14b, r14b
0x180021c82  jns     loc_180021D33
0x180021c88  mov     r8, [rsp+360h+Buffer]
0x180021c8d  lea     rax, [rsp+360h+var_2E8]
0x180021c92  mov     rdx, [rsp+360h+var_310]; PolicyHandle
0x180021c97  mov     r9d, r14d
0x180021c9a  mov     [rsp+360h+var_338], rax; __int64
0x180021c9f  mov     rcx, rsi; hToken
0x180021ca2  lea     rax, [rbp+260h+var_2E0]
0x180021ca6  mov     [rsp+360h+var_340], rax; __int64
0x180021cab  call    DsRolepCreateParentTrustObject
0x180021cb0  mov     edi, 0C0000035h
0x180021cb5  mov     ebx, eax
0x180021cb7  cmp     eax, edi
0x180021cb9  jnz     short loc_180021CF5
0x180021cbb  mov     ecx, edi; Status
0x180021cbd  call    cs:__imp_RtlNtStatusToDosError
0x180021cc3  test    eax, eax
0x180021cc5  jz      loc_180021DFF
0x180021ccb  mov     ecx, edi; Status
0x180021ccd  call    cs:__imp_RtlNtStatusToDosError
0x180021cd3  mov     r9, [rsp+360h+var_2F0]
0x180021cd8  mov     r8, r12
0x180021cdb  mov     ecx, eax
0x180021cdd  mov     [rsp+360h+var_340], 0
0x180021ce6  mov     edx, 0C000721Bh
0x180021ceb  call    DsRolepSetFailureMessage
0x180021cf0  jmp     loc_180021DFF
0x180021cf5  mov     ecx, ebx; Status
0x180021cf7  call    cs:__imp_RtlNtStatusToDosError
0x180021cfd  test    eax, eax
0x180021cff  jz      short loc_180021D26
0x180021d01  mov     ecx, ebx; Status
0x180021d03  call    cs:__imp_RtlNtStatusToDosError
0x180021d09  mov     r8, [rsp+360h+var_2F0]
0x180021d0e  mov     r9, r12
0x180021d11  mov     ecx, eax
0x180021d13  mov     [rsp+360h+var_340], 0
0x180021d1c  mov     edx, 0C000721Ch
0x180021d21  call    DsRolepSetFailureMessage
0x180021d26  test    ebx, ebx
0x180021d28  js      loc_180021DFF
0x180021d2e  mov     rdi, [rsp+360h+var_2E8]
0x180021d33  mov     rdx, [rsp+360h+Buffer]
0x180021d38  xor     r8d, r8d
0x180021d3b  mov     ecx, 7010h
0x180021d40  mov     rdx, [rdx+18h]
0x180021d44  call    DsRolepSetCurrentOperationStatus
0x180021d49  mov     r9, [rbp+260h+var_2B0]
0x180021d4d  lea     rax, [rbp+260h+var_2E0]
0x180021d51  mov     r8, [rsp+360h+PolicyHandle]
0x180021d56  mov     rcx, rsi
0x180021d59  mov     rdx, [rsp+360h+var_310]
0x180021d5e  mov     [rsp+360h+var_330], r14d
0x180021d63  mov     [rsp+360h+var_338], rax
0x180021d68  mov     rax, [rsp+360h+Buffer]
0x180021d6d  mov     [rsp+360h+var_340], rax
0x180021d72  call    DsRolepCreateChildTrustObject
0x180021d77  mov     ebx, eax
0x180021d79  test    eax, eax
0x180021d7b  jns     short loc_180021DBD
0x180021d7d  mov     r14d, 4
0x180021d83  lea     rdx, aDsrolepcreatec; "DsRolepCreateChildTrustObject failed: 0"...
0x180021d8a  mov     ecx, r14d
0x180021d8d  mov     r8d, eax
0x180021d90  call    DsRolepLogPrintRoutine
0x180021d95  test    r15d, r15d
0x180021d98  jnz     short loc_180021DBD
0x180021d9a  mov     rdx, rdi
0x180021d9d  mov     rcx, rsi
0x180021da0  call    ImpLsaDelete
0x180021da5  test    eax, eax
0x180021da7  jns     short loc_180021DFF
0x180021da9  mov     r8d, eax
0x180021dac  lea     rdx, aLsadeleteOfPar; "LsaDelete of ParentTrustedDomain failed"...
0x180021db3  mov     ecx, r14d
0x180021db6  call    DsRolepLogPrintRoutine
0x180021dbb  jmp     short loc_180021DFF
0x180021dbd  test    rdi, rdi
0x180021dc0  jz      short loc_180021DFF
0x180021dc2  mov     rdx, rdi
0x180021dc5  mov     rcx, rsi
0x180021dc8  call    ImpLsaClose
0x180021dcd  jmp     short loc_180021DFF
0x180021dcf  mov     r9d, eax
0x180021dd2  lea     rdx, aOpenpolicyOnWs; "OpenPolicy on %ws failed with 0x%lx\n"
0x180021dd9  mov     r8, r12
0x180021ddc  mov     ecx, r15d
0x180021ddf  call    DsRolepLogPrintRoutine
0x180021de4  jmp     short loc_180021DFF
0x180021de6  mov     r8d, eax
0x180021de9  lea     rdx, aFailedToGenera; "Failed to generate a trust password: %l"...
0x180021df0  mov     ecx, 1
0x180021df5  call    DsRolepLogPrintRoutine
0x180021dfa  mov     ebx, 0C0000001h
0x180021dff  mov     rcx, [rsp+360h+Buffer]; Buffer
0x180021e04  call    cs:__imp_LsaFreeMemory
0x180021e0a  mov     rcx, [rsp+360h+PolicyHandle]; ObjectHandle
0x180021e0f  test    rcx, rcx
0x180021e12  jz      short loc_180021E1A
0x180021e14  call    cs:__imp_LsaClose
0x180021e1a  mov     rdx, [rsp+360h+var_310]
0x180021e1f  test    rdx, rdx
0x180021e22  jz      short loc_180021E2C
0x180021e24  mov     rcx, rsi
0x180021e27  call    ImpLsaClose
0x180021e2c  mov     ecx, 30h ; '0'
0x180021e31  lea     rax, [rbp+260h+var_2E0]
0x180021e35  mov     byte ptr [rax], 0
0x180021e38  inc     rax
0x180021e3b  sub     rcx, 1
0x180021e3f  jnz     short loc_180021E35
0x180021e41  mov     ecx, 18h
0x180021e46  lea     rax, [rsp+360h+SystemTime]
0x180021e4b  mov     byte ptr [rax], 0
0x180021e4e  inc     rax
0x180021e51  sub     rcx, 1
0x180021e55  jnz     short loc_180021E4B
0x180021e57  lea     rax, [rbp+260h+var_260]
0x180021e5b  mov     byte ptr [rax], 0
0x180021e5e  inc     rax
0x180021e61  sub     r13, 1
0x180021e65  jnz     short loc_180021E5B
0x180021e67  mov     ecx, ebx; Status
0x180021e69  call    cs:__imp_RtlNtStatusToDosError
0x180021e6f  mov     rcx, [rbp+260h+var_50]
0x180021e76  xor     rcx, rsp; StackCookie
0x180021e79  call    __security_check_cookie
0x180021e7e  add     rsp, 328h
0x180021e85  pop     r15
0x180021e87  pop     r14
0x180021e89  pop     r13
0x180021e8b  pop     r12
0x180021e8d  pop     rdi
0x180021e8e  pop     rsi
0x180021e8f  pop     rbx
0x180021e90  pop     rbp
0x180021e91  retn
```
