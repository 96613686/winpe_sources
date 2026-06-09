# CFont::GetPropsetData(tagFORMATETC *,tagSTGMEDIUM *,_GUID const &)

- ea: `0x1800b1594`
- end: `0x1800b19ee`
- name: `?GetPropsetData@CFont@@QEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@AEBU_GUID@@@Z`
- size: `1114`
- prototype: `HRESULT __fastcall(CFont *this, tagFORMATETC *lpFormatEtc, tagSTGMEDIUM *lpStgMedium, const _GUID *lpFormatEtc)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b14e0`

## callees

- `0x18003346c`
- `0x180050940`
- `0x180052390`
- `0x1800b1594`
- `0x1800b9d2c`
- `0x1800b9e08`
- `0x1800baf80`
- `0x1800bb044`
- `0x1800bb9d8`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b17ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b17ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b1639`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b1655`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b1639`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b1655`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1815`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b1815`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b16dd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b16dd`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800b170f`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800b170f`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800b172d`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800b172d`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CFont::GetPropsetData(
        CFont *this,
        tagFORMATETC *lpFormatEtc,
        tagSTGMEDIUM *lpStgMedium,
        const _GUID *a4)
{
  HRESULT result; // eax
  DWORD tymed; // esi
  DWORD v9; // r15d
  CPropertySection *v10; // rax
  CPropertySection *v11; // r14
  HRESULT updated; // ebx
  IStorage *pstg; // rcx
  int v14; // ebx
  const tagFontPropSetTable *i; // rbx
  int memid; // edx
  IStorage *v17; // rax
  IStream *lpStream; // [rsp+48h] [rbp-59h] BYREF
  IStorage *lpStorage; // [rsp+50h] [rbp-51h] BYREF
  IStorage *ppstgOpen; // [rsp+58h] [rbp-49h] BYREF
  _BYTE pplkbyt[68]; // [rsp+68h] [rbp-39h] OVERLAPPED BYREF

  if ( !lpFormatEtc || !lpStgMedium )
    return -2147467261;
  if ( (lpFormatEtc->tymed & 0xC) == 0 )
    return -2147024809;
  tymed = lpStgMedium->tymed;
  ppstgOpen = 0;
  lpStorage = 0;
  v9 = 4;
  if ( (lpFormatEtc->tymed & 4) != 0 )
  {
    if ( tymed )
    {
      lpStorage = lpStgMedium->pstg;
    }
    else if ( CreateStreamOnHGlobal(0, 1, (LPSTREAM *)&lpStorage) < 0 )
    {
      return -2147024882;
    }
  }
  else
  {
    if ( tymed )
    {
      pstg = lpStgMedium->pstg;
      ppstgOpen = pstg;
    }
    else
    {
      *(_QWORD *)pplkbyt = 0;
      result = CreateILockBytesOnHGlobal(0, 1, (LPLOCKBYTES *)pplkbyt);
      if ( result < 0 )
        return result;
      updated = StgCreateDocfileOnILockBytes(*(ILockBytes **)pplkbyt, 0x1012u, 0, &ppstgOpen);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pplkbyt + 16LL))(*(_QWORD *)pplkbyt);
      if ( updated < 0 )
        return updated;
      pstg = ppstgOpen;
    }
    updated = ((__int64 (__fastcall *)(IStorage *, const wchar_t *, __int64, _QWORD, _DWORD, IStorage **))pstg->lpVtbl->CreateStream)(
                pstg,
                szPropStream,
                4114,
                0,
                0,
                &lpStorage);
    if ( updated < 0 )
    {
      if ( !tymed )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
      return updated;
    }
  }
  memset(&pplkbyt[48], 0, 20);
  *(_DWORD *)&pplkbyt[16] = 65534;
  *(_DWORD *)&pplkbyt[20] = (unsigned __int16)GetVersion() | 0x20000;
  *(GUID *)&pplkbyt[24] = CLSID_StdFont;
  *(_DWORD *)&pplkbyt[40] = 0;
  *(_DWORD *)&pplkbyt[20] = (unsigned __int16)GetVersion() | 0x20000;
  *(GUID *)pplkbyt = CLSID_PersistPropset;
  v10 = CPropertySet::AddSection((CPropertySet *)&pplkbyt[16], (_GUID *)pplkbyt);
  v11 = v10;
  if ( !v10 )
  {
    if ( !tymed )
    {
      ((void (__fastcall *)(IStorage *))lpStorage->lpVtbl->Release)(lpStorage);
      if ( ppstgOpen )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    }
    if ( (lpFormatEtc->tymed & 4) == 0 )
    {
      if ( tymed )
        ((void (__fastcall *)(IStorage *))lpStorage->lpVtbl->Release)(lpStorage);
    }
    updated = -2147024882;
    goto LABEL_46;
  }
  HeapFree(g_hHeap, 0, v10->m_pwszSectionName);
  v11->m_pwszSectionName = CopyStringLower(L"Font");
  updated = CFont::UpdateFont(this);
  if ( updated < 0
    || (*(_QWORD *)pplkbyt = 0,
        updated = ((__int64 (__fastcall *)(CFont *, _BYTE *))this->IFont::IUnknown::lpVtbl[1].QueryInterface)(
                    this,
                    pplkbyt),
        updated < 0) )
  {
LABEL_46:
    CPropertySet::~CPropertySet((CPropertySet *)&pplkbyt[16]);
    return updated;
  }
  v14 = CPropertySection::Set(v11, 2u, *(void **)pplkbyt, 8u);
  SysFreeString(*(BSTR *)pplkbyt);
  if ( !v14
    || !CPropertySection::Set(v11, 0xAu, &this->m_fr.sCharset, 2u)
    || !CPropertySection::Set(v11, 9u, &this->m_fr.sWeight, 2u)
    || !CPropertySection::Set(v11, 4u, &this->m_fr, 6u)
    || (LODWORD(lpStream) = (this->m_fr.bFlags >> 2) & 1, !CPropertySection::Set(v11, 7u, &lpStream, 0xBu))
    || (LODWORD(lpStream) = (this->m_fr.bFlags >> 1) & 1, !CPropertySection::Set(v11, 6u, &lpStream, 0xBu))
    || (LODWORD(lpStream) = (this->m_fr.bFlags >> 3) & 1, !CPropertySection::Set(v11, 8u, &lpStream, 0xBu)) )
  {
LABEL_45:
    updated = -2147467259;
    goto LABEL_46;
  }
  for ( i = Table; i->lpname; ++i )
  {
    memid = i->memid;
    if ( memid != 3 )
      CPropertySection::SetName(v11, memid + 2, i->lpname);
  }
  if ( !CPropertySet::WriteToStream((CPropertySet *)&pplkbyt[16], (IStream *)lpStorage) )
  {
    if ( !tymed )
    {
      ((void (__fastcall *)(IStorage *))lpStorage->lpVtbl->Release)(lpStorage);
      if ( ppstgOpen )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    }
    goto LABEL_45;
  }
  if ( (lpFormatEtc->tymed & 4) != 0 )
  {
    v17 = lpStorage;
  }
  else
  {
    ((void (__fastcall *)(IStorage *))lpStorage->lpVtbl->Release)(lpStorage);
    v17 = ppstgOpen;
    v9 = 8;
  }
  lpStgMedium->hBitmap = (HBITMAP)v17;
  lpStgMedium->tymed = v9;
  lpStgMedium->pUnkForRelease = 0;
  CPropertySet::~CPropertySet((CPropertySet *)&pplkbyt[16]);
  return 0;
}

```

## disassembly

```asm
0x1800b1594  mov     rax, rsp
0x1800b1597  mov     [rax+10h], rbx
0x1800b159b  push    rbp
0x1800b159c  push    rsi
0x1800b159d  push    rdi
0x1800b159e  push    r12
0x1800b15a0  push    r13
0x1800b15a2  push    r14
0x1800b15a4  push    r15
0x1800b15a6  lea     rbp, [rax-5Fh]
0x1800b15aa  sub     rsp, 0C0h
0x1800b15b1  movaps  xmmword ptr [rax-48h], xmm6
0x1800b15b5  mov     rax, cs:__security_cookie
0x1800b15bc  xor     rax, rsp
0x1800b15bf  mov     [rbp+57h+var_48], rax
0x1800b15c3  mov     rdi, lpStgMedium
0x1800b15c6  mov     r13, lpFormatEtc
0x1800b15c9  mov     r12, this
0x1800b15cc  xor     r14d, r14d
0x1800b15cf  test    lpFormatEtc, lpFormatEtc
0x1800b15d2  jz      loc_1800B19BD
0x1800b15d8  test    lpStgMedium, lpStgMedium
0x1800b15db  jz      loc_1800B19BD
0x1800b15e1  test    byte ptr [lpFormatEtc+18h], 0Ch
0x1800b15e5  jnz     short loc_1800B15F1
0x1800b15e7  mov     eax, 80070057h
0x1800b15ec  jmp     loc_1800B19C2
0x1800b15f1  mov     esi, [lpStgMedium]
0x1800b15f4  mov     [rbp+57h+ppstgOpen], r14
0x1800b15f8  mov     [rbp+57h+lpStorage], r14
0x1800b15fc  mov     eax, 1
0x1800b1601  lea     r15d, [rax+3]
0x1800b1605  test    [lpFormatEtc+18h], r15b
0x1800b1609  jz      loc_1800B16F5
0x1800b160f  test    esi, esi
0x1800b1611  jz      loc_1800B16D5
0x1800b1617  mov     rax, [lpStgMedium+8]
0x1800b161b  mov     [rbp+57h+lpStorage], rax
0x1800b161f  movups  xmm6, xmmword ptr cs:CLSID_StdFont.Data1
0x1800b1626  mov     qword ptr [rbp+57h+pset.m_SectionList.m_nSize], r14
0x1800b162a  mov     qword ptr [rbp+57h+pset.m_SectionList+14h], r14
0x1800b162e  mov     [rbp+57h+pset.m_SectionList.m_nGrowBy], r14d
0x1800b1632  mov     [rbp+57h+pset.m_PH.clsID.Data1], 0FFFEh
0x1800b1639  call    cs:__imp_GetVersion
0x1800b163f  movzx   ecx, ax
0x1800b1642  mov     ebx, 20000h
0x1800b1647  or      ecx, ebx
0x1800b1649  mov     dword ptr [rbp+57h+pset.m_PH.clsID.Data2], ecx
0x1800b164c  movdqu  xmmword ptr [rbp+57h+pset.m_PH.clsID.Data4], xmm6
0x1800b1651  mov     dword ptr [rbp+57h+pset.m_SectionList.m_pData], r14d
0x1800b1655  call    cs:__imp_GetVersion
0x1800b165b  movzx   ecx, ax
0x1800b165e  or      ecx, ebx
0x1800b1660  mov     dword ptr [rbp+57h+pset.m_PH.clsID.Data2], ecx
0x1800b1663  movups  xmm0, xmmword ptr cs:CLSID_PersistPropset.Data1
0x1800b166a  movdqu  xmmword ptr [rbp+57h+pplkbyt], xmm0
0x1800b166f  lea     lpFormatEtc, [rbp+57h+pplkbyt]
0x1800b1673  lea     this, [rbp+57h+pset.m_PH.clsID]
0x1800b1677  call    ?AddSection@CPropertySet@@QEAAPEAVCPropertySection@@U_GUID@@@Z; CPropertySet::AddSection(_GUID)
0x1800b167c  mov     r14, rax
0x1800b167f  test    rax, rax
0x1800b1682  jnz     loc_1800B179E
0x1800b1688  test    esi, esi
0x1800b168a  jnz     short loc_1800B16B1
0x1800b168c  mov     this, [rbp+57h+lpStorage]
0x1800b1690  mov     rax, [this]
0x1800b1693  mov     rax, [rax+10h]
0x1800b1697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b169c  mov     this, [rbp+57h+ppstgOpen]
0x1800b16a0  test    this, this
0x1800b16a3  jz      short loc_1800B16B1
0x1800b16a5  mov     rax, [this]
0x1800b16a8  mov     rax, [rax+10h]
0x1800b16ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b16b1  test    [r13+18h], r15b
0x1800b16b5  jnz     short loc_1800B16CB
0x1800b16b7  test    esi, esi
0x1800b16b9  jz      short loc_1800B16CB
0x1800b16bb  mov     this, [rbp+57h+lpStorage]
0x1800b16bf  mov     rax, [this]
0x1800b16c2  mov     rax, [rax+10h]
0x1800b16c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b16cb  mov     ebx, 8007000Eh
0x1800b16d0  jmp     loc_1800B1970
0x1800b16d5  lea     lpStgMedium, [rbp+57h+lpStorage]; ppstm
0x1800b16d9  mov     edx, eax; fDeleteOnRelease
0x1800b16db  xor     ecx, ecx; hGlobal
0x1800b16dd  call    cs:__imp_CreateStreamOnHGlobal
0x1800b16e3  test    eax, eax
0x1800b16e5  jns     loc_1800B161F
0x1800b16eb  mov     eax, 8007000Eh
0x1800b16f0  jmp     loc_1800B19C2
0x1800b16f5  test    esi, esi
0x1800b16f7  jz      short loc_1800B1703
0x1800b16f9  mov     this, [lpStgMedium+8]
0x1800b16fd  mov     [rbp+57h+ppstgOpen], this
0x1800b1701  jmp     short loc_1800B1754
0x1800b1703  mov     [rbp+57h+pplkbyt], r14
0x1800b1707  lea     lpStgMedium, [rbp+57h+pplkbyt]; pplkbyt
0x1800b170b  mov     edx, eax; fDeleteOnRelease
0x1800b170d  xor     ecx, ecx; hGlobal
0x1800b170f  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800b1715  test    eax, eax
0x1800b1717  js      loc_1800B19C2
0x1800b171d  lea     r9, [rbp+57h+ppstgOpen]; ppstgOpen
0x1800b1721  xor     r8d, r8d; reserved
0x1800b1724  mov     edx, 1012h; grfMode
0x1800b1729  mov     this, [rbp+57h+pplkbyt]; plkbyt
0x1800b172d  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800b1733  mov     ebx, eax
0x1800b1735  mov     this, [rbp+57h+pplkbyt]
0x1800b1739  mov     lpFormatEtc, [this]
0x1800b173c  mov     rax, [lpFormatEtc+10h]
0x1800b1740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1745  test    ebx, ebx
0x1800b1747  jns     short loc_1800B1750
0x1800b1749  mov     eax, ebx
0x1800b174b  jmp     loc_1800B19C2
0x1800b1750  mov     this, [rbp+57h+ppstgOpen]
0x1800b1754  mov     rax, [this]
0x1800b1757  lea     lpFormatEtc, [rbp+57h+lpStorage]
0x1800b175b  mov     [rsp+0F0h+var_C8], lpFormatEtc
0x1800b1760  mov     dword ptr [rsp+0F0h+var_D0], r14d
0x1800b1765  xor     r9d, r9d
0x1800b1768  mov     r8d, 1012h
0x1800b176e  lea     lpFormatEtc, _szPropStream
0x1800b1775  mov     rax, [rax+18h]
0x1800b1779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b177e  mov     ebx, eax
0x1800b1780  test    eax, eax
0x1800b1782  jns     loc_1800B161F
0x1800b1788  test    esi, esi
0x1800b178a  jnz     short loc_1800B1749
0x1800b178c  mov     this, [rbp+57h+ppstgOpen]
0x1800b1790  mov     lpFormatEtc, [this]
0x1800b1793  mov     rax, [lpFormatEtc+10h]
0x1800b1797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b179c  jmp     short loc_1800B1749
0x1800b179e  mov     lpStgMedium, [rax+58h]; lpMem
0x1800b17a2  xor     edx, edx; dwFlags
0x1800b17a4  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800b17ab  call    cs:__imp_HeapFree
0x1800b17b1  lea     this, aFont; "Font"
0x1800b17b8  call    ?CopyStringLower@@YAPEAGPEBG@Z; CopyStringLower(ushort const *)
0x1800b17bd  mov     [r14+58h], rax
0x1800b17c1  mov     this, r12; this
0x1800b17c4  call    ?UpdateFont@CFont@@QEAAJXZ; CFont::UpdateFont(void)
0x1800b17c9  mov     ebx, eax
0x1800b17cb  test    eax, eax
0x1800b17cd  js      loc_1800B1970
0x1800b17d3  mov     [rbp+57h+pplkbyt], 0
0x1800b17db  mov     rax, [r12]
0x1800b17df  lea     lpFormatEtc, [rbp+57h+pplkbyt]
0x1800b17e3  mov     this, r12
0x1800b17e6  mov     rax, [rax+18h]
0x1800b17ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b17ef  mov     ebx, eax
0x1800b17f1  test    eax, eax
0x1800b17f3  js      loc_1800B1970
0x1800b17f9  mov     r9d, 8; dwType
0x1800b17ff  mov     lpStgMedium, [rbp+57h+pplkbyt]; pValue
0x1800b1803  lea     edx, [r9-6]; dwPropID
0x1800b1807  mov     this, r14; this
0x1800b180a  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b180f  mov     ebx, eax
0x1800b1811  mov     this, [rbp+57h+pplkbyt]; bstrString
0x1800b1815  call    cs:__imp_SysFreeString
0x1800b181b  test    ebx, ebx
0x1800b181d  jz      loc_1800B196B
0x1800b1823  lea     rbx, [r12+88h]
0x1800b182b  lea     lpStgMedium, [rbx+10h]; pValue
0x1800b182f  mov     edx, 0Ah; dwPropID
0x1800b1834  lea     r9d, [lpFormatEtc-8]; dwType
0x1800b1838  mov     this, r14; this
0x1800b183b  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b1840  test    eax, eax
0x1800b1842  jz      loc_1800B196B
0x1800b1848  lea     lpStgMedium, [rbx+12h]; pValue
0x1800b184c  mov     edx, 9; dwPropID
0x1800b1851  lea     r9d, [lpFormatEtc-7]; dwType
0x1800b1855  mov     this, r14; this
0x1800b1858  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b185d  test    eax, eax
0x1800b185f  jz      loc_1800B196B
0x1800b1865  mov     r9d, 6; dwType
0x1800b186b  mov     lpStgMedium, rbx; pValue
0x1800b186e  mov     edx, r15d; dwPropID
0x1800b1871  mov     this, r14; this
0x1800b1874  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b1879  test    eax, eax
0x1800b187b  jz      loc_1800B196B
0x1800b1881  movzx   eax, byte ptr [r12+9Ch]
0x1800b188a  shr     eax, 2
0x1800b188d  and     eax, 1
0x1800b1890  mov     dword ptr [rbp+57h+lpStream], eax
0x1800b1893  mov     ebx, 0Bh
0x1800b1898  mov     r9d, ebx; dwType
0x1800b189b  lea     lpStgMedium, [rbp+57h+lpStream]; pValue
0x1800b189f  lea     edx, [rbx-4]; dwPropID
0x1800b18a2  mov     this, r14; this
0x1800b18a5  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b18aa  test    eax, eax
0x1800b18ac  jz      loc_1800B196B
0x1800b18b2  movzx   eax, byte ptr [r12+9Ch]
0x1800b18bb  shr     eax, 1
0x1800b18bd  and     eax, 1
0x1800b18c0  mov     dword ptr [rbp+57h+lpStream], eax
0x1800b18c3  mov     r9d, ebx; dwType
0x1800b18c6  lea     lpStgMedium, [rbp+57h+lpStream]; pValue
0x1800b18ca  lea     edx, [rbx-5]; dwPropID
0x1800b18cd  mov     this, r14; this
0x1800b18d0  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b18d5  test    eax, eax
0x1800b18d7  jz      loc_1800B196B
0x1800b18dd  movzx   eax, byte ptr [r12+9Ch]
0x1800b18e6  shr     eax, 3
0x1800b18e9  and     eax, 1
0x1800b18ec  mov     dword ptr [rbp+57h+lpStream], eax
0x1800b18ef  mov     r9d, ebx; dwType
0x1800b18f2  lea     lpStgMedium, [rbp+57h+lpStream]; pValue
0x1800b18f6  lea     r12d, [rbx-3]
0x1800b18fa  mov     edx, r12d; dwPropID
0x1800b18fd  mov     this, r14; this
0x1800b1900  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b1905  test    eax, eax
0x1800b1907  jz      short loc_1800B196B
0x1800b1909  lea     rbx, Table
0x1800b1910  mov     lpStgMedium, [rbx]; pszName
0x1800b1913  test    lpStgMedium, lpStgMedium
0x1800b1916  jz      short loc_1800B1931
0x1800b1918  mov     edx, [rbx+0Ch]
0x1800b191b  cmp     edx, 3
0x1800b191e  jz      short loc_1800B192B
0x1800b1920  add     edx, 2; dwPropID
0x1800b1923  mov     this, r14; this
0x1800b1926  call    ?SetName@CPropertySection@@QEAAHKPEBG@Z; CPropertySection::SetName(ulong,ushort const *)
0x1800b192b  add     rbx, 10h
0x1800b192f  jmp     short loc_1800B1910
0x1800b1931  mov     lpFormatEtc, [rbp+57h+lpStorage]; pIStream
0x1800b1935  lea     this, [rbp+57h+pset.m_PH.clsID]; this
0x1800b1939  call    ?WriteToStream@CPropertySet@@QEAAHPEAUIStream@@@Z; CPropertySet::WriteToStream(IStream *)
0x1800b193e  test    eax, eax
0x1800b1940  jnz     short loc_1800B197E
0x1800b1942  test    esi, esi
0x1800b1944  jnz     short loc_1800B196B
0x1800b1946  mov     this, [rbp+57h+lpStorage]
0x1800b194a  mov     rax, [this]
0x1800b194d  mov     rax, [rax+10h]
0x1800b1951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1956  mov     this, [rbp+57h+ppstgOpen]
0x1800b195a  test    this, this
0x1800b195d  jz      short loc_1800B196B
0x1800b195f  mov     rax, [this]
0x1800b1962  mov     rax, [rax+10h]
0x1800b1966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b196b  mov     ebx, 80004005h
0x1800b1970  lea     this, [rbp+57h+pset.m_PH.clsID]; this
0x1800b1974  call    ??1CPropertySet@@QEAA@XZ; CPropertySet::~CPropertySet(void)
0x1800b1979  jmp     loc_1800B1749
0x1800b197e  test    [r13+18h], r15b
0x1800b1982  jz      short loc_1800B198A
0x1800b1984  mov     rax, [rbp+57h+lpStorage]
0x1800b1988  jmp     short loc_1800B19A1
0x1800b198a  mov     this, [rbp+57h+lpStorage]
0x1800b198e  mov     rax, [this]
0x1800b1991  mov     rax, [rax+10h]
0x1800b1995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b199a  mov     rax, [rbp+57h+ppstgOpen]
0x1800b199e  mov     r15d, r12d
0x1800b19a1  mov     [rdi+8], rax
0x1800b19a5  mov     [rdi], r15d
0x1800b19a8  mov     qword ptr [rdi+10h], 0
0x1800b19b0  lea     this, [rbp+57h+pset.m_PH.clsID]; this
0x1800b19b4  call    ??1CPropertySet@@QEAA@XZ; CPropertySet::~CPropertySet(void)
0x1800b19b9  xor     eax, eax
0x1800b19bb  jmp     short loc_1800B19C2
0x1800b19bd  mov     eax, 80004003h
0x1800b19c2  mov     this, [rbp+57h+var_48]
0x1800b19c6  xor     this, rsp; StackCookie
0x1800b19c9  call    __security_check_cookie
0x1800b19ce  lea     r11, [rsp+0F0h+var_30]
0x1800b19d6  mov     rbx, [r11+48h]
0x1800b19da  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b19df  mov     rsp, r11
0x1800b19e2  pop     r15
0x1800b19e4  pop     r14
0x1800b19e6  pop     r13
0x1800b19e8  pop     r12
0x1800b19ea  pop     rdi
0x1800b19eb  pop     rsi
0x1800b19ec  pop     rbp
0x1800b19ed  retn
```
