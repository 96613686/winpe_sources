# CMsiEngine::ExecuteRecord(ixoEnum,IMsiRecord &)

- ea: `0x1800640c0`
- end: `0x180065ab6`
- name: `?ExecuteRecord@CMsiEngine@@UEAA?AW4iesEnum@@W4ixoEnum@@AEAVIMsiRecord@@@Z`
- size: `6646`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180014528`
- `0x180018ee0`
- `0x180019cc0`
- `0x18001e254`
- `0x18002e870`
- `0x180057804`
- `0x1800640c0`
- `0x180065abc`
- `0x180067fec`
- `0x180077470`
- `0x1800798e4`
- `0x1800c0244`
- `0x1800c6b44`
- `0x1800ee66c`
- `0x1801370c4`
- `0x18013c0b8`
- `0x18013f240`
- `0x18013fa30`
- `0x180153e68`
- `0x180159c38`
- `0x18016cf90`
- `0x180210bb4`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800647f9`
- `KERNEL32!CloseHandle` at `0x18006562f`
- `KERNEL32!CloseHandle` at `0x1800647f9`
- `KERNEL32!CloseHandle` at `0x18006562f`
- `KERNEL32!GetLastError` at `0x180065245`
- `KERNEL32!GetLastError` at `0x1800655d1`
- `KERNEL32!GetLastError` at `0x180065245`
- `KERNEL32!GetLastError` at `0x1800655d1`
- `KERNEL32!GlobalFree` at `0x180064ef7`
- `KERNEL32!GlobalFree` at `0x180064f16`
- `KERNEL32!GlobalFree` at `0x180064fb8`
- `KERNEL32!GlobalFree` at `0x180064ef7`
- `KERNEL32!GlobalFree` at `0x180064f16`
- `KERNEL32!GlobalFree` at `0x180064fb8`
- `KERNEL32!CreateFileW` at `0x1800655bf`
- `KERNEL32!CreateFileW` at `0x1800655bf`

## string_xrefs

- `0x18006465d`: `Rollback`
- `0x1800646d0`: `Rollback`
- `0x1800646e7`: `RollbackCleanup`
- `0x180064757`: `RollbackCleanup`

## pseudocode

```c
__int64 __fastcall CMsiEngine::ExecuteRecord(__int64 *a1, unsigned int a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  unsigned int v4; // r14d
  struct IMsiMessage *v5; // r13
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 result; // rax
  struct IMsiRecord *v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rsi
  _QWORD *v15; // r12
  void (__fastcall *v16)(__int64, __int64, __int64); // rdi
  __int64 v17; // rbx
  __int64 v18; // rsi
  void (__fastcall *v19)(__int64, __int64, __int64); // rdi
  __int64 v20; // rbx
  __int64 v21; // rsi
  void (__fastcall *v22)(__int64, __int64, __int64); // rdi
  __int64 v23; // rbx
  unsigned int v24; // esi
  _QWORD *v25; // rbx
  __int64 v26; // rdi
  int v27; // eax
  void (__fastcall **v28)(_QWORD *, __int64, __int64); // r9
  __int64 v29; // rax
  __int64 v30; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r15
  void (__fastcall *v34)(__int64, __int64, _QWORD); // rdi
  unsigned int v35; // eax
  void *v36; // r12
  __int64 v37; // r14
  unsigned int (__fastcall *v38)(struct IMsiMessage *, const WCHAR *, void **, void **); // rdi
  unsigned int (__fastcall *v39)(struct IMsiMessage *, const WCHAR *, void **, void **); // rdi
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rcx
  unsigned __int16 *v43; // rax
  void *v44; // rax
  void *v45; // rcx
  __int64 v46; // rsi
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r13
  char v51; // al
  __int64 v52; // r14
  struct IMsiRecord *v53; // rax
  __int64 v54; // r13
  unsigned int CurrentDateTime; // eax
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // r14
  __int64 v60; // rbx
  __int64 (__fastcall *v61)(__int64, __int64, struct IMsiMessage **); // rdi
  __int64 v62; // rax
  __int64 v63; // rdi
  __int64 (__fastcall *v64)(_QWORD, _QWORD, _QWORD, _QWORD); // r8
  struct IMsiMessage *v65; // rsi
  __int64 (__fastcall *v66)(struct IMsiMessage *, __int64, struct IMsiRecord **); // rdi
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rbx
  unsigned int (__fastcall *v71)(struct IMsiMessage *, const WCHAR *, void **, void **); // rdi
  __int64 v72; // rax
  int v73; // edi
  int v74; // eax
  void *v75; // rcx
  __int64 v76; // rax
  unsigned int ProductInfoRec; // ebx
  int v78; // ecx
  __int64 v79; // rax
  void (__fastcall *v80)(void *, __int64, __int64); // r14
  __int64 v81; // rdi
  struct IMsiRecord *v82; // rax
  unsigned __int16 *v83; // rsi
  DWORD v84; // eax
  __int64 v85; // rcx
  unsigned __int16 *v86; // rax
  __int64 v87; // rsi
  void (__fastcall *v88)(struct IMsiMessage *, _QWORD, __int64); // r13
  MsiString *v89; // rax
  __int64 v90; // r8
  struct IMsiMessage *v91; // rsi
  __int64 (__fastcall *v92)(struct IMsiRecord *, __int64, __int64, __int64); // r13
  __int64 v93; // rsi
  __int64 v94; // rax
  __int64 v95; // rax
  const WCHAR *v96; // rax
  HANDLE FileW; // rax
  DWORD LastError; // esi
  const unsigned __int16 *v99; // rax
  struct IMsiRecord *v100; // rax
  const WCHAR *v101; // rax
  __int64 v102; // rdx
  struct IMsiRecord *v103; // rax
  __int64 (__fastcall *v104)(void (__fastcall **)(_QWORD *, __int64, __int64), __int64, __int64, __int64); // r13
  __int64 v105; // rsi
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // r13
  unsigned int v109; // eax
  __int64 v110; // rax
  void **v111; // rcx
  unsigned int v112; // eax
  __int64 v113; // rbx
  __int64 v114; // rbx
  int v115; // ebx
  void *v116; // [rsp+40h] [rbp-C0h] BYREF
  void *v117; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v118; // [rsp+50h] [rbp-B0h] BYREF
  void *v119; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v120; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v121; // [rsp+68h] [rbp-98h] BYREF
  __int64 v122; // [rsp+70h] [rbp-90h] BYREF
  char v123; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v124)(__int64, __int64, __int64, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  struct IMsiMessage *v125; // [rsp+88h] [rbp-78h] BYREF
  struct IMsiRecord *v126; // [rsp+90h] [rbp-70h] BYREF
  int v127; // [rsp+98h] [rbp-68h] BYREF
  void *v128; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v129; // [rsp+A8h] [rbp-58h]
  void (__fastcall **v130)(_QWORD *, __int64, __int64); // [rsp+B0h] [rbp-50h] BYREF
  void *v131; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v132; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v133; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v134; // [rsp+D0h] [rbp-30h] BYREF
  int v135; // [rsp+D8h] [rbp-28h]
  HGLOBAL hMem; // [rsp+F0h] [rbp-10h] BYREF
  int v137; // [rsp+F8h] [rbp-8h]
  int v138; // [rsp+FCh] [rbp-4h]
  _BYTE v139[528]; // [rsp+100h] [rbp+0h] BYREF

  v132 = a3;
  LODWORD(v126) = 0;
  v3 = a3;
  v4 = a2;
  v129 = a2;
  v5 = (struct IMsiMessage *)a1;
  v125 = (struct IMsiMessage *)a1;
  v124 = 0;
  if ( !*((_DWORD *)a1 + 22) )
  {
    v10 = PostError(2762);
    v11 = (*(__int64 (__fastcall **)(struct IMsiMessage *, struct IMsiRecord *))(*(_QWORD *)v5 + 208LL))(v5, v10);
    if ( !v10 )
      return v11;
LABEL_20:
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
    return v11;
  }
  LODWORD(qword_1803136B4) = qword_1803136B4 + 1;
  if ( *((_DWORD *)a1 + 20) )
  {
    if ( (*((_BYTE *)a1 + 36) & 0x40) == 0 )
    {
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 104))(a1, 64, 1);
      v121 = 0;
      v76 = CComPointer<IEnumMsiRecord>::operator=(&v121);
      ProductInfoRec = CMsiEngine::CreateProductInfoRec(v5, v76);
      if ( ProductInfoRec != 1
        || (ProductInfoRec = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v5 + 22) + 128LL))(
                               *((_QWORD *)v5 + 22),
                               4,
                               v121),
            ProductInfoRec != 1) )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v124);
        return ProductInfoRec;
      }
      if ( *((_QWORD *)v5 + 116) )
      {
        v24 = CMsiBaselineManager::SendBaselineDefinitionOpcodes();
        if ( v24 != ProductInfoRec )
        {
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
          goto LABEL_118;
        }
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**((_QWORD **)v5 + 22) + 128LL))(
            *((_QWORD *)v5 + 22),
            v4,
            v3);
    goto LABEL_118;
  }
  if ( a2 == 8 && !*((_DWORD *)a1 + 122) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1[16] + 48LL))(a1[16], 3);
    CComPointer<IMsiDatabase>::operator=((char *)v5 + 464, v13);
    v14 = *((_QWORD *)v5 + 58);
    v15 = v132;
    v16 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 120LL);
    v17 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v132 + 72LL))(v132, 1);
    v16(v14, 1, v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v18 = *((_QWORD *)v5 + 58);
    v19 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 120LL);
    v20 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v15 + 72LL))(v15, 2);
    v19(v18, 2, v20);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v21 = *((_QWORD *)v5 + 58);
    v22 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v21 + 120LL);
    v23 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v15 + 72LL))(v15, 3);
    v22(v21, 3, v23);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = 1;
LABEL_118:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v124);
    return v24;
  }
  if ( *((_DWORD *)a1 + 124)
    || *((_DWORD *)a1 + 122)
    || !a1[58]
    || (v12 = *a1,
        *((_DWORD *)a1 + 122) = 1,
        result = (*(__int64 (__fastcall **)(__int64 *, __int64))(v12 + 128))(a1, 8),
        *((_DWORD *)v5 + 122) = 0,
        *((_DWORD *)v5 + 124) = 1,
        (_DWORD)result == 1) )
  {
    if ( ((*(__int64 (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v5 + 96LL))(v5) & 0x40) != 0 )
      goto LABEL_6;
    v10 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiMessage *, const wchar_t *))(*(_QWORD *)v5 + 184LL))(
                                 v5,
                                 L"EXECUTEMODE");
    if ( (*(unsigned int (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 56LL))(v10) )
    {
      v78 = *(_WORD *)(*(__int64 (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 80LL))(v10) & 0xDF;
      if ( v78 == 78 )
      {
        *((_DWORD *)v5 + 15) = 1;
      }
      else if ( v78 == 83 )
      {
        *((_DWORD *)v5 + 15) = 0;
      }
    }
    v32 = *((_QWORD *)v5 + 55);
    v133 = (_QWORD *)((char *)v5 + 440);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    *((_QWORD *)v5 + 55) = (*(__int64 (__fastcall **)(struct IMsiMessage *, const unsigned __int16 *))(*(_QWORD *)v5 + 184LL))(
                             v5,
                             L"SCRIPTFILE");
    (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64))(*(_QWORD *)v5 + 104LL))(v5, 64, 1);
    *((_QWORD *)v5 + 69) = 0;
    v122 = 0;
    v11 = CMsiEngine::CreateProductInfoRec(v5, &v122);
    if ( v11 == 1 )
    {
      v33 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(*((_QWORD *)v5 + 16), 3);
      v120 = (_QWORD *)v33;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 104LL))(v33, 1, 0);
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 104LL))(
        v33,
        2,
        *((unsigned __int16 *)v5 + 16));
      v34 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 104LL);
      v35 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 19) + 216LL))(*((_QWORD *)v5 + 19));
      v34(v33, 3, v35);
      v36 = 0;
      v119 = 0;
      if ( *((_QWORD *)v5 + 35) )
      {
        v79 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(*((_QWORD *)v5 + 16), 2);
        CComPointer<IMsiDatabase>::operator=(&v119, v79);
        v36 = v119;
        (*(void (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v119 + 104LL))(v119, 1, 1);
        v80 = *(void (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v36 + 120LL);
        v81 = (*(__int64 (__fastcall **)(struct IMsiMessage *, _QWORD))(*(_QWORD *)v5 + 144LL))(
                v5,
                *((_QWORD *)v5 + 35));
        v80(v36, 2, v81);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
      }
      v37 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(*((_QWORD *)v5 + 16), 7);
      v121 = v37;
      v117 = &MsiString::s_NullString;
      v116 = &MsiString::s_NullString;
      (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v37 + 128LL))(v37, 2, L"Rollback");
      v38 = *(unsigned int (__fastcall **)(struct IMsiMessage *, const WCHAR *, void **, void **))(*(_QWORD *)v5 + 792LL);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v116 = &MsiString::s_NullString;
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v117 = &MsiString::s_NullString;
      if ( v38(v5, L"Rollback", &v117, &v116) )
      {
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 3, v117);
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 4, v116);
      }
      (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v37 + 128LL))(v37, 5, L"RollbackCleanup");
      v39 = *(unsigned int (__fastcall **)(struct IMsiMessage *, const WCHAR *, void **, void **))(*(_QWORD *)v5 + 792LL);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
      v116 = &MsiString::s_NullString;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
      v117 = &MsiString::s_NullString;
      if ( v39(v5, L"RollbackCleanup", &v117, &v116) )
      {
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 6, v117);
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 7, v116);
      }
      v40 = (*(__int64 (__fastcall **)(struct IMsiMessage *, const unsigned __int16 *))(*(_QWORD *)v5 + 184LL))(
              v5,
              L"IsAdminPackage");
      v41 = v40;
      if ( (*((_BYTE *)v5 + 36) & 2) != 0 )
      {
        LODWORD(v128) = 3;
      }
      else if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v40 + 56LL))(v40) )
      {
        LODWORD(v128) = 4;
      }
      else
      {
        LODWORD(v128) = (4 * (*((_BYTE *)v5 + 36) & 1)) | 1;
      }
      v118 = 0;
      if ( *((_DWORD *)v5 + 15) )
        goto LABEL_90;
      v42 = *((_QWORD *)v5 + 54);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        *((_QWORD *)v5 + 54) = 0;
      }
      CElevate::CElevate((CElevate *)&v127, 1);
      v135 = 260;
      v43 = (unsigned __int16 *)operator new(0x208u);
      v134 = v43;
      if ( v43 )
      {
        v44 = OpenSecuredTempFile(1, v43);
        if ( v44 != (void *)-1LL )
        {
          CloseHandle(v44);
          v131 = &MsiString::s_NullString;
          (*(void (__fastcall **)(void *, unsigned __int16 *, void **))(MsiString::s_NullString + 96LL))(
            &MsiString::s_NullString,
            v134,
            &v131);
          v45 = v131;
          *((_QWORD *)v5 + 54) = v131;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 8LL))(v45);
          v46 = *((_QWORD *)v5 + 16);
          v124 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v46 + 296LL);
          if ( v118 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
          v47 = *((_QWORD *)v5 + 54);
          v118 = 0;
          v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 80LL))(v47);
          v49 = v124(v46, v48, 1, &v118);
          v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))v49;
          if ( v49 )
          {
            (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, 0x1000000, v49);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
            CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v134);
            CElevate::~CElevate((CElevate *)&v127);
            goto LABEL_117;
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
          if ( v135 > 1 )
            operator delete(v134);
          CElevate::~CElevate((CElevate *)&v127);
          v127 = *((_BYTE *)v5 + 579) != 0;
          if ( !(unsigned int)IsTerminalServerInstalled()
            || ((*(__int64 (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v5 + 96LL))(v5) & 3) != 0 )
          {
            v50 = (__int64)v130;
          }
          else
          {
            v50 = (*(__int64 (__fastcall **)(struct IMsiMessage *, const unsigned __int16 *))(*(_QWORD *)v5 + 184LL))(
                    v5,
                    L"ALLUSERS");
            LODWORD(v126) = 1;
            if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v50 + 56LL))(v50) )
            {
              v123 = 1;
              v51 = 1;
LABEL_62:
              if ( (v51 & 1) != 0 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v123 )
                v127 |= 2u;
              v53 = (struct IMsiRecord *)operator new(0x38u);
              v126 = v53;
              if ( v53 )
              {
                v54 = *((_QWORD *)v125 + 16);
                CurrentDateTime = GetCurrentDateTime();
                v53 = (struct IMsiRecord *)CScriptGenerate::CScriptGenerate(
                                             v126,
                                             v118,
                                             *((unsigned __int16 *)v125 + 16),
                                             CurrentDateTime,
                                             (_DWORD)v128,
                                             v127,
                                             v54);
              }
              v5 = v125;
              *((_QWORD *)v125 + 13) = v53;
              if ( !v53 )
              {
                if ( v118 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                if ( v37 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                if ( v36 )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
                if ( v33 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                if ( v122 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
                (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                return 3;
              }
              while ( !CScriptGenerate::InitializeScript(*((CScriptGenerate **)v5 + 13), *((_WORD *)v5 + 302)) )
              {
                if ( !PostScriptWriteError(v5) )
                  goto LABEL_117;
              }
              if ( (!v122 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 4, v122, 0, v5))
                && (!v33 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 5, v33, 0, v5))
                && (!v36 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 5, v36, 0, v5))
                && (!v37 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 6, v37, 0, v5)) )
              {
LABEL_90:
                v56 = *((_QWORD *)v5 + 55);
                if ( !v56
                  || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v56 + 56LL))(v56)
                  || *((_QWORD *)v5 + 14) )
                {
                  goto LABEL_91;
                }
                v137 = 260;
                v138 = 260;
                v85 = *((_QWORD *)v5 + 55);
                hMem = v139;
                v86 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 80LL))(v85);
                ExpandPath(v86, (__int64)&hMem, 0);
                (*(void (__fastcall **)(_QWORD, HGLOBAL, __int64))(**((_QWORD **)v5 + 55) + 96LL))(
                  *((_QWORD *)v5 + 55),
                  hMem,
                  (__int64)v5 + 440);
                v87 = *((_QWORD *)v5 + 55);
                v88 = *(void (__fastcall **)(struct IMsiMessage *, _QWORD, __int64))(*(_QWORD *)v5 + 160LL);
                v89 = MsiString::MsiString((MsiString *)&v126, L"SCRIPTFILE");
                v90 = v87;
                v91 = v125;
                v88(v125, *(_QWORD *)v89, v90);
                (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v126 + 16LL))(v126);
                if ( (_DWORD)v128 == 3 )
                {
                  v126 = (struct IMsiRecord *)*((_QWORD *)v91 + 16);
                  v92 = *(__int64 (__fastcall **)(struct IMsiRecord *, __int64, __int64, __int64))(*(_QWORD *)v126
                                                                                                 + 296LL);
                  v93 = CComPointer<IEnumMsiRecord>::operator=(&v118);
                  v94 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v133 + 80LL))(*v133);
                  v95 = v92(v126, v94, 1, v93);
                  CComPointer<IMsiDatabase>::operator=(&v124, v95);
LABEL_168:
                  if ( v124 )
                  {
                    (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64 (__fastcall *)(__int64, __int64, __int64, __int64 *)))(*(_QWORD *)v125 + 24LL))(
                      v125,
                      0x1000000,
                      v124);
LABEL_119:
                    if ( v137 > 260 )
                      GlobalFree(hMem);
                    v137 = 260;
                    hMem = v139;
                    goto LABEL_117;
                  }
                  v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))operator new(0x38u);
                  if ( !v130 )
                  {
                    *((_QWORD *)v125 + 14) = 0;
                    goto LABEL_119;
                  }
                  v108 = *((_QWORD *)v125 + 16);
                  v109 = GetCurrentDateTime();
                  v110 = CScriptGenerate::CScriptGenerate(
                           v130,
                           v118,
                           *((unsigned __int16 *)v125 + 16),
                           v109,
                           (_DWORD)v128,
                           0,
                           v108);
                  v5 = v125;
                  *((_QWORD *)v125 + 14) = v110;
                  if ( !v110 )
                    goto LABEL_119;
                  while ( !CScriptGenerate::InitializeScript(*((CScriptGenerate **)v5 + 14), *((_WORD *)v5 + 302)) )
                  {
                    if ( !PostScriptWriteError(v5) )
                      goto LABEL_119;
                  }
                  if ( v122 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 4, v122, 0, v5)
                    || v33 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 5, v33, 0, v5)
                    || v36 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 5, v36, 0, v5)
                    || v37 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 6, v37, 0, v5) )
                  {
                    goto LABEL_119;
                  }
                  if ( v137 > 260 )
                    GlobalFree(hMem);
LABEL_91:
                  if ( *((_QWORD *)v5 + 116) )
                  {
                    LODWORD(v126) = CMsiBaselineManager::SendBaselineDefinitionOpcodes();
                    if ( (_DWORD)v126 != 1 )
                    {
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
                      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                      v24 = (unsigned int)v126;
                      goto LABEL_118;
                    }
                  }
                  if ( v118 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                  if ( v37 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                  if ( v36 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
                  if ( v33 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                  if ( v122 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
                  (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                  v3 = v132;
                  v4 = v129;
LABEL_6:
                  if ( !*((_QWORD *)v5 + 13) && !*((_QWORD *)v5 + 14) )
                    return 1;
                  if ( *((_DWORD *)v5 + 120) != 1 )
                  {
                    v69 = *((_QWORD *)v5 + 16);
                    *((_DWORD *)v5 + 120) = 1;
                    v70 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 48LL))(v69, 3);
                    v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))v70;
                    v128 = &MsiString::s_NullString;
                    v119 = &MsiString::s_NullString;
                    (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v70 + 128LL))(
                      v70,
                      1,
                      L"GenerateScript");
                    v71 = *(unsigned int (__fastcall **)(struct IMsiMessage *, const WCHAR *, void **, void **))(*(_QWORD *)v5 + 792LL);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v119 + 16LL))(v119);
                    v119 = &MsiString::s_NullString;
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v128 + 16LL))(v128);
                    v128 = &MsiString::s_NullString;
                    if ( v71(v5, L"GenerateScript", &v128, &v119) )
                    {
                      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v70 + 120LL))(v70, 2, v128);
                      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v70 + 120LL))(v70, 3, v119);
                    }
                    v72 = *(_QWORD *)v5;
                    v73 = *((_DWORD *)v5 + 122);
                    *((_DWORD *)v5 + 122) = 1;
                    v74 = (*(__int64 (__fastcall **)(struct IMsiMessage *, __int64, __int64))(v72 + 24))(
                            v5,
                            0x8000000,
                            v70);
                    v75 = v119;
                    if ( v74 == 2 )
                    {
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v119 + 16LL))(v119);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v128 + 16LL))(v128);
                      v111 = (void **)&v130;
                      goto LABEL_189;
                    }
                    *((_DWORD *)v5 + 122) = v73;
                    *((_DWORD *)v5 + 123) = 0;
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v75 + 16LL))(v75);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v128 + 16LL))(v128);
                    if ( v70 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
                  }
                  if ( v4 == 25 )
                  {
                    v112 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 2);
                    if ( v112 <= 1 )
                    {
                      v115 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 1);
                      *((_QWORD *)v5 + 69) += (int)(v115
                                                  * (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 3));
                      goto LABEL_10;
                    }
                    if ( v112 == 2 )
                    {
                      v113 = (__int64)(*(int (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 1) << 32;
                      v114 = (*(unsigned int (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 3) + v113;
                      *((_QWORD *)v5 + 69) += v114;
                      (*(void (__fastcall **)(_QWORD *, __int64))(*v3 + 104LL))(v3, 2);
                      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v3 + 104LL))(v3, 3, 1);
                      (*(void (__fastcall **)(_QWORD *, __int64, _QWORD))(*v3 + 104LL))(v3, 1, (unsigned int)v114);
                      goto LABEL_11;
                    }
                  }
                  else
                  {
                    if ( v4 != 72 )
                    {
LABEL_10:
                      if ( v4 != 8 )
                      {
LABEL_11:
                        v6 = *((_QWORD *)v5 + 71);
                        if ( !v6
                          || ((*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v6 + 104LL))(v6, 1, 2),
                              (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v5 + 71) + 104LL))(
                                *((_QWORD *)v5 + 71),
                                2,
                                1),
                              (*(unsigned int (__fastcall **)(struct IMsiMessage *, __int64, _QWORD))(*(_QWORD *)v5 + 24LL))(
                                v5,
                                167772160,
                                *((_QWORD *)v5 + 71)) != 2) )
                        {
                          v7 = *((_QWORD *)v5 + 13);
                          if ( v7 && !(unsigned __int8)WriteScriptRecord(v7, v4, v3, 0, v5) )
                            return 3;
                          v8 = *((_QWORD *)v5 + 14);
                          if ( v8 && !(unsigned __int8)WriteScriptRecord(v8, v4, v3, 0, v5) )
                            goto LABEL_199;
                          return 1;
                        }
LABEL_190:
                        v24 = 2;
                        goto LABEL_118;
                      }
                      v25 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(
                                        *((_QWORD *)v5 + 16),
                                        1);
                      v132 = v25;
                      v26 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 72LL))(v3, 2);
                      v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 56LL))(v26);
                      v28 = (void (__fastcall **)(_QWORD *, __int64, __int64))*v25;
                      v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))*v25;
                      if ( v27 )
                      {
                        v28[15](v25, 1, v26);
                      }
                      else
                      {
                        v52 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 72LL))(v3, 1);
                        v130[15](v25, 1, v52);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                      }
                      v29 = *(_QWORD *)v5;
                      *((_DWORD *)v5 + 122) = 1;
                      if ( (*(unsigned int (__fastcall **)(struct IMsiMessage *, __int64, _QWORD *))(v29 + 24))(
                             v5,
                             150994944,
                             v25) != 2 )
                      {
                        *((_DWORD *)v5 + 122) = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                        if ( !v25 )
                        {
LABEL_36:
                          v4 = v129;
                          goto LABEL_11;
                        }
                        v30 = *v25;
                        v31 = v25;
LABEL_35:
                        (*(void (__fastcall **)(_QWORD *))(v30 + 16))(v31);
                        goto LABEL_36;
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                      v111 = (void **)&v132;
LABEL_189:
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v111);
                      goto LABEL_190;
                    }
                    if ( !(*(unsigned int (__fastcall **)(_QWORD *, __int64))(*v3 + 32LL))(v3, 3) )
                      goto LABEL_11;
                    v57 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 80LL))(v3, 1);
                    v120 = &MsiString::s_NullString;
                    (*(void (__fastcall **)(void *, __int64, _QWORD **))(MsiString::s_NullString + 96LL))(
                      &MsiString::s_NullString,
                      v57,
                      &v120);
                    v58 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64))(*v120 + 176LL))(v120, 6, 92);
                    v59 = *((_QWORD *)v5 + 16);
                    v60 = v58;
                    v125 = 0;
                    v61 = *(__int64 (__fastcall **)(__int64, __int64, struct IMsiMessage **))(*(_QWORD *)v59 + 120LL);
                    v62 = (*(__int64 (__fastcall **)(_QWORD *))(*v120 + 80LL))(v120);
                    v63 = v61(v59, v62, &v125);
                    v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))v63;
                    if ( v63 )
                    {
                      v64 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v63;
                    }
                    else
                    {
                      v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))(*(__int64 (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v125 + 112LL))(v125);
                      v64 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v124;
                      if ( !v124 )
                      {
                        v65 = v125;
                        LODWORD(v126) = 0;
                        v66 = *(__int64 (__fastcall **)(struct IMsiMessage *, __int64, struct IMsiRecord **))(*(_QWORD *)v125 + 168LL);
                        v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 80LL))(v60);
                        v68 = v66(v65, v67, &v126);
                        v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))v68;
                        if ( !v68 )
                        {
                          *((_QWORD *)v5 + 69) += (unsigned int)v126;
                          if ( v125 )
                            (*(void (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v125 + 16LL))(v125);
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                          v31 = v120;
                          v30 = *v120;
                          goto LABEL_35;
                        }
                        v64 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v68;
                      }
                    }
                    (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD)))(*(_QWORD *)v5 + 24LL))(
                      v5,
                      0x1000000,
                      v64);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v125);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                    (*(void (__fastcall **)(_QWORD *))(*v120 + 16LL))(v120);
                  }
LABEL_199:
                  v24 = 3;
                  goto LABEL_118;
                }
                v96 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v91 + 55) + 80LL))(*((_QWORD *)v91 + 55));
                FileW = CreateFileW(v96, 0x40000000u, 1u, 0, 2u, 0x100000u, 0);
                if ( FileW == (HANDLE)-1LL )
                {
                  LastError = GetLastError();
                  v99 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v133 + 80LL))(*v133);
                  v100 = PostError(1101, v99, LastError);
                  CComPointer<IMsiDatabase>::operator=(&v124, v100);
                  (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64 (__fastcall *)(__int64, __int64, __int64, __int64 *)))(*(_QWORD *)v125 + 24LL))(
                    v125,
                    0x1000000,
                    v124);
                }
                else
                {
                  CloseHandle(FileW);
                  CElevate::CElevate((CElevate *)&v127, 1);
                  v101 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v91 + 55) + 80LL))(*((_QWORD *)v91 + 55));
                  LOBYTE(v102) = 1;
                  v103 = LockdownPath(v101, v102);
                  v126 = v103;
                  if ( !v103 )
                  {
                    v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))*((_QWORD *)v91 + 16);
                    v104 = (__int64 (__fastcall *)(void (__fastcall **)(_QWORD *, __int64, __int64), __int64, __int64, __int64))*((_QWORD *)*v130 + 37);
                    v105 = CComPointer<IEnumMsiRecord>::operator=(&v118);
                    v106 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v133 + 80LL))(*v133);
                    v107 = v104(v130, v106, 1, v105);
                    CComPointer<IMsiDatabase>::operator=(&v124, v107);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v126);
                    CElevate::~CElevate((CElevate *)&v127);
                    goto LABEL_168;
                  }
                  (*(void (__fastcall **)(struct IMsiMessage *, __int64, struct IMsiRecord *))(*(_QWORD *)v91 + 24LL))(
                    v91,
                    0x1000000,
                    v103);
                  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v126);
                  CElevate::~CElevate((CElevate *)&v127);
                }
                if ( v137 > 260 )
                  GlobalFree(hMem);
                v137 = 260;
                hMem = v139;
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
                (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                v24 = 3;
                goto LABEL_118;
              }
LABEL_117:
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
              (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
              v24 = 3;
              goto LABEL_118;
            }
          }
          v51 = (char)v126;
          v123 = 0;
          goto LABEL_62;
        }
        v83 = v134;
        v84 = GetLastError();
        v82 = PostError(1336, v84, v83);
      }
      else
      {
        v135 = 0;
        v82 = PostError(2346);
      }
      CComPointer<IMsiDatabase>::operator=(&v124, v82);
      v24 = (*(__int64 (__fastcall **)(struct IMsiMessage *, __int64 (__fastcall *)(__int64, __int64, __int64, __int64 *)))(*(_QWORD *)v5 + 208LL))(
              v5,
              v124);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v134);
      CElevate::~CElevate((CElevate *)&v127);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_118;
    }
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x1800640c0  mov     [rsp-8+arg_18], rbx
0x1800640c5  push    rbp
0x1800640c6  push    rsi
0x1800640c7  push    rdi
0x1800640c8  push    r12
0x1800640ca  push    r13
0x1800640cc  push    r14
0x1800640ce  push    r15
0x1800640d0  lea     rbp, [rsp-220h]
0x1800640d8  sub     rsp, 320h
0x1800640df  mov     rax, cs:__security_cookie
0x1800640e6  xor     rax, rsp
0x1800640e9  mov     [rbp+250h+var_40], rax
0x1800640f0  xor     edi, edi
0x1800640f2  mov     [rbp+250h+var_290], r8
0x1800640f6  mov     dword ptr [rbp+250h+var_2C0], edi
0x1800640f9  mov     r15, r8
0x1800640fc  mov     r14d, edx
0x1800640ff  mov     [rbp+250h+var_2A8], edx
0x180064102  mov     r13, rcx
0x180064105  mov     [rbp+250h+var_2C8], rcx
0x180064109  mov     esi, edi
0x18006410b  mov     [rbp+250h+var_2D0], rdi
0x18006410f  cmp     [rcx+58h], edi
0x180064112  jz      loc_18006427E
0x180064118  lea     ebx, [rdi+1]
0x18006411b  add     dword ptr cs:qword_1803136B4, ebx
0x180064121  cmp     [rcx+50h], edi
0x180064124  jnz     loc_180064FC9
0x18006412a  cmp     edx, 8
0x18006412d  jz      loc_18006431E
0x180064133  cmp     [rcx+1F0h], edi
0x180064139  jz      loc_1800642CD
0x18006413f  mov     rax, [r13+0]
0x180064143  mov     rcx, r13
0x180064146  mov     rax, [rax+60h]
0x18006414a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006414f  mov     r12d, 3
0x180064155  test    al, 40h
0x180064157  jz      loc_1800644F8
0x18006415d  cmp     [r13+68h], rdi
0x180064161  jz      loc_1800642BE
0x180064167  cmp     [r13+1E0h], ebx
0x18006416e  jnz     loc_180064D19
0x180064174  cmp     r14d, 19h
0x180064178  jz      loc_180065966
0x18006417e  cmp     r14d, 48h ; 'H'
0x180064182  jz      loc_180064BB4
0x180064188  cmp     r14d, 8
0x18006418c  jz      loc_180064429
0x180064192  mov     rcx, [r13+238h]
0x180064199  test    rcx, rcx
0x18006419c  jz      short loc_1800641F4
0x18006419e  mov     rax, [rcx]
0x1800641a1  mov     edx, 1
0x1800641a6  mov     rax, [rax+68h]
0x1800641aa  lea     r8d, [rdx+1]
0x1800641ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641b3  mov     rcx, [r13+238h]
0x1800641ba  mov     edx, 2
0x1800641bf  mov     rax, [rcx]
0x1800641c2  lea     r8d, [rdx-1]
0x1800641c6  mov     rax, [rax+68h]
0x1800641ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641cf  mov     rax, [r13+0]
0x1800641d3  mov     edx, 0A000000h
0x1800641d8  mov     r8, [r13+238h]
0x1800641df  mov     rcx, r13
0x1800641e2  mov     rax, [rax+18h]
0x1800641e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800641eb  cmp     eax, 2
0x1800641ee  jz      loc_18006595C
0x1800641f4  mov     rcx, [r13+68h]
0x1800641f8  test    rcx, rcx
0x1800641fb  jz      short loc_180064214
0x1800641fd  xor     r9d, r9d
0x180064200  mov     qword ptr [rsp+350h+dwCreationDisposition], r13
0x180064205  mov     r8, r15
0x180064208  mov     edx, r14d
0x18006420b  call    ?WriteScriptRecord@@YA_NPEAVCScriptGenerate@@W4ixoEnum@@AEAVIMsiRecord@@_NAEAUIMsiMessage@@@Z; WriteScriptRecord(CScriptGenerate *,ixoEnum,IMsiRecord &,bool,IMsiMessage &)
0x180064210  test    al, al
0x180064212  jz      short loc_180064265
0x180064214  mov     rcx, [r13+70h]
0x180064218  test    rcx, rcx
0x18006421b  jnz     loc_180065A93
0x180064221  test    rsi, rsi
0x180064224  jz      short loc_180064235
0x180064226  mov     rcx, [rsi]
0x180064229  mov     rax, [rcx+10h]
0x18006422d  mov     rcx, rsi
0x180064230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064235  mov     eax, 1
0x18006423a  mov     rcx, [rbp+250h+var_40]
0x180064241  xor     rcx, rsp; StackCookie
0x180064244  call    __security_check_cookie
0x180064249  mov     rbx, [rsp+350h+arg_18]
0x180064251  add     rsp, 320h
0x180064258  pop     r15
0x18006425a  pop     r14
0x18006425c  pop     r13
0x18006425e  pop     r12
0x180064260  pop     rdi
0x180064261  pop     rsi
0x180064262  pop     rbp
0x180064263  retn
0x180064265  test    rsi, rsi
0x180064268  jz      short loc_180064279
0x18006426a  mov     rax, [rsi]
0x18006426d  mov     rcx, rsi
0x180064270  mov     rax, [rax+10h]
0x180064274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064279  mov     eax, r12d
0x18006427c  jmp     short loc_18006423A
0x18006427e  mov     ecx, 0ACAh; int
0x180064283  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x180064288  mov     rdx, [r13+0]
0x18006428c  mov     rbx, rax
0x18006428f  mov     rcx, r13
0x180064292  mov     rax, [rdx+0D0h]
0x180064299  mov     rdx, rbx
0x18006429c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642a1  mov     edi, eax
0x1800642a3  test    rbx, rbx
0x1800642a6  jz      short loc_1800642B7
0x1800642a8  mov     rcx, [rbx]
0x1800642ab  mov     rax, [rcx+10h]
0x1800642af  mov     rcx, rbx
0x1800642b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642b7  mov     eax, edi
0x1800642b9  jmp     loc_18006423A
0x1800642be  cmp     [r13+70h], rdi
0x1800642c2  jz      loc_180064221
0x1800642c8  jmp     loc_180064167
0x1800642cd  cmp     [rcx+1E8h], edi
0x1800642d3  jnz     loc_18006413F
0x1800642d9  mov     r8, [rcx+1D0h]
0x1800642e0  test    r8, r8
0x1800642e3  jz      loc_18006413F
0x1800642e9  mov     rax, [rcx]
0x1800642ec  mov     edx, 8
0x1800642f1  mov     [rcx+1E8h], ebx
0x1800642f7  mov     rax, [rax+80h]
0x1800642fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064303  mov     [r13+1E8h], edi
0x18006430a  mov     [r13+1F0h], ebx
0x180064311  cmp     eax, ebx
0x180064313  jnz     loc_18006423A
0x180064319  jmp     loc_18006413F
0x18006431e  cmp     [rcx+1E8h], edi
0x180064324  jnz     loc_180064133
0x18006432a  mov     rcx, [rcx+80h]
0x180064331  lea     r14, [r13+1D0h]
0x180064338  mov     r15d, 3
0x18006433e  mov     edx, r15d
0x180064341  mov     rax, [rcx]
0x180064344  mov     rax, [rax+30h]
0x180064348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006434d  mov     rdx, rax
0x180064350  mov     rcx, r14
0x180064353  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x180064358  mov     rsi, [r14]
0x18006435b  mov     r12, [rbp+250h+var_290]
0x18006435f  mov     rcx, r12
0x180064362  mov     rax, [rsi]
0x180064365  mov     rdx, [r12]
0x180064369  mov     rdi, [rax+78h]
0x18006436d  mov     rax, [rdx+48h]
0x180064371  mov     edx, ebx
0x180064373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064378  mov     rbx, rax
0x18006437b  lea     edx, [r15-2]
0x18006437f  mov     r8, rax
0x180064382  mov     rcx, rsi
0x180064385  mov     rax, rdi
0x180064388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006438d  mov     rcx, [rbx]
0x180064390  mov     rax, [rcx+10h]
0x180064394  mov     rcx, rbx
0x180064397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006439c  mov     rdx, [r12]
0x1800643a0  lea     r13d, [r15-1]
0x1800643a4  mov     rsi, [r14]
0x1800643a7  mov     rcx, r12
0x1800643aa  mov     rax, [rsi]
0x1800643ad  mov     rdi, [rax+78h]
0x1800643b1  mov     rax, [rdx+48h]
0x1800643b5  mov     edx, r13d
0x1800643b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643bd  mov     rbx, rax
0x1800643c0  mov     r8, rax
0x1800643c3  mov     rax, rdi
0x1800643c6  mov     edx, r13d
0x1800643c9  mov     rcx, rsi
0x1800643cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643d1  mov     rcx, [rbx]
0x1800643d4  mov     rax, [rcx+10h]
0x1800643d8  mov     rcx, rbx
0x1800643db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643e0  mov     rsi, [r14]
0x1800643e3  mov     edx, r15d
0x1800643e6  mov     r8, [r12]
0x1800643ea  mov     rcx, r12
0x1800643ed  mov     rax, [rsi]
0x1800643f0  mov     rdi, [rax+78h]
0x1800643f4  mov     rax, [r8+48h]
0x1800643f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800643fd  mov     rbx, rax
0x180064400  mov     r8, rax
0x180064403  mov     rax, rdi
0x180064406  mov     edx, r15d
0x180064409  mov     rcx, rsi
0x18006440c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064411  mov     rcx, [rbx]
0x180064414  mov     rax, [rcx+10h]
0x180064418  mov     rcx, rbx
0x18006441b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064420  lea     esi, [r15-2]
0x180064424  jmp     loc_180064ED5
0x180064429  mov     rcx, [r13+80h]
0x180064430  mov     r14d, 1
0x180064436  mov     edx, r14d
0x180064439  mov     rax, [rcx]
0x18006443c  mov     rax, [rax+30h]
0x180064440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064445  mov     rbx, rax
0x180064448  mov     [rbp+250h+var_290], rax
0x18006444c  mov     rax, [r15]
0x18006444f  lea     edx, [r14+1]
0x180064453  mov     rcx, r15
0x180064456  mov     rax, [rax+48h]
0x18006445a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006445f  mov     rdi, rax
0x180064462  mov     rcx, rdi
0x180064465  mov     rax, [rax]
0x180064468  mov     rax, [rax+38h]
0x18006446c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064471  mov     r9, [rbx]
0x180064474  mov     edx, r14d
0x180064477  mov     [rbp+250h+var_2A0], r9
0x18006447b  test    eax, eax
0x18006447d  jz      loc_180064917
0x180064483  mov     rax, [r9+78h]
0x180064487  mov     r8, rdi
0x18006448a  mov     rcx, rbx
0x18006448d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064492  mov     rax, [r13+0]
0x180064496  mov     r8, rbx
0x180064499  mov     edx, 9000000h
0x18006449e  mov     dword ptr [r13+1E8h], 1
0x1800644a9  mov     rcx, r13
0x1800644ac  mov     r14, rbx
0x1800644af  mov     rax, [rax+18h]
0x1800644b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644b8  mov     rcx, rdi
0x1800644bb  cmp     eax, 2
0x1800644be  jz      loc_180065947
0x1800644c4  mov     dword ptr [r13+1E8h], 0
0x1800644cf  mov     rax, [rdi]
0x1800644d2  mov     rax, [rax+10h]
0x1800644d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644db  test    rbx, rbx
0x1800644de  jz      short loc_1800644EF
0x1800644e0  mov     rax, [rbx]
0x1800644e3  mov     rcx, rbx
0x1800644e6  mov     rax, [rax+10h]
0x1800644ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800644ef  mov     r14d, [rbp+250h+var_2A8]
0x1800644f3  jmp     loc_180064192
0x1800644f8  mov     rax, [r13+0]
0x1800644fc  lea     rdx, aExecutemode; "EXECUTEMODE"
0x180064503  mov     rcx, r13
0x180064506  mov     rax, [rax+0B8h]
0x18006450d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064512  mov     rbx, rax
0x180064515  mov     rcx, rbx
0x180064518  mov     rax, [rax]
0x18006451b  mov     rax, [rax+38h]
0x18006451f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064524  test    eax, eax
0x180064526  jnz     loc_18006509A
0x18006452c  lea     rdi, [r13+1B8h]
0x180064533  xor     r14d, r14d
0x180064536  mov     rcx, [rdi]
0x180064539  mov     [rbp+250h+var_288], rdi
0x18006453d  test    rcx, rcx
0x180064540  jnz     loc_1800650D6
0x180064546  mov     rax, [r13+0]
0x18006454a  lea     rdx, aScriptfile_0; "SCRIPTFILE"
0x180064551  mov     rcx, r13
0x180064554  mov     rax, [rax+0B8h]
0x18006455b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064560  mov     [rdi], rax
0x180064563  mov     edx, 40h ; '@'
0x180064568  mov     rax, [r13+0]
0x18006456c  mov     rcx, r13
0x18006456f  lea     r8d, [rdx-3Fh]
0x180064573  mov     rax, [rax+68h]
0x180064577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006457c  lea     rdx, [rsp+350h+var_2E0]
0x180064581  mov     [r13+228h], r14
  ... truncated ...
```
