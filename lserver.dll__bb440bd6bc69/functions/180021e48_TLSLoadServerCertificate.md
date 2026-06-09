# TLSLoadServerCertificate

- ea: `0x180021e48`
- end: `0x1800221d2`
- name: `TLSLoadServerCertificate`
- size: `906`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014310`
- `0x180021994`
- `0x1800221d8`

## callees

- `0x18000575c`
- `0x180021968`
- `0x180021e48`
- `0x18002256c`
- `0x180022910`
- `0x18003a1f8`
- `0x18007ccec`
- `0x1800a5010`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x18002215f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002215f`
- `CRYPT32!CertCreateCertificateContext` at `0x18002207f`
- `CRYPT32!CertCreateCertificateContext` at `0x18002213a`
- `CRYPT32!CertCreateCertificateContext` at `0x18002207f`
- `CRYPT32!CertCreateCertificateContext` at `0x18002213a`
- `CRYPT32!CertFreeCertificateContext` at `0x180022061`
- `CRYPT32!CertFreeCertificateContext` at `0x1800220d9`
- `CRYPT32!CertFreeCertificateContext` at `0x180022061`
- `CRYPT32!CertFreeCertificateContext` at `0x1800220d9`
- `KERNEL32!GetLastError` at `0x180022099`
- `KERNEL32!GetLastError` at `0x180022179`
- `KERNEL32!GetLastError` at `0x180022099`
- `KERNEL32!GetLastError` at `0x180022179`
- `KERNEL32!LocalFree` at `0x1800221aa`
- `KERNEL32!LocalFree` at `0x1800221aa`

## pseudocode

```c
__int64 __fastcall TLSLoadServerCertificate(int a1)
{
  BYTE *v2; // rdi
  int v3; // esi
  __int64 v4; // rax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  RdlsSecretsCache *v8; // rcx
  unsigned __int8 *v9; // r8
  unsigned int v10; // r9d
  unsigned int v11; // ebx
  DWORD LastError; // eax
  int v13; // eax
  DWORD v14; // eax
  struct _EVENT_DESCRIPTOR v16; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbCertEncoded; // [rsp+88h] [rbp+38h] BYREF
  BYTE *pbCertEncoded; // [rsp+90h] [rbp+40h] BYREF

  v2 = 0;
  cbCertEncoded = 0;
  v3 = 0;
  RdlsSecretsCache::g_ftCertExpiredTime.dwLowDateTime = -1;
  RdlsSecretsCache::g_ftCertExpiredTime.dwHighDateTime = -1;
  v4 = *(_QWORD *)g_RdlsSecrets;
  pbCertEncoded = 0;
  v5 = (*(__int64 (__fastcall **)(RdlsSecretsCache *, HCRYPTPROV_LEGACY, HCERTSTORE *))(v4 + 64))(
         g_RdlsSecrets,
         g_RdlsCryptProv,
         &g_hCaStore);
  if ( (unsigned int)(v5 + 1073676254) > 1 )
    goto LABEL_6;
  v5 = (*(__int64 (__fastcall **)(RdlsSecretsCache *, __int64, __int64))(*(_QWORD *)g_RdlsSecrets + 56LL))(
         g_RdlsSecrets,
         2,
         1);
  if ( !v5 )
  {
    v5 = (*(__int64 (__fastcall **)(RdlsSecretsCache *, HCRYPTPROV_LEGACY, HCERTSTORE *))(*(_QWORD *)g_RdlsSecrets + 64LL))(
           g_RdlsSecrets,
           g_RdlsCryptProv,
           &g_hCaStore);
    if ( !v5 )
    {
      CrimsonHelper::RaiseEvent<unsigned short *>(
        CrimsonHelper::s_instance,
        TLS_W_CORRUPTTRYBACKUPCERTIFICATE,
        &g_szComputerName);
      v6 = 2;
      v7 = 3;
LABEL_10:
      (*(void (__fastcall **)(RdlsSecretsCache *, __int64, __int64))(*(_QWORD *)g_RdlsSecrets + 56LL))(
        g_RdlsSecrets,
        v6,
        v7);
      goto LABEL_11;
    }
  }
  if ( v5 != -1073676253 )
  {
LABEL_6:
    if ( v5 != -1073676254 )
      goto LABEL_11;
  }
  v5 = (*(__int64 (__fastcall **)(RdlsSecretsCache *, __int64, __int64))(*(_QWORD *)g_RdlsSecrets + 56LL))(
         g_RdlsSecrets,
         3,
         1);
  if ( !v5 )
  {
    v5 = (*(__int64 (__fastcall **)(RdlsSecretsCache *, HCRYPTPROV_LEGACY, HCERTSTORE *))(*(_QWORD *)g_RdlsSecrets + 64LL))(
           g_RdlsSecrets,
           g_RdlsCryptProv,
           &g_hCaStore);
    if ( !v5 )
    {
      CrimsonHelper::RaiseEvent<unsigned short *>(
        CrimsonHelper::s_instance,
        TLS_W_CORRUPTTRYBACKUPCERTIFICATE,
        &g_szComputerName);
      v6 = 3;
      v7 = 2;
      goto LABEL_10;
    }
  }
LABEL_11:
  if ( g_bIsInfoEventLogged )
  {
    CrimsonHelper::RaiseEvent<unsigned short *>(CrimsonHelper::s_instance, TLS_W_EXPIRE_CERT, &g_szComputerName);
    g_bIsInfoEventLogged = 0;
  }
  if ( v5 == -1073676253 )
  {
    CrimsonHelper::RaiseEvent<unsigned short *>(
      CrimsonHelper::s_instance,
      TLS_W_STARTUPCORRUPTEDCERT,
      &g_szComputerName);
  }
  else
  {
    if ( !(unsigned int)CanIssuePermLicense() && a1 == 1 )
      CrimsonHelper::RaiseEvent<unsigned short *>(CrimsonHelper::s_instance, TLS_W_STARTUPNOCERT, &g_szComputerName);
    if ( !v5 )
      goto LABEL_28;
  }
  v9 = (unsigned __int8 *)Src;
  if ( !Src || (v10 = Size) == 0 )
  {
    TLSReGenerateKeys(0);
    v9 = (unsigned __int8 *)Src;
    v10 = Size;
  }
  if ( RdlsSecretsCache::GenerateSelfSignCertificates(v8, g_RdlsCryptProv, v9, v10) )
    return 0;
  if ( RdlsSecretsCache::g_pLicenseCertContext )
    CertFreeCertificateContext(RdlsSecretsCache::g_pLicenseCertContext);
  RdlsSecretsCache::g_pLicenseCertContext = CertCreateCertificateContext(
                                              1u,
                                              *((const BYTE **)g_RdlsSecrets + 4),
                                              *((_DWORD *)g_RdlsSecrets + 6));
  if ( !RdlsSecretsCache::g_pLicenseCertContext )
  {
    v11 = 0;
    LastError = GetLastError();
    v16 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
    TLSLogEvent(&v16, 0xC0110004, LastError);
    return v11;
  }
  v3 = 1;
LABEL_28:
  v11 = 1;
  if ( g_SelfSignCertContext )
  {
    CertFreeCertificateContext(g_SelfSignCertContext);
    g_SelfSignCertContext = 0;
  }
  if ( v3 )
  {
    g_SelfSignCertContext = CertDuplicateCertificateContext(RdlsSecretsCache::g_pLicenseCertContext);
    if ( g_SelfSignCertContext )
      return v11;
    goto LABEL_36;
  }
  v13 = TLSCreateSelfSignCertificate(g_RdlsCryptProv, 2u, 0, 0, (__int64)&cbCertEncoded, (__int64)&pbCertEncoded);
  v2 = pbCertEncoded;
  if ( !v13 )
  {
    g_SelfSignCertContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
    if ( !g_SelfSignCertContext )
    {
LABEL_36:
      v11 = 0;
      v14 = GetLastError();
      v16 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
      TLSLogEvent(&v16, 0xC0110004, v14);
    }
  }
  if ( v2 )
    LocalFree(v2);
  return v11;
}

```

## disassembly

```asm
0x180021e48  mov     [rsp-28h+arg_0], rbx
0x180021e4d  mov     [rsp-28h+arg_18], rsi
0x180021e52  push    rbp
0x180021e53  push    rdi
0x180021e54  push    r12
0x180021e56  push    r13
0x180021e58  push    r14
0x180021e5a  mov     rbp, rsp
0x180021e5d  sub     rsp, 50h
0x180021e61  mov     rdx, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; RdlsCryptHandle g_RdlsCryptProv
0x180021e68  lea     r8, ?g_hCaStore@@3PEAXEA; void * g_hCaStore
0x180021e6f  or      eax, 0FFFFFFFFh
0x180021e72  mov     r14d, ecx
0x180021e75  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180021e7c  xor     edi, edi
0x180021e7e  and     [rbp+cbCertEncoded], edi
0x180021e81  xor     esi, esi
0x180021e83  mov     cs:?g_ftCertExpiredTime@RdlsSecretsCache@@2U_FILETIME@@A.dwLowDateTime, eax; _FILETIME RdlsSecretsCache::g_ftCertExpiredTime ...
0x180021e89  mov     cs:?g_ftCertExpiredTime@RdlsSecretsCache@@2U_FILETIME@@A.dwHighDateTime, eax; _FILETIME RdlsSecretsCache::g_ftCertExpiredTime ...
0x180021e8f  mov     rax, [rcx]
0x180021e92  mov     [rbp+pbCertEncoded], rdi
0x180021e96  mov     rax, [rax+40h]
0x180021e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e9f  lea     r12d, [rdi+1]
0x180021ea3  mov     ebx, eax
0x180021ea5  lea     r13, ?g_szComputerName@@3PAGA; ushort near * g_szComputerName
0x180021eac  lea     ecx, [rax+3FFEFFDEh]
0x180021eb2  cmp     ecx, r12d
0x180021eb5  ja      short loc_180021F24
0x180021eb7  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180021ebe  lea     edx, [rdi+2]
0x180021ec1  mov     r8d, r12d
0x180021ec4  mov     rax, [rcx]
0x180021ec7  mov     rax, [rax+38h]
0x180021ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ed0  mov     ebx, eax
0x180021ed2  test    eax, eax
0x180021ed4  jnz     short loc_180021F1C
0x180021ed6  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180021edd  lea     r8, ?g_hCaStore@@3PEAXEA; void * g_hCaStore
0x180021ee4  mov     rdx, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; RdlsCryptHandle g_RdlsCryptProv
0x180021eeb  mov     rax, [rcx]
0x180021eee  mov     rax, [rax+40h]
0x180021ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ef7  mov     ebx, eax
0x180021ef9  test    eax, eax
0x180021efb  jnz     short loc_180021F1C
0x180021efd  mov     r8, r13
0x180021f00  lea     rdx, TLS_W_CORRUPTTRYBACKUPCERTIFICATE
0x180021f07  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180021f0e  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180021f13  lea     edx, [rdi+2]
0x180021f16  lea     r8d, [rdi+3]
0x180021f1a  jmp     short loc_180021F91
0x180021f1c  cmp     ebx, 0C0010023h
0x180021f22  jz      short loc_180021F2C
0x180021f24  cmp     ebx, 0C0010022h
0x180021f2a  jnz     short loc_180021FA4
0x180021f2c  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180021f33  mov     r8d, r12d
0x180021f36  mov     edx, 3
0x180021f3b  mov     rax, [rcx]
0x180021f3e  mov     rax, [rax+38h]
0x180021f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f47  mov     ebx, eax
0x180021f49  test    eax, eax
0x180021f4b  jnz     short loc_180021FA4
0x180021f4d  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180021f54  lea     r8, ?g_hCaStore@@3PEAXEA; void * g_hCaStore
0x180021f5b  mov     rdx, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; RdlsCryptHandle g_RdlsCryptProv
0x180021f62  mov     rax, [rcx]
0x180021f65  mov     rax, [rax+40h]
0x180021f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f6e  mov     ebx, eax
0x180021f70  test    eax, eax
0x180021f72  jnz     short loc_180021FA4
0x180021f74  mov     r8, r13
0x180021f77  lea     rdx, TLS_W_CORRUPTTRYBACKUPCERTIFICATE
0x180021f7e  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180021f85  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180021f8a  lea     edx, [rbx+3]
0x180021f8d  lea     r8d, [rbx+2]
0x180021f91  mov     rcx, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180021f98  mov     rax, [rcx]
0x180021f9b  mov     rax, [rax+38h]
0x180021f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa4  cmp     cs:?g_bIsInfoEventLogged@@3HA, esi; int g_bIsInfoEventLogged
0x180021faa  jz      short loc_180021FC8
0x180021fac  mov     r8, r13
0x180021faf  lea     rdx, TLS_W_EXPIRE_CERT
0x180021fb6  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180021fbd  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180021fc2  and     cs:?g_bIsInfoEventLogged@@3HA, esi; int g_bIsInfoEventLogged
0x180021fc8  cmp     ebx, 0C0010023h
0x180021fce  jnz     short loc_180021FE8
0x180021fd0  mov     r8, r13
0x180021fd3  lea     rdx, TLS_W_STARTUPCORRUPTEDCERT
0x180021fda  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180021fe1  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x180021fe6  jmp     short loc_180022014
0x180021fe8  call    CanIssuePermLicense
0x180021fed  test    eax, eax
0x180021fef  jnz     short loc_18002200C
0x180021ff1  cmp     r14d, r12d
0x180021ff4  jnz     short loc_18002200C
0x180021ff6  mov     r8, r13
0x180021ff9  lea     rdx, TLS_W_STARTUPNOCERT
0x180022000  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180022007  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x18002200c  test    ebx, ebx
0x18002200e  jz      loc_1800220CA
0x180022014  mov     r8, cs:Src
0x18002201b  test    r8, r8
0x18002201e  jz      short loc_18002202C
0x180022020  mov     r9d, cs:Size
0x180022027  test    r9d, r9d
0x18002202a  jnz     short loc_180022041
0x18002202c  xor     ecx, ecx
0x18002202e  call    TLSReGenerateKeys
0x180022033  mov     r8, cs:Src; unsigned __int8 *
0x18002203a  mov     r9d, cs:Size; unsigned int
0x180022041  mov     rdx, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; unsigned __int64
0x180022048  call    ?GenerateSelfSignCertificates@RdlsSecretsCache@@QEAAK_KPEAEK@Z; RdlsSecretsCache::GenerateSelfSignCertificates(unsigned __int64,uchar *,ulong)
0x18002204d  test    eax, eax
0x18002204f  jnz     loc_180022154
0x180022055  mov     rcx, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; pCertContext
0x18002205c  test    rcx, rcx
0x18002205f  jz      short loc_18002206D
0x180022061  call    cs:__imp_CertFreeCertificateContext
0x180022068  nop     dword ptr [rax+rax+00h]
0x18002206d  mov     rax, cs:?g_RdlsSecrets@@3PEAVRdlsSecretsCache@@EA; RdlsSecretsCache * g_RdlsSecrets
0x180022074  mov     ecx, r12d; dwCertEncodingType
0x180022077  mov     r8d, [rax+18h]; cbCertEncoded
0x18002207b  mov     rdx, [rax+20h]; pbCertEncoded
0x18002207f  call    cs:__imp_CertCreateCertificateContext
0x180022086  nop     dword ptr [rax+rax+00h]
0x18002208b  mov     cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const RdlsSecretsCache::g_pLicenseCertContext
0x180022092  test    rax, rax
0x180022095  jnz     short loc_1800220C7
0x180022097  xor     ebx, ebx
0x180022099  call    cs:__imp_GetLastError
0x1800220a0  nop     dword ptr [rax+rax+00h]
0x1800220a5  movups  xmm0, cs:TLS_E_SERVICEINIT
0x1800220ac  mov     r8d, eax
0x1800220af  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x1800220b3  mov     edx, 0C0110004h; unsigned int
0x1800220b8  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x1800220bd  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x1800220c2  jmp     loc_1800221B6
0x1800220c7  mov     esi, r12d
0x1800220ca  mov     rcx, cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB; pCertContext
0x1800220d1  mov     ebx, r12d
0x1800220d4  test    rcx, rcx
0x1800220d7  jz      short loc_1800220EC
0x1800220d9  call    cs:__imp_CertFreeCertificateContext
0x1800220e0  nop     dword ptr [rax+rax+00h]
0x1800220e5  and     cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB, rdi; _CERT_CONTEXT const * const g_SelfSignCertContext
0x1800220ec  test    esi, esi
0x1800220ee  jnz     short loc_180022158
0x1800220f0  mov     r9d, cs:Size
0x1800220f7  lea     rax, [rbp+pbCertEncoded]
0x1800220fb  mov     r8, cs:Src
0x180022102  lea     edx, [rsi+2]; dwKeySpec
0x180022105  mov     rcx, cs:?g_RdlsCryptProv@@3VRdlsCryptHandle@@A; hCryptProvOrNCryptKey
0x18002210c  mov     [rsp+50h+var_18], rax; __int64
0x180022111  lea     rax, [rbp+cbCertEncoded]
0x180022115  mov     [rsp+50h+var_20], rax; __int64
0x18002211a  and     [rsp+50h+var_28], rdi
0x18002211f  and     [rsp+50h+var_30], edi
0x180022123  call    TLSCreateSelfSignCertificate
0x180022128  mov     rdi, [rbp+pbCertEncoded]
0x18002212c  test    eax, eax
0x18002212e  jnz     short loc_1800221A2
0x180022130  mov     r8d, [rbp+cbCertEncoded]; cbCertEncoded
0x180022134  mov     rdx, rdi; pbCertEncoded
0x180022137  mov     ecx, r12d; dwCertEncodingType
0x18002213a  call    cs:__imp_CertCreateCertificateContext
0x180022141  nop     dword ptr [rax+rax+00h]
0x180022146  mov     cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const g_SelfSignCertContext
0x18002214d  test    rax, rax
0x180022150  jnz     short loc_1800221A2
0x180022152  jmp     short loc_180022177
0x180022154  xor     ebx, ebx
0x180022156  jmp     short loc_1800221B6
0x180022158  mov     rcx, cs:?g_pLicenseCertContext@RdlsSecretsCache@@2PEBU_CERT_CONTEXT@@EB; pCertContext
0x18002215f  call    cs:__imp_CertDuplicateCertificateContext
0x180022166  nop     dword ptr [rax+rax+00h]
0x18002216b  mov     cs:?g_SelfSignCertContext@@3PEBU_CERT_CONTEXT@@EB, rax; _CERT_CONTEXT const * const g_SelfSignCertContext
0x180022172  test    rax, rax
0x180022175  jnz     short loc_1800221B6
0x180022177  xor     ebx, ebx
0x180022179  call    cs:__imp_GetLastError
0x180022180  nop     dword ptr [rax+rax+00h]
0x180022185  movups  xmm0, cs:TLS_E_SERVICEINIT
0x18002218c  mov     r8d, eax
0x18002218f  lea     rcx, [rbp+var_10]; struct _EVENT_DESCRIPTOR
0x180022193  mov     edx, 0C0110004h; unsigned int
0x180022198  movdqu  xmmword ptr [rbp+var_10.Id], xmm0
0x18002219d  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x1800221a2  test    rdi, rdi
0x1800221a5  jz      short loc_1800221B6
0x1800221a7  mov     rcx, rdi; hMem
0x1800221aa  call    cs:__imp_LocalFree
0x1800221b1  nop     dword ptr [rax+rax+00h]
0x1800221b6  lea     r11, [rsp+50h+var_s0]
0x1800221bb  mov     eax, ebx
0x1800221bd  mov     rbx, [r11+30h]
0x1800221c1  mov     rsi, [r11+48h]
0x1800221c5  mov     rsp, r11
0x1800221c8  pop     r14
0x1800221ca  pop     r13
0x1800221cc  pop     r12
0x1800221ce  pop     rdi
0x1800221cf  pop     rbp
0x1800221d0  retn
```
