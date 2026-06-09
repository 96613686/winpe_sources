# CEnumCategories::Next(ulong,tagCATEGORYINFO *,ulong *)

- ea: `0x1800ad180`
- end: `0x1800ad430`
- name: `?Next@CEnumCategories@@UEAAJKPEAUtagCATEGORYINFO@@PEAK@Z`
- size: `688`
- prototype: `HRESULT __fastcall(CEnumCategories *this, unsigned int celt, tagCATEGORYINFO *rgelt, unsigned int *pceltFetched)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001b810`
- `0x180052390`
- `0x180053014`
- `0x1800a867c`
- `0x1800ad180`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad1c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ad1c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad2e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad3d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad3f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad405`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad2e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad3d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad3f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ad405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad2c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad348`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad2c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad348`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ad25a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800ad25a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800ad22e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800ad22e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ad299`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ad299`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ad2b3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800ad2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad33d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ad33d`

## pseudocode

```c
__int64 __fastcall CEnumCategories::Next(
        CEnumCategories *this,
        unsigned int celt,
        tagCATEGORYINFO *rgelt,
        unsigned int *pceltFetched)
{
  Microsoft::WRL::Wrappers::SRWLock *p_enumeratorLock; // rbx
  tagCATEGORYINFO *v7; // r13
  unsigned int v9; // r14d
  DWORD m_dwIndex; // edx
  HKEY__ *m_hKey; // rcx
  LSTATUS v12; // eax
  unsigned int v13; // esi
  bool v14; // cc
  _GUID *p_catid; // r13
  unsigned int m_lcid; // edx
  int CategoryDesc; // eax
  wchar_t *v19; // r10
  IEnumCATEGORYINFO *m_pcsIEnumCat; // rcx
  int v21; // eax
  unsigned int count; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Size; // [rsp+44h] [rbp-BCh] BYREF
  HKEY__ *hKeyCat; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *pszDesc; // [rsp+50h] [rbp-B0h] BYREF
  tagCATEGORYINFO *v26; // [rsp+58h] [rbp-A8h]
  char szCatID[272]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR wszCatID[264]; // [rsp+170h] [rbp+70h] BYREF

  p_enumeratorLock = &this->_enumeratorLock;
  v26 = rgelt;
  v7 = rgelt;
  AcquireSRWLockExclusive(&this->_enumeratorLock.SRWLock_);
  if ( pceltFetched )
  {
    *pceltFetched = 0;
  }
  else if ( celt > 1 )
  {
    if ( p_enumeratorLock )
      ReleaseSRWLockExclusive(&p_enumeratorLock->SRWLock_);
    return 2147942487LL;
  }
  if ( !this->m_hKey )
    goto LABEL_31;
  v9 = 0;
  hKeyCat = 0;
  Size = 0;
  if ( !this->m_fromcs )
  {
    while ( v9 < celt )
    {
      m_dwIndex = this->m_dwIndex;
      m_hKey = this->m_hKey;
      Size = 261;
      v12 = RegEnumKeyExA(m_hKey, m_dwIndex, szCatID, &Size, 0, 0, 0, 0);
      v13 = v12;
      if ( v12 )
      {
        if ( v12 != 259 )
        {
          v14 = v12 <= 0;
LABEL_35:
          if ( !v14 )
            v13 = (unsigned __int16)v12 | 0x80070000;
          if ( p_enumeratorLock )
            ReleaseSRWLockExclusive(&p_enumeratorLock->SRWLock_);
          return v13;
        }
        this->m_fromcs = 1;
        break;
      }
      v12 = RegOpenKeyExA(this->m_hKey, szCatID, 0, 0x20019u, &hKeyCat);
      v13 = v12;
      v14 = v12 <= 0;
      if ( v12 )
        goto LABEL_35;
      memset_0(wszCatID, 0, 0x20Au);
      MultiByteToWideChar(0, 0, szCatID, -1, wszCatID, 261);
      p_catid = &v7[v9].catid;
      if ( CLSIDFromString(wszCatID, p_catid) >= 0 )
      {
        m_lcid = this->m_lcid;
        count = 0;
        pszDesc = 0;
        CategoryDesc = CComCat::GetCategoryDesc(hKeyCat, m_lcid, &pszDesc, &count);
        v19 = pszDesc;
        if ( CategoryDesc < 0 )
          p_catid[1].Data2 = 0;
        else
          StringCchCopyW(&p_catid[1].Data2, 0x80u, pszDesc);
        if ( v19 )
          CoTaskMemFree(v19);
        RegCloseKey(hKeyCat);
        if ( pceltFetched )
          ++*pceltFetched;
        ++this->m_dwIndex;
        p_catid[1].Data1 = count;
      }
      else
      {
        RegCloseKey(hKeyCat);
        --v9;
        ++this->m_dwIndex;
      }
      v7 = v26;
      ++v9;
    }
    if ( !this->m_fromcs )
      goto LABEL_40;
  }
  m_pcsIEnumCat = this->m_pcsIEnumCat;
  count = 0;
  if ( !m_pcsIEnumCat )
    goto LABEL_31;
  v21 = ((__int64 (__fastcall *)(IEnumCATEGORYINFO *, _QWORD, tagCATEGORYINFO *, unsigned int *))m_pcsIEnumCat->lpVtbl[1].QueryInterface)(
          m_pcsIEnumCat,
          celt - v9,
          &v7[v9],
          &count);
  if ( pceltFetched )
    *pceltFetched += count;
  if ( v21 >= 0 && v21 != 1 )
  {
LABEL_40:
    if ( p_enumeratorLock )
      ReleaseSRWLockExclusive(&p_enumeratorLock->SRWLock_);
    return 0;
  }
  else
  {
LABEL_31:
    if ( p_enumeratorLock )
      ReleaseSRWLockExclusive(&p_enumeratorLock->SRWLock_);
    return 1;
  }
}

```

## disassembly

```asm
0x1800ad180  push    rbp
0x1800ad182  push    rbx
0x1800ad183  push    rsi
0x1800ad184  push    rdi
0x1800ad185  push    r12
0x1800ad187  push    r13
0x1800ad189  push    r14
0x1800ad18b  push    r15
0x1800ad18d  lea     rbp, [rsp-298h]
0x1800ad195  sub     rsp, 398h
0x1800ad19c  mov     rax, cs:__security_cookie
0x1800ad1a3  xor     rax, rsp
0x1800ad1a6  mov     [rbp+2D0h+var_50], rax
0x1800ad1ad  lea     rbx, [this+28h]
0x1800ad1b1  mov     [rsp+3D0h+var_378], rgelt
0x1800ad1b6  mov     rdi, this
0x1800ad1b9  mov     r15, pceltFetched
0x1800ad1bc  mov     this, rbx; SRWLock
0x1800ad1bf  mov     r13, rgelt
0x1800ad1c2  mov     r12d, celt
0x1800ad1c5  call    cs:__imp_AcquireSRWLockExclusive
0x1800ad1cb  xor     esi, esi
0x1800ad1cd  test    r15, r15
0x1800ad1d0  jz      loc_1800AD2D5
0x1800ad1d6  mov     [r15], esi
0x1800ad1d9  cmp     [rdi+8], rsi
0x1800ad1dd  jz      loc_1800AD3C9
0x1800ad1e3  mov     r14d, esi
0x1800ad1e6  mov     [rsp+3D0h+hKeyCat], rsi
0x1800ad1eb  mov     [rsp+3D0h+Size], esi
0x1800ad1ef  cmp     [rdi+20h], esi
0x1800ad1f2  jnz     loc_1800AD383
0x1800ad1f8  cmp     r14d, r12d
0x1800ad1fb  jnb     loc_1800AD37E
0x1800ad201  mov     celt, [rdi+10h]; dwIndex
0x1800ad204  lea     pceltFetched, [rsp+3D0h+Size]; lpcchName
0x1800ad209  mov     this, [rdi+8]; hKey
0x1800ad20d  lea     rgelt, [rsp+3D0h+szCatID]; lpName
0x1800ad212  mov     [rsp+3D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800ad217  mov     [rsp+3D0h+lpcchClass], rsi; lpcchClass
0x1800ad21c  mov     [rsp+3D0h+lpClass], rsi; lpClass
0x1800ad221  mov     [rsp+3D0h+lpReserved], rsi; lpReserved
0x1800ad226  mov     [rsp+3D0h+Size], 105h
0x1800ad22e  call    cs:__imp_RegEnumKeyExA
0x1800ad234  mov     esi, eax
0x1800ad236  test    eax, eax
0x1800ad238  jnz     loc_1800AD36E
0x1800ad23e  mov     this, [rdi+8]; hKey
0x1800ad242  lea     rax, [rsp+3D0h+hKeyCat]
0x1800ad247  mov     r9d, 20019h; samDesired
0x1800ad24d  mov     [rsp+3D0h+lpReserved], rax; phkResult
0x1800ad252  xor     r8d, r8d; ulOptions
0x1800ad255  lea     rdx, [rsp+3D0h+szCatID]; lpSubKey
0x1800ad25a  call    cs:__imp_RegOpenKeyExA
0x1800ad260  mov     esi, eax
0x1800ad262  test    eax, eax
0x1800ad264  jnz     loc_1800AD3E0
0x1800ad26a  xor     celt, celt; Val
0x1800ad26c  lea     this, [rbp+2D0h+wszCatID]; void *
0x1800ad270  mov     r8d, 20Ah; Size
0x1800ad276  call    memset_0
0x1800ad27b  lea     rax, [rbp+2D0h+wszCatID]
0x1800ad27f  mov     dword ptr [rsp+3D0h+lpClass], 105h; cchWideChar
0x1800ad287  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800ad28b  mov     [rsp+3D0h+lpReserved], rax; lpWideCharStr
0x1800ad290  lea     rgelt, [rsp+3D0h+szCatID]; lpMultiByteStr
0x1800ad295  xor     celt, celt; dwFlags
0x1800ad297  xor     ecx, ecx; CodePage
0x1800ad299  call    cs:__imp_MultiByteToWideChar
0x1800ad29f  mov     eax, r14d
0x1800ad2a2  imul    this, rax, 114h
0x1800ad2a9  add     r13, this
0x1800ad2ac  lea     this, [rbp+2D0h+wszCatID]; lpsz
0x1800ad2b0  mov     rdx, r13; pclsid
0x1800ad2b3  call    cs:__imp_CLSIDFromString
0x1800ad2b9  mov     this, [rsp+3D0h+hKeyCat]; hKey
0x1800ad2be  xor     esi, esi
0x1800ad2c0  test    eax, eax
0x1800ad2c2  jns     short loc_1800AD2F7
0x1800ad2c4  call    cs:__imp_RegCloseKey
0x1800ad2ca  dec     r14d
0x1800ad2cd  inc     dword ptr [rdi+10h]
0x1800ad2d0  jmp     loc_1800AD361
0x1800ad2d5  cmp     r12d, 1
0x1800ad2d9  jbe     loc_1800AD1D9
0x1800ad2df  test    rbx, rbx
0x1800ad2e2  jz      short loc_1800AD2ED
0x1800ad2e4  mov     this, rbx; SRWLock
0x1800ad2e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad2ed  mov     eax, 80070057h
0x1800ad2f2  jmp     loc_1800AD40D
0x1800ad2f7  mov     celt, [rdi+14h]; lcid
0x1800ad2fa  lea     pceltFetched, [rsp+3D0h+count]; plcid
0x1800ad2ff  lea     rgelt, [rsp+3D0h+pszDesc]; ppszDesc
0x1800ad304  mov     [rsp+3D0h+count], esi
0x1800ad308  mov     [rsp+3D0h+pszDesc], rsi
0x1800ad30d  call    ?GetCategoryDesc@CComCat@@SAJPEAUHKEY__@@KPEAPEAGPEAK@Z; CComCat::GetCategoryDesc(HKEY__ *,ulong,ushort * *,ulong *)
0x1800ad312  mov     r10, [rsp+3D0h+pszDesc]
0x1800ad317  test    eax, eax
0x1800ad319  js      short loc_1800AD32E
0x1800ad31b  mov     rgelt, r10; pszSrc
0x1800ad31e  lea     this, [r13+14h]; pszDest
0x1800ad322  mov     celt, 80h; cchDest
0x1800ad327  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad32c  jmp     short loc_1800AD335
0x1800ad32e  xor     eax, eax
0x1800ad330  mov     [r13+14h], ax
0x1800ad335  test    r10, r10
0x1800ad338  jz      short loc_1800AD343
0x1800ad33a  mov     this, r10; pv
0x1800ad33d  call    cs:__imp_CoTaskMemFree
0x1800ad343  mov     this, [rsp+3D0h+hKeyCat]; hKey
0x1800ad348  call    cs:__imp_RegCloseKey
0x1800ad34e  test    r15, r15
0x1800ad351  jz      short loc_1800AD356
0x1800ad353  inc     dword ptr [r15]
0x1800ad356  inc     dword ptr [rdi+10h]
0x1800ad359  mov     eax, [rsp+3D0h+count]
0x1800ad35d  mov     [r13+10h], eax
0x1800ad361  mov     r13, [rsp+3D0h+var_378]
0x1800ad366  inc     r14d
0x1800ad369  jmp     loc_1800AD1F8
0x1800ad36e  cmp     eax, 103h
0x1800ad373  jnz     short loc_1800AD3DE
0x1800ad375  mov     dword ptr [rdi+20h], 1
0x1800ad37c  xor     esi, esi
0x1800ad37e  cmp     [rdi+20h], esi
0x1800ad381  jz      short loc_1800AD3FD
0x1800ad383  mov     this, [rdi+18h]
0x1800ad387  mov     [rsp+3D0h+count], esi
0x1800ad38b  test    this, this
0x1800ad38e  jz      short loc_1800AD3C9
0x1800ad390  mov     rdx, [this]
0x1800ad393  lea     pceltFetched, [rsp+3D0h+count]
0x1800ad398  mov     eax, r14d
0x1800ad39b  sub     r12d, r14d
0x1800ad39e  imul    rgelt, rax, 114h
0x1800ad3a5  mov     rax, [rdx+18h]
0x1800ad3a9  mov     celt, r12d
0x1800ad3ac  add     rgelt, r13
0x1800ad3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3b4  test    r15, r15
0x1800ad3b7  jz      short loc_1800AD3C0
0x1800ad3b9  mov     ecx, [rsp+3D0h+count]
0x1800ad3bd  add     [r15], ecx
0x1800ad3c0  test    eax, eax
0x1800ad3c2  js      short loc_1800AD3C9
0x1800ad3c4  cmp     eax, 1
0x1800ad3c7  jnz     short loc_1800AD3FD
0x1800ad3c9  test    rbx, rbx
0x1800ad3cc  jz      short loc_1800AD3D7
0x1800ad3ce  mov     this, rbx; SRWLock
0x1800ad3d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad3d7  mov     eax, 1
0x1800ad3dc  jmp     short loc_1800AD40D
0x1800ad3de  test    eax, eax
0x1800ad3e0  jle     short loc_1800AD3EB
0x1800ad3e2  movzx   esi, ax
0x1800ad3e5  or      esi, 80070000h
0x1800ad3eb  test    rbx, rbx
0x1800ad3ee  jz      short loc_1800AD3F9
0x1800ad3f0  mov     this, rbx; SRWLock
0x1800ad3f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad3f9  mov     eax, esi
0x1800ad3fb  jmp     short loc_1800AD40D
0x1800ad3fd  test    rbx, rbx
0x1800ad400  jz      short loc_1800AD40B
0x1800ad402  mov     this, rbx; SRWLock
0x1800ad405  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ad40b  xor     eax, eax
0x1800ad40d  mov     this, [rbp+2D0h+var_50]
0x1800ad414  xor     this, rsp; StackCookie
0x1800ad417  call    __security_check_cookie
0x1800ad41c  add     rsp, 398h
0x1800ad423  pop     r15
0x1800ad425  pop     r14
0x1800ad427  pop     r13
0x1800ad429  pop     r12
0x1800ad42b  pop     rdi
0x1800ad42c  pop     rsi
0x1800ad42d  pop     rbx
0x1800ad42e  pop     rbp
0x1800ad42f  retn
```
