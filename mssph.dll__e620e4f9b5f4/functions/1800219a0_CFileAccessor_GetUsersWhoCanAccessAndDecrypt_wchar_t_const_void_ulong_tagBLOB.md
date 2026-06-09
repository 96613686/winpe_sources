# CFileAccessor::GetUsersWhoCanAccessAndDecrypt(wchar_t const *,void *,ulong *,tagBLOB * *)

- ea: `0x1800219a0`
- end: `0x180021e1f`
- name: `?GetUsersWhoCanAccessAndDecrypt@CFileAccessor@@AEAAJPEB_WPEAXPEAKPEAPEAUtagBLOB@@@Z`
- size: `1151`
- prototype: `__int64 __fastcall(CFileHandler **this, const wchar_t *, void *, unsigned int *, struct tagBLOB **)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020ecc`
- `0x180021770`

## callees

- `0x18000be20`
- `0x18000ea90`
- `0x180011150`
- `0x180011244`
- `0x18001f474`
- `0x18001f504`
- `0x18001f7b8`
- `0x18001fb44`
- `0x180020610`
- `0x180020b7c`
- `0x180020cdc`
- `0x1800219a0`
- `0x180024bec`
- `0x180024c74`
- `0x180024ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021de8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021bae`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021cd0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021bae`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180021cd0`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!FreeEncryptionCertificateHashList` at `0x180021c07`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!FreeEncryptionCertificateHashList` at `0x180021c07`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!QueryUsersOnEncryptedFile` at `0x180021a05`
- `ext-ms-win-advapi32-encryptedfile-l1-1-0!QueryUsersOnEncryptedFile` at `0x180021a05`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientQueryProtectors` at `0x180021c69`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientQueryProtectors` at `0x180021c69`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientFreeProtectorList` at `0x180021d2a`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientFreeProtectorList` at `0x180021d2a`

## pseudocode

```c
__int64 __fastcall CFileAccessor::GetUsersWhoCanAccessAndDecrypt(
        CFileHandler **this,
        const wchar_t *a2,
        void *a3,
        unsigned int *a4,
        struct tagBLOB **a5)
{
  const WCHAR *v5; // r12
  int Thumb2SidsFromRegistry; // r14d
  char v7; // di
  struct tagBLOB *v8; // r15
  unsigned int v9; // ebx
  signed int v10; // eax
  DWORD nCert_Hash; // r12d
  DWORD i; // edi
  PEFS_HASH_BLOB pHash; // rcx
  void *v14; // rcx
  int v15; // edx
  PENCRYPTION_CERTIFICATE_HASH v16; // rax
  const unsigned __int8 *p_Revision; // r13
  DWORD LengthSid; // eax
  DWORD v19; // edi
  int v20; // eax
  unsigned int v21; // r12d
  void *v22; // rbx
  DWORD v23; // eax
  unsigned int v24; // r13d
  unsigned int v25; // r12d
  __int64 v27; // rcx
  unsigned int v28; // [rsp+20h] [rbp-E8h] BYREF
  unsigned int v29; // [rsp+24h] [rbp-E4h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-E0h] BYREF
  unsigned int v31; // [rsp+30h] [rbp-D8h]
  struct tagBLOB *v32; // [rsp+38h] [rbp-D0h] BYREF
  PENCRYPTION_CERTIFICATE_HASH_LIST pUsers; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v34; // [rsp+48h] [rbp-C0h]
  LPVOID *p_pv; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *v36; // [rsp+58h] [rbp-B0h] BYREF
  char v37; // [rsp+60h] [rbp-A8h]
  __int128 v38; // [rsp+68h] [rbp-A0h] BYREF
  int v39; // [rsp+78h] [rbp-90h]
  __int64 v40; // [rsp+80h] [rbp-88h]
  int v41; // [rsp+88h] [rbp-80h]
  __int128 v42; // [rsp+90h] [rbp-78h]
  _BYTE v43[24]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v44[80]; // [rsp+B8h] [rbp-50h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]

  v5 = a2;
  Thumb2SidsFromRegistry = 0;
  v7 = 0;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v28 = 0;
  if ( (unsigned __int8)IsFreeEncryptionCertificateHashListPresent()
    && (unsigned __int8)IsFreeEncryptionCertificateHashListPresent() )
  {
    pUsers = 0;
    v10 = QueryUsersOnEncryptedFile(v5, &pUsers);
    if ( v10 )
    {
      nCert_Hash = 0;
      if ( v10 > 0 )
        Thumb2SidsFromRegistry = (unsigned __int16)v10 | 0x80070000;
      else
        Thumb2SidsFromRegistry = v10;
    }
    else
    {
      nCert_Hash = pUsers->nCert_Hash;
    }
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    for ( i = 0; Thumb2SidsFromRegistry >= 0 && i < nCert_Hash; ++i )
    {
      pHash = pUsers->pUsers[i]->pHash;
      pv = 0;
      v29 = 0;
      p_pv = &pv;
      v36 = 0;
      v37 = 1;
      Thumb2SidsFromRegistry = CertHashToString(pHash->pbData, pHash->cbData, &v36, &v29);
      wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( Thumb2SidsFromRegistry < 0
        || (Thumb2SidsFromRegistry = CHashValueStringList::AddStringToListAndOwn(
                                       (CHashValueStringList *)&v38,
                                       (wchar_t *)pv,
                                       v29),
            v14 = 0,
            Thumb2SidsFromRegistry < 0) )
      {
        v14 = pv;
      }
      pv = 0;
      if ( v14 )
        CoTaskMemFree(v14);
    }
    CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>(v43);
    CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>(v44);
    if ( Thumb2SidsFromRegistry >= 0 )
    {
      Thumb2SidsFromRegistry = CCertThumbprintsAndSidsMapping::ReadThumb2SidsFromRegistry(
                                 (CCertThumbprintsAndSidsMapping *)v43,
                                 v15);
      if ( Thumb2SidsFromRegistry >= 0 )
      {
        Thumb2SidsFromRegistry = CCertThumbprintsAndSidsMapping::GetSidsForThumbs(
                                   (CCertThumbprintsAndSidsMapping *)v43,
                                   (struct CHashValueStringList *)&v38,
                                   &v32,
                                   &v28);
        v9 = v28;
        if ( Thumb2SidsFromRegistry < 0 || v28 || !nCert_Hash )
        {
          v8 = v32;
        }
        else
        {
          try
          {
            pv = 0;
            v31 = 0;
            CSidContainer::Allocate((CSidContainer *)&pv, nCert_Hash);
            v19 = 0;
            v8 = (struct tagBLOB *)pv;
            while ( v19 < nCert_Hash )
            {
              v16 = pUsers->pUsers[v19];
              p_Revision = &v16->pUserSid->Revision;
              if ( p_Revision )
              {
                LengthSid = GetLengthSid(v16->pUserSid);
                CSidBlob::InitDeepCopy((CSidBlob *)&v8[v9++], p_Revision, LengthSid);
                v28 = v9;
              }
              ++v19;
            }
            v32 = v8;
            pv = 0;
            v31 = 0;
            CSidContainer::FreeBlobs((CSidContainer *)&pv);
          }
          catch ( ... )
          {
            indexer::result::details::result_from_caught_exception<1>(
              retaddr,
              252,
              "onecoreuap\\base\\appmodel\\search\\mssph\\file\\fileacc.cxx");
          }
        }
      }
    }
    if ( pUsers )
      FreeEncryptionCertificateHashList(pUsers);
    CCertThumbprintsAndSidsMapping::~CCertThumbprintsAndSidsMapping((CCertThumbprintsAndSidsMapping *)v43);
    CHashValueStringList::~CHashValueStringList((CHashValueStringList *)&v38);
    if ( Thumb2SidsFromRegistry < 0 )
      goto LABEL_46;
    v7 = 1;
    if ( v9 )
      goto LABEL_46;
    v5 = a2;
  }
  if ( (unsigned __int8)IsEfsClientQueryProtectorsPresent() && (unsigned __int8)IsEfsClientQueryProtectorsPresent() )
  {
    pv = 0;
    v20 = EfsClientQueryProtectors(v5, &pv);
    Thumb2SidsFromRegistry = v20;
    if ( v20 > 0 )
      Thumb2SidsFromRegistry = (unsigned __int16)v20 | 0x80070000;
    if ( Thumb2SidsFromRegistry >= 0 && *(_DWORD *)pv )
    {
      pUsers = 0;
      v34 = 0;
      CSidContainer::Allocate((CSidContainer *)&pUsers, *(_DWORD *)pv);
      v21 = 0;
      v8 = (struct tagBLOB *)pUsers;
      while ( v21 < *(_DWORD *)pv )
      {
        v22 = *(void **)(*(_QWORD *)(*((_QWORD *)pv + 1) + 8LL * v21) + 8LL);
        v23 = GetLengthSid(v22);
        CSidBlob::InitDeepCopy((CSidBlob *)&v8[v21++], (const unsigned __int8 *)v22, v23);
      }
      v32 = v8;
      v9 = v34;
      v28 = v34;
      pUsers = 0;
      v34 = 0;
      CSidContainer::FreeBlobs((CSidContainer *)&pUsers);
    }
    if ( pv )
      EfsClientFreeProtectorList();
  }
  else if ( !v7 )
  {
    Thumb2SidsFromRegistry = -2147467263;
LABEL_49:
    pv = 0;
    v31 = 0;
    CSidContainer::FreeBlobs((CSidContainer *)&pv);
    pv = v8;
    v31 = v9;
    CSidContainer::FreeBlobs((CSidContainer *)&pv);
    return (unsigned int)Thumb2SidsFromRegistry;
  }
LABEL_46:
  v24 = 0;
  v25 = 0;
LABEL_57:
  if ( Thumb2SidsFromRegistry < 0 )
    goto LABEL_49;
  while ( v25 < v9 )
  {
    Thumb2SidsFromRegistry = CFileHandler::CheckFileGenericReadAccess(this[112], v8[v25].pBlobData, a3);
    if ( Thumb2SidsFromRegistry )
    {
      CoTaskMemFree(v8[v25].pBlobData);
      v8[v25].pBlobData = 0;
      v8[v25++].cbSize = 0;
      goto LABEL_57;
    }
    if ( v25 > v24 )
    {
      v27 = v24;
      v8[v27].pBlobData = v8[v25].pBlobData;
      v8[v27].cbSize = v8[v25].cbSize;
      v8[v25].pBlobData = 0;
      v8[v25].cbSize = 0;
    }
    ++v24;
    ++v25;
  }
  *a5 = v8;
  *a4 = v24;
  return (unsigned int)Thumb2SidsFromRegistry;
}

```

## disassembly

```asm
0x1800219a0  mov     rax, rsp
0x1800219a3  mov     [rax+20h], r9
0x1800219a7  mov     [rax+18h], r8
0x1800219ab  mov     [rax+10h], rdx
0x1800219af  mov     [rax+8], rcx
0x1800219b3  push    rbx
0x1800219b4  push    rsi
0x1800219b5  push    rdi
0x1800219b6  push    r12
0x1800219b8  push    r13
0x1800219ba  push    r14
0x1800219bc  push    r15
0x1800219be  sub     rsp, 0D0h
0x1800219c5  mov     r12, rdx
0x1800219c8  xor     esi, esi
0x1800219ca  mov     r14d, esi
0x1800219cd  mov     dil, sil
0x1800219d0  mov     r15d, esi
0x1800219d3  mov     [rsp+108h+var_D0], rsi
0x1800219d8  mov     ebx, esi
0x1800219da  mov     [rsp+108h+var_E8], ebx
0x1800219de  call    IsFreeEncryptionCertificateHashListPresent
0x1800219e3  test    al, al
0x1800219e5  jz      loc_180021C42
0x1800219eb  call    IsFreeEncryptionCertificateHashListPresent
0x1800219f0  test    al, al
0x1800219f2  jz      loc_180021C42
0x1800219f8  mov     [rsp+108h+pUsers], rsi
0x1800219fd  lea     rdx, [rsp+108h+pUsers]; pUsers
0x180021a02  mov     rcx, r12; lpFileName
0x180021a05  call    cs:__imp_QueryUsersOnEncryptedFile
0x180021a0b  test    eax, eax
0x180021a0d  jz      short loc_180021A26
0x180021a0f  mov     r12d, esi
0x180021a12  jg      short loc_180021A19
0x180021a14  mov     r14d, eax
0x180021a17  jmp     short loc_180021A2E
0x180021a19  movzx   r14d, ax
0x180021a1d  or      r14d, 80070000h
0x180021a24  jmp     short loc_180021A2E
0x180021a26  mov     rax, [rsp+108h+pUsers]
0x180021a2b  mov     r12d, [rax]
0x180021a2e  xorps   xmm0, xmm0
0x180021a31  movdqu  [rsp+108h+var_A0], xmm0
0x180021a37  mov     [rsp+108h+var_90], esi
0x180021a3b  mov     [rsp+108h+var_88], rsi
0x180021a43  mov     [rsp+108h+var_80], esi
0x180021a4a  movdqu  [rsp+108h+var_78], xmm0
0x180021a53  mov     edi, esi
0x180021a55  jmp     loc_180021AEF
0x180021a5a  cmp     edi, r12d
0x180021a5d  jnb     loc_180021AF8
0x180021a63  mov     edx, edi
0x180021a65  mov     rax, [rsp+108h+pUsers]
0x180021a6a  mov     rcx, [rax+8]
0x180021a6e  mov     rax, [rcx+rdx*8]
0x180021a72  mov     rcx, [rax+10h]
0x180021a76  mov     [rsp+108h+pv], rsi
0x180021a7b  mov     [rsp+108h+var_E4], esi
0x180021a7f  lea     rax, [rsp+108h+pv]
0x180021a84  mov     [rsp+108h+var_B8], rax
0x180021a89  mov     [rsp+108h+var_B0], rsi
0x180021a8e  mov     [rsp+108h+var_A8], 1
0x180021a93  lea     r9, [rsp+108h+var_E4]; unsigned int *
0x180021a98  lea     r8, [rsp+108h+var_B0]; wchar_t **
0x180021a9d  mov     edx, [rcx]; cbBinary
0x180021a9f  mov     rcx, [rcx+8]; pbBinary
0x180021aa3  call    ?CertHashToString@@YAJPEAEKPEAPEA_WPEAK@Z; CertHashToString(uchar *,ulong,wchar_t * *,ulong *)
0x180021aa8  mov     r14d, eax
0x180021aab  lea     rcx, [rsp+108h+var_B8]
0x180021ab0  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180021ab5  test    r14d, r14d
0x180021ab8  js      short loc_180021AD8
0x180021aba  mov     r8d, [rsp+108h+var_E4]; unsigned int
0x180021abf  mov     rdx, [rsp+108h+pv]; wchar_t *
0x180021ac4  lea     rcx, [rsp+108h+var_A0]; this
0x180021ac9  call    ?AddStringToListAndOwn@CHashValueStringList@@QEAAJPEA_WK@Z; CHashValueStringList::AddStringToListAndOwn(wchar_t *,ulong)
0x180021ace  mov     r14d, eax
0x180021ad1  test    eax, eax
0x180021ad3  mov     rcx, rsi
0x180021ad6  jns     short loc_180021ADD
0x180021ad8  mov     rcx, [rsp+108h+pv]; pv
0x180021add  mov     [rsp+108h+pv], rsi
0x180021ae2  test    rcx, rcx
0x180021ae5  jz      short loc_180021AED
0x180021ae7  call    cs:__imp_CoTaskMemFree
0x180021aed  inc     edi
0x180021aef  test    r14d, r14d
0x180021af2  jns     loc_180021A5A
0x180021af8  lea     rcx, [rsp+108h+var_68]
0x180021b00  call    ??0?$CTKPLiteHashMapContainer@VCStringHashKey@@VCHashValueStringList@@@@QEAA@K@Z; CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>(ulong)
0x180021b05  nop
0x180021b06  lea     rcx, [rsp+108h+var_50]
0x180021b0e  call    ??0?$CTKPLiteHashMapContainer@VCStringHashKey@@VCHashValueStringList@@@@QEAA@K@Z; CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>::CTKPLiteHashMapContainer<CStringHashKey,CHashValueStringList>(ulong)
0x180021b13  nop
0x180021b14  test    r14d, r14d
0x180021b17  js      loc_180021BFD
0x180021b1d  lea     rcx, [rsp+108h+var_68]; this
0x180021b25  call    ?ReadThumb2SidsFromRegistry@CCertThumbprintsAndSidsMapping@@QEAAJH@Z; CCertThumbprintsAndSidsMapping::ReadThumb2SidsFromRegistry(int)
0x180021b2a  mov     r14d, eax
0x180021b2d  test    eax, eax
0x180021b2f  js      loc_180021BFD
0x180021b35  lea     r9, [rsp+108h+var_E8]; unsigned int *
0x180021b3a  lea     r8, [rsp+108h+var_D0]; struct tagBLOB **
0x180021b3f  lea     rdx, [rsp+108h+var_A0]; struct CHashValueStringList *
0x180021b44  lea     rcx, [rsp+108h+var_68]; this
0x180021b4c  call    ?GetSidsForThumbs@CCertThumbprintsAndSidsMapping@@QEAAJPEAVCHashValueStringList@@PEAPEAUtagBLOB@@PEAK@Z; CCertThumbprintsAndSidsMapping::GetSidsForThumbs(CHashValueStringList *,tagBLOB * *,ulong *)
0x180021b51  mov     r14d, eax
0x180021b54  mov     ebx, [rsp+108h+var_E8]
0x180021b58  test    eax, eax
0x180021b5a  js      loc_180021BF8
0x180021b60  test    ebx, ebx
0x180021b62  jnz     loc_180021BF8
0x180021b68  test    r12d, r12d
0x180021b6b  jz      loc_180021BF8
0x180021b71  mov     [rsp+108h+pv], rsi
0x180021b76  mov     [rsp+108h+var_D8], esi
0x180021b7a  mov     edx, r12d; unsigned int
0x180021b7d  lea     rcx, [rsp+108h+pv]; this
0x180021b82  call    ?Allocate@CSidContainer@@QEAAXK@Z; CSidContainer::Allocate(ulong)
0x180021b87  mov     edi, esi
0x180021b89  mov     r15, [rsp+108h+pv]
0x180021b8e  cmp     edi, r12d
0x180021b91  jnb     short loc_180021BD2
0x180021b93  mov     edx, edi
0x180021b95  mov     rax, [rsp+108h+pUsers]
0x180021b9a  mov     rcx, [rax+8]
0x180021b9e  mov     rax, [rcx+rdx*8]
0x180021ba2  mov     r13, [rax+8]
0x180021ba6  test    r13, r13
0x180021ba9  jz      short loc_180021BCE
0x180021bab  mov     rcx, r13; pSid
0x180021bae  call    cs:__imp_GetLengthSid
0x180021bb4  mov     ecx, ebx
0x180021bb6  shl     rcx, 4
0x180021bba  add     rcx, r15; this
0x180021bbd  mov     r8d, eax; unsigned int
0x180021bc0  mov     rdx, r13; unsigned __int8 *
0x180021bc3  call    ?InitDeepCopy@CSidBlob@@QEAAXPEBEK@Z; CSidBlob::InitDeepCopy(uchar const *,ulong)
0x180021bc8  inc     ebx
0x180021bca  mov     [rsp+108h+var_E8], ebx
0x180021bce  inc     edi
0x180021bd0  jmp     short loc_180021B8E
0x180021bd2  mov     [rsp+108h+var_D0], r15
0x180021bd7  mov     [rsp+108h+pv], rsi
0x180021bdc  mov     [rsp+108h+var_D8], esi
0x180021be0  lea     rcx, [rsp+108h+pv]; this
0x180021be5  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x180021bea  nop
0x180021beb  jmp     short loc_180021BFD
0x180021bed  xor     esi, esi
0x180021bef  mov     r14d, [rsp+108h+var_E4]
0x180021bf4  mov     ebx, [rsp+108h+var_E8]
0x180021bf8  mov     r15, [rsp+108h+var_D0]
0x180021bfd  mov     rcx, [rsp+108h+pUsers]; pUsers
0x180021c02  test    rcx, rcx
0x180021c05  jz      short loc_180021C0E
0x180021c07  call    cs:__imp_FreeEncryptionCertificateHashList
0x180021c0d  nop
0x180021c0e  lea     rcx, [rsp+108h+var_68]; this
0x180021c16  call    ??1CCertThumbprintsAndSidsMapping@@QEAA@XZ; CCertThumbprintsAndSidsMapping::~CCertThumbprintsAndSidsMapping(void)
0x180021c1b  nop
0x180021c1c  lea     rcx, [rsp+108h+var_A0]; this
0x180021c21  call    ??1CHashValueStringList@@QEAA@XZ; CHashValueStringList::~CHashValueStringList(void)
0x180021c26  test    r14d, r14d
0x180021c29  js      loc_180021D30
0x180021c2f  mov     dil, 1
0x180021c32  test    ebx, ebx
0x180021c34  jnz     loc_180021D30
0x180021c3a  mov     r12, [rsp+108h+arg_8]
0x180021c42  call    IsEfsClientQueryProtectorsPresent
0x180021c47  test    al, al
0x180021c49  jz      loc_180021D3B
0x180021c4f  call    IsEfsClientQueryProtectorsPresent
0x180021c54  test    al, al
0x180021c56  jz      loc_180021D3B
0x180021c5c  mov     [rsp+108h+pv], rsi
0x180021c61  lea     rdx, [rsp+108h+pv]
0x180021c66  mov     rcx, r12
0x180021c69  call    cs:__imp_EfsClientQueryProtectors
0x180021c6f  mov     r14d, eax
0x180021c72  test    eax, eax
0x180021c74  jle     short loc_180021C81
0x180021c76  movzx   r14d, ax
0x180021c7a  or      r14d, 80070000h
0x180021c81  test    r14d, r14d
0x180021c84  js      loc_180021D20
0x180021c8a  mov     rax, [rsp+108h+pv]
0x180021c8f  cmp     [rax], esi
0x180021c91  jbe     loc_180021D20
0x180021c97  mov     [rsp+108h+pUsers], rsi
0x180021c9c  mov     [rsp+108h+var_C0], esi
0x180021ca0  mov     edx, [rax]; unsigned int
0x180021ca2  lea     rcx, [rsp+108h+pUsers]; this
0x180021ca7  call    ?Allocate@CSidContainer@@QEAAXK@Z; CSidContainer::Allocate(ulong)
0x180021cac  mov     r12d, esi
0x180021caf  mov     r15, [rsp+108h+pUsers]
0x180021cb4  mov     rax, [rsp+108h+pv]
0x180021cb9  cmp     r12d, [rax]
0x180021cbc  jnb     short loc_180021CED
0x180021cbe  mov     edi, r12d
0x180021cc1  mov     rax, [rax+8]
0x180021cc5  mov     rdx, [rax+rdi*8]
0x180021cc9  mov     rbx, [rdx+8]
0x180021ccd  mov     rcx, rbx; pSid
0x180021cd0  call    cs:__imp_GetLengthSid
0x180021cd6  add     rdi, rdi
0x180021cd9  lea     rcx, [r15+rdi*8]; this
0x180021cdd  mov     r8d, eax; unsigned int
0x180021ce0  mov     rdx, rbx; unsigned __int8 *
0x180021ce3  call    ?InitDeepCopy@CSidBlob@@QEAAXPEBEK@Z; CSidBlob::InitDeepCopy(uchar const *,ulong)
0x180021ce8  inc     r12d
0x180021ceb  jmp     short loc_180021CB4
0x180021ced  mov     [rsp+108h+var_D0], r15
0x180021cf2  mov     ebx, [rsp+108h+var_C0]
0x180021cf6  mov     [rsp+108h+var_E8], ebx
0x180021cfa  mov     [rsp+108h+pUsers], rsi
0x180021cff  mov     [rsp+108h+var_C0], esi
0x180021d03  lea     rcx, [rsp+108h+pUsers]; this
0x180021d08  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x180021d0d  nop
0x180021d0e  jmp     short loc_180021D20
0x180021d10  xor     esi, esi
0x180021d12  mov     r14d, [rsp+108h+var_E4]
0x180021d17  mov     r15, [rsp+108h+var_D0]
0x180021d1c  mov     ebx, [rsp+108h+var_E8]
0x180021d20  mov     rcx, [rsp+108h+pv]
0x180021d25  test    rcx, rcx
0x180021d28  jz      short loc_180021D30
0x180021d2a  call    cs:__imp_EfsClientFreeProtectorList
0x180021d30  mov     r13d, esi
0x180021d33  mov     r12d, esi
0x180021d36  jmp     loc_180021DFA
0x180021d3b  test    dil, dil
0x180021d3e  jnz     short loc_180021D30
0x180021d40  mov     r14d, 80004001h
0x180021d46  mov     [rsp+108h+pv], rsi
0x180021d4b  mov     [rsp+108h+var_D8], esi
0x180021d4f  lea     rcx, [rsp+108h+pv]; this
0x180021d54  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x180021d59  mov     [rsp+108h+pv], r15
0x180021d5e  mov     [rsp+108h+var_D8], ebx
0x180021d62  lea     rcx, [rsp+108h+pv]; this
0x180021d67  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x180021d6c  mov     eax, r14d
0x180021d6f  add     rsp, 0D0h
0x180021d76  pop     r15
0x180021d78  pop     r14
0x180021d7a  pop     r13
0x180021d7c  pop     r12
0x180021d7e  pop     rdi
0x180021d7f  pop     rsi
0x180021d80  pop     rbx
0x180021d81  retn
0x180021d82  cmp     r12d, ebx
0x180021d85  jnb     short loc_180021E04
0x180021d87  mov     edi, r12d
0x180021d8a  add     rdi, rdi
0x180021d8d  mov     r8, [rsp+108h+arg_10]; void *
0x180021d95  mov     rdx, [r15+rdi*8+8]; void *
0x180021d9a  mov     rcx, [rsp+108h+arg_0]
0x180021da2  mov     rcx, [rcx+380h]; this
0x180021da9  call    ?CheckFileGenericReadAccess@CFileHandler@@QEAAJPEAX0@Z; CFileHandler::CheckFileGenericReadAccess(void *,void *)
0x180021dae  mov     r14d, eax
0x180021db1  test    eax, eax
0x180021db3  jnz     short loc_180021DE3
0x180021db5  cmp     r12d, r13d
0x180021db8  jbe     short loc_180021DDB
0x180021dba  mov     ecx, r13d
0x180021dbd  add     rcx, rcx
0x180021dc0  mov     rax, [r15+rdi*8+8]
0x180021dc5  mov     [r15+rcx*8+8], rax
0x180021dca  mov     eax, [r15+rdi*8]
0x180021dce  mov     [r15+rcx*8], eax
0x180021dd2  mov     [r15+rdi*8+8], rsi
0x180021dd7  mov     [r15+rdi*8], esi
0x180021ddb  inc     r13d
0x180021dde  inc     r12d
0x180021de1  jmp     short loc_180021D82
0x180021de3  mov     rcx, [r15+rdi*8+8]; pv
0x180021de8  call    cs:__imp_CoTaskMemFree
0x180021dee  mov     [r15+rdi*8+8], rsi
0x180021df3  mov     [r15+rdi*8], esi
0x180021df7  inc     r12d
0x180021dfa  test    r14d, r14d
0x180021dfd  jns     short loc_180021D82
0x180021dff  jmp     loc_180021D46
0x180021e04  mov     rax, [rsp+108h+arg_20]
0x180021e0c  mov     [rax], r15
0x180021e0f  mov     rax, [rsp+108h+arg_18]
0x180021e17  mov     [rax], r13d
0x180021e1a  jmp     loc_180021D6C
```
