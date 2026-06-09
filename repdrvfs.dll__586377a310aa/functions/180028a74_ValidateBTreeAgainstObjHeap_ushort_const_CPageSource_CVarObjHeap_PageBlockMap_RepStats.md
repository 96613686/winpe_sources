# ValidateBTreeAgainstObjHeap(ushort const *,CPageSource &,CVarObjHeap &,PageBlockMap *,_RepStats &)

- ea: `0x180028a74`
- end: `0x18002923a`
- name: `?ValidateBTreeAgainstObjHeap@@YAKPEBGAEAVCPageSource@@AEAVCVarObjHeap@@PEAVPageBlockMap@@AEAU_RepStats@@@Z`
- size: `1990`
- prototype: `unsigned int(const unsigned __int16 *, struct CPageSource *, struct CVarObjHeap *, struct PageBlockMap *, struct _RepStats *)`
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040e24`

## callees

- `0x1800012b8`
- `0x18000bc10`
- `0x18000d220`
- `0x18000dc00`
- `0x18000def0`
- `0x18000e000`
- `0x18000f8f0`
- `0x180010fa0`
- `0x180024f8c`
- `0x180028a74`
- `0x180029414`
- `0x180029458`
- `0x1800296d0`
- `0x1800297f8`
- `0x180029860`
- `0x18002ca6c`
- `0x180037a98`
- `0x180037cb0`
- `0x1800404c4`
- `0x180040d2c`
- `0x180041414`
- `0x180041a88`
- `0x180041ae8`
- `0x1800443eb`

## import_xrefs

- `msvcrt!wcsstr` at `0x180028dfc`
- `msvcrt!wcsstr` at `0x180028e1f`
- `msvcrt!wcsstr` at `0x180028e3f`
- `msvcrt!wcsstr` at `0x180028e5f`
- `msvcrt!wcsstr` at `0x180028dfc`
- `msvcrt!wcsstr` at `0x180028e1f`
- `msvcrt!wcsstr` at `0x180028e3f`
- `msvcrt!wcsstr` at `0x180028e5f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028c1d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180028c1d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180028f09`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180028f09`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x180028b1c`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x180028c7c`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x180028b1c`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x180028c7c`
- `wbemcomn!??4WString2@@QEAAAEAV0@PEBG@Z` at `0x180028b2e`
- `wbemcomn!??4WString2@@QEAAAEAV0@PEBG@Z` at `0x180028b2e`
- `wbemcomn!??4WString2@@QEAAAEAV0@AEBV0@@Z` at `0x180028cf0`
- `wbemcomn!??4WString2@@QEAAAEAV0@AEBV0@@Z` at `0x180028cf0`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028b52`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028d21`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028dec`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e0f`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e2f`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e4f`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e9c`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180029029`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028b52`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028d21`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028dec`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e0f`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e2f`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e4f`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180028e9c`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x180029029`
- `wbemcomn!??0WString2@@QEAA@PEBD@Z` at `0x180028cdc`
- `wbemcomn!??0WString2@@QEAA@PEBD@Z` at `0x180028cdc`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180028cff`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180029090`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002909f`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180029196`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x1800291dd`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180028cff`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180029090`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18002909f`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x180029196`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x1800291dd`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x180028b43`
- `wbemcomn!??YWString2@@QEAAAEAV0@PEBG@Z` at `0x180028b43`
- `wbemcomn!GetMemLogObject` at `0x180028b72`
- `wbemcomn!GetMemLogObject` at `0x180028bc8`
- `wbemcomn!GetMemLogObject` at `0x180028d83`
- `wbemcomn!GetMemLogObject` at `0x180028f20`
- `wbemcomn!GetMemLogObject` at `0x180028f79`
- `wbemcomn!GetMemLogObject` at `0x180028ff8`
- `wbemcomn!GetMemLogObject` at `0x1800290f2`
- `wbemcomn!GetMemLogObject` at `0x18002913c`
- `wbemcomn!GetMemLogObject` at `0x180028b72`
- `wbemcomn!GetMemLogObject` at `0x180028bc8`
- `wbemcomn!GetMemLogObject` at `0x180028d83`
- `wbemcomn!GetMemLogObject` at `0x180028f20`
- `wbemcomn!GetMemLogObject` at `0x180028f79`
- `wbemcomn!GetMemLogObject` at `0x180028ff8`
- `wbemcomn!GetMemLogObject` at `0x1800290f2`
- `wbemcomn!GetMemLogObject` at `0x18002913c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028b7d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028bd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028d8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f87`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029006`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800290fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029147`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028b7d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028bd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028d8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180028f87`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029006`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800290fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180029147`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ValidateBTreeAgainstObjHeap(
        const unsigned __int16 *a1,
        struct CPageSource *a2,
        struct CVarObjHeap *a3,
        struct PageBlockMap *a4,
        struct _RepStats *a5)
{
  unsigned __int16 *v7; // rdx
  unsigned int v8; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v10; // rcx
  __int64 v11; // rdx
  CMemoryLog *v12; // rax
  unsigned int v13; // ebx
  MemoryPage *v14; // rax
  MemoryPage *v15; // rax
  MemoryPage *v16; // rsi
  unsigned int v17; // eax
  CPageFile *v18; // r15
  unsigned int *v19; // r8
  char *v20; // r14
  const unsigned __int16 *v21; // rax
  unsigned int v22; // r12d
  int Page; // eax
  int v24; // r14d
  CMemoryLog *v25; // rax
  const wchar_t *v26; // rax
  const wchar_t *v27; // rax
  const wchar_t *v28; // rax
  const wchar_t *v29; // rax
  unsigned int v30; // r14d
  wchar_t *v31; // rax
  unsigned int v32; // r15d
  CMemoryLog *v33; // rax
  MemoryPage *v34; // rcx
  _DWORD *v35; // r14
  int v36; // r15d
  CMemoryLog *v37; // rax
  char v38; // r14
  CMemoryLog *v39; // rax
  int v40; // eax
  int v41; // edx
  int v42; // r8d
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  MemoryPage *v46; // [rsp+30h] [rbp-178h] BYREF
  unsigned int v47; // [rsp+38h] [rbp-170h] BYREF
  unsigned int v48; // [rsp+3Ch] [rbp-16Ch] BYREF
  unsigned __int8 *v49; // [rsp+40h] [rbp-168h] BYREF
  MemoryPage *v50; // [rsp+48h] [rbp-160h] BYREF
  CPageFile *v51; // [rsp+50h] [rbp-158h]
  char *Str2; // [rsp+58h] [rbp-150h] BYREF
  _BYTE v53[24]; // [rsp+60h] [rbp-148h] BYREF
  _BYTE v54[40]; // [rsp+78h] [rbp-130h] BYREF
  _BYTE v55[8]; // [rsp+A0h] [rbp-108h] BYREF
  _BYTE *v56; // [rsp+A8h] [rbp-100h]
  unsigned int (__fastcall *v57)(CBTree *__hidden, unsigned int); // [rsp+B0h] [rbp-F8h]
  int v58; // [rsp+B8h] [rbp-F0h]
  _BYTE v59[8]; // [rsp+C0h] [rbp-E8h] BYREF
  _BYTE *v60; // [rsp+C8h] [rbp-E0h]
  unsigned int (__fastcall *v61)(CBTreeFile *__hidden, unsigned int); // [rsp+D0h] [rbp-D8h]
  int v62; // [rsp+D8h] [rbp-D0h]
  _BYTE v63[40]; // [rsp+E0h] [rbp-C8h] BYREF
  MemoryPage **v64; // [rsp+108h] [rbp-A0h]
  _BYTE v65[64]; // [rsp+110h] [rbp-98h] BYREF
  _BYTE v66[48]; // [rsp+150h] [rbp-58h] BYREF

  CBTreeFile::CBTreeFile((CBTreeFile *)v53);
  CBTree::CBTree((CBTree *)v65);
  v59[0] = 0;
  v60 = v53;
  v61 = CBTreeFile::Shutdown;
  v62 = 0;
  v55[0] = 0;
  v56 = v65;
  v57 = CBTree::Shutdown;
  v58 = 0;
  WString2::WString2((WString2 *)v63);
  try
  {
    WString2::operator=(v63, a1);
    WString2::operator+=(v63, L"\\index.btr");
  }
  catch ( CX_MemoryException )
  {
    WString2::~WString2((WString2 *)v63);
    ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v55);
    ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v59);
    CBTree::~CBTree((CBTree *)v65);
    CBTreeFile::~CBTreeFile((CBTreeFile *)v53);
    return 14;
  }
  WString2::operator unsigned short *(v63);
  v8 = CBTreeFile::Init((CBTreeFile *)v53, v7, a2);
  if ( v8 )
  {
    g_error = 1;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 21;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v8);
LABEL_13:
    v13 = 0;
LABEL_76:
    WString2::~WString2((WString2 *)v63);
    ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v55);
    ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v59);
    CBTree::~CBTree((CBTree *)v65);
    CBTreeFile::~CBTreeFile((CBTreeFile *)v53);
    return v13;
  }
  v8 = CBTree::Init((CBTree *)v65, (struct CBTreeFile *)v53);
  if ( v8 )
  {
    g_error = 1;
    v12 = GetMemLogObject();
    CMemoryLog::Write(v12, v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_13;
    }
    v11 = 22;
    goto LABEL_12;
  }
  v14 = (MemoryPage *)CWin32DefaultArena::WbemMemAlloc(0x2B18u);
  v50 = v14;
  if ( !v14 || (v15 = CBTreeIterator::CBTreeIterator(v14), v16 = v15, (v50 = v15) == 0) )
  {
    v45 = GetMemLogObject();
    CMemoryLog::Write(v45, 0);
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v13 = 14;
    }
    else
    {
      v13 = 14;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, 14);
    }
    goto LABEL_76;
  }
  try
  {
    v17 = CBTreeIterator::Init(v15, (struct CBTree *)v65, "NS_");
    v13 = v17;
  }
  catch ( CX_MemoryException )
  {
    v48 = 14;
    v13 = 14;
    v16 = v50;
    goto LABEL_67;
  }
  if ( v17 )
  {
LABEL_67:
    CBTreeIterator::Release(v16);
    v44 = GetMemLogObject();
    CMemoryLog::Write(v44, v13);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v13);
    }
    goto LABEL_76;
  }
  v18 = (struct CPageSource *)((char *)a2 + 488);
  v51 = (struct CPageSource *)((char *)a2 + 488);
  WString2::WString2((WString2 *)v54);
  Str2 = 0;
  while ( !CBTreeIterator::Next(v16, &Str2, v19) )
  {
    v20 = Str2;
    if ( strncmp_0("NS_", Str2, 3u) )
    {
      _BtrMemFree(v20);
      break;
    }
    WString2::WString2((WString2 *)v66, v20);
    WString2::operator=(v54, v66);
    WString2::~WString2((WString2 *)v66);
    _BtrMemFree(v20);
    v47 = 0;
    LODWORD(v49) = 0;
    v48 = 0;
    v21 = (const unsigned __int16 *)WString2::operator unsigned short *(v54);
    if ( !(unsigned int)ParseInfoFromIndexFile(v21, &v47, (unsigned int *)&v49, &v48) )
    {
      v46 = 0;
      v64 = &v46;
      v22 = v47;
      Page = CPageFile::GetPage(v18, v47, (__int64)v19, &v46);
      v24 = Page;
      if ( Page )
      {
        if ( Page == 14 )
        {
          if ( v46 )
            MemoryPage::Release(v46);
          break;
        }
        g_error = 1;
        v25 = GetMemLogObject();
        CMemoryLog::Write(v25, v24);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v22, v24);
        }
        if ( v46 )
          MemoryPage::Release(v46);
        v46 = 0;
      }
      else
      {
        v26 = (const wchar_t *)WString2::operator unsigned short *(v54);
        if ( wcsstr(v26, L"\\CD_")
          || (v27 = (const wchar_t *)WString2::operator unsigned short *(v54), wcsstr(v27, L"\\KI_"))
          && ((v28 = (const wchar_t *)WString2::operator unsigned short *(v54), wcsstr(v28, L"\\I_"))
           || (v29 = (const wchar_t *)WString2::operator unsigned short *(v54), wcsstr(v29, L"\\IR_"))) )
        {
          v30 = (unsigned int)v49;
          UpdateBlockMap(a4, *((_DWORD *)a5 + 8), v22, (unsigned int)v49, v46);
        }
        else
        {
          v30 = (unsigned int)v49;
        }
        v31 = (wchar_t *)WString2::operator unsigned short *(v54);
        GatherIndexStats(v31, a5);
        v47 = 0;
        v49 = 0;
        v50 = 0;
        v32 = CVarObjHeap::ReadBuffer(a3, v22, v30, &v49, &v47, &v50);
        if ( v49 )
        {
          if ( v50 )
            MemoryPage::Release(v50);
          else
            CWin32DefaultArena::WbemMemFree(v49);
        }
        if ( v32 )
        {
          g_error = 1;
          v33 = GetMemLogObject();
          CMemoryLog::Write(v33, v32);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v19, v22, v30, v32);
          }
          v34 = v46;
          v35 = (_DWORD *)*((_QWORD *)v46 + 2);
          v36 = 0;
          if ( *v35 )
          {
            do
            {
              v37 = GetMemLogObject();
              CMemoryLog::Write(v37, 1358);
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_LLL(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  27,
                  v19,
                  (unsigned int)v35[4 * v36],
                  v35[4 * v36 + 1],
                  v35[4 * v36 + 2]);
              }
              ++v36;
            }
            while ( v35[4 * v36] );
            v34 = v46;
          }
        }
        else
        {
          v38 = v47;
          if ( v47 != v48 )
          {
            g_error = 1;
            v39 = GetMemLogObject();
            CMemoryLog::Write(v39, 1358);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v40 = WString2::operator unsigned short *(v54);
              WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), v41, v42, v40, v38);
            }
          }
          v34 = v46;
        }
        if ( v34 )
          MemoryPage::Release(v34);
        v46 = 0;
        v18 = v51;
      }
    }
  }
  CBTreeIterator::Release(v16);
  WString2::~WString2((WString2 *)v54);
  WString2::~WString2((WString2 *)v63);
  ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v55);
  ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v59);
  CBTree::~CBTree((CBTree *)v65);
  CBTreeFile::~CBTreeFile((CBTreeFile *)v53);
  return 0;
}

```

## disassembly

```asm
0x180028a74  mov     rax, rsp
0x180028a77  mov     [rax+8], rbx
0x180028a7b  mov     [rax+10h], rsi
0x180028a7f  mov     [rax+20h], r9
0x180028a83  mov     [rax+18h], r8
0x180028a87  push    rdi
0x180028a88  push    r12
0x180028a8a  push    r13
0x180028a8c  push    r14
0x180028a8e  push    r15
0x180028a90  sub     rsp, 180h
0x180028a97  mov     rdi, rdx
0x180028a9a  mov     rbx, rcx
0x180028a9d  lea     rcx, [rsp+1A8h+var_148]; this
0x180028aa2  call    ??0CBTreeFile@@QEAA@XZ; CBTreeFile::CBTreeFile(void)
0x180028aa7  nop
0x180028aa8  lea     rcx, [rsp+1A8h+var_98]; this
0x180028ab0  call    ??0CBTree@@QEAA@XZ; CBTree::CBTree(void)
0x180028ab5  nop
0x180028ab6  xor     r12d, r12d
0x180028ab9  mov     [rsp+1A8h+var_E8], r12b
0x180028ac1  lea     rax, [rsp+1A8h+var_148]
0x180028ac6  mov     [rsp+1A8h+var_E0], rax
0x180028ace  lea     rax, ?Shutdown@CBTreeFile@@QEAAKK@Z; CBTreeFile::Shutdown(ulong)
0x180028ad5  mov     [rsp+1A8h+var_D8], rax
0x180028add  mov     [rsp+1A8h+var_D0], r12d
0x180028ae5  mov     [rsp+1A8h+var_108], r12b
0x180028aed  lea     rax, [rsp+1A8h+var_98]
0x180028af5  mov     [rsp+1A8h+var_100], rax
0x180028afd  lea     rax, ?Shutdown@CBTree@@QEAAKK@Z; CBTree::Shutdown(ulong)
0x180028b04  mov     [rsp+1A8h+var_F8], rax
0x180028b0c  mov     [rsp+1A8h+var_F0], r12d
0x180028b14  lea     rcx, [rsp+1A8h+var_C8]
0x180028b1c  call    cs:__imp_??0WString2@@QEAA@XZ; WString2::WString2(void)
0x180028b22  nop
0x180028b23  mov     rdx, rbx
0x180028b26  lea     rcx, [rsp+1A8h+var_C8]
0x180028b2e  call    cs:__imp_??4WString2@@QEAAAEAV0@PEBG@Z; WString2::operator=(ushort const *)
0x180028b34  lea     rdx, aIndexBtr_0; "\\index.btr"
0x180028b3b  lea     rcx, [rsp+1A8h+var_C8]
0x180028b43  call    cs:__imp_??YWString2@@QEAAAEAV0@PEBG@Z; WString2::operator+=(ushort const *)
0x180028b49  nop
0x180028b4a  lea     rcx, [rsp+1A8h+var_C8]
0x180028b52  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180028b58  mov     r8, rdi; struct CPageSource *
0x180028b5b  lea     rcx, [rsp+1A8h+var_148]; this
0x180028b60  call    ?Init@CBTreeFile@@QEAAKPEAGPEAVCPageSource@@@Z; CBTreeFile::Init(ushort *,CPageSource *)
0x180028b65  mov     ebx, eax
0x180028b67  test    eax, eax
0x180028b69  jz      short loc_180028BA9
0x180028b6b  mov     cs:?g_error@@3_NA, 1; bool g_error
0x180028b72  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028b78  mov     edx, ebx
0x180028b7a  mov     rcx, rax
0x180028b7d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028b83  lea     rdi, WPP_GLOBAL_Control
0x180028b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b91  cmp     rcx, rdi
0x180028b94  jz      short loc_180028C10
0x180028b96  test    byte ptr [rcx+1Ch], 1
0x180028b9a  jz      short loc_180028C10
0x180028b9c  cmp     byte ptr [rcx+19h], 2
0x180028ba0  jb      short loc_180028C10
0x180028ba2  mov     edx, 15h
0x180028ba7  jmp     short loc_180028BFD
0x180028ba9  lea     rdx, [rsp+1A8h+var_148]; struct CBTreeFile *
0x180028bae  lea     rcx, [rsp+1A8h+var_98]; this
0x180028bb6  call    ?Init@CBTree@@QEAAKPEAVCBTreeFile@@@Z; CBTree::Init(CBTreeFile *)
0x180028bbb  mov     ebx, eax
0x180028bbd  test    eax, eax
0x180028bbf  jz      short loc_180028C18
0x180028bc1  mov     cs:?g_error@@3_NA, 1; bool g_error
0x180028bc8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028bce  mov     edx, ebx
0x180028bd0  mov     rcx, rax
0x180028bd3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028bd9  lea     rdi, WPP_GLOBAL_Control
0x180028be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180028be7  cmp     rcx, rdi
0x180028bea  jz      short loc_180028C10
0x180028bec  test    byte ptr [rcx+1Ch], 1
0x180028bf0  jz      short loc_180028C10
0x180028bf2  cmp     byte ptr [rcx+19h], 2
0x180028bf6  jb      short loc_180028C10
0x180028bf8  mov     edx, 16h
0x180028bfd  mov     r9d, ebx
0x180028c00  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x180028c07  mov     rcx, [rcx+10h]
0x180028c0b  call    WPP_SF_d
0x180028c10  mov     ebx, r12d
0x180028c13  jmp     loc_18002918E
0x180028c18  mov     ecx, 2B18h
0x180028c1d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180028c23  mov     [rsp+1A8h+var_160], rax
0x180028c28  test    rax, rax
0x180028c2b  jz      loc_18002913C
0x180028c31  mov     rcx, rax; this
0x180028c34  call    ??0CBTreeIterator@@QEAA@XZ; CBTreeIterator::CBTreeIterator(void)
0x180028c39  mov     rsi, rax
0x180028c3c  mov     [rsp+1A8h+var_160], rax
0x180028c41  test    rax, rax
0x180028c44  jz      loc_18002913C
0x180028c4a  lea     r8, Str1; "NS_"
0x180028c51  lea     rdx, [rsp+1A8h+var_98]; struct CBTree *
0x180028c59  mov     rcx, rax; this
0x180028c5c  call    ?Init@CBTreeIterator@@QEAAKPEAVCBTree@@PEAD@Z; CBTreeIterator::Init(CBTree *,char *)
0x180028c61  mov     ebx, eax
0x180028c63  test    eax, eax
0x180028c65  jnz     loc_1800290EA
0x180028c6b  lea     r15, [rdi+1E8h]
0x180028c72  mov     [rsp+1A8h+var_158], r15
0x180028c77  lea     rcx, [rsp+1A8h+var_130]
0x180028c7c  call    cs:__imp_??0WString2@@QEAA@XZ; WString2::WString2(void)
0x180028c82  nop
0x180028c83  mov     [rsp+1A8h+Str2], r12
0x180028c88  lea     rdi, WPP_GLOBAL_Control
0x180028c8f  mov     ebx, 0Eh
0x180028c94  mov     r13, [rsp+1A8h+arg_20]
0x180028c9c  lea     rdx, [rsp+1A8h+Str2]; char **
0x180028ca1  mov     rcx, rsi; this
0x180028ca4  call    ?Next@CBTreeIterator@@QEAAKPEAPEADPEAK@Z; CBTreeIterator::Next(char * *,ulong *)
0x180028ca9  test    eax, eax
0x180028cab  jnz     loc_180029082
0x180028cb1  lea     r8d, [rax+3]; MaxCount
0x180028cb5  mov     r14, [rsp+1A8h+Str2]
0x180028cba  mov     rdx, r14; Str2
0x180028cbd  lea     rcx, Str1; "NS_"
0x180028cc4  call    strncmp_0
0x180028cc9  test    eax, eax
0x180028ccb  jnz     loc_18002907A
0x180028cd1  mov     rdx, r14
0x180028cd4  lea     rcx, [rsp+1A8h+var_58]
0x180028cdc  call    cs:__imp_??0WString2@@QEAA@PEBD@Z; WString2::WString2(char const *)
0x180028ce2  nop
0x180028ce3  lea     rdx, [rsp+1A8h+var_58]
0x180028ceb  lea     rcx, [rsp+1A8h+var_130]
0x180028cf0  call    cs:__imp_??4WString2@@QEAAAEAV0@AEBV0@@Z; WString2::operator=(WString2 const &)
0x180028cf6  nop
0x180028cf7  lea     rcx, [rsp+1A8h+var_58]
0x180028cff  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x180028d05  mov     rcx, r14; void *
0x180028d08  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x180028d0d  mov     [rsp+1A8h+var_170], r12d
0x180028d12  mov     dword ptr [rsp+1A8h+var_168], r12d
0x180028d17  mov     [rsp+1A8h+var_16C], r12d
0x180028d1c  lea     rcx, [rsp+1A8h+var_130]
0x180028d21  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180028d27  mov     rcx, rax; unsigned __int16 *
0x180028d2a  lea     r9, [rsp+1A8h+var_16C]; unsigned int *
0x180028d2f  lea     r8, [rsp+1A8h+var_168]; unsigned int *
0x180028d34  lea     rdx, [rsp+1A8h+var_170]; unsigned int *
0x180028d39  call    ?ParseInfoFromIndexFile@@YAJPEBGPEAK11@Z; ParseInfoFromIndexFile(ushort const *,ulong *,ulong *,ulong *)
0x180028d3e  test    eax, eax
0x180028d40  jnz     loc_180028C9C
0x180028d46  mov     [rsp+1A8h+var_178], r12
0x180028d4b  lea     rax, [rsp+1A8h+var_178]
0x180028d50  mov     [rsp+1A8h+var_A0], rax
0x180028d58  lea     r9, [rsp+1A8h+var_178]; struct MemoryPage **
0x180028d5d  mov     r12d, [rsp+1A8h+var_170]
0x180028d62  mov     edx, r12d; unsigned int
0x180028d65  mov     rcx, r15; this
0x180028d68  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x180028d6d  mov     r14d, eax
0x180028d70  test    eax, eax
0x180028d72  jz      short loc_180028DE7
0x180028d74  cmp     eax, ebx
0x180028d76  jz      loc_180029069
0x180028d7c  mov     cs:?g_error@@3_NA, 1; bool g_error
0x180028d83  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028d89  mov     edx, r14d
0x180028d8c  mov     rcx, rax
0x180028d8f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d9c  cmp     rcx, rdi
0x180028d9f  jz      short loc_180028DCB
0x180028da1  test    byte ptr [rcx+1Ch], 1
0x180028da5  jz      short loc_180028DCB
0x180028da7  cmp     byte ptr [rcx+19h], 2
0x180028dab  jb      short loc_180028DCB
0x180028dad  mov     edx, 19h
0x180028db2  mov     dword ptr [rsp+1A8h+var_188], r14d
0x180028db7  mov     r9d, r12d
0x180028dba  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x180028dc1  mov     rcx, [rcx+10h]
0x180028dc5  call    WPP_SF_LL
0x180028dca  nop
0x180028dcb  mov     rcx, [rsp+1A8h+var_178]; this
0x180028dd0  xor     r12d, r12d
0x180028dd3  test    rcx, rcx
0x180028dd6  jz      short loc_180028DDD
0x180028dd8  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180028ddd  mov     [rsp+1A8h+var_178], r12
0x180028de2  jmp     loc_180028C9C
0x180028de7  lea     rcx, [rsp+1A8h+var_130]
0x180028dec  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180028df2  mov     rcx, rax; Str
0x180028df5  lea     rdx, aCd; "\\CD_"
0x180028dfc  call    cs:__imp_wcsstr
0x180028e02  xor     r15d, r15d
0x180028e05  test    rax, rax
0x180028e08  jnz     short loc_180028E71
0x180028e0a  lea     rcx, [rsp+1A8h+var_130]
0x180028e0f  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180028e15  mov     rcx, rax; Str
0x180028e18  lea     rdx, aKi; "\\KI_"
0x180028e1f  call    cs:__imp_wcsstr
0x180028e25  test    rax, rax
0x180028e28  jz      short loc_180028E6A
0x180028e2a  lea     rcx, [rsp+1A8h+var_130]
0x180028e2f  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180028e35  mov     rcx, rax; Str
0x180028e38  lea     rdx, aI; "\\I_"
0x180028e3f  call    cs:__imp_wcsstr
0x180028e45  test    rax, rax
0x180028e48  jnz     short loc_180028E71
0x180028e4a  lea     rcx, [rsp+1A8h+var_130]
0x180028e4f  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180028e55  mov     rcx, rax; Str
0x180028e58  lea     rdx, aIr_0; "\\IR_"
0x180028e5f  call    cs:__imp_wcsstr
0x180028e65  test    rax, rax
0x180028e68  jnz     short loc_180028E71
0x180028e6a  mov     r14d, dword ptr [rsp+1A8h+var_168]
0x180028e6f  jmp     short loc_180028E97
0x180028e71  mov     rax, [rsp+1A8h+var_178]
0x180028e76  mov     [rsp+1A8h+var_188], rax; struct MemoryPage *
0x180028e7b  mov     r14d, dword ptr [rsp+1A8h+var_168]
0x180028e80  mov     r9d, r14d; unsigned int
0x180028e83  mov     r8d, r12d; unsigned int
0x180028e86  mov     edx, [r13+20h]; unsigned int
0x180028e8a  mov     rcx, [rsp+1A8h+arg_18]; struct PageBlockMap *
0x180028e92  call    ?UpdateBlockMap@@YAXPEAVPageBlockMap@@KKKPEAVMemoryPage@@@Z; UpdateBlockMap(PageBlockMap *,ulong,ulong,ulong,MemoryPage *)
0x180028e97  lea     rcx, [rsp+1A8h+var_130]
0x180028e9c  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x180028ea2  mov     rcx, rax; Str
0x180028ea5  mov     rdx, r13; struct _RepStats *
0x180028ea8  call    ?GatherIndexStats@@YAXPEBGAEAU_RepStats@@@Z; GatherIndexStats(ushort const *,_RepStats &)
0x180028ead  mov     [rsp+1A8h+var_170], r15d
0x180028eb2  mov     [rsp+1A8h+var_168], r15
0x180028eb7  mov     [rsp+1A8h+var_160], r15
0x180028ebc  lea     rax, [rsp+1A8h+var_160]
0x180028ec1  mov     [rsp+1A8h+var_180], rax; struct MemoryPage **
0x180028ec6  lea     rax, [rsp+1A8h+var_170]
0x180028ecb  mov     [rsp+1A8h+var_188], rax; unsigned int *
0x180028ed0  lea     r9, [rsp+1A8h+var_168]; unsigned __int8 **
0x180028ed5  mov     r8d, r14d; unsigned int
0x180028ed8  mov     edx, r12d; unsigned int
0x180028edb  mov     rcx, [rsp+1A8h+arg_10]; this
0x180028ee3  call    ?ReadBuffer@CVarObjHeap@@QEAAKKKPEAPEAEPEAKPEAPEAVMemoryPage@@@Z; CVarObjHeap::ReadBuffer(ulong,ulong,uchar * *,ulong *,MemoryPage * *)
0x180028ee8  mov     r15d, eax
0x180028eeb  mov     rax, [rsp+1A8h+var_168]
0x180028ef0  test    rax, rax
0x180028ef3  jz      short loc_180028F10
0x180028ef5  mov     rcx, [rsp+1A8h+var_160]; this
0x180028efa  test    rcx, rcx
0x180028efd  jz      short loc_180028F06
0x180028eff  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180028f04  jmp     short loc_180028F10
0x180028f06  mov     rcx, rax
0x180028f09  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180028f0f  nop
0x180028f10  test    r15d, r15d
0x180028f13  jz      loc_180028FE5
0x180028f19  mov     cs:?g_error@@3_NA, 1; bool g_error
0x180028f20  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028f26  mov     edx, r15d
0x180028f29  mov     rcx, rax
0x180028f2c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f39  cmp     rcx, rdi
0x180028f3c  jz      short loc_180028F65
0x180028f3e  test    byte ptr [rcx+1Ch], 1
0x180028f42  jz      short loc_180028F65
0x180028f44  cmp     byte ptr [rcx+19h], 2
0x180028f48  jb      short loc_180028F65
0x180028f4a  mov     edx, 1Ah
0x180028f4f  mov     dword ptr [rsp+1A8h+var_180], r15d
0x180028f54  mov     dword ptr [rsp+1A8h+var_188], r14d
0x180028f59  mov     r9d, r12d
0x180028f5c  mov     rcx, [rcx+10h]
0x180028f60  call    WPP_SF_LLL
0x180028f65  mov     rcx, [rsp+1A8h+var_178]
0x180028f6a  mov     r14, [rcx+10h]
0x180028f6e  xor     r12d, r12d
0x180028f71  mov     r15d, r12d
0x180028f74  cmp     [r14], r12d
0x180028f77  jz      short loc_180028FE3
0x180028f79  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180028f7f  mov     edx, 54Eh
0x180028f84  mov     rcx, rax
0x180028f87  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180028f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f94  cmp     rcx, rdi
0x180028f97  jz      short loc_180028FCF
0x180028f99  test    byte ptr [rcx+1Ch], 1
0x180028f9d  jz      short loc_180028FCF
0x180028f9f  cmp     byte ptr [rcx+19h], 2
0x180028fa3  jb      short loc_180028FCF
0x180028fa5  mov     r9d, r15d
0x180028fa8  add     r9, r9
  ... truncated ...
```
