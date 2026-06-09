# InternalActivate(uint,ushort *,ushort *,ushort *,void *,long (*)(_DRM_STATUS_MSG,long,void *,void *),void *,ushort * *,ushort * *,_DRM_STATUS_MSG *,ushort * *)

- ea: `0x18002cb38`
- end: `0x18002d03c`
- name: `?InternalActivate@@YAJIPEAG00PEAXP6AJW4_DRM_STATUS_MSG@@J11@Z1PEAPEAG4PEAW41@4@Z`
- size: `1284`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, HANDLE hHandle, int (*)(enum _DRM_STATUS_MSG, int, void *, void *), void *, unsigned __int16 **, unsigned __int16 **, enum _DRM_STATUS_MSG *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002d6a0`
- `0x18002e5e0`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180017210`
- `0x180018b74`
- `0x18002c390`
- `0x18002cb38`
- `0x180031764`
- `0x180037bc0`
- `0x180037e18`
- `0x180037e58`
- `0x180040220`
- `0x18004033c`
- `0x180040648`
- `0x18004bfb4`
- `0x18005bd8a`

## string_xrefs

- `0x18002cbd7`: `https://certification.drm.microsoft.com/certification`
- `0x18002cc83`: `https://certification.drm.microsoft.com/certification`

## pseudocode

```c
__int64 __fastcall InternalActivate(
        unsigned int a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        HANDLE hHandle,
        int (*a6)(enum _DRM_STATUS_MSG, int, void *, void *),
        void *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9,
        enum _DRM_STATUS_MSG *a10,
        unsigned __int16 **a11)
{
  unsigned __int16 *v11; // rsi
  unsigned __int16 *v13; // r15
  wchar_t *v14; // r12
  CDRMLicense *v15; // r14
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  int FileNameWithSystemPath; // ebx
  unsigned __int64 v19; // rdx
  signed __int64 v20; // rbx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  unsigned int v24; // esi
  const unsigned __int16 *v25; // r13
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int64 v28; // rbx
  unsigned __int16 *v29; // rax
  CDRMLicense *v30; // rax
  const struct _DRM_CRYPTO_VERSION_PARAMETERS *v31; // rax
  int v32; // ecx
  unsigned int ClientHierarchy; // eax
  unsigned __int16 **v34; // r8
  const unsigned __int16 *const near *const *v35; // rcx
  const unsigned __int16 *v36; // rdx
  WCHAR *v37; // rsi
  const unsigned __int16 *v38; // rdx
  unsigned __int16 *v39; // r8
  unsigned __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // ecx
  void *Block; // [rsp+60h] [rbp-78h] BYREF
  unsigned __int16 *v45; // [rsp+68h] [rbp-70h]
  unsigned __int16 *v46; // [rsp+70h] [rbp-68h] BYREF
  unsigned __int16 *v47; // [rsp+78h] [rbp-60h]
  unsigned __int64 v48; // [rsp+88h] [rbp-50h]
  __int64 v49; // [rsp+90h] [rbp-48h]

  v49 = -2;
  v11 = a4;
  v13 = 0;
  v45 = 0;
  v14 = 0;
  v47 = 0;
  v46 = 0;
  v15 = 0;
  LODWORD(Block) = 0;
  if ( (a1 & 1) != 0 )
  {
    Block = 0;
    ClientHierarchy = GetClientHierarchy();
    v35 = &g_wszRMActivateExe_Server_Names;
    if ( !g_fGlobalOptionUseServerProc )
      v35 = &g_wszRMActivateExe_DeskTop_Names;
    FileNameWithSystemPath = DRMOS::GetFileNameWithSystemPath(
                               (DRMOS *)v35[ClientHierarchy],
                               (const unsigned __int16 *)&Block,
                               v34);
    v37 = (WCHAR *)Block;
    if ( FileNameWithSystemPath >= 0 )
    {
      if ( DRMOS::GetFileAttributesA((LPCWSTR)Block, v36) == -1 )
      {
        FileNameWithSystemPath = -2147168435;
      }
      else
      {
        FileNameWithSystemPath = DRMOS::DoProcess(v37, v38, v39, hHandle);
        _RTLTRACE("[msdrm]:RMActivate.exe HR = %x\n", FileNameWithSystemPath);
        if ( FileNameWithSystemPath < 0 )
        {
          v40 = (unsigned int)(FileNameWithSystemPath + 2147168447);
          if ( (unsigned int)v40 > 0x38 || (v41 = 0x100000000001001LL, !_bittest64(&v41, v40)) )
            FileNameWithSystemPath = -2147168448;
        }
      }
    }
    operator delete(v37);
    if ( FileNameWithSystemPath < 0 )
      goto LABEL_34;
    goto LABEL_54;
  }
  *a10 = DRM_MSG_ACTIVATE_GROUPIDENTITY;
  _RTLTRACE("[msdrm]:wszServer = %S ,wszUserID = %S,wszUserType = %S ", a4, a2, a3);
  if ( v11 )
  {
LABEL_18:
    v25 = L"/ServerCertification.asmx";
    if ( !g_fGlobalOptionUseServerProc )
      v25 = L"/Certification.asmx";
    v26 = -1;
    do
      ++v26;
    while ( v11[v26] );
    v27 = -1;
    do
      ++v27;
    while ( v25[v27] );
    v28 = v27 + v26 + 1;
    v48 = v28;
    v29 = (unsigned __int16 *)operator new[](saturated_mul(v28, 2u));
    v13 = v29;
    v45 = v29;
    if ( !v29 )
      goto LABEL_25;
    FileNameWithSystemPath = StringCchCopyW(v29, v28, v11);
    if ( FileNameWithSystemPath < 0 )
      goto LABEL_34;
    FileNameWithSystemPath = StringCchCatW(v13, v48, v25);
    if ( FileNameWithSystemPath < 0 )
      goto LABEL_34;
    if ( (a1 & 2) != 0 )
    {
      FileNameWithSystemPath = GetLicensorCert(v11, &v46);
      if ( FileNameWithSystemPath < 0 )
        goto LABEL_34;
      v30 = (CDRMLicense *)operator new(0x28u);
      v15 = v30;
      v48 = (unsigned __int64)v30;
      if ( !v30 )
      {
        v15 = 0;
LABEL_25:
        FileNameWithSystemPath = -2147024882;
        goto LABEL_17;
      }
      *((_QWORD *)v30 + 1) = 0;
      *((_DWORD *)v30 + 4) = 0;
      *((_QWORD *)v30 + 3) = 0;
      *((_DWORD *)v30 + 1) = 1;
      FileNameWithSystemPath = CDRMLicense::ParseLicense(v30, v46);
      if ( FileNameWithSystemPath < 0
        || (FileNameWithSystemPath = CDRMLicense::VerifySignature(v15, (unsigned int *)&Block),
            FileNameWithSystemPath < 0)
        || (v31 = UDGetCryptoVersion((unsigned int)Block),
            FileNameWithSystemPath = CertifyGroupIdentity(v31, a1, v13, a2, a3, hHandle, a6, a7, a8, a9, a11),
            FileNameWithSystemPath < 0) )
      {
LABEL_34:
        if ( FileNameWithSystemPath > -2147168304 )
        {
          if ( FileNameWithSystemPath == -2147168300 )
          {
            v24 = -2147168444;
            goto LABEL_63;
          }
          if ( FileNameWithSystemPath == -2147024882 || FileNameWithSystemPath == -2147024809 )
            goto LABEL_17;
        }
        else
        {
          v24 = -2147168441;
          if ( FileNameWithSystemPath == -2147168304 )
            goto LABEL_63;
          if ( FileNameWithSystemPath > -2147168441 )
          {
            if ( (unsigned int)(FileNameWithSystemPath + 2147168438) <= 0x15 )
            {
              v42 = 3080207;
              if ( _bittest(&v42, FileNameWithSystemPath + 2147168438) )
                goto LABEL_17;
            }
          }
          else
          {
            if ( FileNameWithSystemPath == -2147168441 )
              goto LABEL_63;
            if ( (unsigned int)(FileNameWithSystemPath + 2147168453) <= 8 )
            {
              v32 = 461;
              if ( _bittest(&v32, FileNameWithSystemPath + 2147168453) )
                goto LABEL_17;
            }
            v24 = -2147168444;
            if ( FileNameWithSystemPath == -2147168444 )
              goto LABEL_63;
            if ( (unsigned int)(FileNameWithSystemPath + 2147168443) <= 1 )
              goto LABEL_17;
          }
        }
        v24 = -2147168448;
        goto LABEL_63;
      }
    }
LABEL_54:
    v24 = 315140;
    goto LABEL_64;
  }
  if ( wcscmp_0(a3, L"PassportAuthProvider") )
  {
    FileNameWithSystemPath = -2147024809;
    goto LABEL_17;
  }
  v16 = 0x7FFFFFFF;
  v17 = L"https://certification.drm.microsoft.com/certification";
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  FileNameWithSystemPath = v16 == 0 ? 0x80070057 : 0;
  v19 = (0x7FFFFFFF - v16) & ((unsigned __int128)-(__int128)(unsigned __int64)v16 >> 64);
  if ( !v16 )
    goto LABEL_34;
  v20 = v19 + 1;
  if ( v19 + 1 < v19 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  if ( v20 < 0 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  v21 = 2LL * (unsigned int)v20;
  v22 = HIDWORD(v20) << 33;
  if ( v22 + v21 < v21 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  if ( !(v22 + v21) )
  {
LABEL_15:
    v11 = v14;
    _RTLTRACE("[msdrm]: wszServerURL = %S ", v14);
    goto LABEL_18;
  }
  v23 = (unsigned __int16 *)operator new[](saturated_mul(v20, 2u));
  v14 = v23;
  v47 = v23;
  if ( v23 )
  {
    FileNameWithSystemPath = StringCchCopyW(v23, v20, L"https://certification.drm.microsoft.com/certification");
    if ( FileNameWithSystemPath < 0 )
      goto LABEL_34;
    goto LABEL_15;
  }
  FileNameWithSystemPath = -2147024882;
LABEL_17:
  v24 = FileNameWithSystemPath;
LABEL_63:
  v13 = v45;
LABEL_64:
  operator delete(v46);
  operator delete(v14);
  operator delete(v13);
  if ( v15 )
    CDRMLicense::Release(v15);
  return v24;
}

```

## disassembly

```asm
0x18002cb38  mov     rax, rsp
0x18002cb3b  mov     [rax+18h], r8
0x18002cb3f  mov     [rax+10h], rdx
0x18002cb43  mov     [rax+8], ecx
0x18002cb46  push    rbx
0x18002cb47  push    rsi
0x18002cb48  push    rdi
0x18002cb49  push    r12
0x18002cb4b  push    r13
0x18002cb4d  push    r14
0x18002cb4f  push    r15
0x18002cb51  sub     rsp, 0A0h
0x18002cb58  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18002cb60  mov     rsi, r9
0x18002cb63  mov     rbx, r8
0x18002cb66  xor     edi, edi
0x18002cb68  mov     r15d, edi
0x18002cb6b  mov     [rsp+0D8h+var_70], rdi
0x18002cb70  mov     r12d, edi
0x18002cb73  mov     [rsp+0D8h+var_60], rdi
0x18002cb78  mov     [rax-68h], rdi
0x18002cb7c  mov     r14d, edi
0x18002cb7f  mov     [rax-78h], edi
0x18002cb82  test    cl, 1
0x18002cb85  jnz     loc_18002CEF6
0x18002cb8b  mov     rax, [rsp+0D8h+arg_48]
0x18002cb93  mov     dword ptr [rax], 1
0x18002cb99  mov     r9, rbx
0x18002cb9c  mov     r8, rdx
0x18002cb9f  mov     rdx, rsi
0x18002cba2  lea     rcx, aMsdrmWszserver_0; "[msdrm]:wszServer = %S ,wszUserID = %S,"...
0x18002cba9  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002cbae  test    rsi, rsi
0x18002cbb1  jnz     loc_18002CCD8
0x18002cbb7  lea     rdx, aPassportauthpr; "PassportAuthProvider"
0x18002cbbe  mov     rcx, rbx; String1
0x18002cbc1  call    wcscmp_0
0x18002cbc6  test    eax, eax
0x18002cbc8  jnz     loc_18002CCCC
0x18002cbce  mov     r8d, 7FFFFFFFh
0x18002cbd4  mov     ecx, r8d
0x18002cbd7  lea     rax, ?g_wszCloudCertificationServerUrl@@3QBGB; "https://certification.drm.microsoft.com"...
0x18002cbde  cmp     [rax], di
0x18002cbe1  jz      short loc_18002CBED
0x18002cbe3  add     rax, 2
0x18002cbe7  sub     rcx, 1
0x18002cbeb  jnz     short loc_18002CBDE
0x18002cbed  mov     rax, rcx
0x18002cbf0  neg     rax
0x18002cbf3  sbb     ebx, ebx
0x18002cbf5  not     ebx
0x18002cbf7  and     ebx, 80070057h
0x18002cbfd  mov     rax, rcx
0x18002cc00  sub     r8, rcx
0x18002cc03  neg     rax
0x18002cc06  sbb     rdx, rdx
0x18002cc09  and     rdx, r8
0x18002cc0c  test    rcx, rcx
0x18002cc0f  jnz     short loc_18002CC16
0x18002cc11  jmp     loc_18002CE8E
0x18002cc16  lea     rbx, [rdx+1]
0x18002cc1a  cmp     rbx, rdx
0x18002cc1d  jb      loc_18002D02A
0x18002cc23  mov     rcx, rbx
0x18002cc26  shr     rcx, 20h
0x18002cc2a  mov     rax, rcx
0x18002cc2d  shr     rax, 1Fh
0x18002cc31  test    eax, eax
0x18002cc33  jnz     loc_18002D030
0x18002cc39  mov     eax, ebx
0x18002cc3b  add     rax, rax
0x18002cc3e  shl     rcx, 21h
0x18002cc42  lea     rdx, [rcx+rax]
0x18002cc46  cmp     rdx, rax
0x18002cc49  jb      loc_18002D035
0x18002cc4f  test    rdx, rdx
0x18002cc52  jz      short loc_18002CCA0
0x18002cc54  mov     eax, 2
0x18002cc59  mul     rbx
0x18002cc5c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18002cc63  cmovb   rax, r15
0x18002cc67  mov     rcx, rax; unsigned __int64
0x18002cc6a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002cc6f  mov     r12, rax
0x18002cc72  mov     [rsp+0D8h+var_60], rax
0x18002cc77  test    rax, rax
0x18002cc7a  jnz     short loc_18002CC83
0x18002cc7c  mov     ebx, 8007000Eh
0x18002cc81  jmp     short loc_18002CCD1
0x18002cc83  lea     r8, ?g_wszCloudCertificationServerUrl@@3QBGB; "https://certification.drm.microsoft.com"...
0x18002cc8a  mov     rdx, rbx; unsigned __int64
0x18002cc8d  mov     rcx, rax; unsigned __int16 *
0x18002cc90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cc95  mov     ebx, eax
0x18002cc97  test    eax, eax
0x18002cc99  jns     short loc_18002CCA4
0x18002cc9b  jmp     loc_18002CE8E
0x18002cca0  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002cca4  mov     rsi, r12
0x18002cca7  mov     rdx, r12
0x18002ccaa  lea     rcx, aMsdrmWszserver; "[msdrm]: wszServerURL = %S "
0x18002ccb1  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002ccb6  jmp     short loc_18002CCDC
0x18002ccb8  xor     edi, edi
0x18002ccba  mov     [rsp+0D8h+var_70], rdi
0x18002ccbf  mov     r12, [rsp+0D8h+var_60]
0x18002ccc4  mov     r14d, edi
0x18002ccc7  jmp     loc_18002CFDD
0x18002cccc  mov     ebx, 80070057h
0x18002ccd1  mov     esi, ebx
0x18002ccd3  jmp     loc_18002CFE9
0x18002ccd8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002ccdc  lea     r13, ?g_wszACT_ServerCertificationPadding@@3QBGB; "/ServerCertification.asmx"
0x18002cce3  lea     rax, ?g_wszACT_CertificationPadding@@3QBGB; "/Certification.asmx"
0x18002ccea  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, edi; int g_fGlobalOptionUseServerProc
0x18002ccf0  cmovz   r13, rax
0x18002ccf4  mov     rcx, r15
0x18002ccf7  inc     rcx
0x18002ccfa  cmp     [rsi+rcx*2], di
0x18002ccfe  jnz     short loc_18002CCF7
0x18002cd00  mov     rax, r15
0x18002cd03  inc     rax
0x18002cd06  cmp     [r13+rax*2+0], di
0x18002cd0c  jnz     short loc_18002CD03
0x18002cd0e  lea     rbx, [rcx+1]
0x18002cd12  add     rbx, rax
0x18002cd15  mov     [rsp+0D8h+var_50], rbx
0x18002cd1d  mov     eax, 2
0x18002cd22  mul     rbx
0x18002cd25  cmovb   rax, r15
0x18002cd29  mov     rcx, rax; unsigned __int64
0x18002cd2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002cd31  mov     r15, rax
0x18002cd34  mov     [rsp+0D8h+var_70], rax
0x18002cd39  test    rax, rax
0x18002cd3c  jnz     short loc_18002CD45
0x18002cd3e  mov     ebx, 8007000Eh
0x18002cd43  jmp     short loc_18002CCD1
0x18002cd45  mov     r8, rsi; unsigned __int16 *
0x18002cd48  mov     rdx, rbx; unsigned __int64
0x18002cd4b  mov     rcx, r15; unsigned __int16 *
0x18002cd4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cd53  mov     ebx, eax
0x18002cd55  test    eax, eax
0x18002cd57  js      loc_18002CE8E
0x18002cd5d  mov     r8, r13; unsigned __int16 *
0x18002cd60  mov     rdx, [rsp+0D8h+var_50]; unsigned __int64
0x18002cd68  mov     rcx, r15; unsigned __int16 *
0x18002cd6b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002cd70  mov     ebx, eax
0x18002cd72  test    eax, eax
0x18002cd74  js      loc_18002CE8E
0x18002cd7a  mov     r13d, [rsp+0D8h+arg_0]
0x18002cd82  test    r13b, 2
0x18002cd86  jz      loc_18002CF9B
0x18002cd8c  lea     rdx, [rsp+0D8h+var_68]; unsigned __int16 **
0x18002cd91  mov     rcx, rsi; unsigned __int16 *
0x18002cd94  call    ?GetLicensorCert@@YAJPEAGPEAPEAG@Z; GetLicensorCert(ushort *,ushort * *)
0x18002cd99  mov     ebx, eax
0x18002cd9b  test    eax, eax
0x18002cd9d  js      loc_18002CE8E
0x18002cda3  mov     ecx, 28h ; '('; Size
0x18002cda8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cdad  mov     r14, rax
0x18002cdb0  mov     [rsp+0D8h+var_50], rax
0x18002cdb8  test    rax, rax
0x18002cdbb  jz      loc_18002CEEE
0x18002cdc1  mov     [rax+8], rdi
0x18002cdc5  mov     [rax+10h], edi
0x18002cdc8  mov     [rax+18h], rdi
0x18002cdcc  mov     dword ptr [rax+4], 1
0x18002cdd3  test    rax, rax
0x18002cdd6  jz      loc_18002CD3E
0x18002cddc  mov     rdx, [rsp+0D8h+var_68]; unsigned __int16 *
0x18002cde1  mov     rcx, rax; this
0x18002cde4  call    ?ParseLicense@CDRMLicense@@QEAAJPEBG@Z; CDRMLicense::ParseLicense(ushort const *)
0x18002cde9  mov     ebx, eax
0x18002cdeb  test    eax, eax
0x18002cded  js      loc_18002CE8E
0x18002cdf3  lea     rdx, [rsp+0D8h+Block]; unsigned int *
0x18002cdf8  mov     rcx, r14; this
0x18002cdfb  call    ?VerifySignature@CDRMLicense@@QEAAJPEAK@Z; CDRMLicense::VerifySignature(ulong *)
0x18002ce00  mov     ebx, eax
0x18002ce02  test    eax, eax
0x18002ce04  js      loc_18002CE8E
0x18002ce0a  mov     ecx, dword ptr [rsp+0D8h+Block]; unsigned int
0x18002ce0e  call    ?UDGetCryptoVersion@@YAPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@K@Z; UDGetCryptoVersion(ulong)
0x18002ce13  mov     rcx, rax; struct _DRM_CRYPTO_VERSION_PARAMETERS *
0x18002ce16  mov     rax, [rsp+0D8h+arg_50]
0x18002ce1e  mov     [rsp+0D8h+var_88], rax; unsigned __int16 **
0x18002ce23  mov     rax, [rsp+0D8h+arg_40]
0x18002ce2b  mov     [rsp+0D8h+var_90], rax; unsigned __int16 **
0x18002ce30  mov     rax, [rsp+0D8h+arg_38]
0x18002ce38  mov     [rsp+0D8h+var_98], rax; unsigned __int16 **
0x18002ce3d  mov     rax, [rsp+0D8h+arg_30]
0x18002ce45  mov     [rsp+0D8h+var_A0], rax; void *
0x18002ce4a  mov     rax, [rsp+0D8h+arg_28]
0x18002ce52  mov     [rsp+0D8h+var_A8], rax; int (*)(enum _DRM_STATUS_MSG, int, void *, void *)
0x18002ce57  mov     rax, [rsp+0D8h+arg_20]
0x18002ce5f  mov     [rsp+0D8h+hHandle], rax; hHandle
0x18002ce64  mov     rax, [rsp+0D8h+arg_10]
0x18002ce6c  mov     [rsp+0D8h+String1], rax; String1
0x18002ce71  mov     r9, [rsp+0D8h+arg_8]; unsigned __int16 *
0x18002ce79  mov     r8, r15; unsigned __int16 *
0x18002ce7c  mov     edx, r13d; unsigned int
0x18002ce7f  call    ?CertifyGroupIdentity@@YAJPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@IPEAG11PEAXP6AJW4_DRM_STATUS_MSG@@J22@Z2PEAPEAG55@Z; CertifyGroupIdentity(_DRM_CRYPTO_VERSION_PARAMETERS const *,uint,ushort *,ushort *,ushort *,void *,long (*)(_DRM_STATUS_MSG,long,void *,void *),void *,ushort * *,ushort * *,ushort * *)
0x18002ce84  mov     ebx, eax
0x18002ce86  test    eax, eax
0x18002ce88  jns     loc_18002CF9B
0x18002ce8e  mov     eax, 8004CFD0h
0x18002ce93  cmp     ebx, eax
0x18002ce95  jg      loc_18002CFBD
0x18002ce9b  mov     esi, 8004CF47h
0x18002cea0  jz      loc_18002CFE9
0x18002cea6  cmp     ebx, esi
0x18002cea8  jg      loc_18002CFA2
0x18002ceae  jz      loc_18002CFE9
0x18002ceb4  lea     eax, [rbx+7FFB30C5h]
0x18002ceba  cmp     eax, 8
0x18002cebd  ja      short loc_18002CECD
0x18002cebf  mov     ecx, 1CDh
0x18002cec4  bt      ecx, eax
0x18002cec7  jb      loc_18002CCD1
0x18002cecd  mov     esi, 8004CF44h
0x18002ced2  cmp     ebx, esi
0x18002ced4  jz      loc_18002CFE9
0x18002ceda  lea     eax, [rbx+7FFB30BBh]
0x18002cee0  cmp     eax, 1
0x18002cee3  jbe     loc_18002CCD1
0x18002cee9  jmp     loc_18002CFDD
0x18002ceee  mov     r14, rdi
0x18002cef1  jmp     loc_18002CD3E
0x18002cef6  mov     [rsp+0D8h+Block], rdi
0x18002cefb  call    ?GetClientHierarchy@@YAKXZ; GetClientHierarchy(void)
0x18002cf00  mov     eax, eax
0x18002cf02  lea     rcx, ?g_wszRMActivateExe_Server_Names@@3QBQEBGB; ushort const * const near * const g_wszRMActivateExe_Server_Names
0x18002cf09  lea     rdx, ?g_wszRMActivateExe_DeskTop_Names@@3QBQEBGB; ushort const * const near * const g_wszRMActivateExe_DeskTop_Names
0x18002cf10  cmp     cs:?g_fGlobalOptionUseServerProc@@3HA, edi; int g_fGlobalOptionUseServerProc
0x18002cf16  cmovz   rcx, rdx
0x18002cf1a  lea     rdx, [rsp+0D8h+Block]; unsigned __int16 *
0x18002cf1f  mov     rcx, [rcx+rax*8]; this
0x18002cf23  call    ?GetFileNameWithSystemPath@DRMOS@@YAJPEBGPEAPEAG@Z; DRMOS::GetFileNameWithSystemPath(ushort const *,ushort * *)
0x18002cf28  mov     ebx, eax
0x18002cf2a  mov     rsi, [rsp+0D8h+Block]
0x18002cf2f  test    eax, eax
0x18002cf31  js      short loc_18002CF8B
0x18002cf33  mov     rcx, rsi; lpFileName
0x18002cf36  call    ?GetFileAttributesA@DRMOS@@YAKPEBG@Z; DRMOS::GetFileAttributesA(ushort const *)
0x18002cf3b  cmp     eax, 0FFFFFFFFh
0x18002cf3e  jnz     short loc_18002CF47
0x18002cf40  mov     ebx, 8004CF4Dh
0x18002cf45  jmp     short loc_18002CF8B
0x18002cf47  mov     r9, [rsp+0D8h+arg_20]; int
0x18002cf4f  mov     rcx, rsi; this
0x18002cf52  call    ?DoProcess@DRMOS@@YAJPEBGPEAGHPEAX@Z; DRMOS::DoProcess(ushort const *,ushort *,int,void *)
0x18002cf57  mov     ebx, eax
0x18002cf59  mov     edx, eax
0x18002cf5b  lea     rcx, aMsdrmRmactivat; "[msdrm]:RMActivate.exe HR = %x\n"
0x18002cf62  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18002cf67  test    ebx, ebx
0x18002cf69  jns     short loc_18002CF8B
0x18002cf6b  lea     eax, [rbx+7FFB30BFh]
0x18002cf71  cmp     eax, 38h ; '8'
0x18002cf74  ja      short loc_18002CF86
0x18002cf76  mov     rcx, 100000000001001h
0x18002cf80  bt      rcx, rax
0x18002cf84  jb      short loc_18002CF8B
0x18002cf86  mov     ebx, 8004CF40h
0x18002cf8b  mov     rcx, rsi; Block
0x18002cf8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cf93  test    ebx, ebx
0x18002cf95  js      loc_18002CE8E
0x18002cf9b  mov     esi, 4CF04h
0x18002cfa0  jmp     short loc_18002CFEE
0x18002cfa2  lea     eax, [rbx+7FFB30B6h]
0x18002cfa8  cmp     eax, 15h
0x18002cfab  ja      short loc_18002CFDD
0x18002cfad  mov     ecx, 2F000Fh
0x18002cfb2  bt      ecx, eax
0x18002cfb5  jb      loc_18002CCD1
0x18002cfbb  jmp     short loc_18002CFDD
0x18002cfbd  cmp     ebx, 8004CFD4h
0x18002cfc3  jz      short loc_18002CFE4
0x18002cfc5  cmp     ebx, 8007000Eh
0x18002cfcb  jz      loc_18002CCD1
0x18002cfd1  cmp     ebx, 80070057h
0x18002cfd7  jz      loc_18002CCD1
0x18002cfdd  mov     esi, 8004CF40h
0x18002cfe2  jmp     short loc_18002CFE9
0x18002cfe4  mov     esi, 8004CF44h
0x18002cfe9  mov     r15, [rsp+0D8h+var_70]
0x18002cfee  mov     rcx, [rsp+0D8h+var_68]; Block
0x18002cff3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cff8  mov     rcx, r12; Block
0x18002cffb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d000  mov     rcx, r15; Block
0x18002d003  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d008  test    r14, r14
0x18002d00b  jz      short loc_18002D015
0x18002d00d  mov     rcx, r14; this
  ... truncated ...
```
