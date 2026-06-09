# CMVEngine::QueryPackageForState(ProvSource const &,std::vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>> const &,_MVProvisionData * *,ulong *)

- ea: `0x18001a6fc`
- end: `0x18001b05f`
- name: `?QueryPackageForState@CMVEngine@@AEAAJAEBVProvSource@@AEBV?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@PEAPEAU_MVProvisionData@@PEAK@Z`
- size: `2403`
- prototype: `__int64 __fastcall(CMVEngine *this, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015740`

## callees

- `0x1800010c8`
- `0x1800021b4`
- `0x1800098dc`
- `0x18000a18c`
- `0x18000b030`
- `0x18000f230`
- `0x180010ad8`
- `0x180011328`
- `0x1800117b8`
- `0x180011a70`
- `0x180013c8c`
- `0x180016f5c`
- `0x18001a6fc`
- `0x18001def0`
- `0x180034920`
- `0x180036780`
- `0x18003804c`
- `0x18003bbe8`
- `0x18003bd10`
- `0x18004371a`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001a90b`
- `msvcrt!_wcsnicmp` at `0x18001a90b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a78e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a934`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a956`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a973`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a990`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa38`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa55`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa72`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ab6e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001abcb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001abed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ac0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ac2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ac49`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001acee`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ad2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ad56`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af20`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af3d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af5a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af77`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001afb3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001afd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aff2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b00f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a78e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a934`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a956`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a973`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a990`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa38`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa55`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aa72`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ab6e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001abcb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001abed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ac0f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ac2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ac49`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001acee`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ad2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ad56`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af20`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af3d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af5a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af77`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001afb3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001afd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001aff2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b00f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a813`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001a813`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMVEngine::QueryPackageForState(CMVEngine *this, __int64 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  char v7; // r14
  __int64 v8; // rbx
  __int64 v9; // rax
  _QWORD *v10; // r12
  _DWORD *v11; // r9
  __int64 v12; // r15
  const struct expanded_wstring *CosaFolderPath; // rax
  size_t v14; // rbx
  const wchar_t *v15; // rdi
  __int64 v16; // rax
  int v17; // edi
  int v18; // r14d
  int StringFromProvisionState; // eax
  unsigned int v20; // edi
  void *v22; // rbx
  __int64 v23; // r8
  ProvResults *v24; // rdi
  ProvResults *v25; // rsi
  int v26; // eax
  unsigned int v27; // r14d
  TraceLoggingCorrelationVector *v28; // rcx
  __int64 v29; // rax
  ProvResults **v30; // r12
  ProvResults *v31; // r14
  int MVProvisionData; // eax
  __int64 *v33; // rcx
  __int64 *v34; // rax
  __int64 *v35; // rdx
  __int64 v36; // r8
  int v37; // r8d
  __int64 v38; // rcx
  int v39; // ecx
  int v40; // r15d
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v44; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v45[3]; // [rsp+50h] [rbp-B0h] BYREF
  char v46; // [rsp+68h] [rbp-98h]
  _DWORD *v47; // [rsp+70h] [rbp-90h] BYREF
  ProvResults *v48; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h]
  void *v51; // [rsp+90h] [rbp-70h]
  _BYTE v52[24]; // [rsp+98h] [rbp-68h] BYREF
  void *v53[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v55; // [rsp+C8h] [rbp-38h]
  void *v56[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v58; // [rsp+E8h] [rbp-18h]
  void *v59[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v60; // [rsp+100h] [rbp+0h]
  unsigned __int64 v61; // [rsp+108h] [rbp+8h]
  void *v62; // [rsp+110h] [rbp+10h] BYREF
  __int64 v63; // [rsp+120h] [rbp+20h]
  unsigned __int64 v64; // [rsp+128h] [rbp+28h]
  int v65; // [rsp+130h] [rbp+30h] BYREF
  char v66; // [rsp+134h] [rbp+34h]
  GUID ActivityId; // [rsp+138h] [rbp+38h] BYREF
  _DWORD v68[4]; // [rsp+148h] [rbp+48h] BYREF
  void *v69; // [rsp+158h] [rbp+58h] BYREF
  __int64 v70; // [rsp+168h] [rbp+68h]
  unsigned __int64 v71; // [rsp+170h] [rbp+70h]
  void *v72[3]; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int64 v73; // [rsp+190h] [rbp+90h]
  void *v74[7]; // [rsp+198h] [rbp+98h] BYREF
  char Destination[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 *v76; // [rsp+1F0h] [rbp+F0h]
  int v77; // [rsp+1F8h] [rbp+F8h]
  int v78; // [rsp+1FCh] [rbp+FCh]
  __int64 *v79; // [rsp+200h] [rbp+100h]
  int v80; // [rsp+208h] [rbp+108h]
  int v81; // [rsp+20Ch] [rbp+10Ch]
  __int64 *v82; // [rsp+210h] [rbp+110h]
  int v83; // [rsp+218h] [rbp+118h]
  int v84; // [rsp+21Ch] [rbp+11Ch]
  _QWORD *v85; // [rsp+220h] [rbp+120h]
  __int64 v86; // [rsp+228h] [rbp+128h]
  int *v87; // [rsp+230h] [rbp+130h]
  __int64 v88; // [rsp+238h] [rbp+138h]
  _WORD Src[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v49 = a4;
  v50 = a3;
  v47 = a5;
  v7 = 0;
  v43 = 0;
  *a4 = 0;
  *a5 = 0;
  v8 = *((_QWORD *)this + 26);
  v9 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 16LL))(a2, v72);
  v10 = *(_QWORD **)std::map<std::wstring,std::unique_ptr<PackageContext>>::at(v8 + 64, v9);
  v44 = v10;
  if ( v73 >= 8 )
    operator delete(v72[0]);
  v73 = 7;
  v72[2] = 0;
  LOWORD(v72[0]) = 0;
  v65 = 0;
  v66 = 0;
  (**(void (__fastcall ***)(__int64, void **))a2)(a2, v59);
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 16LL))(a2, v53);
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 24LL))(a2, v56);
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)a2 + 32LL))(a2, &v62);
  if ( (unsigned int)dword_18005A000 <= 4 )
    ActivityId = 0;
  else
    EventActivityIdControl(3u, &ActivityId);
  v65 = 1;
  if ( (unsigned int)dword_18005A000 > 4 )
  {
    v43 = *(_DWORD *)(*((_QWORD *)this + 26) + 24LL);
    if ( v66 && (v68[0] || v68[1] || v68[2] || v68[3]) )
      v11 = v68;
    else
      v11 = 0;
    v74[4] = &v43;
    v74[5] = (void *)4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F1E5, &ActivityId, v11, 3, v74);
  }
  v45[0] = &v65;
  v45[1] = v53;
  v45[2] = &v47;
  v46 = 1;
  v12 = -1;
  if ( *(_DWORD *)(*((_QWORD *)this + 26) + 24LL) == 18 )
  {
    CosaFolderPath = ProvisioningPaths::GetCosaFolderPath();
    v14 = *((unsigned int *)CosaFolderPath + 2);
    v15 = *(const wchar_t **)CosaFolderPath;
    v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 56LL))(*v10);
    if ( *(_QWORD *)(v16 + 24) >= 8u )
      v16 = *(_QWORD *)v16;
    if ( _wcsnicmp((const wchar_t *)v16, v15, v14) )
    {
      v46 = 0;
      lambda_3ef67bcc2a5ee51b675611ae85f2f4b5_::operator()(v45);
      if ( v64 >= 8 )
        operator delete(v62);
      v64 = 7;
      v63 = 0;
      LOWORD(v62) = 0;
      if ( v58 >= 8 )
        operator delete(v56[0]);
      v58 = 7;
      v57 = 0;
      LOWORD(v56[0]) = 0;
      if ( v55 >= 8 )
        operator delete(v53[0]);
      v55 = 7;
      v54 = 0;
      LOWORD(v53[0]) = 0;
      if ( v61 >= 8 )
        operator delete(v59[0]);
      v61 = 7;
      v60 = 0;
      LOWORD(v59[0]) = 0;
      if ( v65 != 1 )
        return 0;
      goto LABEL_124;
    }
    v17 = 2;
    v18 = 12;
LABEL_82:
    MVProvisionData = CMVEngine::RetrieveMVProvisionData(
                        (_DWORD)this,
                        (_DWORD)v10,
                        v50,
                        v18,
                        v17,
                        (__int64)v49,
                        (__int64)v47);
    v20 = MVProvisionData;
    if ( MVProvisionData >= 0 )
    {
      v46 = 0;
      lambda_3ef67bcc2a5ee51b675611ae85f2f4b5_::operator()(v45);
      if ( v64 >= 8 )
        operator delete(v62);
      v64 = 7;
      v63 = 0;
      LOWORD(v62) = 0;
      if ( v58 >= 8 )
        operator delete(v56[0]);
      v58 = 7;
      v57 = 0;
      LOWORD(v56[0]) = 0;
      if ( v55 >= 8 )
        operator delete(v53[0]);
      v55 = 7;
      v54 = 0;
      LOWORD(v53[0]) = 0;
      if ( v61 >= 8 )
        operator delete(v59[0]);
      v61 = 7;
      v60 = 0;
      LOWORD(v59[0]) = 0;
      if ( v65 != 1 )
        return 0;
LABEL_124:
      v65 = 2;
      _tlgWriteActivityAutoStop<0,4>(&dword_18005A000, &ActivityId);
      return 0;
    }
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      v43 = MVProvisionData;
      LODWORD(v44) = *(_DWORD *)(*((_QWORD *)this + 26) + 24LL);
      v33 = (__int64 *)v56;
      if ( v58 >= 8 )
        v33 = (__int64 *)v56[0];
      v34 = (__int64 *)v53;
      if ( v55 >= 8 )
        v34 = (__int64 *)v53[0];
      v35 = (__int64 *)v59;
      if ( v61 >= 8 )
        v35 = (__int64 *)v59[0];
      v87 = &v43;
      v88 = 4;
      v85 = &v44;
      v86 = 4;
      if ( v33 )
      {
        v36 = -1;
        do
          ++v36;
        while ( *((_WORD *)v33 + v36) );
        v37 = 2 * v36 + 2;
      }
      else
      {
        v33 = &qword_180049F78;
        v37 = 2;
      }
      v82 = v33;
      v83 = v37;
      v84 = 0;
      if ( v34 )
      {
        v38 = -1;
        do
          ++v38;
        while ( *((_WORD *)v34 + v38) );
        v39 = 2 * v38 + 2;
      }
      else
      {
        v34 = &qword_180049F78;
        v39 = 2;
      }
      v79 = v34;
      v80 = v39;
      v81 = 0;
      if ( v35 )
      {
        do
          ++v12;
        while ( *((_WORD *)v35 + v12) );
        v40 = 2 * v12 + 2;
      }
      else
      {
        v35 = &qword_180049F78;
        v40 = 2;
      }
      v76 = v35;
      v77 = v40;
      v78 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &unk_18004E740, &ActivityId, 0, 7, Destination);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x939,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)v20,
      v42);
    v46 = 0;
    lambda_3ef67bcc2a5ee51b675611ae85f2f4b5_::operator()(v45);
    if ( v64 >= 8 )
      operator delete(v62);
    v64 = 7;
    v63 = 0;
    LOWORD(v62) = 0;
    if ( v58 >= 8 )
      operator delete(v56[0]);
    v58 = 7;
    v57 = 0;
    LOWORD(v56[0]) = 0;
    if ( v55 >= 8 )
      operator delete(v53[0]);
    v55 = 7;
    v54 = 0;
    LOWORD(v53[0]) = 0;
    if ( v61 >= 8 )
      operator delete(v59[0]);
    v61 = 7;
    v60 = 0;
    LOWORD(v59[0]) = 0;
    if ( v65 != 1 )
      return v20;
LABEL_40:
    v65 = 2;
    _tlgWriteActivityAutoStop<0,4>(&dword_18005A000, &ActivityId);
    return v20;
  }
  StringFromProvisionState = GetStringFromProvisionState(*(unsigned int *)(v10[2] + 24LL), Src);
  v20 = StringFromProvisionState;
  if ( StringFromProvisionState < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)StringFromProvisionState,
      v41);
    v46 = 0;
    lambda_3ef67bcc2a5ee51b675611ae85f2f4b5_::operator()(v45);
    if ( v64 >= 8 )
      operator delete(v62);
    v64 = 7;
    v63 = 0;
    LOWORD(v62) = 0;
    if ( v58 >= 8 )
      operator delete(v56[0]);
    v58 = 7;
    v57 = 0;
    LOWORD(v56[0]) = 0;
    if ( v55 >= 8 )
      operator delete(v53[0]);
    v55 = 7;
    v54 = 0;
    LOWORD(v53[0]) = 0;
    if ( v61 >= 8 )
      operator delete(v59[0]);
    v61 = 7;
    v60 = 0;
    LOWORD(v59[0]) = 0;
    if ( v65 != 1 )
      return v20;
    goto LABEL_40;
  }
  v22 = operator new(0x50u);
  v51 = v22;
  if ( v22 )
  {
    v71 = 7;
    v70 = 0;
    LOWORD(v69) = 0;
    if ( Src[0] )
    {
      v23 = -1;
      do
        ++v23;
      while ( Src[v23] );
    }
    std::wstring::assign(&v69, Src);
    v43 = 1;
    GetContextIds(v52, v10);
    v7 = 3;
    v43 = 3;
    v24 = (ProvResults *)ProvResults::ProvResults(v22);
  }
  else
  {
    v24 = 0;
  }
  v25 = v24;
  v48 = v24;
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    std::vector<std::wstring>::_Tidy(v52);
  }
  if ( (v7 & 1) != 0 )
  {
    if ( v71 >= 8 )
      operator delete(v69);
    v71 = 7;
    v70 = 0;
    LOWORD(v69) = 0;
  }
  v26 = CMVEngine::InitializeProvisioningSession(this);
  v27 = v26;
  if ( v26 >= 0 )
  {
    memset_0(Destination, 0, 0x81u);
    v28 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 25);
    if ( v28 )
      TraceLoggingCorrelationVector::ToString(v28, Destination);
    v29 = (*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*v10 + 8LL))(*v10, v74);
    if ( *(_QWORD *)(v29 + 24) >= 8u )
      v29 = *(_QWORD *)v29;
    ProvResults::AddPreProvisioningData(v24, (const unsigned __int16 *)v29, Destination);
    if ( v74[3] >= (void *)8 )
      operator delete(v74[0]);
    v30 = (ProvResults **)std::map<std::wstring,std::unique_ptr<ProvResults>>::operator[]((char *)this + 304, v53);
    if ( v30 != &v48 )
    {
      v25 = 0;
      v31 = *v30;
      if ( v24 != *v30 )
      {
        if ( v31 )
        {
          ProvResults::~ProvResults(*v30);
          operator delete(v31);
        }
        *v30 = v24;
      }
    }
    v17 = 1;
    v18 = *(_DWORD *)(*((_QWORD *)this + 26) + 24LL);
    if ( v25 )
    {
      ProvResults::~ProvResults(v25);
      operator delete(v25);
    }
    LODWORD(v10) = (_DWORD)v44;
    goto LABEL_82;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x91E,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
    (const char *)(unsigned int)v26,
    v41);
  if ( v24 )
  {
    ProvResults::~ProvResults(v24);
    operator delete(v24);
  }
  v46 = 0;
  lambda_3ef67bcc2a5ee51b675611ae85f2f4b5_::operator()(v45);
  if ( v64 >= 8 )
    operator delete(v62);
  v64 = 7;
  v63 = 0;
  LOWORD(v62) = 0;
  if ( v58 >= 8 )
    operator delete(v56[0]);
  v58 = 7;
  v57 = 0;
  LOWORD(v56[0]) = 0;
  if ( v55 >= 8 )
    operator delete(v53[0]);
  v55 = 7;
  v54 = 0;
  LOWORD(v53[0]) = 0;
  if ( v61 >= 8 )
    operator delete(v59[0]);
  v61 = 7;
  v60 = 0;
  LOWORD(v59[0]) = 0;
  if ( v65 == 1 )
  {
    v65 = 2;
    _tlgWriteActivityAutoStop<0,4>(&dword_18005A000, &ActivityId);
  }
  return v27;
}

```

## disassembly

```asm
0x18001a6fc  push    rbp
0x18001a6fe  push    rbx
0x18001a6ff  push    rsi
0x18001a700  push    rdi
0x18001a701  push    r12
0x18001a703  push    r13
0x18001a705  push    r14
0x18001a707  push    r15
0x18001a709  lea     rbp, [rsp-388h]
0x18001a711  sub     rsp, 488h
0x18001a718  mov     rax, cs:__security_cookie
0x18001a71f  xor     rax, rsp
0x18001a722  mov     [rbp+3C0h+var_50], rax
0x18001a729  mov     [rbp+3C0h+var_440], r9
0x18001a72d  mov     [rbp+3C0h+var_438], r8
0x18001a731  mov     rdi, rdx
0x18001a734  mov     r13, rcx
0x18001a737  mov     rax, [rbp+3C0h+arg_20]
0x18001a73e  mov     [rsp+4C0h+var_450], rax
0x18001a743  xor     esi, esi
0x18001a745  mov     r14d, esi
0x18001a748  mov     [rsp+4C0h+var_480], esi
0x18001a74c  mov     [r9], rsi
0x18001a74f  mov     [rax], esi
0x18001a751  mov     rbx, [rcx+0D0h]
0x18001a758  mov     rax, [rdx]
0x18001a75b  lea     rdx, [rbp+3C0h+var_348]
0x18001a75f  mov     rcx, rdi
0x18001a762  mov     rax, [rax+10h]
0x18001a766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a76b  nop
0x18001a76c  lea     rcx, [rbx+40h]
0x18001a770  mov     rdx, rax
0x18001a773  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<PackageContext>>::at(std::wstring const &)
0x18001a778  mov     r12, [rax]
0x18001a77b  mov     [rsp+4C0h+var_478], r12
0x18001a780  cmp     [rbp+3C0h+var_330], 8
0x18001a788  jb      short loc_18001A794
0x18001a78a  mov     rcx, [rbp+3C0h+var_348]
0x18001a78e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a794  mov     ebx, 7
0x18001a799  mov     [rbp+3C0h+var_330], rbx
0x18001a7a0  mov     [rbp+3C0h+var_338], rsi
0x18001a7a7  mov     word ptr [rbp+3C0h+var_348], si
0x18001a7ab  mov     [rbp+3C0h+var_390], esi
0x18001a7ae  mov     [rbp+3C0h+var_38C], sil
0x18001a7b2  mov     rax, [rdi]
0x18001a7b5  lea     rdx, [rbp+3C0h+var_3D0]
0x18001a7b9  mov     rcx, rdi
0x18001a7bc  mov     rax, [rax]
0x18001a7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7c4  nop
0x18001a7c5  mov     rax, [rdi]
0x18001a7c8  lea     rdx, [rbp+3C0h+var_410]
0x18001a7cc  mov     rcx, rdi
0x18001a7cf  mov     rax, [rax+10h]
0x18001a7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7d8  nop
0x18001a7d9  mov     rax, [rdi]
0x18001a7dc  lea     rdx, [rbp+3C0h+var_3F0]
0x18001a7e0  mov     rcx, rdi
0x18001a7e3  mov     rax, [rax+18h]
0x18001a7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7ec  nop
0x18001a7ed  mov     rax, [rdi]
0x18001a7f0  lea     rdx, [rbp+3C0h+var_3B0]
0x18001a7f4  mov     rcx, rdi
0x18001a7f7  mov     rax, [rax+20h]
0x18001a7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a800  nop
0x18001a801  mov     eax, cs:dword_18005A000
0x18001a807  cmp     eax, 4
0x18001a80a  jbe     short loc_18001A81B
0x18001a80c  lea     rdx, [rbp+3C0h+ActivityId]; ActivityId
0x18001a810  lea     ecx, [rbx-4]; ControlCode
0x18001a813  call    cs:__imp_EventActivityIdControl
0x18001a819  jmp     short loc_18001A822
0x18001a81b  xorps   xmm0, xmm0
0x18001a81e  movups  xmmword ptr [rbp+3C0h+ActivityId.Data1], xmm0
0x18001a822  mov     [rbp+3C0h+var_390], 1
0x18001a829  mov     eax, cs:dword_18005A000
0x18001a82f  cmp     eax, 4
0x18001a832  jbe     short loc_18001A8A7
0x18001a834  mov     rax, [r13+0D0h]
0x18001a83b  mov     ecx, [rax+18h]
0x18001a83e  mov     [rsp+4C0h+var_480], ecx
0x18001a842  cmp     [rbp+3C0h+var_38C], sil
0x18001a846  jz      short loc_18001A862
0x18001a848  cmp     [rbp+3C0h+var_378], esi
0x18001a84b  jnz     short loc_18001A85C
0x18001a84d  cmp     [rbp+3C0h+var_374], esi
0x18001a850  jnz     short loc_18001A85C
0x18001a852  cmp     [rbp+3C0h+var_370], esi
0x18001a855  jnz     short loc_18001A85C
0x18001a857  cmp     [rbp+3C0h+var_36C], esi
0x18001a85a  jz      short loc_18001A862
0x18001a85c  lea     r9, [rbp+3C0h+var_378]
0x18001a860  jmp     short loc_18001A865
0x18001a862  mov     r9, rsi
0x18001a865  lea     rax, [rsp+4C0h+var_480]
0x18001a86a  mov     [rbp+3C0h+var_308], rax
0x18001a871  mov     [rbp+3C0h+var_300], 4
0x18001a87c  lea     rax, [rbp+3C0h+var_328]
0x18001a883  mov     [rsp+4C0h+var_498], rax
0x18001a888  mov     [rsp+4C0h+var_4A0], 3; int
0x18001a890  lea     r8, [rbp+3C0h+ActivityId]
0x18001a894  lea     rdx, byte_18004F1E5
0x18001a89b  lea     rcx, dword_18005A000
0x18001a8a2  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a8a7  lea     rax, [rbp+3C0h+var_390]
0x18001a8ab  mov     [rsp+4C0h+var_470], rax
0x18001a8b0  lea     rax, [rbp+3C0h+var_410]
0x18001a8b4  mov     [rsp+4C0h+var_468], rax
0x18001a8b9  lea     rax, [rsp+4C0h+var_450]
0x18001a8be  mov     [rsp+4C0h+var_460], rax
0x18001a8c3  mov     [rsp+4C0h+var_458], 1
0x18001a8c8  mov     rax, [r13+0D0h]
0x18001a8cf  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001a8d3  cmp     dword ptr [rax+18h], 12h
0x18001a8d7  jnz     loc_18001A9C6
0x18001a8dd  call    ?GetCosaFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetCosaFolderPath(void)
0x18001a8e2  mov     ebx, [rax+8]
0x18001a8e5  mov     rdi, [rax]
0x18001a8e8  mov     rcx, [r12]
0x18001a8ec  mov     rax, [rcx]
0x18001a8ef  mov     rax, [rax+38h]
0x18001a8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8f8  cmp     qword ptr [rax+18h], 8
0x18001a8fd  jb      short loc_18001A902
0x18001a8ff  mov     rax, [rax]
0x18001a902  mov     r8, rbx; MaxCount
0x18001a905  mov     rdx, rdi; String2
0x18001a908  mov     rcx, rax; String1
0x18001a90b  call    cs:__imp__wcsnicmp
0x18001a911  test    eax, eax
0x18001a913  jz      loc_18001A9B6
0x18001a919  mov     [rsp+4C0h+var_458], sil
0x18001a91e  lea     rcx, [rsp+4C0h+var_470]
0x18001a923  call    _lambda_3ef67bcc2a5ee51b675611ae85f2f4b5___operator__
0x18001a928  nop
0x18001a929  cmp     [rbp+3C0h+var_398], 8
0x18001a92e  jb      short loc_18001A93A
0x18001a930  mov     rcx, [rbp+3C0h+var_3B0]
0x18001a934  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a93a  mov     ebx, 7
0x18001a93f  mov     [rbp+3C0h+var_398], rbx
0x18001a943  mov     [rbp+3C0h+var_3A0], rsi
0x18001a947  mov     word ptr [rbp+3C0h+var_3B0], si
0x18001a94b  cmp     [rbp+3C0h+var_3D8], 8
0x18001a950  jb      short loc_18001A95C
0x18001a952  mov     rcx, [rbp+3C0h+var_3F0]
0x18001a956  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a95c  mov     [rbp+3C0h+var_3D8], rbx
0x18001a960  mov     [rbp+3C0h+var_3E0], rsi
0x18001a964  mov     word ptr [rbp+3C0h+var_3F0], si
0x18001a968  cmp     [rbp+3C0h+var_3F8], 8
0x18001a96d  jb      short loc_18001A979
0x18001a96f  mov     rcx, [rbp+3C0h+var_410]
0x18001a973  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a979  mov     [rbp+3C0h+var_3F8], rbx
0x18001a97d  mov     [rbp+3C0h+var_400], rsi
0x18001a981  mov     word ptr [rbp+3C0h+var_410], si
0x18001a985  cmp     [rbp+3C0h+var_3B8], 8
0x18001a98a  jb      short loc_18001A996
0x18001a98c  mov     rcx, [rbp+3C0h+var_3D0]
0x18001a990  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a996  mov     [rbp+3C0h+var_3B8], rbx
0x18001a99a  mov     [rbp+3C0h+var_3C0], rsi
0x18001a99e  mov     word ptr [rbp+3C0h+var_3D0], si
0x18001a9a2  cmp     [rbp+3C0h+var_390], 1
0x18001a9a6  jnz     loc_18001B03A
0x18001a9ac  mov     ebx, 2
0x18001a9b1  jmp     loc_18001B027
0x18001a9b6  mov     ebx, 2
0x18001a9bb  mov     edi, ebx
0x18001a9bd  lea     r14d, [rbx+0Ah]
0x18001a9c1  jmp     loc_18001AD63
0x18001a9c6  mov     rcx, [r12+10h]
0x18001a9cb  lea     rdx, [rbp+3C0h+Src]
0x18001a9d2  mov     ecx, [rcx+18h]
0x18001a9d5  call    ?GetStringFromProvisionState@@YAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@PEAGK@Z; GetStringFromProvisionState(__MIDL___MIDL_itf_mvengine_0000_0000_0001,ushort *,ulong)
0x18001a9da  mov     edi, eax
0x18001a9dc  test    eax, eax
0x18001a9de  jns     loc_18001AAA9
0x18001a9e4  mov     rcx, [rbp+3C8h]; this
0x18001a9eb  mov     r9d, eax; char *
0x18001a9ee  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001a9f5  mov     edx, 91Bh; void *
0x18001a9fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a9ff  nop
0x18001aa00  mov     [rsp+4C0h+var_458], sil
0x18001aa05  lea     rcx, [rsp+4C0h+var_470]
0x18001aa0a  call    _lambda_3ef67bcc2a5ee51b675611ae85f2f4b5___operator__
0x18001aa0f  nop
0x18001aa10  cmp     [rbp+3C0h+var_398], 8
0x18001aa15  jb      short loc_18001AA21
0x18001aa17  mov     rcx, [rbp+3C0h+var_3B0]
0x18001aa1b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001aa21  mov     [rbp+3C0h+var_398], rbx
0x18001aa25  mov     [rbp+3C0h+var_3A0], rsi
0x18001aa29  mov     word ptr [rbp+3C0h+var_3B0], si
0x18001aa2d  cmp     [rbp+3C0h+var_3D8], 8
0x18001aa32  jb      short loc_18001AA3E
0x18001aa34  mov     rcx, [rbp+3C0h+var_3F0]
0x18001aa38  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001aa3e  mov     [rbp+3C0h+var_3D8], rbx
0x18001aa42  mov     [rbp+3C0h+var_3E0], rsi
0x18001aa46  mov     word ptr [rbp+3C0h+var_3F0], si
0x18001aa4a  cmp     [rbp+3C0h+var_3F8], 8
0x18001aa4f  jb      short loc_18001AA5B
0x18001aa51  mov     rcx, [rbp+3C0h+var_410]
0x18001aa55  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001aa5b  mov     [rbp+3C0h+var_3F8], rbx
0x18001aa5f  mov     [rbp+3C0h+var_400], rsi
0x18001aa63  mov     word ptr [rbp+3C0h+var_410], si
0x18001aa67  cmp     [rbp+3C0h+var_3B8], 8
0x18001aa6c  jb      short loc_18001AA78
0x18001aa6e  mov     rcx, [rbp+3C0h+var_3D0]
0x18001aa72  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001aa78  mov     [rbp+3C0h+var_3B8], rbx
0x18001aa7c  mov     [rbp+3C0h+var_3C0], rsi
0x18001aa80  mov     word ptr [rbp+3C0h+var_3D0], si
0x18001aa84  cmp     [rbp+3C0h+var_390], 1
0x18001aa88  jnz     short loc_18001AAA2
0x18001aa8a  mov     ebx, 2
0x18001aa8f  mov     [rbp+3C0h+var_390], ebx
0x18001aa92  lea     rdx, [rbp+3C0h+ActivityId]
0x18001aa96  lea     rcx, dword_18005A000
0x18001aa9d  call    ??$_tlgWriteActivityAutoStop@$0A@$03@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<0,4>(_tlgProvider_t const *,_GUID const *)
0x18001aaa2  mov     eax, edi
0x18001aaa4  jmp     loc_18001B03C
0x18001aaa9  mov     ecx, 50h ; 'P'; Size
0x18001aaae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aab3  mov     rbx, rax
0x18001aab6  mov     [rbp+3C0h+var_430], rax
0x18001aaba  test    rax, rax
0x18001aabd  jz      short loc_18001AB3A
0x18001aabf  mov     [rbp+3C0h+var_350], 7
0x18001aac7  mov     [rbp+3C0h+var_358], rsi
0x18001aacb  mov     word ptr [rbp+3C0h+var_368], si
0x18001aacf  cmp     [rbp+3C0h+Src], si
0x18001aad6  jnz     short loc_18001AADD
0x18001aad8  mov     r8, rsi
0x18001aadb  jmp     short loc_18001AAF1
0x18001aadd  lea     rax, [rbp+3C0h+Src]
0x18001aae4  mov     r8, r15
0x18001aae7  inc     r8
0x18001aaea  cmp     [rax+r8*2], si
0x18001aaef  jnz     short loc_18001AAE7
0x18001aaf1  lea     rdx, [rbp+3C0h+Src]; Src
0x18001aaf8  lea     rcx, [rbp+3C0h+var_368]; void *
0x18001aafc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001ab01  nop
0x18001ab02  mov     [rsp+4C0h+var_480], 1
0x18001ab0a  mov     rdx, r12
0x18001ab0d  lea     rcx, [rbp+3C0h+var_428]
0x18001ab11  call    GetContextIds
0x18001ab16  nop
0x18001ab17  mov     r14d, 3
0x18001ab1d  mov     [rsp+4C0h+var_480], r14d
0x18001ab22  lea     r9, [rbp+3C0h+var_368]
0x18001ab26  mov     r8, rax
0x18001ab29  lea     rdx, [rbp+3C0h+var_410]
0x18001ab2d  mov     rcx, rbx; void *
0x18001ab30  call    ??0ProvResults@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@0@Z; ProvResults::ProvResults(std::wstring const &,std::vector<std::wstring> const &,std::wstring const &)
0x18001ab35  mov     rdi, rax
0x18001ab38  jmp     short loc_18001AB3D
0x18001ab3a  mov     rdi, rsi
0x18001ab3d  mov     rsi, rdi
0x18001ab40  mov     [rsp+4C0h+var_448], rdi
0x18001ab45  mov     ebx, 2
0x18001ab4a  test    bl, r14b
0x18001ab4d  jz      short loc_18001AB5D
0x18001ab4f  and     r14d, 0FFFFFFFDh
0x18001ab53  lea     rcx, [rbp+3C0h+var_428]
0x18001ab57  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001ab5c  nop
0x18001ab5d  test    r14b, 1
0x18001ab61  jz      short loc_18001AB8A
0x18001ab63  cmp     [rbp+3C0h+var_350], 8
0x18001ab68  jb      short loc_18001AB74
0x18001ab6a  mov     rcx, [rbp+3C0h+var_368]
0x18001ab6e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ab74  mov     [rbp+3C0h+var_350], 7
0x18001ab7c  mov     [rbp+3C0h+var_358], 0
0x18001ab84  xor     eax, eax
0x18001ab86  mov     word ptr [rbp+3C0h+var_368], ax
0x18001ab8a  mov     rcx, r13; this
0x18001ab8d  call    ?InitializeProvisioningSession@CMVEngine@@AEAAJXZ; CMVEngine::InitializeProvisioningSession(void)
0x18001ab92  mov     r14d, eax
0x18001ab95  test    eax, eax
0x18001ab97  jns     loc_18001AC7C
0x18001ab9d  mov     rcx, [rbp+3C8h]; this
0x18001aba4  mov     r9d, eax; char *
0x18001aba7  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001abae  mov     edx, 91Eh; void *
0x18001abb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001abb8  nop
0x18001abb9  xor     esi, esi
0x18001abbb  test    rdi, rdi
  ... truncated ...
```
