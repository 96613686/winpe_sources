# RegistrationController::CreateTransportKey(ushort const *,ushort const *,_JOIN_TYPE,_KEY_POLICY,_HARDWARE_POLICY,ulong *,ByteArray &,ByteArray &,ByteArray &)

- ea: `0x1800565d8`
- end: `0x180056935`
- name: `?CreateTransportKey@RegistrationController@@CAJPEBG0W4_JOIN_TYPE@@W4_KEY_POLICY@@W4_HARDWARE_POLICY@@PEAKAEAVByteArray@@55@Z`
- size: `861`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058074`
- `0x18005aa90`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x180032234`
- `0x1800565d8`
- `0x180057b94`
- `0x180074278`
- `0x1800752b0`
- `0x1800762e8`
- `0x1800b93c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800568b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800568c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800568c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800568b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800568c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800568c9`

## string_xrefs

- `0x180056672`: `RegistrationController::CreateTransportKey`
- `0x18005668c`: `RegistrationController::CreateTransportKey`
- `0x1800566b0`: `RegistrationController::CreateTransportKey`
- `0x18005673c`: `RegistrationController::CreateTransportKey`
- `0x18005677b`: `RegistrationController::CreateTransportKey`
- `0x180056802`: `RegistrationController::CreateTransportKey`
- `0x18005683a`: `RegistrationController::CreateTransportKey`
- `0x180056886`: `RegistrationController::CreateTransportKey`
- `0x18005690c`: `RegistrationController::CreateTransportKey`
- `0x180056735`: `RegistrationKeyHelper::CreateTransportKey`
- `0x1800567f3`: `%s: Transport key successfully created. KeyType: %s. Public key size: %u byte(s). AIK certificate present: %s. Attestation statement present: %s`
- `0x180056892`: `%s: The transport key is successfully created, but it is empty.`

## pseudocode

```c
__int64 __fastcall RegistrationController::CreateTransportKey(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        ByteArray *a7,
        ByteArray *a8,
        ByteArray *a9)
{
  unsigned int v11; // eax
  ByteArray *v12; // r13
  unsigned int v13; // r15d
  HLOCAL v14; // r12
  unsigned __int8 *v15; // rsi
  unsigned __int8 *v16; // rdi
  int v17; // ebx
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // r15
  const unsigned __int16 *DsregKeyType; // rax
  int v25; // eax
  const wchar_t *v26; // r8
  unsigned int *v27; // r14
  __int64 v28; // rcx
  HLOCAL v30; // [rsp+60h] [rbp-31h] BYREF
  HLOCAL v31; // [rsp+68h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-21h] BYREF
  unsigned __int64 v33; // [rsp+78h] [rbp-19h] BYREF
  unsigned __int64 v34; // [rsp+80h] [rbp-11h] BYREF
  unsigned __int64 v35[9]; // [rsp+88h] [rbp-9h] BYREF

  v11 = IsDeviceJoin(a3);
  v12 = a7;
  v13 = v11;
  hMem = 0;
  v33 = 0;
  v14 = 0;
  v30 = 0;
  v15 = 0;
  v34 = 0;
  v16 = 0;
  v31 = 0;
  v35[0] = 0;
  a5 = 0;
  ByteArray::Assign(a7, 0, 0);
  ByteArray::Assign(a8, 0, 0);
  ByteArray::Assign(a9, 0, 0);
  if ( !a6 )
  {
    v17 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationController::CreateTransportKey", L"pKeyType");
    v18 = L"pKeyType";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationController::CreateTransportKey", v18);
    goto LABEL_24;
  }
  *a6 = 0;
  if ( !a1 )
  {
    v17 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationController::CreateTransportKey", L"tenantId");
    v18 = L"tenantId";
    goto LABEL_3;
  }
  RegistrationKeyHelper::DeleteTransportKey(v13, a1, a2);
  v20 = RegistrationKeyHelper::CreateTransportKey(a4, v19, v13, a1, a2, &hMem, &v33, &v30, &v34, &v31, v35, &a5);
  v17 = v20;
  if ( v20 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationController::CreateTransportKey",
      L"RegistrationKeyHelper::CreateTransportKey",
      (unsigned int)v20);
    v14 = hMem;
LABEL_23:
    v15 = (unsigned __int8 *)v30;
    v16 = (unsigned __int8 *)v31;
    goto LABEL_24;
  }
  v14 = hMem;
  v21 = ByteArray::Assign(v12, (const unsigned __int8 *)hMem, v33);
  v17 = v21;
  if ( v21 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationController::CreateTransportKey",
      L"ByteArray::Assign",
      (unsigned int)v21);
    goto LABEL_23;
  }
  if ( !*(_QWORD *)v12 || !*((_QWORD *)v12 + 1) )
  {
    v17 = -2145648505;
    Logger::TraceError(
      L"%s: The transport key is successfully created, but it is empty.",
      L"RegistrationController::CreateTransportKey");
    MicrosoftTelemetryAssertTriggeredArgs(v28, 2149318791LL);
    goto LABEL_23;
  }
  v15 = (unsigned __int8 *)v30;
  v22 = v34;
  v16 = (unsigned __int8 *)v31;
  v23 = v35[0];
  DsregKeyType = GetDsregKeyType(a5);
  Logger::TraceInformation(
    L"%s: Transport key successfully created. KeyType: %s. Public key size: %u byte(s). AIK certificate present: %s. Attes"
     "tation statement present: %s",
    L"RegistrationController::CreateTransportKey",
    DsregKeyType);
  if ( v15 && v22 && (v25 = ByteArray::Assign(a9, v15, v22), v17 = v25, v25 < 0) )
  {
    v26 = L"ByteArray::Assign(attestationStatement)";
  }
  else
  {
    if ( !v16 || !v23 || (v25 = ByteArray::Assign(a8, v16, v23), v17 = v25, v25 >= 0) )
    {
      v27 = a6;
      *a6 = a5;
      goto LABEL_25;
    }
    v26 = L"ByteArray::Assign(aikCertificate)";
  }
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"RegistrationController::CreateTransportKey",
    v26,
    (unsigned int)v25);
LABEL_24:
  v27 = a6;
LABEL_25:
  LocalFree(v14);
  LocalFree(v15);
  LocalFree(v16);
  if ( v17 < 0 )
  {
    ByteArray::Assign(v12, 0, 0);
    ByteArray::Assign(a8, 0, 0);
    ByteArray::Assign(a9, 0, 0);
    *v27 = 0;
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationController::CreateTransportKey", (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800565d8  mov     [rsp-8+arg_18], r9d
0x1800565dd  push    rbp
0x1800565de  push    rbx
0x1800565df  push    rsi
0x1800565e0  push    rdi
0x1800565e1  push    r12
0x1800565e3  push    r13
0x1800565e5  push    r14
0x1800565e7  push    r15
0x1800565e9  lea     rbp, [rsp-7]
0x1800565ee  sub     rsp, 98h
0x1800565f5  mov     rbx, rcx
0x1800565f8  mov     r14, rdx
0x1800565fb  mov     ecx, r8d
0x1800565fe  call    ?IsDeviceJoin@@YAHW4_JOIN_TYPE@@@Z; IsDeviceJoin(_JOIN_TYPE)
0x180056603  mov     r13, [rbp+3Fh+arg_30]
0x180056607  mov     r15d, eax
0x18005660a  xor     eax, eax
0x18005660c  xor     r8d, r8d; unsigned __int64
0x18005660f  xor     edx, edx; unsigned __int8 *
0x180056611  mov     [rbp+3Fh+hMem], rax
0x180056615  mov     rcx, r13; this
0x180056618  mov     [rbp+3Fh+var_58], rax
0x18005661c  mov     r12d, eax
0x18005661f  mov     [rbp+3Fh+var_70], rax
0x180056623  mov     esi, eax
0x180056625  mov     [rbp+3Fh+var_50], rax
0x180056629  mov     edi, eax
0x18005662b  mov     [rbp+3Fh+var_68], rax
0x18005662f  mov     [rbp+3Fh+var_48], rax
0x180056633  mov     [rbp+3Fh+arg_20], eax
0x180056636  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005663b  mov     rcx, [rbp+3Fh+arg_38]; this
0x180056642  xor     r8d, r8d; unsigned __int64
0x180056645  xor     edx, edx; unsigned __int8 *
0x180056647  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005664c  mov     rcx, [rbp+3Fh+arg_40]; this
0x180056653  xor     r8d, r8d; unsigned __int64
0x180056656  xor     edx, edx; unsigned __int8 *
0x180056658  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005665d  mov     rax, [rbp+3Fh+arg_28]
0x180056661  test    rax, rax
0x180056664  jnz     short loc_18005669D
0x180056666  lea     r8, aPkeytype; "pKeyType"
0x18005666d  mov     ebx, 80070057h
0x180056672  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x180056679  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180056680  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180056685  lea     rdx, aPkeytype; "pKeyType"
0x18005668c  lea     rcx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x180056693  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180056698  jmp     loc_1800568B0
0x18005669d  mov     [rax], esi
0x18005669f  test    rbx, rbx
0x1800566a2  jnz     short loc_1800566CC
0x1800566a4  lea     r8, aTenantid_1; "tenantId"
0x1800566ab  mov     ebx, 80070057h
0x1800566b0  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x1800566b7  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800566be  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800566c3  lea     rdx, aTenantid_1; "tenantId"
0x1800566ca  jmp     short loc_18005668C
0x1800566cc  mov     r8, r14; unsigned __int16 *
0x1800566cf  mov     rdx, rbx; unsigned __int16 *
0x1800566d2  mov     ecx, r15d; int
0x1800566d5  call    ?DeleteTransportKey@RegistrationKeyHelper@@SAJHPEBG0@Z; RegistrationKeyHelper::DeleteTransportKey(int,ushort const *,ushort const *)
0x1800566da  mov     ecx, [rbp+3Fh+arg_18]
0x1800566dd  lea     rax, [rbp+3Fh+arg_20]
0x1800566e1  mov     [rsp+0D0h+var_78], rax
0x1800566e6  mov     r9, rbx
0x1800566e9  lea     rax, [rbp+3Fh+var_48]
0x1800566ed  mov     r8d, r15d
0x1800566f0  mov     [rsp+0D0h+var_80], rax
0x1800566f5  lea     rax, [rbp+3Fh+var_68]
0x1800566f9  mov     [rsp+0D0h+var_88], rax
0x1800566fe  lea     rax, [rbp+3Fh+var_50]
0x180056702  mov     [rsp+0D0h+var_90], rax
0x180056707  lea     rax, [rbp+3Fh+var_70]
0x18005670b  mov     [rsp+0D0h+var_98], rax
0x180056710  lea     rax, [rbp+3Fh+var_58]
0x180056714  mov     [rsp+0D0h+var_A0], rax
0x180056719  lea     rax, [rbp+3Fh+hMem]
0x18005671d  mov     [rsp+0D0h+var_A8], rax
0x180056722  mov     [rsp+0D0h+var_B0], r14
0x180056727  call    ?CreateTransportKey@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@HPEBG2PEAPEAEPEA_K3434PEAK@Z; RegistrationKeyHelper::CreateTransportKey(_KEY_POLICY,_HARDWARE_POLICY,int,ushort const *,ushort const *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,uchar * *,unsigned __int64 *,ulong *)
0x18005672c  mov     ebx, eax
0x18005672e  test    eax, eax
0x180056730  jns     short loc_180056758
0x180056732  mov     r9d, eax
0x180056735  lea     r8, aRegistrationke_12; "RegistrationKeyHelper::CreateTransportK"...
0x18005673c  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x180056743  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005674a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005674f  mov     r12, [rbp+3Fh+hMem]
0x180056753  jmp     loc_1800568A8
0x180056758  mov     r12, [rbp+3Fh+hMem]
0x18005675c  mov     rcx, r13; this
0x18005675f  mov     r8, [rbp+3Fh+var_58]; unsigned __int64
0x180056763  mov     rdx, r12; unsigned __int8 *
0x180056766  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005676b  mov     ebx, eax
0x18005676d  test    eax, eax
0x18005676f  jns     short loc_180056793
0x180056771  mov     r9d, eax
0x180056774  lea     r8, aBytearrayAssig; "ByteArray::Assign"
0x18005677b  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x180056782  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180056789  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005678e  jmp     loc_1800568A8
0x180056793  cmp     [r13+0], rsi
0x180056797  jz      loc_180056886
0x18005679d  mov     r9, [r13+8]
0x1800567a1  test    r9, r9
0x1800567a4  jz      loc_180056886
0x1800567aa  mov     rsi, [rbp+3Fh+var_70]
0x1800567ae  lea     rdx, aTrue_0; "TRUE"
0x1800567b5  mov     r14, [rbp+3Fh+var_50]
0x1800567b9  test    rsi, rsi
0x1800567bc  jz      short loc_1800567C6
0x1800567be  mov     r10, rdx
0x1800567c1  test    r14, r14
0x1800567c4  jnz     short loc_1800567CD
0x1800567c6  lea     r10, aFalse_0; "FALSE"
0x1800567cd  mov     rdi, [rbp+3Fh+var_68]
0x1800567d1  mov     r15, [rbp+3Fh+var_48]
0x1800567d5  test    rdi, rdi
0x1800567d8  jz      short loc_1800567DF
0x1800567da  test    r15, r15
0x1800567dd  jnz     short loc_1800567E6
0x1800567df  lea     rdx, aFalse_0; "FALSE"
0x1800567e6  mov     ecx, [rbp+3Fh+arg_20]; unsigned int
0x1800567e9  call    ?GetDsregKeyType@@YAPEBGK@Z; GetDsregKeyType(ulong)
0x1800567ee  mov     [rsp+0D0h+var_A8], r10
0x1800567f3  lea     rcx, aSTransportKeyS; "%s: Transport key successfully created."...
0x1800567fa  mov     [rsp+0D0h+var_B0], rdx
0x1800567ff  mov     r8, rax
0x180056802  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x180056809  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18005680e  test    rsi, rsi
0x180056811  jz      short loc_18005684F
0x180056813  test    r14, r14
0x180056816  jz      short loc_18005684F
0x180056818  mov     rcx, [rbp+3Fh+arg_40]; this
0x18005681f  mov     r8, r14; unsigned __int64
0x180056822  mov     rdx, rsi; unsigned __int8 *
0x180056825  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005682a  mov     ebx, eax
0x18005682c  test    eax, eax
0x18005682e  jns     short loc_18005684F
0x180056830  lea     r8, aBytearrayAssig_3; "ByteArray::Assign(attestationStatement)"
0x180056837  mov     r9d, eax
0x18005683a  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x180056841  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180056848  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005684d  jmp     short loc_1800568B0
0x18005684f  test    rdi, rdi
0x180056852  jz      short loc_18005687A
0x180056854  test    r15, r15
0x180056857  jz      short loc_18005687A
0x180056859  mov     rcx, [rbp+3Fh+arg_38]; this
0x180056860  mov     r8, r15; unsigned __int64
0x180056863  mov     rdx, rdi; unsigned __int8 *
0x180056866  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x18005686b  mov     ebx, eax
0x18005686d  test    eax, eax
0x18005686f  jns     short loc_18005687A
0x180056871  lea     r8, aBytearrayAssig_0; "ByteArray::Assign(aikCertificate)"
0x180056878  jmp     short loc_180056837
0x18005687a  mov     r14, [rbp+3Fh+arg_28]
0x18005687e  mov     eax, [rbp+3Fh+arg_20]
0x180056881  mov     [r14], eax
0x180056884  jmp     short loc_1800568B4
0x180056886  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x18005688d  mov     ebx, 801C0087h
0x180056892  lea     rcx, aSTheTransportK; "%s: The transport key is successfully c"...
0x180056899  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005689e  mov     edx, 801C0087h
0x1800568a3  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800568a8  mov     rsi, [rbp+3Fh+var_70]
0x1800568ac  mov     rdi, [rbp+3Fh+var_68]
0x1800568b0  mov     r14, [rbp+3Fh+arg_28]
0x1800568b4  mov     rcx, r12; hMem
0x1800568b7  call    cs:__imp_LocalFree
0x1800568bd  mov     rcx, rsi; hMem
0x1800568c0  call    cs:__imp_LocalFree
0x1800568c6  mov     rcx, rdi; hMem
0x1800568c9  call    cs:__imp_LocalFree
0x1800568cf  test    ebx, ebx
0x1800568d1  jns     short loc_180056909
0x1800568d3  xor     r8d, r8d; unsigned __int64
0x1800568d6  xor     edx, edx; unsigned __int8 *
0x1800568d8  mov     rcx, r13; this
0x1800568db  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x1800568e0  mov     rcx, [rbp+3Fh+arg_38]; this
0x1800568e7  xor     r8d, r8d; unsigned __int64
0x1800568ea  xor     edx, edx; unsigned __int8 *
0x1800568ec  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x1800568f1  mov     rcx, [rbp+3Fh+arg_40]; this
0x1800568f8  xor     r8d, r8d; unsigned __int64
0x1800568fb  xor     edx, edx; unsigned __int8 *
0x1800568fd  call    ?Assign@ByteArray@@QEAAJPEBE_K@Z; ByteArray::Assign(uchar const *,unsigned __int64)
0x180056902  mov     dword ptr [r14], 0
0x180056909  mov     r8d, ebx
0x18005690c  lea     rdx, aRegistrationco_6; "RegistrationController::CreateTransport"...
0x180056913  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18005691a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18005691f  mov     eax, ebx
0x180056921  add     rsp, 98h
0x180056928  pop     r15
0x18005692a  pop     r14
0x18005692c  pop     r13
0x18005692e  pop     r12
0x180056930  pop     rdi
0x180056931  pop     rsi
0x180056932  pop     rbx
0x180056933  pop     rbp
0x180056934  retn
```
