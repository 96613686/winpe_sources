# RegistrationController::CreateTransportKeyNew(ushort const *,ushort const *,_JOIN_TYPE,_KEY_STORAGE_PROVIDER,ulong *,ByteArray &,ByteArray &,ByteArray &)

- ea: `0x18005693c`
- end: `0x180056c8f`
- name: `?CreateTransportKeyNew@RegistrationController@@CAJPEBG0W4_JOIN_TYPE@@W4_KEY_STORAGE_PROVIDER@@PEAKAEAVByteArray@@44@Z`
- size: `851`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180058074`
- `0x18005aa90`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x180032234`
- `0x18005693c`
- `0x180057b94`
- `0x180074278`
- `0x180075868`
- `0x1800762e8`
- `0x1800b93c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056c26`

## string_xrefs

- `0x1800569d3`: `RegistrationController::CreateTransportKeyNew`
- `0x1800569ed`: `RegistrationController::CreateTransportKeyNew`
- `0x180056a12`: `RegistrationController::CreateTransportKeyNew`
- `0x180056a9c`: `RegistrationController::CreateTransportKeyNew`
- `0x180056adb`: `RegistrationController::CreateTransportKeyNew`
- `0x180056b62`: `RegistrationController::CreateTransportKeyNew`
- `0x180056b9a`: `RegistrationController::CreateTransportKeyNew`
- `0x180056be7`: `RegistrationController::CreateTransportKeyNew`
- `0x180056c66`: `RegistrationController::CreateTransportKeyNew`
- `0x180056b53`: `%s: Transport key successfully created. KeyType: %s. Public key size: %u byte(s). AIK certificate present: %s. Attestation statement present: %s`
- `0x180056bf3`: `%s: The transport key is successfully created, but it is empty.`
- `0x180056a95`: `RegistrationKeyHelper::CreateTransportKeyNew`

## pseudocode

```c
__int64 __fastcall RegistrationController::CreateTransportKeyNew(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        ByteArray *a6,
        ByteArray *a7,
        ByteArray *a8)
{
  unsigned __int8 *v10; // r12
  unsigned __int8 *v11; // rsi
  unsigned __int8 *v12; // rdi
  unsigned int *v13; // r14
  int v14; // ebx
  const unsigned __int16 *v15; // rdx
  int v16; // eax
  int v17; // eax
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // r15
  const unsigned __int16 *DsregKeyType; // rax
  int v21; // eax
  const wchar_t *v22; // r8
  __int64 v23; // rcx
  unsigned int v25; // [rsp+60h] [rbp-41h] BYREF
  int v26; // [rsp+64h] [rbp-3Dh]
  unsigned __int8 *v27; // [rsp+68h] [rbp-39h] BYREF
  unsigned __int8 *v28; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int8 *v29; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int64 v30; // [rsp+80h] [rbp-21h] BYREF
  unsigned __int64 v31; // [rsp+88h] [rbp-19h] BYREF
  unsigned __int64 v32[10]; // [rsp+90h] [rbp-11h] BYREF

  v26 = IsDeviceJoin(a3);
  v10 = 0;
  v29 = 0;
  v30 = 0;
  v11 = 0;
  v27 = 0;
  v12 = 0;
  v31 = 0;
  v28 = 0;
  v32[0] = 0;
  v25 = 0;
  ByteArray::Assign(a6, 0, 0);
  ByteArray::Assign(a7, 0, 0);
  ByteArray::Assign(a8, 0, 0);
  v13 = a5;
  if ( !a5 )
  {
    v14 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationController::CreateTransportKeyNew", L"pKeyType");
    v15 = L"pKeyType";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationController::CreateTransportKeyNew", v15);
    goto LABEL_24;
  }
  *a5 = 0;
  if ( !a1 )
  {
    v14 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationController::CreateTransportKeyNew", L"tenantId");
    v15 = L"tenantId";
    goto LABEL_3;
  }
  RegistrationKeyHelper::DeleteTransportKey(v26, a1, a2);
  v16 = RegistrationKeyHelper::CreateTransportKeyNew(
          a4,
          (unsigned int)v26,
          a1,
          a2,
          &v29,
          &v30,
          &v27,
          &v31,
          &v28,
          v32,
          &v25);
  v14 = v16;
  if ( v16 >= 0 )
  {
    v10 = v29;
    v17 = ByteArray::Assign(a6, v29, v30);
    v14 = v17;
    if ( v17 >= 0 )
    {
      if ( *(_QWORD *)a6 && *((_QWORD *)a6 + 1) )
      {
        v11 = v27;
        v18 = v31;
        v12 = v28;
        v19 = v32[0];
        DsregKeyType = GetDsregKeyType(v25);
        Logger::TraceInformation(
          L"%s: Transport key successfully created. KeyType: %s. Public key size: %u byte(s). AIK certificate present: %s."
           " Attestation statement present: %s",
          L"RegistrationController::CreateTransportKeyNew",
          DsregKeyType);
        if ( v11 && v18 && (v21 = ByteArray::Assign(a8, v11, v18), v14 = v21, v21 < 0) )
        {
          v22 = L"ByteArray::Assign(attestationStatement)";
        }
        else
        {
          if ( !v12 || !v19 || (v21 = ByteArray::Assign(a7, v12, v19), v14 = v21, v21 >= 0) )
          {
            v13 = a5;
            *a5 = v25;
            goto LABEL_24;
          }
          v22 = L"ByteArray::Assign(aikCertificate)";
        }
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationController::CreateTransportKeyNew",
          v22,
          (unsigned int)v21);
        v13 = a5;
        goto LABEL_24;
      }
      v14 = -2145648505;
      Logger::TraceError(
        L"%s: The transport key is successfully created, but it is empty.",
        L"RegistrationController::CreateTransportKeyNew");
      MicrosoftTelemetryAssertTriggeredArgs(v23, 2149318791LL);
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationController::CreateTransportKeyNew",
        L"ByteArray::Assign",
        (unsigned int)v17);
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationController::CreateTransportKeyNew",
      L"RegistrationKeyHelper::CreateTransportKeyNew",
      (unsigned int)v16);
    v10 = v29;
  }
  v11 = v27;
  v12 = v28;
LABEL_24:
  LocalFree(v10);
  LocalFree(v11);
  LocalFree(v12);
  if ( v14 < 0 )
  {
    ByteArray::Assign(a6, 0, 0);
    ByteArray::Assign(a7, 0, 0);
    ByteArray::Assign(a8, 0, 0);
    *v13 = 0;
  }
  Logger::TraceVerbose(
    (wchar_t *)L"%s - hr: 0x%08x",
    L"RegistrationController::CreateTransportKeyNew",
    (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18005693c  mov     [rsp-8+arg_18], r9d
0x180056941  push    rbp
0x180056942  push    rbx
0x180056943  push    rsi
0x180056944  push    rdi
0x180056945  push    r12
0x180056947  push    r13
0x180056949  push    r14
0x18005694b  push    r15
0x18005694d  lea     rbp, [rsp-7]
0x180056952  sub     rsp, 0A8h
0x180056959  mov     rbx, rcx
0x18005695c  mov     r15, rdx
0x18005695f  mov     ecx, r8d
0x180056962  call    ?IsDeviceJoin@@YAHW4_JOIN_TYPE@@@Z; IsDeviceJoin(_JOIN_TYPE)
0x180056967  mov     r13, [rbp+3Fh+arg_28]
0x18005696b  xor     r8d, r8d; unsigned __int64
0x18005696e  mov     [rbp+3Fh+var_7C], eax
0x180056971  xor     edx, edx; unsigned __int8 *
0x180056973  xor     eax, eax
0x180056975  mov     rcx, r13; this
0x180056978  mov     r12d, eax
0x18005697b  mov     [rbp+3Fh+var_68], rax
0x18005697f  mov     [rbp+3Fh+var_60], rax
0x180056983  mov     esi, eax
0x180056985  mov     [rbp+3Fh+var_78], rax
0x180056989  mov     edi, eax
0x18005698b  mov     [rbp+3Fh+var_58], rax
0x18005698f  mov     [rbp+3Fh+var_70], rax
0x180056993  mov     [rbp+3Fh+var_50], rax
0x180056997  mov     [rbp+3Fh+var_80], eax
0x18005699a  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005699f  mov     rcx, [rbp+3Fh+arg_30]; this
0x1800569a3  xor     r8d, r8d; unsigned __int64
0x1800569a6  xor     edx, edx; unsigned __int8 *
0x1800569a8  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x1800569ad  mov     rcx, [rbp+3Fh+arg_38]; this
0x1800569b4  xor     r8d, r8d; unsigned __int64
0x1800569b7  xor     edx, edx; unsigned __int8 *
0x1800569b9  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x1800569be  mov     r14, [rbp+3Fh+arg_20]
0x1800569c2  test    r14, r14
0x1800569c5  jnz     short loc_1800569FE
0x1800569c7  lea     r8, aPkeytype; "pKeyType"
0x1800569ce  mov     ebx, 80070057h
0x1800569d3  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x1800569da  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800569e1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800569e6  lea     rdx, aPkeytype; "pKeyType"
0x1800569ed  lea     rcx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x1800569f4  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800569f9  jmp     loc_180056C11
0x1800569fe  mov     [r14], esi
0x180056a01  test    rbx, rbx
0x180056a04  jnz     short loc_180056A2E
0x180056a06  lea     r8, aTenantid_1; "tenantId"
0x180056a0d  mov     ebx, 80070057h
0x180056a12  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x180056a19  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180056a20  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180056a25  lea     rdx, aTenantid_1; "tenantId"
0x180056a2c  jmp     short loc_1800569ED
0x180056a2e  mov     ecx, [rbp+3Fh+var_7C]; int
0x180056a31  mov     r8, r15; unsigned __int16 *
0x180056a34  mov     rdx, rbx; unsigned __int16 *
0x180056a37  call    ?DeleteTransportKey@RegistrationKeyHelper@@SAJHPEBG0@Z; RegistrationKeyHelper::DeleteTransportKey(int,ushort const *,ushort const *)
0x180056a3c  mov     edx, [rbp+3Fh+var_7C]
0x180056a3f  lea     rax, [rbp+3Fh+var_80]
0x180056a43  mov     ecx, [rbp+3Fh+arg_18]
0x180056a46  mov     r9, r15
0x180056a49  mov     [rsp+0E0h+var_90], rax
0x180056a4e  mov     r8, rbx
0x180056a51  lea     rax, [rbp+3Fh+var_50]
0x180056a55  mov     [rsp+0E0h+var_98], rax
0x180056a5a  lea     rax, [rbp+3Fh+var_70]
0x180056a5e  mov     [rsp+0E0h+var_A0], rax
0x180056a63  lea     rax, [rbp+3Fh+var_58]
0x180056a67  mov     [rsp+0E0h+var_A8], rax
0x180056a6c  lea     rax, [rbp+3Fh+var_78]
0x180056a70  mov     [rsp+0E0h+var_B0], rax
0x180056a75  lea     rax, [rbp+3Fh+var_60]
0x180056a79  mov     [rsp+0E0h+var_B8], rax
0x180056a7e  lea     rax, [rbp+3Fh+var_68]
0x180056a82  mov     [rsp+0E0h+var_C0], rax
0x180056a87  call    ?CreateTransportKeyNew@RegistrationKeyHelper@@SAJW4_KEY_STORAGE_PROVIDER@@HPEBG1PEAPEAEPEA_K2323PEAK@Z; RegistrationKeyHelper::CreateTransportKeyNew(_KEY_STORAGE_PROVIDER,int,ushort const *,ushort const *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,ulong *)
0x180056a8c  mov     ebx, eax
0x180056a8e  test    eax, eax
0x180056a90  jns     short loc_180056AB8
0x180056a92  mov     r9d, eax
0x180056a95  lea     r8, aRegistrationke_10; "RegistrationKeyHelper::CreateTransportK"...
0x180056a9c  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x180056aa3  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180056aaa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180056aaf  mov     r12, [rbp+3Fh+var_68]
0x180056ab3  jmp     loc_180056C09
0x180056ab8  mov     r12, [rbp+3Fh+var_68]
0x180056abc  mov     rcx, r13; this
0x180056abf  mov     r8, [rbp+3Fh+var_60]; unsigned __int64
0x180056ac3  mov     rdx, r12; unsigned __int8 *
0x180056ac6  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180056acb  mov     ebx, eax
0x180056acd  test    eax, eax
0x180056acf  jns     short loc_180056AF3
0x180056ad1  mov     r9d, eax
0x180056ad4  lea     r8, aBytearrayAssig; "ByteArray::Assign"
0x180056adb  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x180056ae2  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180056ae9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180056aee  jmp     loc_180056C09
0x180056af3  cmp     [r13+0], rsi
0x180056af7  jz      loc_180056BE7
0x180056afd  mov     r9, [r13+8]
0x180056b01  test    r9, r9
0x180056b04  jz      loc_180056BE7
0x180056b0a  mov     rsi, [rbp+3Fh+var_78]
0x180056b0e  lea     rdx, aTrue_0; "TRUE"
0x180056b15  mov     r14, [rbp+3Fh+var_58]
0x180056b19  test    rsi, rsi
0x180056b1c  jz      short loc_180056B26
0x180056b1e  mov     r10, rdx
0x180056b21  test    r14, r14
0x180056b24  jnz     short loc_180056B2D
0x180056b26  lea     r10, aFalse_0; "FALSE"
0x180056b2d  mov     rdi, [rbp+3Fh+var_70]
0x180056b31  mov     r15, [rbp+3Fh+var_50]
0x180056b35  test    rdi, rdi
0x180056b38  jz      short loc_180056B3F
0x180056b3a  test    r15, r15
0x180056b3d  jnz     short loc_180056B46
0x180056b3f  lea     rdx, aFalse_0; "FALSE"
0x180056b46  mov     ecx, [rbp+3Fh+var_80]; unsigned int
0x180056b49  call    ?GetDsregKeyType@@YAPEBGK@Z; GetDsregKeyType(ulong)
0x180056b4e  mov     [rsp+0E0h+var_B8], r10
0x180056b53  lea     rcx, aSTransportKeyS; "%s: Transport key successfully created."...
0x180056b5a  mov     [rsp+0E0h+var_C0], rdx
0x180056b5f  mov     r8, rax
0x180056b62  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x180056b69  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180056b6e  test    rsi, rsi
0x180056b71  jz      short loc_180056BB3
0x180056b73  test    r14, r14
0x180056b76  jz      short loc_180056BB3
0x180056b78  mov     rcx, [rbp+3Fh+arg_38]; this
0x180056b7f  mov     r8, r14; unsigned __int64
0x180056b82  mov     rdx, rsi; unsigned __int8 *
0x180056b85  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180056b8a  mov     ebx, eax
0x180056b8c  test    eax, eax
0x180056b8e  jns     short loc_180056BB3
0x180056b90  lea     r8, aBytearrayAssig_3; "ByteArray::Assign(attestationStatement)"
0x180056b97  mov     r9d, eax
0x180056b9a  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x180056ba1  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180056ba8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180056bad  mov     r14, [rbp+3Fh+arg_20]
0x180056bb1  jmp     short loc_180056C11
0x180056bb3  test    rdi, rdi
0x180056bb6  jz      short loc_180056BDB
0x180056bb8  test    r15, r15
0x180056bbb  jz      short loc_180056BDB
0x180056bbd  mov     rcx, [rbp+3Fh+arg_30]; this
0x180056bc1  mov     r8, r15; unsigned __int64
0x180056bc4  mov     rdx, rdi; unsigned __int8 *
0x180056bc7  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180056bcc  mov     ebx, eax
0x180056bce  test    eax, eax
0x180056bd0  jns     short loc_180056BDB
0x180056bd2  lea     r8, aBytearrayAssig_0; "ByteArray::Assign(aikCertificate)"
0x180056bd9  jmp     short loc_180056B97
0x180056bdb  mov     r14, [rbp+3Fh+arg_20]
0x180056bdf  mov     eax, [rbp+3Fh+var_80]
0x180056be2  mov     [r14], eax
0x180056be5  jmp     short loc_180056C11
0x180056be7  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x180056bee  mov     ebx, 801C0087h
0x180056bf3  lea     rcx, aSTheTransportK; "%s: The transport key is successfully c"...
0x180056bfa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180056bff  mov     edx, 801C0087h
0x180056c04  call    MicrosoftTelemetryAssertTriggeredArgs
0x180056c09  mov     rsi, [rbp+3Fh+var_78]
0x180056c0d  mov     rdi, [rbp+3Fh+var_70]
0x180056c11  mov     rcx, r12; hMem
0x180056c14  call    cs:__imp_LocalFree
0x180056c1a  mov     rcx, rsi; hMem
0x180056c1d  call    cs:__imp_LocalFree
0x180056c23  mov     rcx, rdi; hMem
0x180056c26  call    cs:__imp_LocalFree
0x180056c2c  test    ebx, ebx
0x180056c2e  jns     short loc_180056C63
0x180056c30  xor     r8d, r8d; unsigned __int64
0x180056c33  xor     edx, edx; unsigned __int8 *
0x180056c35  mov     rcx, r13; this
0x180056c38  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180056c3d  mov     rcx, [rbp+3Fh+arg_30]; this
0x180056c41  xor     r8d, r8d; unsigned __int64
0x180056c44  xor     edx, edx; unsigned __int8 *
0x180056c46  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180056c4b  mov     rcx, [rbp+3Fh+arg_38]; this
0x180056c52  xor     r8d, r8d; unsigned __int64
0x180056c55  xor     edx, edx; unsigned __int8 *
0x180056c57  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180056c5c  mov     dword ptr [r14], 0
0x180056c63  mov     r8d, ebx
0x180056c66  lea     rdx, aRegistrationco_4; "RegistrationController::CreateTransport"...
0x180056c6d  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180056c74  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180056c79  mov     eax, ebx
0x180056c7b  add     rsp, 0A8h
0x180056c82  pop     r15
0x180056c84  pop     r14
0x180056c86  pop     r13
0x180056c88  pop     r12
0x180056c8a  pop     rdi
0x180056c8b  pop     rsi
0x180056c8c  pop     rbx
0x180056c8d  pop     rbp
0x180056c8e  retn
```
