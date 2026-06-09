# CEnumCategories::Next(ulong,tagCATEGORYINFO *,ulong *)

- ea: `0x1800b5130`
- end: `0x1800b543b`
- name: `?Next@CEnumCategories@@UEAAJKPEAUtagCATEGORYINFO@@PEAK@Z`
- size: `779`
- prototype: `HRESULT __fastcall(CEnumCategories *this, unsigned int celt, tagCATEGORYINFO *rgelt, unsigned int *pceltFetched)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001a630`
- `0x180046460`
- `0x180047484`
- `0x1800afa78`
- `0x1800b5130`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b52bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b53c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b53f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b5409`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b52bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b53c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b53f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b5409`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b5175`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b5175`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800b51e4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800b51e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b5216`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b5216`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5292`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5292`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5328`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b525b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800b525b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b527b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b527b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5317`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b5317`

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
  LSTATUS v14; // eax
  _GUID *p_catid; // r13
  unsigned int m_lcid; // edx
  int CategoryDesc; // eax
  wchar_t *v19; // r10
  int v20; // esi
  IEnumCATEGORYINFO *m_pcsIEnumCat; // rcx
  int v22; // eax
  unsigned int count; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Size; // [rsp+44h] [rbp-BCh] BYREF
  HKEY__ *hKeyCat; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *pszDesc; // [rsp+50h] [rbp-B0h] BYREF
  tagCATEGORYINFO *v27; // [rsp+58h] [rbp-A8h]
  char szCatID[272]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR wszCatID[264]; // [rsp+170h] [rbp+70h] BYREF

  p_enumeratorLock = &this->_enumeratorLock;
  v27 = rgelt;
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
    goto LABEL_33;
  v9 = 0;
  hKeyCat = 0;
  Size = 0;
  if ( !this->m_fromcs )
  {
    while ( 1 )
    {
      if ( v9 >= celt )
        goto LABEL_27;
      m_dwIndex = this->m_dwIndex;
      m_hKey = this->m_hKey;
      Size = 261;
      v12 = RegEnumKeyExA(m_hKey, m_dwIndex, szCatID, &Size, 0, 0, 0, 0);
      v13 = v12;
      if ( v12 )
        break;
      v14 = RegOpenKeyExA(this->m_hKey, szCatID, 0, 0x20019u, &hKeyCat);
      v13 = v14;
      if ( v14 )
      {
        if ( v14 > 0 )
        {
          v20 = (unsigned __int16)v14;
          goto LABEL_38;
        }
        goto LABEL_39;
      }
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
      v7 = v27;
      ++v9;
    }
    if ( v12 != 259 )
    {
      if ( v12 > 0 )
      {
        v20 = (unsigned __int16)v12;
LABEL_38:
        v13 = v20 | 0x80070000;
      }
LABEL_39:
      if ( p_enumeratorLock )
        ReleaseSRWLockExclusive(&p_enumeratorLock->SRWLock_);
      return v13;
    }
    this->m_fromcs = 1;
LABEL_27:
    if ( !this->m_fromcs )
      goto LABEL_42;
  }
  m_pcsIEnumCat = this->m_pcsIEnumCat;
  count = 0;
  if ( !m_pcsIEnumCat )
    goto LABEL_33;
  v22 = ((__int64 (__fastcall *)(IEnumCATEGORYINFO *, _QWORD, tagCATEGORYINFO *, unsigned int *))m_pcsIEnumCat->lpVtbl[1].QueryInterface)(
          m_pcsIEnumCat,
          celt - v9,
          &v7[v9],
          &count);
  if ( pceltFetched )
    *pceltFetched += count;
  if ( v22 >= 0 && v22 != 1 )
  {
LABEL_42:
    if ( p_enumeratorLock )
      ReleaseSRWLockExclusive(&p_enumeratorLock->SRWLock_);
    return 0;
  }
  else
  {
LABEL_33:
    if ( p_enumeratorLock )
      ReleaseSRWLockExclusive(&p_enumeratorLock->SRWLock_);
    return 1;
  }
}

```

## disassembly

```asm
0x1800b5130  push    rbp
0x1800b5132  push    rbx
0x1800b5133  push    rsi
0x1800b5134  push    rdi
0x1800b5135  push    r12
0x1800b5137  push    r13
0x1800b5139  push    r14
0x1800b513b  push    r15
0x1800b513d  lea     rbp, [rsp-298h]
0x1800b5145  sub     rsp, 398h
0x1800b514c  mov     rax, cs:__security_cookie
0x1800b5153  xor     rax, rsp
0x1800b5156  mov     [rbp+2D0h+var_50], rax
0x1800b515d  lea     rbx, [this+28h]
0x1800b5161  mov     [rsp+3D0h+var_378], rgelt
0x1800b5166  mov     rdi, this
0x1800b5169  mov     r15, pceltFetched
0x1800b516c  mov     this, rbx; SRWLock
0x1800b516f  mov     r13, rgelt
0x1800b5172  mov     r12d, celt
0x1800b5175  call    cs:__imp_AcquireSRWLockExclusive
0x1800b517c  nop     dword ptr [rax+rax+00h]
0x1800b5181  xor     esi, esi
0x1800b5183  test    r15, r15
0x1800b5186  jz      loc_1800B52A9
0x1800b518c  mov     [r15], esi
0x1800b518f  cmp     [rdi+8], rsi
0x1800b5193  jz      loc_1800B53C1
0x1800b5199  mov     r14d, esi
0x1800b519c  mov     [rsp+3D0h+hKeyCat], rsi
0x1800b51a1  mov     [rsp+3D0h+Size], esi
0x1800b51a5  cmp     [rdi+20h], esi
0x1800b51a8  jnz     loc_1800B537B
0x1800b51ae  cmp     r14d, r12d
0x1800b51b1  jnb     loc_1800B5372
0x1800b51b7  mov     celt, [rdi+10h]; dwIndex
0x1800b51ba  lea     pceltFetched, [rsp+3D0h+Size]; lpcchName
0x1800b51bf  mov     this, [rdi+8]; hKey
0x1800b51c3  lea     rgelt, [rsp+3D0h+szCatID]; lpName
0x1800b51c8  mov     [rsp+3D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800b51cd  mov     [rsp+3D0h+lpcchClass], rsi; lpcchClass
0x1800b51d2  mov     [rsp+3D0h+lpClass], rsi; lpClass
0x1800b51d7  mov     [rsp+3D0h+lpReserved], rsi; lpReserved
0x1800b51dc  mov     [rsp+3D0h+Size], 105h
0x1800b51e4  call    cs:__imp_RegEnumKeyExA
0x1800b51eb  nop     dword ptr [rax+rax+00h]
0x1800b51f0  mov     esi, eax
0x1800b51f2  test    eax, eax
0x1800b51f4  jnz     loc_1800B5362
0x1800b51fa  mov     this, [rdi+8]; hKey
0x1800b51fe  lea     rax, [rsp+3D0h+hKeyCat]
0x1800b5203  mov     r9d, 20019h; samDesired
0x1800b5209  mov     [rsp+3D0h+lpReserved], rax; phkResult
0x1800b520e  xor     r8d, r8d; ulOptions
0x1800b5211  lea     rdx, [rsp+3D0h+szCatID]; lpSubKey
0x1800b5216  call    cs:__imp_RegOpenKeyExA
0x1800b521d  nop     dword ptr [rax+rax+00h]
0x1800b5222  mov     esi, eax
0x1800b5224  test    eax, eax
0x1800b5226  jnz     loc_1800B5354
0x1800b522c  xor     celt, celt; Val
0x1800b522e  lea     this, [rbp+2D0h+wszCatID]; void *
0x1800b5232  mov     r8d, 20Ah; Size
0x1800b5238  call    memset_0
0x1800b523d  lea     rax, [rbp+2D0h+wszCatID]
0x1800b5241  mov     dword ptr [rsp+3D0h+lpClass], 105h; cchWideChar
0x1800b5249  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800b524d  mov     [rsp+3D0h+lpReserved], rax; lpWideCharStr
0x1800b5252  lea     rgelt, [rsp+3D0h+szCatID]; lpMultiByteStr
0x1800b5257  xor     celt, celt; dwFlags
0x1800b5259  xor     ecx, ecx; CodePage
0x1800b525b  call    cs:__imp_MultiByteToWideChar
0x1800b5262  nop     dword ptr [rax+rax+00h]
0x1800b5267  mov     eax, r14d
0x1800b526a  imul    this, rax, 114h
0x1800b5271  add     r13, this
0x1800b5274  lea     this, [rbp+2D0h+wszCatID]; lpsz
0x1800b5278  mov     rdx, r13; pclsid
0x1800b527b  call    cs:__imp_CLSIDFromString
0x1800b5282  nop     dword ptr [rax+rax+00h]
0x1800b5287  mov     this, [rsp+3D0h+hKeyCat]; hKey
0x1800b528c  xor     esi, esi
0x1800b528e  test    eax, eax
0x1800b5290  jns     short loc_1800B52D1
0x1800b5292  call    cs:__imp_RegCloseKey
0x1800b5299  nop     dword ptr [rax+rax+00h]
0x1800b529e  dec     r14d
0x1800b52a1  inc     dword ptr [rdi+10h]
0x1800b52a4  jmp     loc_1800B5347
0x1800b52a9  cmp     r12d, 1
0x1800b52ad  jbe     loc_1800B518F
0x1800b52b3  test    rbx, rbx
0x1800b52b6  jz      short loc_1800B52C7
0x1800b52b8  mov     this, rbx; SRWLock
0x1800b52bb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b52c2  nop     dword ptr [rax+rax+00h]
0x1800b52c7  mov     eax, 80070057h
0x1800b52cc  jmp     loc_1800B5417
0x1800b52d1  mov     celt, [rdi+14h]; lcid
0x1800b52d4  lea     pceltFetched, [rsp+3D0h+count]; plcid
0x1800b52d9  lea     rgelt, [rsp+3D0h+pszDesc]; ppszDesc
0x1800b52de  mov     [rsp+3D0h+count], esi
0x1800b52e2  mov     [rsp+3D0h+pszDesc], rsi
0x1800b52e7  call    ?GetCategoryDesc@CComCat@@SAJPEAUHKEY__@@KPEAPEAGPEAK@Z; CComCat::GetCategoryDesc(HKEY__ *,ulong,ushort * *,ulong *)
0x1800b52ec  mov     r10, [rsp+3D0h+pszDesc]
0x1800b52f1  xor     ecx, ecx
0x1800b52f3  test    eax, eax
0x1800b52f5  js      short loc_1800B530A
0x1800b52f7  mov     rgelt, r10; pszSrc
0x1800b52fa  lea     this, [r13+14h]; pszDest
0x1800b52fe  mov     celt, 80h; cchDest
0x1800b5303  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b5308  jmp     short loc_1800B530F
0x1800b530a  mov     [r13+14h], cx
0x1800b530f  test    r10, r10
0x1800b5312  jz      short loc_1800B5323
0x1800b5314  mov     this, r10; pv
0x1800b5317  call    cs:__imp_CoTaskMemFree
0x1800b531e  nop     dword ptr [rax+rax+00h]
0x1800b5323  mov     this, [rsp+3D0h+hKeyCat]; hKey
0x1800b5328  call    cs:__imp_RegCloseKey
0x1800b532f  nop     dword ptr [rax+rax+00h]
0x1800b5334  test    r15, r15
0x1800b5337  jz      short loc_1800B533C
0x1800b5339  inc     dword ptr [r15]
0x1800b533c  inc     dword ptr [rdi+10h]
0x1800b533f  mov     eax, [rsp+3D0h+count]
0x1800b5343  mov     [r13+10h], eax
0x1800b5347  mov     r13, [rsp+3D0h+var_378]
0x1800b534c  inc     r14d
0x1800b534f  jmp     loc_1800B51AE
0x1800b5354  jle     loc_1800B53E9
0x1800b535a  movzx   esi, si
0x1800b535d  jmp     loc_1800B53E3
0x1800b5362  cmp     eax, 103h
0x1800b5367  jnz     short loc_1800B53DC
0x1800b5369  mov     dword ptr [rdi+20h], 1
0x1800b5370  xor     esi, esi
0x1800b5372  cmp     [rdi+20h], esi
0x1800b5375  jz      loc_1800B5401
0x1800b537b  mov     this, [rdi+18h]
0x1800b537f  mov     [rsp+3D0h+count], esi
0x1800b5383  test    this, this
0x1800b5386  jz      short loc_1800B53C1
0x1800b5388  mov     rax, [this]
0x1800b538b  lea     pceltFetched, [rsp+3D0h+count]
0x1800b5390  mov     celt, r14d
0x1800b5393  sub     r12d, r14d
0x1800b5396  imul    rgelt, rdx, 114h
0x1800b539d  mov     rax, [rax+18h]
0x1800b53a1  mov     celt, r12d
0x1800b53a4  add     rgelt, r13
0x1800b53a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b53ac  test    r15, r15
0x1800b53af  jz      short loc_1800B53B8
0x1800b53b1  mov     ecx, [rsp+3D0h+count]
0x1800b53b5  add     [r15], ecx
0x1800b53b8  test    eax, eax
0x1800b53ba  js      short loc_1800B53C1
0x1800b53bc  cmp     eax, 1
0x1800b53bf  jnz     short loc_1800B5401
0x1800b53c1  test    rbx, rbx
0x1800b53c4  jz      short loc_1800B53D5
0x1800b53c6  mov     this, rbx; SRWLock
0x1800b53c9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b53d0  nop     dword ptr [rax+rax+00h]
0x1800b53d5  mov     eax, 1
0x1800b53da  jmp     short loc_1800B5417
0x1800b53dc  test    eax, eax
0x1800b53de  jle     short loc_1800B53E9
0x1800b53e0  movzx   esi, ax
0x1800b53e3  or      esi, 80070000h
0x1800b53e9  test    rbx, rbx
0x1800b53ec  jz      short loc_1800B53FD
0x1800b53ee  mov     this, rbx; SRWLock
0x1800b53f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b53f8  nop     dword ptr [rax+rax+00h]
0x1800b53fd  mov     eax, esi
0x1800b53ff  jmp     short loc_1800B5417
0x1800b5401  test    rbx, rbx
0x1800b5404  jz      short loc_1800B5415
0x1800b5406  mov     this, rbx; SRWLock
0x1800b5409  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b5410  nop     dword ptr [rax+rax+00h]
0x1800b5415  xor     eax, eax
0x1800b5417  mov     this, [rbp+2D0h+var_50]
0x1800b541e  xor     this, rsp; StackCookie
0x1800b5421  call    __security_check_cookie
0x1800b5426  add     rsp, 398h
0x1800b542d  pop     r15
0x1800b542f  pop     r14
0x1800b5431  pop     r13
0x1800b5433  pop     r12
0x1800b5435  pop     rdi
0x1800b5436  pop     rsi
0x1800b5437  pop     rbx
0x1800b5438  pop     rbp
0x1800b5439  retn
```
