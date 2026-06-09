# CAppExport::ExportClasses(_GUID const &,ushort *,ulong,ulong *,ushort * * *,ulong *,_tagDLLINFO * *,ulong *,_tagPSDLLINFO * *)

- ea: `0x18000fe08`
- end: `0x1800108f4`
- name: `?ExportClasses@CAppExport@@AEAAJAEBU_GUID@@PEAGKPEAKPEAPEAPEAG2PEAPEAU_tagDLLINFO@@2PEAPEAU_tagPSDLLINFO@@@Z`
- size: `2796`
- prototype: `__int64 __usercall@<rax>(CAppExport *__hidden this@<rcx>, const struct _GUID *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int *, unsigned __int16 ***, unsigned int *, struct _tagDLLINFO **, unsigned int *, struct _tagPSDLLINFO **)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010900`

## callees

- `0x18000a01c`
- `0x18000fe08`
- `0x180011aec`
- `0x18001a6c8`
- `0x18002fa00`
- `0x180049db8`
- `0x18004a6d8`
- `0x18004a82c`
- `0x18004a988`
- `0x18004aa88`
- `0x18004af70`
- `0x18004afcc`
- `0x18004b534`
- `0x18004d140`
- `0x18004d820`
- `0x18004da8c`
- `0x18004f3a0`
- `0x180055502`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180010423`
- `msvcrt!wcsrchr` at `0x180010423`
- `msvcrt!_wcsicmp` at `0x180010458`
- `msvcrt!_wcsicmp` at `0x180010458`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18000ff7b`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180010139`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18000ff7b`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180010139`
- `CLBCatQ!ServerGetApplicationType` at `0x18000fed2`
- `CLBCatQ!ServerGetApplicationType` at `0x18000fed2`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800105ff`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x180010851`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x1800105ff`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x180010851`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x1800105c0`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x1800105c0`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001078f`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001078f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001002f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001083d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001002f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001083d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001020b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001020b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAppExport::ExportClasses(
        CAppExport *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned int *a5,
        unsigned __int16 ***a6,
        unsigned int *a7,
        struct _tagDLLINFO **a8,
        unsigned int *a9,
        struct _tagPSDLLINFO **a10)
{
  unsigned __int16 *v11; // r12
  struct _GUID *v12; // r15
  struct _GUID v14; // xmm6
  GUID v15; // xmm7
  int ApplicationType; // ebx
  int v17; // esi
  GUID *v18; // r13
  int v20; // eax
  int v21; // esi
  GUID *v22; // r12
  const wchar_t *v23; // r14
  char *v24; // rbx
  __int64 v25; // rcx
  unsigned int i; // r15d
  GUID **v27; // rsi
  __int64 v28; // r8
  unsigned int Data1; // edx
  unsigned int j; // eax
  wchar_t *v31; // rax
  const wchar_t *v32; // rbx
  const wchar_t *v33; // rdx
  WCHAR *v34; // rsi
  int v35; // eax
  int v36; // r15d
  int v37; // eax
  GUID *p_Buf1; // r8
  CAppExport *v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  CAppExport *v42; // rcx
  WCHAR *v43; // rax
  int v44; // ecx
  int v45; // edx
  char v46; // r13
  CAppExport *v47; // rcx
  int v48; // eax
  HRESULT TypeLib; // ebx
  __int64 v50; // [rsp+40h] [rbp-C8h]
  int v51[2]; // [rsp+58h] [rbp-B0h] BYREF
  const unsigned __int16 *v52; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+70h] [rbp-98h] BYREF
  __int64 v55; // [rsp+78h] [rbp-90h] BYREF
  struct _GUID *v56; // [rsp+80h] [rbp-88h]
  struct _GUID v57; // [rsp+88h] [rbp-80h] BYREF
  int v58; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v59; // [rsp+9Ch] [rbp-6Ch] BYREF
  int v60; // [rsp+A0h] [rbp-68h]
  LPVOID pv[2]; // [rsp+A8h] [rbp-60h] BYREF
  struct _GUID v62; // [rsp+B8h] [rbp-50h] BYREF
  ITypeLib *pptlib[2]; // [rsp+C8h] [rbp-40h] BYREF
  int v64; // [rsp+D8h] [rbp-30h] BYREF
  void *v65; // [rsp+E0h] [rbp-28h]
  unsigned __int16 *v66; // [rsp+E8h] [rbp-20h]
  unsigned int *v67; // [rsp+F0h] [rbp-18h]
  unsigned __int16 ***v68; // [rsp+F8h] [rbp-10h]
  unsigned int *v69; // [rsp+100h] [rbp-8h]
  struct _tagDLLINFO **v70; // [rsp+108h] [rbp+0h]
  unsigned int *v71; // [rsp+110h] [rbp+8h]
  struct _tagPSDLLINFO **v72; // [rsp+118h] [rbp+10h]
  unsigned __int16 *v73; // [rsp+120h] [rbp+18h] BYREF
  int v74; // [rsp+128h] [rbp+20h]
  int v75; // [rsp+12Ch] [rbp+24h]
  int v76; // [rsp+130h] [rbp+28h]
  int v77; // [rsp+134h] [rbp+2Ch]
  int *v78; // [rsp+138h] [rbp+30h] BYREF
  int v79; // [rsp+140h] [rbp+38h]
  int v80; // [rsp+144h] [rbp+3Ch]
  int v81; // [rsp+148h] [rbp+40h]
  int v82; // [rsp+14Ch] [rbp+44h]
  struct _GUID *v83; // [rsp+150h] [rbp+48h]
  int v84; // [rsp+158h] [rbp+50h]
  int v85; // [rsp+15Ch] [rbp+54h]
  int v86; // [rsp+160h] [rbp+58h]
  int v87; // [rsp+164h] [rbp+5Ch]
  GUID v88; // [rsp+168h] [rbp+60h] BYREF
  GUID Buf1; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 v90[264]; // [rsp+188h] [rbp+80h] BYREF

  v60 = a4;
  v11 = a3;
  v66 = a3;
  v12 = a2;
  v56 = a2;
  v67 = a5;
  v68 = a6;
  v69 = a7;
  v70 = a8;
  v71 = a9;
  v72 = a10;
  v54 = 0;
  v55 = 0;
  v64 = 1;
  pv[0] = 0;
  v14 = (struct _GUID)guidGlobalPartition;
  v15 = GUID_NULL;
  v51[0] = 1;
  ApplicationType = ServerGetApplicationType(*((_QWORD *)this + 22), a2, v51);
  if ( ApplicationType < 0 )
    goto LABEL_15;
  if ( v51[0] == 1 )
  {
    v17 = 2097157;
  }
  else
  {
    v17 = 4194309;
    if ( v51[0] == 2 && (a4 & 0x80u) != 0 )
    {
      ApplicationType = -2147024809;
      goto LABEL_15;
    }
  }
  v57 = *v12;
  ApplicationType = CAppExport::ExportLegacyClasses(this, &v57, v11, a4);
  v18 = 0;
  if ( ApplicationType < 0 )
    goto LABEL_15;
  v78 = &v64;
  v79 = 0;
  v80 = -268435451;
  v81 = 19;
  v82 = 4;
  v83 = v12;
  v84 = 0;
  v85 = 9;
  v86 = 72;
  v87 = 16;
  v54 = 0;
  if ( !*((_QWORD *)this + 22) )
  {
    v52 = 0;
    ApplicationType = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v52);
    if ( ApplicationType < 0 )
      goto LABEL_12;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, (signed __int64)v52, 0) )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v52 + 16LL))(v52);
  }
  if ( memcmp_0(tidCOMSERVICES_CLASSES, &TID_APPLICATION, 0x10u) )
    v17 |= 2u;
  ApplicationType = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, int **, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                      *((_QWORD *)this + 22),
                      didCOMSERVICES,
                      tidCOMSERVICES_CLASSES,
                      &v78,
                      2,
                      1,
                      v17,
                      &v54);
LABEL_12:
  if ( ApplicationType < 0 )
    goto LABEL_15;
  if ( !v54 )
    goto LABEL_14;
  ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 24LL))(v54);
  if ( ApplicationType < 0 )
    goto LABEL_15;
  ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 32LL))(v54);
  if ( ApplicationType < 0 )
    goto LABEL_15;
  v73 = v11;
  v74 = 0;
  v75 = -268435455;
  v76 = 130;
  v77 = 2 * safe_lstrlenW(v11) + 2;
  v55 = 0;
  if ( !*((_QWORD *)this + 22) )
  {
    v52 = 0;
    ApplicationType = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v52);
    if ( ApplicationType < 0 )
      goto LABEL_32;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, (signed __int64)v52, 0) )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v52 + 16LL))(v52);
  }
  v20 = memcmp_0(tidCOMSERVICES_CLASSES_EXPORT, &TID_APPLICATION, 0x10u);
  ApplicationType = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                      *((_QWORD *)this + 22),
                      didCOMSERVICES,
                      tidCOMSERVICES_CLASSES_EXPORT,
                      &v73,
                      1,
                      1,
                      v20 != 0 ? 6 : 4,
                      &v55);
LABEL_32:
  if ( ApplicationType < 0 )
    goto LABEL_15;
  if ( !v55 )
    goto LABEL_14;
  ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 24LL))(v55);
  if ( ApplicationType < 0 )
    goto LABEL_15;
  v65 = CoTaskMemAlloc(0x228u);
  if ( !v65 )
  {
LABEL_14:
    ApplicationType = -2147024882;
    goto LABEL_15;
  }
  v90[0] = 0;
  while ( 2 )
  {
    LODWORD(v53) = 1;
    v88 = 0;
    Buf1 = GUID_NULL;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v54 + 40LL))(v54) == -2146367487 )
    {
      v57 = *v12;
      ApplicationType = CAppExport::ExportDllNames(this, &v57, v11);
      if ( ApplicationType >= 0 )
      {
        ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 96LL))(v55);
        if ( ApplicationType >= 0 )
        {
          *v67 = *((_DWORD *)this + 4);
          *v68 = (unsigned __int16 **)*((_QWORD *)this + 3);
          *v69 = *((_DWORD *)this + 12);
          *v70 = (struct _tagDLLINFO *)*((_QWORD *)this + 7);
          *v71 = *((_DWORD *)this + 16);
          *v72 = (struct _tagPSDLLINFO *)*((_QWORD *)this + 9);
          *((_DWORD *)this + 16) = 0;
          *((_DWORD *)this + 12) = 0;
          *((_DWORD *)this + 4) = 0;
          *((_QWORD *)this + 3) = 0;
          *((_QWORD *)this + 7) = 0;
          *((_QWORD *)this + 9) = 0;
        }
      }
      break;
    }
    ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 120LL))(v55);
    v21 = 0;
    if ( ApplicationType < 0 )
      break;
    v22 = 0;
    v23 = 0;
    *(_QWORD *)&v62.Data1 = 0;
    pptlib[0] = 0;
    v24 = (char *)v65;
    memset_0(v65, 0, 0x228u);
    for ( i = 0; i < 0x39; ++i )
    {
      v58 = 0;
      v59 = 0;
      v27 = (GUID **)&v24[8 * i];
      ApplicationType = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, GUID **))(*(_QWORD *)v54 + 64LL))(
                          v54,
                          i,
                          &v58,
                          &v59,
                          v27);
      if ( ApplicationType < 0 )
        goto LABEL_113;
      if ( !*v27 )
        goto LABEL_68;
      v28 = 0;
      if ( v58 == 128 )
        v28 = v59;
      ApplicationType = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v55 + 160LL))(v55, i, v28);
      if ( ApplicationType < 0 )
        goto LABEL_113;
      switch ( i )
      {
        case 0u:
          v88 = **v27;
          goto LABEL_68;
        case 1u:
          v23 = (const wchar_t *)*v27;
          goto LABEL_68;
        case 3u:
          v18 = *v27;
          goto LABEL_68;
        case 4u:
          v22 = *v27;
          goto LABEL_68;
        case 5u:
          *(_QWORD *)&v62.Data1 = *v27;
          goto LABEL_68;
        case 6u:
          v14 = **v27;
          goto LABEL_68;
        case 7u:
          v15 = **v27;
          goto LABEL_68;
        case 0xAu:
          Buf1 = **v27;
LABEL_68:
          v21 = 0;
          goto LABEL_69;
      }
      if ( i != 48 )
        goto LABEL_68;
      Data1 = (*v27)->Data1;
      v21 = 0;
      for ( j = 0; j < 4; ++j )
      {
        v25 = 2LL * j;
        if ( dword_18005A198[4 * j] == Data1 )
        {
          pptlib[0] = *((ITypeLib **)&g_mapThreadModels + 2 * j);
          break;
        }
      }
LABEL_69:
      v24 = (char *)v65;
    }
    if ( v23 )
      LODWORD(v53) = CAppExport::EFileTypeFromExt(v25, v23);
    ApplicationType = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 144LL))(v55);
    if ( ApplicationType >= 0 )
    {
      if ( !v23 || !*v23 )
        goto LABEL_84;
      if ( (v60 & 0x20) != 0 )
      {
        v31 = wcsrchr(v23, 0x5Cu);
        if ( v31 )
          v32 = v31 + 1;
        else
          v32 = v23;
        while ( 1 )
        {
          v33 = (&off_180059B90)[3 * v21];
          if ( !v33 )
            break;
          if ( !_wcsicmp(v32, v33) )
          {
            if ( !dword_180059BA0[6 * v21] )
              break;
            goto LABEL_83;
          }
          ++v21;
        }
LABEL_84:
        v34 = (WCHAR *)&word_18005C890;
      }
      else
      {
LABEL_83:
        v34 = (WCHAR *)v23;
      }
      v35 = memcmp_0(&Buf1, &GUID_NULL, 0x10u);
      v36 = 0;
      v51[1] = 0;
      if ( v35 )
      {
        v34 = (WCHAR *)&word_18005C890;
        goto LABEL_88;
      }
      if ( !v34 )
        goto LABEL_98;
LABEL_88:
      if ( !*v34 )
        goto LABEL_98;
      v37 = memcmp_0(&Buf1, &GUID_NULL, 0x10u);
      p_Buf1 = &v88;
      if ( v37 )
        p_Buf1 = &Buf1;
      if ( !(unsigned int)CAppExport::CheckHostingEnv(this, v34, p_Buf1, (unsigned int)v51[0], v56, pv, &v53) )
        v34 = (WCHAR *)pv[0];
      ApplicationType = CAppExport::CheckForSystemFile(v39, v34, &v51[1]);
      if ( ApplicationType >= 0 )
      {
        v36 = v51[1];
        if ( v51[1] )
          goto LABEL_97;
        v41 = CAppExport::CheckNonRedistFiles(v40, v34, &v88, v51[0]);
        ApplicationType = v41;
        if ( v41 >= 0 )
        {
          if ( v41 == 1 )
LABEL_97:
            v34 = (WCHAR *)&word_18005C890;
LABEL_98:
          LODWORD(v50) = v53;
          ApplicationType = CAppExport::AddClassInfo(
                              (__int64)this,
                              v34,
                              &v88,
                              (unsigned __int16 *)v22,
                              v18,
                              *(_QWORD *)&v62.Data1,
                              pptlib[0],
                              v50);
          if ( ApplicationType >= 0 )
          {
            if ( !v36 || !v23 )
            {
LABEL_104:
              if ( v34 && *v34 && (_DWORD)v53 != 7 )
              {
                v43 = v34;
                do
                {
                  v44 = *(WCHAR *)((char *)v43 + (char *)v90 - (char *)v34);
                  v45 = *v43 - v44;
                  if ( v45 )
                    break;
                  ++v43;
                }
                while ( v44 );
                v12 = v56;
                if ( v45 )
                {
                  v57 = *v56;
                  v62 = v14;
                  ApplicationType = RegScanUtil::RegisterDllToSelfReg(&v62, &v57, v34);
                  if ( ApplicationType < 0 )
                    break;
                  ApplicationType = StringCchCopyW(v90, 0x105u, v34);
                  if ( ApplicationType < 0 )
                    break;
                }
              }
              else
              {
                v12 = v56;
              }
              v57 = v15;
              v62 = v14;
              *(GUID *)pptlib = v88;
              v46 = v60;
              v11 = v66;
              ApplicationType = CAppExport::ExportInterfaceInfo(this, pptlib, &v62, &v57, v51[0], v66, v60);
              if ( ApplicationType < 0 )
                break;
              v57 = v88;
              v62 = *v12;
              ApplicationType = CAppExport::ExportSubscriptionInfo(this, &v62, &v57, v11);
              if ( ApplicationType < 0 )
                break;
              v48 = 0;
              v51[1] = 0;
              if ( v23 )
              {
                ApplicationType = CAppExport::CheckForSystemFile(v47, v23, &v51[1]);
                if ( ApplicationType < 0 )
                  break;
                v48 = v51[1];
              }
              if ( (v46 & 0x20) != 0 )
              {
                v18 = 0;
                if ( v23 && *v23 && !v48 )
                {
                  pptlib[0] = 0;
                  v57 = GUID_NULL;
                  TypeLib = LoadTypeLib(v23, pptlib);
                  if ( TypeLib >= 0 )
                  {
                    *(_QWORD *)&v62.Data1 = 0;
                    TypeLib = ((__int64 (__fastcall *)(ITypeLib *, struct _GUID *))pptlib[0]->lpVtbl->GetLibAttr)(
                                pptlib[0],
                                &v62);
                    if ( TypeLib >= 0 )
                    {
                      v57 = *(struct _GUID *)*(_QWORD *)&v62.Data1;
                      ((void (__fastcall *)(ITypeLib *))pptlib[0]->lpVtbl->ReleaseTLibAttr)(pptlib[0]);
                    }
                  }
                  if ( pptlib[0] )
                  {
                    ((void (__fastcall *)(ITypeLib *))pptlib[0]->lpVtbl->Release)(pptlib[0]);
                    pptlib[0] = 0;
                  }
                  if ( !TypeLib )
                  {
                    v51[1] = 0;
                    if ( !CMap<_GUID,_GUID &,unsigned long,unsigned long &>::GetAssocAt(
                            (char *)this + 128,
                            &v57,
                            &v51[1]) )
                    {
                      ApplicationType = CAppExport::AddTypeLibInfo(this, v23, (unsigned int)v51[0]);
                      if ( ApplicationType < 0 )
                        break;
                    }
                  }
                }
              }
              else
              {
                v18 = 0;
              }
              if ( pv[0] )
              {
                CoTaskMemFree(pv[0]);
                pv[0] = 0;
              }
              continue;
            }
            CString::CString((CString *)&v52, &word_18005C890);
            ApplicationType = CAppExport::GetLongFileName(v42, v23, (struct CString *)&v52);
            if ( ApplicationType >= 0 )
            {
              ApplicationType = CAppExport::AddDllNameInternal((__int64)this, v52, v53);
              if ( ApplicationType >= 0 )
              {
                CString::~CString((CString *)&v52);
                goto LABEL_104;
              }
            }
            CString::~CString((CString *)&v52);
          }
        }
      }
    }
    break;
  }
LABEL_113:
  memset_0(v65, 0, 0x228u);
  CoTaskMemFree(v65);
LABEL_15:
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  return (unsigned int)ApplicationType;
}

```

## disassembly

```asm
0x18000fe08  mov     rax, rsp
0x18000fe0b  push    rbp
0x18000fe0c  push    rbx
0x18000fe0d  push    rsi
0x18000fe0e  push    rdi
0x18000fe0f  push    r12
0x18000fe11  push    r13
0x18000fe13  push    r14
0x18000fe15  push    r15
0x18000fe17  lea     rbp, [rax-308h]
0x18000fe1e  sub     rsp, 3C8h
0x18000fe25  movaps  xmmword ptr [rax-58h], xmm6
0x18000fe29  movaps  xmmword ptr [rax-68h], xmm7
0x18000fe2d  mov     rax, cs:__security_cookie
0x18000fe34  xor     rax, rsp
0x18000fe37  mov     [rbp+300h+var_70], rax
0x18000fe3e  mov     r13d, r9d
0x18000fe41  mov     [rbp+300h+var_368], r9d
0x18000fe45  mov     r12, r8
0x18000fe48  mov     [rbp+300h+var_320], r8
0x18000fe4c  mov     r15, rdx
0x18000fe4f  mov     [rsp+400h+var_388], rdx
0x18000fe54  mov     rdi, rcx
0x18000fe57  mov     r14, [rbp+300h+arg_20]
0x18000fe5e  mov     [rbp+300h+var_318], r14
0x18000fe62  mov     r14, [rbp+300h+arg_28]
0x18000fe69  mov     [rbp+300h+var_310], r14
0x18000fe6d  mov     r14, [rbp+300h+arg_30]
0x18000fe74  mov     [rbp+300h+var_308], r14
0x18000fe78  mov     r14, [rbp+300h+arg_38]
0x18000fe7f  mov     [rbp+300h+var_300], r14
0x18000fe83  mov     r14, [rbp+300h+arg_40]
0x18000fe8a  mov     [rbp+300h+var_2F8], r14
0x18000fe8e  mov     r14, [rbp+300h+arg_48]
0x18000fe95  mov     [rbp+300h+var_2F0], r14
0x18000fe99  xor     esi, esi
0x18000fe9b  mov     [rsp+400h+var_398], rsi
0x18000fea0  mov     [rsp+400h+var_390], rsi
0x18000fea5  mov     [rbp+300h+var_330], 1
0x18000feac  mov     [rbp+300h+pv], rsi
0x18000feb0  movups  xmm6, cs:guidGlobalPartition
0x18000feb7  movups  xmm7, xmmword ptr cs:GUID_NULL.Data1
0x18000febe  mov     [rsp+400h+var_3B0], 1
0x18000fec6  lea     r8, [rsp+400h+var_3B0]
0x18000fecb  mov     rcx, [rcx+0B0h]
0x18000fed2  call    cs:__imp_ServerGetApplicationType
0x18000fed8  mov     ebx, eax
0x18000feda  test    eax, eax
0x18000fedc  js      loc_180010026
0x18000fee2  lea     r14d, [rsi+2]
0x18000fee6  cmp     [rsp+400h+var_3B0], 1
0x18000feeb  jnz     loc_180010099
0x18000fef1  mov     esi, 200005h
0x18000fef6  movups  xmm0, xmmword ptr [r15]
0x18000fefa  movdqu  xmmword ptr [rbp+300h+var_380.Data1], xmm0
0x18000feff  mov     r9d, r13d; unsigned int
0x18000ff02  mov     r8, r12; unsigned __int16 *
0x18000ff05  lea     rdx, [rbp+300h+var_380]; struct _GUID
0x18000ff09  mov     rcx, rdi; this
0x18000ff0c  call    ?ExportLegacyClasses@CAppExport@@AEAAJU_GUID@@PEAGK@Z; CAppExport::ExportLegacyClasses(_GUID,ushort *,ulong)
0x18000ff11  mov     ebx, eax
0x18000ff13  xor     r13d, r13d
0x18000ff16  test    eax, eax
0x18000ff18  js      loc_180010024
0x18000ff1e  lea     rax, [rbp+300h+var_330]
0x18000ff22  mov     [rbp+300h+var_2D0], rax
0x18000ff26  mov     [rbp+300h+var_2C8], r13d
0x18000ff2a  mov     [rbp+300h+var_2C4], 0F0000005h
0x18000ff31  mov     [rbp+300h+var_2C0], 13h
0x18000ff38  mov     [rbp+300h+var_2BC], 4
0x18000ff3f  mov     [rbp+300h+var_2B8], r15
0x18000ff43  mov     [rbp+300h+var_2B0], r13d
0x18000ff47  mov     [rbp+300h+var_2AC], 9
0x18000ff4e  mov     [rbp+300h+var_2A8], 48h ; 'H'
0x18000ff55  mov     [rbp+300h+var_2A4], 10h
0x18000ff5c  mov     [rsp+400h+var_398], r13
0x18000ff61  cmp     [rdi+0B0h], r13
0x18000ff68  jnz     short loc_18000FFAE
0x18000ff6a  mov     [rsp+400h+var_3A8], r13
0x18000ff6f  lea     rdx, [rsp+400h+var_3A8]
0x18000ff74  lea     rcx, IID_ISimpleTableDispenser
0x18000ff7b  call    cs:__imp_GetSimpleTableDispenser
0x18000ff81  mov     ebx, eax
0x18000ff83  test    eax, eax
0x18000ff85  js      loc_180010010
0x18000ff8b  mov     rcx, [rsp+400h+var_3A8]
0x18000ff90  xor     eax, eax
0x18000ff92  lock cmpxchg [rdi+0B0h], rcx
0x18000ff9b  jz      short loc_18000FFAE
0x18000ff9d  mov     rcx, [rsp+400h+var_3A8]
0x18000ffa2  mov     rax, [rcx]
0x18000ffa5  mov     rax, [rax+10h]
0x18000ffa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffae  mov     r8d, 10h; Size
0x18000ffb4  lea     rdx, TID_APPLICATION; Buf2
0x18000ffbb  lea     rcx, tidCOMSERVICES_CLASSES; Buf1
0x18000ffc2  call    memcmp_0
0x18000ffc7  test    eax, eax
0x18000ffc9  jz      short loc_18000FFCE
0x18000ffcb  or      esi, r14d
0x18000ffce  mov     rcx, [rdi+0B0h]
0x18000ffd5  mov     rax, [rcx]
0x18000ffd8  lea     rdx, [rsp+400h+var_398]
0x18000ffdd  mov     [rsp+400h+var_3C8], rdx
0x18000ffe2  mov     dword ptr [rsp+400h+var_3D0], esi
0x18000ffe6  mov     dword ptr [rsp+400h+var_3D8], 1
0x18000ffee  mov     [rsp+400h+var_3E0], r14
0x18000fff3  lea     r9, [rbp+300h+var_2D0]
0x18000fff7  lea     r8, tidCOMSERVICES_CLASSES
0x18000fffe  lea     rdx, didCOMSERVICES
0x180010005  mov     rax, [rax+18h]
0x180010009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001000e  mov     ebx, eax
0x180010010  test    ebx, ebx
0x180010012  js      short loc_180010024
0x180010014  cmp     [rsp+400h+var_398], r13
0x180010019  jnz     loc_1800100BC
0x18001001f  mov     ebx, 8007000Eh
0x180010024  xor     esi, esi
0x180010026  mov     rcx, [rbp+300h+pv]; pv
0x18001002a  test    rcx, rcx
0x18001002d  jz      short loc_180010035
0x18001002f  call    cs:__imp_CoTaskMemFree
0x180010035  mov     rcx, [rsp+400h+var_398]
0x18001003a  test    rcx, rcx
0x18001003d  jz      short loc_180010050
0x18001003f  mov     rax, [rcx]
0x180010042  mov     rax, [rax+10h]
0x180010046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001004b  mov     [rsp+400h+var_398], rsi
0x180010050  mov     rcx, [rsp+400h+var_390]
0x180010055  test    rcx, rcx
0x180010058  jz      short loc_180010066
0x18001005a  mov     rax, [rcx]
0x18001005d  mov     rax, [rax+10h]
0x180010061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010066  mov     eax, ebx
0x180010068  mov     rcx, [rbp+300h+var_70]
0x18001006f  xor     rcx, rsp; StackCookie
0x180010072  call    __security_check_cookie
0x180010077  lea     r11, [rsp+400h+var_38]
0x18001007f  movaps  xmm6, xmmword ptr [r11-18h]
0x180010084  movaps  xmm7, xmmword ptr [r11-28h]
0x180010089  mov     rsp, r11
0x18001008c  pop     r15
0x18001008e  pop     r14
0x180010090  pop     r13
0x180010092  pop     r12
0x180010094  pop     rdi
0x180010095  pop     rsi
0x180010096  pop     rbx
0x180010097  pop     rbp
0x180010098  retn
0x180010099  mov     esi, 400005h
0x18001009e  cmp     [rsp+400h+var_3B0], r14d
0x1800100a3  jnz     loc_18000FEF6
0x1800100a9  test    r13b, r13b
0x1800100ac  jns     loc_18000FEF6
0x1800100b2  mov     ebx, 80070057h
0x1800100b7  jmp     loc_180010024
0x1800100bc  mov     rcx, [rsp+400h+var_398]
0x1800100c1  mov     rax, [rcx]
0x1800100c4  mov     rax, [rax+18h]
0x1800100c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100cd  mov     ebx, eax
0x1800100cf  test    eax, eax
0x1800100d1  js      loc_180010024
0x1800100d7  mov     rcx, [rsp+400h+var_398]
0x1800100dc  mov     rax, [rcx]
0x1800100df  mov     rax, [rax+20h]
0x1800100e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e8  mov     ebx, eax
0x1800100ea  test    eax, eax
0x1800100ec  js      loc_180010024
0x1800100f2  mov     [rbp+300h+var_2E8], r12
0x1800100f6  mov     [rbp+300h+var_2E0], r13d
0x1800100fa  mov     [rbp+300h+var_2DC], 0F0000001h
0x180010101  mov     [rbp+300h+var_2D8], 82h
0x180010108  mov     rcx, r12; unsigned __int16 *
0x18001010b  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180010110  lea     eax, ds:2[rax*2]
0x180010117  mov     [rbp+300h+var_2D4], eax
0x18001011a  mov     [rsp+400h+var_390], r13
0x18001011f  cmp     [rdi+0B0h], r13
0x180010126  jnz     short loc_18001016C
0x180010128  mov     [rsp+400h+var_3A8], r13
0x18001012d  lea     rdx, [rsp+400h+var_3A8]
0x180010132  lea     rcx, IID_ISimpleTableDispenser
0x180010139  call    cs:__imp_GetSimpleTableDispenser
0x18001013f  mov     ebx, eax
0x180010141  test    eax, eax
0x180010143  js      loc_1800101D8
0x180010149  mov     rcx, [rsp+400h+var_3A8]
0x18001014e  xor     eax, eax
0x180010150  lock cmpxchg [rdi+0B0h], rcx
0x180010159  jz      short loc_18001016C
0x18001015b  mov     rcx, [rsp+400h+var_3A8]
0x180010160  mov     rax, [rcx]
0x180010163  mov     rax, [rax+10h]
0x180010167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001016c  mov     r8d, 10h; Size
0x180010172  lea     rdx, TID_APPLICATION; Buf2
0x180010179  lea     rcx, tidCOMSERVICES_CLASSES_EXPORT; Buf1
0x180010180  call    memcmp_0
0x180010185  neg     eax
0x180010187  sbb     r8d, r8d
0x18001018a  and     r8d, r14d
0x18001018d  add     r8d, 4
0x180010191  mov     rcx, [rdi+0B0h]
0x180010198  mov     rax, [rcx]
0x18001019b  lea     r9, [rsp+400h+var_390]
0x1800101a0  mov     [rsp+400h+var_3C8], r9
0x1800101a5  mov     dword ptr [rsp+400h+var_3D0], r8d
0x1800101aa  mov     dword ptr [rsp+400h+var_3D8], 1
0x1800101b2  mov     [rsp+400h+var_3E0], 1
0x1800101bb  lea     r9, [rbp+300h+var_2E8]
0x1800101bf  lea     r8, tidCOMSERVICES_CLASSES_EXPORT
0x1800101c6  lea     rdx, didCOMSERVICES
0x1800101cd  mov     rax, [rax+18h]
0x1800101d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101d6  mov     ebx, eax
0x1800101d8  test    ebx, ebx
0x1800101da  js      loc_180010024
0x1800101e0  cmp     [rsp+400h+var_390], r13
0x1800101e5  jz      loc_18001001F
0x1800101eb  mov     rcx, [rsp+400h+var_390]
0x1800101f0  mov     rax, [rcx]
0x1800101f3  mov     rax, [rax+18h]
0x1800101f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101fc  mov     ebx, eax
0x1800101fe  test    eax, eax
0x180010200  js      loc_180010024
0x180010206  mov     ecx, 228h; cb
0x18001020b  call    cs:__imp_CoTaskMemAlloc
0x180010211  mov     [rbp+300h+var_328], rax
0x180010215  test    rax, rax
0x180010218  jz      loc_18001001F
0x18001021e  mov     [rbp+300h+var_280], r13w
0x180010226  mov     dword ptr [rsp+400h+var_3A0], 1
0x18001022e  xorps   xmm0, xmm0
0x180010231  movups  [rbp+300h+var_2A0], xmm0
0x180010235  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18001023c  movdqu  [rbp+300h+Buf1], xmm1
0x180010241  mov     rcx, [rsp+400h+var_398]
0x180010246  mov     rax, [rcx]
0x180010249  mov     rax, [rax+28h]
0x18001024d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010252  cmp     eax, 80110801h
0x180010257  jz      loc_18001085C
0x18001025d  mov     rcx, [rsp+400h+var_390]
0x180010262  mov     rax, [rcx]
0x180010265  mov     rax, [rax+78h]
0x180010269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001026e  mov     ebx, eax
0x180010270  xor     esi, esi
0x180010272  test    eax, eax
0x180010274  js      loc_18001068D
0x18001027a  mov     r12, r13
0x18001027d  mov     r14, r13
0x180010280  mov     qword ptr [rbp+300h+var_350.Data1], rsi
0x180010284  mov     [rbp+300h+pptlib], rsi
0x180010288  xor     edx, edx; Val
0x18001028a  mov     r8d, 228h; Size
0x180010290  mov     rbx, [rbp+300h+var_328]
0x180010294  mov     rcx, rbx; void *
0x180010297  call    memset_0
0x18001029c  mov     r15d, esi
0x18001029f  cmp     r15d, 39h ; '9'
0x1800102a3  jnb     loc_1800103DB
0x1800102a9  mov     [rbp+300h+var_370], esi
0x1800102ac  mov     [rbp+300h+var_36C], esi
0x1800102af  mov     eax, r15d
0x1800102b2  lea     rsi, [rbx+rax*8]
0x1800102b6  mov     rcx, [rsp+400h+var_398]
0x1800102bb  mov     rax, [rcx]
0x1800102be  mov     [rsp+400h+var_3E0], rsi
0x1800102c3  lea     r9, [rbp+300h+var_36C]
0x1800102c7  lea     r8, [rbp+300h+var_370]
0x1800102cb  mov     edx, r15d
0x1800102ce  mov     rax, [rax+40h]
0x1800102d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102d7  mov     ebx, eax
0x1800102d9  xor     edx, edx
0x1800102db  test    eax, eax
0x1800102dd  js      loc_18001068B
0x1800102e3  mov     r9, [rsi]
0x1800102e6  test    r9, r9
0x1800102e9  jz      loc_1800103CD
0x1800102ef  mov     rcx, [rsp+400h+var_390]
0x1800102f4  mov     rax, [rcx]
0x1800102f7  mov     r8d, edx
0x1800102fa  cmp     [rbp+300h+var_370], 80h
0x180010301  cmovz   r8d, [rbp+300h+var_36C]
0x180010306  mov     edx, r15d
0x180010309  mov     rax, [rax+0A0h]
0x180010310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010315  mov     ebx, eax
0x180010317  test    eax, eax
0x180010319  js      loc_18001068B
0x18001031f  mov     eax, r15d
  ... truncated ...
```
