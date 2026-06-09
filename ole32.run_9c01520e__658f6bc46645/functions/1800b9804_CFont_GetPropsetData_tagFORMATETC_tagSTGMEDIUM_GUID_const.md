# CFont::GetPropsetData(tagFORMATETC *,tagSTGMEDIUM *,_GUID const &)

- ea: `0x1800b9804`
- end: `0x1800b9c80`
- name: `?GetPropsetData@CFont@@QEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@AEBU_GUID@@@Z`
- size: `1148`
- prototype: `HRESULT __fastcall(CFont *this, tagFORMATETC *lpFormatEtc, tagSTGMEDIUM *lpStgMedium, const _GUID *lpFormatEtc)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b9750`

## callees

- `0x180036d90`
- `0x180046460`
- `0x1800b9804`
- `0x1800c2464`
- `0x1800c269c`
- `0x1800c2770`
- `0x1800c3948`
- `0x1800c3a30`
- `0x1800c4458`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9a3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b9a3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b98a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b98c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b98a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x1800b98c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b9aa6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b9aa6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b9959`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b9959`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800b9992`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x1800b9992`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800b99b6`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800b99b6`

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
  DWORD tymed; // r14d
  HRESULT result; // eax
  DWORD v9; // r12d
  CPropertySection *v10; // rax
  CPropertySection *v11; // rsi
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
  tymed = lpStgMedium->tymed;
  if ( (lpFormatEtc->tymed & 0xC) == 0 )
    return -2147024809;
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
0x1800b9804  mov     rax, rsp
0x1800b9807  mov     [rax+10h], rbx
0x1800b980b  push    rbp
0x1800b980c  push    rsi
0x1800b980d  push    rdi
0x1800b980e  push    r12
0x1800b9810  push    r13
0x1800b9812  push    r14
0x1800b9814  push    r15
0x1800b9816  lea     rbp, [rax-5Fh]
0x1800b981a  sub     rsp, 0C0h
0x1800b9821  movaps  xmmword ptr [rax-48h], xmm6
0x1800b9825  mov     rax, cs:__security_cookie
0x1800b982c  xor     rax, rsp
0x1800b982f  mov     [rbp+57h+var_48], rax
0x1800b9833  mov     rdi, lpStgMedium
0x1800b9836  mov     r13, lpFormatEtc
0x1800b9839  mov     r15, this
0x1800b983c  xor     esi, esi
0x1800b983e  test    lpFormatEtc, lpFormatEtc
0x1800b9841  jz      loc_1800B9C4E
0x1800b9847  test    lpStgMedium, lpStgMedium
0x1800b984a  jz      loc_1800B9C4E
0x1800b9850  mov     r14d, [lpStgMedium]
0x1800b9853  test    byte ptr [lpFormatEtc+18h], 0Ch
0x1800b9857  jnz     short loc_1800B9863
0x1800b9859  mov     eax, 80070057h
0x1800b985e  jmp     loc_1800B9C53
0x1800b9863  mov     [rbp+57h+ppstgOpen], rsi
0x1800b9867  mov     [rbp+57h+lpStorage], rsi
0x1800b986b  mov     eax, 1
0x1800b9870  lea     r12d, [rax+3]
0x1800b9874  test    [lpFormatEtc+18h], r12b
0x1800b9878  jz      loc_1800B9977
0x1800b987e  test    r14d, r14d
0x1800b9881  jz      loc_1800B9951
0x1800b9887  mov     rax, [lpStgMedium+8]
0x1800b988b  mov     [rbp+57h+lpStorage], rax
0x1800b988f  movups  xmm6, xmmword ptr cs:CLSID_StdFont.Data1
0x1800b9896  mov     qword ptr [rbp+57h+pset.m_SectionList.m_nSize], rsi
0x1800b989a  mov     qword ptr [rbp+57h+pset.m_SectionList+14h], rsi
0x1800b989e  mov     [rbp+57h+pset.m_SectionList.m_nGrowBy], esi
0x1800b98a1  mov     [rbp+57h+pset.m_PH.clsID.Data1], 0FFFEh
0x1800b98a8  call    cs:__imp_GetVersion
0x1800b98af  nop     dword ptr [rax+rax+00h]
0x1800b98b4  movzx   ecx, ax
0x1800b98b7  mov     ebx, 20000h
0x1800b98bc  or      ecx, ebx
0x1800b98be  mov     dword ptr [rbp+57h+pset.m_PH.clsID.Data2], ecx
0x1800b98c1  movdqu  xmmword ptr [rbp+57h+pset.m_PH.clsID.Data4], xmm6
0x1800b98c6  mov     dword ptr [rbp+57h+pset.m_SectionList.m_pData], esi
0x1800b98c9  call    cs:__imp_GetVersion
0x1800b98d0  nop     dword ptr [rax+rax+00h]
0x1800b98d5  movzx   ecx, ax
0x1800b98d8  or      ecx, ebx
0x1800b98da  mov     dword ptr [rbp+57h+pset.m_PH.clsID.Data2], ecx
0x1800b98dd  movups  xmm0, xmmword ptr cs:CLSID_PersistPropset.Data1
0x1800b98e4  movdqu  xmmword ptr [rbp+57h+pplkbyt], xmm0
0x1800b98e9  lea     lpFormatEtc, [rbp+57h+pplkbyt]
0x1800b98ed  lea     this, [rbp+57h+pset.m_PH.clsID]
0x1800b98f1  call    ?AddSection@CPropertySet@@QEAAPEAVCPropertySection@@U_GUID@@@Z; CPropertySet::AddSection(_GUID)
0x1800b98f6  mov     rsi, rax
0x1800b98f9  test    rax, rax
0x1800b98fc  jnz     loc_1800B9A2D
0x1800b9902  test    r14d, r14d
0x1800b9905  jnz     short loc_1800B992C
0x1800b9907  mov     this, [rbp+57h+lpStorage]
0x1800b990b  mov     rax, [this]
0x1800b990e  mov     rax, [rax+10h]
0x1800b9912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9917  mov     this, [rbp+57h+ppstgOpen]
0x1800b991b  test    this, this
0x1800b991e  jz      short loc_1800B992C
0x1800b9920  mov     rax, [this]
0x1800b9923  mov     rax, [rax+10h]
0x1800b9927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b992c  test    [r13+18h], r12b
0x1800b9930  jnz     short loc_1800B9947
0x1800b9932  test    r14d, r14d
0x1800b9935  jz      short loc_1800B9947
0x1800b9937  mov     this, [rbp+57h+lpStorage]
0x1800b993b  mov     rax, [this]
0x1800b993e  mov     rax, [rax+10h]
0x1800b9942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9947  mov     ebx, 8007000Eh
0x1800b994c  jmp     loc_1800B9C04
0x1800b9951  lea     lpStgMedium, [rbp+57h+lpStorage]; ppstm
0x1800b9955  mov     edx, eax; fDeleteOnRelease
0x1800b9957  xor     ecx, ecx; hGlobal
0x1800b9959  call    cs:__imp_CreateStreamOnHGlobal
0x1800b9960  nop     dword ptr [rax+rax+00h]
0x1800b9965  test    eax, eax
0x1800b9967  jns     loc_1800B988F
0x1800b996d  mov     eax, 8007000Eh
0x1800b9972  jmp     loc_1800B9C53
0x1800b9977  test    r14d, r14d
0x1800b997a  jz      short loc_1800B9986
0x1800b997c  mov     this, [lpStgMedium+8]
0x1800b9980  mov     [rbp+57h+ppstgOpen], this
0x1800b9984  jmp     short loc_1800B99E3
0x1800b9986  mov     [rbp+57h+pplkbyt], rsi
0x1800b998a  lea     lpStgMedium, [rbp+57h+pplkbyt]; pplkbyt
0x1800b998e  mov     edx, eax; fDeleteOnRelease
0x1800b9990  xor     ecx, ecx; hGlobal
0x1800b9992  call    cs:__imp_CreateILockBytesOnHGlobal
0x1800b9999  nop     dword ptr [rax+rax+00h]
0x1800b999e  test    eax, eax
0x1800b99a0  js      loc_1800B9C53
0x1800b99a6  lea     r9, [rbp+57h+ppstgOpen]; ppstgOpen
0x1800b99aa  xor     r8d, r8d; reserved
0x1800b99ad  mov     edx, 1012h; grfMode
0x1800b99b2  mov     this, [rbp+57h+pplkbyt]; plkbyt
0x1800b99b6  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800b99bd  nop     dword ptr [rax+rax+00h]
0x1800b99c2  mov     ebx, eax
0x1800b99c4  mov     this, [rbp+57h+pplkbyt]
0x1800b99c8  mov     lpFormatEtc, [this]
0x1800b99cb  mov     rax, [lpFormatEtc+10h]
0x1800b99cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99d4  test    ebx, ebx
0x1800b99d6  jns     short loc_1800B99DF
0x1800b99d8  mov     eax, ebx
0x1800b99da  jmp     loc_1800B9C53
0x1800b99df  mov     this, [rbp+57h+ppstgOpen]
0x1800b99e3  mov     rax, [this]
0x1800b99e6  lea     lpFormatEtc, [rbp+57h+lpStorage]
0x1800b99ea  mov     [rsp+0F0h+var_C8], lpFormatEtc
0x1800b99ef  mov     dword ptr [rsp+0F0h+var_D0], esi
0x1800b99f3  xor     r9d, r9d
0x1800b99f6  mov     r8d, 1012h
0x1800b99fc  lea     lpFormatEtc, _szPropStream
0x1800b9a03  mov     rax, [rax+18h]
0x1800b9a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a0c  mov     ebx, eax
0x1800b9a0e  test    eax, eax
0x1800b9a10  jns     loc_1800B988F
0x1800b9a16  test    r14d, r14d
0x1800b9a19  jnz     short loc_1800B99D8
0x1800b9a1b  mov     this, [rbp+57h+ppstgOpen]
0x1800b9a1f  mov     lpFormatEtc, [this]
0x1800b9a22  mov     rax, [lpFormatEtc+10h]
0x1800b9a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a2b  jmp     short loc_1800B99D8
0x1800b9a2d  mov     lpStgMedium, [rax+58h]; lpMem
0x1800b9a31  xor     edx, edx; dwFlags
0x1800b9a33  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800b9a3a  call    cs:__imp_HeapFree
0x1800b9a41  nop     dword ptr [rax+rax+00h]
0x1800b9a46  lea     this, aFont; "Font"
0x1800b9a4d  call    ?CopyStringLower@@YAPEAGPEBG@Z; CopyStringLower(ushort const *)
0x1800b9a52  mov     [rsi+58h], rax
0x1800b9a56  mov     this, r15; this
0x1800b9a59  call    ?UpdateFont@CFont@@QEAAJXZ; CFont::UpdateFont(void)
0x1800b9a5e  mov     ebx, eax
0x1800b9a60  test    eax, eax
0x1800b9a62  js      loc_1800B9C04
0x1800b9a68  and     [rbp+57h+pplkbyt], 0
0x1800b9a6d  mov     rax, [r15]
0x1800b9a70  lea     lpFormatEtc, [rbp+57h+pplkbyt]
0x1800b9a74  mov     this, r15
0x1800b9a77  mov     rax, [rax+18h]
0x1800b9a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a80  mov     ebx, eax
0x1800b9a82  test    eax, eax
0x1800b9a84  js      loc_1800B9C04
0x1800b9a8a  mov     r9d, 8; dwType
0x1800b9a90  mov     lpStgMedium, [rbp+57h+pplkbyt]; pValue
0x1800b9a94  lea     edx, [r9-6]; dwPropID
0x1800b9a98  mov     this, rsi; this
0x1800b9a9b  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b9aa0  mov     ebx, eax
0x1800b9aa2  mov     this, [rbp+57h+pplkbyt]; bstrString
0x1800b9aa6  call    cs:__imp_SysFreeString
0x1800b9aad  nop     dword ptr [rax+rax+00h]
0x1800b9ab2  test    ebx, ebx
0x1800b9ab4  jz      loc_1800B9BFF
0x1800b9aba  lea     lpStgMedium, [r15+98h]; pValue
0x1800b9ac1  mov     ebx, 2
0x1800b9ac6  mov     r9d, ebx; dwType
0x1800b9ac9  lea     edx, [rbx+8]; dwPropID
0x1800b9acc  mov     this, rsi; this
0x1800b9acf  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b9ad4  test    eax, eax
0x1800b9ad6  jz      loc_1800B9BFF
0x1800b9adc  lea     lpStgMedium, [r15+9Ah]; pValue
0x1800b9ae3  mov     r9d, ebx; dwType
0x1800b9ae6  lea     edx, [rbx+7]; dwPropID
0x1800b9ae9  mov     this, rsi; this
0x1800b9aec  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b9af1  test    eax, eax
0x1800b9af3  jz      loc_1800B9BFF
0x1800b9af9  lea     lpStgMedium, [r15+88h]; pValue
0x1800b9b00  lea     r9d, [rbx+4]; dwType
0x1800b9b04  mov     edx, r12d; dwPropID
0x1800b9b07  mov     this, rsi; this
0x1800b9b0a  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b9b0f  test    eax, eax
0x1800b9b11  jz      loc_1800B9BFF
0x1800b9b17  movzx   eax, byte ptr [r15+9Ch]
0x1800b9b1f  shr     eax, 2
0x1800b9b22  and     eax, 1
0x1800b9b25  mov     dword ptr [rbp+57h+lpStream], eax
0x1800b9b28  mov     ebx, 0Bh
0x1800b9b2d  mov     r9d, ebx; dwType
0x1800b9b30  lea     lpStgMedium, [rbp+57h+lpStream]; pValue
0x1800b9b34  lea     edx, [rbx-4]; dwPropID
0x1800b9b37  mov     this, rsi; this
0x1800b9b3a  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b9b3f  test    eax, eax
0x1800b9b41  jz      loc_1800B9BFF
0x1800b9b47  movzx   eax, byte ptr [r15+9Ch]
0x1800b9b4f  shr     eax, 1
0x1800b9b51  and     eax, 1
0x1800b9b54  mov     dword ptr [rbp+57h+lpStream], eax
0x1800b9b57  mov     r9d, ebx; dwType
0x1800b9b5a  lea     lpStgMedium, [rbp+57h+lpStream]; pValue
0x1800b9b5e  lea     edx, [rbx-5]; dwPropID
0x1800b9b61  mov     this, rsi; this
0x1800b9b64  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b9b69  test    eax, eax
0x1800b9b6b  jz      loc_1800B9BFF
0x1800b9b71  movzx   eax, byte ptr [r15+9Ch]
0x1800b9b79  shr     eax, 3
0x1800b9b7c  and     eax, 1
0x1800b9b7f  mov     dword ptr [rbp+57h+lpStream], eax
0x1800b9b82  mov     r9d, ebx; dwType
0x1800b9b85  lea     lpStgMedium, [rbp+57h+lpStream]; pValue
0x1800b9b89  lea     r15d, [rbx-3]
0x1800b9b8d  mov     edx, r15d; dwPropID
0x1800b9b90  mov     this, rsi; this
0x1800b9b93  call    ?Set@CPropertySection@@QEAAHKPEAXK@Z; CPropertySection::Set(ulong,void *,ulong)
0x1800b9b98  test    eax, eax
0x1800b9b9a  jz      short loc_1800B9BFF
0x1800b9b9c  lea     rbx, Table
0x1800b9ba3  mov     lpStgMedium, [rbx]; pszName
0x1800b9ba6  test    lpStgMedium, lpStgMedium
0x1800b9ba9  jz      short loc_1800B9BC4
0x1800b9bab  mov     edx, [rbx+0Ch]
0x1800b9bae  cmp     edx, 3
0x1800b9bb1  jz      short loc_1800B9BBE
0x1800b9bb3  add     edx, 2; dwPropID
0x1800b9bb6  mov     this, rsi; this
0x1800b9bb9  call    ?SetName@CPropertySection@@QEAAHKPEBG@Z; CPropertySection::SetName(ulong,ushort const *)
0x1800b9bbe  add     rbx, 10h
0x1800b9bc2  jmp     short loc_1800B9BA3
0x1800b9bc4  mov     lpFormatEtc, [rbp+57h+lpStorage]; pIStream
0x1800b9bc8  lea     this, [rbp+57h+pset.m_PH.clsID]; this
0x1800b9bcc  call    ?WriteToStream@CPropertySet@@QEAAHPEAUIStream@@@Z; CPropertySet::WriteToStream(IStream *)
0x1800b9bd1  test    eax, eax
0x1800b9bd3  jnz     short loc_1800B9C12
0x1800b9bd5  test    r14d, r14d
0x1800b9bd8  jnz     short loc_1800B9BFF
0x1800b9bda  mov     this, [rbp+57h+lpStorage]
0x1800b9bde  mov     rax, [this]
0x1800b9be1  mov     rax, [rax+10h]
0x1800b9be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9bea  mov     this, [rbp+57h+ppstgOpen]
0x1800b9bee  test    this, this
0x1800b9bf1  jz      short loc_1800B9BFF
0x1800b9bf3  mov     rax, [this]
0x1800b9bf6  mov     rax, [rax+10h]
0x1800b9bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9bff  mov     ebx, 80004005h
0x1800b9c04  lea     this, [rbp+57h+pset.m_PH.clsID]; this
0x1800b9c08  call    ??1CPropertySet@@QEAA@XZ; CPropertySet::~CPropertySet(void)
0x1800b9c0d  jmp     loc_1800B99D8
0x1800b9c12  test    [r13+18h], r12b
0x1800b9c16  jz      short loc_1800B9C1E
0x1800b9c18  mov     rax, [rbp+57h+lpStorage]
0x1800b9c1c  jmp     short loc_1800B9C35
0x1800b9c1e  mov     this, [rbp+57h+lpStorage]
0x1800b9c22  mov     rax, [this]
0x1800b9c25  mov     rax, [rax+10h]
0x1800b9c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c2e  mov     rax, [rbp+57h+ppstgOpen]
0x1800b9c32  mov     r12d, r15d
0x1800b9c35  mov     [rdi+8], rax
0x1800b9c39  mov     [rdi], r12d
0x1800b9c3c  and     qword ptr [rdi+10h], 0
0x1800b9c41  lea     this, [rbp+57h+pset.m_PH.clsID]; this
0x1800b9c45  call    ??1CPropertySet@@QEAA@XZ; CPropertySet::~CPropertySet(void)
0x1800b9c4a  xor     eax, eax
0x1800b9c4c  jmp     short loc_1800B9C53
0x1800b9c4e  mov     eax, 80004003h
0x1800b9c53  mov     this, [rbp+57h+var_48]
0x1800b9c57  xor     this, rsp; StackCookie
0x1800b9c5a  call    __security_check_cookie
0x1800b9c5f  lea     r11, [rsp+0F0h+var_30]
0x1800b9c67  mov     rbx, [r11+48h]
0x1800b9c6b  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b9c70  mov     rsp, r11
0x1800b9c73  pop     r15
0x1800b9c75  pop     r14
0x1800b9c77  pop     r13
0x1800b9c79  pop     r12
0x1800b9c7b  pop     rdi
0x1800b9c7c  pop     rsi
0x1800b9c7d  pop     rbp
0x1800b9c7e  retn
```
