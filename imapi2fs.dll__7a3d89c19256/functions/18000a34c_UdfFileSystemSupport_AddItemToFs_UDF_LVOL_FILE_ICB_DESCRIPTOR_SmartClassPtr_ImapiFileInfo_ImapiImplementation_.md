# UdfFileSystemSupport::AddItemToFs(UDF_LVOL *,FILE_ICB_DESCRIPTOR *,SmartClassPtr<ImapiFileInfo,ImapiImplementation>,SmartClassPtr<ImapiFsObjectBase,ImapiImplementation>)

- ea: `0x18000a34c`
- end: `0x18000aea7`
- name: `?AddItemToFs@UdfFileSystemSupport@@IEAAXPEAVUDF_LVOL@@PEAVFILE_ICB_DESCRIPTOR@@V?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@V?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@@Z`
- size: `2907`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800223c0`
- `0x180022b74`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x18000960c`
- `0x18000a34c`
- `0x18000c8d0`
- `0x18000ff04`
- `0x18001230c`
- `0x180013aec`
- `0x180014040`
- `0x18001b974`
- `0x180023c08`
- `0x1800251dc`
- `0x1800251f6`
- `0x180028568`
- `0x18002ade4`
- `0x18002d4e4`
- `0x180038c94`
- `0x1800631b4`
- `0x180063a90`
- `0x180067558`
- `0x180088010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x18000a52a`
- `ole32!CreateStreamOnHGlobal` at `0x18000a52a`
- `KERNEL32!GlobalFree` at `0x18000a708`
- `KERNEL32!GlobalFree` at `0x18000a708`
- `KERNEL32!GlobalAlloc` at `0x18000a41f`
- `KERNEL32!GlobalAlloc` at `0x18000a41f`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall UdfFileSystemSupport::AddItemToFs(
        UdfFileSystemSupport *this,
        struct UDF_LVOL *a2,
        FILE_ICB_DESCRIPTOR *a3,
        ImapiFsObjectBase ***a4,
        __int64 **a5)
{
  PVOID *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // rax
  unsigned int *v13; // rdx
  const void *v14; // rdi
  SIZE_T v15; // r15
  HGLOBAL v16; // rax
  void *v17; // r14
  CIMAPIException *v18; // rax
  CIMAPIException *v19; // rax
  CIMAPIException **v20; // rbx
  __int64 v21; // r9
  __int64 **v22; // r14
  __int64 *v23; // rdx
  __int64 v24; // r10
  LPSTREAM v25; // r8
  ImapiFsObjectBase **v26; // rax
  LPSTREAM v27; // r8
  ImapiFsObjectBase **v28; // rax
  const struct ATL::CComBSTR *v29; // rax
  CIMAPIException *v30; // rax
  CIMAPIException *v31; // rax
  CIMAPIException **v32; // rbx
  CIMAPIException *v33; // rax
  CIMAPIException *v34; // rax
  CIMAPIException **v35; // rbx
  __int16 v36; // r12
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException *v38; // rax
  CIMAPIException *v39; // rax
  CIMAPIException **v40; // rbx
  const struct ATL::CComBSTR *v41; // rax
  CIMAPIException *v42; // rax
  CIMAPIException *v43; // rax
  CIMAPIException **v44; // rbx
  unsigned int v45; // eax
  struct SPACE_BITMAP_DESCRIPTOR *v46; // rax
  CIMAPIException *v47; // rax
  CIMAPIException *v48; // rax
  CIMAPIException **v49; // rbx
  const struct ATL::CComBSTR *v50; // rax
  CIMAPIException *v51; // rax
  CIMAPIException *v52; // rax
  CIMAPIException **v53; // rbx
  __int64 *v54; // rdx
  __int64 v55; // r8
  ImapiFsObjectBase **v56; // rax
  ImapiFsObjectBase **v57; // rax
  const struct ATL::CComBSTR *v58; // rax
  CIMAPIException *v59; // rax
  CIMAPIException *v60; // rax
  CIMAPIException **v61; // rbx
  unsigned int v62[2]; // [rsp+40h] [rbp-348h] BYREF
  __int16 v63[2]; // [rsp+48h] [rbp-340h] BYREF
  unsigned int v64; // [rsp+4Ch] [rbp-33Ch] BYREF
  LPSTREAM ppstm; // [rsp+50h] [rbp-338h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+58h] [rbp-330h] BYREF
  CIMAPIException **v67; // [rsp+60h] [rbp-328h] BYREF
  CIMAPIException **v68; // [rsp+68h] [rbp-320h] BYREF
  CIMAPIException **v69; // [rsp+70h] [rbp-318h] BYREF
  CIMAPIException **v70; // [rsp+78h] [rbp-310h] BYREF
  CIMAPIException **v71; // [rsp+80h] [rbp-308h] BYREF
  CIMAPIException **v72; // [rsp+88h] [rbp-300h] BYREF
  CIMAPIException **v73; // [rsp+90h] [rbp-2F8h] BYREF
  _BYTE v74[88]; // [rsp+98h] [rbp-2F0h] BYREF
  _BYTE v75[88]; // [rsp+F0h] [rbp-298h] BYREF
  _BYTE v76[88]; // [rsp+148h] [rbp-240h] BYREF
  _BYTE v77[88]; // [rsp+1A0h] [rbp-1E8h] BYREF
  _BYTE v78[88]; // [rsp+1F8h] [rbp-190h] BYREF
  _BYTE v79[88]; // [rsp+250h] [rbp-138h] BYREF
  _BYTE v80[88]; // [rsp+2A8h] [rbp-E0h] BYREF
  _BYTE v81[136]; // [rsp+300h] [rbp-88h] BYREF
  CIMAPIException **v82; // [rsp+3A0h] [rbp+18h] BYREF
  ImapiFsObjectBase ***v83; // [rsp+3A8h] [rbp+20h]

  v83 = a4;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 112, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  ppstm = 0;
  v10 = *((_QWORD *)a3 + 2);
  if ( (*(_BYTE *)(v10 + 34) & 7) != 3 )
  {
    v64 = 0;
    v62[0] = 0;
    v63[0] = 0;
    LOBYTE(v82) = 0;
    v36 = *(_WORD *)(v10 + 20);
    if ( v36 != 4 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 4) != 0 && *((_BYTE *)v9 + 65) >= 2u )
      {
        FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(**a4);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          118,
          (unsigned int)&WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
          *(_QWORD *)FullPathOriginal,
          v36);
      }
      v38 = (CIMAPIException *)operator new(0x58u);
      v82 = (CIMAPIException **)v38;
      if ( v38 )
        v39 = CIMAPIException::CIMAPIException(v38, -1062555308, *((_QWORD *)this + 1));
      else
        v39 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v39);
      v40 = v82;
      if ( v82 && *v82 )
      {
        CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2599);
        v69 = v40;
        if ( v40 )
          ++*((_DWORD *)v40 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v69;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v77,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v77;
    }
    if ( !UdfFileSystemSupport::IsDataContiguous(this, a2, a3) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v41 = ImapiFsObjectBase::GetFullPathOriginal(**a4);
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          119,
          &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
          *(_QWORD *)v41);
      }
      v42 = (CIMAPIException *)operator new(0x58u);
      v82 = (CIMAPIException **)v42;
      if ( v42 )
        v43 = CIMAPIException::CIMAPIException(v42, -1062555308, *((_QWORD *)this + 1));
      else
        v43 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v43);
      v44 = v82;
      if ( v82 && *v82 )
      {
        CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2607);
        v70 = v44;
        if ( v44 )
          ++*((_DWORD *)v44 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v70;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v78,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v78;
    }
    *((_QWORD *)**a4 + 32) = *(_QWORD *)(*((_QWORD *)a3 + 2) + 56LL);
    FILE_ICB_DESCRIPTOR::InitializeAllocationIterator(a3, a2);
    v45 = (*(__int64 (__fastcall **)(FILE_ICB_DESCRIPTOR *))(*(_QWORD *)a3 + 64LL))(a3);
    v46 = (struct SPACE_BITMAP_DESCRIPTOR *)*((_QWORD *)a2
                                            + (unsigned __int16)UDF_LVOL::GetPartitionNumberForAllocationTag(a2, v45)
                                            + 14);
    if ( !v46 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 122, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
      }
      v47 = (CIMAPIException *)operator new(0x58u);
      v82 = (CIMAPIException **)v47;
      if ( v47 )
        v48 = CIMAPIException::CIMAPIException(v47, -1062555392);
      else
        v48 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v48);
      v49 = v82;
      if ( v82 && *v82 )
      {
        CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2658);
        v71 = v49;
        if ( v49 )
          ++*((_DWORD *)v49 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v71;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v79,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v79;
    }
    if ( FILE_ICB_DESCRIPTOR::NextAllocation(a3, 0, &v64, v62, v63, (unsigned __int8 *)&v82, v46) )
    {
      *((_DWORD *)**a4 + 61) = 1;
      *((_DWORD *)**a4 + 62) = *((_DWORD *)this + 23) + v64;
    }
    if ( (_BYTE)v82 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v50 = ImapiFsObjectBase::GetFullPathOriginal(**a4);
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          123,
          &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
          *(_QWORD *)v50);
      }
      v51 = (CIMAPIException *)operator new(0x58u);
      v82 = (CIMAPIException **)v51;
      if ( v51 )
        v52 = CIMAPIException::CIMAPIException(v51, -1062555309, *((_QWORD *)this + 1));
      else
        v52 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v52);
      v53 = v82;
      if ( v82 && *v82 )
      {
        CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2677);
        v72 = v53;
        if ( v53 )
          ++*((_DWORD *)v53 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v72;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v80,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v80;
    }
    v22 = a5;
    v54 = *a5;
    v55 = **a5;
    if ( *(_DWORD *)(v55 + 56) )
    {
      if ( *(_DWORD *)(v55 + 56) == 1 && *((_DWORD *)**a4 + 14) == 2 )
      {
        *(_QWORD *)v62 = *a5;
        ++*((_DWORD *)v54 + 2);
        v57 = *a4;
        v82 = v57;
        if ( v57 )
          ++*((_DWORD *)v57 + 2);
        ImapiFileInfo::AddImportedStream(v55, &v82);
        goto LABEL_135;
      }
    }
    else if ( *((_DWORD *)**a4 + 14) == 1 )
    {
      *(_QWORD *)v62 = *a5;
      ++*((_DWORD *)v54 + 2);
      v56 = *a4;
      v82 = v56;
      if ( v56 )
        ++*((_DWORD *)v56 + 2);
      ImapiDirectoryInfo::AddImportedFile(v55, &v82);
LABEL_135:
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v62);
      goto LABEL_136;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v58 = ImapiFsObjectBase::GetFullPathOriginal(**a4);
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        124,
        &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
        *(_QWORD *)v58);
    }
    v59 = (CIMAPIException *)operator new(0x58u);
    v82 = (CIMAPIException **)v59;
    if ( v59 )
      v60 = CIMAPIException::CIMAPIException(v59, -1062555392);
    else
      v60 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v60);
    v61 = v82;
    if ( v82 && *v82 )
    {
      CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2696);
      v73 = v61;
      if ( v61 )
        ++*((_DWORD *)v61 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v73;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v81, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v81;
  }
  if ( *(_WORD *)v10 == 266 )
  {
    v11 = *(unsigned int *)(v10 + 208) + 216LL;
  }
  else
  {
    v12 = 176;
    if ( *(_WORD *)v10 != 261 )
      v12 = 216;
    v13 = (unsigned int *)(v10 + 168);
    if ( *(_WORD *)v10 != 261 )
      v13 = (unsigned int *)(v10 + 208);
    v11 = v12 + *v13;
  }
  v14 = (const void *)(v10 + v11);
  v15 = *(_QWORD *)(v10 + 56);
  v16 = GlobalAlloc(0x40u, v15);
  v17 = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 115, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    }
    v18 = (CIMAPIException *)operator new(0x58u);
    v82 = (CIMAPIException **)v18;
    if ( v18 )
      v19 = CIMAPIException::CIMAPIException(v18, -2147024882);
    else
      v19 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v19);
    v20 = v82;
    if ( v82 && *v82 )
    {
      CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2524);
      pExceptionObject = v20;
      if ( v20 )
        ++*((_DWORD *)v20 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v74, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v74;
  }
  memcpy_0(v16, v14, v15);
  if ( CreateStreamOnHGlobal(v17, 1, &ppstm) < 0 )
  {
    GlobalFree(v17);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 117, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
    }
    v33 = (CIMAPIException *)operator new(0x58u);
    v82 = (CIMAPIException **)v33;
    if ( v33 )
      v34 = CIMAPIException::CIMAPIException(v33, -1062555392);
    else
      v34 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v34);
    v35 = v82;
    if ( v82 && *v82 )
    {
      CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2581);
      v68 = v35;
      if ( v35 )
        ++*((_DWORD *)v35 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v68;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v76, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v76;
  }
  try
  {
    *((_QWORD *)**a4 + 32) = v15;
    v22 = a5;
    v23 = *a5;
    v24 = **a5;
    if ( *(_DWORD *)(v24 + 56) )
    {
      if ( *(_DWORD *)(v24 + 56) == 1 && *((_DWORD *)**a4 + 14) == 2 )
      {
        *(_QWORD *)v62 = *a5;
        ++*((_DWORD *)v23 + 2);
        v27 = ppstm;
        v28 = *a4;
        v82 = v28;
        if ( v28 )
          ++*((_DWORD *)v28 + 2);
        LOBYTE(v21) = 1;
        ImapiFileInfo::AddStream(v24, &v82, v27, v21, 0);
        goto LABEL_39;
      }
    }
    else if ( *((_DWORD *)**a4 + 14) == 1 )
    {
      *(_QWORD *)v62 = *a5;
      ++*((_DWORD *)v23 + 2);
      v25 = ppstm;
      v26 = *a4;
      v82 = v26;
      if ( v26 )
        ++*((_DWORD *)v26 + 2);
      LOBYTE(v21) = 1;
      ImapiDirectoryInfo::AddFile(v24, &v82, v25, v21, 0);
LABEL_39:
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v62);
      goto LABEL_156;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v29 = ImapiFsObjectBase::GetFullPathOriginal(**a4);
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        116,
        &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids,
        *(_QWORD *)v29);
    }
    v30 = (CIMAPIException *)operator new(0x58u);
    v82 = (CIMAPIException **)v30;
    if ( v30 )
      v31 = CIMAPIException::CIMAPIException(v30, -1062555392);
    else
      v31 = 0;
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v82, v31);
    v32 = v82;
    if ( v82 && *v82 )
    {
      CIMAPIException::SetCodeRefInfo(*v82, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiudf.cpp", 2556);
      v67 = v32;
      if ( v32 )
        ++*((_DWORD *)v32 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v67;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v75, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v75;
  }
  catch ( ... )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    throw;
  }
LABEL_156:
  (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_136:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 125, &WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids);
  }
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(a4);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(v22);
}

```

## disassembly

```asm
0x18000a34c  mov     [rsp+arg_0], rbx
0x18000a351  mov     [rsp+arg_18], r9
0x18000a356  push    rdi
0x18000a357  push    r12
0x18000a359  push    r13
0x18000a35b  push    r14
0x18000a35d  push    r15
0x18000a35f  sub     rsp, 360h
0x18000a366  mov     rbx, r9
0x18000a369  mov     r14, r8
0x18000a36c  mov     r13, rdx
0x18000a36f  mov     r15, rcx
0x18000a372  lea     rdx, WPP_GLOBAL_Control
0x18000a379  mov     r9, cs:WPP_GLOBAL_Control
0x18000a380  cmp     r9, rdx
0x18000a383  jz      short loc_18000A3B6
0x18000a385  test    byte ptr [r9+44h], 8
0x18000a38a  jz      short loc_18000A3B6
0x18000a38c  cmp     byte ptr [r9+41h], 5
0x18000a391  jb      short loc_18000A3B6
0x18000a393  mov     edx, 70h ; 'p'
0x18000a398  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x18000a39f  mov     rcx, [r9+38h]
0x18000a3a3  call    WPP_SF_
0x18000a3a8  mov     r9, cs:WPP_GLOBAL_Control
0x18000a3af  lea     rdx, WPP_GLOBAL_Control
0x18000a3b6  xor     r12d, r12d
0x18000a3b9  mov     [rsp+388h+ppstm], r12
0x18000a3be  mov     rcx, [r14+10h]
0x18000a3c2  mov     al, [rcx+22h]
0x18000a3c5  and     al, 7
0x18000a3c7  cmp     al, 3
0x18000a3c9  jnz     loc_18000A7EE
0x18000a3cf  mov     eax, 10Ah
0x18000a3d4  cmp     [rcx], ax
0x18000a3d7  jnz     short loc_18000A3E8
0x18000a3d9  mov     edi, [rcx+0D0h]
0x18000a3df  add     rdi, 0D8h
0x18000a3e6  jmp     short loc_18000A410
0x18000a3e8  mov     eax, 0B0h
0x18000a3ed  lea     edx, [rax+28h]
0x18000a3f0  lea     r8d, [rax+55h]
0x18000a3f4  cmp     [rcx], r8w
0x18000a3f8  cmovnz  eax, edx
0x18000a3fb  lea     rdx, [rcx+0A8h]
0x18000a402  jz      short loc_18000A40B
0x18000a404  lea     rdx, [rcx+0D0h]
0x18000a40b  mov     edi, [rdx]
0x18000a40d  add     rdi, rax
0x18000a410  add     rdi, rcx
0x18000a413  mov     r15, [rcx+38h]
0x18000a417  mov     rdx, r15; dwBytes
0x18000a41a  mov     ecx, 40h ; '@'; uFlags
0x18000a41f  call    cs:__imp_GlobalAlloc
0x18000a425  mov     r14, rax
0x18000a428  test    rax, rax
0x18000a42b  jnz     loc_18000A50F
0x18000a431  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a438  lea     rdx, WPP_GLOBAL_Control
0x18000a43f  cmp     rcx, rdx
0x18000a442  jz      short loc_18000A466
0x18000a444  lea     edi, [rax+4]
0x18000a447  test    [rcx+44h], dil
0x18000a44b  jz      short loc_18000A466
0x18000a44d  cmp     byte ptr [rcx+41h], 2
0x18000a451  jb      short loc_18000A466
0x18000a453  lea     edx, [rax+73h]
0x18000a456  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x18000a45d  mov     rcx, [rcx+38h]
0x18000a461  call    WPP_SF_
0x18000a466  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000a46b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a470  mov     [rsp+388h+arg_10], rax
0x18000a478  test    rax, rax
0x18000a47b  jz      short loc_18000A48C
0x18000a47d  mov     edx, 8007000Eh; int
0x18000a482  mov     rcx, rax; this
0x18000a485  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000a48a  jmp     short loc_18000A48F
0x18000a48c  mov     rax, r12
0x18000a48f  mov     rdx, rax
0x18000a492  lea     rcx, [rsp+388h+arg_10]
0x18000a49a  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000a49f  nop
0x18000a4a0  mov     rbx, [rsp+388h+arg_10]
0x18000a4a8  test    rbx, rbx
0x18000a4ab  jz      short loc_18000A4E6
0x18000a4ad  cmp     [rbx], r12
0x18000a4b0  jz      short loc_18000A4E6
0x18000a4b2  mov     r8d, 9DCh; int
0x18000a4b8  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x18000a4bf  mov     rcx, [rbx]; this
0x18000a4c2  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000a4c7  mov     [rsp+388h+pExceptionObject], rbx
0x18000a4cc  test    rbx, rbx
0x18000a4cf  jz      short loc_18000A4D4
0x18000a4d1  inc     dword ptr [rbx+8]
0x18000a4d4  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000a4db  lea     rcx, [rsp+388h+pExceptionObject]; pExceptionObject
0x18000a4e0  call    _CxxThrowException_0
0x18000a4e6  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000a4ed  lea     rcx, [rsp+388h+var_2F0]; this
0x18000a4f5  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000a4fa  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000a501  lea     rcx, [rsp+388h+var_2F0]; pExceptionObject
0x18000a509  call    _CxxThrowException_0
0x18000a50f  mov     r8, r15; Size
0x18000a512  mov     rdx, rdi; Src
0x18000a515  mov     rcx, r14; void *
0x18000a518  call    memcpy_0
0x18000a51d  lea     r8, [rsp+388h+ppstm]; ppstm
0x18000a522  mov     edx, 1; fDeleteOnRelease
0x18000a527  mov     rcx, r14; hGlobal
0x18000a52a  call    cs:__imp_CreateStreamOnHGlobal
0x18000a530  test    eax, eax
0x18000a532  js      loc_18000A705
0x18000a538  mov     rax, [rbx]
0x18000a53b  mov     rcx, [rax]
0x18000a53e  mov     [rcx+100h], r15
0x18000a545  mov     r14, [rsp+388h+arg_20]
0x18000a54d  mov     rdx, [r14]
0x18000a550  mov     r10, [rdx]
0x18000a553  cmp     [r10+38h], r12d
0x18000a557  jnz     short loc_18000A5A4
0x18000a559  mov     rax, [rbx]
0x18000a55c  mov     rcx, [rax]
0x18000a55f  cmp     dword ptr [rcx+38h], 1
0x18000a563  jnz     loc_18000A611
0x18000a569  mov     qword ptr [rsp+388h+var_348], rdx
0x18000a56e  inc     dword ptr [rdx+8]
0x18000a571  mov     r8, [rsp+388h+ppstm]
0x18000a576  mov     rax, [rbx]
0x18000a579  mov     [rsp+388h+arg_10], rax
0x18000a581  test    rax, rax
0x18000a584  jz      short loc_18000A589
0x18000a586  inc     dword ptr [rax+8]
0x18000a589  mov     byte ptr [rsp+388h+var_368], r12b
0x18000a58e  mov     r9b, 1
0x18000a591  lea     rdx, [rsp+388h+arg_10]
0x18000a599  mov     rcx, r10
0x18000a59c  call    ?AddFile@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@PEAUIStream@@_N2@Z; ImapiDirectoryInfo::AddFile(SmartClassPtr<ImapiFileInfo,ImapiImplementation>,IStream *,bool,bool)
0x18000a5a1  nop
0x18000a5a2  jmp     short loc_18000A5F0
0x18000a5a4  cmp     dword ptr [r10+38h], 1
0x18000a5a9  jnz     short loc_18000A611
0x18000a5ab  mov     rax, [rbx]
0x18000a5ae  mov     rcx, [rax]
0x18000a5b1  cmp     dword ptr [rcx+38h], 2
0x18000a5b5  jnz     short loc_18000A611
0x18000a5b7  mov     qword ptr [rsp+388h+var_348], rdx
0x18000a5bc  inc     dword ptr [rdx+8]
0x18000a5bf  mov     r8, [rsp+388h+ppstm]
0x18000a5c4  mov     rax, [rbx]
0x18000a5c7  mov     [rsp+388h+arg_10], rax
0x18000a5cf  test    rax, rax
0x18000a5d2  jz      short loc_18000A5D7
0x18000a5d4  inc     dword ptr [rax+8]
0x18000a5d7  mov     byte ptr [rsp+388h+var_368], r12b
0x18000a5dc  mov     r9b, 1
0x18000a5df  lea     rdx, [rsp+388h+arg_10]
0x18000a5e7  mov     rcx, r10
0x18000a5ea  call    ?AddStream@ImapiFileInfo@@QEAAXV?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@PEAUIStream@@_N2@Z; ImapiFileInfo::AddStream(SmartClassPtr<ImapiFileInfo,ImapiImplementation>,IStream *,bool,bool)
0x18000a5ef  nop
0x18000a5f0  lea     rcx, [rsp+388h+var_348]; void *
0x18000a5f5  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000a5fa  nop
0x18000a5fb  mov     rcx, [rsp+388h+ppstm]
0x18000a600  mov     rax, [rcx]
0x18000a603  mov     rax, [rax+10h]
0x18000a607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a60c  jmp     loc_18000AD50
0x18000a611  mov     rax, cs:WPP_GLOBAL_Control
0x18000a618  lea     rdx, WPP_GLOBAL_Control
0x18000a61f  cmp     rax, rdx
0x18000a622  jz      short loc_18000A65D
0x18000a624  mov     edi, 4
0x18000a629  test    [rax+44h], dil
0x18000a62d  jz      short loc_18000A65D
0x18000a62f  cmp     byte ptr [rax+41h], 2
0x18000a633  jb      short loc_18000A65D
0x18000a635  mov     rcx, [rbx]
0x18000a638  mov     rcx, [rcx]; this
0x18000a63b  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18000a640  lea     edx, [rdi+70h]
0x18000a643  mov     r9, [rax]
0x18000a646  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x18000a64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a654  mov     rcx, [rcx+38h]
0x18000a658  call    WPP_SF_S
0x18000a65d  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000a662  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a667  mov     [rsp+388h+arg_10], rax
0x18000a66f  test    rax, rax
0x18000a672  jz      short loc_18000A683
0x18000a674  mov     edx, 0C0AAB100h; int
0x18000a679  mov     rcx, rax; this
0x18000a67c  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000a681  jmp     short loc_18000A686
0x18000a683  mov     rax, r12
0x18000a686  mov     rdx, rax
0x18000a689  lea     rcx, [rsp+388h+arg_10]
0x18000a691  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000a696  nop
0x18000a697  mov     rbx, [rsp+388h+arg_10]
0x18000a69f  test    rbx, rbx
0x18000a6a2  jz      short loc_18000A6DC
0x18000a6a4  cmp     [rbx], r12
0x18000a6a7  jz      short loc_18000A6DC
0x18000a6a9  mov     r8d, 9FCh; int
0x18000a6af  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x18000a6b6  mov     rcx, [rbx]; this
0x18000a6b9  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000a6be  mov     [rsp+388h+var_328], rbx
0x18000a6c3  test    rbx, rbx
0x18000a6c6  jz      short loc_18000A6CB
0x18000a6c8  inc     dword ptr [rbx+8]
0x18000a6cb  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000a6d2  lea     rcx, [rsp+388h+var_328]; pExceptionObject
0x18000a6d7  call    _CxxThrowException_0
0x18000a6dc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000a6e3  lea     rcx, [rsp+388h+var_298]; this
0x18000a6eb  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000a6f0  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000a6f7  lea     rcx, [rsp+388h+var_298]; pExceptionObject
0x18000a6ff  call    _CxxThrowException_0
0x18000a705  mov     rcx, r14; hMem
0x18000a708  call    cs:__imp_GlobalFree
0x18000a70e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a715  lea     rdx, WPP_GLOBAL_Control
0x18000a71c  cmp     rcx, rdx
0x18000a71f  jz      short loc_18000A745
0x18000a721  mov     edi, 4
0x18000a726  test    [rcx+44h], dil
0x18000a72a  jz      short loc_18000A745
0x18000a72c  cmp     byte ptr [rcx+41h], 2
0x18000a730  jb      short loc_18000A745
0x18000a732  lea     edx, [rdi+71h]
0x18000a735  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x18000a73c  mov     rcx, [rcx+38h]
0x18000a740  call    WPP_SF_
0x18000a745  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000a74a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a74f  mov     [rsp+388h+arg_10], rax
0x18000a757  test    rax, rax
0x18000a75a  jz      short loc_18000A76B
0x18000a75c  mov     edx, 0C0AAB100h; int
0x18000a761  mov     rcx, rax; this
0x18000a764  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000a769  jmp     short loc_18000A76E
0x18000a76b  mov     rax, r12
0x18000a76e  mov     rdx, rax
0x18000a771  lea     rcx, [rsp+388h+arg_10]
0x18000a779  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000a77e  nop
0x18000a77f  mov     rbx, [rsp+388h+arg_10]
0x18000a787  test    rbx, rbx
0x18000a78a  jz      short loc_18000A7C5
0x18000a78c  cmp     [rbx], r12
0x18000a78f  jz      short loc_18000A7C5
0x18000a791  mov     r8d, 0A15h; int
0x18000a797  lea     rdx, aDriversStorage_15; "drivers\\storage\\imapi2\\filesystemima"...
0x18000a79e  mov     rcx, [rbx]; this
0x18000a7a1  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000a7a6  mov     [rsp+388h+var_320], rbx
0x18000a7ab  test    rbx, rbx
0x18000a7ae  jz      short loc_18000A7B3
0x18000a7b0  inc     dword ptr [rbx+8]
0x18000a7b3  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000a7ba  lea     rcx, [rsp+388h+var_320]; pExceptionObject
0x18000a7bf  call    _CxxThrowException_0
0x18000a7c5  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000a7cc  lea     rcx, [rsp+388h+var_240]; this
0x18000a7d4  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000a7d9  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000a7e0  lea     rcx, [rsp+388h+var_240]; pExceptionObject
0x18000a7e8  call    _CxxThrowException_0
0x18000a7ee  mov     [rsp+388h+var_33C], r12d
0x18000a7f3  mov     [rsp+388h+var_348], r12d
0x18000a7f8  mov     [rsp+388h+var_340], r12w
0x18000a7fe  mov     byte ptr [rsp+388h+arg_10], r12b
0x18000a806  movzx   r12d, word ptr [rcx+14h]
0x18000a80b  mov     edi, 4
0x18000a810  cmp     di, r12w
0x18000a814  jz      loc_18000A909
0x18000a81a  cmp     r9, rdx
0x18000a81d  jz      short loc_18000A859
0x18000a81f  test    [r9+44h], dil
0x18000a823  jz      short loc_18000A859
0x18000a825  cmp     byte ptr [r9+41h], 2
0x18000a82a  jb      short loc_18000A859
0x18000a82c  mov     rcx, [rbx]
0x18000a82f  mov     rcx, [rcx]; this
0x18000a832  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18000a837  lea     edx, [rdi+72h]
0x18000a83a  mov     dword ptr [rsp+388h+var_368], r12d
0x18000a83f  mov     r9, [rax]
0x18000a842  lea     r8, WPP_cfb9f38fb45937fd90037ddd4a0f05da_Traceguids
0x18000a849  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a850  mov     rcx, [rcx+38h]
0x18000a854  call    WPP_SF_Sd
  ... truncated ...
```
