# CSessionBaseRW::CleanupStagingArea(long *,__int64 *,IFhEngineCleanupProgressEvent *)

- ea: `0x18000cafc`
- end: `0x18000d0f6`
- name: `?CleanupStagingArea@CSessionBaseRW@@IEAAJPEAJPEA_JPEAUIFhEngineCleanupProgressEvent@@@Z`
- size: `1530`
- prototype: `__int64 __fastcall(CSessionBaseRW *__hidden this, int *, __int64 *, struct IFhEngineCleanupProgressEvent *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b4e0`
- `0x1800228b0`

## callees

- `0x1800025b0`
- `0x180002c24`
- `0x1800062d0`
- `0x1800077f0`
- `0x180007818`
- `0x180007970`
- `0x1800079c0`
- `0x180007a9c`
- `0x180007ae4`
- `0x180007c08`
- `0x18000801c`
- `0x180008484`
- `0x180008ac8`
- `0x180008d18`
- `0x180009258`
- `0x18000935c`
- `0x1800093a8`
- `0x180009404`
- `0x1800094d0`
- `0x180009560`
- `0x180009a80`
- `0x18000c360`
- `0x18000cafc`
- `0x18000d4f4`
- `0x180012520`
- `0x1800127b0`
- `0x180030790`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cccc`
- `KERNEL32!GetLastError` at `0x18000cccc`
- `KERNEL32!GetFileAttributesExW` at `0x18000cc9d`
- `KERNEL32!GetFileAttributesExW` at `0x18000cc9d`

## string_xrefs

- `0x18000ce15`: `(hr == HRESULT_FROM_WIN32(ERROR_PATH_NOT_FOUND) || hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))`
- `0x18000ce09`: `Deletion of files should not fail during staging area pruning`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::CleanupStagingArea(
        CSessionBaseRW *this,
        int *a2,
        __int64 *a3,
        struct IFhEngineCleanupProgressEvent *a4)
{
  struct IFhEngineCleanupProgressEvent *v4; // r15
  __int64 v7; // rcx
  CFileRecord *v8; // rax
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // edi
  int v12; // eax
  unsigned __int64 v13; // r15
  unsigned int v14; // r8d
  int v15; // eax
  PVOID *v16; // rcx
  char LastError; // al
  unsigned int v18; // r8d
  _QWORD *v19; // rdi
  _QWORD *v20; // rax
  int v21; // eax
  int v22; // edi
  PVOID *v23; // rcx
  __int64 v24; // rax
  int v25; // eax
  PVOID *v26; // rcx
  __int64 v27; // rdx
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-89h] BYREF
  _QWORD *v33; // [rsp+38h] [rbp-81h] BYREF
  _DWORD *v34; // [rsp+40h] [rbp-79h] BYREF
  struct IFhEngineCleanupProgressEvent *v35; // [rsp+48h] [rbp-71h]
  _DWORD *v36; // [rsp+50h] [rbp-69h] BYREF
  _DWORD *v37; // [rsp+58h] [rbp-61h] BYREF
  int *v38; // [rsp+60h] [rbp-59h]
  __int64 v39; // [rsp+68h] [rbp-51h] BYREF
  __int64 v40; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v41[40]; // [rsp+78h] [rbp-41h] BYREF
  __int128 FileInformation; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v43; // [rsp+B0h] [rbp-9h]
  unsigned int v44; // [rsp+C0h] [rbp+7h]

  v4 = a4;
  v35 = a4;
  v38 = a2;
  v7 = *((_QWORD *)this + 2);
  v33 = (_QWORD *)v7;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  CMultistateFileRecordQuery::CMultistateFileRecordQuery((__int64)v41, (__int64 *)&v33);
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v33);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  v8 = (CFileRecord *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
    v8 = CFileRecord::CFileRecord(v8, (__int64 *)this + 2, (__int64)this + 24);
  SmartPtr<CFileRecord>::operator=(&v33, v8);
  v9 = v33;
  if ( v33 && *v33 )
  {
    v10 = CMultistateFileRecordQuery::Query(v41, 1, 2, 2, 3);
    while ( 1 )
    {
      v11 = v10;
      do
      {
        if ( v11 < 0 )
        {
LABEL_72:
          v12 = 0;
          if ( v11 != -2147023728 )
            v12 = v11;
          v11 = v12;
          if ( v12 >= 0 )
            goto LABEL_88;
          v26 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_80;
          v30 = 133;
LABEL_78:
          WPP_SF_d(v26[2], v30, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, (unsigned int)v12);
LABEL_79:
          v26 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_80;
        }
        FileInformation = 0;
        v43 = 0;
        v44 = 0;
        ATL::CSimpleStringT<unsigned short,0>::Empty(&lpFileName);
        if ( *((_DWORD *)this + 38) )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v29 = 122;
LABEL_70:
            WPP_SF_(v28[2], v29, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids);
          }
LABEL_71:
          v11 = -2147023661;
          goto LABEL_88;
        }
        v34 = v9;
        if ( v9 )
          ++v9[2];
        v12 = CMultistateFileRecordQuery::LoadCurrentRecord(v41, &v34);
        v11 = v12;
        if ( v12 == -2147023728 )
          goto LABEL_72;
        if ( v12 < 0 )
        {
          v26 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v30 = 123;
            goto LABEL_78;
          }
LABEL_80:
          if ( v11 != -2147023661 )
          {
LABEL_85:
            if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 4) != 0 )
              WPP_SF_s(
                v26[2],
                134,
                &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
                "SUCCEEDED(hr) || hr == HRESULT_FROM_WIN32(ERROR_REQUEST_ABORTED)");
          }
          goto LABEL_88;
        }
      }
      while ( *(__int64 *)(*(_QWORD *)v9 + 48LL) < 0 );
      if ( !v4 )
      {
        v13 = -1;
        if ( !a3 )
          goto LABEL_28;
      }
      if ( !*((_DWORD *)lpFileName - 4) )
      {
        v14 = *(_DWORD *)(*(_QWORD *)v9 + 60LL);
        v36 = v9;
        ++v9[2];
        v15 = CSessionBaseRO::ConstructStagingPath((__int64)this + 8, (__int64)&v36, v14, &lpFileName);
        v11 = v15;
        if ( v15 < 0 )
        {
          v26 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_80;
          v27 = 124;
          goto LABEL_54;
        }
      }
      if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
      {
        v13 = v44 + ((unsigned __int64)HIDWORD(v43) << 32);
      }
      else
      {
        v16 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            125,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (_DWORD)lpFileName,
            LastError);
          v16 = (PVOID *)WPP_GLOBAL_Control;
        }
        v13 = *(_QWORD *)(*(_QWORD *)v9 + 48LL);
        if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
          WPP_SF_ss(
            (unsigned int)v16[2],
            126,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)"ret",
            (__int64)"Unable to obtain the size of a presumably staged file");
      }
LABEL_28:
      if ( *(_WORD *)(*(_QWORD *)v9 + 40LL) != 2 )
        break;
      if ( !*((_DWORD *)lpFileName - 4) )
      {
        v18 = *(_DWORD *)(*(_QWORD *)v9 + 60LL);
        v37 = v9;
        ++v9[2];
        v15 = CSessionBaseRO::ConstructStagingPath((__int64)this + 8, (__int64)&v37, v18, &lpFileName);
        v11 = v15;
        if ( v15 < 0 )
        {
          v26 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_80;
          v27 = 127;
          goto LABEL_54;
        }
      }
      v19 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v39,
              (_QWORD *)this + 7);
      v20 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v40,
              &lpFileName);
      v21 = FheFileOperations::DeleteFileWithEmptyParents(v20, v19);
      v22 = v21;
      if ( v21 < 0 )
      {
        v23 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (_DWORD)lpFileName,
            v21);
          v23 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( (unsigned int)(v22 + 2147024894) > 1 && v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 4) != 0 )
          WPP_SF_ss(
            (unsigned int)v23[2],
            129,
            (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
            (unsigned int)"(hr == HRESULT_FROM_WIN32(ERROR_PATH_NOT_FOUND) || hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))",
            (__int64)"Deletion of files should not fail during staging area pruning");
      }
      v34 = v9;
      ++v9[2];
      CSessionBaseRW::ChangeFileRecordStatus(this, &v34, 16);
      v24 = *(_QWORD *)v9;
      *(_DWORD *)(v24 + 76) = 1;
      *(_WORD *)(v24 + 40) = 1;
      v25 = CFileRecord::Commit(*(CFileRecord **)v9);
      v11 = v25;
      if ( v25 < 0 )
      {
        v26 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_80;
        WPP_SF_dSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          130,
          (unsigned int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          *(_DWORD *)(*(_QWORD *)v9 + 16LL),
          (__int64)lpFileName,
          v25);
        goto LABEL_79;
      }
LABEL_44:
      if ( v35
        && (*(unsigned int (__fastcall **)(struct IFhEngineCleanupProgressEvent *, unsigned __int64))(*(_QWORD *)v35 + 40LL))(
             v35,
             v13) == -2147467260 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v29 = 132;
          goto LABEL_70;
        }
        goto LABEL_71;
      }
      if ( v38 )
        ++*v38;
      if ( a3 )
        *a3 += v13;
      v10 = CMultistateFileRecordQuery::MoveNext((CMultistateFileRecordQuery *)v41);
      v4 = v35;
    }
    v34 = v9;
    ++v9[2];
    v15 = CSessionBaseRW::DeleteFileVersion(this);
    v11 = v15;
    if ( v15 >= 0 )
      goto LABEL_44;
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_80;
    v27 = 131;
LABEL_54:
    WPP_SF_dd(
      v26[2],
      v27,
      &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
      *(unsigned int *)(*(_QWORD *)v9 + 16LL),
      v15);
    goto LABEL_79;
  }
  v11 = -2147024882;
  v26 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids, "fileRecord");
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_85;
  }
LABEL_88:
  ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
  SmartPtr<CFileRecord>::~SmartPtr<CFileRecord>(&v33);
  CMultistateFileRecordQuery::~CMultistateFileRecordQuery((CMultistateFileRecordQuery *)v41);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000cafc  push    rbp
0x18000cafe  push    rbx
0x18000caff  push    rsi
0x18000cb00  push    rdi
0x18000cb01  push    r12
0x18000cb03  push    r13
0x18000cb05  push    r14
0x18000cb07  push    r15
0x18000cb09  lea     rbp, [rsp-1Fh]
0x18000cb0e  sub     rsp, 0D8h
0x18000cb15  mov     rax, cs:__security_cookie
0x18000cb1c  xor     rax, rsp
0x18000cb1f  mov     [rbp+57h+var_48], rax
0x18000cb23  mov     r15, r9
0x18000cb26  mov     [rbp+57h+var_C8], r9
0x18000cb2a  mov     r12, r8
0x18000cb2d  mov     [rbp+57h+var_B0], rdx
0x18000cb31  mov     r13, rcx
0x18000cb34  mov     rcx, [rcx+10h]
0x18000cb38  mov     [rsp+110h+var_D8], rcx
0x18000cb3d  test    rcx, rcx
0x18000cb40  jz      short loc_18000CB4F
0x18000cb42  mov     rax, [rcx]
0x18000cb45  mov     rax, [rax+8]
0x18000cb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb4e  nop
0x18000cb4f  lea     rdx, [rsp+110h+var_D8]
0x18000cb54  lea     rcx, [rbp+57h+var_98]
0x18000cb58  call    ??0CMultistateFileRecordQuery@@QEAA@V?$CComPtr@UIFhCatalog@@@ATL@@@Z; CMultistateFileRecordQuery::CMultistateFileRecordQuery(ATL::CComPtr<IFhCatalog>)
0x18000cb5d  lea     rcx, [rsp+110h+var_D8]
0x18000cb62  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18000cb67  lea     rcx, [rsp+110h+lpFileName]
0x18000cb6c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000cb71  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cb78  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000cb7d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cb82  test    rax, rax
0x18000cb85  jz      short loc_18000CB97
0x18000cb87  lea     r8, [r13+18h]
0x18000cb8b  lea     rdx, [r13+10h]
0x18000cb8f  mov     rcx, rax; this
0x18000cb92  call    ??0CFileRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CFileRecord::CFileRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x18000cb97  mov     rdx, rax
0x18000cb9a  lea     rcx, [rsp+110h+var_D8]
0x18000cb9f  call    ??4?$SmartPtr@VCFileRecord@@@@QEAAAEAV0@PEAVCFileRecord@@@Z; SmartPtr<CFileRecord>::operator=(CFileRecord *)
0x18000cba4  mov     rbx, [rsp+110h+var_D8]
0x18000cba9  test    rbx, rbx
0x18000cbac  jz      loc_18000D048
0x18000cbb2  cmp     qword ptr [rbx], 0
0x18000cbb6  jz      loc_18000D048
0x18000cbbc  mov     dword ptr [rsp+110h+var_F0], 3
0x18000cbc4  mov     eax, 2
0x18000cbc9  mov     r9d, eax
0x18000cbcc  mov     r8d, eax
0x18000cbcf  lea     esi, [rax-1]
0x18000cbd2  mov     edx, esi
0x18000cbd4  lea     rcx, [rbp+57h+var_98]
0x18000cbd8  call    ?Query@CMultistateFileRecordQuery@@QEAAJW4_FhFileRecordSortOrder@@JZZ; CMultistateFileRecordQuery::Query(_FhFileRecordSortOrder,long,...)
0x18000cbdd  lea     r14, WPP_GLOBAL_Control
0x18000cbe4  mov     edi, eax
0x18000cbe6  test    edi, edi
0x18000cbe8  js      loc_18000CFF8
0x18000cbee  xorps   xmm0, xmm0
0x18000cbf1  xor     eax, eax
0x18000cbf3  movups  [rbp+57h+FileInformation], xmm0
0x18000cbf7  movups  [rbp+57h+var_60], xmm0
0x18000cbfb  mov     [rbp+57h+var_50], eax
0x18000cbfe  lea     rcx, [rsp+110h+lpFileName]
0x18000cc03  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000cc08  cmp     dword ptr [r13+98h], 0
0x18000cc10  jnz     loc_18000CFC7
0x18000cc16  mov     [rbp+57h+var_D0], rbx
0x18000cc1a  test    rbx, rbx
0x18000cc1d  jz      short loc_18000CC22
0x18000cc1f  add     [rbx+8], esi
0x18000cc22  lea     rdx, [rbp+57h+var_D0]
0x18000cc26  lea     rcx, [rbp+57h+var_98]
0x18000cc2a  call    ?LoadCurrentRecord@CMultistateFileRecordQuery@@QEAAJV?$SmartPtr@VCFileRecord@@@@@Z; CMultistateFileRecordQuery::LoadCurrentRecord(SmartPtr<CFileRecord>)
0x18000cc2f  mov     edi, eax
0x18000cc31  cmp     eax, 80070490h
0x18000cc36  jz      loc_18000CFF8
0x18000cc3c  test    eax, eax
0x18000cc3e  js      loc_18000CFAA
0x18000cc44  mov     r8, [rbx]
0x18000cc47  cmp     qword ptr [r8+30h], 0
0x18000cc4c  jl      short loc_18000CBE6
0x18000cc4e  test    r15, r15
0x18000cc51  jnz     short loc_18000CC60
0x18000cc53  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000cc57  test    r12, r12
0x18000cc5a  jz      loc_18000CD44
0x18000cc60  mov     rax, [rsp+110h+lpFileName]
0x18000cc65  cmp     dword ptr [rax-10h], 0
0x18000cc69  jnz     short loc_18000CC92
0x18000cc6b  mov     r8d, [r8+3Ch]
0x18000cc6f  mov     [rbp+57h+var_C0], rbx
0x18000cc73  add     [rbx+8], esi
0x18000cc76  lea     rcx, [r13+8]
0x18000cc7a  lea     r9, [rsp+110h+lpFileName]
0x18000cc7f  lea     rdx, [rbp+57h+var_C0]
0x18000cc83  call    ?ConstructStagingPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSessionBaseRO::ConstructStagingPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000cc88  mov     edi, eax
0x18000cc8a  test    eax, eax
0x18000cc8c  js      loc_18000CF10
0x18000cc92  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x18000cc96  xor     edx, edx; fInfoLevelId
0x18000cc98  mov     rcx, [rsp+110h+lpFileName]; lpFileName
0x18000cc9d  call    cs:__imp_GetFileAttributesExW
0x18000cca3  test    eax, eax
0x18000cca5  jz      short loc_18000CCBA
0x18000cca7  mov     r15d, dword ptr [rbp+57h+var_60+0Ch]
0x18000ccab  shl     r15, 20h
0x18000ccaf  mov     eax, [rbp+57h+var_50]
0x18000ccb2  add     r15, rax
0x18000ccb5  jmp     loc_18000CD44
0x18000ccba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc1  cmp     rcx, r14
0x18000ccc4  jz      short loc_18000CD0A
0x18000ccc6  test    byte ptr [rcx+1Ch], 2
0x18000ccca  jz      short loc_18000CD0A
0x18000cccc  call    cs:__imp_GetLastError
0x18000ccd2  test    eax, eax
0x18000ccd4  jle     short loc_18000CCDE
0x18000ccd6  movzx   eax, ax
0x18000ccd9  or      eax, 80070000h
0x18000ccde  mov     edx, 7Dh ; '}'
0x18000cce3  mov     dword ptr [rsp+110h+var_F0], eax
0x18000cce7  mov     r9, [rsp+110h+lpFileName]
0x18000ccec  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000ccf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccfa  mov     rcx, [rcx+10h]
0x18000ccfe  call    WPP_SF_Sd
0x18000cd03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd0a  mov     rax, [rbx]
0x18000cd0d  mov     r15, [rax+30h]
0x18000cd11  cmp     rcx, r14
0x18000cd14  jz      short loc_18000CD44
0x18000cd16  test    byte ptr [rcx+1Ch], 4
0x18000cd1a  jz      short loc_18000CD44
0x18000cd1c  mov     edx, 7Eh ; '~'
0x18000cd21  lea     rax, aUnableToObtain_0; "Unable to obtain the size of a presumab"...
0x18000cd28  mov     [rsp+110h+var_F0], rax
0x18000cd2d  lea     r9, aRet; "ret"
0x18000cd34  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000cd3b  mov     rcx, [rcx+10h]
0x18000cd3f  call    WPP_SF_ss
0x18000cd44  mov     r8, [rbx]
0x18000cd47  mov     eax, 2
0x18000cd4c  cmp     [r8+28h], ax
0x18000cd51  jnz     loc_18000CEA7
0x18000cd57  mov     rax, [rsp+110h+lpFileName]
0x18000cd5c  cmp     dword ptr [rax-10h], 0
0x18000cd60  jnz     short loc_18000CD89
0x18000cd62  mov     r8d, [r8+3Ch]
0x18000cd66  mov     [rbp+57h+var_B8], rbx
0x18000cd6a  add     [rbx+8], esi
0x18000cd6d  lea     rcx, [r13+8]
0x18000cd71  lea     r9, [rsp+110h+lpFileName]
0x18000cd76  lea     rdx, [rbp+57h+var_B8]
0x18000cd7a  call    ?ConstructStagingPath@CSessionBaseRO@@IEAAJV?$SmartPtr@VCFileRecord@@@@JAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSessionBaseRO::ConstructStagingPath(SmartPtr<CFileRecord>,long,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000cd7f  mov     edi, eax
0x18000cd81  test    eax, eax
0x18000cd83  js      loc_18000CF4F
0x18000cd89  lea     rdx, [r13+38h]
0x18000cd8d  lea     rcx, [rbp+57h+var_A8]
0x18000cd91  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000cd96  mov     rdi, rax
0x18000cd99  lea     rdx, [rsp+110h+lpFileName]
0x18000cd9e  lea     rcx, [rbp+57h+var_A0]
0x18000cda2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000cda7  mov     rdx, rdi
0x18000cdaa  mov     rcx, rax
0x18000cdad  call    ?DeleteFileWithEmptyParents@FheFileOperations@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; FheFileOperations::DeleteFileWithEmptyParents(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18000cdb2  mov     edi, eax
0x18000cdb4  test    eax, eax
0x18000cdb6  jns     short loc_18000CE2C
0x18000cdb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdbf  cmp     rcx, r14
0x18000cdc2  jz      short loc_18000CDEF
0x18000cdc4  test    byte ptr [rcx+1Ch], 2
0x18000cdc8  jz      short loc_18000CDEF
0x18000cdca  mov     edx, 80h
0x18000cdcf  mov     dword ptr [rsp+110h+var_F0], eax
0x18000cdd3  mov     r9, [rsp+110h+lpFileName]
0x18000cdd8  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000cddf  mov     rcx, [rcx+10h]
0x18000cde3  call    WPP_SF_Sd
0x18000cde8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdef  lea     eax, [rdi+7FF8FFFEh]
0x18000cdf5  cmp     eax, esi
0x18000cdf7  jbe     short loc_18000CE2C
0x18000cdf9  cmp     rcx, r14
0x18000cdfc  jz      short loc_18000CE2C
0x18000cdfe  test    byte ptr [rcx+1Ch], 4
0x18000ce02  jz      short loc_18000CE2C
0x18000ce04  mov     edx, 81h
0x18000ce09  lea     rax, aDeletionOfFile; "Deletion of files should not fail durin"...
0x18000ce10  mov     [rsp+110h+var_F0], rax
0x18000ce15  lea     r9, aHrHresultFromW_1; "(hr == HRESULT_FROM_WIN32(ERROR_PATH_NO"...
0x18000ce1c  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000ce23  mov     rcx, [rcx+10h]
0x18000ce27  call    WPP_SF_ss
0x18000ce2c  mov     [rbp+57h+var_D0], rbx
0x18000ce30  add     [rbx+8], esi
0x18000ce33  xor     r9d, r9d
0x18000ce36  lea     r8d, [r9+10h]
0x18000ce3a  lea     rdx, [rbp+57h+var_D0]
0x18000ce3e  mov     rcx, r13
0x18000ce41  call    ?ChangeFileRecordStatus@CSessionBaseRW@@IEAAXV?$SmartPtr@VCFileRecord@@@@GG@Z; CSessionBaseRW::ChangeFileRecordStatus(SmartPtr<CFileRecord>,ushort,ushort)
0x18000ce46  mov     rax, [rbx]
0x18000ce49  mov     [rax+4Ch], esi
0x18000ce4c  mov     [rax+28h], si
0x18000ce50  mov     rcx, [rbx]; this
0x18000ce53  call    ?Commit@CFileRecord@@QEAAJXZ; CFileRecord::Commit(void)
0x18000ce58  mov     edi, eax
0x18000ce5a  test    eax, eax
0x18000ce5c  jns     short loc_18000CEC7
0x18000ce5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce65  cmp     rcx, r14
0x18000ce68  jz      loc_18000D03E
0x18000ce6e  test    [rcx+1Ch], sil
0x18000ce72  jz      loc_18000D03E
0x18000ce78  mov     r9, [rbx]
0x18000ce7b  mov     edx, 82h
0x18000ce80  mov     [rsp+110h+var_E8], eax
0x18000ce84  mov     rax, [rsp+110h+lpFileName]
0x18000ce89  mov     [rsp+110h+var_F0], rax
0x18000ce8e  mov     r9d, [r9+10h]
0x18000ce92  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000ce99  mov     rcx, [rcx+10h]
0x18000ce9d  call    WPP_SF_dSd
0x18000cea2  jmp     loc_18000D037
0x18000cea7  mov     [rbp+57h+var_D0], rbx
0x18000ceab  add     [rbx+8], esi
0x18000ceae  mov     r8d, esi
0x18000ceb1  lea     rdx, [rbp+57h+var_D0]
0x18000ceb5  mov     rcx, r13
0x18000ceb8  call    ?DeleteFileVersion@CSessionBaseRW@@IEAAJV?$SmartPtr@VCFileRecord@@@@H@Z; CSessionBaseRW::DeleteFileVersion(SmartPtr<CFileRecord>,int)
0x18000cebd  mov     edi, eax
0x18000cebf  test    eax, eax
0x18000cec1  js      loc_18000CF89
0x18000cec7  mov     rcx, [rbp+57h+var_C8]
0x18000cecb  test    rcx, rcx
0x18000cece  jz      short loc_18000CEEA
0x18000ced0  mov     rax, [rcx]
0x18000ced3  mov     rdx, r15
0x18000ced6  mov     rax, [rax+28h]
0x18000ceda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cedf  cmp     eax, 80004004h
0x18000cee4  jz      loc_18000CF70
0x18000ceea  mov     rax, [rbp+57h+var_B0]
0x18000ceee  test    rax, rax
0x18000cef1  jz      short loc_18000CEF5
0x18000cef3  add     [rax], esi
0x18000cef5  test    r12, r12
0x18000cef8  jz      short loc_18000CEFE
0x18000cefa  add     [r12], r15
0x18000cefe  lea     rcx, [rbp+57h+var_98]; this
0x18000cf02  call    ?MoveNext@CMultistateFileRecordQuery@@QEAAJXZ; CMultistateFileRecordQuery::MoveNext(void)
0x18000cf07  mov     r15, [rbp+57h+var_C8]
0x18000cf0b  jmp     loc_18000CBE4
0x18000cf10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf17  cmp     rcx, r14
0x18000cf1a  jz      loc_18000D03E
0x18000cf20  test    [rcx+1Ch], sil
0x18000cf24  jz      loc_18000D03E
0x18000cf2a  mov     edx, 7Ch ; '|'
0x18000cf2f  mov     r9, [rbx]
0x18000cf32  mov     dword ptr [rsp+110h+var_F0], eax
0x18000cf36  mov     r9d, [r9+10h]
0x18000cf3a  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000cf41  mov     rcx, [rcx+10h]
0x18000cf45  call    WPP_SF_dd
0x18000cf4a  jmp     loc_18000D037
0x18000cf4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf56  cmp     rcx, r14
0x18000cf59  jz      loc_18000D03E
0x18000cf5f  test    [rcx+1Ch], sil
0x18000cf63  jz      loc_18000D03E
0x18000cf69  mov     edx, 7Fh
0x18000cf6e  jmp     short loc_18000CF2F
0x18000cf70  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf77  cmp     rcx, r14
0x18000cf7a  jz      short loc_18000CFEE
0x18000cf7c  test    byte ptr [rcx+1Ch], 8
0x18000cf80  jz      short loc_18000CFEE
0x18000cf82  mov     edx, 84h
0x18000cf87  jmp     short loc_18000CFDE
0x18000cf89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf90  cmp     rcx, r14
0x18000cf93  jz      loc_18000D03E
0x18000cf99  test    [rcx+1Ch], sil
0x18000cf9d  jz      loc_18000D03E
0x18000cfa3  mov     edx, 83h
0x18000cfa8  jmp     short loc_18000CF2F
0x18000cfaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfb1  cmp     rcx, r14
0x18000cfb4  jz      loc_18000D03E
0x18000cfba  test    [rcx+1Ch], sil
0x18000cfbe  jz      short loc_18000D03E
  ... truncated ...
```
