# CMachineEnroller::FixupCerts(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,int,ulong,int,int,ulong)

- ea: `0x18004f260`
- end: `0x18004f569`
- name: `?FixupCerts@CMachineEnroller@@CAJPEAUHKEY__@@PEBG1111HHKHHK@Z`
- size: `777`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, int, int, unsigned int, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004ff88`

## callees

- `0x18001aec8`
- `0x18001d724`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x1800439fc`
- `0x180044878`
- `0x18004ea54`
- `0x18004eb6c`
- `0x18004f260`
- `0x18004fc9c`
- `0x180051700`
- `0x180056764`
- `0x1800567d0`
- `0x18006fff4`
- `0x180070114`
- `0x180071fe0`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x18004f50e`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x18004f50e`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18004f398`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18004f398`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18004f2f4`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x18004f2f4`

## string_xrefs

- `0x18004f38c`: `RootCertAlreadyExisted`
- `0x18004f3f7`: `RootCertAlreadyExisted`
- `0x18004f344`: `DeleteEnterpriseClientAppContainerInstalledCert`
- `0x18004f303`: `OmaDmRegistryGetString could not find ENROLLMENT_REGISTRY_CERT_THUMB_PRINT_KEY_NAME`
- `0x18004f3e0`: `TrackCertificates(hEnrollmentKey, pszClientCertThumbprint, ENROLLMENT_REGISTRY_CERT_THUMB_PRINT_KEY_NAME, nullptr, FALSE)`
- `0x18004f3a4`: `OmaDmRegistrySetDWORD failed to set ENROLLMENT_REGISTRY_ROOT_CERT_ALREADY_EXISTED_KEY_NAME`
- `0x18004f431`: `IntermediateCertAlreadyExisted`
- `0x18004f41a`: `TrackCertificates(hEnrollmentKey, pszRootCertThumbprint, ENROLLMENT_REGISTRY_ROOT_CERT_THUMB_PRINT_KEY_NAME,ENROLLMENT_REGISTRY_ROOT_CERT_ALREADY_EXISTED_KEY_NAME, fRootCertAlreadyPresent)`
- `0x18004f454`: `TrackCertificates(hEnrollmentKey, pszIntermediateCertThumbprint, ENROLLMENT_REGISTRY_INTERMEDIATE_CERT_THUMB_PRINT_KEY_NAME,ENROLLMENT_REGISTRY_INTERMEDIATE_CERT_ALREADY_EXISTED_KEY_NAME, fIntermediateCertAlreadyPresent)`
- `0x18004f4f9`: `DeleteCertWithContainerName(szCurKC, szCurCP, fFlags)`
- `0x18004f52c`: `BindCertificateWithKeyContainer(hEnrollmentKey, pszClientCertThumbprint, fFlags, pszSID)`

## pseudocode

```c
__int64 __fastcall CMachineEnroller::FixupCerts(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7,
        int a8,
        unsigned int a9,
        int a10,
        int a11,
        unsigned int a12)
{
  int IsEnrollmentCertExpired; // edi
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // rbx
  const unsigned __int16 *v18; // rax
  int v19; // r9d
  int v20; // r8d
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  CEnrollmentLogger *Logger; // rax
  int v25[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v26[48]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v27[256]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28[256]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v25[0] = 0;
  IsEnrollmentCertExpired = CMachineEnroller::IsEnrollmentCertExpired(a4, v25);
  if ( IsEnrollmentCertExpired < 0 )
  {
    v17 = L"IsEnrollmentCertExpired";
LABEL_38:
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollFixupCertsFailed(Logger, v17, IsEnrollmentCertExpired);
    return (unsigned int)IsEnrollmentCertExpired;
  }
  if ( v25[0] )
  {
    v26[0] = 0;
    IsEnrollmentCertExpired = OmaDmRegistryGetString(a1, 0, L"DMPCertThumbPrint", v26, 0x2Au);
    if ( IsEnrollmentCertExpired == -2147024894 )
    {
      v17 = L"OmaDmRegistryGetString could not find ENROLLMENT_REGISTRY_CERT_THUMB_PRINT_KEY_NAME";
    }
    else
    {
      v18 = a4;
      do
      {
        v19 = *(const unsigned __int16 *)((char *)v18 + (char *)v26 - (char *)a4);
        v20 = *v18 - v19;
        if ( v20 )
          break;
        ++v18;
      }
      while ( v19 );
      if ( v20
        && (IsEnrollmentCertExpired = DeleteEnterpriseClientAppContainerInstalledCert(a4), IsEnrollmentCertExpired < 0) )
      {
        v17 = L"DeleteEnterpriseClientAppContainerInstalledCert";
      }
      else
      {
        v17 = &wszURI;
        IsEnrollmentCertExpired = -2146762495;
      }
    }
    goto LABEL_38;
  }
  if ( a8 )
    CommonDeleteCertificate(a1, L"DMPCertThumbPrint", 0);
  if ( a7 )
  {
    IsEnrollmentCertExpired = OmaDmRegistrySetDWORD(a1, 0, L"RootCertAlreadyExisted", a12);
    if ( IsEnrollmentCertExpired < 0 )
    {
      v17 = L"OmaDmRegistrySetDWORD failed to set ENROLLMENT_REGISTRY_ROOT_CERT_ALREADY_EXISTED_KEY_NAME";
      goto LABEL_38;
    }
    CMachineEnroller::DeleteEnrollmentCertificateFromAccountStores(a1);
  }
  if ( a4 )
  {
    IsEnrollmentCertExpired = CMachineEnroller::TrackCertificates(a1, a4, L"DMPCertThumbPrint", 0, 0);
    if ( IsEnrollmentCertExpired < 0 )
    {
      v17 = L"TrackCertificates(hEnrollmentKey, pszClientCertThumbprint, ENROLLMENT_REGISTRY_CERT_THUMB_PRINT_KEY_NAME, nullptr, FALSE)";
      goto LABEL_38;
    }
  }
  if ( a5 )
  {
    IsEnrollmentCertExpired = CMachineEnroller::TrackCertificates(
                                a1,
                                a5,
                                L"RootCertThumbPrint",
                                L"RootCertAlreadyExisted",
                                a10);
    if ( IsEnrollmentCertExpired < 0 )
    {
      v17 = L"TrackCertificates(hEnrollmentKey, pszRootCertThumbprint, ENROLLMENT_REGISTRY_ROOT_CERT_THUMB_PRINT_KEY_NAME,"
             "ENROLLMENT_REGISTRY_ROOT_CERT_ALREADY_EXISTED_KEY_NAME, fRootCertAlreadyPresent)";
      goto LABEL_38;
    }
  }
  if ( a6 )
  {
    IsEnrollmentCertExpired = CMachineEnroller::TrackCertificates(
                                a1,
                                a6,
                                L"IntermediateCertThumbPrint",
                                L"IntermediateCertAlreadyExisted",
                                a11);
    if ( IsEnrollmentCertExpired < 0 )
    {
      v17 = L"TrackCertificates(hEnrollmentKey, pszIntermediateCertThumbprint, ENROLLMENT_REGISTRY_INTERMEDIATE_CERT_THUMB"
             "_PRINT_KEY_NAME,ENROLLMENT_REGISTRY_INTERMEDIATE_CERT_ALREADY_EXISTED_KEY_NAME, fIntermediateCertAlreadyPresent)";
      goto LABEL_38;
    }
  }
  if ( a7 )
  {
    memset_0(v28, 0, sizeof(v28));
    memset_0(v27, 0, sizeof(v27));
    IsEnrollmentCertExpired = GetCurKeyContainer(a1, v28, v21);
    if ( IsEnrollmentCertExpired < 0 )
    {
      v17 = L"GetCurKeyContainer(hEnrollmentKey, szCurKC, MAX_KEYCONTAINER_OR_CRYPTO_PROVIDER_LENGTH)";
      goto LABEL_38;
    }
    IsEnrollmentCertExpired = GetCryptoProvider(a1, 1, v27, v22);
    if ( IsEnrollmentCertExpired < 0 )
    {
      v17 = L"GetCryptoProvider(hEnrollmentKey, true, szCurCP, MAX_KEYCONTAINER_OR_CRYPTO_PROVIDER_LENGTH)";
      goto LABEL_38;
    }
    ImpersonateForCertAccess(a2);
    IsEnrollmentCertExpired = CMachineEnroller::DeleteCertWithContainerName(v28, v27, a9);
    RevertToSelfFromCertAccess();
    if ( IsEnrollmentCertExpired < 0 )
    {
      v17 = L"DeleteCertWithContainerName(szCurKC, szCurCP, fFlags)";
      goto LABEL_38;
    }
    OmaDmRegistryDeleteValue(a1, 0, L"SslCertStore");
  }
  IsEnrollmentCertExpired = CMachineEnroller::BindCertificateWithKeyContainer(a1, a4, a9, v16);
  if ( IsEnrollmentCertExpired < 0 )
  {
    v17 = L"BindCertificateWithKeyContainer(hEnrollmentKey, pszClientCertThumbprint, fFlags, pszSID)";
    goto LABEL_38;
  }
  return (unsigned int)IsEnrollmentCertExpired;
}

```

## disassembly

```asm
0x18004f260  push    rbp
0x18004f262  push    rbx
0x18004f263  push    rsi
0x18004f264  push    rdi
0x18004f265  push    r12
0x18004f267  push    r13
0x18004f269  push    r15
0x18004f26b  lea     rbp, [rsp-3B0h]
0x18004f273  sub     rsp, 4B0h
0x18004f27a  mov     rax, cs:__security_cookie
0x18004f281  xor     rax, rsp
0x18004f284  mov     [rbp+3E0h+var_40], rax
0x18004f28b  mov     r12, [rbp+3E0h+arg_20]
0x18004f292  mov     r13, rdx
0x18004f295  mov     r15, [rbp+3E0h+arg_28]
0x18004f29c  lea     rdx, [rsp+4E0h+var_4B0]; int *
0x18004f2a1  mov     rbx, rcx
0x18004f2a4  mov     [rsp+4E0h+var_4B0], 0
0x18004f2ac  mov     rcx, r9; unsigned __int16 *
0x18004f2af  mov     rsi, r9
0x18004f2b2  call    ?IsEnrollmentCertExpired@CMachineEnroller@@CAJPEBGPEAH@Z; CMachineEnroller::IsEnrollmentCertExpired(ushort const *,int *)
0x18004f2b7  mov     edi, eax
0x18004f2b9  test    eax, eax
0x18004f2bb  jns     short loc_18004F2C9
0x18004f2bd  lea     rbx, aIsenrollmentce; "IsEnrollmentCertExpired"
0x18004f2c4  jmp     loc_18004F533
0x18004f2c9  cmp     [rsp+4E0h+var_4B0], 0
0x18004f2ce  jz      loc_18004F361
0x18004f2d4  xor     eax, eax
0x18004f2d6  mov     [rsp+4E0h+var_4C0], 2Ah ; '*'
0x18004f2de  lea     r9, [rsp+4E0h+var_4A0]
0x18004f2e3  mov     [rsp+4E0h+var_4A0], ax
0x18004f2e8  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x18004f2ef  xor     edx, edx
0x18004f2f1  mov     rcx, rbx
0x18004f2f4  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x18004f2fa  mov     edi, eax
0x18004f2fc  cmp     eax, 80070002h
0x18004f301  jnz     short loc_18004F30F
0x18004f303  lea     rbx, aOmadmregistryg_2; "OmaDmRegistryGetString could not find E"...
0x18004f30a  jmp     loc_18004F533
0x18004f30f  lea     rdx, [rsp+4E0h+var_4A0]
0x18004f314  mov     rax, rsi
0x18004f317  sub     rdx, rsi
0x18004f31a  movzx   r8d, word ptr [rax]
0x18004f31e  movzx   r9d, word ptr [rax+rdx]
0x18004f323  sub     r8d, r9d
0x18004f326  jnz     short loc_18004F331
0x18004f328  add     rax, 2
0x18004f32c  test    r9d, r9d
0x18004f32f  jnz     short loc_18004F31A
0x18004f331  test    r8d, r8d
0x18004f334  jz      short loc_18004F350
0x18004f336  mov     rcx, rsi; unsigned __int16 *
0x18004f339  call    ?DeleteEnterpriseClientAppContainerInstalledCert@@YAJPEBG@Z; DeleteEnterpriseClientAppContainerInstalledCert(ushort const *)
0x18004f33e  mov     edi, eax
0x18004f340  test    eax, eax
0x18004f342  jns     short loc_18004F350
0x18004f344  lea     rbx, aDeleteenterpri_0; "DeleteEnterpriseClientAppContainerInsta"...
0x18004f34b  jmp     loc_18004F533
0x18004f350  lea     rbx, wszURI
0x18004f357  mov     edi, 800B0101h
0x18004f35c  jmp     loc_18004F533
0x18004f361  cmp     [rbp+3E0h+arg_38], 0
0x18004f368  jz      short loc_18004F37C
0x18004f36a  xor     r8d, r8d; int
0x18004f36d  lea     rdx, aDmpcertthumbpr; "DMPCertThumbPrint"
0x18004f374  mov     rcx, rbx; HKEY
0x18004f377  call    ?CommonDeleteCertificate@@YAJPEAUHKEY__@@PEBGH@Z; CommonDeleteCertificate(HKEY__ *,ushort const *,int)
0x18004f37c  cmp     [rbp+3E0h+arg_30], 0
0x18004f383  jz      short loc_18004F3B8
0x18004f385  mov     r9d, [rbp+3E0h+arg_58]
0x18004f38c  lea     r8, aRootcertalread; "RootCertAlreadyExisted"
0x18004f393  xor     edx, edx
0x18004f395  mov     rcx, rbx
0x18004f398  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18004f39e  mov     edi, eax
0x18004f3a0  test    eax, eax
0x18004f3a2  jns     short loc_18004F3B0
0x18004f3a4  lea     rbx, aOmadmregistrys_1; "OmaDmRegistrySetDWORD failed to set ENR"...
0x18004f3ab  jmp     loc_18004F533
0x18004f3b0  mov     rcx, rbx; HKEY
0x18004f3b3  call    ?DeleteEnrollmentCertificateFromAccountStores@CMachineEnroller@@CAJPEAUHKEY__@@@Z; CMachineEnroller::DeleteEnrollmentCertificateFromAccountStores(HKEY__ *)
0x18004f3b8  test    rsi, rsi
0x18004f3bb  jz      short loc_18004F3EC
0x18004f3bd  xor     r9d, r9d; unsigned __int16 *
0x18004f3c0  mov     [rsp+4E0h+var_4C0], 0; int
0x18004f3c8  lea     r8, aDmpcertthumbpr; "DMPCertThumbPrint"
0x18004f3cf  mov     rdx, rsi; unsigned __int16 *
0x18004f3d2  mov     rcx, rbx; HKEY
0x18004f3d5  call    ?TrackCertificates@CMachineEnroller@@CAJPEAUHKEY__@@PEBG11H@Z; CMachineEnroller::TrackCertificates(HKEY__ *,ushort const *,ushort const *,ushort const *,int)
0x18004f3da  mov     edi, eax
0x18004f3dc  test    eax, eax
0x18004f3de  jns     short loc_18004F3EC
0x18004f3e0  lea     rbx, aTrackcertifica; "TrackCertificates(hEnrollmentKey, pszCl"...
0x18004f3e7  jmp     loc_18004F533
0x18004f3ec  test    r12, r12
0x18004f3ef  jz      short loc_18004F426
0x18004f3f1  mov     eax, [rbp+3E0h+arg_48]
0x18004f3f7  lea     r9, aRootcertalread; "RootCertAlreadyExisted"
0x18004f3fe  lea     r8, aRootcertthumbp; "RootCertThumbPrint"
0x18004f405  mov     [rsp+4E0h+var_4C0], eax; int
0x18004f409  mov     rdx, r12; unsigned __int16 *
0x18004f40c  mov     rcx, rbx; HKEY
0x18004f40f  call    ?TrackCertificates@CMachineEnroller@@CAJPEAUHKEY__@@PEBG11H@Z; CMachineEnroller::TrackCertificates(HKEY__ *,ushort const *,ushort const *,ushort const *,int)
0x18004f414  mov     edi, eax
0x18004f416  test    eax, eax
0x18004f418  jns     short loc_18004F426
0x18004f41a  lea     rbx, aTrackcertifica_1; "TrackCertificates(hEnrollmentKey, pszRo"...
0x18004f421  jmp     loc_18004F533
0x18004f426  test    r15, r15
0x18004f429  jz      short loc_18004F460
0x18004f42b  mov     eax, [rbp+3E0h+arg_50]
0x18004f431  lea     r9, aIntermediatece; "IntermediateCertAlreadyExisted"
0x18004f438  lea     r8, aIntermediatece_0; "IntermediateCertThumbPrint"
0x18004f43f  mov     [rsp+4E0h+var_4C0], eax; int
0x18004f443  mov     rdx, r15; unsigned __int16 *
0x18004f446  mov     rcx, rbx; HKEY
0x18004f449  call    ?TrackCertificates@CMachineEnroller@@CAJPEAUHKEY__@@PEBG11H@Z; CMachineEnroller::TrackCertificates(HKEY__ *,ushort const *,ushort const *,ushort const *,int)
0x18004f44e  mov     edi, eax
0x18004f450  test    eax, eax
0x18004f452  jns     short loc_18004F460
0x18004f454  lea     rbx, aTrackcertifica_0; "TrackCertificates(hEnrollmentKey, pszIn"...
0x18004f45b  jmp     loc_18004F533
0x18004f460  cmp     [rbp+3E0h+arg_30], 0
0x18004f467  jz      loc_18004F514
0x18004f46d  mov     edi, 200h
0x18004f472  lea     rcx, [rbp+3E0h+var_240]; void *
0x18004f479  mov     r8d, edi; Size
0x18004f47c  xor     edx, edx; Val
0x18004f47e  call    memset_0
0x18004f483  mov     r8d, edi; Size
0x18004f486  lea     rcx, [rbp+3E0h+var_440]; void *
0x18004f48a  xor     edx, edx; Val
0x18004f48c  call    memset_0
0x18004f491  lea     rdx, [rbp+3E0h+var_240]; unsigned __int16 *
0x18004f498  mov     rcx, rbx; HKEY
0x18004f49b  call    ?GetCurKeyContainer@@YAJPEAUHKEY__@@PEAGK@Z; GetCurKeyContainer(HKEY__ *,ushort *,ulong)
0x18004f4a0  mov     edi, eax
0x18004f4a2  test    eax, eax
0x18004f4a4  jns     short loc_18004F4B2
0x18004f4a6  lea     rbx, aGetcurkeyconta_0; "GetCurKeyContainer(hEnrollmentKey, szCu"...
0x18004f4ad  jmp     loc_18004F533
0x18004f4b2  lea     r8, [rbp+3E0h+var_440]; unsigned __int16 *
0x18004f4b6  mov     dl, 1; bool
0x18004f4b8  mov     rcx, rbx; HKEY
0x18004f4bb  call    ?GetCryptoProvider@@YAJPEAUHKEY__@@_NPEAGK@Z; GetCryptoProvider(HKEY__ *,bool,ushort *,ulong)
0x18004f4c0  mov     edi, eax
0x18004f4c2  test    eax, eax
0x18004f4c4  jns     short loc_18004F4CF
0x18004f4c6  lea     rbx, aGetcryptoprovi; "GetCryptoProvider(hEnrollmentKey, true,"...
0x18004f4cd  jmp     short loc_18004F533
0x18004f4cf  mov     rcx, r13; unsigned __int16 *
0x18004f4d2  call    ?ImpersonateForCertAccess@@YAJPEBG@Z; ImpersonateForCertAccess(ushort const *)
0x18004f4d7  mov     r8d, [rbp+3E0h+arg_40]; unsigned int
0x18004f4de  lea     rdx, [rbp+3E0h+var_440]; unsigned __int16 *
0x18004f4e2  lea     rcx, [rbp+3E0h+var_240]; unsigned __int16 *
0x18004f4e9  call    ?DeleteCertWithContainerName@CMachineEnroller@@CAJPEBG0K@Z; CMachineEnroller::DeleteCertWithContainerName(ushort const *,ushort const *,ulong)
0x18004f4ee  mov     edi, eax
0x18004f4f0  call    ?RevertToSelfFromCertAccess@@YAXXZ; RevertToSelfFromCertAccess(void)
0x18004f4f5  test    edi, edi
0x18004f4f7  jns     short loc_18004F502
0x18004f4f9  lea     rbx, aDeletecertwith; "DeleteCertWithContainerName(szCurKC, sz"...
0x18004f500  jmp     short loc_18004F533
0x18004f502  lea     r8, aSslcertstore; "SslCertStore"
0x18004f509  xor     edx, edx
0x18004f50b  mov     rcx, rbx
0x18004f50e  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x18004f514  mov     r8d, [rbp+3E0h+arg_40]; unsigned int
0x18004f51b  mov     rdx, rsi; unsigned __int16 *
0x18004f51e  mov     rcx, rbx; HKEY
0x18004f521  call    ?BindCertificateWithKeyContainer@CMachineEnroller@@CAJPEAUHKEY__@@PEBGK1@Z; CMachineEnroller::BindCertificateWithKeyContainer(HKEY__ *,ushort const *,ulong,ushort const *)
0x18004f526  mov     edi, eax
0x18004f528  test    eax, eax
0x18004f52a  jns     short loc_18004F546
0x18004f52c  lea     rbx, aBindcertificat_1; "BindCertificateWithKeyContainer(hEnroll"...
0x18004f533  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18004f538  mov     r8d, edi; int
0x18004f53b  mov     rdx, rbx; unsigned __int16 *
0x18004f53e  mov     rcx, rax; this
0x18004f541  call    ?LogEnrollFixupCertsFailed@CEnrollmentLogger@@QEAAXPEBGJ@Z; CEnrollmentLogger::LogEnrollFixupCertsFailed(ushort const *,long)
0x18004f546  mov     eax, edi
0x18004f548  mov     rcx, [rbp+3E0h+var_40]
0x18004f54f  xor     rcx, rsp; StackCookie
0x18004f552  call    __security_check_cookie
0x18004f557  add     rsp, 4B0h
0x18004f55e  pop     r15
0x18004f560  pop     r13
0x18004f562  pop     r12
0x18004f564  pop     rdi
0x18004f565  pop     rsi
0x18004f566  pop     rbx
0x18004f567  pop     rbp
0x18004f568  retn
```
